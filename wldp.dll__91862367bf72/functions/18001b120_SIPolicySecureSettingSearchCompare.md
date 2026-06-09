# SIPolicySecureSettingSearchCompare

- ea: `0x18001b120`
- end: `0x18001b175`
- name: `SIPolicySecureSettingSearchCompare`
- size: `85`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001b120`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001b13a`
- `ntdll!RtlCompareUnicodeString` at `0x18001b14f`
- `ntdll!RtlCompareUnicodeString` at `0x18001b164`
- `ntdll!RtlCompareUnicodeString` at `0x18001b13a`
- `ntdll!RtlCompareUnicodeString` at `0x18001b14f`
- `ntdll!RtlCompareUnicodeString` at `0x18001b164`

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
0x18001b120  mov     [rsp+arg_0], rbx
0x18001b125  push    rdi
0x18001b126  sub     rsp, 20h
0x18001b12a  mov     rbx, rdx
0x18001b12d  mov     rdi, rcx
0x18001b130  mov     rcx, [rcx]; String1
0x18001b133  add     rdx, 8; String2
0x18001b137  mov     r8b, 1; CaseInsensitive
0x18001b13a  call    cs:__imp_RtlCompareUnicodeString
0x18001b140  test    eax, eax
0x18001b142  jnz     short loc_18001B16A
0x18001b144  mov     rcx, [rdi+8]; String1
0x18001b148  lea     rdx, [rbx+18h]; String2
0x18001b14c  mov     r8b, 1; CaseInsensitive
0x18001b14f  call    cs:__imp_RtlCompareUnicodeString
0x18001b155  test    eax, eax
0x18001b157  jnz     short loc_18001B16A
0x18001b159  mov     rcx, [rdi+10h]; String1
0x18001b15d  lea     rdx, [rbx+28h]; String2
0x18001b161  mov     r8b, 1; CaseInsensitive
0x18001b164  call    cs:__imp_RtlCompareUnicodeString
0x18001b16a  mov     rbx, [rsp+28h+arg_0]
0x18001b16f  add     rsp, 20h
0x18001b173  pop     rdi
0x18001b174  retn
```
