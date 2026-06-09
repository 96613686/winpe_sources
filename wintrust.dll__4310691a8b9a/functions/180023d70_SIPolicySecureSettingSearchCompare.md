# SIPolicySecureSettingSearchCompare

- ea: `0x180023d70`
- end: `0x180023dc7`
- name: `SIPolicySecureSettingSearchCompare`
- size: `87`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180023d70`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180023d8a`
- `ntdll!RtlCompareUnicodeString` at `0x180023daa`
- `ntdll!RtlCompareUnicodeString` at `0x180023dbf`
- `ntdll!RtlCompareUnicodeString` at `0x180023d8a`
- `ntdll!RtlCompareUnicodeString` at `0x180023daa`
- `ntdll!RtlCompareUnicodeString` at `0x180023dbf`

## pseudocode

```c
int __fastcall SIPolicySecureSettingSearchCompare(PCUNICODE_STRING *a1, char *a2)
{
  int result; // eax

  result = RtlCompareUnicodeString(*a1, (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString(a1[1], (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
      return RtlCompareUnicodeString(a1[2], (PCUNICODE_STRING)(a2 + 40), 1u);
  }
  return result;
}

```

## disassembly

```asm
0x180023d70  mov     [rsp+arg_0], rbx
0x180023d75  push    rdi
0x180023d76  sub     rsp, 20h
0x180023d7a  mov     rbx, rdx
0x180023d7d  mov     rdi, rcx
0x180023d80  mov     rcx, [rcx]; String1
0x180023d83  add     rdx, 8; String2
0x180023d87  mov     r8b, 1; CaseInsensitive
0x180023d8a  call    cs:__imp_RtlCompareUnicodeString
0x180023d90  test    eax, eax
0x180023d92  jz      short loc_180023D9F
0x180023d94  mov     rbx, [rsp+28h+arg_0]
0x180023d99  add     rsp, 20h
0x180023d9d  pop     rdi
0x180023d9e  retn
0x180023d9f  mov     rcx, [rdi+8]; String1
0x180023da3  lea     rdx, [rbx+18h]; String2
0x180023da7  mov     r8b, 1; CaseInsensitive
0x180023daa  call    cs:__imp_RtlCompareUnicodeString
0x180023db0  test    eax, eax
0x180023db2  jnz     short loc_180023D94
0x180023db4  mov     rcx, [rdi+10h]; String1
0x180023db8  lea     rdx, [rbx+28h]; String2
0x180023dbc  mov     r8b, 1; CaseInsensitive
0x180023dbf  call    cs:__imp_RtlCompareUnicodeString
0x180023dc5  jmp     short loc_180023D94
```
