# ghcr.io pulls

## JSON Endpoint for GHCR Badges

Makes the pull count badge possible for these ghcr.io packages:

[![violinist-dev/update-check-runner/update-check-runner](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Feiriksm%2Fghcr-pulls%2Fmaster%2Findex.json&query=%24%5B%3F(%40.owner%3D%3D%22violinist-dev%22%20%26%26%20%40.repo%3D%3D%22update-check-runner%22%20%26%26%20%40.image%3D%3D%22update-check-runner%22)%5D.pulls&label=update-check-runner)](https://github.com/violinist-dev/update-check-runner/pkgs/container/update-check-runner) [![violinist-dev/php-base/php-base](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Feiriksm%2Fghcr-pulls%2Fmaster%2Findex.json&query=%24%5B%3F(%40.owner%3D%3D%22violinist-dev%22%20%26%26%20%40.repo%3D%3D%22php-base%22%20%26%26%20%40.image%3D%3D%22php-base%22)%5D.pulls&label=php-base)](https://github.com/violinist-dev/php-base/pkgs/container/php-base)

If we don't yet follow an image, you can either:

* open an issue or pull request to add it to the master `pkg.txt` and/or
* make a fork to start your own.

### Custom Badges

To make a badge, you can modify one of the badges above or generate one with something like [shields.io](https://shields.io/badges/dynamic-json-badge) and these parameters:

#### URL

```markdown
https://raw.githubusercontent.com/ipitio/ghcr-pulls/master/index.json
```

#### JSONPath

You can show either a pretty value like 12K or the raw number like 12345.

##### Pretty Count

```markdown
$[?(@.owner=="<USER>" && @.repo=="<REPO>" && @.image=="<IMAGE>")].pulls
```

##### Raw Count

```markdown
$[?(@.owner=="<USER>" && @.repo=="<REPO>" && @.image=="<IMAGE>")].raw_pulls
```

### Further Study

GHCR itself doesn't provide an API endpoint for the pull count, so Github Packages is scraped twice daily for every image in `pkg.txt`. In addition to the latest stats, the index also contains a history of the raw pull counts for each image, starting on 2024-06-10, should you find that useful or interesting. Should the pulls for each tag be kept individually as well?
