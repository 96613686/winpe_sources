# SetPdoRegistryParameter

- ea: `0x14002d9c4`
- end: `0x14002daa9`
- name: `SetPdoRegistryParameter`
- size: `229`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, ULONG Type)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400142c0`
- `0x140022240`
- `0x1400242a4`

## callees

- `0x14000a6cc`
- `0x14002d9c4`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002da0f`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002da0f`
- `ntoskrnl!ZwClose` at `0x14002da52`
- `ntoskrnl!ZwClose` at `0x14002da52`
- `ntoskrnl!ZwSetValueKey` at `0x14002da3f`
- `ntoskrnl!ZwSetValueKey` at `0x14002da3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d9f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d9f0`

## pseudocode

```c
__int64 __fastcall SetPdoRegistryParameter(
        PDEVICE_OBJECT DeviceObject,
        const WCHAR *a2,
        void *a3,
        ULONG a4,
        ULONG Type)
{
  int v8; // edx
  NTSTATUS v9; // ebx
  void *DeviceRegKey; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-20h] BYREF

  DeviceRegKey = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v9 = IoOpenDeviceRegistryKey(DeviceObject, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v9 >= 0 )
  {
    v9 = ZwSetValueKey(DeviceRegKey, &ValueName, 0, Type, a3, a4);
    ZwClose(DeviceRegKey);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_d(g_RecorderLog, v8, 1, 18, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002d9c4  mov     rax, rsp
0x14002d9c7  mov     [rax+8], rbx
0x14002d9cb  mov     [rax+10h], rsi
0x14002d9cf  push    rdi
0x14002d9d0  sub     rsp, 50h
0x14002d9d4  mov     rbx, rcx
0x14002d9d7  mov     qword ptr [rax-28h], 0
0x14002d9df  xorps   xmm0, xmm0
0x14002d9e2  lea     rcx, [rax-20h]; DestinationString
0x14002d9e6  movups  xmmword ptr [rax-20h], xmm0
0x14002d9ea  mov     edi, r9d
0x14002d9ed  mov     rsi, r8
0x14002d9f0  call    cs:__imp_RtlInitUnicodeString
0x14002d9f7  nop     dword ptr [rax+rax+00h]
0x14002d9fc  lea     r9, [rsp+58h+DeviceRegKey]; DeviceRegKey
0x14002da01  mov     edx, 1; DevInstKeyType
0x14002da06  mov     r8d, 1F0000h; DesiredAccess
0x14002da0c  mov     rcx, rbx; DeviceObject
0x14002da0f  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002da16  nop     dword ptr [rax+rax+00h]
0x14002da1b  mov     ebx, eax
0x14002da1d  test    eax, eax
0x14002da1f  js      short loc_14002DA5E
0x14002da21  mov     r9d, [rsp+58h+Type]; Type
0x14002da29  lea     rdx, [rsp+58h+ValueName]; ValueName
0x14002da2e  mov     rcx, [rsp+58h+DeviceRegKey]; KeyHandle
0x14002da33  xor     r8d, r8d; TitleIndex
0x14002da36  mov     [rsp+58h+DataSize], edi; DataSize
0x14002da3a  mov     [rsp+58h+Data], rsi; Data
0x14002da3f  call    cs:__imp_ZwSetValueKey
0x14002da46  nop     dword ptr [rax+rax+00h]
0x14002da4b  mov     rcx, [rsp+58h+DeviceRegKey]; Handle
0x14002da50  mov     ebx, eax
0x14002da52  call    cs:__imp_ZwClose
0x14002da59  nop     dword ptr [rax+rax+00h]
0x14002da5e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002da65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002da6c  jz      short loc_14002DA96
0x14002da6e  mov     rcx, cs:g_RecorderLog
0x14002da75  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14002da7c  mov     r9d, 12h
0x14002da82  mov     [rsp+58h+DataSize], ebx
0x14002da86  mov     dl, 4
0x14002da88  mov     [rsp+58h+Data], rax
0x14002da8d  lea     r8d, [r9-11h]
0x14002da91  call    WPP_RECORDER_SF_d
0x14002da96  mov     rsi, [rsp+58h+arg_8]
0x14002da9b  mov     eax, ebx
0x14002da9d  mov     rbx, [rsp+58h+arg_0]
0x14002daa2  add     rsp, 50h
0x14002daa6  pop     rdi
0x14002daa7  retn
```
