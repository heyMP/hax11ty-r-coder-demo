---
title: R Code
banner: /assets/images/photo-1498050108023-c5249f4df085.jpeg
---

<p class="preface">
To run the code paste it into an R console window.
</p><p>
</p>
<r-coder endpoint="http://localhost:3000">a &lt;- 42
A &lt;- a * 2  # R is case sensitive
print(a)
cat(A, "\n") # "84" is concatenated with "\n"
if(A&gt;a) # true, 84 &gt; 42
{
  cat(A, "&gt;", a, "\n")
} 
</r-coder>



  <h2>Variables</h2>
  <p>
    R uses <span class="code">&lt;-</span> for variable assignment.
  </p>
  <p>
    Don't call your variables any of the following:
    </p><ul>
      <li> c, q, s, t, C, D, F, I, T
      </li><li> diff, length, mean, pi, range, rank, time, tree, var
      </li><li> if, function, NaN etc.
    </li></ul>
  <p></p>
  <p>
    Howard Seltman provides more information about reserved terms in this "<a href="http://www.stat.cmu.edu/~hseltman/Rclass/R1.R">Learning R</a>" lesson.<br>
    You can use underscores and periods in your identifiers. Google suggests <span class="code">tree.count</span> for variables and <span class="code">DoSomething</span> for functions.
  </p>
  <h2>Comments</h2>
  <p>
    Comments start with a <span class="code">#</span> sign. <a href="http://stackoverflow.com/questions/4131338/is-it-possible-to-have-a-multi-line-comments-in-r&quot;&quot;">Block Comments</a> can't be be done nicely.
  </p>
  <h2>print and cat</h2>
  <p>
    <a href="http://stat.ethz.ch/R-manual/R-patched/library/base/html/print.html"><span class="code">print()</span></a> automatically appends a new line character to the output.
    With <a href="http://stat.ethz.ch/R-manual/R-patched/library/base/html/cat.html"><span class="code">cat()</span></a> you have to append it manually.
    <span class="code">print()</span> can also show more types of content, such as functions:
</p><pre class="code">print(cat)
</pre>
<pre class="output">&gt; print(cat)
function (..., file = "", sep = " ", fill = FALSE, labels = NULL, 
    append = FALSE) 
{
    if (is.character(file)) 
        if (file == "") 
            file &lt;- stdout()
        else if (substring(file, 1L, 1L) == "|") {
            file &lt;- pipe(substring(file, 2L), "w")
            on.exit(close(file))
        }
        else {
            file &lt;- file(file, ifelse(append, "a", "w"))
            on.exit(close(file))
        }
    .Internal(cat(list(...), file, sep, fill, labels, append))
}
&lt;environment: namespace:base&gt;
</pre>
  You can get the <b>documentation of a function</b> from the R console if you type <span class="code">help(print)</span>.
  <p></p>
  
<h2>if statements</h2>
<p>
	If statements are quite straightforward:
</p>
<pre class="code">if(condition)
{
	doSth()
}
</pre>

<br>