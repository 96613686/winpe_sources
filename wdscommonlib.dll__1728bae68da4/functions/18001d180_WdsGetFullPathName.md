# WdsGetFullPathName

- ea: `0x18001d180`
- end: `0x18001d2a8`
- name: `WdsGetFullPathName`
- size: `296`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800111e0`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001d180`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d274`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d274`
- `KERNEL32!GetFullPathNameW` at `0x18001d1c8`
- `KERNEL32!GetFullPathNameW` at `0x18001d23f`
- `KERNEL32!GetFullPathNameW` at `0x18001d1c8`
- `KERNEL32!GetFullPathNameW` at `0x18001d23f`
- `KERNEL32!GetLastError` at `0x18001d1da`
- `KERNEL32!GetLastError` at `0x18001d24f`
- `KERNEL32!GetLastError` at `0x18001d1da`
- `KERNEL32!GetLastError` at `0x18001d24f`

## pseudocode

```c
__int64 __fastcall WdsGetFullPathName(LPCWSTR lpFileName, WCHAR **a2)
{
  unsigned int v4; // ebx
  DWORD FullPathNameW; // eax
  unsigned __int64 v6; // rbp
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8

  v4 = 0;
  if ( lpFileName && *lpFileName && a2 )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    v6 = FullPathNameW;
    if ( FullPathNameW )
    {
      v10 = 2LL * FullPathNameW;
      if ( !is_mul_ok(v6, 2u) )
        v10 = -1;
      v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( v11 )
      {
        if ( GetFullPathNameW(lpFileName, v6, v11, 0) )
        {
          *a2 = v12;
        }
        else
        {
          LastError = GetLastError();
          v4 = ElValidateWin32_8(LastError, v14, v15, 4036);
          if ( !v4 )
            v4 = 31;
          operator delete(v12);
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v7 = GetLastError();
      v4 = ElValidateWin32_8(v7, v8, v9, 4016);
      if ( !v4 )
        return 31;
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x18001d180  mov     [rsp+arg_0], rbx
0x18001d185  mov     [rsp+arg_8], rbp
0x18001d18a  mov     [rsp+arg_10], rsi
0x18001d18f  push    rdi
0x18001d190  push    r14
0x18001d192  push    r15
0x18001d194  sub     rsp, 20h
0x18001d198  xor     r15d, r15d
0x18001d19b  mov     r14, rdx
0x18001d19e  mov     rdi, rcx
0x18001d1a1  mov     ebx, r15d
0x18001d1a4  test    rcx, rcx
0x18001d1a7  jz      loc_18001D287
0x18001d1ad  cmp     [rcx], r15w
0x18001d1b1  jz      loc_18001D287
0x18001d1b7  test    rdx, rdx
0x18001d1ba  jz      loc_18001D287
0x18001d1c0  xor     r9d, r9d; lpFilePart
0x18001d1c3  xor     r8d, r8d; lpBuffer
0x18001d1c6  xor     edx, edx; nBufferLength
0x18001d1c8  call    cs:__imp_GetFullPathNameW
0x18001d1cf  nop     dword ptr [rax+rax+00h]
0x18001d1d4  mov     ebp, eax
0x18001d1d6  test    eax, eax
0x18001d1d8  jnz     short loc_18001D205
0x18001d1da  call    cs:__imp_GetLastError
0x18001d1e1  nop     dword ptr [rax+rax+00h]
0x18001d1e6  mov     ecx, eax
0x18001d1e8  mov     r9d, 0FB0h
0x18001d1ee  call    ElValidateWin32_8
0x18001d1f3  mov     ebx, eax
0x18001d1f5  test    eax, eax
0x18001d1f7  jnz     loc_18001D28C
0x18001d1fd  lea     ebx, [rax+1Fh]
0x18001d200  jmp     loc_18001D28C
0x18001d205  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d20c  mov     eax, 2
0x18001d211  mul     rbp
0x18001d214  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d21b  cmovo   rax, rcx
0x18001d21f  mov     rcx, rax; unsigned __int64
0x18001d222  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d227  mov     rsi, rax
0x18001d22a  test    rax, rax
0x18001d22d  jnz     short loc_18001D234
0x18001d22f  lea     ebx, [rax+8]
0x18001d232  jmp     short loc_18001D28C
0x18001d234  xor     r9d, r9d; lpFilePart
0x18001d237  mov     r8, rsi; lpBuffer
0x18001d23a  mov     edx, ebp; nBufferLength
0x18001d23c  mov     rcx, rdi; lpFileName
0x18001d23f  call    cs:__imp_GetFullPathNameW
0x18001d246  nop     dword ptr [rax+rax+00h]
0x18001d24b  test    eax, eax
0x18001d24d  jnz     short loc_18001D282
0x18001d24f  call    cs:__imp_GetLastError
0x18001d256  nop     dword ptr [rax+rax+00h]
0x18001d25b  mov     ecx, eax
0x18001d25d  mov     r9d, 0FC4h
0x18001d263  call    ElValidateWin32_8
0x18001d268  mov     ebx, eax
0x18001d26a  test    eax, eax
0x18001d26c  jnz     short loc_18001D271
0x18001d26e  lea     ebx, [rax+1Fh]
0x18001d271  mov     rcx, rsi
0x18001d274  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d27b  nop     dword ptr [rax+rax+00h]
0x18001d280  jmp     short loc_18001D28C
0x18001d282  mov     [r14], rsi
0x18001d285  jmp     short loc_18001D28C
0x18001d287  mov     ebx, 57h ; 'W'
0x18001d28c  mov     rbp, [rsp+38h+arg_8]
0x18001d291  mov     eax, ebx
0x18001d293  mov     rbx, [rsp+38h+arg_0]
0x18001d298  mov     rsi, [rsp+38h+arg_10]
0x18001d29d  add     rsp, 20h
0x18001d2a1  pop     r15
0x18001d2a3  pop     r14
0x18001d2a5  pop     rdi
0x18001d2a6  retn
```
