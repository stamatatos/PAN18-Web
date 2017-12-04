<!DOCTYPE html>
<html lang="en">
<head>

<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>PAN 2018</title>

<link href="bootstrap.min.css" rel="stylesheet" />
<link href="prettify.css" rel="stylesheet" />

<style>
.navbar .navbar-nav {
  font-weight: bold;
}
</style>

<!-- HTML5 Shim and Respond.js IE8 support of HTML5 elements and media queries -->
<!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
<!--[if lt IE 9]>
  <script src="../../js/html5shiv.js"></script>
  <script src="../../js/respond.min.js"></script>
<![endif]-->

<link rel="shortcut icon" href="../pan18-figures/pan-icon-16x16.ico">
<!--
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="ico/apple-touch-icon-144-precomposed.png">
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="ico/apple-touch-icon-114-precomposed.png">
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="ico/apple-touch-icon-72-precomposed.png">
<link rel="apple-touch-icon-precomposed" href="ico/apple-touch-icon-57-precomposed.png">
-->

</head>
<body>

<nav class="navbar navbar-inverse navbar-static-top" role="navigation">
  <div class="navbar-header">
    <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1">
      <span class="sr-only">Toggle navigation</span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
    </button>
    <a class="navbar-brand" href="../../index.html"><img src="../pan17-figures/pan-logo-small-lightgrey.png" alt="PAN" style="margin-top:-5px"></a>
  </div>
  <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
    <ul class="nav navbar-nav navbar-right">
      <li><a href="../../index.html">Home</a></li>
      <li><a href="index.html">PAN @ CLEF 2018:</a></li>
      <li><a href="about.html">About</a></li>
      <li><a href="proceedings.html">Proceedings</a></li>
      <li class="dropdown active">
        <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Tasks <span class="caret"></span></a>
        <ul class="dropdown-menu">
          <li class="active"><a href="author-identification.html">Author Identification</a></li>
          <li><a href="author-profiling.html">Author Profiling</a></li>
          <li><a href="author-obfuscation.html">Author Obfuscation</a></li>
        </ul>
      </li>
    </ul>
  </div>
</nav>

<div class="container">

<div class="row">
  <div class="col-xs-12">
    <h1 id="task-description" class="page-header">
      Author Identification
      <div class="btn-group">
        <a role="button" class="btn btn-default" href="../../clef16/pan16-web/author-identification.html"><span class="glyphicon glyphicon-chevron-left" style="color:grey;"></span></a>
        <span role="button" class="btn btn-default" disabled="disabled">2018</span>
        <span role="button" class="btn btn-default" disabled="disabled"><span class="glyphicon glyphicon-chevron-right" style="color:grey;"></span></span>
      </div>
    </h1>
    <!--
    <div class="thumbnail pull-right" style="text-align:right;margin-left:15px;"><a href="http://www.adobe.com/" target="_blank"><img src="../pan17-figures/logo-adobe.png" alt="Adobe" style="max-height:150px"></a><div style="font-size:7pt;margin-right:13px;margin-top:2px;">Sponsor</div></div>
    -->
    <p class="lead">This task is divided into <strong>cross-domain authorship attribution</strong> and <strong>style change detection</strong>. You can choose to solve one or both of them.</p>
    <ul class="nav nav-pills visible-xs">
      <li><a href="#author-clustering" class="btn btn-large"><span class="glyphicon glyphicon-chevron-down"></span> Author Clustering</a></li>
      <li><a href="#author-diarization" class="btn btn-large"><span class="glyphicon glyphicon-chevron-down"></span> Style Breach Detection</a></li>
    </ul>
  </div>
</div>

