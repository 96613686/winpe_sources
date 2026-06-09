# CCodeDownload::GetInfSectionInfo(char *,int,char *,int,_GUID * *,ulong *,ulong *,DESTINATION_DIR *,ulong *,ulong *,int *,int *)

- ea: `0x1800c8b8c`
- end: `0x1800c8e07`
- name: `?GetInfSectionInfo@CCodeDownload@@QEAAJPEADH0HPEAPEAU_GUID@@PEAK2PEAW4DESTINATION_DIR@@22PEAH4@Z`
- size: `635`
- prototype: `__int64 __usercall@<rax>(CCodeDownload *__hidden this@<rcx>, char *@<rdx>, int@<r8d>, char *@<r9>, int, struct _GUID **, unsigned int *, unsigned int *, enum DESTINATION_DIR *, unsigned int *, unsigned int *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cbbd4`

## callees

- `0x1800a3dc0`
- `0x1800a5d70`
- `0x1800a82b8`
- `0x1800c8adc`
- `0x1800c8b8c`
- `0x1800c9248`
- `0x1800d015c`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8d0e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8cad`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8d43`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8d6a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8cad`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8d43`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x1800c8d6a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8c5b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8ce6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8da3`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8c5b`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8ce6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800c8da3`

## string_xrefs

- `0x1800c8ca0`: `CopyFlags`
- `0x1800c8d87`: `CLSID`

## pseudocode

```c

```
