# Copyright 2020 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM gcr.io/oss-fuzz-base/base-builder
# ! This project was pinned after a clang bump. Please remove the pin, Try to fix any build warnings and errors, as well as runtime errors
RUN apt-get update && apt-get install -y cmake libgc-dev pkg-config
RUN git clone --depth 1 https://github.com/arximboldi/immer.git immer
WORKDIR immer
COPY build.sh $SRC/
