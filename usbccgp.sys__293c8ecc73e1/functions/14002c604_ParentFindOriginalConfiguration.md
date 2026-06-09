# ParentFindOriginalConfiguration

- ea: `0x14002c604`
- end: `0x14002c7c9`
- name: `ParentFindOriginalConfiguration`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x14000a6cc`
- `0x140014e00`
- `0x14002c604`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c7ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c7ab`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002c63b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002c63b`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c765`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c765`
- `ntoskrnl!ZwClose` at `0x14002c6b0`
- `ntoskrnl!ZwClose` at `0x14002c6b0`
- `ntoskrnl!ExAllocatePool2` at `0x14002c731`
- `ntoskrnl!ExAllocatePool2` at `0x14002c731`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c713`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c713`

## string_xrefs

- `0x14002c704`: `OriginalConfigurationValue`

## pseudocode

```c
__int64 __fastcall ParentFindOriginalConfiguration(__int64 a1, _BYTE *a2)
{
  char v2; // di
  NTSTATUS v5; // eax
  int v6; // edx
  int v7; // ebx
  __int64 result; // rax
  _DWORD *Pool2; // rsi
  NTSTATUS v10; // eax
  int v11; // r14d
  unsigned int v12; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v14; // [rsp+80h] [rbp+40h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF
  void *DeviceRegKey; // [rsp+90h] [rbp+50h] BYREF

  v2 = 0;
  v14 = 0;
  DeviceRegKey = 0;
  v5 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 24), 1u, 0x1F0000u, &DeviceRegKey);
  LOBYTE(v7) = v5;
  if ( v5 < 0 )
    goto LABEL_2;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"OriginalConfigurationValue");
  Pool2 = (_DWORD *)ExAllocatePool2(256, 16, 1130525525);
  if ( Pool2 )
  {
    v10 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, Pool2, 0x10u, &ResultLength);
    v7 = 0;
    if ( v10 != -2147483643 )
      v7 = v10;
    v11 = 0;
    if ( v7 >= 0 )
    {
      v12 = Pool2[2];
      if ( v12 > 4 )
        v12 = 4;
      memmove(&v14, Pool2 + 3, v12);
      v11 = Pool2[1];
      v2 = v14;
    }
    ExFreePoolWithTag(Pool2, 0x43627355u);
  }
  else
  {
    v7 = -1073741670;
    v11 = 0;
  }
  ZwClose(DeviceRegKey);
  if ( v7 < 0 )
  {
LABEL_2:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 3;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 1368), v6, 8, 71, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids, v7);
    }
  }
  else
  {
    if ( v11 == 4 )
      goto LABEL_5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v6, 8, 72, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
    }
  }
  v2 = 0;
LABEL_5:
  result = 0;
  *a2 = v2;
  return result;
}

