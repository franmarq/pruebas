

```sas
# Comando para configuración del ambiente
```


```sas
%let homefolder=/folders/myfolders/ECST142;

libname STAT1 "&homefolder";

options fmtsearch=(stat1.myfmts);

proc format library=stat1.myfmts;
run;

/* create macro variables to hold the names of the interval and */
/* categorical variables used in the demo and practice programs */

%let interval=Gr_Liv_Area Basement_Area Garage_Area Deck_Porch_Area 
         Lot_Area Age_Sold Bedroom_AbvGr Total_Bathroom;

%let categorical=House_Style2 Overall_Qual2 Overall_Cond2 Fireplaces 
         Season_Sold Garage_Type_2 Foundation_2 Heating_QC 
         Masonry_Veneer Lot_Shape_2 Central_Air;
```




<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"
   "http://www.w3.org/TR/html4/strict.dtd">

<html>
<head>
  <title></title>
  <meta http-equiv="content-type" content="text/html; charset=None">
  <style type="text/css">
td.linenos { background-color: #f0f0f0; padding-right: 10px; }
span.lineno { background-color: #f0f0f0; padding: 0 5px 0 5px; }
pre { line-height: 125%; }
body .hll { background-color: #ffffcc }
body  { background: #ffffff; }
body .c { color: #0000FF } /* Comment */
body .k { color: #ff0000; font-weight: bold } /* Keyword */
body .n { color: #008000 } /* Name */
body .ch { color: #0000FF } /* Comment.Hashbang */
body .cm { color: #0000FF } /* Comment.Multiline */
body .cp { color: #0000FF } /* Comment.Preproc */
body .cpf { color: #0000FF } /* Comment.PreprocFile */
body .c1 { color: #0000FF } /* Comment.Single */
body .cs { color: #0000FF } /* Comment.Special */
body .kc { color: #ff0000; font-weight: bold } /* Keyword.Constant */
body .kd { color: #ff0000; font-weight: bold } /* Keyword.Declaration */
body .kn { color: #ff0000; font-weight: bold } /* Keyword.Namespace */
body .kp { color: #ff0000; font-weight: bold } /* Keyword.Pseudo */
body .kr { color: #ff0000; font-weight: bold } /* Keyword.Reserved */
body .kt { color: #ff0000; font-weight: bold } /* Keyword.Type */
body .s { color: #111111 } /* Literal.String */
body .na { color: #008000 } /* Name.Attribute */
body .nb { color: #008000 } /* Name.Builtin */
body .nc { color: #008000 } /* Name.Class */
body .no { color: #008000 } /* Name.Constant */
body .nd { color: #008000 } /* Name.Decorator */
body .ni { color: #008000 } /* Name.Entity */
body .ne { color: #008000 } /* Name.Exception */
body .nf { color: #008000 } /* Name.Function */
body .nl { color: #008000 } /* Name.Label */
body .nn { color: #008000 } /* Name.Namespace */
body .nx { color: #008000 } /* Name.Other */
body .py { color: #008000 } /* Name.Property */
body .nt { color: #008000 } /* Name.Tag */
body .nv { color: #008000 } /* Name.Variable */
body .sb { color: #111111 } /* Literal.String.Backtick */
body .sc { color: #111111 } /* Literal.String.Char */
body .sd { color: #111111 } /* Literal.String.Doc */
body .s2 { color: #111111 } /* Literal.String.Double */
body .se { color: #111111 } /* Literal.String.Escape */
body .sh { color: #111111 } /* Literal.String.Heredoc */
body .si { color: #111111 } /* Literal.String.Interpol */
body .sx { color: #111111 } /* Literal.String.Other */
body .sr { color: #111111 } /* Literal.String.Regex */
body .s1 { color: #111111 } /* Literal.String.Single */
body .ss { color: #111111 } /* Literal.String.Symbol */
body .bp { color: #008000 } /* Name.Builtin.Pseudo */
body .vc { color: #008000 } /* Name.Variable.Class */
body .vg { color: #008000 } /* Name.Variable.Global */
body .vi { color: #008000 } /* Name.Variable.Instance */

  </style>
</head>
<body>
<h2></h2>

<div class="highlight"><pre><span></span><span class="s">41   ods listing close;ods html5 (id=saspy_internal) file=stdout options(bitmap_mode=&#39;inline&#39;) device=svg style=HTMLBlue; ods</span><br><span class="s">41 ! graphics on / outputfmt=png;</span><br><span class="cm">NOTE: Writing HTML5(SASPY_INTERNAL) Body file: STDOUT</span><br><span class="s">42   </span><br><span class="s">43   %let homefolder=/folders/myfolders/ECST142;</span><br><span class="s">44   </span><br><span class="s">45   libname STAT1 &quot;&amp;homefolder&quot;;</span><br><span class="cm">NOTE: Libref STAT1 was successfully assigned as follows: </span><br><span class="cm">      Engine:        V9 </span><br><span class="cm">      Physical Name: /folders/myfolders/ECST142</span><br><span class="s">46   </span><br><span class="s">47   options fmtsearch=(stat1.myfmts);</span><br><span class="s">48   </span><br><span class="s">49   proc format library=stat1.myfmts;</span><br><span class="s">50   run;</span><br><span class="cm">NOTE: PROCEDURE FORMAT used (Total process time):</span><br><span class="cm">      real time           0.03 seconds</span><br><span class="cm">      cpu time            0.03 seconds</span><br><span class="cm">      </span><br><span class="s">51   </span><br><span class="s">52   /* create macro variables to hold the names of the interval and */</span><br><span class="s">53   /* categorical variables used in the demo and practice programs */</span><br><span class="s">54   </span><br><span class="s">55   %let interval=Gr_Liv_Area Basement_Area Garage_Area Deck_Porch_Area</span><br><span class="s">56            Lot_Area Age_Sold Bedroom_AbvGr Total_Bathroom;</span><br><span class="s">57   </span><br><span class="s">58   %let categorical=House_Style2 Overall_Qual2 Overall_Cond2 Fireplaces</span><br><span class="s">59            Season_Sold Garage_Type_2 Foundation_2 Heating_QC</span><br><span class="s">60            Masonry_Veneer Lot_Shape_2 Central_Air;</span><br><span class="s">61   </span><br><span class="s">62   ods html5 (id=saspy_internal) close;ods listing;</span><br><br><span class="s">63   </span><br></pre></div>
</body>
</html>





```sas
proc datasets lib=stat1; 
contents tables ; 
run;
```
