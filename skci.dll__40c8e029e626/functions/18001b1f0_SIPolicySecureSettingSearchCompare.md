# SIPolicySecureSettingSearchCompare

- ea: `0x18001b1f0`
- end: `0x18001b258`
- name: `SIPolicySecureSettingSearchCompare`
- size: `104`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001b1f0`

## import_xrefs

- `securekernel!RtlCompareUnicodeString` at `0x18001b20a`
- `securekernel!RtlCompareUnicodeString` at `0x18001b225`
- `securekernel!RtlCompareUnicodeString` at `0x18001b240`
- `securekernel!RtlCompareUnicodeString` at `0x18001b20a`
- `securekernel!RtlCompareUnicodeString` at `0x18001b225`
- `securekernel!RtlCompareUnicodeString` at `0x18001b240`

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
0x18001b1f0  mov     [rsp+arg_0], rbx
0x18001b1f5  push    rdi
0x18001b1f6  sub     rsp, 20h
0x18001b1fa  mov     rbx, rdx
0x18001b1fd  mov     rdi, rcx
0x18001b200  mov     rcx, [rcx]; String1
0x18001b203  add     rdx, 8; String2
0x18001b207  mov     r8b, 1; CaseInSensitive
0x18001b20a  call    cs:__imp_RtlCompareUnicodeString
0x18001b211  nop     dword ptr [rax+rax+00h]
0x18001b216  test    eax, eax
0x18001b218  jnz     short loc_18001B24C
0x18001b21a  mov     rcx, [rdi+8]; String1
0x18001b21e  lea     rdx, [rbx+18h]; String2
0x18001b222  mov     r8b, 1; CaseInSensitive
0x18001b225  call    cs:__imp_RtlCompareUnicodeString
0x18001b22c  nop     dword ptr [rax+rax+00h]
0x18001b231  test    eax, eax
0x18001b233  jnz     short loc_18001B24C
0x18001b235  mov     rcx, [rdi+10h]; String1
0x18001b239  lea     rdx, [rbx+28h]; String2
0x18001b23d  mov     r8b, 1; CaseInSensitive
0x18001b240  call    cs:__imp_RtlCompareUnicodeString
0x18001b247  nop     dword ptr [rax+rax+00h]
0x18001b24c  mov     rbx, [rsp+28h+arg_0]
0x18001b251  add     rsp, 20h
0x18001b255  pop     rdi
0x18001b256  retn
```
