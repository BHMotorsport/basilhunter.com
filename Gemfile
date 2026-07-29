source "https://rubygems.org"

# NOTE: the `github-pages` gem (Jekyll 3.9) no longer runs on modern Ruby (3.2+
# removed taint checking, which its pinned Liquid 4.0.3 depends on). Jekyll 4.x
# is used for local preview; GitHub Pages builds the deployed site with its own
# environment, so this only affects `bundle exec jekyll serve` locally.
gem "jekyll", "~> 4.3"
gem "webrick" # required for local `jekyll serve` on Ruby 3+

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
end

# Stdlib gems removed from Ruby's default set (3.4+); Jekyll still needs them locally
gem "csv"
gem "logger"
gem "base64"
gem "bigdecimal"
