# BuiltInCliAuthAcquireCertContexts(_SecHandle *,CERT_CONTEXT_ARRAY * *)

- ea: `0x18016d818`
- end: `0x18016db64`
- name: `?BuiltInCliAuthAcquireCertContexts@@YAKPEAU_SecHandle@@PEAPEAVCERT_CONTEXT_ARRAY@@@Z`
- size: `844`
- prototype: `unsigned int __fastcall(PCtxtHandle phContext, struct CERT_CONTEXT_ARRAY **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18016db6c`

## callees

- `0x18003e350`
- `0x18007ad20`
- `0x18008aaf0`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x18015f4bc`
- `0x180161378`
- `0x180166c8c`
- `0x18016d708`
- `0x18016d818`
- `0x1801e1790`
- `0x1801e2f30`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x18016daf7`
- `SspiCli!FreeContextBuffer` at `0x18016daf7`
- `SspiCli!QueryContextAttributesExA` at `0x18016d8d5`
- `SspiCli!QueryContextAttributesExA` at `0x18016d8d5`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18016da42`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18016da42`
- `CRYPT32!CertFindExtension` at `0x18016da16`
- `CRYPT32!CertFindExtension` at `0x18016da16`
- `CRYPT32!CertFindChainInStore` at `0x18016d9c4`
- `CRYPT32!CertFindChainInStore` at `0x18016d9c4`
- `CRYPT32!CertFreeCertificateChain` at `0x18016dabf`
- `CRYPT32!CertFreeCertificateChain` at `0x18016dabf`
- `CRYPT32!CertCloseStore` at `0x18016db13`
- `CRYPT32!CertCloseStore` at `0x18016db13`

## pseudocode

```c

```
