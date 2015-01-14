# CPAN History

### Version 0.1

This document is a history of the Comprehensive Perl Archive Network,
or [CPAN](http://www.cpan.org). CPAN is a collection of open source
Perl libraries, contributed by 6000+ developers over a period of 19 years.
The archive is mirrored on 250+ servers around the world.

But this is also a history of the other services that make up the CPAN
ecosystem, and the people who made it all happen.

This is the first version of this history, and it's been pulled together
in something of a rush. Apologies to all those who should be here,
but aren't yet.
The [master copy](https://github.com/neilbowers/history-of-cpan) is on github,
please send pull requests with additions and corrections.
You can just add topics to the todo list at the end of this document.

## The perl 4 days

With perl 4, we didn't have modules,
we had .pl library files.
For example, before the [`CGI`](https://metacpan.org/pod/CGI)
module we had [`cgi-lib.pl`](http://cgi-lib.berkeley.edu).
These libraries were collections of functions,
which you included in your code with:

    require 'cgi-lib.pl';

Perl 4.036 was the final release of Perl 4, on 5th Feb 1993.
It came with 31 libraries,
for example <tt>getopts.pl</tt> for processing command-line arguments.

There were also many third-party libraries,
written by Perl users around the world.
These were collected together in various ftp sites.
There wasn't any single master site.
The big ones were funet.fi, metronet, coombs, and ??

The libwww-perl project started at the first WWW conference in 1994
(Geneva) where
Martijn Koster ([MAK](https://metacpan.org/author/MAK))
discussed MOMspider with Roy Fielding
(later of REST fame).
Martijn suggested that it would be a good thing if the reusable components
of this program were broken out into a library. The result was the
libwww-perl library for perl4 that Roy maintained

Perl version 1 included tests that were based on what became the
test anything protocol (TAP):
printing "ok #" or "not ok #" to STDOUT.
Up to Perl 5, tests just effectively did <tt><b>print "ok 1\n"</b></tt>.

The USENET group comp.lang.perl is where most public perl discussion happened
at this time,
and where people announced new libraries, and where to find them.


## perl-packrats

The perl-packrats mailing list was created by Bill Middleton (Bill)
on 2nd December 1993, for discussion between people who were maintaining ftp sites for perl.
Founding members: Bill,
Tom Christiansen ([TOMC](https://metacpan.org/author/TOMC)),
Henk Penning (Henk),
Jarkko Hietaniemi ([JHI](https://metacpan.org/author/JHI)),
Stephen Potter ([SPP](https://metacpan.org/author/SPP)),
Lee McLoughlin ([LMJM](https://metacpan.org/author/LMJM)),
and Mark ?? (coombs).

On December 6th,
Bill emailed a [list of topics](https://raw.githubusercontent.com/neilbowers/history-of-cpan/master/packrats/wjm-1993-12-06.txt) for discussion,
which included "master archive".
On the same day,
an email from Jared Rhine ([JARED](https://metacpan.org/author/JARED))
was forwarded to the list,
in which he wrote "I propose that we cooperate to create a unified structure,
much like the [CTAN](http://www.ctan.org) project".

On December 7th,
Bill emailed the CTAN admins asking for any advice and any tools
for running a CTAN-like thing.
[Sebastian Rahtz](http://users.ox.ac.uk/~rahtz/) replied with some tips
("an agreed structure is crucial"),
also saying that CTAN mostly ran on "luck and spit" :-)

On 10th December,
JARED mailed a more concrete and detailed proposal,
and used the name "CPAN" for the first time.

From there they got into more pragmatic concerns, like mirroring,
and how to handle the transition to a standard structure without
breaking all existing references to the different structures (symlinks!).
Remember this was 1993, so there was discussion about what interfaces,
protocols, and tools to use:
[archie](http://en.wikipedia.org/wiki/Archie_search_engine),
[gopher](http://en.wikipedia.org/wiki/Gopher_(protocol)),
[WAIS](http://en.wikipedia.org/wiki/Wide_area_information_server),
[http](http://en.wikipedia.org/wiki/Http),
[ftp](http://en.wikipedia.org/wiki/Ftp), ...

Then Christmas came, and things cooled for a while.
Partly because everyone was playing with alpha and beta
(and gamma, on Oct 14th 1994!) releases of Perl 5...

As people were kicking the tyres of Perl 5, they started writing modules.
In August 1994, Tim Bunce ([TIMB](https://metacpan.org/author/TIMB))
created the Module List,
which was a manually edited text file containing an index
of all known Perl 5 modules.
I don't have a copy of the first-ever list,
but [revision 2.2](http://groups.google.com/groups?selm=perl-faq/module-list-1-794455075%40ig.co.uk) was posted 7th March 1995.
For a long time this was the place to look,
to find out what modules were available for Perl 5.

In the Perl 4 days, using a database typically required you to
compile a special version of Perl for each kind of database,
each with an incompatible API.
Buzz Moschetti, the author of the
Interbase perl, emailed the other authors on 29th September 1992 to say
"it might be a
swell idea to standardize our perl-DB-API interfaces". They agreed
and the "DBperl" project was born.
TIMB joined the effort a few days later.
After a year or so, TIMB became the lead for implementing the
DBperl project for Perl 5, later renamed "DBI",
and [`DBD::Oracle`](https://metacpan.org/pod/DBD::Oracle),
the first driver.
The first public release of [`DBI`](https://metacpan.org/pod/DBI)
was on 12th October 1994,
5 days before the first public release of Perl 5.


## Perl 5

Perl 5 was first released 17th October 1994,
introducing modules, which could be object-oriented (OO)
as well as collections of functions.
That first release included
[`ExtUtils::MakeMaker`](https://metacpan.org/pod/ExtUtils::MakeMaker),
which effectively defined what distros would look like.

Releasing a module generally involved putting it on an ftp site somewhere,
then posting about it to USENET group comp.lang.perl.

[Test::Harness](https://metacpan.org/pod/Test::Harness)
was written by ANDK and TIMB,
and came with the first release of Perl 5.
This allowed modules to write tests based around Perl's core testing model.

12th Feb 1995, JHI emailed packrats saying "let's do this CPAN thing",
proposing a directory structure, and that he was going to get on with it.

> *For me this is a key moment.
> It needed someone to say "right, I'm gonna do it"*
>
> ["Nothing gets done without someone doing it"](http://groups.google.com/groups?selm=1994Nov8.014614.13584%40netlabs.com) &mdash; Larry Wall 1994-11-08 (ie not in response to this).

JARED followed up on the 20th with some proposed principles
(easy to maintain, easy to submit, things should have an abstract,
tagging *ahem*).

March 17th Ian Burrell ([IBURRELL](https://metacpan.org/author/IBURRELL))
posted some questions and thoughts about how scripts and modules
would be indexed.

15th April, TOMC posted a list of extensions
("module" and "extension" were both widely used),
which he'd pulled together, saying they were hard to find.
Kenneth Albanowski ([KJALB](https://metacpan.org/author/KJALB))
replied it would be easier if authors of modules had
"some place standard to deposit them",
and this place could be used to populate the repositories.

17th April, Andreas König ([ANDK](https://metacpan.org/author/ANDK))
suggested a "MASTER site for modules",
which would be mirrored by the official repositories.
He said "I have written 33% of the programs needed".
Up to this point different modules and packages had different master sites.

> *This is the second key "I'm gonna do it" moment.*

29th April: ANDK emailed with details of his "first cut".
This wasn't for uploads at this point:
it was a central database of URLs pointing to the master copy of perl modules
(I think!).
The goal at this point was the automated maintenance of
TIMB's module list,
or at least a central database that held the information
needed to build the list.

May 4th: TIMB announced an incoming/ directory on ftp.demon.co.uk
where authors could upload modules (and other perl things).

May 12th: TIMB expressed some frustration with the lack of progress,
and desire to get on with things.
Bill noted that there was no-one "in charge",
and that maybe part of the problem was trying to cope with everything,
so why not focus on modules and perl source.
JHI apologised for the delay in his (CPAN) efforts,
but said his Master's thesis was taking priority,
for just a little while longer...

In Perl 4, cgi-lib.pl was the de facto standard used when creating CGI scripts.
In June 1995 Lincoln Stein ([LDS](https://metacpan.org/author/LDS))
created the [CGI](https://metacpan.org/pod/CGI) module,
a 'port' of cgi-lib.pl.
For many years it was the way people created dynamic web interfaces in Perl.
So much so that it was "moved into the core",
and bundled with Perl from 5.004 onwards
(it was dropped from the core in Perl 5.20, in 2014).

## CPAN and PAUSE take shape

5th June, JHI announced "CPAN v0.000" to perl-packrats, saying it was built from "about a dozen ftp sites". There was still discussion about what the "proper name" should be (REEPH, ARK, EYEKAP).

1st August, JHI announced the "CPAN private showing".

15th August,
ANDK emailed saying that he'd rethought what was needed for upload,
asking for input, but that he was coding *NOW*.
He started working on a database and upload server. During his development the first true upload was logged in the database: Symdump 1.20, on 16th August 1995.
Initially people were uploading files into a directory structure that mirrored the module list.

17th August, KJALB said "Username directory seem to make sense in general",
to which ANDK replied "!!!! light bulb on !!!!",
to which KJALB in turn replied, "I think an author tree is a good idea, especially as automatically generating a symlinked module tree from the author tree and the module list should be quite simple".

If you look at the early PAUSE uploads, most days there are just one or
two uploads. But on 20th August it *looks* as if 14 different people
uploaded 28 releases.
But in fact this was ANDK testing: he grabbed releases from the early
pioneers,
and was doing 'uploads by proxy'.
Those early pioneers: AMOSS, ANDK, FMC, GBARR, GBOSS, ILYAZ, JACKS, JKAST,
KJALB, MICB, NWINT, SPIDB, TYEMQ, WPS.

Those early uploads were proper modules,
with a Makefile.PL based on
[ExtUtils::MakeMaker](https://metacpan.org/pod/ExtUtils::MakeMaker).

Aug 21st, ANDK emailed an update on the "module list server", which was starting to sound a bit like modern PAUSE by this point. It used Msql for the database and LWP for network stuff. Author directories were CPAN/mod/pml/byauthor/<id> (what did PML stand for? Perl module list?)

Sep 20th: ANDK emailed an update, where I think he established himself and TIMB as the first "PAUSE admins" (though they weren't referred to as that). At this point there was a close linkage between the module list and the nascent PAUSE.

Sep 25th: TIMB asked JHI and ANDK if they were ready to announce CPAN and the module upload server?

Sep 27th: JARED proposed a change in directory structure for the module part
of CPAN, to have three key trees:
by-author, by-category, and by-module.
Category was thematic (eg www would contain LWP),
where by-module was by the namespace of modules (so LWP would be under LWP/).
In response ANDK suggested `pml/byauthor/`.

29th Sep: JHI did a bunch of reorg on CPAN,
and replied that he wasn't quite ready to announce it: "RSN" :-)

Oct 4th: ANDK created `by-module/` and `by-category/`.
Lots of discussion followed...

Oct 8th: ANDK created `authors/id/` as the root of the author directories,
so his directory was `authors/id/ANDK/`.
This structure remained until May 2000.

Oct 12th: ANDK noted that the Module List Server had become a
Perl Authors Upload Server, or CPAN Lounge, or Open CPAN.
He didn't use the PAUSE acronym just yet ...

Oct 15th: ANDK -> JHI "isn't it time?". JHI: "I guess so". Such unbridled enthusiasm!

Oct 16th: ANDK "I'm tempted to call franz the PAUSE, the Perl Authors Upload SErver, indicating, that each author has deserved some break after having coded bravely for that many hours". The first use of the name PAUSE.

> *When was PAUSE announced to the public? It wasn't mentioned in the CPAN announcement.*

## The CPAN years

Oct 26th: [JHI announced CPAN to c.l.p.a](http://groups.google.com/groups?selm=46o5va$33f%40maureen.teleport.com)

May 1996: Gisle Aas ([GAAS](https://metacpan.org/author/GAAS))
released the first version of libwww-perl-5 (aka LWP).
This was a Perl 5 rewrite of the libwww-perl library for Perl 4.
LWP was written by MAK and GAAS, but subsequently maintained by Gisle for many years. For a long time this was *the* library for writing HTTP clients in Perl.

August 19-21 1997: O'Reilly ran the first Perl Conference.
Of note here is that this was the first time that JHI and ANDK met face to face.
It was the first time many key players in Perl met face to face.

> *Does anyone have any photos of ANDK and JHI together at the conference?*

The [Test](https://metacpan.org/pod/Test) module was released by Joshua Pritikin
([https://metacpan.org/author/JPRIT](https://metacpan.org/author/JPRIT))
in January 1998.
This introduced the notion of structuring tests using a module.
It wasn't very widely used,
but was the start of what became a large movement in Perl / CPAN history.

In May 1998, Graham Barr ([GBARR](https://metacpan.org/author/GBARR))
and Chris Nandor ([CNANDOR](https://metacpan.org/author/CNANDOR))
had the idea for [CPAN Testers](http://www.cpantesters.org):
multi-platform testing of distributions uploaded to CPAN.
The service launched in 1999,
and the volunteer testers had to upload test reports by hand.

19th May 1999:
GBARR emailed P5P a link to a web site which had docs for all modules, crosslinked.
This early version of [search.cpan.org](http://search.cpan.org)
was running on a machine at his home.

In July 1999, ANDK and Loic Dachary
([LDACHARY](https://metacpan.org/author/LDACHARY)) did some major work on PAUSE,
including a rework of the database schema.
From this point forwards,
we know the date and time for when PAUSE accounts were created.
All of the existing accounts had their creation date set to Thu Jun 10 16:48:40 1999 (epoch time: 929033320), so we know there were 694 PAUSE accounts by this point.

In August 1999, the UI for PAUSE was overhauled, and it switched to using MySQL (from Msql).

In August 1999, Andy Wardley ([ABW](https://metacpan.org/author/ABW))
released the [Template Toolkit](https://metacpan.org/pod/Template).
This was his second templating system,
and was driven by the lessons he'd learned writing
[Text::MetaText](https://metacpan.org/pod/Text::MetaText).

[BackPAN](http://backpan.perl.org) was started by ANDK on the 4th February 2000.
This holds a copy of everything ever released to CPAN,
including things that are no longer on CPAN.
CPAN Testers has a [longer description of BackPAN](http://backpan.cpantesters.org).

In May 2000, the author directories were changed from authors/id/ANDK/ to the current format format authors/id/A/AN/ANDK/.

Michael Schwern ([MSCHWERN](https://metacpan.org/author/MSCHWERN))
posted [the initial idea for CPANTS](http://www.nntp.perl.org/group/perl.qa/2000/08/msg149.html) in August 2000.
It was conceived as a 'CPAN Testing Service' that would measure the 'kwalitee'
of a CPAN distribution, a measure of how well-behaved a dist is,
in terms of working with the rest of the CPAN ecosystem.
The original vision was broader than the current system.
It would be a few years before anything got implemented...

In October 2000, the PAUSE database was converted to UTF-8.

December 2000: Mark Fowler started the first Perl Module Advent Calendar.

In 2001, MSCHWERN released [Test::Simple](https://metacpan.org/pod/Test::Simple),
[Test::Tutorial](https://metacpan.org/pod/Test::Tutorial)
and
[Test::More](https://metacpan.org/pod/Test::More).
These were designed to provide a simple clear interface,
to encourage more people to write tests.

Between 2000 and 2002, the testing culture in Perl, and CPAN,
really started to take off.
Many more core modules had tests,
and CPAN modules started to switch from a <tt>test.pl</tt> testsuite
(whose output wasn't parsed), to the `t/*.t` system.

Paul Johnson ([PJCJ](https://metacpan.org/author/PJCJ))
had written code coverage tools for Hardware
Description Languages and wanted something similar for Perl.
However, it wasn't until Perl 5.6.1 that perl provided the
infrastructure to make that feasible.
On 9th April 2001, the day after 5.6.1 was released,
[Devel::Cover](https://metacpan.org/pod/Devel::Cover) 0.01
was [announced](http://www.nntp.perl.org/group/perl.qa.metrics/2001/04/msg4.html)
on the perl-qa mailing list.

20th May 2001: PAUSE's official hostname became `pause.perl.org`.

Following discussions at YAPC::EU in 2001,
Jos Boumans ([KANE](https://metacpan.org/author/KANE))
wrote [CPANPLUS](https://metacpan.org/pod/CPANPLUS),
an alternative installer to CPAN.pm.
One feature of CPANPLUS was that it automated the sending of
test reports to cpan-testers.

In Sept 2001,
chromatic ([chromatic](https://metacpan.org/author/CHROMATIC)) and SCHWERN
released [Test::Builder](https://metacpan.org/pod/Test::Builder).
This moved the guts of the testing model / framework into a separate library,
opening the door for more specialised testing libraries that could be used together
in the same testsuite.

While working on [Devel::Cover](https://metacpan.org/pod/Devel::Cover),
PJCJ started testing it with more and more CPAN distributions.
Eventually this grew into [cpancover](http://cpancover.com),
which aims to run coverage tests for as much of CPAN as possible.
It [started running](https://web.archive.org/web/20021003051502/http://pjcj.sytes.net/cover/cpancover/cpancover.html)
in October 2002,
and was [announced on the perl-qa mailing list](http://www.nntp.perl.org/group/perl.qa/2002/12/msg1778.html) in December 2002.

Inspired by MSCHWERN's vision,
Léon Brocard ([LBROCARD](https://metacpan.org/author/LBROCARD))
implemented the first version of part of CPANTS, which was released 24th March 2003.
Module::CPANTS held the result data,
and was created by
[Module::CPANTS::Generator](https://metacpan.org/pod/Module::CPANTS::Generator).

In 2003, the [Phalanx 100 project](http://qa.perl.org/phalanx/) was started by
Andy Lester ([PETDANCE](https://metacpan.org/author/PETDANCE)) and others (who?).
The goal was to identify the top 100 CPAN dists,
in terms of most widely used by other dists.
Then improve test coverage and fix bugs,
to improve the overall quality / reliability of CPAN.  Results?

In August 2003 Ask Bjørn Hansen ([ABH](https://metacpan.org/author/ABH))
[announced](http://use.perl.org/use.perl.org/printec8f.html?sid=03/08/13/1350221)
a beta of [cpanratings.perl.org](http://cpanratings.perl.org),
a site where perl users could review CPAN modules, giving comments and a 1-5 star rating. When you see stars ratings on MetaCPAN, they're coming from CPAN ratings.

In September 2003, Thomas Klausner ([DOMM](https://metacpan.org/author/DOMM))
took over CPANTS and rewrote everything, so the data was stored in a database.
This resulted in
[Module::CPANTS::Analyse](https://metacpan.org/pod/Module::CPANTS::Analyse)
and the other modules, which are still part of CPANTS today (2014).

In February 2004, Simon Cozens ([SIMON](https://metacpan.org/author/SIMON))
released [Maypole](https://metacpan.org/pod/Maypole). Was this the first popular
web application framework for Perl 5?

Sebastian Riedel ([SRI](https://metacpan.org/author/SRI)) had been working on
Maypole with others, but had different ideas from SIMON on how it should evolve,
and left to start his own project.
This resulted in [Catalyst](https://metacpan.org/pod/Catalyst),
which was first released in February 2005.

In February 2005, Audrey Tang ([AUDREYT](https://metacpan.org/author/AUDREYT))
started the [Pugs](http://www.pugscode.org) project; Pugs was an implementation
of Perl6 in Haskell.

8th August 2005: first release of DBIx::Class

Stevan Little ([STEVAN](https://metacpan.org/author/STEVAN)) spent some
months working with AUDREYT on the Perl6 project. One of the things he
worked on was the object system,
described in [Synopsis 12](http://perlcabal.org/syn/S12.html).
Working in Perl 5, he wanted similar capabilities, so started working on
them. Several failed prototypes later,
he released [Class::MOP](https://metacpan.org/pod/Class::MOP) in January 2006.
Two months later he released [Moose](https://metacpan.org/pod/Moose)
0.01, which revolutionised the Perl OO world.

In August 2006, David Golden ([DAGOLDEN](https://metacpan.org/author/DAGOLDEN))
released [CPAN::Reporter](https://metacpan.org/pod/CPAN::Reporter),
which enabled CPAN.pm to submit test reports to CPAN Testers
when people install things from CPAN.

After time away from doing Ruby, SRI returned to Perl in 2008, and started
the [Mojo](https://metacpan.org/pod/Mojo) project, as a new foundation
for Catalyst. That didn't work out,
and [Mojolicious](https://metacpan.org/pod/Mojolicious) was created as a web
toolkit, to demonstrate the capabilities of Mojo.
Mojolicious took on a life of its own.

In 2008, people realised that Perl's testing model might be of interest
outside the Perl community.
It was at this point that it got the name [TAP](http://testanything.org),
and people started talking about it more widely.

Having got to the point where he was maintaining a lot of CPAN dists,
Rik Signes ([RJBS](https://metacpan.org/author/RJBS))
became frustrated at the amount of time spent typing the same boilerplate
over and over, and how many rote tasks were involved in releasing code.
Existing release automation tools couldn't be customized to work the way he
wanted, so over the course of a few hours on the bus,
[Dist::Zilla](https://metacpan.org/pod/Dist::Zilla) was born
(["Dist::Zilla is a tool for writing less crap and more code when building
CPAN distributions"](http://www.slideshare.net/rjbs/distzilla-presentation))
and the first version released to CPAN in June 2008.

In the middle of 2009,
Tatsuhiko Miyagawa ([MIYAGAWA](https://metacpan.org/author/MIYAGAWA))
was frustrated trying to build something on
[HTTP::Engine](https://metacpan.org/pod/HTTP::Engine),
and finding it too much work. In September, he brainstormed
with Tokuhiro Matsuno ([TOKUHIROM](https://metacpan.org/author/TOKUHIROM))
and Kazuhiro Osawa ([YAPPO](https://metacpan.org/author/YAPPO)),
and came up with an idea based on
[WSGI](http://en.wikipedia.org/wiki/Web_Server_Gateway_Interface) and
[Rack](http://en.wikipedia.org/wiki/Rack_(web_server_interface)).
This resulted in [PSGI](https://metacpan.org/pod/distribution/PSGI/PSGI.pod)
(a gateway protocol between web servers and perl
web applications or frameworks.
[Plack](https://metacpan.org/pod/Plack) is a toolkit which implements the PSGI
stack.
All of Perl's modern web frameworks are now built on Plack.

In February 2010, MIYAGAWA was frustrated (again with the frustration!)
trying to install Perl on memory-limited box -
CPAN.pm kept running out of memory. He knocked up a
script which would find a CPAN dist, download it,
then run <tt><b>perl Makefile.PL && make install</b></tt>.
After putting it on github, it rapidly evolved, and
version 1 of
[cpanm](https://metacpan.org/pod/distribution/App-cpanminus/bin/cpanm)
was released on April 24th 2010.

In late 2010, Olaf Alders ([OALDERS](https://metacpan.org/author/OALDERS))
wanted an API to CPAN, for an iOS app he was working on.
Following a chat with [Toronto Perl Mongers](http://to.pm.org) in the pub,
he ended up creating the CPAN API,
and Mark Jubenville ([IONCACHE](https://metacpan.org/author/IONCACHE))
then knocked up a web interface on top of that.
A little while later, [metacpan.org](https://metacpan.org) was born.
This is the default CPAN search engine for many of us, these days.

On 13th June 2012, brian d foy ([BDFOY](https://metacpan.org/author/BDFOY))
gave a tutorial at YAPC::NA, part of which involved the attendees uploading
their first ever CPAN distribution. There were 150 releases uploaded to PAUSE
that day, which was the record number of uploads, until CPAN Day 2014.

In late 2012
Kenichi Ishigaki ([ISHIGAKI](https://metacpan.org/author/ISHIGAKI))
resurrected CPANTS in 2012, while preparing a talk for YAPC Asia 2012.
He ported it to Mojolicious::Lite, leading to the site you see today:
[cpants.cpanauthors.org](http://cpants.cpanauthors.org).

On 4th June 2014, Philippe Bruhat (BOOK) had the idea for CPAN Day,
and proposed (to NEILB) that it be based on the date
of the first recorded upload to CPAN.

## Colophon

This history was edited by Neil Bowers
([NEILB](https://metacpan.org/author/NEILB)) from a multitude of sources,
and email discussions with many of the people listed above.
All errors are theirs.

Key sources:

 * The [Perl Timeline](http://history.perl.org/PerlTimeline.html)
 * [PAUSE history](https://pause.perl.org/pause/query?ACTION=pause_06history)
 * An archive of the perl-packrats mailing list

## Todo list

These are things I think should be added:

* CPAN.pm
* CPAN Testers analysis
* PrePAN
* Dancer
* Metabase
* Barbie's role in CPAN Testers
* Links to lots more of the key packrats messages
* Mention that the name CPAN came from CTAN (comprehensive TeX archive network)

