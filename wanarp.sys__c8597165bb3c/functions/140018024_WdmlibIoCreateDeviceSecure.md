# WdmlibIoCreateDeviceSecure

- ea: `0x140018024`
- end: `0x14001809c`
- name: `WdmlibIoCreateDeviceSecure`
- size: `120`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001a078`

## callees

- `0x1400050f0`
- `0x140017f98`
- `0x140018024`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, PCUNICODE_STRING, LPCGUID, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           18,
           256,
           0,
           DefaultSDDLString,
           DeviceClassGuid,
           DeviceObject);
}

```

## disassembly

```asm
0x140018024  mov     [rsp+arg_0], rbx
0x140018029  push    rdi
0x14001802a  sub     rsp, 50h
0x14001802e  cmp     cs:WdmlibInitialized, 0
0x140018035  mov     rbx, r8
0x140018038  mov     rdi, rcx
0x14001803b  jnz     short loc_140018042
0x14001803d  call    WdmlibInit
0x140018042  mov     rdx, [rsp+58h+DeviceObject]
0x14001804a  mov     r9d, 12h
0x140018050  mov     rcx, [rsp+58h+DefaultSDDLString]
0x140018058  mov     r8, rbx
0x14001805b  mov     rax, cs:PfnIoCreateDeviceSecure
0x140018062  mov     [rsp+58h+var_18], rdx
0x140018067  mov     rdx, [rsp+58h+DeviceClassGuid]
0x14001806f  mov     [rsp+58h+var_20], rdx
0x140018074  xor     edx, edx
0x140018076  mov     [rsp+58h+var_28], rcx
0x14001807b  mov     rcx, rdi
0x14001807e  mov     [rsp+58h+var_30], 0
0x140018083  mov     [rsp+58h+var_38], 100h
0x14001808b  call    _guard_dispatch_icall
0x140018090  mov     rbx, [rsp+58h+arg_0]
0x140018095  add     rsp, 50h
0x140018099  pop     rdi
0x14001809a  retn
```
