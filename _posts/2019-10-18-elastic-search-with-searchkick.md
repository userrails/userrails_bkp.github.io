---
layout: post
title:  "Elastic Search with Searchkick"
date:   2019-10-18 08:01:18 +0545
categories: tutorials
---

# What is Searchkick?

Searchkick is a smart and intillegent search engine Rubygems that creates quicker search results based on user search activity.

Before using Searchkick make sure Elasticsearch is installed on your system.

# Steps to use Searchkick

* Create a Rails application

```
rails new institutions -d postgres
```

* Generate the scaffold for Student

```
rails g scaffold Student name:string roll:integer grade:string fee:decimal
```

* Run rake db:create rake db:migrate

* Configure the routes

```
root "students#index"
resources :students
```

* Add following gem into Gemfile

```
gem 'searchkick'
```

Here is the Guide for Elasticsearch 6 or 7.

* In each models you need to add keyword `searchkick` to make searchkick work as shown below

```
class Student < ApplicationRecord
	searchkick
end
```

* Now add data to search index by using following code and you need to run this command everytime as model changes

```
Student.reindex
```

