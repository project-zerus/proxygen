licenses(['notice'])

cc_library(
  name = 'http_parser',
  srcs = [
    'proxygen/external/http_parser/http_parser.c',
    'proxygen/external/http_parser/http_parser_cpp.cpp'
  ],
  includes = [
    '.'
  ]
)

cc_test(
  name = 'http_parser_test',
  deps = [
    ':http_parser'
  ],
  srcs = [
    'proxygen/external/http_parser/test.c',
  ]
)

genrule(
  name = 'gen_http_common_headers_h',
  srcs = [
    'proxygen/lib/http/gen_HTTPCommonHeaders.cpp.sh',
    'proxygen/lib/http/gen_HTTPCommonHeaders.h.sh',
    'proxygen/lib/http/HTTPCommonHeaders.txt',
    'proxygen/lib/http/HTTPCommonHeaders.template.gperf',
    'proxygen/lib/http/HTTPCommonHeaders.template.h',
  ],
  cmd =
    'HEADERS_LIST=$(location proxygen/lib/http/HTTPCommonHeaders.txt) ' +
    'INSTALL_DIR=$(@D) FBCODE_DIR=proxygen ' +
    '$(location proxygen/lib/http/gen_HTTPCommonHeaders.h.sh)',
  outs = [
    'proxygen/lib/http/HTTPCommonHeaders.h',
  ]
)

genrule(
  name = 'gen_http_common_headers_cpp',
  srcs = [
    'proxygen/lib/http/gen_HTTPCommonHeaders.cpp.sh',
    'proxygen/lib/http/gen_HTTPCommonHeaders.h.sh',
    'proxygen/lib/http/HTTPCommonHeaders.txt',
    'proxygen/lib/http/HTTPCommonHeaders.template.gperf',
    'proxygen/lib/http/HTTPCommonHeaders.template.h',
  ],
  cmd =
    'HEADERS_LIST=$(location proxygen/lib/http/HTTPCommonHeaders.txt) ' +
    'INSTALL_DIR=$(@D) FBCODE_DIR=proxygen ' +
    '$(location proxygen/lib/http/gen_HTTPCommonHeaders.cpp.sh)',
  outs = [
    'proxygen/lib/http/HTTPCommonHeaders.cpp',
  ]
)

cc_library(
  name = 'http_common_headers',
  deps = [
    '//external:folly',
  ],
  hdrs = [
    'proxygen/lib/http/HTTPCommonHeaders.h',
  ],
  srcs = [
    'proxygen/lib/http/HTTPCommonHeaders.cpp',
  ],
  copts = [
    '-isystem$(GENDIR)/proxygen'
  ]
)

genrule(
  name = 'gen_trace_event_constants',
  srcs = [
    'proxygen/lib/utils/gen_trace_event_constants.py',
    'proxygen/lib/utils/TraceEventType.txt',
    'proxygen/lib/utils/TraceFieldType.txt',
  ],
  cmd =
    'python ' +
    '$(location proxygen/lib/utils/gen_trace_event_constants.py) ' +
    '--output_type=cpp --fbcode_dir=proxygen ' +
    '--input_files=$(location proxygen/lib/utils/TraceEventType.txt),' +
    '$(location proxygen/lib/utils/TraceFieldType.txt) ' +
    '--output_scope=proxygen --header_path=proxygen/lib/utils ' +
    '--install_dir=$(GENDIR)/proxygen/proxygen/lib/utils/',
  outs = [
    'proxygen/lib/utils/TraceEventType.cpp',
    'proxygen/lib/utils/TraceEventType.h',
    'proxygen/lib/utils/TraceFieldType.cpp',
    'proxygen/lib/utils/TraceFieldType.h',
  ]
)

cc_library(
  name = 'trace_event_constants',
  deps = [
    '//external:folly',
  ],
  hdrs = [
    'proxygen/lib/utils/TraceEventType.h',
    'proxygen/lib/utils/TraceFieldType.h',
  ],
  srcs = [
    'proxygen/lib/utils/TraceEventType.cpp',
    'proxygen/lib/utils/TraceFieldType.cpp',
  ],
  copts = [
    '-isystem$(GENDIR)/proxygen',
  ]
)

