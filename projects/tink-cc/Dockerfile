# Copyright 2021 Google LLC
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
FROM gcr.io/oss-fuzz-base/base-builder-go
RUN apt-get update && apt-get install -y make pkg-config
RUN git clone --depth 1 https://github.com/tink-crypto/tink-cc

RUN mkdir $SRC/tink-cc/fuzzing
COPY fuzzing_CMake $SRC/tink-cc/fuzzing/CMakeLists.txt
COPY tink_encrypt_decrypt_fuzzer.cc $SRC/tink-cc/fuzzing/tink_encrypt_decrypt_fuzzer.cc
COPY build.sh $SRC/

WORKDIR tink-cc
