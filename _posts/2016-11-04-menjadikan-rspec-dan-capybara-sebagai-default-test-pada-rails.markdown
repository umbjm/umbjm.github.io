---
layout: post
title: "Menjadikan RSpec dan Capybara Sebagai Default Test Pada Rails"
permalink: "menjadikan-rspec-dan-capybara-sebagai-default-test-pada-rails"
date: 2016-11-04 15:08
categories: rails
---

Sebagaimana yang kita ketahui bahwa Rails menggunakan Test::Unit sebagai default test nya, pada tulisan kali ini saya akan share bagaimana menjadikan RSpec dan Capybara sebagai default test pada rails, berikut langkah-langkahnya: 

Pertama buat proyek baru rails dengan meng__skip__ test dengan menambahkan `-T`
{% highlight bash %}
rails new railsspec -T
{% endhighlight %}
Kedua, pada file `Gemfile` tambahkan gem `rspec-rails` pada group development, dan test, sedangkan `capybara` pada group test
{% highlight  ruby %}
group :development, :test do
  gem 'rspec-rails'
end
group :test do
  gem 'capybara'
end
{% endhighlight %}
lanjutkan dengan `bundle install`

Ketiga, inisialisasi `/spec` direktori dengan menggunakan
{% highlight bash %}
rails g rspec:install
{% endhighlight %}
maka akan ditambahkan file berikut
{% highlight bash %}
Running via Spring preloader in process 25274
      create  .rspec
      create  spec
      create  spec/spec_helper.rb
      create  spec/rails_helper.rb
{% endhighlight %}
Keempat, RSpec sudah berhasil di install, untuk menjalankan bisa menggunakan `rspec` atau `rake spec`

![tes](/assets/img/posts/rspec-test.png)



