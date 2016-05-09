



操作浏览器历史
Manipulating the browser history





wukan@staff.sina.com.cn


https://developer.mozilla.org/en/DOM/Manipulating_the_browser_history
DOM中的window对象通过window.history方法提供了对浏览器历史记录的读取，让你可以在用户的访问记录中前进和后退。
从HTML5开始，我们可以开始操作这个历史记录堆栈。

History
使用back(), forward(),和go()方法可以在用户的历史记录中前进和后退

前进和后退
后退：
window.history.back();
这个方法会像用户点击了浏览器工具栏上的返回键一样。
同样的，也可以用以下方法产生用户前进行为：
window.history.forward();
移动到历史记录中特定的位置
你可以使用go()方法从session历史中载入特定的页面。
向后移动一页：
window.history.go(-1);
向前移动一页：
window.history.go(1);
类似的，你可以前进或者后退多页。
还可以通过检查浏览器历史记录的length属性来找到历史记录堆栈中的页面总数。
var numberOfEntries = window.history.length;
注意:  IE支持向go()方法传URL参数。


添加和修改history实体
自Gecko2开始引入
(Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1)
HTML5引入了histtory.pushState() 和history.replaceState()这两个方法，他们允许添加和修改history实体。同时，这些方法会和window.onpostate事件一起工作。
使用history.pushState()方法来修改referrer,这种方法可以被用在经过修改状态后而为xmlhttpRequest对象创建的http header中。这个referrer会是创建XMLHttpRequest 时document的URL。
pushState 用于向 history 添加当前页面的记录，而 replaceState 和 pushState 的用法完全一样，唯一的区别就是它用于修改当前页面在 history 中的记录。
例子
假设http://mozilla.org/foo.html页面执行了一下JS
var stateObj = { foo: "bar" };
history.pushState(stateObj, "page 2", "bar.html");
这种方法将会使url地址栏显示http://mozilla.org/bar.html，但浏览器不会加载bar.html页面，即使这个页面存在也不会加载。
现在再次假设用户继续访问http://google.com，然后点击后退。这时，url地址栏将会，http://mozilla.org/bar.html，页面会得到popstate事件（chrome），这个状态对象会包含一个stateObj的copy。这个页面看起来像foo.html。+
这时，我们再次点击后退，URL将变成http://mozilla.org/foo.html，document将得到另一个popstate事件和为null的state对象。这次的返回动作并没有改变文档的内容。（也许会过一会尝试加载…chrome）
pushState方法
pushState()有三个参数:state对象，标题(现在是被忽略，未作处理)，URL(可选)。具体细节：
•	state对象 – state对象是一个JavaScript对象，它关系到由pushState()方法创建出来的新的history实体。用以存储关于你所要插入到历史记录的条目的相关信息。 State对象可以是任何Json字符串。因为firefox会使用用户的硬盘来存取state对象，这个对象的最大存储空间为640k。如果大于这个数值，则pushState()方法会抛出一个异常。如果确实需要更多的空间来存储，请使用本地存储。
•	title —firefox现在回忽略这个参数，虽然它可能将来会被使用上。而现在最安全的使用方式是传一个空字符串，以防止将来的修改。或者可以传一个简短的标题来表示state
•	URL —这个参数用来传递新的history实体的URL，注意浏览器将不会在调用pushState()方法后加载这个URL。但也许会过一会尝试加载这个URL。比如在用户重启了浏览器后，新的url可以不是绝对路径。如果是相对路径，那么它会相对于现有的url。新的url必须和现有的url同域，否则pushState()将抛出异常。这个参数是选填的，如果为空，则会被置为document当前的url。
某种意义上来说，调用pushState()方法很像设置了window.location = "#foo",这两者都会创建和激活另一个关联到当前document的history实体，但pushState()另外有一些优点：
λ	新的url可以是任何和当前url同域的url，相比之下，如果只设置hash，window.location会保持在同一个document。
λ	如果不需要，你可以不修改url。对比而言，设置window.location = "#foo";仅产生新的history实体，如果你当前的hash不是#foo
λ	你可以将任意的数据与你的新history实体关联。使用基于hash的方法，需要将所有相关的数据编码为一个短字符串。
注意，pushState()方法不会使hashchange时间发生，即使是新旧url只是hash不同。
replaceState()方法
history.replaceState() 用起来很像pushState()，除了replaceState()是用来修改当前的history实体而不是创建一个新的。这个方法有时会很有用，当你需要对某些用户行为作反应而更新一个state对象或者当前history实体时，可以使用它来更新state对象或者当前history实体的url。
popstate事件
当history实体被改变时，popstate事件将会发生。如果history实体是有pushState和replaceState方法产生的，popstate事件的state属性会包含一份来自history实体的state对象的拷贝
详见window.onpopstate
读取当前的state
读取现有state
当页面加载时，它可能会有一个非空的state对象。这可能发生在当页面设置一个state对象(使用pushState或者replaceState)之后用户重启了浏览器。当页面重新加载，页面将收到onload事件，但不会有popstate事件。然而，如果你读取history.state属性，将在popstate事件发生后得到这个state对象
var currentState = history.state;