<div class="row">
  <div class="col-sm-6">
    <h2 id="cross-domain">Cross-domain Authorship Attribution</h2>
    <p>Authorship attribution is an important problem in information retrieval and computational linguistics but also in applied areas such as law and journalism where knowing the author of a document (such as a ransom note) may be able to save lives. The most common framework for testing candidate algorithms is the <strong>closed-set attribution</strong> task: given known sample documents from a small, finite set of candidate authors, which wrote a questioned document of unknown authorship? This task may be quite challenging when documents of known and unkonwn authorship come from different domains (e.g., thematic area, genre). 
	<p>In this edition of PAN, for the first time, we focus on <strong>cross-domain attribution</strong> applied to <strong>Fanfiction</strong>. Fanfiction refers to fictional forms of literature which are nowadays produced by admirers ('fans') of a certain author (e.g. J.K. Rowling), novel ('Pride and Prejudice'), TV series (Sherlock Holmes), etc. The fans heavily borrow from the original work's theme, atmosphere, style, characters, story world etc. to produce new fictional literature, i.e. the so-called <strong>fanfics</strong>. This is why fanfiction is also known as transformative literature and has generated a number of controversies in recent years related to the intellectual rights property of the original authors (cf. plagiarism). Fanfiction, however, is typically produced by fans without any explicit commercial goals. The publication of fanfics typically happens online, on informal community platforms that are dedicated to making such literature accessible to a wider audience (e.g. <a href=https://www.fanfiction.net>fanfiction.net</a>). The original work of art or genre is typically refered to as a <strong>fandom</strong>.</p>
	<p>The cross-domain attribution task in this edition of PAN can be more accurately described as <strong>cross-fandom attribution in fanfiction</strong>. In more detail, all documents of unknown authorship are fanfics of the same fandom (target fandom) while the documents of known authorship by the candidate authors are fanfics of several fandoms (other than the target-fandom). </p>
	
    <div class="panel panel-default">
      <div class="panel-heading">Task</div>
      <div class="panel-body">Given a set of documents (known fanfics) by a small number (up to 20) of candidate authors, identify the authors of another set of documents (unknown fanfics). All unknown fanfics belong to the same target fandom. The known fanfics belong to several fandoms (excluding the target fandom), not necessarily the same for all candidate authors. An equal number of fanfics per candidate author is provided. In contrast, the unknown fanfics are not equally distributed over the authors. Text-length of fanfics varies from 500 to 1,000 tokens. Language of documents may be <strong>English, French, Italian, Polish, or Spanish</strong></div>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">Development Phase</div>
      <div class="panel-body"><p>To develop your software, we provide you with a corpus of similar characteristics with the evaluation corpus. It comprises a set of cross-domain authorship attribution problems in each of the following 5 languages: English, French, Italian, Polish, and Spanish. Note that we specifically avoid to use the term 'training corpus' because <strong>the sets of candidate authors of the developing and the evaluation corpora are not overlapping</strong>. Therefore, your approach should not be designed to particularly handle the candidate authors of the development corpus. </p>
	  <p>Each problem consists of a set of known fanfics by each candidate author and a set of unknown fanfics located in separate folders. The file <code>problem-info.json</code> that can be found in the main folder of each problem, shows the name of folder of unknown documents and the list of names of candidate author folders. </p>
	<pre class="prettyprint lang-py" style="overflow-x:auto">

{
    "unknown-folder": "unknown",
    "candidate-authors": [
        { "author-name": "candidate00001" },
        { "author-name": "candidate00002" },
		...
	]
}
	</pre>
	<p>The true author of each unknown document can be seen in the file <code>ground-truth.json</code>, also found in the main folder of each problem.</p>
    <p>In addition, to handle a collection of such problems, the file <code>collection-info.json</code> includes all relevant information. In more detail, for each problem it lists its main folder, the language (either <code>"en"</code>, <code>"fr"</code>, <code>"it"</code>, <code>"pl"</code>, or <code>"sp"</code>) and encoding (always <code>UTF-8</code>) of its documents. </p>
	<pre class="prettyprint lang-py" style="overflow-x:auto">

