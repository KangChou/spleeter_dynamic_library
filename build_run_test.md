# 构建成功

```bash
root@0eb8bb98e4bd:~/spleeter# bazel build //application:spleeter
DEBUG: Rule 'eigen' indicated that a canonical reproducible form can be obtained by modifying arguments commit = "21ae2afd4edaa1b69782c67a54182d34efe43f9c", shallow_since = "1544551075 +0100" and dropping ["tag"]
DEBUG: Repository eigen instantiated at:
  /root/spleeter/WORKSPACE:5:22: in <toplevel>
  /root/.cache/bazel/_bazel_root/745280113deedbe3e5183d48a80fa67d/external/spleeter/third_party/dependencies.bzl:17:10: in spleeter_dependencies
  /root/.cache/bazel/_bazel_root/745280113deedbe3e5183d48a80fa67d/external/spleeter/third_party/eigen/eigen.bzl:5:27: in eigen
Repository rule new_git_repository defined at:
  /root/.cache/bazel/_bazel_root/745280113deedbe3e5183d48a80fa67d/external/bazel_tools/tools/build_defs/repo/git.bzl:186:37: in <toplevel>
INFO: Analyzed target //application:spleeter (67 packages loaded, 15814 targets configured).
INFO: Found 1 target...
INFO: From Compiling src/wave/file.cc:
external/audionamix/src/wave/file.cc: In member function 'wave::Error wave::File::Impl::ReadHeader(wave::HeaderList*)':
external/audionamix/src/wave/file.cc:83:19: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
     if (file_size < sizeof(WAVEHeader)) {
         ~~~~~~~~~~^~~~~~~~~
INFO: From Compiling spleeter/inference_engine/tflite_inference_engine.cpp:
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tflite_inference_engine.cpp:8:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h: In instantiation of 'std::__cxx11::string* google::Check_EQImpl(const T1&, const T2&, const char*) [with T1 = long unsigned int; T2 = int; std::__cxx11::string = std::__cxx11::basic_string<char>]':
spleeter/inference_engine/tflite_inference_engine.cpp:131:5:   required from here
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:719:32: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
 DEFINE_CHECK_OP_IMPL(Check_EQ, ==)  // Compilation error with CHECK_EQ(NULL, x)?
                                ^
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:148:53: note: in definition of macro 'GOOGLE_PREDICT_TRUE'
 #define GOOGLE_PREDICT_TRUE(x) (__builtin_expect(!!(x), 1))
                                                     ^
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:719:1: note: in expansion of macro 'DEFINE_CHECK_OP_IMPL'
 DEFINE_CHECK_OP_IMPL(Check_EQ, ==)  // Compilation error with CHECK_EQ(NULL, x)?
 ^~~~~~~~~~~~~~~~~~~~
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h: In instantiation of 'std::__cxx11::string* google::Check_GTImpl(const T1&, const T2&, const char*) [with T1 = long unsigned int; T2 = int; std::__cxx11::string = std::__cxx11::basic_string<char>]':
spleeter/inference_engine/tflite_inference_engine.cpp:139:5:   required from here
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:724:32: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
 DEFINE_CHECK_OP_IMPL(Check_GT, > )
                                ^
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:148:53: note: in definition of macro 'GOOGLE_PREDICT_TRUE'
 #define GOOGLE_PREDICT_TRUE(x) (__builtin_expect(!!(x), 1))
                                                     ^
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:724:1: note: in expansion of macro 'DEFINE_CHECK_OP_IMPL'
 DEFINE_CHECK_OP_IMPL(Check_GT, > )
 ^~~~~~~~~~~~~~~~~~~~
INFO: From Compiling spleeter/inference_engine/tf_inference_engine.cpp:
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:506:0: warning: "LOG" redefined
 #define LOG(severity) COMPACT_GOOGLE_LOG_ ## severity.stream()
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:110:0: note: this is the location of the previous definition
 #define LOG(severity) _TF_LOG_##severity
 
In file included from bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:513:0,
                 from ./spleeter/logging/logging.h:9,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/vlog_is_on.h:82:0: warning: "VLOG_IS_ON" redefined
 #define VLOG_IS_ON(verboselevel)                                \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:122:0: note: this is the location of the previous definition
 #define VLOG_IS_ON(lvl)                                                     \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:586:0: warning: "CHECK" redefined
 #define CHECK(condition)  \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:254:0: note: this is the location of the previous definition
 #define CHECK(condition)              \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:744:0: warning: "CHECK_OP_LOG" redefined
 #define CHECK_OP_LOG(name, op, val1, val2, log)                         \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:392:0: note: this is the location of the previous definition
 #define CHECK_OP_LOG(name, op, val1, val2)                     \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:765:0: warning: "CHECK_OP" redefined
 #define CHECK_OP(name, op, val1, val2) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:400:0: note: this is the location of the previous definition
 #define CHECK_OP(name, op, val1, val2) CHECK_OP_LOG(name, op, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:790:0: warning: "CHECK_EQ" redefined
 #define CHECK_EQ(val1, val2) CHECK_OP(_EQ, ==, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:403:0: note: this is the location of the previous definition
 #define CHECK_EQ(val1, val2) CHECK_OP(Check_EQ, ==, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:791:0: warning: "CHECK_NE" redefined
 #define CHECK_NE(val1, val2) CHECK_OP(_NE, !=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:404:0: note: this is the location of the previous definition
 #define CHECK_NE(val1, val2) CHECK_OP(Check_NE, !=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:792:0: warning: "CHECK_LE" redefined
 #define CHECK_LE(val1, val2) CHECK_OP(_LE, <=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:405:0: note: this is the location of the previous definition
 #define CHECK_LE(val1, val2) CHECK_OP(Check_LE, <=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:793:0: warning: "CHECK_LT" redefined
 #define CHECK_LT(val1, val2) CHECK_OP(_LT, < , val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:406:0: note: this is the location of the previous definition
 #define CHECK_LT(val1, val2) CHECK_OP(Check_LT, <, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:794:0: warning: "CHECK_GE" redefined
 #define CHECK_GE(val1, val2) CHECK_OP(_GE, >=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:407:0: note: this is the location of the previous definition
 #define CHECK_GE(val1, val2) CHECK_OP(Check_GE, >=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:795:0: warning: "CHECK_GT" redefined
 #define CHECK_GT(val1, val2) CHECK_OP(_GT, > , val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:408:0: note: this is the location of the previous definition
 #define CHECK_GT(val1, val2) CHECK_OP(Check_GT, >, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:800:0: warning: "CHECK_NOTNULL" redefined
 #define CHECK_NOTNULL(val) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:409:0: note: this is the location of the previous definition
 #define CHECK_NOTNULL(val)                                 \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:941:0: warning: "LOG_EVERY_N" redefined
 #define LOG_EVERY_N(severity, n)                                        \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:224:0: note: this is the location of the previous definition
 #define LOG_EVERY_N(severity, n)                       \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:950:0: warning: "LOG_FIRST_N" redefined
 #define LOG_FIRST_N(severity, n) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:230:0: note: this is the location of the previous definition
 #define LOG_FIRST_N(severity, n)                       \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:986:0: warning: "DVLOG" redefined
 #define DVLOG(verboselevel) VLOG(verboselevel)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:141:0: note: this is the location of the previous definition
 #define DVLOG VLOG
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/tf_inference_engine.cpp:7:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:1098:0: warning: "VLOG" redefined
 #define VLOG(verboselevel) LOG_IF(INFO, VLOG_IS_ON(verboselevel))
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/tf_inference_engine.cpp:5:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:131:0: note: this is the location of the previous definition
 #define VLOG(level)                                              \
 
INFO: From Compiling spleeter/inference_engine/inference_engine_strategy.cpp:
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:506:0: warning: "LOG" redefined
 #define LOG(severity) COMPACT_GOOGLE_LOG_ ## severity.stream()
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:110:0: note: this is the location of the previous definition
 #define LOG(severity) _TF_LOG_##severity
 
In file included from bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:513:0,
                 from ./spleeter/logging/logging.h:9,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/vlog_is_on.h:82:0: warning: "VLOG_IS_ON" redefined
 #define VLOG_IS_ON(verboselevel)                                \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:122:0: note: this is the location of the previous definition
 #define VLOG_IS_ON(lvl)                                                     \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:586:0: warning: "CHECK" redefined
 #define CHECK(condition)  \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:254:0: note: this is the location of the previous definition
 #define CHECK(condition)              \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:744:0: warning: "CHECK_OP_LOG" redefined
 #define CHECK_OP_LOG(name, op, val1, val2, log)                         \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:392:0: note: this is the location of the previous definition
 #define CHECK_OP_LOG(name, op, val1, val2)                     \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:765:0: warning: "CHECK_OP" redefined
 #define CHECK_OP(name, op, val1, val2) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:400:0: note: this is the location of the previous definition
 #define CHECK_OP(name, op, val1, val2) CHECK_OP_LOG(name, op, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:790:0: warning: "CHECK_EQ" redefined
 #define CHECK_EQ(val1, val2) CHECK_OP(_EQ, ==, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:403:0: note: this is the location of the previous definition
 #define CHECK_EQ(val1, val2) CHECK_OP(Check_EQ, ==, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:791:0: warning: "CHECK_NE" redefined
 #define CHECK_NE(val1, val2) CHECK_OP(_NE, !=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:404:0: note: this is the location of the previous definition
 #define CHECK_NE(val1, val2) CHECK_OP(Check_NE, !=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:792:0: warning: "CHECK_LE" redefined
 #define CHECK_LE(val1, val2) CHECK_OP(_LE, <=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:405:0: note: this is the location of the previous definition
 #define CHECK_LE(val1, val2) CHECK_OP(Check_LE, <=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:793:0: warning: "CHECK_LT" redefined
 #define CHECK_LT(val1, val2) CHECK_OP(_LT, < , val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:406:0: note: this is the location of the previous definition
 #define CHECK_LT(val1, val2) CHECK_OP(Check_LT, <, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:794:0: warning: "CHECK_GE" redefined
 #define CHECK_GE(val1, val2) CHECK_OP(_GE, >=, val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:407:0: note: this is the location of the previous definition
 #define CHECK_GE(val1, val2) CHECK_OP(Check_GE, >=, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:795:0: warning: "CHECK_GT" redefined
 #define CHECK_GT(val1, val2) CHECK_OP(_GT, > , val1, val2)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:408:0: note: this is the location of the previous definition
 #define CHECK_GT(val1, val2) CHECK_OP(Check_GT, >, val1, val2)
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:800:0: warning: "CHECK_NOTNULL" redefined
 #define CHECK_NOTNULL(val) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:409:0: note: this is the location of the previous definition
 #define CHECK_NOTNULL(val)                                 \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:941:0: warning: "LOG_EVERY_N" redefined
 #define LOG_EVERY_N(severity, n)                                        \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:224:0: note: this is the location of the previous definition
 #define LOG_EVERY_N(severity, n)                       \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:950:0: warning: "LOG_FIRST_N" redefined
 #define LOG_FIRST_N(severity, n) \
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:230:0: note: this is the location of the previous definition
 #define LOG_FIRST_N(severity, n)                       \
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:986:0: warning: "DVLOG" redefined
 #define DVLOG(verboselevel) VLOG(verboselevel)
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:141:0: note: this is the location of the previous definition
 #define DVLOG VLOG
 
In file included from ./spleeter/logging/logging.h:9:0,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:10:
bazel-out/k8-fastbuild/bin/external/glog/_virtual_includes/glog/glog/logging.h:1098:0: warning: "VLOG" redefined
 #define VLOG(verboselevel) LOG_IF(INFO, VLOG_IS_ON(verboselevel))
 
In file included from external/tensorflow/include/tensorflow/core/platform/logging.h:27:0,
                 from external/tensorflow/include/tensorflow/core/framework/allocator.h:28,
                 from external/tensorflow/include/tensorflow/core/framework/tensor.h:23,
                 from external/tensorflow/include/tensorflow/cc/framework/ops.h:21,
                 from external/tensorflow/include/tensorflow/cc/client/client_session.h:24,
                 from ./spleeter/inference_engine/tf_inference_engine.h:11,
                 from spleeter/inference_engine/inference_engine_strategy.cpp:8:
external/tensorflow/include/tensorflow/core/platform/default/logging.h:131:0: note: this is the location of the previous definition
 #define VLOG(level)                                              \
 
Target //application:spleeter up-to-date:
  bazel-bin/application/spleeter
INFO: Elapsed time: 287.805s, Critical Path: 9.90s
INFO: 206 processes: 45 internal, 161 processwrapper-sandbox.
INFO: Build completed successfully, 206 total actions


```
