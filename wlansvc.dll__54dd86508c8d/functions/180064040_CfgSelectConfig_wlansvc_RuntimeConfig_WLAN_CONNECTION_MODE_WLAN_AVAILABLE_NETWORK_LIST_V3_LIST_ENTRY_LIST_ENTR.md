# CfgSelectConfig(wlansvc::RuntimeConfig *,_WLAN_CONNECTION_MODE,_WLAN_AVAILABLE_NETWORK_LIST_V3 *,_LIST_ENTRY *,_LIST_ENTRY *,int,int,int,ulong,ulong)

- ea: `0x180064040`
- end: `0x180064967`
- name: `?CfgSelectConfig@@YAKPEAURuntimeConfig@wlansvc@@W4_WLAN_CONNECTION_MODE@@PEAU_WLAN_AVAILABLE_NETWORK_LIST_V3@@PEAU_LIST_ENTRY@@3HHHKK@Z`
- size: `2343`
- prototype: `unsigned int __usercall@<eax>(struct wlansvc::RuntimeConfig *@<rcx>, enum _WLAN_CONNECTION_MODE@<edx>, struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *@<r8>, struct _LIST_ENTRY *@<r9>, struct _LIST_ENTRY *, int, int, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180063c48`
- `0x180151b14`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180013630`
- `0x180017120`
- `0x1800171c0`
- `0x18003fee8`
- `0x180056c6c`
- `0x180064040`
- `0x180064970`
- `0x180064b90`
- `0x180064f70`
- `0x1800c6774`
- `0x18010730c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800642ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800642ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064332`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006431e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064347`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006431e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064347`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064888`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064888`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006459b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800648e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006459b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800648e6`

## pseudocode

```c

```
