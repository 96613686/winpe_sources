# CTSCryptUtils::UnSerializeCertificate(uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x180042a60`
- end: `0x180042c73`
- name: `?UnSerializeCertificate@CTSCryptUtils@@SAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(BYTE *pbElement, DWORD cbElement, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180042630`

## callees

- `0x180002130`
- `0x180042a60`
- `0x18004301c`
- `0x180043070`
- `0x1800430f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b55`
- `CRYPT32!CertFreeCertificateContext` at `0x180042c5a`
- `CRYPT32!CertFreeCertificateContext` at `0x180042c5a`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180042b47`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180042b47`

## string_xrefs

- `0x180042b8e`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
