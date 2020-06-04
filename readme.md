# Flank Bug

## GCloud

- `gcloud firebase test android run flank.yml:gcloud`

```
$ gcloud firebase test android run flank.yml:gcloud

Have questions, feedback, or issues? Get support by visiting:
  https://firebase.google.com/support/

Uploading [./app-single-success-debug.apk] to Firebase Test Lab...
Uploading [./app-single-success-debug-androidTest.apk] to Firebase Test Lab...
Raw results will be stored in your GCS bucket at [https://console.developers.google.com/storage/browser/test-lab-v9cn46bb990nx-kz69ymd4nm9aq/2020-06-04_12:23:56.226083_OKRc/]

Test [matrix-1js6b13j8amnp] has been created in the Google Cloud.
Firebase Test Lab will execute your instrumentation test on 1 device(s).
Creating individual test executions...done.

Test results will be streamed to [https://console.firebase.google.com/project/flank-open-source/testlab/histories/bh.da0c237aaa33732/matrices/8086891561925724866].
12:24:06 Test is Pending
12:26:44 Starting attempt 1.
12:26:44 Started logcat recording.
12:26:44 Test is Running
12:26:50 Preparing device.
12:26:57 Logging in to Google account on device.
12:27:03 Installing apps.
12:27:03 Retrieving Pre-Test Package Stats information from the device.
12:27:03 Retrieving Performance Environment information from the device.
12:27:09 Started crash detection.
12:27:09 Started crash monitoring.
12:27:09 Started performance monitoring.
12:27:09 Started video recording.
12:27:09 Starting instrumentation test.
12:27:09 Completed instrumentation test.
12:27:09 Stopped video recording.
12:27:15 Stopped performance monitoring.
12:27:15 Stopped crash monitoring.
12:27:15 Retrieving Post-test Package Stats information from the device.
12:27:15 Logging out of Google account on device.
12:27:15 Stopped logcat recording.
12:27:15 Done. Test time = 2 (secs)
12:27:15 Starting results processing. Attempt: 1
12:27:21 Completed results processing. Time taken = 2 (secs)
12:27:21 Test is Finished

Instrumentation testing complete.

More details are available at [https://console.firebase.google.com/project/flank-open-source/testlab/histories/bh.da0c237aaa33732/matrices/8086891561925724866].
┌─────────┬────────────────────────┬─────────────────────┐
│ OUTCOME │    TEST_AXIS_VALUE     │     TEST_DETAILS    │
├─────────┼────────────────────────┼─────────────────────┤
│ Passed  │ walleye-26-en-portrait │ 1 test cases passed │
└─────────┴────────────────────────┴─────────────────────┘

```

## Flank

- `flank android run`

```
$ flank android run
version: local_snapshot
revision: 81303e5948429125ab8f04dbb0bc1ce44c6bc9f4

AndroidArgs
    gcloud:
      results-bucket: test-lab-v9cn46bb990nx-kz69ymd4nm9aq
      results-dir: 2020-06-04_19-28-34.396000_hUvr
      record-video: false
      timeout: 15m
      async: false
      client-details:
      network-profile: null
      results-history-name: null
      # Android gcloud
      app: /Users/mac/code/flank_bug2/app-single-success-debug.apk
      test: /Users/mac/code/flank_bug2/app-single-success-debug-androidTest.apk
      additional-apks:
      auto-google-login: false
      use-orchestrator: false
      directories-to-pull:
      other-files:
      performance-metrics: false
      num-uniform-shards: null
      test-runner-class: null
      test-targets:
      robo-directives:
      robo-script: null
      device:
        - model: NexusLowRes
          version: 28
          locale: en
          orientation: portrait
      num-flaky-test-attempts: 0

    flank:
      max-test-shards: 1
      shard-time: -1
      num-test-runs: 1
      smart-flank-gcs-path:
      smart-flank-disable-upload: false
      files-to-download:
      test-targets-always-run:
      disable-sharding: false
      project: flank-open-source
      local-result-dir: results
      full-junit-result: false
      # Android Flank Yml
      keep-file-path: false
      additional-app-test-apks:
      run-timeout: -1
      legacy-junit-result: false
      ignore-failed-tests: false
      output-style: multi

RunTests

 Smart Flank cache hit: 0% (0 / 1)
  Shard times: 120s

  Uploading app-single-success-debug.apk .
  Uploading app-single-success-debug-androidTest.apk .
  1 test / 1 shard

  1 matrix ids created in 0m 3s
  https://console.developers.google.com/storage/browser/test-lab-v9cn46bb990nx-kz69ymd4nm9aq/2020-06-04_19-28-34.396000_hUvr

Matrices webLink
  matrix-2zohu9i2o0vqb https://console.firebase.google.com/project/flank-open-source/testlab/histories/bh.da0c237aaa33732/matrices/7572966618634793250/executions/bs.c296a265cd20dd08

  2m 23s matrix-2zohu9i2o0vqb NexusLowRes-28 shard-0 FINISHED
  2m 29s matrix-2zohu9i2o0vqb FINISHED

FetchArtifacts
  .
  Updating matrix file

CostReport
  Virtual devices
    $0.02 for 1m

MatrixResultsReport
  0 / 1 (0.00%)
  1 matrices failed

More details are available at [https://console.firebase.google.com/project/flank-open-source/testlab/histories/bh.da0c237aaa33732/matrices/7572966618634793250]
┌─────────┬────────────────────────┬────────────────────┐
│ OUTCOME │    TEST_AXIS_VALUE     │    TEST_DETAILS    │
├─────────┼────────────────────────┼────────────────────┤
│ failure │  matrix-2zohu9i2o0vqb  │                    │
└─────────┴────────────────────────┴────────────────────┘
  Uploading JUnitReport.xml .
```
