# ReVerifyTrustEx(_CERT_CONTEXT const *,SECURITY_CACHE_LIST_ENTRY *,ulong,ulong,int,int,int)

- ea: `0x180059ec4`
- end: `0x18005a3fb`
- name: `?ReVerifyTrustEx@@YAKPEBU_CERT_CONTEXT@@PEAVSECURITY_CACHE_LIST_ENTRY@@KKHHH@Z`
- size: `1335`
- prototype: `unsigned int(const struct _CERT_CONTEXT *, struct SECURITY_CACHE_LIST_ENTRY *, unsigned int, unsigned int, int, int, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800282f8`
- `0x180059394`

## callees

- `0x180011930`
- `0x180019d20`
- `0x180058a24`
- `0x180058b04`
- `0x180059ec4`
- `0x18005a404`
- `0x18005a4c4`
- `0x18007ad20`
- `0x18008a970`
- `0x18008aaf0`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e3c78`
- `0x1801e5e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a175`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a175`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a139`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a139`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180059f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180059f53`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a14c`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a244`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a276`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a14c`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a244`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a276`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a1a7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a1a7`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a0c3`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a106`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a15e`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a0c3`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a106`
- `CRYPT32!CertDuplicateCertificateChain` at `0x18005a15e`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18005a099`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18005a099`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18005a0af`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18005a0af`

## pseudocode

```c

```
