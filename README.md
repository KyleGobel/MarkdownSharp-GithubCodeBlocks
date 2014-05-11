MarkdownSharp - With Github style code blocks
=========================================

The original MarkdownSharp can be found on google code here [https://code.google.com/p/markdownsharp/](https://code.google.com/p/markdownsharp/)


This is basically a fork of that, that has been slightly modified to support github style code blocks.

If you're unfamiliar with MarkdownSharp, it's a markdown parser, which was ported from the original perl markdown parser.  I believe it is what StackOverflow uses.

My light modifications allow this

<pre lang="no-highlight"><code>
```cs
public void Main()
{
  Console.WriteLine("Github Style Code blocks");
}
```
</code></pre>

Which will be transformed to the following html

```html
<pre><code class='language-cs'>
public void Main()
{
  Console.WriteLine("Github Style Code blocks");
}
</code></pre>
```

Then you can use a library like [HighlightJS](http://highlightjs.org/) to sytnax highlight that code block, and since we added the class ``language-cs``, it will be highlighted as c# code.

Whatever is after the 3 ticks will be put in the class name

so 
<pre lang="no-highlight"><code>```mylanguage
</code></pre> 
would transform to 
```html
<pre><code class='language-mylanguage'>
```


