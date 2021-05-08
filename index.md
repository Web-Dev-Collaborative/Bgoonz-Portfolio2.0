<h1 id="using-a-theme">Using a Theme</h1>
<blockquote>
<p>In this tutorial, you&#39;ll learn how to use Gatsby themes by creating a new site using the official Gatsby blog theme. Pre-requisites A Gatsby…</p>
</blockquote>
<p>In this tutorial, you’ll learn how to use Gatsby themes by creating a new site using the official Gatsby blog theme.</p>
<h2 id="-pre-requisites-pre-requisites"><a href="#pre-requisites"></a>Pre-requisites</h2>
<ul>
<li>A Gatsby site</li>
</ul>
<blockquote>
<p>Note: This tutorial assumes you already have a Gatsby site to install your theme in. If you’d prefer to start with an entirely new site you can run <code>gatsby new my-blog https://github.com/gatsbyjs/gatsby-starter-blog-theme</code> to set up a starter with the blog theme already installed.</p>
</blockquote>
<h2 id="-installing-the-blog-theme-installing-the-blog-theme"><a href="#installing-the-blog-theme"></a>Installing the blog theme</h2>
<p>Navigate to the root of your project inside your terminal and install the theme with the following command:</p>
<pre><code>npm <span class="hljs-keyword">install</span> gatsby-theme-blog
</code></pre><h2 id="-configure-the-theme-configure-the-theme"><a href="#configure-the-theme"></a>Configure the theme</h2>
<p>In your <code>gatsby-config.js</code> file, add <code>gatsby-theme-blog</code>. This theme takes optional dependencies that you can find in the <a href="https://github.com/gatsbyjs/themes/tree/master/packages/gatsby-theme-blog#theme-options">README</a>. However, you won’t need to use them here.</p>
<pre><code>module.exports = {  <span class="hljs-string">plugins:</span> [    {      <span class="hljs-string">resolve:</span> <span class="hljs-string">"gatsby-theme-blog"</span>,      <span class="hljs-string">options:</span> {},    },  ],}
</code></pre><blockquote>
<p>Note: If you already have a landing page set up for your site, you may want to make use of the <code>basePath</code> option that will put your blog listing page at a path other than <code>/</code>, such as <code>/blog</code>.</p>
</blockquote>
<p>Customize the information on your site by replacing the site metadata in the <code>gatsby-config.js</code> file. Your <code>siteUrl</code> should point to your public domain. It’s ok if you don’t have one yet, you can update it later.</p>
<pre><code>module.exports = {  <span class="hljs-string">siteMetadata:</span> {    <span class="hljs-string">title:</span> <span class="hljs-string">"My Blog"</span>,    <span class="hljs-string">author:</span> <span class="hljs-string">"Amberley Romo"</span>,    <span class="hljs-string">description:</span> <span class="hljs-string">"A collection of my thoughts and writings."</span>,    <span class="hljs-string">siteUrl:</span> <span class="hljs-string">"https://amberley.blog/"</span>,    <span class="hljs-string">social:</span> [      {        <span class="hljs-string">name:</span> <span class="hljs-string">"twitter"</span>,        <span class="hljs-string">url:</span> <span class="hljs-string">"https://twitter.com/amber1ey"</span>,      },      {        <span class="hljs-string">name:</span> <span class="hljs-string">"github"</span>,        <span class="hljs-string">url:</span> <span class="hljs-string">"https://github.com/amberleyromo"</span>,      },    ],  },  <span class="hljs-string">plugins:</span> [    {      <span class="hljs-string">resolve:</span> <span class="hljs-string">"gatsby-theme-blog"</span>,      <span class="hljs-string">options:</span> {},    },  ],}
</code></pre><h2 id="-add-some-content-add-some-content"><a href="#add-some-content"></a>Add some content</h2>
<p>Before you can see anything, you’ll want to add some content so there is something to show.</p>
<p>By default, the posts are expected in the <code>/content/posts</code> directory, so create those folders and add a <code>my-post.md</code> file. Your file structure should look something like this.</p>
<pre><code><span class="hljs-selector-tag">my-blog</span>├── <span class="hljs-selector-tag">content</span>│   └── <span class="hljs-selector-tag">posts</span>│       └── <span class="hljs-selector-tag">my-post</span><span class="hljs-selector-class">.md</span>├── <span class="hljs-selector-tag">src</span>├── <span class="hljs-selector-tag">gatsby-config</span><span class="hljs-selector-class">.js</span>└── <span class="hljs-selector-tag">package</span><span class="hljs-selector-class">.json</span>
</code></pre><p>Despite the <code>md</code> extension, <code>my-post.md</code> is treated as an MDX file. When using this theme, you can use <code>md</code> and <code>mdx</code> extensions interchangeably.</p>
<p>Inside that Markdown file, add content. The top section is called <a href="chrome-extension://cjedbglnccaioiolemnfhjncicchinao/docs/how-to/routing/mdx/writing-pages/#using-frontmatter-in-mdx">frontmatter</a> and <code>title</code> and <code>date</code> are required fields.</p>
<p>/content/posts/my-post.md</p>
<pre><code><span class="hljs-attribute">---title</span>: My <span class="hljs-attribute">Postdate</span>: <span class="hljs-number">2020</span>-<span class="hljs-number">04</span>-<span class="hljs-number">15</span>---Let's write a post!<span class="hljs-built_in">``</span><span class="hljs-built_in">`javascriptconst test = "this is a theme"`</span><span class="hljs-built_in">``</span>
</code></pre><h2 id="-test-run-your-site-test-run-your-site"><a href="#test-run-your-site"></a>Test run your site</h2>
<p>To make sure everything is working, run your site. This command should be run in your terminal in your project’s root directory.</p>
<p>Navigate to <code>http://localhost:8000</code> to see the landing page of your site.</p>
<h2 id="-replace-your-avatar-replace-your-avatar"><a href="#replace-your-avatar"></a>Replace your avatar</h2>
<p>At the moment, the bio on your pages shows a blank section where a picture should be. Add your own avatar by choosing the image you want, and overwriting the file located at <code>/content/assets/avatar.png</code>.</p>
<h2 id="-replace-the-content-of-the-bio-replace-the-content-of-the-bio"><a href="#replace-the-content-of-the-bio"></a>Replace the content of the bio</h2>
<p>When using Gatsby themes, you can take advantage of something called component shadowing. This allows you to override the default component included in the theme with a custom one you’ve created.</p>
<p>The Gatsby blog theme package has a component that contains the content of the site author’s biography. The file path to that component (in the blog theme package, not your site) is <code>src/gatsby-theme-blog/components/bio-content.js</code>. You can find this path by looking through the theme in your site’s <code>node_modules/gatsby-theme-blog</code> directory.</p>
<p>If you look at the file tree of your site, you’ll see it looks something like this:</p>
<pre><code><span class="hljs-selector-tag">my-blog</span>├── <span class="hljs-selector-tag">content</span>│   ├── <span class="hljs-selector-tag">assets</span>│   │   └── <span class="hljs-selector-tag">avatar</span><span class="hljs-selector-class">.png</span>│   └── <span class="hljs-selector-tag">posts</span>│       └── <span class="hljs-selector-tag">my-post</span><span class="hljs-selector-class">.md</span>├── <span class="hljs-selector-tag">src</span>│   └── <span class="hljs-selector-tag">gatsby-theme-blog</span>│       └── <span class="hljs-selector-tag">components</span>│           └── <span class="hljs-selector-tag">bio-content</span><span class="hljs-selector-class">.js</span>├── <span class="hljs-selector-tag">gatsby-config</span><span class="hljs-selector-class">.js</span>└── <span class="hljs-selector-tag">package</span><span class="hljs-selector-class">.json</span>
</code></pre><p>In the <code>src</code> directory of the site, there’s a <code>gatsby-theme-blog</code> directory. Any file placed in that directory with a path that matches the path of a file in the blog theme directory will completely shadow the theme.</p>
<blockquote>
<p>💡 The name of the directory (here <code>gatsby-theme-blog</code>) must exactly mirror the name of the published theme package, which in this case is <a href="https://www.npmjs.com/package/gatsby-theme-blog"><code>gatsby-theme-blog</code></a>.</p>
</blockquote>
<p>Open up the <code>bio-content.js</code> file and make some content edits:</p>
<pre><code><span class="hljs-keyword">import</span> React, { Fragment } <span class="hljs-keyword">from</span> <span class="hljs-string">"react"</span><span class="hljs-keyword">export</span> <span class="hljs-keyword">default</span> <span class="hljs-function"><span class="hljs-keyword">function</span> <span class="hljs-title">Bio</span>(<span class="hljs-params"></span>) </span>{  <span class="hljs-keyword">return</span> (    <span class="xml"><span class="hljs-tag">&lt;<span class="hljs-name">Fragment</span>&gt;</span>      This is my updated bio.      <span class="hljs-tag">&lt;<span class="hljs-name">br</span> /&gt;</span>      It's shadowing the content from the theme.    <span class="hljs-tag">&lt;/<span class="hljs-name">Fragment</span>&gt;</span></span>  )}
</code></pre><p>At this point, you should have an updated avatar, updated site details, and an updated bio. You may want to re-run <code>gatsby develop</code> to make sure everything looks good.</p>
<h2 id="-change-the-color-theme-change-the-color-theme"><a href="#change-the-color-theme"></a>Change the color theme</h2>
<p>The blog theme uses <code>gatsby-plugin-theme-ui</code> to style your site. There are a number of presets available for you to make use of, or you can make your own!</p>
<blockquote>
<p>If you want to use a preset take a look at the <a href="https://theme-ui.com/packages/presets">Theme UI preset listing</a>.</p>
</blockquote>
<p>You’re going to use <code>@theme-ui/preset-funk</code>. To start, you have to install it.</p>
<pre><code><span class="hljs-selector-tag">npm</span> <span class="hljs-selector-tag">install</span> @<span class="hljs-keyword">theme</span>-<span class="hljs-keyword">ui</span>/<span class="hljs-keyword">preset</span>-<span class="hljs-keyword">funk</span>
</code></pre><p>Next, update your <code>gatsby-config.js</code> file to pass in the preset package name.</p>
<pre><code>module.exports = {  <span class="hljs-string">plugins:</span> [    {      <span class="hljs-string">resolve:</span> <span class="hljs-string">"gatsby-theme-blog"</span>,      <span class="hljs-string">options:</span> {        <span class="hljs-string">preset:</span> <span class="hljs-string">"@theme-ui/preset-funk"</span>,      },    },  ],}
</code></pre><p>If you want to further customize this theme you can shadow it. Create a file at <code>/src/gatsby-plugin-theme-ui/index.js</code>.</p>
<p>/src/gatsby-plugin-theme-ui/index.js</p>
<pre><code>const darkBlue = `#<span class="hljs-number">007</span>acc`const lightBlue = `#<span class="hljs-number">66E0</span>FF`const blueGray = `#<span class="hljs-number">282</span>c35`<span class="hljs-keyword">export</span> default {  colors: {    text: blueGray,    primary: darkBlue,    heading: blueGray,  },}
</code></pre><p>These colors will merge with the preset theme and override that part of the preset.</p>
<h3 id="-change-your-prism-theme-change-your-prism-theme"><a href="#change-your-prism-theme"></a>Change your prism theme</h3>
<p>Another option you can make use of is prism styling for code blocks. There are many available from <a href="https://theme-ui.com/packages/prism#syntax-themes">Theme UI</a>.</p>
<p>In this example you’ll use <code>prism-okaidia</code>. Update your <code>gatsby-config.js</code> file with that option.</p>
<pre><code>module.exports = {  <span class="hljs-string">plugins:</span> [    {      <span class="hljs-string">resolve:</span> <span class="hljs-string">"gatsby-theme-blog"</span>,      <span class="hljs-string">options:</span> {        <span class="hljs-string">preset:</span> <span class="hljs-string">"@theme-ui/preset-funk"</span>,        <span class="hljs-string">prismPreset:</span> <span class="hljs-string">"prism-okaidia"</span>,      },    },  ],}
</code></pre><p>When you restart your development server you’ll see new syntax highlighting in your code snippets.</p>
<h2 id="-take-a-look-take-a-look"><a href="#take-a-look"></a>Take a look</h2>
<p>Fire up your development server by running <code>gatsby develop</code> again in your terminal. Navigate to <code>http://localhost:8000</code> and take a look at your blog listing page.</p>
<h2 id="-wrapping-up-wrapping-up"><a href="#wrapping-up"></a>Wrapping up</h2>
<p>This was a step-by-step introduction to using a Gatsby theme through looking at a specific example. Note that different themes will be built differently, to accept different customization options. To dive deeper, check out the <a href="chrome-extension://cjedbglnccaioiolemnfhjncicchinao/docs/themes/">Gatsby Theme docs</a>.</p>
<h2 id="-whats-next-what-s-next-"><a href="#whats-next"></a>What’s next?</h2>
<ul>
<li><a href="chrome-extension://cjedbglnccaioiolemnfhjncicchinao/tutorial/using-multiple-themes-together/">Using multiple themes together</a></li>
</ul>
<p><a href="https://www.gatsbyjs.com/tutorial/using-a-theme/">Source</a></p>
