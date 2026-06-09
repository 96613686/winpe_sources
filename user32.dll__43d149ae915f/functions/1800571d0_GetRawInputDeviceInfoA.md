# GetRawInputDeviceInfoA

- ea: `0x1800571d0`
- end: `0x180057305`
- name: `GetRawInputDeviceInfoA`
- size: `309`
- prototype: `UINT __stdcall(HANDLE hDevice, UINT uiCommand, LPVOID pData, PUINT pcbSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800571d0`

## import_xrefs

- `win32u!NtUserGetRawInputDeviceInfo` at `0x1800571ea`
- `win32u!NtUserGetRawInputDeviceInfo` at `0x18005724d`
- `win32u!NtUserGetRawInputDeviceInfo` at `0x180057278`
- `win32u!NtUserGetRawInputDeviceInfo` at `0x1800571ea`
- `win32u!NtUserGetRawInputDeviceInfo` at `0x18005724d`
- `win32u!NtUserGetRawInputDeviceInfo` at `0x180057278`
- `ntdll!RtlSetLastWin32Error` at `0x180057235`
- `ntdll!RtlSetLastWin32Error` at `0x180057235`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800572cf`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800572cf`
- `ntdll!RtlFreeHeap` at `0x1800572af`
- `ntdll!RtlFreeHeap` at `0x1800572af`
- `ntdll!RtlAllocateHeap` at `0x180057224`
- `ntdll!RtlAllocateHeap` at `0x180057224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572f0`

## pseudocode

```c

```
