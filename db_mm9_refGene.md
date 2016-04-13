<div id="center-content" class="box">

<div id="header">

<div id="logo">

[![(please configure the \[header\_logo\] section in
trac.ini)](/trac/trac_backup/chrome/site/novologo640t2.png)]()

</div>

------------------------------------------------------------------------

<div class="noscreen noprint">

*Quick links: [content](#main), [navigation](#mainnav),
[search](#theme-search).*

------------------------------------------------------------------------

</div>

<div id="theme-search" class="noprint">

Search <span class="noscreen">Find:</span> <span
id="search-input-out"></span>

</div>

</div>

<div id="theme-mainnav" class="noprint">

### Navigation {#navigation .noscreen}

-   [Wiki<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/wiki)
-   [Timeline<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/timeline)
-   [Roadmap<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/roadmap)
-   [Browse Source<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/browser)
-   [View Tickets<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/report)
-   [New Ticket<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/newticket)
-   [Search<span class="tab-l"></span><span
    class="tab-r"></span>](/trac/trac_backup/search)

------------------------------------------------------------------------

</div>

<div id="page" class="box">

<div id="page-in" class="box">

<div id="strip" class="box noprint">

<div id="ctxtnav" class="nav">

-   [Start Page](/trac/trac_backup/wiki/WikiStart)
-   [Index](/trac/trac_backup/wiki/TitleIndex)
-   [History](/trac/trac_backup/wiki/db_mm9_refGene?action=history)

</div>

<div id="metanav" class="nav">

-   logged in as amirh
-   [Logout](/trac/trac_backup/logout)
-   [Preferences](/trac/trac_backup/prefs)
-   [Help/Guide](/trac/trac_backup/wiki/TracGuide)
-   [About Trac](/trac/trac_backup/about)

</div>

</div>

<div id="main">

<div id="content" class="wiki">

<div class="wikipage searchable">

<div class="trac-modifiedby">

<span>[Last
modified](/trac/trac_backup/wiki/db_mm9_refGene?action=diff&version=7 "Version 7 by sharonc")
[6
years](/trac/trac_backup/timeline?from=2010-08-24T12%3A12%3A03%2B08%3A00&precision=second "2010-08-24T12:12:03+08:00 in Timeline"){.timeline}
ago</span> <span class="trac-print">Last modified on 08/24/10
12:12:03</span>

</div>

<div id="wikipage">

Schema for [RefSeq?](/trac/trac_backup/wiki/RefSeq){.missing .wiki} Genes - [RefSeq?](/trac/trac_backup/wiki/RefSeq){.missing .wiki} Genes {#SchemaforRefSeqGenes-RefSeqGenes}
==========================================================================================================================================

Database: **mm9**

Primary Table: **refGene**

Row Count: **27,480**

Format description: **A gene prediction with some additional info.**

  -------------- -------------------------------- ------------------------------------ -------- ---------------------------------------------------
  field          example                          SQL type                             info     description
  bin            164                              smallint(5) unsigned                 range    Indexing field to speed chromosome range queries.
  name           NM\_010110                       varchar(255)                         values   Name of gene (usually transcript\_id from GTF)
  chrom          chrX                             varchar(255)                         values   Reference sequence chromosome or scaffold
  strand         +                                char(1)                              values   + or - for strand
  txStart        96331468                         int(10) unsigned                     range    Transcription start position
  txEnd          96344330                         int(10) unsigned                     range    Transcription end position
  cdsStart       96332224                         int(10) unsigned                     range    Coding region start
  cdsEnd         96342866                         int(10) unsigned                     range    Coding region end
  exonCount      5                                int(10) unsigned                     range    Number of exons
  exonStarts     96331468,96340630,96341816,...   longblob                                      Exon start positions
  exonEnds       96332352,96340908,96341909,...   longblob                                      Exon end positions
  id             225687                           int(10) unsigned                     range    Unique identifier
  name2          Efnb1                            varchar(255)                         values   Alternate name (e.g. gene\_id from GTF)
  cdsStartStat   cmpl                             enum('none','unk','incmpl','cmpl')   values   enum('none','unk','incmpl','cmpl')
  cdsEndStat     cmpl                             enum('none','unk','incmpl','cmpl')   values   enum('none','unk','incmpl','cmpl')
  exonFrames     0,2,1,1,1,                       longblob                                      Exon frame {0,1,2}, or -1 if no frame for exon
  -------------- -------------------------------- ------------------------------------ -------- ---------------------------------------------------

### Connected Tables and Joining Fields {#ConnectedTablesandJoiningFields}

> mm9.all\_est.qName (via refGene.name)

> mm9.all\_mrna.qName (via refGene.name)

> mm9.ccdsInfo.mrnaAcc (via refGene.name)

> mm9.gbCdnaInfo.acc (via refGene.name)

> mm9.gbMiscDiff.acc (via refGene.name)

> mm9.gbSeq.acc (via refGene.name)

> mm9.gbStatus.acc (via refGene.name)

> mm9.gbWarn.acc (via refGene.name)

> mm9.imageClone.acc (via refGene.name)

> mm9.kgXref.refseq (via refGene.name)

> mm9.knownToRefSeq.value (via refGene.name)

> mm9.mrnaOrientInfo.name (via refGene.name)

> mm9.refFlat.name (via refGene.name)

> mm9.refLink.mrnaAcc (via refGene.name)

> mm9.refSeqAli.qName (via refGene.name)

> mm9.refSeqStatus.mrnaAcc (via refGene.name)

> mm9.refSeqSummary.mrnaAcc (via refGene.name)

> mm9.seq.acc (via refGene.name)

> mm9.xenoMrna.qName (via refGene.name)

> mm9.xenoRefGene.name (via refGene.name)

> mm9.xenoRefSeqAli.qName (via refGene.name)

### Sample Rows {#SampleRows}

  ------ --------------- ------- -------- ----------- ----------- ----------- ----------- ----------- -------------------- --------------------
  bin    name            chrom   strand   txStart     txEnd       cdsStart    cdsEnd      exonCount   exonStarts           exonEnds
  866    NM\_009841      chr18   -        36884720    36886308    36884953    36886145    2           36884720,36886142,   36886051,36886308,
  743    NM\_001166750   chr7    +        20779058    20779981    20779058    20779981    1           20779058,            20779981,
  1433   NM\_147121      chr7    -        111216598   111217543   111216598   111217543   1           111216598,           111217543,
  ------ --------------- ------- -------- ----------- ----------- ----------- ----------- ----------- -------------------- --------------------

[Back to Database Schema Page](/trac/trac_backup/wiki/ddSchema){.wiki}

</div>

</div>

<div id="attachments">

</div>

<div class="buttons">

<div>

</div>

<div>

</div>

</div>

</div>

<div id="altlinks">

### Download in other formats:

-   [Plain Text](/trac/trac_backup/wiki/db_mm9_refGene?format=txt)

</div>

</div>

</div>

</div>

<div id="footer" lang="en" lang="en">

<div id="top" class="noprint">

<span class="noscreen">Back on top</span>
[\^<span></span>](#header "Back on top ^")

</div>

------------------------------------------------------------------------

[![Trac
Powered](/trac/trac_backup/chrome/common/trac_logo_mini.png){width="107"
height="30"}](http://trac.edgewall.org/){#tracpowered}
Powered by [**Trac 0.12.5**](/trac/trac_backup/about)\
By [Edgewall Software](http://www.edgewall.org/).

Original theme created\
by [Nuvio | Webdesign](http://www.nuvio.cz)

Visit the Trac open source project at\
<http://trac.edgewall.org/>

</div>

</div>