[  { "problem-name": "problem00001", 
     "language": "en", 
     "encoding": "UTF-8" },
   { "problem-name": "problem00002", 
     "language": "fr", 
     "encoding": "UTF-8" },
	  ...
]
	</pre>

	<p><a class="btn btn-default" target="_blank" href="">Download corpus</a> </p>
	<p> This is a password-protected file. To obtain the password, first <a href=https://docs.google.com/forms/d/e/1FAIpQLSfR_xoBuGU3q7o3EYPoItN28UPuZENjs3wlWYEX_EdRGUyRfA/viewform>register</a> for the author identification task at PAN-2018, and then <a href="mailto:pan@webis.de?Subject=PAN-18" target="_top">notify</a> PAN organizers.
</div>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">Evaluation Phase</div>
      <div class="panel-body">Once you finished tuning your approach to achieve satisfying performance on the development corpus, your software will be tested on the evaluation corpus. During the competition, the evaluation corpus will not be released publicly. Instead, we ask you to <strong>submit your software</strong> for evaluation at our site as described below.
<br>After the competition, the evaluation corpus will become available including ground truth data. This way, you have all the necessities to evaluate your approach on your own, yet being comparable to those who took part in the competition.

	    </div></div>
    <div class="panel panel-default">
      <div class="panel-heading">Output</div>
      <div class="panel-body">
<p>Your system should produce one output file for each authorship attribution problem in <a href="http://www.json.org/">JSON</a>. The name of the output files should be <code>answers-PROBLEMNAME.txt</code> (e.g., <code>answers-problem00001.txt</code>, <code>answers-problem00002.txt</code>) including the list of unknown documents and their predicted author:</p>

<pre class="prettyprint lang-py" style="overflow-x:auto">
[
    { "unknown-document":  "unknown00001.txt", 
      "predicted-author":  "candidate00003.txt" },
    { "unknown-document":  "unknown00002.txt", 
      "predicted-author":  "candidate00005.txt" },
	…
]
</pre>
</div></div>
    <div class="panel panel-default">
      <div class="panel-heading">Performance Measures</div>
      <div class="panel-body">
	  <p>The submissions will be evaluated in each attribution problem separately based on their <strong>macro-average classification accuracy</strong> (macro-A). Participants will be ranked according to their average macro-A across all attibution problems of the evaluation corpus. </p>
	</div></div>
	  <div class="panel panel-default">
      <div class="panel-heading">Submission</div>
      <div class="panel-body">
        <p>We ask you to prepare your software so that it can be executed via command line calls. The command shall take as input (i) an absolute path to the directory of the evaluation corpus and (ii) an absolute path to an empty output directory:</p>
	<pre class="prettyprint lang-py" style="overflow-x:auto">
