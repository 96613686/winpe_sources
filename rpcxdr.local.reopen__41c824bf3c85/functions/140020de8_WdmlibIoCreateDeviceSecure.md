# WdmlibIoCreateDeviceSecure

- ea: `0x140020de8`
- end: `0x140020e5e`
- name: `WdmlibIoCreateDeviceSecure`
- size: `118`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140024b80`

## callees

- `0x140015680`
- `0x140020d5c`
- `0x140020de8`

## pseudocode

```c
NTSTATUS __stdcall WdmlibIoCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        ULONG DeviceExtensionSize,
        PUNICODE_STRING DeviceName,
        ULONG DeviceType,
        ULONG DeviceCharacteristics,
        BOOLEAN Exclusive,
        PCUNICODE_STRING DefaultSDDLString,
        LPCGUID DeviceClassGuid,
        PDEVICE_OBJECT *DeviceObject)
{
  if ( !WdmlibInitialized )
    WdmlibInit();
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, struct _UNICODE_STRING *, __int64, int, _BYTE, const wchar_t *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           DeviceExtensionSize,
           &::DeviceName,
           33,
           256,
           0,
           L"VX",
           0,
           DeviceObject);
}

```

## disassembly

```asm
0x140020de8  mov     [rsp+arg_0], rbx
0x140020ded  push    rdi
0x140020dee  sub     rsp, 50h
0x140020df2  cmp     cs:WdmlibInitialized, 0
0x140020df9  mov     ebx, edx
0x140020dfb  mov     rdi, rcx
0x140020dfe  jnz     short loc_140020E05
0x140020e00  call    WdmlibInit
0x140020e05  mov     r8, [rsp+58h+DeviceObject]
0x140020e0d  lea     rcx, NFS_SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R; "VX"
0x140020e14  mov     rax, cs:PfnIoCreateDeviceSecure
0x140020e1b  mov     r9d, 21h ; '!'
0x140020e21  mov     [rsp+58h+var_18], r8
0x140020e26  mov     edx, ebx
0x140020e28  mov     [rsp+58h+var_20], 0
0x140020e31  lea     r8, DeviceName
0x140020e38  mov     [rsp+58h+var_28], rcx
0x140020e3d  mov     rcx, rdi
0x140020e40  mov     [rsp+58h+var_30], 0
0x140020e45  mov     [rsp+58h+var_38], 100h
0x140020e4d  call    _guard_dispatch_icall
0x140020e52  mov     rbx, [rsp+58h+arg_0]
0x140020e57  add     rsp, 50h
0x140020e5b  pop     rdi
0x140020e5c  retn
```
