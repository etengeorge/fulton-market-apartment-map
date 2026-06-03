# Fulton Market Apartment Map

Static site for sharing the apartment commute map as a public link.

## Publish With GitHub Pages

From this folder:

```sh
gh auth login --hostname github.com --git-protocol https --web
git init
git branch -M main
git add index.html README.md
git commit -m "Publish apartment map"
gh repo create fulton-market-apartment-map --public --source=. --remote=origin --push
OWNER=$(gh api user -q .login)
gh api --method POST "repos/$OWNER/fulton-market-apartment-map/pages" -f "source[branch]=main" -f "source[path]=/"
echo "https://$OWNER.github.io/fulton-market-apartment-map/"
```

GitHub Pages can take a minute or two to go live after the API call succeeds.
