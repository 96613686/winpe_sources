# UsbVideoDeviceStoreRegistry

- ea: `0x14001334c`
- end: `0x140013468`
- name: `UsbVideoDeviceStoreRegistry`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140026c30`
- `0x1400547fc`

## callees

- `0x14001334c`
- `0x14001e1e4`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400133da`
- `ntoskrnl!ZwSetValueKey` at `0x1400133da`
- `ntoskrnl!ZwClose` at `0x1400133ed`
- `ntoskrnl!ZwClose` at `0x1400133ed`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140013388`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140013388`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400133ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400133ae`

## pseudocode

```c
__int64 __fastcall UsbVideoDeviceStoreRegistry(__int64 a1, const WCHAR *a2, __int64 a3, void *a4)
{
  int v4; // edi
  __int64 v5; // rcx
  NTSTATUS v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  int v10; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  void *DeviceRegKey; // [rsp+70h] [rbp+8h] BYREF

  v4 = a1;
  DeviceRegKey = 0;
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
  {
    v8 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(v5 + 32), 1u, 0xF003Fu, &DeviceRegKey);
    if ( v8 >= 0 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, a2);
      v8 = ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, a4, 4u);
      ZwClose(DeviceRegKey);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v10 = 63;
LABEL_11:
          WPP_SF_qDS(
            v9->AttachedDevice,
            v10,
            (unsigned int)WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids,
            v4,
            v8,
            (__int64)a2);
          return (unsigned int)v8;
        }
      }
      return (unsigned int)v8;
    }
  }
  else
  {
    v8 = -1073741811;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v10 = 64;
    goto LABEL_11;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001334c  push    rbx
0x14001334e  push    rbp
0x14001334f  push    rsi
0x140013350  push    rdi
0x140013351  sub     rsp, 48h
0x140013355  mov     rdi, rcx
0x140013358  mov     [rsp+68h+DeviceRegKey], 0
0x140013361  mov     rcx, [rcx+18h]
0x140013365  mov     rbp, r9
0x140013368  mov     rsi, rdx
0x14001336b  test    rcx, rcx
0x14001336e  jz      loc_14001341D
0x140013374  mov     rcx, [rcx+20h]; DeviceObject
0x140013378  lea     r9, [rsp+68h+DeviceRegKey]; DeviceRegKey
0x14001337d  mov     edx, 1; DevInstKeyType
0x140013382  mov     r8d, 0F003Fh; DesiredAccess
0x140013388  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001338f  nop     dword ptr [rax+rax+00h]
0x140013394  mov     ebx, eax
0x140013396  test    eax, eax
0x140013398  js      loc_140013422
0x14001339e  xorps   xmm0, xmm0
0x1400133a1  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400133a6  mov     rdx, rsi; SourceString
0x1400133a9  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400133ae  call    cs:__imp_RtlInitUnicodeString
0x1400133b5  nop     dword ptr [rax+rax+00h]
0x1400133ba  mov     rcx, [rsp+68h+DeviceRegKey]; KeyHandle
0x1400133bf  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1400133c4  mov     r9d, 4; Type
0x1400133ca  mov     [rsp+68h+DataSize], 4; DataSize
0x1400133d2  xor     r8d, r8d; TitleIndex
0x1400133d5  mov     [rsp+68h+Data], rbp; Data
0x1400133da  call    cs:__imp_ZwSetValueKey
0x1400133e1  nop     dword ptr [rax+rax+00h]
0x1400133e6  mov     rcx, [rsp+68h+DeviceRegKey]; Handle
0x1400133eb  mov     ebx, eax
0x1400133ed  call    cs:__imp_ZwClose
0x1400133f4  nop     dword ptr [rax+rax+00h]
0x1400133f9  test    ebx, ebx
0x1400133fb  jns     short loc_14001345C
0x1400133fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140013404  lea     rax, WPP_GLOBAL_Control
0x14001340b  cmp     rcx, rax
0x14001340e  jz      short loc_14001345C
0x140013410  cmp     byte ptr [rcx+29h], 4
0x140013414  jb      short loc_14001345C
0x140013416  mov     edx, 3Fh ; '?'
0x14001341b  jmp     short loc_140013440
0x14001341d  mov     ebx, 0C000000Dh
0x140013422  mov     rcx, cs:WPP_GLOBAL_Control
0x140013429  lea     rax, WPP_GLOBAL_Control
0x140013430  cmp     rcx, rax
0x140013433  jz      short loc_14001345C
0x140013435  cmp     byte ptr [rcx+29h], 4
0x140013439  jb      short loc_14001345C
0x14001343b  mov     edx, 40h ; '@'
0x140013440  mov     rcx, [rcx+18h]
0x140013444  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001344b  mov     qword ptr [rsp+68h+DataSize], rsi
0x140013450  mov     r9, rdi
0x140013453  mov     dword ptr [rsp+68h+Data], ebx
0x140013457  call    WPP_SF_qDS
0x14001345c  mov     eax, ebx
0x14001345e  add     rsp, 48h
0x140013462  pop     rdi
0x140013463  pop     rsi
0x140013464  pop     rbp
0x140013465  pop     rbx
0x140013466  retn
```
