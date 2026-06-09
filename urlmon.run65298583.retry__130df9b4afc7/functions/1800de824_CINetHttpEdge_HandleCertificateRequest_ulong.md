# CINetHttpEdge::HandleCertificateRequest(ulong)

- ea: `0x1800de824`
- end: `0x1800dea25`
- name: `?HandleCertificateRequest@CINetHttpEdge@@AEAAKK@Z`
- size: `513`
- prototype: `unsigned int __fastcall(CINetHttpEdge *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800decc0`

## callees

- `0x18000a110`
- `0x18000a270`
- `0x1800de824`
- `0x1800e12ac`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de933`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de90b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de9f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de8e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800de8e7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dea02`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dea02`
- `WININET!InternetSetOptionA` at `0x1800de9e7`
- `WININET!InternetSetOptionA` at `0x1800de9e7`
- `WININET!InternetQueryOptionA` at `0x1800de986`
- `WININET!InternetQueryOptionA` at `0x1800de986`

## pseudocode

```c

```
