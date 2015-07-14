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
5. Access WP admin at `http://example.com/wp/wp-admin`

## Adding to Heroku

1. Remove Git Origin "git remote rm origin"
2. git init
3. git add -A
4. git commit -am "Initial commit"
5. heroku create <your site name>
6. git push heroku master
7. Assign the new heroku subdomain to ste@sotechnology.co.uk
8. export your local db using migrate db using the heroku app domain
9. heroku addons:create cleardb
10. run in mysql terminal -> --host=<cleardb host> --user=<cleardb user> --password=<cleardb password> --reconnect <cleardb name> < <your sqlfile name and location>
