# WFDGOGetRemoteClientIPv4Address(_WLAN_INTERFACE_CONTEXT *,uchar (*)[6],void *,void *,sockaddr_in *)

- ea: `0x1800f578c`
- end: `0x1800f5d69`
- name: `?WFDGOGetRemoteClientIPv4Address@@YAKPEAU_WLAN_INTERFACE_CONTEXT@@PEAY05EPEAX2PEAUsockaddr_in@@@Z`
- size: `1501`
- prototype: `unsigned int __usercall@<eax>(struct _WLAN_INTERFACE_CONTEXT *@<rcx>, unsigned __int8 (*)[6]@<rdx>, void *@<r8>, void *@<r9>, struct sockaddr_in *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180184a84`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800893cc`
- `0x180089478`
- `0x1800f578c`
- `0x180106340`
- `0x18019de70`
- `0x18019df3c`
- `0x1801cf770`
- `0x1801d022c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f5a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f5c89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f5a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f5c89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f58bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f5c6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f58bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f5c6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f597b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f597b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f598a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f598a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5be7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ce1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5ce1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800f5a4c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800f5a4c`

## pseudocode

```c

```
