# InstancePdoWritePipeInformation

- ea: `0x140029d98`
- end: `0x140029e55`
- name: `InstancePdoWritePipeInformation`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140029ae0`

## callees

- `0x140017190`
- `0x140029d98`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140029e3b`
- `ntoskrnl!ZwClose` at `0x140029e3b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140029df2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140029df2`
- `ntoskrnl!ZwSetValueKey` at `0x140029e28`
- `ntoskrnl!ZwSetValueKey` at `0x140029e28`

## pseudocode

```c
__int64 __fastcall InstancePdoWritePipeInformation(__int64 a1, __int64 a2)
{
  struct _DEVICE_OBJECT *v3; // rax
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  void *DeviceRegKey; // [rsp+60h] [rbp+18h] BYREF

  DeviceRegKey = 0;
  ValueName.Buffer = L"UserDefined";
  *(_QWORD *)&ValueName.Length = 1572886;
  v3 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 248))(
                                  WdfDriverGlobals,
                                  a1);
  v4 = IoOpenDeviceRegistryKey(v3, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v4 >= 0 )
  {
    v4 = ZwSetValueKey(DeviceRegKey, &ValueName, 0, 3u, (PVOID)(a2 + 60), 0x70u);
    ZwClose(DeviceRegKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140029d98  mov     r11, rsp
0x140029d9b  mov     [r11+8], rbx
0x140029d9f  push    rdi
0x140029da0  sub     rsp, 40h
0x140029da4  lea     rax, aUserdefined; "UserDefined"
0x140029dab  mov     qword ptr [r11+18h], 0
0x140029db3  mov     [r11-10h], rax
0x140029db7  mov     rdi, rdx
0x140029dba  mov     rax, cs:WdfFunctions_01033
0x140029dc1  mov     rdx, rcx
0x140029dc4  mov     rcx, cs:WdfDriverGlobals
0x140029dcb  mov     qword ptr [r11-18h], 180016h
0x140029dd3  mov     rax, [rax+0F8h]
0x140029dda  call    _guard_dispatch_icall
0x140029ddf  lea     r9, [rsp+48h+DeviceRegKey]; DeviceRegKey
0x140029de4  mov     edx, 1; DevInstKeyType
0x140029de9  mov     r8d, 1F0000h; DesiredAccess
0x140029def  mov     rcx, rax; DeviceObject
0x140029df2  call    cs:__imp_IoOpenDeviceRegistryKey
0x140029df9  nop     dword ptr [rax+rax+00h]
0x140029dfe  mov     ebx, eax
0x140029e00  test    eax, eax
0x140029e02  js      short loc_140029E47
0x140029e04  mov     rcx, [rsp+48h+DeviceRegKey]; KeyHandle
0x140029e09  lea     rax, [rdi+3Ch]
0x140029e0d  mov     [rsp+48h+DataSize], 70h ; 'p'; DataSize
0x140029e15  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140029e1a  mov     r9d, 3; Type
0x140029e20  mov     [rsp+48h+Data], rax; Data
0x140029e25  xor     r8d, r8d; TitleIndex
0x140029e28  call    cs:__imp_ZwSetValueKey
0x140029e2f  nop     dword ptr [rax+rax+00h]
0x140029e34  mov     rcx, [rsp+48h+DeviceRegKey]; Handle
0x140029e39  mov     ebx, eax
0x140029e3b  call    cs:__imp_ZwClose
0x140029e42  nop     dword ptr [rax+rax+00h]
0x140029e47  mov     eax, ebx
0x140029e49  mov     rbx, [rsp+48h+arg_0]
0x140029e4e  add     rsp, 40h
0x140029e52  pop     rdi
0x140029e53  retn
```
