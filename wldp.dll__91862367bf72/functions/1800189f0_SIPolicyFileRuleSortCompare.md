# SIPolicyFileRuleSortCompare

- ea: `0x1800189f0`
- end: `0x180018a9b`
- name: `SIPolicyFileRuleSortCompare`
- size: `171`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800189f0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180018a30`
- `ntdll!RtlCompareUnicodeString` at `0x180018a4b`
- `ntdll!RtlCompareUnicodeString` at `0x180018a66`
- `ntdll!RtlCompareUnicodeString` at `0x180018a81`
- `ntdll!RtlCompareUnicodeString` at `0x180018a30`
- `ntdll!RtlCompareUnicodeString` at `0x180018a4b`
- `ntdll!RtlCompareUnicodeString` at `0x180018a66`
- `ntdll!RtlCompareUnicodeString` at `0x180018a81`

## pseudocode

```c
int __fastcall SIPolicyFileRuleSortCompare(char *a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  int v6; // ecx
  int v7; // eax
  int result; // eax

  v4 = 168LL * *a3;
  v5 = 168LL * *a2;
  v6 = *(_DWORD *)&a1[v4];
  v7 = *(_DWORD *)&a1[v5];
  if ( v7 != v6 )
    return v7 - v6;
  result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v5 + 8], (PCUNICODE_STRING)&a1[v4 + 8], 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v5 + 24], (PCUNICODE_STRING)&a1[v4 + 24], 1u);
    if ( !result )
    {
      result = RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v5 + 40], (PCUNICODE_STRING)&a1[v4 + 40], 1u);
      if ( !result )
        return RtlCompareUnicodeString((PCUNICODE_STRING)&a1[v5 + 56], (PCUNICODE_STRING)&a1[v4 + 56], 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800189f0  mov     [rsp+arg_0], rbx
0x1800189f5  mov     [rsp+arg_8], rsi
0x1800189fa  push    rdi
0x1800189fb  sub     rsp, 20h
0x1800189ff  mov     eax, [r8]
0x180018a02  mov     rbx, rcx
0x180018a05  imul    rdi, rax, 0A8h
0x180018a0c  mov     eax, [rdx]
0x180018a0e  imul    rsi, rax, 0A8h
0x180018a15  mov     ecx, [rdi+rcx]
0x180018a18  mov     eax, [rsi+rbx]
0x180018a1b  cmp     eax, ecx
0x180018a1d  jnz     short loc_180018A97
0x180018a1f  lea     rdx, [rbx+8]
0x180018a23  mov     r8b, 1; CaseInsensitive
0x180018a26  lea     rcx, [rbx+8]
0x180018a2a  add     rdx, rdi; String2
0x180018a2d  add     rcx, rsi; String1
0x180018a30  call    cs:__imp_RtlCompareUnicodeString
0x180018a36  test    eax, eax
0x180018a38  jnz     short loc_180018A87
0x180018a3a  lea     rdx, [rbx+18h]
0x180018a3e  mov     r8b, 1; CaseInsensitive
0x180018a41  lea     rcx, [rbx+18h]
0x180018a45  add     rdx, rdi; String2
0x180018a48  add     rcx, rsi; String1
0x180018a4b  call    cs:__imp_RtlCompareUnicodeString
0x180018a51  test    eax, eax
0x180018a53  jnz     short loc_180018A87
0x180018a55  lea     rdx, [rbx+28h]
0x180018a59  mov     r8b, 1; CaseInsensitive
0x180018a5c  lea     rcx, [rbx+28h]
0x180018a60  add     rdx, rdi; String2
0x180018a63  add     rcx, rsi; String1
0x180018a66  call    cs:__imp_RtlCompareUnicodeString
0x180018a6c  test    eax, eax
0x180018a6e  jnz     short loc_180018A87
0x180018a70  lea     rdx, [rbx+38h]
0x180018a74  mov     r8b, 1; CaseInsensitive
0x180018a77  lea     rcx, [rbx+38h]
0x180018a7b  add     rdx, rdi; String2
0x180018a7e  add     rcx, rsi; String1
0x180018a81  call    cs:__imp_RtlCompareUnicodeString
0x180018a87  mov     rbx, [rsp+28h+arg_0]
0x180018a8c  mov     rsi, [rsp+28h+arg_8]
0x180018a91  add     rsp, 20h
0x180018a95  pop     rdi
0x180018a96  retn
0x180018a97  sub     eax, ecx
0x180018a99  jmp     short loc_180018A87
```
