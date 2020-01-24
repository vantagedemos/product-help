<div class="nested0" aria-labelledby="ariaid-title1" topicindex="1" topicid="aay1507660157006" id="aay1507660157006"><h1 class="title topictitle1" id="ariaid-title1">PathAnalyzer (ML Engine)</h1><div class="body conbody"><div class="p">The PathAnalyzer function:
<ol class="ol" id="aay1507660157006__ol_blc_hmk_p1b">
<li class="li">Inputs a set of paths to the function <a href="bqv1558447447291.md#xwn1507648929521">PathGenerator (ML Engine)</a>.</li>
<li class="li">Inputs the output to the function <a href="ftl1558447565569.md#odv1507653146030">PathSummarizer (ML Engine)</a>.</li>
<li class="li">Inputs the output to the function <a href="cdn1558447910639.md#wim1507653724768">PathStart (ML Engine)</a>, which outputs, for each parent, all children and the number of times that the user traveled each child.</li></ol></div>
<p class="p">For the definitions of the terms that this section uses, see <a href="hri1570132673913.md">Path Analysis Functions (ML Engine)</a>.</p></div><div class="topic reference nested1" aria-labelledby="ariaid-title2" topicindex="2" topicid="blv1507660203172" xml:lang="en-us" lang="en-us" id="blv1507660203172">
<h2 class="title topictitle2" id="ariaid-title2">PathAnalyzer Syntax</h2><div class="body refbody"><div class="section" id="blv1507660203172__section_N1000E_N1000C_N10001">
<h3 class="title sectiontitle">Version <span>1.10</span></h3><pre class="pre codeblock" xml:space="preserve"><code>SELECT * FROM PathAnalyzer (
  <span>ON { <var class="keyword varname">table</var> | <var class="keyword varname">view</var> | (<var class="keyword varname">query</var>) }</span> AS InputTable
  OUT TABLE OutputTable (<var class="keyword varname">output_table</var>)
  USING
  SeqColumn ('<var class="keyword varname">sequence_column</var>')
  [ CountColumn ('<var class="keyword varname">count_column</var>') ]
  [ HashCode (<span><b>{'true'|'t'|'yes'|'y'|'1'|'false'|'f'|'no'|'n'|'0'}</b></span>) ]
  Delimiter ('<var class="keyword varname">delimiter</var>')
) AS <var class="keyword varname">alias</var>;</code></pre></div></div></div><div class="topic reference nested1" aria-labelledby="ariaid-title3" topicindex="3" topicid="bwg1507660298322" xml:lang="en-us" lang="en-us" id="bwg1507660298322">
<h2 class="title topictitle2" id="ariaid-title3">PathAnalyzer Syntax Elements</h2><div class="body refbody"><div class="section" id="bwg1507660298322__section_N10011_N1000E_N10001"><dl class="dl parml"><dt class="dt pt dlterm">OutputTable</dt><dd class="dd pd">Specify the name of the output table.</dd><dt class="dt pt dlterm">SeqColumn</dt><dd class="dd pd">Specify the name of the InputTable column that contains the paths.</dd><dt class="dt pt dlterm">CountColumn</dt><dd class="dd pd">[Optional] Specify the name of the InputTable column that contains the number of times a path was traveled.</dd><dd class="dd pd ddexpand">Default: 1</dd><dt class="dt pt dlterm">HashCode</dt><dd class="dd pd">[Optional] Specify whether to include the hash code of the output column node.</dd><dd class="dd pd ddexpand">Default: 'false'</dd><dt class="dt pt dlterm">Delimiter</dt><dd class="dd pd">Specify the single Unicode character delimiter that separates symbols in the path string.</dd><dd class="dd pd ddexpand"><div class="note note" id="bwg1507660298322__note_N1006F_N1006D_N10064_N10018_N10014_N10010_N10001"><span><b>Note</b></span><div class="notebody">If <var class="keyword varname">delimiter</var> is backslash (\) or single quotation mark ('), you must precede it with the escape character, backslash (\). For example:<pre class="pre codeblock" xml:space="preserve"><code>Delimiter ('\\') -- Delimiter is backslash
Delimiter ('\'') -- Delimiter is single quotation mark</code></pre></div></div></dd></dl></div></div></div></div>