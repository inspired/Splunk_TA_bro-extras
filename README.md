# Splunk_TA_bro-extras
Features listed below:

## CIM compliance for Certificate Data Model
http://docs.splunk.com/Documentation/CIM/4.3.1/User/Certificates

This makes SSL data from Bro work the same way as SSL data collected by Stream

It contains a scheduled search that adds correlated events to a summary index (index=summary search_name="Summary - Bro IDS SSL")

## CIM Compliance for Network Resolution (DNS) Data Model
http://docs.splunk.com/Documentation/CIM/4.3.1/User/NetworkResolutionDNS

This makes DNS data from Bro work the same way as DNS data collected by Stream or DNS server logs
