# CINetHttp::HandleCertificateRequest(ulong)

- ea: `0x1800d9554`
- end: `0x1800d9729`
- name: `?HandleCertificateRequest@CINetHttp@@AEAAKK@Z`
- size: `469`
- prototype: `unsigned int __fastcall(CINetHttp *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d9900`

## callees

- `0x1800d5a48`
- `0x1800d9554`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d9618`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d9618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d96fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d96fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d95c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d95f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d95c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d95f4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800d970f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800d970f`
- `WININET!InternetSetOptionA` at `0x1800d96f4`
- `WININET!InternetSetOptionA` at `0x1800d96f4`
- `WININET!InternetQueryOptionA` at `0x1800d9693`
- `WININET!InternetQueryOptionA` at `0x1800d9693`

## pseudocode

```c

```
