Cowosedlice.cz
====================

# How to

## Get Jekyll runnig locally (Ubuntu 16.04)
```
sudo apt install ruby-dev gcc make libghc-zlib-dev
gem install rubygems-update
gem install jekyll bundler
```
Or read https://jekyllrb.com/ if you have more questions.

## Stay up to date
`bundle install` - Install requirements. Note that these can be changed by pulling new code.

## Develop locally
```
bundle exec jekyll serve
```

## Develop locally
```
bundle exec jekyll build
```

## Hosting

Cloudflare Worker `cowosedlice-cz` (`wrangler.jsonc`, workflow `.github/workflows/deploy.yml`):
every push to `main` deploys https://cowosedlice.cz, and every pull request gets its own
preview, linked in a PR comment with a QR code, Lighthouse scores and a visual comparison
with production. `www.cowosedlice.cz` 301s to `cowosedlice.cz` (a Redirect Rule on the
Cloudflare zone). Same setup as https://cfsite.klaska.net. Details: `CLAUDE.md`, section
"Deployment".
