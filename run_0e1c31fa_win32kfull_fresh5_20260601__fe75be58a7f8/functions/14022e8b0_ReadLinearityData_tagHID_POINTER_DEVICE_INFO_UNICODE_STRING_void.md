# ReadLinearityData(tagHID_POINTER_DEVICE_INFO *,_UNICODE_STRING,void *)

- ea: `0x14022e8b0`
- end: `0x14022ecc9`
- name: `?ReadLinearityData@@YAHPEAUtagHID_POINTER_DEVICE_INFO@@U_UNICODE_STRING@@PEAX@Z`
- size: `1049`
- prototype: `__int64 __fastcall(struct tagHID_POINTER_DEVICE_INFO *, struct _UNICODE_STRING *__struct_ptr, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14022e5f0`

## callees

- `0x14010d600`
- `0x14022e8b0`
- `0x14022ecd0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14022eaab`
- `ntoskrnl!ZwClose` at `0x14022eb43`
- `ntoskrnl!ZwClose` at `0x14022ec4e`
- `ntoskrnl!ZwClose` at `0x14022eaab`
- `ntoskrnl!ZwClose` at `0x14022eb43`
- `ntoskrnl!ZwClose` at `0x14022ec4e`
- `ntoskrnl!ZwOpenKey` at `0x14022ea71`
- `ntoskrnl!ZwOpenKey` at `0x14022eaf2`
- `ntoskrnl!ZwOpenKey` at `0x14022ebfd`
- `ntoskrnl!ZwOpenKey` at `0x14022ea71`
- `ntoskrnl!ZwOpenKey` at `0x14022eaf2`
- `ntoskrnl!ZwOpenKey` at `0x14022ebfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e936`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e94d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e964`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ea32`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022eb69`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ebbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ec1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e936`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e94d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022e964`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ea32`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022eb69`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ebbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14022ec1b`
- `ntoskrnl!wcschr` at `0x14022e9b8`
- `ntoskrnl!wcschr` at `0x14022e9d6`
- `ntoskrnl!wcschr` at `0x14022e9b8`
- `ntoskrnl!wcschr` at `0x14022e9d6`
- `win32kbase!Win32AllocPoolZInit` at `0x14022e90f`
- `win32kbase!Win32AllocPoolZInit` at `0x14022ea01`
- `win32kbase!Win32AllocPoolZInit` at `0x14022e90f`
- `win32kbase!Win32AllocPoolZInit` at `0x14022ea01`
- `win32kbase!Win32FreePool` at `0x14022ec64`
- `win32kbase!Win32FreePool` at `0x14022ec7c`
- `win32kbase!Win32FreePool` at `0x14022ec92`
- `win32kbase!Win32FreePool` at `0x14022ec64`
- `win32kbase!Win32FreePool` at `0x14022ec7c`
- `win32kbase!Win32FreePool` at `0x14022ec92`

## string_xrefs

- `0x14022e927`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC\LinearityData`
- `0x14022e942`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC`
- `0x14022ebb3`: `\Registry\Machine\System\CurrentControlSet\Control\TabletPC\UserLinearityData`

## pseudocode

```c

```
