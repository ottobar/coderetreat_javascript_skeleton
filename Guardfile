spec_location = "spec/%sSpec"

guard 'jasmine-headless-webkit' do
  watch(%r{^lib/(.*)\.(js|coffee)$}) { |m| newest_js_file(spec_location % m[1]) }
  watch(%r{^spec/(.*)Spec\..*}) { |m| newest_js_file(spec_location % m[1]) }
end

