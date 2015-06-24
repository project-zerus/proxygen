gen_rule(
  name = 'HTTPCommonHeaders_h',
  srcs = [
    'gen_HTTPCommonHeaders.h.sh',
    'HTTPCommonHeaders.template.h',
    'HTTPCommonHeaders.txt',
  ],
  outs = [
    'HTTPCommonHeaders.h',
  ],
  cmd = '''FBCODE_DIR=. ''' \
        '''INSTALL_DIR=$BUILD_DIR/proxygen/lib/http ''' \
        '''HEADERS_LIST=proxygen/lib/http/HTTPCommonHeaders.txt ''' \
        '''$FIRST_SRC'''
)

gen_rule(
  name = 'HTTPCommonHeaders_cpp',
  srcs = [
    'gen_HTTPCommonHeaders.cpp.sh',
    'HTTPCommonHeaders.template.gperf',
    'HTTPCommonHeaders.txt',
  ],
  outs = [
    'HTTPCommonHeaders.cpp',
  ],
  cmd = '''FBCODE_DIR=. ''' \
        '''INSTALL_DIR=$BUILD_DIR/proxygen/lib/http ''' \
        '''HEADERS_LIST=proxygen/lib/http/HTTPCommonHeaders.txt ''' \
        '''$FIRST_SRC'''
)

cc_library(
  name = 'http',
  warning = 'no',
  srcs = [
    'HTTPCommonHeaders.cpp',
    'HTTPConnector.cpp',
    'HTTPConstants.cpp',
    'HTTPException.cpp',
    'HTTPHeaders.cpp',
    'HTTPMessage.cpp',
    'HTTPMethod.cpp',
    'ProxygenErrorEnum.cpp',
    'RFC2616.cpp',
    'Window.cpp',
    'codec/CodecProtocol.cpp',
    'codec/ErrorCode.cpp',
    'codec/FlowControlFilter.cpp',
    'codec/HTTP1xCodec.cpp',
    'codec/HTTPChecks.cpp',
    'codec/HTTPCodecFilter.cpp',
    'codec/HTTPCodecPrinter.cpp',
    'codec/HTTPSettings.cpp',
    'codec/SettingsId.cpp',
    'codec/SPDYCodec.cpp',
    'codec/SPDYConstants.cpp',
    'codec/SPDYUtil.cpp',
    'codec/TransportDirection.cpp',
    'codec/compress/GzipHeaderCodec.cpp',
    'codec/compress/HeaderTable.cpp',
    'codec/compress/HPACKCodec.cpp',
    'codec/compress/HPACKContext.cpp',
    'codec/compress/HPACKDecodeBuffer.cpp',
    'codec/compress/HPACKDecoder.cpp',
    'codec/compress/HPACKEncodeBuffer.cpp',
    'codec/compress/HPACKEncoder.cpp',
    'codec/compress/HPACKHeader.cpp',
    'codec/compress/Huffman.cpp',
    'codec/compress/Logging.cpp',
    'codec/compress/StaticHeaderTable.cpp',
    'codec/compress/experimental/hpack9/HPACKCodec.cpp',
    'codec/compress/experimental/hpack9/HPACKDecoder.cpp',
    'codec/compress/experimental/hpack9/HPACKEncoder.cpp',
    'codec/compress/experimental/hpack9/Huffman.cpp',
    'codec/compress/experimental/hpack9/StaticHeaderTable.cpp',
    'codec/experimental/HTTP2Codec.cpp',
    'codec/experimental/HTTP2Constants.cpp',
    'codec/experimental/HTTP2Framer.cpp',
    'session/ByteEvents.cpp',
    'session/ByteEventTracker.cpp',
    'session/CodecErrorResponseHandler.cpp',
    'session/HTTP2PriorityQueue.cpp',
    'session/HTTPDirectResponseHandler.cpp',
    'session/HTTPDownstreamSession.cpp',
    'session/HTTPErrorPage.cpp',
    'session/HTTPEvent.cpp',
    'session/HTTPSessionAcceptor.cpp',
    'session/HTTPSession.cpp',
    'session/HTTPTransaction.cpp',
    'session/HTTPTransactionEgressSM.cpp',
    'session/HTTPTransactionIngressSM.cpp',
    'session/HTTPUpstreamSession.cpp',
    'session/SimpleController.cpp',
    'session/TransportFilter.cpp',
  ],
  deps = [
    ':HTTPCommonHeaders_cpp',
    ':HTTPCommonHeaders_h',
    '//proxygen/lib/utils:utils',
  ]
)
