# InstancePdoWritePipeInformation

- ea: `0x140029d48`
- end: `0x140029e05`
- name: `InstancePdoWritePipeInformation`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140029a90`

## callees

- `0x140017190`
- `0x140029d48`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140029deb`
- `ntoskrnl!ZwClose` at `0x140029deb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140029da2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140029da2`
- `ntoskrnl!ZwSetValueKey` at `0x140029dd8`
- `ntoskrnl!ZwSetValueKey` at `0x140029dd8`

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
0x140029d48  mov     r11, rsp
0x140029d4b  mov     [r11+8], rbx
0x140029d4f  push    rdi
0x140029d50  sub     rsp, 40h
0x140029d54  lea     rax, aUserdefined; "UserDefined"
0x140029d5b  mov     qword ptr [r11+18h], 0
0x140029d63  mov     [r11-10h], rax
0x140029d67  mov     rdi, rdx
0x140029d6a  mov     rax, cs:WdfFunctions_01033
0x140029d71  mov     rdx, rcx
0x140029d74  mov     rcx, cs:WdfDriverGlobals
0x140029d7b  mov     qword ptr [r11-18h], 180016h
0x140029d83  mov     rax, [rax+0F8h]
0x140029d8a  call    _guard_dispatch_icall
0x140029d8f  lea     r9, [rsp+48h+DeviceRegKey]; DeviceRegKey
0x140029d94  mov     edx, 1; DevInstKeyType
0x140029d99  mov     r8d, 1F0000h; DesiredAccess
0x140029d9f  mov     rcx, rax; DeviceObject
0x140029da2  call    cs:__imp_IoOpenDeviceRegistryKey
0x140029da9  nop     dword ptr [rax+rax+00h]
0x140029dae  mov     ebx, eax
0x140029db0  test    eax, eax
0x140029db2  js      short loc_140029DF7
0x140029db4  mov     rcx, [rsp+48h+DeviceRegKey]; KeyHandle
0x140029db9  lea     rax, [rdi+3Ch]
0x140029dbd  mov     [rsp+48h+DataSize], 70h ; 'p'; DataSize
0x140029dc5  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140029dca  mov     r9d, 3; Type
0x140029dd0  mov     [rsp+48h+Data], rax; Data
0x140029dd5  xor     r8d, r8d; TitleIndex
0x140029dd8  call    cs:__imp_ZwSetValueKey
0x140029ddf  nop     dword ptr [rax+rax+00h]
0x140029de4  mov     rcx, [rsp+48h+DeviceRegKey]; Handle
0x140029de9  mov     ebx, eax
0x140029deb  call    cs:__imp_ZwClose
0x140029df2  nop     dword ptr [rax+rax+00h]
0x140029df7  mov     eax, ebx
0x140029df9  mov     rbx, [rsp+48h+arg_0]
0x140029dfe  add     rsp, 40h
0x140029e02  pop     rdi
0x140029e03  retn
```
