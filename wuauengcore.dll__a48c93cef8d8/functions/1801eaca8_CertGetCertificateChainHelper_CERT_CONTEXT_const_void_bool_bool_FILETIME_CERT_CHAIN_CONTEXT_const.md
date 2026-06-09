# CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x1801eaca8`
- end: `0x1801eb056`
- name: `?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `942`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, HCERTSTORE hAdditionalStore@<rdx>, bool@<r8b>, bool@<r9b>, struct _FILETIME *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1801e99e0`
- `0x1801ea0fc`
- `0x1801ea730`

## callees

- `0x18011d064`
- `0x18012b618`
- `0x1801eaca8`
- `0x1801eb05c`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eadef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eae08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eaf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eaf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eadef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eae08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eaf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eaf5c`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801eaed1`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801eb02e`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801eaed1`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801eb02e`
- `CRYPT32!CertCloseStore` at `0x1801eae7d`
- `CRYPT32!CertCloseStore` at `0x1801eb017`
- `CRYPT32!CertCloseStore` at `0x1801eae7d`
- `CRYPT32!CertCloseStore` at `0x1801eb017`
- `CRYPT32!CertGetCertificateChain` at `0x1801eade5`
- `CRYPT32!CertGetCertificateChain` at `0x1801eaf35`
- `CRYPT32!CertGetCertificateChain` at `0x1801eade5`
- `CRYPT32!CertGetCertificateChain` at `0x1801eaf35`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaea3`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaefa`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaf7c`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eafeb`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eb005`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaea3`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaefa`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eaf7c`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eafeb`
- `CRYPT32!CertFreeCertificateChain` at `0x1801eb005`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1801eaee7`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1801eaee7`

## pseudocode

```c

```
