# WlidsvcUtil::DeleteAllCertificatesFromCertStore(void *)

- ea: `0x1800f3790`
- end: `0x1800f384c`
- name: `?DeleteAllCertificatesFromCertStore@WlidsvcUtil@@SAJPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004ae40`

## callees

- `0x18000c050`
- `0x1800f3790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f37bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f37e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f37bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f37e2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800f3801`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800f3801`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800f37d8`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800f37d8`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800f37ae`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800f37ae`

## string_xrefs

- `0x1800f3835`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\wlidsvcutil.cpp`
- `0x1800f3829`: `WlidsvcUtil::DeleteAllCertificatesFromCertStore`

## pseudocode

```c

```
