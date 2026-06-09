# CHttpHeaders::_ReplaceHeader(ulong,char const *,ulong,char const *,ulong,ulong,ulong)

- ea: `0x18000d360`
- end: `0x18000db1d`
- name: `?_ReplaceHeader@CHttpHeaders@@AEAAKKPEBDK0KKK@Z`
- size: `1981`
- prototype: `unsigned int(CHttpHeaders *__hidden this, unsigned int, const char *, unsigned int, const char *, unsigned int, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180008560`
- `0x18000cd64`
- `0x18000cddc`
- `0x18000cea0`
- `0x180011b58`
- `0x180013dd0`
- `0x180034b40`
- `0x18008b070`
- `0x1800e6d64`
- `0x1800f1970`
- `0x180111380`
- `0x180118594`

## callees

- `0x180009cf0`
- `0x18000d360`
- `0x18000ecb0`
- `0x18000f490`
- `0x1800f20bc`
- `0x1801e1790`
- `0x1801eb7bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d3c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d3c4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000d491`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000d6e7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000d491`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000d6e7`
- `ntdll!RtlNtStatusToDosError` at `0x18000dac6`
- `ntdll!RtlNtStatusToDosError` at `0x18000daff`
- `ntdll!RtlNtStatusToDosError` at `0x18000dac6`
- `ntdll!RtlNtStatusToDosError` at `0x18000daff`

## pseudocode

```c

```
