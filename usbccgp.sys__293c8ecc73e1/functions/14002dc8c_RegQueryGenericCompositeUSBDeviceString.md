# RegQueryGenericCompositeUSBDeviceString

- ea: `0x14002dc8c`
- end: `0x14002dd52`
- name: `RegQueryGenericCompositeUSBDeviceString`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002f078`

## callees

- `0x140014d50`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002dd11`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002dd11`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14002dd34`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002dd01`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002dd01`

## string_xrefs

- `0x14002dcac`: `RtlQueryRegistryValuesEx`
- `0x14002dcb3`: `GenericCompositeUSBDeviceString\n`

## pseudocode

```c
__int64 RegQueryGenericCompositeUSBDeviceString()
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const wchar_t *, void **); // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  void *v3; // [rsp+40h] [rbp-19h] BYREF
  int v4; // [rsp+48h] [rbp-11h]
  const wchar_t *v5; // [rsp+50h] [rbp-9h]
  PVOID *v6; // [rsp+58h] [rbp-1h]
  int v7; // [rsp+60h] [rbp+7h]
  __int64 v8; // [rsp+68h] [rbp+Fh]
  int v9; // [rsp+70h] [rbp+17h]
  __int64 v10; // [rsp+78h] [rbp+1Fh]
  int v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]

  v4 = 4;
  v3 = &GetConfigValue;
  v7 = 0;
  v5 = L"GenericCompositeUSBDeviceString\n";
  v8 = 0;
  v6 = &GenericCompositeUSBDeviceString;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, void **))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, void **))RtlQueryRegistryValues;
  return SystemRoutineAddress(2, L"usbflags", &v3);
}

```

## disassembly

```asm
0x14002dc8c  push    rbp
0x14002dc8e  lea     rbp, [rsp-57h]
0x14002dc93  sub     rsp, 0B0h
0x14002dc9a  lea     rax, GetConfigValue
0x14002dca1  mov     [rbp+57h+var_68], 4
0x14002dca8  mov     [rbp+57h+var_70], rax
0x14002dcac  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14002dcb3  lea     rax, aGenericcomposi; "GenericCompositeUSBDeviceString\n"
0x14002dcba  mov     [rbp+57h+var_50], 0
0x14002dcc1  mov     [rbp+57h+var_60], rax
0x14002dcc5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002dcc9  lea     rax, GenericCompositeUSBDeviceString
0x14002dcd0  mov     [rbp+57h+var_48], 0
0x14002dcd8  xorps   xmm0, xmm0
0x14002dcdb  mov     [rbp+57h+var_58], rax
0x14002dcdf  mov     [rbp+57h+var_40], 0
0x14002dce6  mov     [rbp+57h+var_38], 0
0x14002dcee  mov     [rbp+57h+var_30], 0
0x14002dcf5  mov     [rbp+57h+var_28], 0
0x14002dcfd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002dd01  call    cs:__imp_RtlInitUnicodeString
0x14002dd08  nop     dword ptr [rax+rax+00h]
0x14002dd0d  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14002dd11  call    cs:__imp_MmGetSystemRoutineAddress
0x14002dd18  nop     dword ptr [rax+rax+00h]
0x14002dd1d  lea     r8, [rbp+57h+var_70]
0x14002dd21  mov     [rsp+0B0h+var_90], 0
0x14002dd2a  test    rax, rax
0x14002dd2d  lea     rdx, aUsbflags; "usbflags"
0x14002dd34  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14002dd3c  xor     r9d, r9d
0x14002dd3f  lea     ecx, [r9+2]
0x14002dd43  call    _guard_dispatch_icall
0x14002dd48  add     rsp, 0B0h
0x14002dd4f  pop     rbp
0x14002dd50  retn
```
