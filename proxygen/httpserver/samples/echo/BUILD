licenses(["notice"])

cc_library(
  name = 'echo_handler',
  deps = [
    '//proxygen:proxygen',
  ],
  srcs = [
    'EchoHandler.cpp',
  ]
)

cc_test(
  name = 'echo_handler_test',
  deps = [
    ':echo_handler',
    '//external:gmock_main',
  ],
  srcs = [
    'test/EchoHandlerTest.cpp',
  ]
)

cc_binary(
  name = 'echo_server',
  deps = [
    ':echo_handler',
  ],
  srcs = [
    'EchoServer.cpp',
  ]
)
