<div class="nested0" aria-labelledby="ariaid-title1" topicindex="1" topicid="dgl1507650972185" id="dgl1507650972185"><h1 class="title topictitle1" id="ariaid-title1">Approximate Cardinality (ML Engine)</h1><div class="body conbody">
<p class="p">The Approximate Cardinality function, which is composed of the ApproxCardinalityReduce and ApproxCardinalityMap functions, can estimate the cardinality (number of distinct values) in a column or combination of columns, scanning the table only once.</p>
<p class="p">Teradata recommends this function when the column or combination of columns has a large cardinality. When the cardinality is small, Teradata recommends the SQL SELECT DISTINCT command.</p>
<p class="p">The function uses the Flajolet-Martin algorithm. For more information, see <cite class="cite">Probabilistic Counting Algorithms for Data Base Applications, by Philippe Flajolet and G. Nigel Martin</cite> (<a class="xref" href="http://portal.acm.org/citation.cfm?id=5215" target="_blank" title="" shape="rect">http://portal.acm.org/citation.cfm?id=5215</a>).</p></div><div class="topic reference nested1" aria-labelledby="ariaid-title2" topicindex="2" topicid="cnp1507651078126" xml:lang="en-us" lang="en-us" id="cnp1507651078126">
<h2 class="title topictitle2" id="ariaid-title2">Approximate Cardinality Syntax</h2><div class="body refbody"><div class="section" id="cnp1507651078126__section_N1000E_N1000C_N10001">
<h3 class="title sectiontitle">ApproxCardinalityReduce version 1.3, ApproxCardinalityMap version <span>1.3</span></h3><pre class="pre codeblock" xml:space="preserve"><code>SELECT * FROM ApproxCardinalityReduce (
  ON ( [ SELECT * FROM ] ApproxCardinalityMap (
    <span>ON { <var class="keyword varname">table</var> | <var class="keyword varname">view</var> | (<var class="keyword varname">query</var>) }</span>
    USING
    TargetColumns ({ '<var class="keyword varname">target_column</var>' | <var class="keyword varname">target_column_range</var> [,...])
    [ ErrorRate (<var class="keyword varname">error_tolerance</var>) ]
    ) AS <var class="keyword varname">alias_1</var>
  ) PARTITION BY <var class="keyword varname">column_name</var>
) AS <var class="keyword varname">alias_2</var>;</code></pre></div></div><div class="related-links"><div class="linklistheader"><p></p><b>Related Information</b></div>
<ul class="linklist linklist relinfo"><div class="linklistmember"><a href="ndv1557782188375.md">Column Specification Syntax Elements</a></div></ul></div></div><div class="topic reference nested1" aria-labelledby="ariaid-title3" topicindex="3" topicid="eos1507653339186" xml:lang="en-us" lang="en-us" id="eos1507653339186">
<h2 class="title topictitle2" id="ariaid-title3">Approximate Cardinality Syntax Elements</h2><div class="body refbody"><div class="section" id="eos1507653339186__section_N10011_N1000E_N10001"><dl class="dl parml"><dt class="dt pt dlterm">TargetColumns</dt><dd class="dd pd">Specify the columns for which to estimate the number of distinct values.</dd><dt class="dt pt dlterm">ErrorRate</dt><dd class="dd pd">[Optional] Specify the acceptable error rate, expressed as a decimal (for example, if <var class="keyword varname">error_tolerance</var> is 10, the acceptable error rate is 10%). The <var class="keyword varname">error_tolerance</var> must be in the range (5.0e<span><sup>-4</sup></span>, 10].</dd><dd class="dd pd ddexpand">Default: 10</dd></dl></div></div></div></div>