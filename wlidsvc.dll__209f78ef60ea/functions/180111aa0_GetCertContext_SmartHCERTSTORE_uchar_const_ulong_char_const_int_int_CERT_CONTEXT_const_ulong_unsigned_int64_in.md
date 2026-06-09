# GetCertContext(SmartHCERTSTORE &,uchar const *,ulong,char const *,int,int,_CERT_CONTEXT const * *,ulong &,unsigned __int64 *,int &,int &)

- ea: `0x180111aa0`
- end: `0x180111d33`
- name: `?GetCertContext@@YAJAEAVSmartHCERTSTORE@@PEBEKPEBDHHPEAPEBU_CERT_CONTEXT@@AEAKPEA_KAEAH6@Z`
- size: `659`
- prototype: `int(struct SmartHCERTSTORE *, const unsigned __int8 *, unsigned int, const char *, int, int, const struct _CERT_CONTEXT **, unsigned int *, unsigned __int64 *, int *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800cc8a0`
- `0x1800cec54`

## callees

- `0x18000c050`
- `0x1800151c4`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x180040f70`
- `0x18009d99c`
- `0x180111aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111cb5`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180111c42`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180111c42`
- `CRYPT32!CertFindCertificateInStore` at `0x180111b76`
- `CRYPT32!CertFindCertificateInStore` at `0x180111b76`
- `CRYPTSP!CryptSetProvParam` at `0x180111cab`
- `CRYPTSP!CryptSetProvParam` at `0x180111cab`

## string_xrefs

- `0x180111b02`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111ba7`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111bf9`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111c72`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111d08`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`

## pseudocode

```c

```
