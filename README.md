# テクノロジー（藤原）12/6授業

## Bashの実行ログ

```
seno2:~/workspace $ cd ~/workspace
seno2:~/workspace $ git clone　git@github.com:seno2/lecture-1206.git
git: 'clone　git@github.com:seno2/lecture-1206.git' is not a git command. See 'git --help'.
seno2:~/workspace $ git clone　git@github.com:seno2/lecture-1206.git
git: 'clone　git@github.com:seno2/lecture-1206.git' is not a git command. See 'git --help'.
seno2:~/workspace $ git clone git@github.com:seno2/lecture-1206.git
Cloning into 'lecture-1206'...
Warning: Permanently added 'github.com,192.30.253.112' (RSA) to the list of known hosts.
remote: Counting objects: 95, done.
remote: Compressing objects: 100% (79/79), done.
remote: Total 95 (delta 2), reused 95 (delta 2), pack-reused 0
Receiving objects: 100% (95/95), 38.69 KiB | 218.00 KiB/s, done.
Resolving deltas: 100% (2/2), done.
seno2:~/workspace $ cd lecture-1206/asagao
seno2:~/workspace/lecture-1206/asagao (master) $ bundle install
The latest bundler is 1.16.0, but you are currently running 1.15.4.
To update, run `gem install bundler`
The git source `git://github.com/flori/json.git` uses the `git` protocol, which transmits data without encryption. Disable this warning with `bundle config git.allow_insecure true`, or switch to the `https` protocol to keep your data secure.
Warning: the running version of Bundler (1.15.4) is older than the version that created the lockfile (1.16.0). We suggest you upgrade to the latest version of Bundler by running `gem install bundler`.
Using rake 12.2.1
Using concurrent-ruby 1.0.5
Using minitest 5.10.3
Using thread_safe 0.3.6
Using builder 3.2.3
Using erubis 2.7.0
Using mini_portile2 2.3.0
Using crass 1.0.2
Using rack 1.6.8
Using mini_mime 0.1.4
Using arel 6.0.4
Using debug_inspector 0.0.3
Using bundler 1.15.4
Using byebug 9.1.0
Using coffee-script-source 1.8.0
Using execjs 2.7.0
Using thor 0.20.0
Using ffi 1.9.18
Using multi_json 1.12.2
Using json 1.8.6 from git://github.com/flori/json.git (at v1.8@7f4cfd8)
Using rb-fsevent 0.10.2
Using rdoc 4.3.0
Using tilt 2.0.8
Using sqlite3 1.3.13
Using turbolinks-source 5.0.3
Using i18n 0.9.1
Using tzinfo 1.2.4
Using nokogiri 1.8.1
Using rack-test 0.6.3
Using sprockets 3.7.1
Using mail 2.7.0
Using binding_of_caller 0.7.3
Using coffee-script 2.4.1
Using uglifier 3.2.0
Using rb-inotify 0.9.10
Using sdoc 0.4.2
Using turbolinks 5.0.1
Using activesupport 4.2.10
Using loofah 2.1.1
Using sass-listen 4.0.0
Using rails-deprecated_sanitizer 1.0.3
Using globalid 0.4.1
Using activemodel 4.2.10
Using jbuilder 2.7.0
Using spring 2.0.2
Using rails-html-sanitizer 1.0.3
Using sass 3.5.3
Using rails-dom-testing 1.0.8
Using activejob 4.2.10
Using activerecord 4.2.10
Using actionview 4.2.10
Using actionpack 4.2.10
Using actionmailer 4.2.10
Using railties 4.2.10
Using sprockets-rails 3.2.1
Using coffee-rails 4.1.1
Using jquery-rails 4.3.1
Using rails 4.2.10
Using sass-rails 5.0.6
Using web-console 2.3.0
Bundle complete! 15 Gemfile dependencies, 60 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
seno2:~/workspace/lecture-1206/asagao (master) $  bin/rake db:create
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rails g model member
      invoke  active_record
      create    db/migrate/20171206005902_create_members.rb
      create    app/models/member.rb
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rake db:migrate
== 20171206005902 CreateMembers: migrating ====================================
-- create_table(:members)
   -> 0.0022s
== 20171206005902 CreateMembers: migrated (0.0023s) ===========================

seno2:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > Member.count
   (0.1ms)  SELECT COUNT(*) FROM "members"
 => 0 
2.4.0 :002 > member = Member.new
 => #<Member id: nil, number: nil, name: nil, full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: nil, updated_at: nil> 
2.4.0 :003 > member.number = 1
 => 1 
2.4.0 :004 > member.name = "Taro"
 => "Taro" 