cc_library(
  name = 'proxygen',
  visibility = ['//visibility:public'],
  deps = [
    ':http_common_headers',
    ':http_parser',
    ':trace_event_constants',
  ],
  includes = [
    '.',
  ],
  srcs = [
    'proxygen/httpserver/HTTPServerAcceptor.cpp',
    'proxygen/httpserver/HTTPServer.cpp',
    'proxygen/httpserver/RequestHandlerAdaptor.cpp',
    'proxygen/httpserver/SignalHandler.cpp',
    'proxygen/lib/http/HTTPConnector.cpp',
    'proxygen/lib/http/HTTPConstants.cpp',
    'proxygen/lib/http/HTTPException.cpp',
    'proxygen/lib/http/HTTPHeaders.cpp',
    'proxygen/lib/http/HTTPMessage.cpp',
    'proxygen/lib/http/HTTPMethod.cpp',
    'proxygen/lib/http/ProxygenErrorEnum.cpp',
    'proxygen/lib/http/RFC2616.cpp',
    'proxygen/lib/http/Window.cpp',
    'proxygen/lib/http/codec/CodecProtocol.cpp',
    'proxygen/lib/http/codec/ErrorCode.cpp',
    'proxygen/lib/http/codec/FlowControlFilter.cpp',
    'proxygen/lib/http/codec/HTTP1xCodec.cpp',
    'proxygen/lib/http/codec/HTTPChecks.cpp',
    'proxygen/lib/http/codec/HTTPCodecFilter.cpp',
    'proxygen/lib/http/codec/HTTPSettings.cpp',
    'proxygen/lib/http/codec/SettingsId.cpp',
    'proxygen/lib/http/codec/SPDYCodec.cpp',
    'proxygen/lib/http/codec/SPDYConstants.cpp',
    'proxygen/lib/http/codec/SPDYUtil.cpp',
    'proxygen/lib/http/codec/TransportDirection.cpp',
    'proxygen/lib/http/codec/compress/GzipHeaderCodec.cpp',
    'proxygen/lib/http/codec/compress/HeaderTable.cpp',
    'proxygen/lib/http/codec/compress/HPACKCodec.cpp',
    'proxygen/lib/http/codec/compress/HPACKContext.cpp',
    'proxygen/lib/http/codec/compress/HPACKDecodeBuffer.cpp',
    'proxygen/lib/http/codec/compress/HPACKDecoder.cpp',
    'proxygen/lib/http/codec/compress/HPACKEncodeBuffer.cpp',
    'proxygen/lib/http/codec/compress/HPACKEncoder.cpp',
    'proxygen/lib/http/codec/compress/HPACKHeader.cpp',
    'proxygen/lib/http/codec/compress/Huffman.cpp',
    'proxygen/lib/http/codec/compress/Logging.cpp',
    'proxygen/lib/http/codec/compress/StaticHeaderTable.cpp',
    'proxygen/lib/http/codec/compress/experimental/hpack9/HPACKCodec.cpp',
    'proxygen/lib/http/codec/compress/experimental/hpack9/HPACKDecoder.cpp',
    'proxygen/lib/http/codec/compress/experimental/hpack9/HPACKEncoder.cpp',
    'proxygen/lib/http/codec/compress/experimental/hpack9/Huffman.cpp',
    'proxygen/lib/http/codec/compress/experimental/hpack9/StaticHeaderTable.cpp',
    'proxygen/lib/http/codec/experimental/HTTP2Codec.cpp',
    'proxygen/lib/http/codec/experimental/HTTP2Constants.cpp',
    'proxygen/lib/http/codec/experimental/HTTP2Framer.cpp',
    'proxygen/lib/http/session/ByteEvents.cpp',
    'proxygen/lib/http/session/ByteEventTracker.cpp',
    'proxygen/lib/http/session/CodecErrorResponseHandler.cpp',
    'proxygen/lib/http/session/HTTPDirectResponseHandler.cpp',
    'proxygen/lib/http/session/HTTPDownstreamSession.cpp',
    'proxygen/lib/http/session/HTTPErrorPage.cpp',
    'proxygen/lib/http/session/HTTPEvent.cpp',
    'proxygen/lib/http/session/HTTPSessionAcceptor.cpp',
    'proxygen/lib/http/session/HTTPSession.cpp',
    'proxygen/lib/http/session/HTTPTransaction.cpp',
    'proxygen/lib/http/session/HTTPTransactionEgressSM.cpp',
    'proxygen/lib/http/session/HTTPTransactionIngressSM.cpp',
    'proxygen/lib/http/session/HTTPUpstreamSession.cpp',
    'proxygen/lib/http/session/SimpleController.cpp',
    'proxygen/lib/http/session/TransportFilter.cpp',
    'proxygen/lib/services/RequestWorker.cpp',
    'proxygen/lib/services/Service.cpp',
    'proxygen/lib/services/WorkerThread.cpp',
    'proxygen/lib/utils/AsyncTimeoutSet.cpp',
    'proxygen/lib/utils/CryptUtil.cpp',
    'proxygen/lib/utils/Exception.cpp',
    'proxygen/lib/utils/HTTPTime.cpp',
    'proxygen/lib/utils/Logging.cpp',
    'proxygen/lib/utils/ParseURL.cpp',
    'proxygen/lib/utils/TraceEventContext.cpp',
    'proxygen/lib/utils/TraceEvent.cpp',
  ],
)
