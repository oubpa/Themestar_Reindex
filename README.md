# Reindex – Smart Index Management, Scheduling & Monitoring for Magento 2

Smart index management for Magento 2 — live admin dashboard with one-click rebuilds, smart advisor recommendations, named automatic schedules, full run history with durations, cron health monitoring and large-catalog safety guards.

- Module: `Themestar_Reindex` (`themestar/magento2-reindex`)
- Version: 1.0.0
- Compatible: Magento 2.4.5+ / PHP 8.1+ / MySQL 5.7+ / MariaDB 10.3+

## Features

- **Live Admin Dashboard** (`Reindex > Dashboard`)
  - Health counts: total, outdated, processing, healthy + warning banners
  - Per-index status, last-updated info and mode display, live refresh during rebuilds
  - One-click single rebuild + rebuild-everything-outdated
- **Smart Rebuild Order**
  - Rebuilds only outdated indexes in dependency-safe order
  - Handles shared indexes once, skips busy indexes instead of colliding
  - Clear message when everything is already up to date
- **Smart Advisor**
  - Select what you changed: products, categories, prices, inventory, attributes, catalog price rules, search config, customers
  - Get the exact indexes to rebuild — never rebuild blindly
- **Named Automatic Schedules** (`Reindex > Schedule`)
  - Unlimited schedules, each with its own name, index set, active state
  - Presets from every 5 minutes to weekly + fully custom timetable
  - Last-run / next-run tracking + Run Now on demand
  - Executed automatically by cron (`Cron/ScheduledReindex.php`)
- **Complete Run History** (`Reindex > Reindex History`)
  - Every run logged: index, operation, outcome, duration (ms), error message, initiator, start/finish times
  - Status filters, bulk delete, one-click clear
  - Automatic expiry after retention period (default 30 days, `Cron/HistoryCleanup.php`)
- **Cron Health Monitoring**
  - Last successful run time, delayed-job pileups, failed/missed jobs in last 24h
  - Overall verdict + plain-language warnings + admin notifications when reindex is required
- **Large-Catalog Safety**
  - Warning before full rebuilds on large catalogs
  - Concurrent-operation protection: new rebuilds blocked while one is processing
  - Busy indexes report working state instead of starting twice
- **Indexer Mode Control**
  - Switch any index between Update on Save / Update by Schedule directly from dashboard
  - Mode changes logged to history
- **Permission-Aware & Translatable**
  - Separate ACL for Dashboard, History, Schedule, Config
  - Optional confirmation step before rebuilds
  - English translations included (`i18n/en_US.csv`)
- **Private by Design**
  - Only operational records stored locally (`themestar_reindex_history`, `themestar_reindex_schedule`)
  - No customer/order data touched, no external calls, nothing leaves your server

## Get this module (license per module)

This module is distributed via OUBPA. To use it in production you need a license for each module / site.

1. Go to the product page:
   https://oubpa.com/product/reindex-smart-index-management-scheduling-monitoring-for-magento-2/
2. Create an account (or log in):
   https://oubpa.com/my-account/
3. Choose your License Plan (e.g. Regular — 1 site / lifetime), Add to Cart and complete checkout.
4. Download the module from `My Account > Downloads`.
5. Install it in `app/code/Themestar/Reindex`, then:
   ```bash
   bin/magento module:enable Themestar_Reindex
   bin/magento setup:upgrade
   bin/magento setup:di:compile
   bin/magento setup:static-content:deploy -f
   bin/magento cache:flush
   ```
6. Magento cron must be running for schedules + history cleanup:
   ```bash
   bin/magento cron:install
   bin/magento cron:run
   ```

Each production site needs its own license. See the product page for pricing, updates and refund terms.

## Support

- Docs / Tickets: https://oubpa.com/support/
- Email: support@oubpa.com
- Product updates: https://oubpa.com/product/reindex-smart-index-management-scheduling-monitoring-for-magento-2/

## License

Commercial license via OUBPA — one license per module / site. See product page for terms. All rights reserved.
