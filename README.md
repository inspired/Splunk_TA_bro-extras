# Splunk_TA_bro-extras
Extra stuff for Bro (CIM compliance for Certificate Data Model ++)

## Make this a scheduled search with collect to sourcetype bro_ssl_summary ##
index=bro (sourcetype=bro_files OR sourcetype=bro_ssl OR sourcetype=bro_x509) correlation_id!="-" correlation_id!="(empty)" | stats latest(duration) AS duration latest(response_time) AS response_time latest(src) AS src latest(src_port) AS src_port latest(dest) AS dest latest(dest_port) AS dest_port values(sourcetype) AS sourcetypes latest(transport) AS transport latest(ssl_end_time) AS ssl_end_time latest(ssl_engine) AS ssl_engine latest(ssl_hash) AS ssl_hash latest(ssl_cipher_name) AS ssl_cipher_name latest(ssl_issuer) AS ssl_issuer latest(ssl_issuer_common_name) AS ssl_issuer_common_name latest(ssl_issuer_email) AS ssl_issuer_email latest(ssl_issuer_locality) AS ssl_issuer_locality latest(ssl_issuer_organization) AS ssl_issuer_organization latest(ssl_issuer_state) AS ssl_issuer_state latest(ssl_issuer_street) AS ssl_issuer_street latest(ssl_issuer_unit) AS ssl_issuer_unit latest(ssl_name) AS ssl_name latest(ssl_policies) AS ssl_policies latest(ssl_publickey) AS ssl_publickey latest(ssl_publickey_algorithm) AS ssl_publickey_algorithm latest(ssl_serial) AS ssl_serial latest(ssl_session_id) AS ssl_session_id latest(ssl_signature_algorithm) AS ssl_signature_algorithm latest(ssl_start_time) AS ssl_start_time latest(ssl_subject) AS ssl_subject latest(ssl_subject_common_name) AS ssl_subject_common_name latest(ssl_subject_email) AS ssl_subject_email latest(ssl_subject_locality) AS ssl_subject_locality latest(ssl_subject_state) AS ssl_subject_state latest(ssl_subject_street) AS ssl_subject_street latest(ssl_subject_unit) AS ssl_subject_unit latest(ssl_version) AS ssl_version latest(version) AS version first(_time) AS _time BY correlation_id | where sourcetypes = "bro_x509"

| collect sourcetype=bro_ssl_summary marker="search_name=Splunk_TA_bro-extras_summary"

## sourcetype=bro_ssl_summary ##
As long as this is tagged with certificate and tls/ssl it should work
 
http://docs.splunk.com/Documentation/CIM/4.3.1/User/Certificates
 
Bruker data fra sourcetype=bro_files sourcetype=bro_x509 sourcetype=bro_ssl


## Examples from Stream App ##
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
