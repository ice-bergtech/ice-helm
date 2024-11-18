# [`peertube`](https://github.com/ice-bergtech/ice-helm)

> A Helm Chart for chocobozzz/peertube, a self-hosted federated video publishing platform

[](https://github.com/ice-bergtech/ice-helm)[![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ](https://github.com/ice-bergtech/ice-helm)

* <https://github.com/ice-bergtech/helm-charts/tree/main/charts/peertube>
* <https://github.com/Chocobozzz/PeerTube>
* <https://hub.docker.com/r/chocobozzz/peertube/tags>

## Requirements

- [`helm`](https://helm.sh) - Refer to their [docs](https://helm.sh/docs) to get started.

## Usage

**Note:** This chart is a library chart which can not be used directly!

## Values

The following values can be used to adjust the helm chart.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| apiVersionOverrides | object | `{}` |  |
| client.menu.login.redirect_on_single_external_auth | bool | `false` |  |
| client.videos.miniature.display_author_avatar | bool | `false` |  |
| client.videos.miniature.prefer_author_display_name | bool | `false` |  |
| database.containerPorts.db | int | `5432` |  |
| database.enabled | bool | `true` |  |
| database.image.repository | string | `nil` |  |
| database.image.tag | string | `nil` |  |
| database.name | string | `"postgres"` |  |
| database.service.annotations | string | `nil` |  |
| database.service.labels | string | `nil` |  |
| database.service.nodePortHttp | string | `""` |  |
| database.service.servicePortHttp | int | `5432` |  |
| database.service.servicePortHttpName | string | `"db"` |  |
| database.service.type | string | `"ClusterIP"` | one of: ClusterIP | LoadBalancer | NodePort |
| dlp.force_ipv4 | bool | `false` |  |
| export.users.enabled | bool | `true` |  |
| export.users.export_expiration | string | `"2d"` |  |
| export.users.max_user_video_quota | string | `"10GB"` |  |
| followings.instance.auto_follow_back.enabled | bool | `false` |  |
| followings.instance.auto_follow_index.enabled | bool | `false` |  |
| followings.instance.auto_follow_index.index_url | string | `""` |  |
| instance."admin.email" | string | `""` |  |
| instance."contact_form.enabled" | bool | `false` |  |
| instance.admin_email | string | `"admin@example.com"` |  |
| instance.administrator | string | `""` | Primary administrator |
| instance.broadcast_message.dismissable | bool | `false` |  |
| instance.broadcast_message.enabled | bool | `false` |  |
| instance.broadcast_message.level | string | `"info"` |  |
| instance.broadcast_message.message | string | `""` |  |
| instance.business_model | string | `""` | Instance business model |
| instance.cache | string | `"previews:\n  size: 50\ncaptions:\n  size: 50\ntorrents:\n  size: 50\n"` | Cache Settings |
| instance.categories | list | `[]` | Video Categories |
| instance.code_of_conduct | string | `""` | Code of Conduct |
| instance.creation_reason | string | `""` | Reason for server creation |
| instance.default_client_route | string | `"/videos/trending"` | Default client route |
| instance.default_nsfw_policy | string | `"do_not_list"` | NSFW default policy |
| instance.default_theme | string | `"dark"` | Default instance theme |
| instance.description | string | `""` | Long Description of server |
| instance.followers.enabled | bool | `true` |  |
| instance.followers.manual_approval | bool | `false` |  |
| instance.followings.auto_follow_back.enabled | bool | `false` |  |
| instance.followings.auto_follow_index.enabled | bool | `false` |  |
| instance.followings.auto_follow_index.index_url | string | `""` |  |
| instance.hardware_information | string | `""` | Instance hardware info |
| instance.import | string | `"videos:\n  concurrency: 1\n  http:\n    enabled: false\n  torrent:\n    enabled: false\nvideo_channel_synchronization:\n  enabled: false\n"` |  |
| instance.is_nsfw | bool | `false` | If server is NSFW |
| instance.languages | list | `[]` |  |
| instance.maintenance_lifetime | string | `""` | Log of instance maintenance |
| instance.moderation_information | string | `""` | Information about moderation policies |
| instance.search | string | `"# Add ability to fetch remote videos/actors by their URI, that may not be federated with your instance\n# If enabled, the associated group will be able to \"escape\" from the instance follows\n# That means they will be able to follow channels, watch videos, list videos of non followed instances\nremote_uri:\n  users: true\n  anonymous: false\n\n# Use a third party index instead of your local index, only for search results\n# Useful to discover content outside of your instance\n# If you enable search_index, you must enable remote_uri search for users\n# If you do not enable remote_uri search for anonymous user, your instance will redirect the user on the origin instance\n# instead of loading the video locally\nsearch_index:\n  enabled: false\n  # URL of the search index, that should use the same search API and routes\n  # than PeerTube: https://docs.joinpeertube.org/api-rest-reference.html\n  # You should deploy your own with https://framagit.org/framasoft/peertube/search-index,\n  # and can use https://search.joinpeertube.org/ for tests, but keep in mind the latter is an unmoderated search index\n  url: ''\n  # You can disable local search in the client, so users only use the search index\n  disable_local_search: false\n  # If you did not disable local search in the client, you can decide to use the search index by default\n  is_default_search: false\n"` | Search configuration |
| instance.secrets.peertube | string | `""` |  |
| instance.services | string | `"# Cards configuration to format video in Twitter/X\n# All other social media (Facebook, Mastodon, etc.) are supported out of the box\ntwitter:\n  # Indicates the Twitter/X account for the website or platform where the content was published\n  # This is just an information injected in HTML that is required by Twitter/X\n  username: '@Chocobozzz'\n"` |  |
| instance.short_description | string | `""` | Short description of server |
| instance.signup | string | `"enabled: false\nlimit: 10\nrequires_email_verification: false\nminimum_age: 16\n"` |  |
| instance.terms | string | `"No terms for now."` | Legal Terms |
| instance.transcoding | string | `"enabled: true\nthreads: 1\nallow_additional_extensions: true\nallow_audio_files: true\nprofile: default\nconcurrency: 1\nresolutions:\n  0p: false\n  144p: false\n  240p: false\n  360p: false\n  480p: false\n  720p: false\n  1080p: false\n  1440p: false\n  2160p: false\nalways_transcode_original_resolution: true\nhls:\n  enabled: true\nwebtorrent:\n  enabled: false\n"` | Transcoding settings  |
| instance.trending.videos.algorithms.default | string | `"most-viewed"` |  |
| instance.trending.videos.algorithms.enabled[0] | string | `"hot"` |  |
| instance.trending.videos.algorithms.enabled[1] | string | `"most-viewed"` |  |
| instance.trending.videos.algorithms.enabled[2] | string | `"most-liked"` |  |
| instance.twitter_username | string | `"@Chocobozzz"` |  |
| instance.user.max_channels | int | `20` |  |
| instance.user.video_quota | int | `-1` |  |
| instance.user.video_quota_daily | int | `-1` |  |
| live.enabled | bool | `false` |  |
| live.store_live_streams | bool | `true` |  |
| log.accept_client_log | bool | `true` |  |
| log.anonymize_ip | bool | `true` |  |
| log.level | string | `"info"` |  |
| log.log_http_requests | bool | `true` |  |
| log.log_ping_requests | bool | `true` |  |
| log.log_tracker_unknown_infohash | bool | `true` |  |
| log.prettify_sql | bool | `false` |  |
| log.rotation.enabled | bool | `true` |  |
| log.rotation.max_file_size | string | `"12MB"` |  |
| log.rotation.max_files | int | `20` |  |
| metrics.geo_ip.city_db_url | string | `"https://dbip.mirror.framasoft.org/files/dbip-city-lite-latest.mmdb"` |  |
| metrics.geo_ip.country_db_url | string | `"https://dbip.mirror.framasoft.org/files/dbip-country-lite-latest.mmdb"` |  |
| metrics.geo_ip.enabled | bool | `false` |  |
| metrics.open_telemetry.enabled | bool | `false` |  |
| metrics.open_telemetry.http_request_duration.enabled | bool | `false` |  |
| metrics.open_telemetry.playback_stats_interval | string | `"15 seconds"` |  |
| metrics.open_telemetry.prometheus_exporter.hostname | string | `"127.0.0.1"` |  |
| metrics.open_telemetry.prometheus_exporter.port | int | `9091` |  |
| metrics.stats.enabled | bool | `false` |  |
| name | string | `"peertube"` | Provide a name in place of `peertube` |
| namespace | string | `peertube` | Override the namespace |
| peertube.containerPorts.stream | int | `1935` |  |
| peertube.containerPorts.webgui | int | `9000` |  |
| peertube.image.image | string | `"v6.3.2-bookworm"` |  |
| peertube.image.repository | string | `"Chocobozzz/PeerTube"` |  |
| peertube.name | string | `"peertube"` |  |
| peertube.replicas | int | `1` |  |
| peertube.service.annotations | string | `nil` |  |
| peertube.service.externalIPs | string | `""` |  |
| peertube.service.externalTrafficPolicy | string | `""` |  |
| peertube.service.labels | string | `nil` |  |
| peertube.service.loadBalancerClass | string | `""` |  |
| peertube.service.loadBalancerIP | string | `""` |  |
| peertube.service.loadBalancerSourceRanges | list | `[]` |  |
| peertube.service.nodePortHttp | string | `""` |  |
| peertube.service.servicePortHttp | int | `9000` |  |
| peertube.service.servicePortHttpName | string | `"webgui"` |  |
| peertube.service.servicePortLive | int | `1935` |  |
| peertube.service.servicePortLiveName | string | `"stream"` |  |
| peertube.service.sessionAffinity | string | `"None"` | either: None | ClientIP |
| peertube.service.type | string | `"ClusterIP"` | one of: ClusterIP | LoadBalancer | NodePort |
| redis.containerPorts.redis | int | `6379` |  |
| redis.containerPorts.sentinal | int | `26379` |  |
| redis.enabled | bool | `true` |  |
| redis.image.repository | string | `"redis"` |  |
| redis.image.tag | string | `"6-alpine"` |  |
| redis.name | string | `"redis"` |  |
| redis.sentinal.enabled | bool | `false` |  |
| redis.sentinal.master_name | string | `""` |  |
| redis.sentinal.tls | bool | `false` |  |
| redis.service.annotations | string | `nil` |  |
| redis.service.labels | string | `nil` |  |
| redis.service.nodePortHttp | string | `""` |  |
| redis.service.sentinelHostname | string | `""` |  |
| redis.service.servicePortHttp | int | `6379` |  |
| redis.service.servicePortHttpName | string | `"redis"` |  |
| redis.service.servicePortSentinel | int | `26379` |  |
| redis.service.servicePortSentinelName | string | `"sentinal"` |  |
| redis.service.type | string | `"ClusterIP"` | one of: ClusterIP | LoadBalancer | NodePort |
| s3.buckets.enabled | bool | `false` |  |
| s3.buckets.original_video_files.base_url | string | `""` |  |
| s3.buckets.original_video_files.bucket_name | string | `"original-video-files"` |  |
| s3.buckets.original_video_files.prefix | string | `""` |  |
| s3.buckets.streaming_playlists.base_url | string | `""` |  |
| s3.buckets.streaming_playlists.bucket_name | string | `"streaming-playlists"` |  |
| s3.buckets.streaming_playlists.prefix | string | `""` |  |
| s3.buckets.user_exports.base_url | string | `""` |  |
| s3.buckets.user_exports.bucket_name | string | `"user-exports"` |  |
| s3.buckets.user_exports.prefix | string | `""` |  |
| s3.buckets.web_videos.base_url | string | `""` |  |
| s3.buckets.web_videos.bucket_name | string | `"web-videos"` |  |
| s3.buckets.web_videos.prefix | string | `""` |  |
| s3.credentials.access_key_id | string | `""` |  |
| s3.credentials.secret_access_key | string | `""` |  |
| s3.enabled | bool | `false` |  |
| s3.endpoint | string | `""` |  |
| s3.max_request_attempts | int | `3` |  |
| s3.max_upload_part | string | `"100MB"` |  |
| s3.proxy_private_files | bool | `true` |  |
| s3.region | string | `"us-east-1"` |  |
| s3.single_bucket | string | `""` |  |
| s3.upload_acl.private | string | `"private"` |  |
| s3.upload_acl.public | string | `"public-read"` |  |
| search.remote_uri.anonymous | bool | `false` |  |
| search.remote_uri.users | bool | `true` |  |
| search.search_index.disable_local_search | bool | `false` |  |
| search.search_index.enabled | bool | `false` |  |
| search.search_index.is_default_search | bool | `false` |  |
| search.search_index.url | string | `""` |  |
| selectorLabels | list | `[]` |  |
| services.twitter.username | string | `nil` |  |
| storyboards.enabled | bool | `true` |  |
| strategy | string | `"type: Recreate"` |  |
| theme.default | string | `"default"` |  |
| users.enabled | bool | `true` |  |
| video_channel_synchronization.check_interval | string | `"1h"` |  |
| video_channel_synchronization.enabled | bool | `false` |  |
| video_channel_synchronization.full_sync_videos_limit | int | `1000` |  |
| video_channel_synchronization.max_per_user | int | `10` |  |
| video_channel_synchronization.videos_limit_per_synchronization | int | `10` |  |
| webserver.hostname | string | `"peertube.local"` |  |
| webserver.https | bool | `false` |  |
| webserver.port | int | `80` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Iceberg Tech |  | <https://ice-bergtech.github.io/> |

## License

[MIT](../LICENSE.md) – © 2024 [Iceberg Tech](https://icebergtech.xyz)