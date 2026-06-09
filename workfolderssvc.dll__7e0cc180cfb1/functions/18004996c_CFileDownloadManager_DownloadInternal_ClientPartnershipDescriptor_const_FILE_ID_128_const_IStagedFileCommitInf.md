# CFileDownloadManager::DownloadInternal(ClientPartnershipDescriptor const &,_FILE_ID_128 const &,IStagedFileCommitInfo *,int,ISyncShareManagerProgressCallback *)

- ea: `0x18004996c`
- end: `0x18004a0e3`
- name: `?DownloadInternal@CFileDownloadManager@@AEAAJAEBVClientPartnershipDescriptor@@AEBU_FILE_ID_128@@PEAUIStagedFileCommitInfo@@HPEAUISyncShareManagerProgressCallback@@@Z`
- size: `1911`
- prototype: `__int64 __usercall@<rax>(CFileDownloadManager *__hidden this@<rcx>, const struct ClientPartnershipDescriptor *@<rdx>, const struct _FILE_ID_128 *@<r8>, struct IStagedFileCommitInfo *@<r9>, int, struct ISyncShareManagerProgressCallback *)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x18004b1b0`

## callees

- `0x180002fa4`
- `0x180003604`
- `0x18000444c`
- `0x180007e10`
- `0x180008b60`
- `0x180008b8c`
- `0x180009158`
- `0x180009774`
- `0x18000a694`
- `0x180010d38`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x180048fc0`
- `0x180049040`
- `0x1800493dc`
- `0x180049900`
- `0x18004996c`
- `0x18004a894`
- `0x18004af44`
- `0x18004af74`
- `0x18004b0d0`
- `0x18004ce68`
- `0x18004d720`
- `0x18004e4b4`
- `0x18004e630`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180049a60`
- `KERNEL32!GetTickCount64` at `0x180049a60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a0b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a0b7`

## pseudocode

```c

```
