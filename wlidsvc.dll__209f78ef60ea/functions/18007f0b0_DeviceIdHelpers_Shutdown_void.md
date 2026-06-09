# DeviceIdHelpers::Shutdown(void)

- ea: `0x18007f0b0`
- end: `0x18007f164`
- name: `?Shutdown@DeviceIdHelpers@@SAJXZ`
- size: `180`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ee98`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18007f0b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f0d7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007f0d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f12a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f12a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f0bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f0bd`

## string_xrefs

- `0x18007f150`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers.cpp`
- `0x18007f0f6`: `::FreeLibrary(m_hXmlLite) failed with hr = %x`
- `0x18007f107`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\deviceidstore.h`

## pseudocode

```c

```
