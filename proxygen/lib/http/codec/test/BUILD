licenses(["notice"])

cc_library(
  name = 'codec_test_utils',
  visibility = ['//visibility:public'],
  testonly = 1,
  deps = [
    '//proxygen/proxygen/lib/test:test_main',
  ],
  srcs = [
    'TestUtils.cpp',
  ]
)

cc_test(
  name = 'FilterTests',
  srcs = ['FilterTests.cpp'],
  deps = [':codec_test_utils']
)

cc_test(
  name = 'HTTP1xCodecTest',
  srcs = ['HTTP1xCodecTest.cpp'],
  deps = [':codec_test_utils']
)


cc_test(
  name = 'SPDYCodecTest',
  srcs = ['SPDYCodecTest.cpp'],
  deps = [':codec_test_utils']
)
