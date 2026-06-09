# CreateSubCAContext(wchar_t const *,void * *)

- ea: `0x1801eb270`
- end: `0x1801eb416`
- name: `?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801eb05c`

## callees

- `0x180113a10`
- `0x180113ae8`
- `0x18012b618`
- `0x1801eb270`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb397`
- `CRYPT32!CertFreeCertificateContext` at `0x1801eb3db`
- `CRYPT32!CertFreeCertificateContext` at `0x1801eb3db`
- `CRYPT32!CryptStringToBinaryW` at `0x1801eb2d7`
- `CRYPT32!CryptStringToBinaryW` at `0x1801eb32e`
- `CRYPT32!CryptStringToBinaryW` at `0x1801eb2d7`
- `CRYPT32!CryptStringToBinaryW` at `0x1801eb32e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1801eb379`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1801eb379`
- `CRYPT32!CertCreateCertificateContext` at `0x1801eb345`
- `CRYPT32!CertCreateCertificateContext` at `0x1801eb345`

## string_xrefs

- `0x1801eb3b4`: `CreateSubCAContext failed`

## pseudocode

```c

```
