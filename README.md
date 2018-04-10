# NHL-API-docs
Documenting the public accessible portion of the National Hockey League's API (which is contracted out to [MLBAM][#mlbam]).

The site is live at [steviehoward.com/NHL-API-docs][#site]


### Context
This is true Taco Bell Engineering<sup>*</sup>.

I had played around with the ["old" undocumented NHL API][#old] for my [Ticker][#ticker] project, and [planned to write a crawler to probe and map out the API][#reddit] for the [new [MLBAM] NHL API][#new] once I was finished Spring 2018 semester.  Fortunately for me, [@erunion][#erunion] and [@dword4][#dword4] had already done the work over that time period (January 2018).  It didn't take long at all to assemble the pieces of this documentation and publish as a [public webpage][#site].

### Build Process

1. Download [Slate][#slate]
2. Initialize a git repository in Slate folder, [setting **this** GitHub repository as `remote origin`][#addremote]
2. Download [NHL OpenAPI 3.0 specification file][#openapi]
3. Use [Widdershins][#wid] to convert OpenAPI YAML to Markdown
4. Copy-paste Markdown into Slate
5. [Deploy Slate to GitHub Pages][#deploy]

### Credits / Thanks

I added basically nothing to this project.  All credit should go to those mentioned here:

* [@dword4][#dword4] for [manual!] data discovery, documentation
* [@erunion][#erunion] for data processing, formatting, documentation
* [@lord][#lord] for Slate
* [@mermade][#mermade] for Widdershins

<!-- links -->

[#addremote]: https://help.github.com/articles/adding-a-remote/
[#deploy]: https://github.com/lord/slate/wiki/deploying-slate
[#dword4]: https://github.com/dword4
[#erunion]: https://github.com/erunion
[#lord]: https://github.com/lord
[#mermade]: https://github.com/mermade
[#mlbam]: https://github.com/MajorLeagueBaseball
[#new]: https://statsapi.web.nhl.com/api/v1/schedule
[#old]: http://live.nhle.com/GameData/RegularSeasonScoreboardv3.jsonp 
[#openapi]: https://github.com/erunion/sport-api-specifications/tree/master/nhl
[#reddit]: https://www.reddit.com/r/webdev/comments/7etuxa/is_there_a_programmatic_way_to_blindly_probe_and/
[#site]: https://steviehoward.com/NHL-API-docs
[#slate]: https://github.com/lord/slate
[#ticker]: https://github.com/stvhwrd/Ticker
[#wid]: https://github.com/mermade/widdershins

### TODO

* Use git submodules to pull in any changes to component projects
* Automate updates via CI build system


<br>
<br>

> <sup>*</sup>From [Taco Bell Programming](http://widgetsandshit.com/teddziuba/2010/10/taco-bell-programming.html)
