# CAdminBrokerCall<AsyncIeAxiInstaller,&_GUID const IID_AsyncIeAxiInstaller,&_GUID const CLSID_CIeAxiInstaller,&_GUID const IID_IeAxiInstaller>::GetCurrentDesktop(ushort * *)

- ea: `0x1800c8970`
- end: `0x1800c8ad6`
- name: `?GetCurrentDesktop@?$CAdminBrokerCall@UAsyncIeAxiInstaller@@$1?IID_AsyncIeAxiInstaller@@3U_GUID@@B$1?CLSID_CIeAxiInstaller@@3U3@B$1?IID_IeAxiInstaller@@3U3@B@@QEAAKPEAPEAG@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800c7140`

## callees

- `0x1800c8970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c89b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c89b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8a5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c8ab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c8ab4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c89e4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a06`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a4e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a9a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c89e4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a06`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a4e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800c8a9a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800c89bf`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800c89bf`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x1800c89a2`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x1800c89a2`

## pseudocode

```c

```
