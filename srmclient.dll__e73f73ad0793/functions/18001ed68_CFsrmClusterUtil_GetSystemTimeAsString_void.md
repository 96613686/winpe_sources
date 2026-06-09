# CFsrmClusterUtil::GetSystemTimeAsString(void)

- ea: `0x18001ed68`
- end: `0x18001f24b`
- name: `?GetSystemTimeAsString@CFsrmClusterUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1251`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800202b8`

## callees

- `0x180001350`
- `0x18000ebd4`
- `0x180010b24`
- `0x180010bc4`
- `0x18001ed68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x18001ef1f`
- `KERNEL32!FileTimeToSystemTime` at `0x18001ef1f`
- `KERNEL32!GetLastError` at `0x18001ee2b`
- `KERNEL32!GetLastError` at `0x18001eec2`
- `KERNEL32!GetLastError` at `0x18001ef29`
- `KERNEL32!GetLastError` at `0x18001efa3`
- `KERNEL32!GetLastError` at `0x18001f016`
- `KERNEL32!GetLastError` at `0x18001ee2b`
- `KERNEL32!GetLastError` at `0x18001eec2`
- `KERNEL32!GetLastError` at `0x18001ef29`
- `KERNEL32!GetLastError` at `0x18001efa3`
- `KERNEL32!GetLastError` at `0x18001f016`
- `KERNEL32!SystemTimeToFileTime` at `0x18001ee21`
- `KERNEL32!SystemTimeToFileTime` at `0x18001ee21`
- `KERNEL32!GetSystemTime` at `0x18001ee0c`
- `KERNEL32!GetSystemTime` at `0x18001ee0c`
- `KERNEL32!GetTimeFormatW` at `0x18001f00c`
- `KERNEL32!GetTimeFormatW` at `0x18001f00c`
- `KERNEL32!GetDateFormatW` at `0x18001ef99`
- `KERNEL32!GetDateFormatW` at `0x18001ef99`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18001eeb8`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18001eeb8`

## string_xrefs

- `0x18001eda0`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`

## pseudocode

```c

```
