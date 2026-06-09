# SclExtractSidSubString

- ea: `0x180001764`
- end: `0x180001841`
- name: `SclExtractSidSubString`
- size: `221`
- prototype: `__int64 __fastcall(PSID Sid, _WORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006024`
- `0x180007060`

## callees

- `0x180001464`
- `0x180001764`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x180001784`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180001784`
- `ntdll!RtlFreeUnicodeString` at `0x18000182e`
- `ntdll!RtlFreeUnicodeString` at `0x18000182e`

## string_xrefs

- `0x18000179b`: `(%lx): RtlConvertSidToUnicodeString failed!`
- `0x1800017b2`: `SclExtractSidSubString`
- `0x1800017e8`: `SclExtractSidSubString`
- `0x1800017d3`: `RtlConvertSidToUnicodeString returned too short of a string.`

## pseudocode

```c
__int64 __fastcall SclExtractSidSubString(PSID Sid, _WORD *a2)
{
  int v3; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-18h] BYREF

  UnicodeString = 0;
  v3 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v3 >= 0 )
  {
    if ( UnicodeString.Length >= 0x12u )
    {
      v3 = RtlStringCchCopyNW(a2, 0x104u, UnicodeString.Buffer + 9, (unsigned int)UnicodeString.Length - 18);
    }
    else
    {
      SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 164, (__int64)"SclExtractSidSubString");
      v3 = -1073741823;
    }
  }
  else
  {
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 154, (__int64)"SclExtractSidSubString");
  }
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001764  mov     [rsp+arg_0], rbx
0x180001769  push    rdi
0x18000176a  sub     rsp, 50h
0x18000176e  mov     rdi, rdx
0x180001771  xorps   xmm0, xmm0
0x180001774  mov     rdx, rcx; Sid
0x180001777  mov     r8b, 1; AllocateDestinationString
0x18000177a  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x18000177f  movups  xmmword ptr [rsp+58h+UnicodeString.Length], xmm0
0x180001784  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000178a  mov     ebx, eax
0x18000178c  test    eax, eax
0x18000178e  jns     short loc_1800017C7
0x180001790  mov     [rsp+58h+var_28], eax
0x180001794  lea     r8, SclEvent_Generic_Error
0x18000179b  lea     rax, aLxRtlconvertsi; "(%lx): RtlConvertSidToUnicodeString fai"...
0x1800017a2  mov     r9d, 9Ah
0x1800017a8  mov     [rsp+58h+var_30], rax
0x1800017ad  mov     edx, 3
0x1800017b2  lea     rax, aSclextractsids; "SclExtractSidSubString"
0x1800017b9  xor     ecx, ecx
0x1800017bb  mov     [rsp+58h+var_38], rax
0x1800017c0  call    SclLogGenericMessage
0x1800017c5  jmp     short loc_180001829
0x1800017c7  mov     ecx, 12h
0x1800017cc  cmp     [rsp+58h+UnicodeString.Length], cx
0x1800017d1  jnb     short loc_180001809
0x1800017d3  lea     rax, aRtlconvertsidt; "RtlConvertSidToUnicodeString returned t"...
0x1800017da  mov     r9d, 0A4h
0x1800017e0  mov     [rsp+58h+var_30], rax
0x1800017e5  lea     edx, [rcx-0Fh]
0x1800017e8  lea     rax, aSclextractsids; "SclExtractSidSubString"
0x1800017ef  xor     ecx, ecx
0x1800017f1  lea     r8, SclEvent_Generic_Error
0x1800017f8  mov     [rsp+58h+var_38], rax
0x1800017fd  call    SclLogGenericMessage
0x180001802  mov     ebx, 0C0000001h
0x180001807  jmp     short loc_180001829
0x180001809  movzx   r9d, [rsp+58h+UnicodeString.Length]
0x18000180f  mov     edx, 104h
0x180001814  mov     r8, [rsp+58h+UnicodeString.Buffer]
0x180001819  sub     r9d, ecx
0x18000181c  add     r8, rcx
0x18000181f  mov     rcx, rdi
0x180001822  call    RtlStringCchCopyNW
0x180001827  mov     ebx, eax
0x180001829  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x18000182e  call    cs:__imp_RtlFreeUnicodeString
0x180001834  mov     eax, ebx
0x180001836  mov     rbx, [rsp+58h+arg_0]
0x18000183b  add     rsp, 50h
0x18000183f  pop     rdi
0x180001840  retn
```
