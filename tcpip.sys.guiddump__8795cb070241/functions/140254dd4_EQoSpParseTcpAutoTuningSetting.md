# EQoSpParseTcpAutoTuningSetting

- ea: `0x140254dd4`
- end: `0x140254f09`
- name: `EQoSpParseTcpAutoTuningSetting`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140255020`

## callees

- `0x140254dd4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e20`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e5f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e9d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254ede`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e20`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e5f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254e9d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140254ede`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254df2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e86`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254ec7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254df2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254e86`
- `ntoskrnl!RtlInitUnicodeString` at `0x140254ec7`

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
0x140254dd4  push    rbp
0x140254dd6  mov     rbp, rsp
0x140254dd9  sub     rsp, 40h
0x140254ddd  xorps   xmm0, xmm0
0x140254de0  xorps   xmm1, xmm1
0x140254de3  mov     rdx, rcx; SourceString
0x140254de6  lea     rcx, [rbp+DestinationString]; DestinationString
0x140254dea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140254dee  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140254df2  call    cs:__imp_RtlInitUnicodeString
0x140254df9  nop     dword ptr [rax+rax+00h]
0x140254dfe  lea     rdx, aOff; "Off"
0x140254e05  lea     rcx, [rbp+String2]; DestinationString
0x140254e09  call    cs:__imp_RtlInitUnicodeString
0x140254e10  nop     dword ptr [rax+rax+00h]
0x140254e15  mov     r8b, 1; CaseInSensitive
0x140254e18  lea     rdx, [rbp+String2]; String2
0x140254e1c  lea     rcx, [rbp+DestinationString]; String1
0x140254e20  call    cs:__imp_RtlCompareUnicodeString
0x140254e27  nop     dword ptr [rax+rax+00h]
0x140254e2c  test    eax, eax
0x140254e2e  jnz     short loc_140254E3D
0x140254e30  mov     cs:EQoSpPolicyTcpAutoTuningSetting, eax
0x140254e36  xor     eax, eax
0x140254e38  jmp     loc_140254F02
0x140254e3d  lea     rdx, aHighlyRestrict; "Highly Restricted"
0x140254e44  lea     rcx, [rbp+String2]; DestinationString
0x140254e48  call    cs:__imp_RtlInitUnicodeString
0x140254e4f  nop     dword ptr [rax+rax+00h]
0x140254e54  mov     r8b, 1; CaseInSensitive
0x140254e57  lea     rdx, [rbp+String2]; String2
0x140254e5b  lea     rcx, [rbp+DestinationString]; String1
0x140254e5f  call    cs:__imp_RtlCompareUnicodeString
0x140254e66  nop     dword ptr [rax+rax+00h]
0x140254e6b  test    eax, eax
0x140254e6d  jnz     short loc_140254E7B
0x140254e6f  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 1
0x140254e79  jmp     short loc_140254E36
0x140254e7b  lea     rdx, aRestricted; "Restricted"
0x140254e82  lea     rcx, [rbp+String2]; DestinationString
0x140254e86  call    cs:__imp_RtlInitUnicodeString
0x140254e8d  nop     dword ptr [rax+rax+00h]
0x140254e92  mov     r8b, 1; CaseInSensitive
0x140254e95  lea     rdx, [rbp+String2]; String2
0x140254e99  lea     rcx, [rbp+DestinationString]; String1
0x140254e9d  call    cs:__imp_RtlCompareUnicodeString
0x140254ea4  nop     dword ptr [rax+rax+00h]
0x140254ea9  test    eax, eax
0x140254eab  jnz     short loc_140254EBC
0x140254ead  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 2
0x140254eb7  jmp     loc_140254E36
0x140254ebc  lea     rdx, aNormal; "Normal"
0x140254ec3  lea     rcx, [rbp+String2]; DestinationString
0x140254ec7  call    cs:__imp_RtlInitUnicodeString
0x140254ece  nop     dword ptr [rax+rax+00h]
0x140254ed3  mov     r8b, 1; CaseInSensitive
0x140254ed6  lea     rdx, [rbp+String2]; String2
0x140254eda  lea     rcx, [rbp+DestinationString]; String1
0x140254ede  call    cs:__imp_RtlCompareUnicodeString
0x140254ee5  nop     dword ptr [rax+rax+00h]
0x140254eea  test    eax, eax
0x140254eec  jnz     short loc_140254EFD
0x140254eee  mov     cs:EQoSpPolicyTcpAutoTuningSetting, 3
0x140254ef8  jmp     loc_140254E36
0x140254efd  mov     eax, 0C000000Dh
0x140254f02  add     rsp, 40h
0x140254f06  pop     rbp
0x140254f07  retn
```
