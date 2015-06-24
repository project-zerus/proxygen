gen_rule(
  name = 'trace_gen',
  srcs = [
    'gen_trace_event_constants.py',
    'TraceEventType.txt',
    'TraceFieldType.txt',
  ],
  outs = [
    'TraceEventType.cpp',
    'TraceEventType.h',
    'TraceFieldType.cpp',
    'TraceFieldType.h',
  ],
  cmd = '''python $FIRST_SRC ''' \
        '''--output_type=cpp ''' \
        '''--input_files=proxygen/lib/utils/TraceEventType.txt,proxygen/lib/utils/TraceFieldType.txt ''' \
        '''--output_scope=proxygen ''' \
        '''--header_path=proxygen/lib/utils ''' \
        '''--install_dir=$BUILD_DIR/proxygen/lib/utils ''' \
        '''--fbcode_dir=proxygen/lib/utils'''
)

cc_library(
  name = 'utils',
  warning = 'no',
  srcs = [
    'AsyncTimeoutSet.cpp',
    'ChromeUtils.cpp',
    'CryptUtil.cpp',
    'Exception.cpp',
    'HTTPTime.cpp',
    'Logging.cpp',
    'ParseURL.cpp',
    'RendezvousHash.cpp',
    'TraceEventContext.cpp',
    'TraceEvent.cpp',
    'ZlibStreamCompressor.cpp',
    'ZlibStreamDecompressor.cpp',
    'TraceEventType.cpp',
    'TraceFieldType.cpp',
  ],
  deps = [
    ':trace_gen',
    '//folly:folly',
    '//proxygen/external/http_parser:http_parser',
  ]
)
