# AddCertContextToStore(ushort const *,ulong,_CERT_CONTEXT const *)

- ea: `0x18003fa88`
- end: `0x18003fb19`
- name: `?AddCertContextToStore@@YAJPEBGKPEBU_CERT_CONTEXT@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(const unsigned __int16 *pvPara, unsigned int, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800402cc`

## callees

- `0x18003fa88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fae8`
- `CRYPT32!CertCloseStore` at `0x18003fb06`
- `CRYPT32!CertCloseStore` at `0x18003fb06`
- `CRYPT32!CertOpenStore` at `0x18003faac`
- `CRYPT32!CertOpenStore` at `0x18003faac`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003fade`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003fade`

## pseudocode

```c

```
