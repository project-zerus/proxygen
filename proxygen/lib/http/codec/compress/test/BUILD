licenses(["notice"])

cc_library(
  name = 'compress_test_utils',
  visibility = ['//visibility:public'],
  deps = [
    '//proxygen/proxygen/lib/test:test_main',
  ],
  srcs = [
    'HTTPArchive.cpp',
    'TestUtil.cpp',
  ]
)

cc_test(
  name = "CompressTests",
  deps = [
    ':compress_test_utils'
  ],
  srcs = [
    'HeaderPieceTests.cpp',
    'HeaderTableTests.cpp',
    'HPACKBufferTests.cpp',
    'HPACKCodecTests.cpp',
    'HPACKContextTests.cpp',
    'HPACKHeaderTests.cpp',
    'HuffmanTests.cpp',
    'LoggingTests.cpp',
    'RFCExamplesTests.cpp',
  ]
)
