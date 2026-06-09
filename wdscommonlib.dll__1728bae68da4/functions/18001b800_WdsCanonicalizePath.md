# WdsCanonicalizePath

- ea: `0x18001b800`
- end: `0x18001b881`
- name: `WdsCanonicalizePath`
- size: `129`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18001b780`
- `0x18001cda0`

## callees

- `0x18000214c`
- `0x18001b800`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b858`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b858`
- `SHLWAPI!PathCanonicalizeW` at `0x18001b840`
- `SHLWAPI!PathCanonicalizeW` at `0x18001b840`

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
0x18001b800  mov     [rsp+arg_0], rbx
0x18001b805  mov     [rsp+arg_8], rbp
0x18001b80a  mov     [rsp+arg_10], rsi
0x18001b80f  push    rdi
0x18001b810  sub     rsp, 20h
0x18001b814  mov     rsi, rdx
0x18001b817  mov     rbp, rcx
0x18001b81a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b821  mov     ecx, 20Ah; unsigned __int64
0x18001b826  xor     ebx, ebx
0x18001b828  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b82d  mov     rdi, rax
0x18001b830  test    rax, rax
0x18001b833  jnz     short loc_18001B83A
0x18001b835  lea     ebx, [rax+8]
0x18001b838  jmp     short loc_18001B869
0x18001b83a  mov     rdx, rbp; pszPath
0x18001b83d  mov     rcx, rdi; pszBuf
0x18001b840  call    cs:__imp_PathCanonicalizeW
0x18001b847  nop     dword ptr [rax+rax+00h]
0x18001b84c  test    eax, eax
0x18001b84e  jnz     short loc_18001B866
0x18001b850  mov     rcx, rdi
0x18001b853  mov     ebx, 0A1h
0x18001b858  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b85f  nop     dword ptr [rax+rax+00h]
0x18001b864  jmp     short loc_18001B869
0x18001b866  mov     [rsi], rdi
0x18001b869  mov     rbp, [rsp+28h+arg_8]
0x18001b86e  mov     eax, ebx
0x18001b870  mov     rbx, [rsp+28h+arg_0]
0x18001b875  mov     rsi, [rsp+28h+arg_10]
0x18001b87a  add     rsp, 20h
0x18001b87e  pop     rdi
0x18001b87f  retn
```
