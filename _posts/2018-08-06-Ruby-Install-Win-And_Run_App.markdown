### When you are at Win machine

#### ERR:
```
C:\Users\Siv\Desktop\2314\newtest>bundle install
C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/dependency.rb:308:in `to_specs': Could not find 'bundler' (>= 0) among 13 total gem(s) (Gem::MissingSpecError)
Checked in 'GEM_PATH=C:/Users/Siv/.gem/ruby/2.4.0;C:/Ruby24-x64/lib/ruby/gems/2.4.0', execute `gem env` for more information
        from C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/dependency.rb:320:in `to_spec'
        from C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/core_ext/kernel_gem.rb:65:in `gem'
```

#### To Resolve just run

```
  gem install bundler
```

#### ERR:
```
C:\Users\Siv\Desktop\2314\newtest>rails s
C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/dependency.rb:308:in `to_specs': Could not find 'railties' (>= 0) among 14 total gem(s) (Gem::MissingSpecError)
Checked in 'GEM_PATH=C:/Users/Siv/.gem/ruby/2.4.0;C:/Ruby24-x64/lib/ruby/gems/2.4.0', execute `gem env` for more information
        from C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/dependency.rb:320:in `to_spec'
        from C:/Ruby24-x64/lib/ruby/2.4.0/rubygems/core_ext/kernel_gem.rb:65:in `gem'
        from C:/Ruby200/bin/rails:22:in `<main>'
```
#### Just run following commands

```
bundle install
```
