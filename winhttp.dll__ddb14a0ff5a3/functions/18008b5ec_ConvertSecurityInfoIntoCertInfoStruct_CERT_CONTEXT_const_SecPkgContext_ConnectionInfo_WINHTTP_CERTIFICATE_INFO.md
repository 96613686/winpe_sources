# ConvertSecurityInfoIntoCertInfoStruct(_CERT_CONTEXT const *,_SecPkgContext_ConnectionInfo *,_WINHTTP_CERTIFICATE_INFO *,ulong *)

- ea: `0x18008b5ec`
- end: `0x18008b763`
- name: `?ConvertSecurityInfoIntoCertInfoStruct@@YAKPEBU_CERT_CONTEXT@@PEAU_SecPkgContext_ConnectionInfo@@PEAU_WINHTTP_CERTIFICATE_INFO@@PEAK@Z`
- size: `375`
- prototype: `unsigned int(const struct _CERT_CONTEXT *, struct _SecPkgContext_ConnectionInfo *, struct _WINHTTP_CERTIFICATE_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b4e84`

## callees

- `0x18008b5ec`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b675`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b6d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b675`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b6d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b6f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b706`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b6f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b706`
- `CRYPT32!CertNameToStrW` at `0x18008b65f`
- `CRYPT32!CertNameToStrW` at `0x18008b69c`
- `CRYPT32!CertNameToStrW` at `0x18008b6bc`
- `CRYPT32!CertNameToStrW` at `0x18008b72b`
- `CRYPT32!CertNameToStrW` at `0x18008b65f`
- `CRYPT32!CertNameToStrW` at `0x18008b69c`
- `CRYPT32!CertNameToStrW` at `0x18008b6bc`
- `CRYPT32!CertNameToStrW` at `0x18008b72b`

## pseudocode

```c

```
