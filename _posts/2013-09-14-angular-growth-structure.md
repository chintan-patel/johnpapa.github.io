---
layout: post
title: Angular Structure&#58; Refactoring for Growth
date: 2013-09-14 08:26
author: John
comments: true
categories: [angular, javascript, Uncategorized]
---
<p>Your <a href="http://www.angularjs.org" target="_blank">Angular</a> app is growing and you want your structure to adapt with it. Let's explore one way you can approach this.</p>

<p>As your app grows it becomes even more important to structure it in a way that makes it easy to manage and maintain it. I <a href="http://www.johnpapa.net/structuring-an-angular-project/" target="_blank">recently posted a common technique I use when I create a new app to help structure it</a>. A simple structure by type is easy out of the gate, as the app generally starts with a single set of features. This usually starts as the first module you write. Now fast forward and imagine you are working on an app that has a handful of modules, with dozens of views and controllers. How do you organize your code now?</p>

<h2>Options for Managing Growth</h2>

<p>I like the type organization (folders for controllers and views, for example), but as an app grows, instead of putting that at the root and putting all views and controllers in their own folders, sometimes it makes more sense to organize them 1 level deeper into feature areas. For a similar approach, see <a href="http://cliffmeyers.com/blog/2013/4/21/code-organization-angularjs-javascript" target="_blank">Cliff Meyer's great post</a>. We tend to look for the one right answer, but often there are many good options. You have to choose what feels right for you.</p>

<p>So how might this look? There are a lot of ways we could do this, but let's focus on two options side by side. <img src="http://images.johnpapa.net/wp-content/uploads/2013/08/NgStructureCompare.jpg" alt="NgStructureCompare" width="529" height="596" class="aligncenter size-full wp-image-21361" /></p>

<h2>Sort By Type</h2>

<p>On the left we have the app organized by type. Not too bad for smaller apps, but even here you can start to see it gets more difficult to find what you are looking for. When I want to find a specific view and its controller, they are in different folders. It can be good to start here if you are not sure how else to organize the code as it is quite easy to shift to the technique on the right: structure by feature.</p>

<h2>Sort By Feature</h2>

<p>On the left the project is organized by feature. All of the layout views and controllers go in the <code>layout</code> folder, the admin content goes in the <code>admin</code> folder, and the services that are used by all of the areas go in the <code>services</code> folder. The idea here is that when you are looking for the code that makes a feature work, it is located in one place. Services are a bit different as they "service" many features. I like this once my app starts to take shape as it becomes a lot easier to manage for me.</p>

<h2>Structuring for Modules</h2>

<p>This structure by feature can be extended fairly easily once you start to gather multiple modules. When i see common functionality that can be extracted and re-used, I like to break that out into its own module. In the structure by feature notice that I have a common folder. In there I have another module named <code>common</code> that contains logging, progress bars, and other common features. Sometimes I break this out such that the modules are the first folder under the <code>app</code> folder. But in this case I just had 2 modules: common and the main app.</p>

<p>As the app grows even further, you can have many modules. That's when I like to have the modules in their own folders under app. Specifically when the main app has very separate feature areas like <code>point of sale</code> and <code>inventory</code>, for example. Those could be their own modules. Then I'd also have some other common modules. See where this is heading? Separate silos of features that are easily separated (think Separation of Concerns).</p>

<h2>Your Choice</h2>

<p>Ultimately how you organize your code is entirely up to you and your team. Don't feel married to your choice, you can adapt when it makes sense. The key is in keeping good separation and making it easy to find your code.</p>

<blockquote>
  <p>If you are interested in SPA, HTML5, Angular, BreezeJS or JavaScript patterns then you will love my upcoming course at <a href="http://pluralsight.com/training/Authors/Details/john-papa" target="_blank">Pluralsight</a>, due out in October 2013. Or if you prefer Knockout and Durandal check out <a href="http://pluralsight.com/training/Authors/Details/john-papa" target="_blank">my courses on Pluralsight today</a>.</p>
</blockquote>

