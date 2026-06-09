# SIPolicyFileRuleCompare

- ea: `0x18001c820`
- end: `0x18001c8a0`
- name: `SIPolicyFileRuleCompare`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c790`
- `0x180023758`

## callees

- `0x18001c820`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001c843`
- `ntdll!RtlCompareUnicodeString` at `0x18001c858`
- `ntdll!RtlCompareUnicodeString` at `0x18001c86d`
- `ntdll!RtlCompareUnicodeString` at `0x18001c882`
- `ntdll!RtlCompareUnicodeString` at `0x18001c843`
- `ntdll!RtlCompareUnicodeString` at `0x18001c858`
- `ntdll!RtlCompareUnicodeString` at `0x18001c86d`
- `ntdll!RtlCompareUnicodeString` at `0x18001c882`

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
0x18001c820  mov     [rsp+arg_0], rbx
0x18001c825  push    rdi
0x18001c826  sub     rsp, 20h
0x18001c82a  mov     rbx, rcx
0x18001c82d  mov     rdi, rdx
0x18001c830  mov     ecx, [rdx]
0x18001c832  mov     eax, [rbx]
0x18001c834  cmp     eax, ecx
0x18001c836  jnz     short loc_18001C893
0x18001c838  add     rdx, 8; String2
0x18001c83c  lea     rcx, [rbx+8]; String1
0x18001c840  mov     r8b, 1; CaseInsensitive
0x18001c843  call    cs:__imp_RtlCompareUnicodeString
0x18001c849  test    eax, eax
0x18001c84b  jnz     short loc_18001C888
0x18001c84d  lea     rdx, [rdi+18h]; String2
0x18001c851  mov     r8b, 1; CaseInsensitive
0x18001c854  lea     rcx, [rbx+18h]; String1
0x18001c858  call    cs:__imp_RtlCompareUnicodeString
0x18001c85e  test    eax, eax
0x18001c860  jnz     short loc_18001C888
0x18001c862  lea     rdx, [rdi+28h]; String2
0x18001c866  mov     r8b, 1; CaseInsensitive
0x18001c869  lea     rcx, [rbx+28h]; String1
0x18001c86d  call    cs:__imp_RtlCompareUnicodeString
0x18001c873  test    eax, eax
0x18001c875  jnz     short loc_18001C888
0x18001c877  lea     rdx, [rdi+38h]; String2
0x18001c87b  mov     r8b, 1; CaseInsensitive
0x18001c87e  lea     rcx, [rbx+38h]; String1
0x18001c882  call    cs:__imp_RtlCompareUnicodeString
0x18001c888  mov     rbx, [rsp+28h+arg_0]
0x18001c88d  add     rsp, 20h
0x18001c891  pop     rdi
0x18001c892  retn
0x18001c893  mov     rbx, [rsp+28h+arg_0]
0x18001c898  sub     eax, ecx
0x18001c89a  add     rsp, 20h
0x18001c89e  pop     rdi
0x18001c89f  retn
```
