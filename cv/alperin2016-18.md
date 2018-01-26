<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
<script type='text/javascript'>
  $( document ).ready(function() {
    // clean up some dd's that don't have a p
    $("dd:not(:has('p'))").each(function(i, element) { 
      $(element).wrapInner('<p></p>');
    });

    $.getJSON('./scholar.json', function(article_stats) {
      article_ids = Object.keys(article_stats);
      $('a').each(function(i, element) { 

        var href = $(element)[0].getAttribute('href');
        if ($(element)[0].innerHTML.indexOf('doi.org') == 0 ) {
          $($(element)[0]).addClass('doiLink');
          var doi = $(element)[0].innerHTML;
          doi = doi.substr(doi.indexOf('/') + 1);  // strip out doi.org/ 
          $($(element)[0]).closest('dd').append('<div data-badge-popover="right" data-badge-type="2" data-doi="' + doi + '" data-hide-no-mentions="true" class="altmetric-embed"></div>');
            metrics = true;
        } else if (href.indexOf('scholar.google') > -1) {
          var gsid = href.substring(href.indexOf('cites=') + 6);
          if (article_ids.indexOf(gsid) > -1  ) {
            $($(element)[0]).closest('dd').append('<div class="google-scholar"><a href="' + href +'" ><img src="scholar_logo_long.png" align="left" /></a><span class="metricbubble">' + article_stats[gsid] + '</span></div>'
              );
            $(element).remove()
          } else {
            console.log("Not found, Google Scholar: " + gsid)
          }
        } 
      });  
    });

    $.getScript("https://d1bxh8uas1mnw7.cloudfront.net/assets/embed.js", function() {
        $('head').append('<link rel="stylesheet" href="./css-overrides.css" type="text/css" />')
    });

    $('head').append('<link rel="stylesheet" href="genericons/genericons.css" type="text/css" />');

    // Do some link handling
    $("a").attr('target','_blank');

    // change links called "link" to icon
    $("a").filter(function() {
      return $(this).text() === "link";
    }).addClass("with-genericon").addClass("externalLink").attr('alt', 'link to open access version').text(' ');

    // change links called "video" to icon
    $("a").filter(function() {
      return $(this).text() === "video";
    }).addClass("with-genericon").addClass("videoLink").attr('alt', 'link to video').text(' ');

    // change links called "slides" to icon
    $("a").filter(function() {
      return $(this).text() === "slides";
    }).addClass("with-genericon").addClass("slidesLink").attr('alt', 'link to slides').attr('title', 'link to slides').text(' ');

    // change Twitter link to icon
    $("a").filter(function() {
      return $(this).text() === "Twitter";
    }).addClass("with-genericon").addClass("contant-icon").addClass("twitterLink").attr('alt', 'Twitter').attr('title', 'Twitter').text(' ');

    // change Github link to icon
    $("a").filter(function() {
      return $(this).text() === "Github";
    }).addClass("with-genericon").addClass("contant-icon").addClass("githubLink").attr('alt', 'Github').attr('title', 'Github').text(' ');

    // change Github link to icon
    $("a").filter(function() {
      return $(this).text() === "email";
    }).addClass("with-genericon").addClass("contant-icon").addClass("emailLink").attr('alt', 'email').attr('title', 'email').text(' ');    

  });
</script>



# Juan Pablo Alperin
## Abbreviated CV: 2016–2018

