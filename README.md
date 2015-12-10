# Splunk_TA_bro-extras
Extra stuff for Bro (CIM compliance for Certificate Data Model ++)

## Make this a scheduled search with collect to sourcetype bro_ssl_summary ##
index=bro correlation_id!="-" correlation_id!="(empty)" | stats latest(duration) AS duration latest(response_time) AS response_time latest(src) AS src latest(src_port) AS src_port latest(dest) AS dest latest(dest_port) AS dest_port values(tag) AS tag latest(transport) AS transport latest(ssl_end_time) AS ssl_end_time latest(ssl_engine) AS ssl_engine latest(ssl_hash) AS ssl_hash latest(ssl_is_valid) AS ssl_is_valid latest(ssl_issuer) AS ssl_issuer latest(ssl_issuer_common_name) AS ssl_issuer_common_name latest(ssl_issuer_email) AS ssl_issuer_email latest(ssl_issuer_locality) AS ssl_issuer_locality latest(ssl_issuer_organization) AS ssl_issuer_organization latest(ssl_issuer_state) AS ssl_issuer_state latest(ssl_issuer_street) AS ssl_issuer_street latest(ssl_issuer_unit) AS ssl_issuer_unit latest(ssl_name) AS ssl_name latest(ssl_policies) AS ssl_policies latest(ssl_publickey) AS ssl_publickey latest(ssl_publickey_algorithm) AS ssl_publickey_algorithm latest(ssl_serial) AS ssl_serial latest(ssl_session_id) AS ssl_session_id latest(ssl_signature_algorithm) AS ssl_signature_algorithm latest(ssl_start_time) AS ssl_start_time latest(ssl_subject) AS ssl_subject latest(ssl_subject_common_name) AS ssl_subject_common_name latest(ssl_subject_email) AS ssl_subject_email latest(ssl_subject_locality) AS ssl_subject_locality latest(ssl_subject_state) AS ssl_subject_state latest(ssl_subject_street) AS ssl_subject_street latest(ssl_subject_unit) AS ssl_subject_unit latest(ssl_validity_window) AS ssl_validity_window latest(ssl_version) AS ssl_version latest(version) AS version first(_time) AS _time BY correlation_id | where isnotnull(src)

## sourcetype=bro_ssl_summary ##
As long as this is tagged with certificate and tls/ssl it should work
 
http://docs.splunk.com/Documentation/CIM/4.3.1/User/Certificates
 
Bruker data fra sourcetype=bro_files sourcetype=bro_x509 sourcetype=bro_ssl
