licenses(["notice"])

cc_library(
  name = 'session_test_utils',
  deps = [
    '//proxygen/proxygen/lib/http/codec/test:codec_test_utils',
  ],
  srcs = [
    'TestUtils.cpp',
  ]
)


cc_test(
  name = 'DownstreamTransactionTest',
  srcs = ['DownstreamTransactionTest.cpp'],
  deps = [':session_test_utils']
)


cc_test(
  name = 'HTTPDownstreamSessionTest',
  srcs = ['HTTPDownstreamSessionTest.cpp'],
  deps = [':session_test_utils']
)


cc_test(
  name = 'HTTPSessionAcceptorTest',
  srcs = ['HTTPSessionAcceptorTest.cpp'],
  data = [
    'test_cert1.key',
    'test_cert1.pem',
  ],
  deps = [':session_test_utils']
)


cc_test(
  name = 'HTTPTransactionSMTest',
  srcs = ['HTTPTransactionSMTest.cpp'],
  deps = [':session_test_utils']
)


cc_test(
  name = 'HTTPUpstreamSessionTest',
  srcs = ['HTTPUpstreamSessionTest.cpp'],
  deps = [':session_test_utils']
)


cc_test(
  name = 'MockCodecDownstreamTest',
  srcs = ['MockCodecDownstreamTest.cpp'],
  deps = [':session_test_utils']
)
