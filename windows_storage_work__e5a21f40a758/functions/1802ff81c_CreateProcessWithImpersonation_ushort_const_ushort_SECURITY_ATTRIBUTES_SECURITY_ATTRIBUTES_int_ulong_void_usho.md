# CreateProcessWithImpersonation(ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x1802ff81c`
- end: `0x1802ff9c9`
- name: `?CreateProcessWithImpersonation@@YAHPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `429`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpApplicationName@<rcx>, LPWSTR lpCommandLine@<rdx>, struct _SECURITY_ATTRIBUTES *@<r8>, struct _SECURITY_ATTRIBUTES *@<r9>, int, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801cf0b0`

## callees

- `0x1802ff81c`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802ff953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802ff953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ff910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ff95b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ff910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ff95b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1802ff908`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1802ff908`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802ff85b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802ff85b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802ff872`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802ff872`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1802ff992`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1802ff992`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ff947`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802ff8ad`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802ff8ad`
- `USERENV!CreateEnvironmentBlock` at `0x1802ff8c2`
- `USERENV!CreateEnvironmentBlock` at `0x1802ff8c2`
- `USERENV!DestroyEnvironmentBlock` at `0x1802ff921`
- `USERENV!DestroyEnvironmentBlock` at `0x1802ff921`

## pseudocode

```c

```
