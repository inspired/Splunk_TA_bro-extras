# Splunk_TA_bro-extras
Features listed below:

## CIM compliance for Certificate Data Model
This makes SSL data from Bro work the same way as SSL data collected by Stream
http://docs.splunk.com/Documentation/CIM/4.3.1/User/Certificates

It contains a scheduled search that adds correlated events to a summary index (index=summary search_name="Summary - Bro IDS SSL")

## CIM Compliance for Network Resolution (DNS) Data Model
This makes DNS data from Bro work the same way as DNS data collected by Stream or DNS server logs
http://docs.splunk.com/Documentation/CIM/latest/User/NetworkResolutionDNS

TODO in props.conf and transforms.conf


## Examples from Stream App (REMOVE THIS) ##
    bytes_in:  1638 
    bytes_out:  2925 
    count:  1 
    dest_ip:  172.24.201.35 
    dest_port:  8089 
    endtime:  2015-12-10T10:52:31.062802Z 
    psrsvd_ss_bytes_in:  2683044 
    psrsvd_ss_bytes_out:  8555625 
    psrsvd_ss_time_taken:  2491906561 
    src_ip:  172.24.151.151 
    src_port:  64596 
    ssl_cert_md5:  1CB7A180D569E1E1A80C69AB68091A91 
    ssl_cert_sha1:  1021A5A3DC580772FE95E02A4E290991CDB8EF4C 
    ssl_cert_sha256:  DB1B6EEEE12509400178FE1B481FC8BD3343DD559F36B5886283BA97FE8C3013 
    ssl_cipher_id:  53 
    ssl_cipher_name:  TLS_RSA_WITH_AES_256_CBC_SHA 
    ssl_issuer:  C = US, ST = CA, L = San Francisco, O = Splunk, CN = SplunkCommonCA, emailAddress = support@splunk.com 
    ssl_publickey_algorithm:  rsaEncryption 
    ssl_publickey_bit_len:  1024 
    ssl_serialnumber:  11340258854711084181 
    ssl_session_id:  AC2505D76B41E1DA392F66A1E366ACE97ADA177906FB76377DC779C42702FF63 
    ssl_signature_algorithm:  sha1WithRSAEncryption 
    ssl_subject:  CN = SplunkServerDefaultCert, O = SplunkUser 
    ssl_time:  0 
    ssl_validity_end:  Apr 24 09:12:30 2016 GMT 
    ssl_validity_start:  Apr 25 09:12:30 2013 GMT 
    ssl_version:  3.0 
    time_taken:  49919 
    timestamp:  2015-12-10T10:52:31.062802Z 
