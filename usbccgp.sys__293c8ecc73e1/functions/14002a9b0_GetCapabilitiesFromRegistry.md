# GetCapabilitiesFromRegistry

- ea: `0x14002a9b0`
- end: `0x14002ab65`
- name: `GetCapabilitiesFromRegistry`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14002a2e0`

## callees

- `0x14000a6cc`
- `0x140014e00`
- `0x14002a9b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002aa43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aa43`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002a9ed`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002a9ed`
- `ntoskrnl!ZwQueryValueKey` at `0x14002aadd`
- `ntoskrnl!ZwQueryValueKey` at `0x14002aadd`
- `ntoskrnl!ZwClose` at `0x14002aa54`
- `ntoskrnl!ZwClose` at `0x14002aa54`
- `ntoskrnl!ExAllocatePool2` at `0x14002aaaa`
- `ntoskrnl!ExAllocatePool2` at `0x14002aaaa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002aa8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002aa8c`

## pseudocode

```c
__int64 __fastcall GetCapabilitiesFromRegistry(__int64 a1)
{
  void *v1; // rsi
  int v3; // edx
  NTSTATUS v4; // ebx
  _DWORD *Pool2; // rdi
  NTSTATUS v7; // eax
  unsigned int v8; // eax
  int v9; // esi
  int v10; // ebp
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF
  void *DeviceRegKey; // [rsp+78h] [rbp+10h] BYREF

  v1 = (void *)(a1 + 1224);
  DeviceRegKey = 0;
  *(_DWORD *)(a1 + 1224) = 0;
  v4 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 24), 1u, 0x1F0000u, &DeviceRegKey);
  if ( v4 < 0 )
    goto LABEL_2;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"UsbccgpCapabilities");
  Pool2 = (_DWORD *)ExAllocatePool2(256, 16, 1130525525);
  if ( Pool2 )
  {
    v7 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, Pool2, 0x10u, &ResultLength);
    v4 = 0;
    if ( v7 != -2147483643 )
      v4 = v7;
    if ( v4 < 0 )
    {
      v9 = 0;
      v10 = 0;
    }
    else
    {
      if ( v1 )
      {
        v8 = Pool2[2];
        if ( v8 > 4 )
          v8 = 4;
        memmove(v1, Pool2 + 3, v8);
      }
      v9 = Pool2[1];
      v10 = Pool2[2];
    }
    ExFreePoolWithTag(Pool2, 0x43627355u);
  }
  else
  {
    v9 = 0;
    v4 = -1073741670;
    v10 = 0;
  }
  ZwClose(DeviceRegKey);
  if ( v4 < 0 || v9 != 4 || v10 != 4 )
  {
LABEL_2:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 4;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v3, 1, 11, (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids, v4);
    }
    *(_DWORD *)(a1 + 1224) = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002a9b0  mov     [rsp+arg_10], rbx
