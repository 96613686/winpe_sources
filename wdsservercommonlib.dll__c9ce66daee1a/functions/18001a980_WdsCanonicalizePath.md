# WdsCanonicalizePath

- ea: `0x18001a980`
- end: `0x18001a9fa`
- name: `WdsCanonicalizePath`
- size: `122`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18001a900`
- `0x18001bec0`

## callees

- `0x18000179c`
- `0x18001a980`
- `0x18002e468`

## import_xrefs

- `SHLWAPI!PathCanonicalizeW` at `0x18001a9c0`
- `SHLWAPI!PathCanonicalizeW` at `0x18001a9c0`

## pseudocode

```c
__int64 __fastcall WdsCanonicalizePath(LPCWSTR pszPath, WCHAR **a2)
{
  unsigned int v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rdi

  v4 = 0;
  v5 = (WCHAR *)operator new[](0x20Au, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    if ( PathCanonicalizeW(v5, pszPath) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = 161;
      operator delete(v6);
    }
  }
  else
  {
    return 8;
  }
  return v4;
}

```

## disassembly

```asm
0x18001a980  mov     [rsp+arg_0], rbx
0x18001a985  mov     [rsp+arg_8], rbp
0x18001a98a  mov     [rsp+arg_10], rsi
0x18001a98f  push    rdi
0x18001a990  sub     rsp, 20h
0x18001a994  mov     rsi, rdx
0x18001a997  mov     rbp, rcx
0x18001a99a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a9a1  mov     ecx, 20Ah; unsigned __int64
0x18001a9a6  xor     ebx, ebx
0x18001a9a8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a9ad  mov     rdi, rax
0x18001a9b0  test    rax, rax
0x18001a9b3  jnz     short loc_18001A9BA
0x18001a9b5  lea     ebx, [rax+8]
0x18001a9b8  jmp     short loc_18001A9E2
0x18001a9ba  mov     rdx, rbp; pszPath
0x18001a9bd  mov     rcx, rdi; pszBuf
0x18001a9c0  call    cs:__imp_PathCanonicalizeW
0x18001a9c7  nop     dword ptr [rax+rax+00h]
0x18001a9cc  test    eax, eax
0x18001a9ce  jnz     short loc_18001A9DF
0x18001a9d0  mov     rcx, rdi; lpMem
0x18001a9d3  mov     ebx, 0A1h
0x18001a9d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a9dd  jmp     short loc_18001A9E2
0x18001a9df  mov     [rsi], rdi
0x18001a9e2  mov     rbp, [rsp+28h+arg_8]
0x18001a9e7  mov     eax, ebx
0x18001a9e9  mov     rbx, [rsp+28h+arg_0]
0x18001a9ee  mov     rsi, [rsp+28h+arg_10]
0x18001a9f3  add     rsp, 20h
0x18001a9f7  pop     rdi
0x18001a9f8  retn
```
