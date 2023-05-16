# site-homelab

https://homelab.ricebucket.dev

## initializing

```zsh
konri@macmini-m2 site-homelab % git init
konri@macmini-m2 site-homelab % git submodule add https://github.com/alex-shpak/hugo-book themes/hugo-book
konri@macmini-m2 site-homelab % cp themes/hugo-book/exampleSite/config.toml .
konri@macmini-m2 site-homelab % git add *
konri@macmini-m2 site-homelab % git commit -m 'initializing'
konri@macmini-m2 site-homelab % git branch -M main
konri@macmini-m2 site-homelab % git push origin main
```
