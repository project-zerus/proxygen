licenses(["notice"])

cc_test(
  name = 'HTTPServerTest',
  srcs = ['HTTPServerTest.cpp'],
  data = [
    'certs/ca_cert.pem',
    'certs/ca_key.pem',
    'certs/test_cert1.pem',
    'certs/test_cert2.pem',
    'certs/test_cert3.pem',
    'certs/test_cert4.pem',
    'certs/test_cert5.pem',
    'certs/test_ecdsa_cert1.pem',
    'certs/test_ecdsa_cert2.pem',
    'certs/test_ecdsa_cert3.pem',
    'certs/test_ecdsa_key1.pem',
    'certs/test_ecdsa_key2.pem',
    'certs/test_ecdsa_key3.pem',
    'certs/test_key1.pem',
    'certs/test_key2.pem',
    'certs/test_key3.pem',
    'certs/test_key4.pem',
    'certs/test_key5.pem',
  ],
  deps = ['//proxygen/proxygen/lib/test:test_main']
)
