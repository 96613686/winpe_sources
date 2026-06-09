# CCodeDownload::GetInfSectionInfo(char *,int,char *,int,_GUID * *,ulong *,ulong *,DESTINATION_DIR *,ulong *,ulong *,int *,int *)

- ea: `0x1800c0840`
- end: `0x1800c0a90`
- name: `?GetInfSectionInfo@CCodeDownload@@QEAAJPEADH0HPEAPEAU_GUID@@PEAK2PEAW4DESTINATION_DIR@@22PEAH4@Z`
- size: `592`
- prototype: `__int64 __usercall@<rax>(CCodeDownload *__hidden this@<rcx>, char *@<rdx>, int@<r8d>, char *@<r9>, int, struct _GUID **, unsigned int *, unsigned int *, enum DESTINATION_DIR *, unsigned int *, unsigned int *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c3748`

## callees

- `0x18009d130`
- `0x18009ef68`
- `0x1800a14fc`
- `0x1800c079c`
- `0x1800c0840`
- `0x1800c0e98`
- `0x1800c7a14`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c09b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c09b0`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c095b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c09df`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c0a00`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c095b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c09df`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c0a00`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c090f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c098e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c0a33`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c090f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c098e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c0a33`

## string_xrefs

- `0x1800c094e`: `CopyFlags`
- `0x1800c0a17`: `CLSID`

## pseudocode

```c

```
