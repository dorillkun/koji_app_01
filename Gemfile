gem 'fog-aws', group: :production
gem 'carrierwave', '~> 1.0'


# config/initializers/carrierwave.rb
require 'carrierwave/storage/abstract'
require 'carrierwave/storage/file'
require 'carrierwave/storage/fog'

CarrierWave.configure do |config|
  if Rails.env.production?
    config.storage :fog
    config.fog_provider = 'fog/aws'
    config.fog_credentials = {
      provider:              'AWS',
      [...]
    }
    [...]
  else
    config.storage :file
    config.enable_processing = false if Rails.env.test?
  end
end