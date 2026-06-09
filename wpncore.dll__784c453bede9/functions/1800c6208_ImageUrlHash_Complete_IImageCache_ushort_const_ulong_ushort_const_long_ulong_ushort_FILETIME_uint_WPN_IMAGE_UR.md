# ImageUrlHash::Complete(IImageCache *,ushort const *,ulong,ushort const *,long,ulong,ushort *,_FILETIME *,uint *,WPN_IMAGE_URL_REQUEST_REFERENCE * *)

- ea: `0x1800c6208`
- end: `0x1800c649c`
- name: `?Complete@ImageUrlHash@@QEAAXPEAVIImageCache@@PEBGK1JKPEAGPEAU_FILETIME@@PEAIPEAPEAUWPN_IMAGE_URL_REQUEST_REFERENCE@@@Z`
- size: `660`
- prototype: `void __fastcall(ImageUrlHash *__hidden this, struct IImageCache *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, int, unsigned int, unsigned __int16 *, struct _FILETIME *, unsigned int *, struct WPN_IMAGE_URL_REQUEST_REFERENCE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c71b0`

## callees

- `0x18002ee38`
- `0x18007fd64`
- `0x1800a0b2c`
- `0x1800a6a44`
- `0x1800af0a4`
- `0x1800c6208`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c62f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c62f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c639d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c647e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c639d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c647e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c62cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c62cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c63cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c63cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c63be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c645e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c63be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c645e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c646c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c646c`

## pseudocode

```c

```
