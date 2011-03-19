# ==================================================================================================
# Copyright 2011 Twitter, Inc.
# --------------------------------------------------------------------------------------------------
# Licensed to the Apache Software Foundation (ASF) under one or more contributor license
# agreements.  See the NOTICE file distributed with this work for additional information regarding
# copyright ownership.  The ASF licenses this file to you under the Apache License, Version 2.0
# (the "License"); you may not use this file except in compliance with the License.  You may
# obtain a copy of the License at
#
#  http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software distributed under the
# License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either
# express or implied.  See the License for the specific language governing permissions and
# limitations under the License.
# ==================================================================================================

from pants import *

java_library(name = 'stats-provider',
  provides = artifact(
    org = 'com.twitter.common',
    name = 'stats-provider',
    repo = pants('build-support/commons/ivy:public'),
  ),
  dependencies = [
    pants('3rdparty:guava'),
  ],
  sources = [
    'Stat.java',
    'StatsProvider.java',
  ],
)

java_library(name = 'stats',
  provides = artifact(
    org = 'com.twitter.common',
    name = 'stats',
    repo = pants('build-support/commons/ivy:public'),
  ),
  dependencies = [
    pants('3rdparty:guava'),
    pants('3rdparty:jsr305'),
    pants(':stats-provider'),
    pants('src/java/com/twitter/common/base'),
    pants('src/java/com/twitter/common/collections'),
    pants('src/java/com/twitter/common/quantity'),
    pants('src/java/com/twitter/common/util:sampler'),
  ],
  sources = [
    'MovingAverage.java',
    'Percentile.java',
    'PipelineStats.java',
    'Ratio.java',
    'Rate.java',
    'RecordingStat.java',
    'RecordingStatImpl.java',
    'RequestStats.java',
    'SlidingStats.java',
    'SampledStat.java',
    'StatImpl.java',
    'Stats.java',
  ],
)

java_library(name = 'jvm',
  provides = artifact(
    org = 'com.twitter.common',
    name = 'stats-jvm',
    repo = pants('build-support/commons/ivy:public'),
  ),
  dependencies = [
    pants(':stats'),
    pants('src/java/com/twitter/common/quantity'),
  ],
  sources = [ 'JvmStats.java' ],
)

java_library(name = 'time-series',
  provides = artifact(
    org = 'com.twitter.common',
    name = 'stats-time-series',
    repo = pants('build-support/commons/ivy:public'),
  ),
  dependencies = [
    pants('3rdparty:guava'),
    pants('3rdparty:guice'),
    pants(':stats'),
    pants('src/java/com/twitter/common/application:action'),
    pants('src/java/com/twitter/common/collections'),
    pants('src/java/com/twitter/common/quantity'),
  ],
  sources = [
    'TimeSeries.java',
    'TimeSeriesRepository.java',
    'TimeSeriesRepositoryImpl.java',
  ],
)

java_library(name = 'util',
  provides = artifact(
    org = 'com.twitter.common',
    name = 'stats-util',
    repo = pants('build-support/commons/ivy:public'),
  ),
  dependencies = [
    pants('3rdparty:guava'),
  ],
  sources = [
    'CounterMap.java',
    'CounterMapWithTopKey.java',
    'Entropy.java',
    'PrintableHistogram.java',
    'Significance.java',
    'Statistics.java',
  ],
)