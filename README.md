# Archipelago Docker Deployment for Drupal 9

This repository serves as bootstrap for a Archipelago 1.0.0-RC3 deployment via Docker and provides many more options this time:

- minio.io (latest) S3/Azure/Local/Remote alternative with a new Console and also Gateway to many others.
- Apache Solr 8.8.2 (or 7.5 if you go legacy) with the wizardly Solr OCR Highlight library [v0.7.1](https://github.com/dbmdz/solr-ocrhighlighting/releases/tag/0.7.1) build by the Developement Team at the [Bavarian State Library](https://github.com/dbmdz). Thanks Johannes Baiter!
- MySQL 8.0.22 (or MySQL 5.7 if you go legacy)
- NGINX 11
- Custom PHP FPM 7.4 super-tuned for Drupal 8/9 with multi-arch (so M1 too) capabilities (or 7.3 FPM if you go legacy), WARC to WACZ processing, and Composer 2.0
- Natural Language Processing via NLPWEB64
- Cantaloupe 4.1.9 as IIIF Server with Video Frame extraction and PDF support
- A Skeleton Project setup to run latest Version of Drupal (9.2.9) and Strawberry Field modules on 1.0.0-RC3 & friends on 0.2.0
- Official *Drupal 9 ready* release again. D9.2.9 this time. Drupal 8 is no longer maintained, and we have [documented the upgrade path](docs/upgradeFromD8ToD9.md)
- Complete support for Apple Silicon *M1* Machines and in general arm64 architecture Chips like Raspberry Pi 4, with specially built arm64 docker containers. Blazing fast OCR!

The skeleton project contains all the pieces needed to run a local deployment of a vanilla Archipelago including (*YES*!) content provided as an optional feature from [archipelago-recyclables](https://github.com/esmero/archipelago-recyclables)
