# Revocation Entries

This file contains revocation entries that is to be added or removed from the new CRL. The settings file is in
TOML format.

````toml
# Revocation entries to add in the CRL. If no entries to add, then it must be absent
[ADD_REVOCATION_ENTRIES]
entries = [
    # Serial number in hex format
    # Revocation date in UTC format e.g. 2022-04-04 13:19:01
    # Standard RFC 5280 revocation reasons
    {serial_number = "123",revocation_date = "2022-04-04 13:19:01",revocation_reason = "unspecified"},
    {serial_number = "456",revocation_date = "2022-04-04 13:19:01",revocation_reason = "unspecified"},
    {serial_number = "789",revocation_date = "2022-04-04 13:19:01",revocation_reason = "keyCompromise"}
]

# Revocation entries to remove from the CRL. If no entries to remove, then it must be absent
[REMOVE_REVOCATION_ENTRIES]
# Array to serial numbers in hex format to remove from CRL
entries = [
	"123", "456"
]
````