```

## disassembly

```asm
0x14002c604  mov     [rsp-38h+arg_18], rbx
0x14002c609  push    rbp
0x14002c60a  push    rsi
0x14002c60b  push    rdi
0x14002c60c  push    r12
0x14002c60e  push    r13
0x14002c610  push    r14
0x14002c612  push    r15
0x14002c614  mov     rbp, rsp
0x14002c617  sub     rsp, 40h
0x14002c61b  xor     edi, edi
0x14002c61d  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x14002c621  mov     r12, rdx
0x14002c624  mov     [rbp+arg_0], edi
0x14002c627  mov     r15, rcx
0x14002c62a  mov     [rbp+DeviceRegKey], rdi
0x14002c62e  mov     rcx, [rcx+18h]; DeviceObject
0x14002c632  mov     r8d, 1F0000h; DesiredAccess
0x14002c638  lea     edx, [rdi+1]; DevInstKeyType
0x14002c63b  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002c642  nop     dword ptr [rax+rax+00h]
0x14002c647  mov     ebx, eax
0x14002c649  test    eax, eax
0x14002c64b  jns     loc_14002C6FE
0x14002c651  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c658  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c65f  jnz     short loc_14002C682
0x14002c661  xor     edi, edi
0x14002c663  mov     rbx, [rsp+40h+arg_18]
0x14002c66b  xor     eax, eax
0x14002c66d  mov     [r12], dil
0x14002c671  add     rsp, 40h
0x14002c675  pop     r15
0x14002c677  pop     r14
0x14002c679  pop     r13
0x14002c67b  pop     r12
0x14002c67d  pop     rdi
0x14002c67e  pop     rsi
0x14002c67f  pop     rbp
0x14002c680  retn
0x14002c682  mov     rcx, [r15+558h]
0x14002c689  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c690  mov     r9d, 47h ; 'G'
0x14002c696  mov     dword ptr [rsp+40h+ResultLength], ebx
0x14002c69a  mov     dl, 3
0x14002c69c  mov     qword ptr [rsp+40h+Length], rax
0x14002c6a1  lea     r8d, [r9-3Fh]
0x14002c6a5  call    WPP_RECORDER_SF_d
0x14002c6aa  jmp     short loc_14002C661
0x14002c6ac  mov     rcx, [rbp+DeviceRegKey]; Handle
0x14002c6b0  call    cs:__imp_ZwClose
0x14002c6b7  nop     dword ptr [rax+rax+00h]
0x14002c6bc  test    ebx, ebx
0x14002c6be  js      short loc_14002C651
0x14002c6c0  cmp     r14d, r13d
0x14002c6c3  jz      short loc_14002C663
0x14002c6c5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c6cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c6d3  jz      short loc_14002C661
0x14002c6d5  mov     rcx, [r15+558h]
0x14002c6dc  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c6e3  mov     r9d, 48h ; 'H'
0x14002c6e9  mov     qword ptr [rsp+40h+Length], rax
0x14002c6ee  mov     dl, 2
0x14002c6f0  lea     r8d, [r9-40h]
0x14002c6f4  call    WPP_RECORDER_SF_
0x14002c6f9  jmp     loc_14002C661
0x14002c6fe  xorps   xmm0, xmm0
0x14002c701  mov     [rbp+arg_8], edi
0x14002c704  lea     rdx, aOriginalconfig; "OriginalConfigurationValue"
0x14002c70b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002c70f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002c713  call    cs:__imp_RtlInitUnicodeString
0x14002c71a  nop     dword ptr [rax+rax+00h]
0x14002c71f  mov     ebx, 10h
0x14002c724  mov     r8d, 43627355h
0x14002c72a  mov     edx, ebx
0x14002c72c  mov     ecx, 100h
0x14002c731  call    cs:__imp_ExAllocatePool2
0x14002c738  nop     dword ptr [rax+rax+00h]
0x14002c73d  lea     r13d, [rbx-0Ch]
0x14002c741  mov     rsi, rax
0x14002c744  test    rax, rax
0x14002c747  jz      short loc_14002C7BC
0x14002c749  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14002c74d  lea     rax, [rbp+arg_8]
0x14002c751  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14002c756  lea     r8d, [rbx-0Eh]; KeyValueInformationClass
0x14002c75a  mov     r9, rsi; KeyValueInformation
0x14002c75d  mov     [rsp+40h+Length], ebx; Length
0x14002c761  lea     rdx, [rbp+DestinationString]; ValueName
0x14002c765  call    cs:__imp_ZwQueryValueKey
0x14002c76c  nop     dword ptr [rax+rax+00h]
0x14002c771  xor     ebx, ebx
0x14002c773  cmp     eax, 80000005h
0x14002c778  cmovnz  ebx, eax
0x14002c77b  xor     r14d, r14d
0x14002c77e  test    ebx, ebx
0x14002c780  js      short loc_14002C7A3
0x14002c782  mov     eax, [rsi+8]
0x14002c785  lea     rdx, [rsi+0Ch]; Src
0x14002c789  cmp     eax, r13d
0x14002c78c  lea     rcx, [rbp+arg_0]; void *
0x14002c790  cmova   eax, r13d
0x14002c794  mov     r8d, eax; Size
0x14002c797  call    memmove
0x14002c79c  mov     r14d, [rsi+4]
0x14002c7a0  mov     edi, [rbp+arg_0]
0x14002c7a3  mov     edx, 43627355h; Tag
0x14002c7a8  mov     rcx, rsi; P
0x14002c7ab  call    cs:__imp_ExFreePoolWithTag
0x14002c7b2  nop     dword ptr [rax+rax+00h]
0x14002c7b7  jmp     loc_14002C6AC
0x14002c7bc  mov     ebx, 0C000009Ah
0x14002c7c1  xor     r14d, r14d
0x14002c7c4  jmp     loc_14002C6AC
```
