# glab-groups-android

Thin GitHub Actions wrapper for the Android Gitiles root mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-android`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_ANDROID_SVC`
- Mirrors the current public `android.googlesource.com` repositories into
  `android/*` beneath `glab-forks`
- Preserves nested source repository paths such as `platform/...` under the
  target namespace
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 11 and 23 UTC
- Publishes discovery, plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```
