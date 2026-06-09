# InitMTSPlatformSupport(void)

- ea: `0x18001c358`
- end: `0x18001c440`
- name: `?InitMTSPlatformSupport@@YAJXZ`
- size: `232`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c590`
- `0x18001c5d8`
- `0x18001c61c`
- `0x18001c6f8`
- `0x18001c730`

## callees

- `0x18001c358`
- `0x18001c440`
- `0x18004a740`
- `0x18004d3c4`
- `0x18004d474`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001c3be`
- `KERNEL32!GetProcAddress` at `0x18001c3d7`
- `KERNEL32!GetProcAddress` at `0x18001c3f0`
- `KERNEL32!GetProcAddress` at `0x18001c409`
- `KERNEL32!GetProcAddress` at `0x18001c3be`
- `KERNEL32!GetProcAddress` at `0x18001c3d7`
- `KERNEL32!GetProcAddress` at `0x18001c3f0`
- `KERNEL32!GetProcAddress` at `0x18001c409`

## string_xrefs

- `0x18001c3a0`: `COMSVCS.DLL`
- `0x18001c3c9`: `MTSCreateActivity`
- `0x18001c3e2`: `CoEnterServiceDomain`
- `0x18001c3fb`: `CoLeaveServiceDomain`

## pseudocode

```c

```