0x14002a9b5  push    rbp
0x14002a9b6  push    rsi
0x14002a9b7  push    rdi
0x14002a9b8  push    r12
0x14002a9ba  push    r14
0x14002a9bc  sub     rsp, 40h
0x14002a9c0  lea     rsi, [rcx+4C8h]
0x14002a9c7  mov     [rsp+68h+DeviceRegKey], 0
0x14002a9d0  mov     r14, rcx
0x14002a9d3  mov     dword ptr [rsi], 0
0x14002a9d9  mov     rcx, [rcx+18h]; DeviceObject
0x14002a9dd  lea     r9, [rsp+68h+DeviceRegKey]; DeviceRegKey
0x14002a9e2  mov     edx, 1; DevInstKeyType
0x14002a9e7  mov     r8d, 1F0000h; DesiredAccess
0x14002a9ed  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002a9f4  nop     dword ptr [rax+rax+00h]
0x14002a9f9  mov     ebx, eax
0x14002a9fb  mov     r12d, 4
0x14002aa01  test    eax, eax
0x14002aa03  jns     short loc_14002AA70
0x14002aa05  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002aa0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002aa13  jnz     loc_14002AB37
0x14002aa19  mov     dword ptr [r14+4C8h], 0
0x14002aa24  mov     eax, ebx
0x14002aa26  mov     rbx, [rsp+68h+arg_10]
0x14002aa2e  add     rsp, 40h
0x14002aa32  pop     r14
0x14002aa34  pop     r12
0x14002aa36  pop     rdi
0x14002aa37  pop     rsi
0x14002aa38  pop     rbp
0x14002aa39  retn
0x14002aa3b  mov     edx, 43627355h; Tag
0x14002aa40  mov     rcx, rdi; P
0x14002aa43  call    cs:__imp_ExFreePoolWithTag
0x14002aa4a  nop     dword ptr [rax+rax+00h]
0x14002aa4f  mov     rcx, [rsp+68h+DeviceRegKey]; Handle
0x14002aa54  call    cs:__imp_ZwClose
0x14002aa5b  nop     dword ptr [rax+rax+00h]
0x14002aa60  test    ebx, ebx
0x14002aa62  js      short loc_14002AA05
0x14002aa64  cmp     esi, r12d
0x14002aa67  jnz     short loc_14002AA05
0x14002aa69  cmp     ebp, r12d
0x14002aa6c  jz      short loc_14002AA24
0x14002aa6e  jmp     short loc_14002AA05
0x14002aa70  xorps   xmm0, xmm0
0x14002aa73  mov     [rsp+68h+arg_0], 0
0x14002aa7b  lea     rdx, aUsbccgpcapabil; "UsbccgpCapabilities"
0x14002aa82  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14002aa87  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14002aa8c  call    cs:__imp_RtlInitUnicodeString
0x14002aa93  nop     dword ptr [rax+rax+00h]
0x14002aa98  mov     ebx, 10h
0x14002aa9d  mov     r8d, 43627355h
0x14002aaa3  mov     edx, ebx
0x14002aaa5  mov     ecx, 100h
0x14002aaaa  call    cs:__imp_ExAllocatePool2
0x14002aab1  nop     dword ptr [rax+rax+00h]
0x14002aab6  mov     rdi, rax
0x14002aab9  test    rax, rax
0x14002aabc  jz      short loc_14002AB29
0x14002aabe  mov     rcx, [rsp+68h+DeviceRegKey]; KeyHandle
0x14002aac3  lea     rax, [rsp+68h+arg_0]
0x14002aac8  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14002aacd  lea     r8d, [rbx-0Eh]; KeyValueInformationClass
0x14002aad1  mov     r9, rdi; KeyValueInformation
0x14002aad4  mov     [rsp+68h+Length], ebx; Length
0x14002aad8  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14002aadd  call    cs:__imp_ZwQueryValueKey
0x14002aae4  nop     dword ptr [rax+rax+00h]
0x14002aae9  xor     ebx, ebx
0x14002aaeb  cmp     eax, 80000005h
0x14002aaf0  cmovnz  ebx, eax
0x14002aaf3  test    ebx, ebx
0x14002aaf5  js      short loc_14002AB20
0x14002aaf7  test    rsi, rsi
0x14002aafa  jz      short loc_14002AB15
0x14002aafc  mov     eax, [rdi+8]
0x14002aaff  lea     rdx, [rdi+0Ch]; Src
0x14002ab03  cmp     eax, r12d
0x14002ab06  mov     rcx, rsi; void *
0x14002ab09  cmova   eax, r12d
0x14002ab0d  mov     r8d, eax; Size
0x14002ab10  call    memmove
0x14002ab15  mov     esi, [rdi+4]
0x14002ab18  mov     ebp, [rdi+8]
0x14002ab1b  jmp     loc_14002AA3B
0x14002ab20  xor     esi, esi
0x14002ab22  xor     ebp, ebp
0x14002ab24  jmp     loc_14002AA3B
0x14002ab29  xor     esi, esi
0x14002ab2b  mov     ebx, 0C000009Ah
0x14002ab30  xor     ebp, ebp
0x14002ab32  jmp     loc_14002AA4F
0x14002ab37  mov     rcx, [r14+558h]
0x14002ab3e  lea     rax, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002ab45  mov     r9d, 0Bh
0x14002ab4b  mov     dword ptr [rsp+68h+ResultLength], ebx
0x14002ab4f  mov     dl, r12b
0x14002ab52  mov     qword ptr [rsp+68h+Length], rax
0x14002ab57  lea     r8d, [r9-0Ah]
0x14002ab5b  call    WPP_RECORDER_SF_d
0x14002ab60  jmp     loc_14002AA19
```
