#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#

exports_files(["RelationTypeSteps.ts"])

load("@graknlabs_dependencies//tool/checkstyle:rules.bzl", "checkstyle_test")
load("//test/behaviour:rules.bzl", "node_cucumber_test")

checkstyle_test(
    name = "checkstyle",
    include = glob(["*"]),
    license_type = "apache",
)

node_cucumber_test(
    name = "test",
    features = ["@graknlabs_behaviour//concept/type:relationtype.feature"],
    node_modules = "//:node_modules",
    package_json = "//:package.json",
    core_artifact = "//test:native-grakn-artifact",
    client = "//:client-nodejs-compiled",
    steps = "//test/behaviour:behavioural-steps-compiled",
)