2.4.0 :005 > member.save
   (0.2ms)  begin transaction
  SQL (0.8ms)  INSERT INTO "members" ("number", "name", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["number", 1], ["name", "Taro"], ["created_at", "2017-12-06 01:14:04.877274"], ["updated_at", "2017-12-06 01:14:04.877274"]]
   (9.1ms)  commit transaction
 => true 
2.4.0 :006 > Member.first
  Member Load (0.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:14:04", updated_at: "2017-12-06 01:14:04"> 
2.4.0 :007 > pp Member.first
  Member Load (1.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
#<Member:0x000000039c2748
 id: 1,
 number: 1,
 name: "Taro",
 full_name: nil,
 email: nil,
 birthday: nil,
 gender: 0,
 administrator: false,
 created_at: Wed, 06 Dec 2017 10:14:04 JST +09:00,
 updated_at: Wed, 06 Dec 2017 10:14:04 JST +09:00>
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:14:04", updated_at: "2017-12-06 01:14:04"> 
2.4.0 :008 > member = Member.first
  Member Load (0.3ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 1, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:14:04", updated_at: "2017-12-06 01:14:04"> 
2.4.0 :009 > member.number = 41
 => 41 
2.4.0 :010 > member.save
   (1.8ms)  begin transaction
  SQL (0.4ms)  UPDATE "members" SET "number" = ?, "updated_at" = ? WHERE "members"."id" = ?  [["number", 41], ["updated_at", "2017-12-06 01:20:10.017568"], ["id", 1]]
   (9.9ms)  commit transaction
 => true 
2.4.0 :011 > Member.first
  Member Load (0.4ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
 => #<Member id: 1, number: 41, name: "Taro", full_name: nil, email: nil, birthday: nil, gender: 0, administrator: false, created_at: "2017-12-06 01:14:04", updated_at: "2017-12-06 01:20:10"> 
2.4.0 :012 > 
seno2:~/workspace/lecture-1206/asagao (master) $ mkdir -p db/seeds/development
seno2:~/workspace/lecture-1206/asagao (master) $ touch db/seeds/development/members.rb
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rake db:reset
-- create_table("members", {:force=>:cascade})
   -> 0.0139s
-- initialize_schema_migrations_table()
   -> 0.0676s
-- create_table("members", {:force=>:cascade})
   -> 0.0114s
-- initialize_schema_migrations_table()
   -> 0.0160s
Creating members...
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rake db:seed
Creating members...
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > pp Member.first
  Member Load (0.2ms)  SELECT  "members".* FROM "members"  ORDER BY "members"."id" ASC LIMIT 1
#<Member:0x000000036b14f0
 id: 1,
 number: 10,
 name: "Taro",
 full_name: "佐藤 太郎",
 email: "Taro@example.com",
 birthday: Tue, 01 Dec 1981,
 gender: 0,
 administrator: true,
 created_at: Wed, 06 Dec 2017 10:25:25 JST +09:00,
 updated_at: Wed, 06 Dec 2017 10:25:25 JST +09:00>
 => #<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25"> 
2.4.0 :002 > 
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rails db
SQLite version 3.8.2 2013-12-06 14:53:30
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite> .tables
members            schema_migrations
sqlite> .schema members
CREATE TABLE "members" ("id" INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, "number" integer NOT NULL, "name" varchar NOT NULL, "full_name" varchar, "email" varchar, "birthday" date, "gender" integer DEFAULT 0 NOT NULL, "administrator" boolean DEFAULT 'f' NOT NULL, "created_at" datetime NOT NULL, "updated_at" datetime NOT NULL);
sqlite> SELECT * from members;
1|10|Taro|佐藤 太郎|Taro@example.com|1981-12-01|0|t|2017-12-06 01:25:25.575638|2017-12-06 01:25:25.575638
2|11|Jiro|鈴木 次郎|Jiro@example.com|1981-12-01|0|f|2017-12-06 01:25:25.588610|2017-12-06 01:25:25.588610
3|12|Hana|高橋 花子|Hana@example.com|1981-12-01|1|f|2017-12-06 01:25:25.598711|2017-12-06 01:25:25.598711
4|13|John|田中 太郎|John@example.com|1981-12-01|0|f|2017-12-06 01:25:25.609807|2017-12-06 01:25:25.609807
5|14|Mike|佐藤 次郎|Mike@example.com|1981-12-01|0|f|2017-12-06 01:25:25.623840|2017-12-06 01:25:25.623840
6|15|Sophy|鈴木 花子|Sophy@example.com|1981-12-01|1|f|2017-12-06 01:25:25.636792|2017-12-06 01:25:25.636792
7|16|Bill|高橋 太郎|Bill@example.com|1981-12-01|0|f|2017-12-06 01:25:25.649787|2017-12-06 01:25:25.649787
8|17|Alex|田中 次郎|Alex@example.com|1981-12-01|0|f|2017-12-06 01:25:25.663583|2017-12-06 01:25:25.663583
9|18|Mary|佐藤 花子|Mary@example.com|1981-12-01|1|f|2017-12-06 01:25:25.680073|2017-12-06 01:25:25.680073
10|19|Tom|鈴木 太郎|Tom@example.com|1981-12-01|0|f|2017-12-06 01:25:25.699018|2017-12-06 01:25:25.699018
11|10|Taro|佐藤 太郎|Taro@example.com|1981-12-01|0|t|2017-12-06 01:25:37.504219|2017-12-06 01:25:37.504219
12|11|Jiro|鈴木 次郎|Jiro@example.com|1981-12-01|0|f|2017-12-06 01:25:37.535814|2017-12-06 01:25:37.535814
13|12|Hana|高橋 花子|Hana@example.com|1981-12-01|1|f|2017-12-06 01:25:37.549791|2017-12-06 01:25:37.549791
14|13|John|田中 太郎|John@example.com|1981-12-01|0|f|2017-12-06 01:25:37.574626|2017-12-06 01:25:37.574626
15|14|Mike|佐藤 次郎|Mike@example.com|1981-12-01|0|f|2017-12-06 01:25:37.594494|2017-12-06 01:25:37.594494
16|15|Sophy|鈴木 花子|Sophy@example.com|1981-12-01|1|f|2017-12-06 01:25:37.611944|2017-12-06 01:25:37.611944
17|16|Bill|高橋 太郎|Bill@example.com|1981-12-01|0|f|2017-12-06 01:25:37.630838|2017-12-06 01:25:37.630838
18|17|Alex|田中 次郎|Alex@example.com|1981-12-01|0|f|2017-12-06 01:25:37.642459|2017-12-06 01:25:37.642459
19|18|Mary|佐藤 花子|Mary@example.com|1981-12-01|1|f|2017-12-06 01:25:37.656027|2017-12-06 01:25:37.656027
20|19|Tom|鈴木 太郎|Tom@example.com|1981-12-01|0|f|2017-12-06 01:25:37.688916|2017-12-06 01:25:37.688916
sqlite> .quit 
seno2:~/workspace/lecture-1206/asagao (master) $ bin/rails c
Loading development environment (Rails 4.2.10)
2.4.0 :001 > Members.ids
NameError: uninitialized constant Members
        from (irb):1
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :002 >    (0.2ms)  SELECT "members"."id" FROM "members"
SyntaxError: (irb):2: syntax error, unexpected tIDENTIFIER, expecting ')'
   (0.2ms)  SELECT "members"."id" FROM 
         ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :003 > member = Members.find(3)
NameError: uninitialized constant Members
        from (irb):3
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :004 > member.email
NoMethodError: undefined method `email' for nil:NilClass
        from (irb):4
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :005 > Members.ids (0.2ms)  SELECT "members"."id" FROM "members"
SyntaxError: (irb):5: syntax error, unexpected tIDENTIFIER, expecting ')'
Members.ids (0.2ms)  SELECT "members"."id" FROM 
                  ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :006 >  member = Member.find_by(name: "Taro")
  Member Load (0.2ms)  SELECT  "members".* FROM "members" WHERE "members"."name" = ? LIMIT 1  [["name", "Taro"]]
 => #<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25"> 
2.4.0 :007 > member = Member.find_by(gender: 0, administrator: false)
  Member Load (0.3ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 0], ["administrator", "f"]]
 => #<Member id: 2, number: 11, name: "Jiro", full_name: "鈴木 次郎", email: "Jiro@example.com", birthday: "1981-12-01", gender: 0, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25"> 
2.4.0 :008 > member = Member.find_by(gender: 1, administrator: true)
  Member Load (0.3ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 1], ["administrator", "t"]]
 => nil 
2.4.0 :009 > member = Member.where(name: "Taro")
  Member Load (0.4ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :010 > puts member.to_sql
SELECT "members".* FROM "members" WHERE "members"."name" = 'Taro'
 => nil 
2.4.0 :011 > members = Member.where(name: "Taro")
  Member Load (0.2ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :012 > members = member.where("number < 20")
  Member Load (0.3ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ? AND (number < 20)  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :013 > members = Member.where(name: "Taro").where("number < 20")
  Member Load (0.3ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ? AND (number < 20)  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :014 > ^C
2.4.0 :014 > members = Member.where(gender: 1).order("number")
  Member Load (0.4ms)  SELECT "members".* FROM "members" WHERE "members"."gender" = ?  ORDER BY number  [["gender", 1]]
 => #<ActiveRecord::Relation [#<Member id: 3, number: 12, name: "Hana", full_name: "高橋 花子", email: "Hana@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 13, number: 12, name: "Hana", full_name: "高橋 花子", email: "Hana@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">, #<Member id: 6, number: 15, name: "Sophy", full_name: "鈴木 花子", email: "Sophy@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 16, number: 15, name: "Sophy", full_name: "鈴木 花子", email: "Sophy@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">, #<Member id: 9, number: 18, name: "Mary", full_name: "佐藤 花子", email: "Mary@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 19, number: 18, name: "Mary", full_name: "佐藤 花子", email: "Mary@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :015 > 

2.4.0 :004 > Member.ids
   (0.3ms)  SELECT "members"."id" FROM "members"
 => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20] 
2.4.0 :005 > (0.2ms)  SELECT "members"."id" FROM "members"
SyntaxError: (irb):5: syntax error, unexpected tIDENTIFIER, expecting ')'
(0.2ms)  SELECT "members"."id" FROM 
      ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :006 > member = Members.find(3)
NameError: uninitialized constant Members
        from (irb):6
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :007 > member.email
NoMethodError: undefined method `email' for nil:NilClass
        from (irb):7
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :008 >  Member.ids
   (0.4ms)  SELECT "members"."id" FROM "members"
 => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20] 
2.4.0 :009 > member = Member.find_by(name: "Taro")
  Member Load (0.5ms)  SELECT  "members".* FROM "members" WHERE "members"."name" = ? LIMIT 1  [["name", "Taro"]]
 => #<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25"> 
2.4.0 :010 >  member = Member.find_by(gender: 0, administrator: false)
  Member Load (0.4ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 0], ["administrator", "f"]]
 => #<Member id: 2, number: 11, name: "Jiro", full_name: "鈴木 次郎", email: "Jiro@example.com", birthday: "1981-12-01", gender: 0, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25"> 
2.4.0 :011 > member = Member.find_by(gender: 1, administrator: true)
  Member Load (0.2ms)  SELECT  "members".* FROM "members" WHERE "members"."gender" = ? AND "members"."administrator" = ? LIMIT 1  [["gender", 1], ["administrator", "t"]]
 => nil 
2.4.0 :012 > member = Member.where(name: "Taro")
  Member Load (0.3ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :013 > puts member.to_sq
NoMethodError: undefined method `to_sq' for #<Member::ActiveRecord_Relation:0x00000003a11118>
Did you mean?  to_sql
               to_s
               to_a
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/activerecord-4.2.10/lib/active_record/relation/delegation.rb:136:in `method_missing'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/activerecord-4.2.10/lib/active_record/relation/delegation.rb:99:in `method_missing'
        from (irb):13
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :014 > SELECT "members".* FROM "members" WHERE "members"."name" = 'Taro'
SyntaxError: (irb):14: syntax error, unexpected tCONSTANT, expecting end-of-input
embers".* FROM "members" WHERE "members"."name" = 'Taro'
                              ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :015 > リレーションオブジェクト (p.197)
SyntaxError: (irb):15: no .<digit> floating literal anymore; put 0 before dot
ョンオブジェクト (p.197)
                              ^
(irb):15: syntax error, unexpected tINTEGER, expecting '('
ンオブジェクト (p.197)
                              ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :016 > クエリーメソッドはリレーションオブジェクトを返す
NameError: undefined local variable or method `クエリーメソッドはリレーションオブジェクトを返す' for main:Object
        from (irb):16
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :017 > リレーションオブジェクトの役割
NameError: undefined local variable or method `リレーションオブジェクトの役割' for main:Object
        from (irb):17
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :018 > 検索条件を保持する
NameError: undefined local variable or method `検索条件を保持する' for main:Object
        from (irb):18
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :019 > 検索実行後にモデルの配列を返す
NameError: undefined local variable or method `検索実行後にモデルの配列を返す' for main:Object
        from (irb):19
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :020 > 検索が実行されるタイミング (p.198)
SyntaxError: (irb):20: no .<digit> floating literal anymore; put 0 before dot
されるタイミング (p.198)
                              ^
(irb):20: syntax error, unexpected tINTEGER, expecting '('
れるタイミング (p.198)
                              ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :021 > whereメソッドを実行しただけでは、検索は実行されない
NameError: undefined local variable or method `whereメソッドを実行しただけでは、検索は実行されない' for main:Object
        from (irb):21
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :022 > 検索結果を保持しているだけ
NameError: undefined local variable or method `検索結果を保持しているだけ' for main:Object
        from (irb):22
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :023 > リレーションオブジェクトを配列として呼びだした瞬間に、SQL文が実行される
NameError: undefined local variable or method `リレーションオブジェクトを配列として呼びだした瞬間に、SQL文が実行される' for main:Object
        from (irb):23
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :024 > each, map, lengthなどのメソッドを呼びだしたとき
SyntaxError: (irb):24: syntax error, unexpected '\n', expecting '='
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :025 > この「実際に検索を実行してデータを取り出すのは、データが必要となったとき」という仕組みをLazy Loadingという
NameError: uninitialized constant Loadingという
        from (irb):25
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :026 > members = Member.where(name: "Taro")
  Member Load (0.3ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ?  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :027 > members = member.where("number < 20")
  Member Load (0.3ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ? AND (number < 20)  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :028 > members = Member.where(name: "Taro").where("number < 20")
  Member Load (0.2ms)  SELECT "members".* FROM "members" WHERE "members"."name" = ? AND (number < 20)  [["name", "Taro"]]
 => #<ActiveRecord::Relation [#<Member id: 1, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 11, number: 10, name: "Taro", full_name: "佐藤 太郎", email: "Taro@example.com", birthday: "1981-12-01", gender: 0, administrator: true, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :029 > orderメソッド (p.200)
SyntaxError: (irb):29: no .<digit> floating literal anymore; put 0 before dot
orderメソッド (p.200)
                     ^
(irb):29: syntax error, unexpected tINTEGER, expecting '('
orderメソッド (p.200)
                        ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :030 > 検索結果のソート順を指定するには、クエリメソッドのorderを用いる
NameError: undefined local variable or method `検索結果のソート順を指定するには、クエリメソッドのorderを用いる' for main:Object
        from (irb):30
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :031 > 例: 性別(gender)が1(女性)の館員を、背番号(number)の昇順で取り出す
SyntaxError: (irb):31: syntax error, unexpected ':', expecting end-of-input
例: 性別(gender)が1(女性)の
    ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :032 >  > members = Member.where(gender: 1).order("number")
SyntaxError: (irb):32: syntax error, unexpected '>'
 > members = Member.where(gender
  ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :033 > 降順にしたい場合
NameError: undefined local variable or method `降順にしたい場合' for main:Object
        from (irb):33
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :034 > .order(number: :desc)
SyntaxError: (irb):34: syntax error, unexpected '.'
.order(number: :desc)
 ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :035 > 引数がハッシュ＋シンボルになっているので注意
NameError: undefined local variable or method `引数がハッシュ＋シンボルになっているので注意' for main:Object
        from (irb):35
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :036 > Railsコンソールを終了
NameError: uninitialized constant Railsコンソールを終了
        from (irb):36
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :037 > Ctrl-D(command-D)で終了
SyntaxError: (irb):37: syntax error, unexpected tIDENTIFIER, expecting end-of-input
Ctrl-D(command-D)で終了
                          ^
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:110:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/console.rb:9:in `start'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:68:in `console'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
        from /usr/local/rvm/gems/ruby-2.4.0@global/gems/railties-4.2.10/lib/rails/commands.rb:17:in `<top (required)>'
        from bin/rails:4:in `require'
        from bin/rails:4:in `<main>'
2.4.0 :038 > members = Member.where(gender: 1).order("number")
  Member Load (0.4ms)  SELECT "members".* FROM "members" WHERE "members"."gender" = ?  ORDER BY number  [["gender", 1]]
 => #<ActiveRecord::Relation [#<Member id: 3, number: 12, name: "Hana", full_name: "高橋 花子", email: "Hana@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 13, number: 12, name: "Hana", full_name: "高橋 花子", email: "Hana@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">, #<Member id: 6, number: 15, name: "Sophy", full_name: "鈴木 花子", email: "Sophy@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 16, number: 15, name: "Sophy", full_name: "鈴木 花子", email: "Sophy@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">, #<Member id: 9, number: 18, name: "Mary", full_name: "佐藤 花子", email: "Mary@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:25", updated_at: "2017-12-06 01:25:25">, #<Member id: 19, number: 18, name: "Mary", full_name: "佐藤 花子", email: "Mary@example.com", birthday: "1981-12-01", gender: 1, administrator: false, created_at: "2017-12-06 01:25:37", updated_at: "2017-12-06 01:25:37">]> 
2.4.0 :039 > 
```