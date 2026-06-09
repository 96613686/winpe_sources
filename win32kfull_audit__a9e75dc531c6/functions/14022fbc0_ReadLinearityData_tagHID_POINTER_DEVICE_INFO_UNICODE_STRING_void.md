# ReadLinearityData(tagHID_POINTER_DEVICE_INFO *,_UNICODE_STRING,void *)

- ea: `0x14022fbc0`
- end: `0x14022ffd9`
- name: `?ReadLinearityData@@YAHPEAUtagHID_POINTER_DEVICE_INFO@@U_UNICODE_STRING@@PEAX@Z`
- size: `1049`
- prototype: `__int64 __fastcall(struct tagHID_POINTER_DEVICE_INFO *, struct _UNICODE_STRING *__struct_ptr, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14022f900`

## callees

- `0x140123bb0`
- `0x14022fbc0`
- `0x14022ffe0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14022fdbb`
- `ntoskrnl!ZwClose` at `0x14022fe53`
- `ntoskrnl!ZwClose` at `0x14022ff5e`
- `ntoskrnl!ZwClose` at `0x14022fdbb`
- `ntoskrnl!ZwClose` at `0x14022fe53`
- `ntoskrnl!ZwClose` at `0x14022ff5e`
- `ntoskrnl!ZwOpenKey` at `0x14022fd81`
- `ntoskrnl!ZwOpenKey` at `0x14022fe02`
- `ntoskrnl!ZwOpenKey` at `0x14022ff0d`
- `ntoskrnl!ZwOpenKey` at `0x14022fd81`
- `ntoskrnl!ZwOpenKey` at `0x14022fe02`
- `ntoskrnl!ZwOpenKey` at `0x14022ff0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc46`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc74`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fd42`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fe79`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fece`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ff2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc46`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fc74`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fd42`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fe79`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022fece`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ff2b`
- `ntoskrnl!wcschr` at `0x14022fcc8`
- `ntoskrnl!wcschr` at `0x14022fce6`
- `ntoskrnl!wcschr` at `0x14022fcc8`
- `ntoskrnl!wcschr` at `0x14022fce6`
- `win32kbase!Win32AllocPoolZInit` at `0x14022fc1f`
- `win32kbase!Win32AllocPoolZInit` at `0x14022fd11`
- `win32kbase!Win32AllocPoolZInit` at `0x14022fc1f`
- `win32kbase!Win32AllocPoolZInit` at `0x14022fd11`
- `win32kbase!Win32FreePool` at `0x14022ff74`
- `win32kbase!Win32FreePool` at `0x14022ff8c`
- `win32kbase!Win32FreePool` at `0x14022ffa2`
- `win32kbase!Win32FreePool` at `0x14022ff74`
- `win32kbase!Win32FreePool` at `0x14022ff8c`
- `win32kbase!Win32FreePool` at `0x14022ffa2`

## string_xrefs

- `0x14022fc37`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC\LinearityData`
- `0x14022fc52`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC`
- `0x14022fec3`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC\UserLinearityData`

## pseudocode

```c

```
