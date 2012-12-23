### Version 0.8.1
* Bump librato-metrics to fix issue with Rails 3.1.6

### Version 0.8.0
* Add support for terser `LIBRATO_` prefixed environment variables
* Deprecate `LIBRATO_METRICS_` prefixed environment variables
* Always check worker, not just in forking servers
* Refactor configuration/logging functionality into standalone modules

### Version 0.7.3
* More resilient handling of invalid metric/source names
* Don't start if provided source is invalid

### Version 0.7.2
* Relax multi_json version requirement to allow running with Rails 3.1/3.0
* Fix exception if current environment is not in config file
* Always respect LIBRATO_METRICS_LOG_LEVEL env variable for easier startup debugging
* Add more debugging statements in startup sequence_

### Version 0.7.1
* Support for Passenger 4 (James Miller)

### Version 0.7.0
* Add configurable log_level for easier debugging
* Show settings during startup in debug mode
* Logs are now redirected to be visible when running on Heroku
* Fix running with unicorn on Heroku
* Don't start on Heroku without an explicit source being set
* Improve log messages
* Clean up tracing output for measurements
* Remove redundant per-measurement time tracking
* Add some initial benchmarks of instrumenting performance
* Added troubleshooting and heroku setup sections to README
* Documentation improvements

### Version 0.6.0
* Add support for custom sources per measurement via increment
* Add support for custom sources per measurement via measure/timing
* Add support for sporadic (non-continuous) increment metrics
* Aggregate metrics by source by default
* Don't append pids to sources by default anymore
* Start extracting collector behaviors into Collector
* measure/timing metrics prefix now updates dynamically if .prefix changes after startup
* Fix issue with some helpers not being found when running on unicorn
* Fix issue with sometimes attempting submission without full credentials
* Documentation improvements

### Version 0.5.2
* Fix bug where measure/timing events don't apply global prefix properly
* Fix bug where increment events could have missing values if not called

### Version 0.5.1
* Remove old helper libs which may cause load conflict for rails helpers
* Don't lock mutex during duration of timing blocks

### Version 0.5.0
* Support block form of timing
* Config option to disable pid inclusion in source (Chris Roby)
* Change prefix handling to be global for all reported metrics
* Fix misassignment of source to prefix

### Version 0.4.1
* Fix whitespace-before-params warning.

### Version 0.4.0
* Support ERB config file using env variables. (Justin Smestad)
* Precedence changed to favor YAML config (if present) over env vars.
  Mirrors Heroku add-on model. (Justin Smestad)
* Report counters as gauge increments instead.

### Version 0.3.1
* Fix config file fields to match new env variables

### Version 0.3.0
* Rename to librato-rails
* Change env variables to LIBRATO_METRICS_USER and LIBRATO_METRICS_TOKEN

### Version 0.2.0
* Add rack middleware component (Pat Allan)
* Fix config file detection (Rafael Chacon)
