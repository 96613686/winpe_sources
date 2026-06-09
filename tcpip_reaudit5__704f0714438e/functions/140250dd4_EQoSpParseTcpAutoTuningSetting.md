# EQoSpParseTcpAutoTuningSetting

- ea: `0x140250dd4`
- end: `0x140250f09`
- name: `EQoSpParseTcpAutoTuningSetting`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140251020`

## callees

- `0x140250dd4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e20`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e5f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e9d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250ede`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e20`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e5f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250e9d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140250ede`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250df2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e86`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250ec7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250df2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250e86`
- `ntoskrnl!RtlInitUnicodeString` at `0x140250ec7`

## pseudocode

```c
__int64 __fastcall EQoSpParseTcpAutoTuningSetting(PCWSTR SourceString)
{
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF

  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&String2, L"Off");
  if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
  {
    EQoSpPolicyTcpAutoTuningSetting = 0;
    return 0;
  }
  RtlInitUnicodeString(&String2, L"Highly Restricted");
  if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
  {
    EQoSpPolicyTcpAutoTuningSetting = 1;
    return 0;
  }
  RtlInitUnicodeString(&String2, L"Restricted");
  if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
  {
    EQoSpPolicyTcpAutoTuningSetting = 2;
    return 0;
  }
  RtlInitUnicodeString(&String2, L"Normal");
  if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
  {
    EQoSpPolicyTcpAutoTuningSetting = 3;
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140250dd4  push    rbp
0x140250dd6  mov     rbp, rsp
0x140250dd9  sub     rsp, 40h
0x140250ddd  xorps   xmm0, xmm0
0x140250de0  xorps   xmm1, xmm1
0x140250de3  mov     rdx, rcx; SourceString
0x140250de6  lea     rcx, [rbp+DestinationString]; DestinationString
0x140250dea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140250dee  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140250df2  call    cs:__imp_RtlInitUnicodeString
0x140250df9  nop     dword ptr [rax+rax+00h]
0x140250dfe  lea     rdx, aOff; "Off"
0x140250e05  lea     rcx, [rbp+String2]; DestinationString
0x140250e09  call    cs:__imp_RtlInitUnicodeString
0x140250e10  nop     dword ptr [rax+rax+00h]
0x140250e15  mov     r8b, 1; CaseInSensitive
0x140250e18  lea     rdx, [rbp+String2]; String2
0x140250e1c  lea     rcx, [rbp+DestinationString]; String1
0x140250e20  call    cs:__imp_RtlCompareUnicodeString
0x140250e27  nop     dword ptr [rax+rax+00h]
0x140250e2c  test    eax, eax
0x140250e2e  jnz     short loc_140250E3D
0x140250e30  mov     cs:EQoSpPolicyTcpAutoTuningSetting, eax
0x140250e36  xor     eax, eax
0x140250e38  jmp     loc_140250F02
0x140250e3d  lea     rdx, aHighlyRestrict; "Highly Restricted"
0x140250e44  lea     rcx, [rbp+String2]; DestinationString
0x140250e48  call    cs:__imp_RtlInitUnicodeString
0x140250e4f  nop     dword ptr [rax+rax+00h]
0x140250e54  mov     r8b, 1; CaseInSensitive
0x140250e57  lea     rdx, [rbp+String2]; String2
0x140250e5b  lea     rcx, [rbp+DestinationString]; String1
0x140250e5f  call    cs:__imp_RtlCompareUnicodeString
0x140250e66  nop     dword ptr [rax+rax+00h]
0x140250e6b  test    eax, eax
0x140250e6d  jnz     short loc_140250E7B
0x140250e6f  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 1
0x140250e79  jmp     short loc_140250E36
0x140250e7b  lea     rdx, aRestricted; "Restricted"
0x140250e82  lea     rcx, [rbp+String2]; DestinationString
0x140250e86  call    cs:__imp_RtlInitUnicodeString
0x140250e8d  nop     dword ptr [rax+rax+00h]
0x140250e92  mov     r8b, 1; CaseInSensitive
0x140250e95  lea     rdx, [rbp+String2]; String2
0x140250e99  lea     rcx, [rbp+DestinationString]; String1
0x140250e9d  call    cs:__imp_RtlCompareUnicodeString
0x140250ea4  nop     dword ptr [rax+rax+00h]
0x140250ea9  test    eax, eax
0x140250eab  jnz     short loc_140250EBC
0x140250ead  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 2
0x140250eb7  jmp     loc_140250E36
0x140250ebc  lea     rdx, aNormal; "Normal"
0x140250ec3  lea     rcx, [rbp+String2]; DestinationString
0x140250ec7  call    cs:__imp_RtlInitUnicodeString
0x140250ece  nop     dword ptr [rax+rax+00h]
0x140250ed3  mov     r8b, 1; CaseInSensitive
0x140250ed6  lea     rdx, [rbp+String2]; String2
0x140250eda  lea     rcx, [rbp+DestinationString]; String1
0x140250ede  call    cs:__imp_RtlCompareUnicodeString
0x140250ee5  nop     dword ptr [rax+rax+00h]
0x140250eea  test    eax, eax
0x140250eec  jnz     short loc_140250EFD
0x140250eee  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 3
0x140250ef8  jmp     loc_140250E36
0x140250efd  mov     eax, 0C000000Dh
0x140250f02  add     rsp, 40h
0x140250f06  pop     rbp
0x140250f07  retn
```
