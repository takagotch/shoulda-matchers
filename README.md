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







```

```
```

```
```
