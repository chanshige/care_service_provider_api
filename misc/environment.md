RubyGems Environment:
--
- RUBYGEMS VERSION: 3.3.26
- INSTALLATION DIRECTORY: /usr/local/bundle
- USER INSTALLATION DIRECTORY: /root/.local/share/gem/ruby/3.1.0
- RUBY EXECUTABLE: /usr/local/bin/ruby
- GIT EXECUTABLE:
- EXECUTABLE DIRECTORY: /usr/local/bundle/bin
- SPEC CACHE DIRECTORY: /root/.local/share/gem/specs
- SYSTEM CONFIGURATION DIRECTORY: /usr/local/etc

Initial
--
    $ docker compose run --rm --no-deps app rails new . --force --skip-git --api --minimal -J -T -B --database=postgresql
    $ docker compose build --no-cache

Start
--
    $ docker compose up
