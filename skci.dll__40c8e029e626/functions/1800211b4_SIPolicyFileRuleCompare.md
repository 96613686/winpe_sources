# SIPolicyFileRuleCompare

- ea: `0x1800211b4`
- end: `0x180021244`
- name: `SIPolicyFileRuleCompare`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019690`
- `0x18001a7d4`
- `0x18001df70`

## callees

- `0x1800211b4`

## import_xrefs

- `securekernel!RtlCompareUnicodeString` at `0x1800211db`
- `securekernel!RtlCompareUnicodeString` at `0x1800211f6`
- `securekernel!RtlCompareUnicodeString` at `0x180021211`
- `securekernel!RtlCompareUnicodeString` at `0x18002122c`
- `securekernel!RtlCompareUnicodeString` at `0x1800211db`
- `securekernel!RtlCompareUnicodeString` at `0x1800211f6`
- `securekernel!RtlCompareUnicodeString` at `0x180021211`
- `securekernel!RtlCompareUnicodeString` at `0x18002122c`

## pseudocode

```c
int __fastcall SIPolicyFileRuleCompare(__int64 a1, __int64 a2)
{
  int result; // eax

  if ( *(_DWORD *)a1 != *(_DWORD *)a2 )
    return *(_DWORD *)a1 - *(_DWORD *)a2;
  result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 8), (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 24), (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
    {
      result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 40), (PCUNICODE_STRING)(a2 + 40), 1u);
      if ( !result )
        return RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 56), (PCUNICODE_STRING)(a2 + 56), 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800211b4  mov     [rsp+arg_0], rbx
0x1800211b9  push    rdi
0x1800211ba  sub     rsp, 20h
0x1800211be  mov     rdi, rcx
0x1800211c1  mov     rbx, rdx
0x1800211c4  mov     ecx, [rdx]
0x1800211c6  mov     eax, [rdi]
0x1800211c8  cmp     eax, ecx
0x1800211ca  jz      short loc_1800211D0
0x1800211cc  sub     eax, ecx
0x1800211ce  jmp     short loc_180021238
0x1800211d0  add     rdx, 8; String2
0x1800211d4  lea     rcx, [rdi+8]; String1
0x1800211d8  mov     r8b, 1; CaseInSensitive
0x1800211db  call    cs:__imp_RtlCompareUnicodeString
0x1800211e2  nop     dword ptr [rax+rax+00h]
0x1800211e7  test    eax, eax
0x1800211e9  jnz     short loc_180021238
0x1800211eb  lea     rdx, [rbx+18h]; String2
0x1800211ef  mov     r8b, 1; CaseInSensitive
0x1800211f2  lea     rcx, [rdi+18h]; String1
0x1800211f6  call    cs:__imp_RtlCompareUnicodeString
0x1800211fd  nop     dword ptr [rax+rax+00h]
0x180021202  test    eax, eax
0x180021204  jnz     short loc_180021238
0x180021206  lea     rdx, [rbx+28h]; String2
0x18002120a  mov     r8b, 1; CaseInSensitive
0x18002120d  lea     rcx, [rdi+28h]; String1
0x180021211  call    cs:__imp_RtlCompareUnicodeString
0x180021218  nop     dword ptr [rax+rax+00h]
0x18002121d  test    eax, eax
0x18002121f  jnz     short loc_180021238
0x180021221  lea     rdx, [rbx+38h]; String2
0x180021225  mov     r8b, 1; CaseInSensitive
0x180021228  lea     rcx, [rdi+38h]; String1
0x18002122c  call    cs:__imp_RtlCompareUnicodeString
0x180021233  nop     dword ptr [rax+rax+00h]
0x180021238  mov     rbx, [rsp+28h+arg_0]
0x18002123d  add     rsp, 20h
0x180021241  pop     rdi
0x180021242  retn
```
