# StoreUVCCacheControl

- ea: `0x14001d94c`
- end: `0x14001daba`
- name: `StoreUVCCacheControl`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006ae0`

## callees

- `0x14001ab4c`
- `0x14001d94c`
- `0x14001e1e4`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14001da37`
- `ntoskrnl!ZwSetValueKey` at `0x14001da37`
- `ntoskrnl!ZwClose` at `0x14001da4a`
- `ntoskrnl!ZwClose` at `0x14001da4a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001d9d1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001d9d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da00`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da00`

## pseudocode

```c
__int64 __fastcall StoreUVCCacheControl(__int64 a1, int a2)
{
  __int64 v2; // rsi
  __int64 v5; // rcx
  NTSTATUS v6; // ebx
  const WCHAR *v7; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  void *DeviceRegKey; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  DeviceRegKey = 0;
  if ( a1 )
  {
    v5 = *(_QWORD *)(a1 + 24);
    if ( v5 )
    {
      v6 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(v5 + 32), 1u, 0xF003Fu, &DeviceRegKey);
      if ( v6 >= 0 )
      {
        v7 = (const WCHAR *)qword_140045500[3 * v2 + 1];
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v7);
        v6 = ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, (PVOID)(a1 + 1432 + 8 * v2), 4u);
        ZwClose(DeviceRegKey);
        return (unsigned int)v6;
      }
    }
    else
    {
      v6 = -1073741811;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qDS(
        WPP_GLOBAL_Control->AttachedDevice,
        80,
        (unsigned int)WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids,
        a1,
        v6,
        qword_140045500[3 * v2 + 1]);
    return (unsigned int)v6;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, 0, -1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14001d94c  mov     [rsp+arg_8], rbx
0x14001d951  mov     [rsp+arg_10], rsi
0x14001d956  push    rdi
0x14001d957  sub     rsp, 40h
0x14001d95b  movsxd  rsi, edx
0x14001d95e  mov     rdi, rcx
0x14001d961  mov     [rsp+48h+DeviceRegKey], 0
0x14001d96a  test    rcx, rcx
0x14001d96d  jnz     short loc_14001D9B0
0x14001d96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d976  lea     rax, WPP_GLOBAL_Control
0x14001d97d  cmp     rcx, rax
0x14001d980  jz      short loc_14001D9A6
0x14001d982  cmp     byte ptr [rcx+29h], 2
0x14001d986  jb      short loc_14001D9A6
0x14001d988  mov     rcx, [rcx+18h]
0x14001d98c  lea     edx, [rdi+4Fh]
0x14001d98f  xor     r9d, r9d
0x14001d992  mov     dword ptr [rsp+48h+Data], 0C000000Dh
0x14001d99a  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001d9a1  call    WPP_SF_qD
0x14001d9a6  mov     eax, 0C000000Dh
0x14001d9ab  jmp     loc_14001DAA9
0x14001d9b0  mov     rcx, [rcx+18h]
0x14001d9b4  test    rcx, rcx
0x14001d9b7  jz      loc_14001DA58
0x14001d9bd  mov     rcx, [rcx+20h]; DeviceObject
0x14001d9c1  lea     r9, [rsp+48h+DeviceRegKey]; DeviceRegKey
0x14001d9c6  mov     edx, 1; DevInstKeyType
0x14001d9cb  mov     r8d, 0F003Fh; DesiredAccess
0x14001d9d1  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001d9d8  nop     dword ptr [rax+rax+00h]
0x14001d9dd  mov     ebx, eax
0x14001d9df  test    eax, eax
0x14001d9e1  js      short loc_14001DA5D
0x14001d9e3  lea     r8, qword_140045500
0x14001d9ea  xorps   xmm0, xmm0
0x14001d9ed  lea     rdx, [rsi+rsi*2]
0x14001d9f1  mov     rdx, [r8+rdx*8+8]; SourceString
0x14001d9f6  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001d9fb  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001da00  call    cs:__imp_RtlInitUnicodeString
0x14001da07  nop     dword ptr [rax+rax+00h]
0x14001da0c  mov     rcx, [rsp+48h+DeviceRegKey]; KeyHandle
0x14001da11  lea     rax, [rdi+598h]
0x14001da18  lea     rax, [rax+rsi*8]
0x14001da1c  mov     [rsp+48h+DataSize], 4; DataSize
0x14001da24  mov     r9d, 4; Type
0x14001da2a  mov     [rsp+48h+Data], rax; Data
0x14001da2f  xor     r8d, r8d; TitleIndex
0x14001da32  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x14001da37  call    cs:__imp_ZwSetValueKey
0x14001da3e  nop     dword ptr [rax+rax+00h]
0x14001da43  mov     rcx, [rsp+48h+DeviceRegKey]; Handle
0x14001da48  mov     ebx, eax
0x14001da4a  call    cs:__imp_ZwClose
0x14001da51  nop     dword ptr [rax+rax+00h]
0x14001da56  jmp     short loc_14001DAA7
0x14001da58  mov     ebx, 0C000000Dh
0x14001da5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da64  lea     rax, WPP_GLOBAL_Control
0x14001da6b  cmp     rcx, rax
0x14001da6e  jz      short loc_14001DAA7
0x14001da70  cmp     byte ptr [rcx+29h], 4
0x14001da74  jb      short loc_14001DAA7
0x14001da76  mov     rcx, [rcx+18h]
0x14001da7a  lea     r8, qword_140045500
0x14001da81  lea     rax, [rsi+rsi*2]
0x14001da85  mov     edx, 50h ; 'P'
0x14001da8a  mov     rax, [r8+rax*8+8]
0x14001da8f  mov     r9, rdi
0x14001da92  mov     qword ptr [rsp+48h+DataSize], rax
0x14001da97  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001da9e  mov     dword ptr [rsp+48h+Data], ebx
0x14001daa2  call    WPP_SF_qDS
0x14001daa7  mov     eax, ebx
0x14001daa9  mov     rbx, [rsp+48h+arg_8]
0x14001daae  mov     rsi, [rsp+48h+arg_10]
0x14001dab3  add     rsp, 40h
0x14001dab7  pop     rdi
0x14001dab8  retn
```
