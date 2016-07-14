# z-push
Mirror of z-push Git repository used in EGroupware 16.1+

List of branches:
* master (used with EGroupware master / development version)
* 16.1 (used with EGroupware 16.1 release/branch)
* develop (z-push developement version)
* release/2.3 (z-push 2.3 release branch)

Updating to new 2.3 release in clone with with two remote branches:
<pre>
RalfsMac:z-push ralf$ git remote -v
egroupware	git@github.com:EGroupware/z-push.git (fetch)
egroupware	git@github.com:EGroupware/z-push.git (push)
origin	https://RalfBecker@stash.z-hub.io/scm/zp/z-push.git (fetch)
origin	https://RalfBecker@stash.z-hub.io/scm/zp/z-push.git (push)
</pre>
Run the following git commands:
<pre>
git checkout release/2.3
git pull
git push egroupware release/2.3
git checkout -b egroupware/master egroupware/master # tracking egroupware/master local as egroupware/master
git merge egroupware/master release/2.3
# fix evtl. merge conflicts
git commit -m '* eSync: merge z-push 2.3.0-beta3 https://jira.z-hub.io/projects/ZP/versions/10414'
git push egroupware HEAD:master
</pre>
Merge to our release branch from master:
<pre>
cd activesync/vendor/vendor/z-push
git checkout 16.1
git pull
git merge 16.1 master
git push
</pre>
