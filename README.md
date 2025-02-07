# wporg-mu-plugins

Over time, this is intended to become the canonical source repository for all `mu-plugins` on the WordPress.org network. At the moment, it only includes a few.

## Usage

1. Add entries to the `repositories` and `require-dev` sections of `composer.json`. See `wporg-news-2021` as an example.
1. Run `composer update` to install it
1. `require_once` the files that you want. e.g.,
	```php
	require_once WPMU_PLUGIN_DIR . '/wporg-mu-plugins/mu-plugins/blocks/global-header-footer/blocks.php';
	```
1. See individual plugin readmes for specific instructions


## Development

* `npm run start` during development
* `npm run build` before commit/sync/deploy


## Sync/Deploy

The files here are commited to `dotorg.svn` so they can be deployed. The aren't synced to `meta.svn`, since they're already open.

The other `mu-plugins` in `meta.svn` are not synced here. Over time, they can be removed from `meta.svn` and added here.

To sync these to `dotorg.svn`, run `composer exec sync-svn` (WIP) and follow the instructions. Once they're committed, you can deploy like normal.
