SoTech Roots Bedrock for Heroku


## Installation

1. Clone the git repo - `git clone https://github.com/sotechnology/bedrock.git`
2. Run `composer install`
3. Copy `.env.example` to `.env` and update environment variables:
  * `DB_NAME` - Database name
  * `DB_USER` - Database user
  * `DB_PASSWORD` - Database password
  * `DB_HOST` - Database host
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
4. Sage theme already added, Add new theme(s) in `web/app/themes` as you would for a normal WordPress site.
5. If using sage theme navigate to folder and run "npm install" and then "bower install" 
6. Access WP admin at `http://example.com/wp/wp-admin`

## Adding to Heroku

1. git remote rm origin
2. move to your theme and run "gulp --production" (make sure dist is not in git ignore)
3. git init
4. git add -A
5. git commit -am "Initial commit"
6. heroku create your-site-name
7. git push heroku master
8. Assign the new heroku subdomain to ste@sotechnology.co.uk
9. export your local db using migrate db using the heroku app domain, once download move to root directory of your website
10. heroku addons:create cleardb
11. /Applications/MAMP/Library/bin/mysql --host={the-host-name} --user={cleardb user} --password={cleardb password} --reconnect {cleardb name} < {your sqlfile name and location} (dont add curlys)
12. heroku config:set WP_ENV=production
13. heroku config:set WP_SITEURL=http://example.com/wp
14. heroku config:set WP_HOME=http://example.com
15. Activate w3 offload and amazon web services plugin
16. add a new user to sotech aws account
17. add user key and key secret to wp config (details in amazon web services plugin)
18. make sure to attch the full access policy to the aws bucket

## Mail service

# sendgrid
1. install the sendgrid plugin
2. add the sendgrid addon to the heroku directory
3. retrieve the sendgrid credentials and add them to the sendgrid wordpress plugin


