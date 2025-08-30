# NGEN Networks, LLC — Geofeed

This repository provides the official **IP geolocation data feed** for NGEN Networks, LLC (**NNL-33; AS54721**). This "geofeed" is a simple, standards-based CSV file containing geolocation data for IP prefixes held by NGEN Networks, LLC.

## What is a Geofeed?

A geofeed is a plain-text comma-separated values (CSV) file mapping IP address prefixes to geographic locations. It enables geolocation providers to improve location accuracy and enables resource holders to publish authoritative location info for their networks. This helps end-users, online businesses, and internet infrastructure operators reduce errors in IP address origin identification.[1][2][3]

## Format

Our geofeed follows [RFC 8805](https://datatracker.ietf.org/doc/rfc8805/), [RFC 9092](https://datatracker.ietf.org/doc/rfc9092/), and is UTF-8 encoded. Each non-comment line contains up to five fields:

```
ip_prefix,country_code,region_code,city,postal_code
```
- **ip_prefix**: IPv4 or IPv6 network in CIDR notation (e.g., `192.0.2.0/25`)
- **country_code**: Two-letter [ISO 3166-1 alpha-2](https://www.iso.org/iso-3166-country-codes.html) country code (e.g., `US`)
- **region_code**: [ISO 3166-2](https://www.iso.org/iso-3166-2.html) country-region code (e.g., `US-FL`)
- **city**: City name (preferred in plain Latin characters)
- **postal_code**: Optional postal/ZIP code

Lines starting with `#` are comments and ignored by automated consumers.[2][3][1]

### Example

```
# prefix,country,region,city,postal
23.163.129.0/27,US,US-FL,Miami,
23.163.128.0/27,US,US-WA,Seattle,
2602:fef4:300::/48,US,US-WA,Seattle,
2602:fef4:400::/48,US,US-FL,Miami,
```

## Usage

Geolocation providers and other users may download and parse this file for improved accuracy. For best results, this CSV should be fetched via HTTPS and referenced from NGEN Networks' public Whois/RIR objects under the `remarks` or `geofeed` attribute per [RFC 9092].[4][5][6]

- **This geofeed file is authoritative for IP space allocated to NGEN Networks, LLC (AS54721).**
- Consumers must ignore addresses not covered by an authenticated Whois object with a corresponding geofeed reference.

## License

This file is provided for public use to improve the geolocation of NGEN Networks' address space. No warranty is expressed or implied. Redistribution is permitted with attribution.

## Resources

- [RFC 8805: A Format for Self-published IP Geolocation Feeds](https://datatracker.ietf.org/doc/html/rfc8805)
- [RFC 9092: Finding and Using Geofeed Data](https://datatracker.ietf.org/doc/html/rfc9092)
- Learn more: [Official PeeringDB for AS54721](https://www.peeringdb.com/asn/54721)

## Contact

For corrections or questions about this feed, contact:  
- **NOC**: noc@ngennetworks.com  
- **Peering**: peering@ngennetworks.com
