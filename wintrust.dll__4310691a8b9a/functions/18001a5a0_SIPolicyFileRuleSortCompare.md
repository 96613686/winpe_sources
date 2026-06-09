# SIPolicyFileRuleSortCompare

- ea: `0x18001a5a0`
- end: `0x18001a64f`
- name: `SIPolicyFileRuleSortCompare`
- size: `175`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001a5a0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18001a5df`
- `ntdll!RtlCompareUnicodeString` at `0x18001a5f7`
- `ntdll!RtlCompareUnicodeString` at `0x18001a60f`
- `ntdll!RtlCompareUnicodeString` at `0x18001a627`
- `ntdll!RtlCompareUnicodeString` at `0x18001a5df`
- `ntdll!RtlCompareUnicodeString` at `0x18001a5f7`
- `ntdll!RtlCompareUnicodeString` at `0x18001a60f`
- `ntdll!RtlCompareUnicodeString` at `0x18001a627`

## pseudocode

```c
int __fastcall SIPolicyFileRuleSortCompare(char *a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v4; // rbx
  char *v5; // rsi
  int v6; // eax
  int result; // eax

  v4 = 168LL * *a2;
  v5 = &a1[168 * *a3];
  v6 = *(_DWORD *)&a1[v4];
  if ( v6 != *(_DWORD *)v5 )
    return v6 - *(_DWORD *)v5;
  result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v4 + 8], (PCUNICODE_STRING)(v5 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v4 + 24], (PCUNICODE_STRING)(v5 + 24), 1u);
    if ( !result )
    {
      result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v4 + 40], (PCUNICODE_STRING)(v5 + 40), 1u);
      if ( !result )
        return RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v4 + 56], (PCUNICODE_STRING)(v5 + 56), 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a5a0  mov     [rsp+arg_0], rbx
0x18001a5a5  mov     [rsp+arg_8], rsi
0x18001a5aa  push    rdi
0x18001a5ab  sub     rsp, 20h
0x18001a5af  mov     eax, [r8]
0x18001a5b2  mov     rdi, rcx
0x18001a5b5  imul    rsi, rax, 0A8h
0x18001a5bc  mov     eax, [rdx]
0x18001a5be  imul    rbx, rax, 0A8h
0x18001a5c5  add     rsi, rcx
0x18001a5c8  mov     eax, [rbx+rdi]
0x18001a5cb  mov     ecx, [rsi]
0x18001a5cd  cmp     eax, ecx
0x18001a5cf  jnz     short loc_18001A63D
0x18001a5d1  lea     rcx, [rdi+8]
0x18001a5d5  mov     r8b, 1; CaseInsensitive
0x18001a5d8  add     rcx, rbx; String1
0x18001a5db  lea     rdx, [rsi+8]; String2
0x18001a5df  call    cs:__imp_RtlCompareUnicodeString
0x18001a5e5  test    eax, eax
0x18001a5e7  jnz     short loc_18001A62D
0x18001a5e9  lea     rcx, [rdi+18h]
0x18001a5ed  mov     r8b, 1; CaseInsensitive
0x18001a5f0  add     rcx, rbx; String1
0x18001a5f3  lea     rdx, [rsi+18h]; String2
0x18001a5f7  call    cs:__imp_RtlCompareUnicodeString
0x18001a5fd  test    eax, eax
0x18001a5ff  jnz     short loc_18001A62D
0x18001a601  lea     rcx, [rdi+28h]
0x18001a605  mov     r8b, 1; CaseInsensitive
0x18001a608  add     rcx, rbx; String1
0x18001a60b  lea     rdx, [rsi+28h]; String2
0x18001a60f  call    cs:__imp_RtlCompareUnicodeString
0x18001a615  test    eax, eax
0x18001a617  jnz     short loc_18001A62D
0x18001a619  lea     rcx, [rdi+38h]
0x18001a61d  mov     r8b, 1; CaseInsensitive
0x18001a620  add     rcx, rbx; String1
0x18001a623  lea     rdx, [rsi+38h]; String2
0x18001a627  call    cs:__imp_RtlCompareUnicodeString
0x18001a62d  mov     rbx, [rsp+28h+arg_0]
0x18001a632  mov     rsi, [rsp+28h+arg_8]
0x18001a637  add     rsp, 20h
0x18001a63b  pop     rdi
0x18001a63c  retn
0x18001a63d  mov     rbx, [rsp+28h+arg_0]
0x18001a642  sub     eax, ecx
0x18001a644  mov     rsi, [rsp+28h+arg_8]
0x18001a649  add     rsp, 20h
0x18001a64d  pop     rdi
0x18001a64e  retn
```
