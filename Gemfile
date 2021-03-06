# frozen_string_literal: true

source 'https://rubygems.org'

gemspec

gem 'bump', require: false
# memory_profiler 1.0.0 requires Ruby 2.5.0 or higher.
# Please remove this branch when dropping support for Ruby 2.4.
if RUBY_VERSION >= '2.5.0'
  gem 'memory_profiler', platform: :mri
else
  gem 'memory_profiler', '<= 1.0.0', platform: :mri
end
gem 'rake', '~> 13.0'
gem 'rspec', '~> 3.7'
gem 'rubocop-performance', '~> 1.9.0'
gem 'rubocop-rspec', '~> 2.2.0'
# Workaround for cc-test-reporter with SimpleCov 0.18.
# Stop upgrading SimpleCov until the following issue will be resolved.
# https://github.com/codeclimate/test-reporter/issues/418
gem 'simplecov', '~> 0.10', '< 0.18'
gem 'stackprof', platform: :mri
gem 'test-queue'
gem 'yard', '~> 0.9'

group :test do
  gem 'webmock', require: false
end

local_ast = File.expand_path('../rubocop-ast', __dir__)
gem 'rubocop-ast', path: local_ast if Dir.exist? local_ast

local_gemfile = File.expand_path('Gemfile.local', __dir__)
eval_gemfile local_gemfile if File.exist?(local_gemfile)
