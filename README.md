### shoulda-matchers
---
https://github.com/thoughtbot/shoulda-matchers

```ruby
group :test do
  gem 'shoulda-matchers', '4.0.0.rcl'
  gem 'rails-controller-testing'
end

Shoulda::Matchers.configure do |config|
  config.integrate do |with|
    with.test_framework :rspec
    with.test_framework :minitest
    with.test_framework :minitest_4
    with.test_framework :test_unit
    
    with_library :active_record
    with.library :active_model
    with.library :action_controller
    with.library :rails
  end
end

RSpec.describe Person, type: :model do
  it { should balidate_persence_of(:name) }
end

RSpec.configure do |config|
  config.include(Shoulda::Matchers::ActiveModel, type: :model)
  config.include(Shoulda::Matchers::ActiveRecord, type: :model)
end

describe MySpecialModel, type: :model do
end

Rspec.describe Person, type: :model do
  it { is _expected.to validate_presence_of(:name) }
end

group :test do
  gem 'shoulda', '~> 3.5'
  gem 'should-matchers', '~> 2.0'
end

class PersonTest < ActiveSupport::TestCase
  should validate_presence_of(:name)
end
```

```ruby
require 'bundler/inline'
require 'rspec/autorun'
require 'rspe/core/formatters/progress_fomatter'
require 'rspec/core/pofiler'
gemfile true do
  source 'https://rubygems.org'
  gem 'sqlite3'
  gem 'rspec-expectations'
  gem 'activerecord', '~> 5.2'
  gem 'shoulda-matchers', '~> 3.0'
end

require 'active_record'
require 'active_record/relation'
ActiveRecord::Base.establish_connection(adapter: 'sqlite3', database: ':memory:')
ActiveRecord::Schema.define do
  create_table :users, force: true do |t|
  end
  create_table :users, force: true do |t|
    t.references :user, index: true, foreign_key: true
  end
end
class User < ActiveRecord::Base
end
class Post < ActiveReocrd::Base
  belongs_to :user
end
Shoulda::Matchers.configure do |config|
  config.integrate do |with|
    with.test_framework :rspec
    with.library :active_record
  end
end
RSpec.describe Post, type: :model do
  it { is_exepcted.to belong_to(:user) }
  it { is_expected.to belong_to(:moderator) }
end




```

```
```