[Twitter](http://twitter.com/juancommander)
[Github](http://github.com/jalperin)
[email](mailto:juan@alperin.ca)

> [Download PDF](alperinCV.pdf)

------

### Education {#education}

PhD Education, Stanford University 
: Multidisciplinary Studies in Education
  __2015__

Masters of Arts, University of Waterloo
: Geography
  __2008__

Bachelor of Mathematics, University of Waterloo
: Computer Science Honours, Combinatorics & Optimization Minor
  __2003__

------

### Professional Affiliations {#employment}

Assistant Professor
 : Simon Fraser University

Associate Director of Research
 : Public Knowledge Project

Director
 : Scholarly Communications Lab

-------

### Research Interests {#research}

1. public's use of research
2. societal impact of research
3. open science 
4. open access
5. higher education
6. scholarly communication
7. altmetrics
8. publishing technologies
9. 

------

### Teaching {.singlespace #teaching}

#### Seminar Courses 
: PUB802: Technology and the Evolving Forms of Publishing, Graduate [link](http://tkbr.ccsp.sfu.ca/pub802)
  __2014–2018__

#### Project Courses
: PUB607: Publishing Technology Project, Graduate [link](http://tkbr.ccsp.sfu.ca/pub607)
 __2014–2017__ 

#### Public Lectures
: *Does our research serve the public, or only ourselves?*, University of Illinois Urbana-Champaign [link](http://illinois.edu/calendar/detail/598?eventId=33263788)
__Mar. 2017__

#### Workshops
: Identifying audiences on Twitter, FORCE11 Scholarly Communications Summer Institute, San Diego University
__2017__
 
------

### Research Projects {#funding} 

#### Current 
: **Alperin, J.P.** et al. *Sustaining Open Access’ Most Widely Used Publishing Software*. Laura and John Arnold Foundation. *total award: C$89,295*
__2017-2018__

: **Alperin, J.P.** *&* Riedlinger, M. *Mapping the new landscape of science communication in Canada*. Social Science and Humanities Research Council (SSHRC). *total award: C$23,596*
__2017-2018__

: **Alperin, J.P.** et al. *Understanding Societal Impact of Research through Social Media*. Social Science and Humanities Research Council (SSHRC). *total award: C$217,401*
__2016-2019__

: **Alperin, J.P.**, et al. *Assessing the Value of Openness in Faculty Review and Promotion*. Open Society Foundations. *total award: C$146,612*
__2016-2018__

: Larivière, V. et al. (Collaborator). *Open Science: Social Science & Humanities Cyberinfrastructure*, Canada Foundation for Innovation (CFI). *total award: C$4,340,315* 
__2016-2018__

#### Teaching

: **Alperin, J.P.** *Encouraging and Supporting Discussions Through Online Annotations*. The Institute for the Study of Teaching and Learning in the Disciplines, SFU. *total award: C$5,000*
__2016__

: **Alperin, J.P.** *Building Foundations for Graduate Studies in Publishing*. Dean of Graduate Studies, SFU. *total award: C$5,000*
__2016__

------
### Publications {#publications}
#### In progress
: Schimanski, L., Muñoz, C., Niles, M., McKiernan, E. *&* **Alperin, J.P.** *Academic Freedom in Peril? The Threat of Publication Requirements for Tenure and Promotion*. 
__forthcoming__

: Niles, M., Fischman, G.E., Schimanski, L., Muñoz, C., Niles, M., McKiernan, E. *&* **Alperin, J.P.** *Serving the public or serving ourselves? A look at disincentives for public scholarship in the tenure review process*. 
__forthcoming__

: Schimanski, L. *&* **Alperin, J.P.**. *A Review of the Research on Promotion and Tenure Practices in the United States and Canada*. 
__forthcoming__

: Moscrop, D., Wong, L. *&* **Alperin, J.P.** *Have You Seen This? Why Political Pundits Share Scholarly Research on Social Media*. 
__forthcoming__

: Reilly, K. *&* **Alperin, J.P.** Theorizing Altmetrics as a Measure of Scholarly Impact: A Bounded Approach
__forthcoming__

#### Peer-Reviewed Publications
: **Alperin, J.P.**, Gomez, C. *&* Haustein, S. Identifying diffusion patterns of research on social media. *Public Understanding of Science.* 
__revisions__

: Siler, K., Haustein, S., Smith, E., Larivière, V. *&* **Alperin, J.P.** Authorial and institutional stratification in open access publishing: The case of global health research. *PeerJ*
__in press__

: Piwowar, H., Priem, J., Larivière, V., **Alperin, J.P.**, Matthias, L., Norlander, B., Farley, A., West, J. & Haustein, S. The State of OA: A large-scale analysis of the prevalence and impact of Open Access articles. *PeerJ* [preprint](https://doi.org/10.7287/peerj.preprints.3119v1) [doi.org/10.7287/peerj.preprints.3119v1](https://doi.org/10.7287/peerj.preprints.3119v1)
__in press__

: Barata, G., Haustein, S., Shores, K. *&* **Alperin, J.P.** Local chatter or international buzz? Differences in language of social posts about Zika research. *PLOS ONE.* [link](https://doi.org/10.1371/journal.pone.0190482) [10.1371/journal.pone.0190482](https://doi.org/10.1371/journal.pone.0190482)
__2018__

: Shu, F., Mongeon, P., Haustein, S., Siler, K., **Alperin, J.P.**, Larivière, V. Is it such a big deal? On the cost of journal use in the digital era. *College & Research Libraries.* [link](http://crl.acrl.org/index.php/crl/article/view/16829)
__2017__

: **Alperin, J.P.** *&* Rozemblum, C. The Reinterpretation of the Visibility and Quality of New Policies to Assess Scienti c Publications. *Revista Interamericana de Bibliotecologia*, 40(3). [link](https://doi.org/10.17533/udea.rib.v40n3a03) [10.17533/udea.rib.v40n3a03](https://doi.org/10.17533/udea.rib.v40n3a03) 
__2017__

: Garnett, A., Aufreiter, M., Buchtala, O., **Alperin, J.P.** Introducing Texture: An Open Source WYSIWYG Javascript Editor for JATS. *JATS-Con Proceedings 2017*, Bethesda: National Center for Biotechnology Information. [link](https://www.ncbi.nlm.nih.gov/books/NBK425544/)
__2017__

: Reilly, K.M.A. *&* **Alperin, J.P.** Intermediation in Open Development: A Knowledge Stewardship Approach. *Global Media Journal: Canadian Edition*, 6(1). [link](http://www.gmj.uottawa.ca/1601/v9i1_reilly%20and%20alperin_e.html) [Google Scholar](https://scholar.google.com/scholar?oi=bibs&hl=en&cites=7158654315290979739)
__2016__

: Carvalho Neto, S, Willinsky, J. *&* **Alperin, J.P.** Measuring, Rating, Supporting, and Strengthening Open Access Scholarly Publishing in Brazil. *Education Policy Analysis Archives*, 24(54). [doi.org/10.14507/epaa.24.2391](http://doi.org/10.14507/epaa.24.2391) [link](http://epaa.asu.edu/ojs/article/view/2391/1777) [Google Scholar](https://scholar.google.com/scholar?oi=bibs&hl=en&cites=18202986914726049811)
__2016__


#### Book Chapters 
: Reilly, K.M.A. *&* **Alperin, J.P.**. A Stewardship Approach to Theorizing Open Data for Development. In *Open Data for Development*. MIT Press.
__in press__ 

#### Other Publications
: **Alperin, J.P.** *The number and proportion of freely available articles is growing; reaching 45% of the literature published in 2015*. LSE Impact Blog. [link](http://blogs.lse.ac.uk/impactofsocialsciences/2017/08/07/the-number-and-proportion-of-freely-available-articles-is-growing-reaching-45-of-the-literature-published-in-2015/)
__2017__

: Piwowar, H., Priem, J., Larivière, V., **Alperin, J.P.**, Matthias, L., Norlander, B., Farley, A., West, J. *&* Haustein, S. Dataset from: The State of OA. *Zenodo*. [link](http://doi.org/10.5281/zenodo.837902) [doi.org/10.5281/zenodo.837902](http://doi.org/10.5281/zenodo.837902)
__2017__

: **Alperin, J.P.** How does Open Source Software Support Knowledge Dissemination? *Abierto al Público (Interamerican Development Bank Blog)*. [link](https://blogs.iadb.org/abierto-al-publico/2017/01/19/como-el-software-libre-apoya-la-diseminacion-del-conocimiento/)
__2017__

: **Alperin, J.P.** Motivating Open Practices Through Faculty Review and Promotion. *OOO Canada Blog* [link](http://www.ooocanada.ca/webinar_how_to_make_research_open_101)
__2016__

: Nicholson, J. *&* **Alperin, J.P.** A brief survey on peer review in scholarly communication. *The Winnower* [link](https://thewinnower.com/papers/4659-a-brief-survey-on-peer-review-in-scholarly-communication) [Google Scholar](https://scholar.google.com/scholar?oi=bibs&hl=en&cites=10951302768564561192)
__2016__

------

### Presentations {#presentations}
#### Invited Presentations 
: **Alperin, J.P.** Challenges with altmetrics across diverse sociocultural contexts. *1st Altmetrics Conference in Iran αLFA1*. Tehran, Iran. 
__Jan. 13, 2018__

: **Alperin, J.P.** Introducing the First Open Altmetrics Database. *INKE Victoria Gathering*. Victoria, Canada.
__Jan. 10, 2018__

: **Alperin, J.P.** Metrics to Incentivize Open Sharing. *OpenCon Satellite Event.* Online. 
__Nov. 8, 2017__

: **Alperin, J.P.**  Open Access and the evolution of Latin American scholarly journals. *I International University Book Fair*. Mexico City, Mexico.
__Aug. 24, 2017__

: **Alperin, J.P.** Research Perspectives Panel: Introducing the ScholCommLab. *PKP Scholarly Publishing Conference 2017*. Montreal, Canada. 
__Aug. 4, 2017__

: **Alperin, J.P.** Studying annotations in the classroom. *iAnnotate Conference.* San Francisco, USA. 
__May 6, 2017__

: **Alperin, J.P.** Shining a Light on Critical Reading with Online Annotations. *Digital Pedagogies Symposium.* Victoria, Canada. [slides](https://speakerdeck.com/jalperin/shining-a-light-on-critical-reading-through-online-annotations-explorations-into-the-use-of-hypothes-dot-is-in-the-classroom)
__May 5, 2017__

: **Alperin, J.P.** Failure of Access: Rethinking Open Education - Panel Discussion. *SFU Open Education Week.* Vancouver, Canada. [video](https://youtu.be/k6FvUTkxy58?t=2302)
__Mar. 28, 2017__

: **Alperin, J.P.**. ¿Que impacto miden las métricas alternativas en publicación científica?. *Aprender3c.* Online. 
__Nov. 28, 2016__

: **Alperin, J.P.** Ferramentas do PKP para publicação científica em acesso aberto. *Annual Meeting of the Brazilian Scientific Editors Association.* Sao Paolo, Brazil. 
__Nov. 7, 2016__

: **Alperin, J.P.** ¿Quien lee las revistas de acceso abierto de América Latina? *Congreso INFO 2016, Foro de Acceso Abierto.* Havana, Cuba. 
__Nov. 3, 2016__

: **Alperin, J.P.** Las limitaciones de los indicadores bibliometricos y las oportunidades del acceso abierto en América Latina. *Seminario el Nuevo Orden Academico: Pontificia Universidad Católica del Peru.* Lima, Peru. 
__Sep. 1, 2016__

: **Alperin, J.P.** Inherent Tensions in Adopting New Scholarly Practices. *61st Seminar on the Acquisition of Latin American Library Materials.* Charlottesville, USA. [slides](https://speakerdeck.com/jalperin/inherent-tensions-in-adopting-new-scholarly-practices)
__May 9, 2016__

: **Alperin, J.P.** Research is also for non-scholars: Lessons from Latin America. *FORCE16.* Portland, USA [doi.org/10.6084/m9.figshare.3187551](https://dx.doi.org/10.6084/m9.figshare.3187551.v1) [video](https://youtu.be/nO0f8bHAYqc?t=1674)
__April 19, 2016__

: **Alperin, J.P.** ¿Who benefits from Latin American research? *National Autonomous University of Mexico.* Mexico City, Mexico.
__Feb. 25, 2016__

: **Alperin, J.P.** Altmetrics: The Basics, the Research, and the Users. *Beedie Business School, Simon Fraser University.* Vancouver, Canada. 
__Feb. 10, 2016__

#### Peer-Reviewed Conference Presentations
: **Alperin, J.P.** *&* Haustein, S. Applying social network analysis to explore Twitter diffusion patterns. *Altmetrics17*. Toronto, Canada. [link](http://altmetrics.org/wp-content/uploads/2017/09/altmetrics17_paper_13.pdf)
__Sep. 26, 2017__

: Barata, G. *&* **Alperin, J.P.** Language metrics as a measure of global reach and local impact: The case of papers about Zika on Facebook and Twitter. *Altmetrics17*. Toronto, Canada. [link](http://altmetrics.org/wp-content/uploads/2017/09/altmetrics17_paper_8.pdf)
__Sep. 26, 2017__

: Didegah, F., Ghaseminik, Z. *&* **Alperin, J.P.** Comparing topics of interest in forum discussions and research articles in search of new indicators of the public’s interest in Diabetes. *Altmetrics17*. Toronto, Canada. [link](http://altmetrics.org/wp-content/uploads/2017/09/altmetrics17_paper_11.pdf) [slides](https://figshare.com/articles/Comparing_topics_of_interest_in_forum_discussions_Wiki_and_research_articles_in_search_of_new_indicators_of_the_public_s_interest_in_Diabetes/5443609)
__Sep. 26, 2017__

: **Alperin, J.P.** What is being published with OJS? and by whom? *PKP Scholarly Publishing Conference 2017*. Montreal, Canada. [slides](https://speakerdeck.com/jalperin/what-is-being-published-with-ojs-and-by-whom)
__Aug. 4, 2017__

: **Alperin, J.P.**, Hanson, E.W., Shores, K., *&* Haustein, S. Twitter bot surveys: A discrete choice experiment to increase response rates. *8th International Conference on Social Media and Society*. Toronto, Canada. [slides](https://speakerdeck.com/jalperin/twitter-bot-surveys-a-discrete-choice-experiment-to-increase-response-rates) [link](http://summit.sfu.ca/item/16763) [doi.org/10.1145/3097286.3097313](https://doi.org/10.1145/3097286.3097313)
__July 28, 2017__

: **Alperin, J.P.**, Stranack, K. *&* Garnett, A. On the Peripheries of Scholarly Infrastructure: A look at the Journals Using Open Journal Systems. *21st International Conference on Science and Technology Indicators (STI Conference 2016)*. Valencia, Spain. [link](http://summit.sfu.ca/item/17305) [slides](https://speakerdeck.com/jalperin/sti-ojsstats) [Google Scholar](https://scholar.google.com/scholar?oi=bibs&hl=en&cites=9988122229558301438)
__Sep. 14, 2016__

-------
### Awards {#awards .singlespace}
#### Fellowships
: Dewey Teaching Fellow: *Simon Fraser University*
__2018 - 2019__
: Future of Scholarly Communication and eScholarship Fellow: *FORCE11*
__2016__

------ 

### Supervision {#supervision .singlespace}
#### Visiting Scholars
: Germana Barata, University of Campinas, Brazil
__2017-present__

: Amin Erfanmanesh, University of Isfahan, Iran
__2017__

: Jon Tennant, Imperial College London, UK
__2017__

: Stefanie Haustein, University of Montreal, Canada
__2016__

#### Post-doctoral Supervision
: David Moscrop
__2017 – present__

: Fereshteh Didegah
__2017 – present__

: Kyle Siler
__2016 - 2017__

#### Senior Supervisor
: Sellars, Stacey. *Non-linear Digital Storytelling in the National Film Board of Canada's Interactive Projects*. Master in Publishing. SFU.
__in progress__

: Bell, Kirsten. *Risky business: Consultations with journal editors regarding a proposed cooperative scholarly publishing model*. Master in Publishing. SFU.
__2017__

: Oliviera, Joshua. *The Balancing Act: Balancing Journalism, Marketing and Publishing in Digital Content Marketing*. Master in Publishing. SFU.
__2017__

: Wake-Hyde, Zoë. *Openly Embracing Change: How the Rebus Foundation is Building a New Model of Publishing*. Master in Publishing. SFU.
__2016__

: Hanson, Erik. *Twitterbot Surveys: A Method for Magazine Audience Analysis*. Master in Publishing. SFU.
__2016__

: Wan, Linlin. *Copyleft and creativity*. Communications Double Major. 
__2016__

: Pouyanne, Sophie. *Designing a Non-linear, Academic Web Book with Scalar*. Master in Publishing. SFU.
__2016__

: Dunlop, Laura. *E-Cookbooks: An Analysis of Profitability*. Master in Publishing. SFU. 
__2016__

#### Supervisor
: Ashok, Apurva. *Opening the Doors to Knowledge: Rebus' Collaborative Publishign Model for Open Textbooks*. Master in Publishing. SFU. 
__2017__

: Zhao, Quiyo. *Cross-media Publishing by Orient Star Media*. Master in Publishing. SFU. 
__2017__

: Cuica, Aniela. *Modular content: a new publishing strategy at the Continuing Legal Education Society of British Columbia*. Master in Publishing. SFU. 
__2017__

: Firlotte, Molly. *An Analysis Of Outreach Strategies In Pursuit Revisiting The Porthole View: Of Market Expansion*. Master in Publishing. SFU.
__2016__

--------
### Professional Service {#professionalservice .singlespace}
#### Board Memberships
: Steering Committee: 
*Scholarly Publishing and Academic Resources Coalition (SPARC) Steering Committee*
__2015 - present__

: Scientific Academic Advisory Board: *Network of Scholarly Journals from Latin America, Spain, and Portugal (redalyc.org)*, 
__2014 - present__

#### Conference Activity
: Program Committee: 
*Electronic Publshing Conference (ELPUB 2018)*, Toronto, Canada
__2018__

: Program Committee: 
*Workshop on Altmetrics for Research Outputs Measurement and Scholarly Information Management (AROSIM 2018)*, Singapore. 
__2018__

: Scientific Committee:
*V Open Science Forum (INFO2018)*, Havana, Cuba
__2018__

: Organizing Committee: 
*OpenCon Latin America 2017*, Mexico City, Mexico.
__2017__

: Scientific Committee:
*XXI International Conference On Science And Technology Indicators*, Valencia, Spain
__2016__

: Scientific Committee:
*IV Open Access Forum (INFO2016)*, Havana, Cuba
__2016__

: Application Review Team: 
*OpenCon: The student and early career academic professional conference on Open Access, Open Education, and Open Data*, Brussels, Belgium
__2015, 2016__

#### Editorial Teams
: Review Editor, *Scholarly Metrics and Analytics*
__2016 - present__

: Founding Editorial Team, *Scholarly and Research Communication*
__2010 - present__

: Technical Editor, *Education Policy Analysis Archives*
__2008 - present__

#### Reviewer
: *The Journal of Web Science*, *Aslib Proceedings (2)*, *Information Research (2)*, *eLife*, *Scientometrics (2)*, *TLA-MELAUA*, *Nature*, *Science and Public Policy (2)*, *Publications*

#### Memberships
: Metadata 2020 Working Group, BOAI 15 Working group, CrossRef DOI Event Tracker Committee, OOO Canada

--------
### Departmental Service {#departmentalservice .singlespace.noheading}
&nbsp;
: Graduate Program Chair
__2015 - present__

: Faculty search committees (3)
__2014 - present__

: All program committees
__2014 - present__

: Library Open Access Advisory
__2014 - 2016__

--------
### Media Coverage {#mediacoverage .singlespace.noheading}
&nbsp;
: *PLOS Blogs* Open Access 2017: A Year of Stand-Offs, Showdowns, & Funders’ Own Journals. [link](http://blogs.plos.org/absolutely-maybe/2018/01/09/open-access-2017-a-year-of-stand-offs-showdowns-funders-own-journals/)

: *El Espectador* Una oportunidad para pensar el acceso abierto desde América Latina. [link](https://www.elespectador.com/tecnologia/una-oportunidad-para-pensar-el-acceso-abierto-desde-america-latina-articulo-726364)
__Dec. 2, 2017__

: *Universo Abierto* “Casi la mitad” de los trabajos de investigación recientes están en acceso abierto. [link](https://universoabierto.org/2017/11/23/casi-la-mitad-de-los-trabajos-de-investigacion-recientes-estan-en-acceso-abierto/)
__Nov. 23, 2017__

: *Le Monde* Des chercheurs se mobilisent pour un accès gratuit aux publications. [link](http://mobile.lemonde.fr/sciences/article/2017/11/06/des-chercheurs-se-mobilisent-pour-un-acces-gratuit-aux-publications_5210895_1650684.html)

: *Scholarly Kitchen* Study Suggests Publisher Public Access Outpacing Open Access; Gold OA Decreases Citation Performance. [link](https://scholarlykitchen.sspnet.org/2017/10/04/study-suggests-publisher-public-access-outpacing-open-access-gold-oa-decreases-citation-performance/)
__Oct. 4, 2017__

: *Al-Fanar Media* A Rising Number of Research Results Is Available Free. [link](https://www.al-fanarmedia.org/2017/09/rising-number-research-results-available-free/)
__Sep. 29, 2017__

: *Quartz* Soon, nobody will read academic journals illegally, because the studies worth reading will be free. [link](https://qz.com/1049870/half-the-time-unpaywall-users-search-for-articles-that-are-legally-free-to-access/)
__Aug. 9, 2017__

: *Phys.org* Two studies suggest trouble ahead for paywall journals. [link](https://phys.org/news/2017-08-paywall-journals.html)
__Aug. 8, 2017__

: *Nature News* Half of papers searched for online are free to read. [link](http://www.nature.com/news/half-of-papers-searched-for-online-are-free-to-read-1.22418)
__Aug. 7, 2017__

: *The Scientist* Open Access On the Rise: Study (Interview with co-author). [link](http://www.the-scientist.com/?articles.view/articleNo/50027/title/Open-Access-On-the-Rise--Study/)
__Aug. 7, 2017__

: *Open and Shut?* The State of Open Access: Some New Data (Interview with co-author). [link](http://poynder.blogspot.ca/2017/08/the-state-of-open-access-some-new.html)
__Aug. 3, 2017__

: *Nature* Trend Watch: The State of Open Access. [link](https://www.nature.com/news/exomoon-candidate-fake-peer-review-and-a-telescope-problem-1.22389)
__Aug. 2, 2017__ 

: *Revista Anfibia (Universidad Nacional de San Martin)*. Los Dueños de la ciencia. [link](http://www.revistaanfibia.com/ensayo/los-duenos-de-la-ciencia/)
__May, 2017__

: *Copyright Chat*. University of Illinois at Urbana-Champaign podcast. [link](http://www.stitcher.com/podcast/copyright-chat/e/50165849)
__Mar. 17, 2017__

: *CONACYT Prensa*. ¿Cuál es el impacto social de las revistas científicas?
[link](http://www.conacytprensa.mx/index.php/sociedad/politica-cientifica/5786-debate-sobre-el-impacto-social-de-las-revistas-cientificas-nota-fil)
__Mar. 2, 2016__

------ 