> mySoftware -i EVALUATION-DIRECTORY -o OUTPUT-DIRECTORY
	</pre>
	<p>Within <code>EVALUATION-DIRECTORY</code> a <code>collection-info.json</code> file and a number of folders, one for each attribution problem, will be found (similar to the developing corpus as described above). For each clustering problem, the output file should be written in <code>OUTPUT-DIRECTORY</code>.</p>
        <p>You can choose freely among the available programming languages and among the operating systems Microsoft Windows and Ubuntu. We will ask you to deploy your software onto a virtual machine that will be made accessible to you after registration. You will be able to reach the virtual machine via ssh and via remote desktop. More information about how to access the virtual machines can be found in the user guide below:</p>
        <p><a class="btn btn-default" href="http://www.tira.io/static/tira-vm-user-guide.pdf">PAN Virtual Machine User Guide »</a></p>
        <p>Once deployed in your virtual machine, we ask you to access TIRA at <a href="http://www.tira.io">www.tira.io</a>, where you can self-evaluate your software on the test data.</p>
        <p><strong>Note:</strong> By submitting your software you retain full copyrights. You agree to grant us usage rights only for the purpose of the PAN competition. We agree not to share your software with a third party or use it for other purposes than the PAN competition.</p>
      </div>
    </div>
    

    <div class="panel panel-default">
      <div class="panel-heading">Related Work</div>
      <div class="panel-body">
        <p>We refer you to:</p>
        <ul>	<li>
			<a href="http://pan.webis.de/clef12/pan12-web/author-identification.html">Author identification task at PAN@CLEF'12</a> (closed-set authorship attribution) </li>
		<li>
			<a href="http://pan.webis.de/clef11/pan11-web/author-identification.html">Author identification task at PAN@CLEF'11</a> (closed-set authorship attribution)</li>
	<li>
        Patrick Juola. <a href="http://portal.acm.org/citation.cfm?id=1373451">Authorship Attribution</a>. In Foundations and Trends in Information Retrieval, Volume 1, Issue 3, March 2008.
        </li><li>
        Moshe Koppel, Jonathan Schler, and Shlomo Argamon. <a href="http://onlinelibrary.wiley.com/doi/10.1002/asi.20961/full">Computational Methods
        Authorship Attribution</a>. Journal of the American Society for Information Science and Technology, Volume 60, Issue 1, pages 9-26, January 2009.
        </li><li>
        Efstathios Stamatatos. <a href="http://onlinelibrary.wiley.com/doi/10.1002/asi.21001/full">A Survey of Modern Authorship Attribution Methods</a>.
        Journal of the American Society for Information Science and Technology, Volume 60, Issue 3, pages 538-556, March 2009.
        </li></ul>
      </div>
    </div>
    <div id="task-committee-clustering" class="row">
      <div class="col-xs-12">
        <h2 class="page-header">Task Chair</h2>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-6">
        <div class="thumbnail" style="text-align:center;">
          <a href="http://www.mike-kestemont.org/" target="_blank"><img src="../pan18-figures/mike.jpg" class="img-rounded" alt="Mike Kestemont"></a>
          <p style="white-space:nowrap"><a href="http://www.mike-kestemont.org/" target="_blank">Mike Kestemont</a></p>
          <p style="font-size:10pt">University of Antwerp</p>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-12">
        <h2>Task Committee</h2>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-6">
        <div class="thumbnail" style="text-align:center;">
          <a href="http://www.icsd.aegean.gr/lecturers/stamatatos/" target="_blank"><img src="../pan18-figures/stathis.jpg" class="img-rounded" alt="Efstathios Stamatatos"></a>
          <p><a href="http://www.icsd.aegean.gr/lecturers/stamatatos/" target="_blank">Efstathios Stamatatos</a></p>
          <p style="font-size:10pt">University of the Aegean</p>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="thumbnail" style="text-align:center;">
          <a href="http://www.clips.ua.ac.be/~walter/" target="_blank"><img src="../pan18-figures/walter.jpg" class="img-rounded" alt="Walter Daelemans"></a>
          <p style="white-space:nowrap"><a href="http://www.clips.ua.ac.be/~walter/" target="_blank">Walter Daelemans</a></p>
          <p style="font-size:10pt">University of Antwerp</p>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="thumbnail" style="text-align:center;">
          <a href="http://www.uni-weimar.de/medien/webis/people" target="_blank"><img src="../pan17-figures/martin.jpg" class="img-rounded" alt="Martin Potthast"></a>
          <p style="white-space:nowrap"><a href="http://www.uni-weimar.de/medien/webis/people" target="_blank">Martin Potthast</a></p>
          <p style="font-size:10pt">Bauhaus-Universit&auml;t Weimar</p>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="thumbnail" style="text-align:center;">
          <a href="http://www.webis.de" target="_blank"><img src="../pan17-figures/benno.jpg" class="img-rounded" alt="Benno Stein"></a>
          <p style="white-space:nowrap"><a href="http://www.webis.de" target="_blank">Benno Stein</a></p>
          <p style="font-size:10pt">Bauhaus-Universit&auml;t Weimar</p>
        </div>
      </div>
    </div>
  </div>

<footer>
  <p class="pull-right">© pan.webis.de</p>
</footer>

</div> <!-- /container -->

<script src="../../js/jquery.js"></script>
<script src="../../js/bootstrap.min.js"></script>
<script src="../../js/prettify.js"></script>
<script>
  !function ($) {
    $(function(){
      window.prettyPrint && prettyPrint()   
    })
  }(window.jQuery)
</script>

<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
  ga('create', 'UA-70770005-1', 'auto');
  ga('send', 'pageview');
</script>

</body>
</html>
