# IsWindowsOldPattern

- ea: `0x1800059f8`
- end: `0x180005a80`
- name: `IsWindowsOldPattern`
- size: `136`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004af0`

## callees

- `0x1800059f8`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180005a2b`
- `msvcrt!_wcsnicmp` at `0x180005a2b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180005a58`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180005a58`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180005a4b`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180005a4b`

## string_xrefs

- `0x180005a24`: `Windows.old(`

## pseudocode

```c
_BOOL8 __fastcall IsWindowsOldPattern(const wchar_t *a1)
{
  unsigned __int64 v2; // rax
  WCHAR *i; // rbx

  if ( a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
    if ( v2 >= 0xC && !_wcsnicmp(a1, L"Windows.old(", 0xCu) )
    {
      for ( i = (WCHAR *)(a1 + 12); *i; ++i )
      {
        if ( *i == 41 )
          return i[1] == 0;
        if ( !IsCharAlphaNumericW(*i) || IsCharAlphaW(*i) )
          return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800059f8  mov     [rsp+arg_0], rbx
0x1800059fd  push    rdi
0x1800059fe  sub     rsp, 20h
0x180005a02  xor     edi, edi
0x180005a04  mov     rbx, rcx
0x180005a07  test    rcx, rcx
0x180005a0a  jz      short loc_180005A73
0x180005a0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a10  inc     rax
0x180005a13  cmp     [rcx+rax*2], di
0x180005a17  jnz     short loc_180005A10
0x180005a19  mov     r8d, 0Ch; MaxCount
0x180005a1f  cmp     rax, r8
0x180005a22  jb      short loc_180005A73
0x180005a24  lea     rdx, aWindowsOld; "Windows.old("
0x180005a2b  call    cs:__imp__wcsnicmp
0x180005a31  test    eax, eax
0x180005a33  jnz     short loc_180005A73
0x180005a35  add     rbx, 18h
0x180005a39  cmp     di, [rbx]
0x180005a3c  jz      short loc_180005A73
0x180005a3e  mov     eax, 29h ; ')'
0x180005a43  cmp     ax, [rbx]
0x180005a46  jz      short loc_180005A68
0x180005a48  movzx   ecx, word ptr [rbx]; ch
0x180005a4b  call    cs:__imp_IsCharAlphaNumericW
0x180005a51  test    eax, eax
0x180005a53  jz      short loc_180005A73
0x180005a55  movzx   ecx, word ptr [rbx]; ch
0x180005a58  call    cs:__imp_IsCharAlphaW
0x180005a5e  test    eax, eax
0x180005a60  jnz     short loc_180005A73
0x180005a62  add     rbx, 2
0x180005a66  jmp     short loc_180005A39
0x180005a68  cmp     di, [rbx+2]
0x180005a6c  mov     eax, edi
0x180005a6e  setz    al
0x180005a71  jmp     short loc_180005A75
0x180005a73  xor     eax, eax
0x180005a75  mov     rbx, [rsp+28h+arg_0]
0x180005a7a  add     rsp, 20h
0x180005a7e  pop     rdi
0x180005a7f  retn
```
