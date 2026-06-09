# XEDefaultPathCanonicalize(wchar_t *,wchar_t const *)

- ea: `0x1005e6bc0`
- end: `0x1005e6ca1`
- name: `?XEDefaultPathCanonicalize@@YAHPEA_WPEB_W@Z`
- size: `225`
- prototype: `__int64 __fastcall(wchar_t *Path, LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1005e6cb0`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1005e6bc0`

## import_xrefs

- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x1005e6c2b`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x1005e6c2b`
- `SHLWAPI!PathCanonicalizeW` at `0x1005e6c02`
- `SHLWAPI!PathCanonicalizeW` at `0x1005e6c02`
- `SHLWAPI!PathIsRelativeW` at `0x1005e6c11`
- `SHLWAPI!PathIsRelativeW` at `0x1005e6c11`

## pseudocode

```c
BOOL __fastcall XEDefaultPathCanonicalize(wchar_t *Path, LPCWSTR pszPath)
{
  BOOL result; // eax
  BOOL v5; // esi
  __int64 v6; // rdi
  signed __int64 v7; // rcx
  wchar_t v8; // ax
  wchar_t *v9; // rcx
  wchar_t Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  result = PathCanonicalizeW(Path, pszPath);
  v5 = result;
  if ( result )
  {
    if ( PathIsRelativeW(Path) && (v6 = 260, _wfullpath(Buffer, Path, 0x104u)) )
    {
      v7 = (char *)Buffer - (char *)Path;
      do
      {
        if ( v6 == -2147483386 )
          break;
        v8 = *(wchar_t *)((char *)Path + v7);
        if ( !v8 )
          break;
        *Path++ = v8;
        --v6;
      }
      while ( v6 );
      v9 = Path - 1;
      if ( v6 )
        v9 = Path;
      *v9 = 0;
      return v6 != 0;
    }
    else
    {
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1005e6bc0  mov     [rsp+arg_10], rbx
0x1005e6bc5  mov     [rsp+arg_18], rsi
0x1005e6bca  push    rdi
0x1005e6bcb  sub     rsp, 240h
0x1005e6bd2  mov     rax, cs:__security_cookie
0x1005e6bd9  xor     rax, rsp
0x1005e6bdc  mov     [rsp+248h+var_18], rax
0x1005e6be4  mov     rdi, rdx
0x1005e6be7  mov     rbx, rcx
0x1005e6bea  xor     edx, edx; Val
0x1005e6bec  lea     rcx, [rsp+248h+Buffer]; void *
0x1005e6bf1  mov     r8d, 208h; Size
0x1005e6bf7  call    memset_0
0x1005e6bfc  mov     rdx, rdi; pszPath
0x1005e6bff  mov     rcx, rbx; pszBuf
0x1005e6c02  call    cs:__imp_PathCanonicalizeW
0x1005e6c08  mov     esi, eax
0x1005e6c0a  test    eax, eax
0x1005e6c0c  jz      short loc_1005E6C7C
0x1005e6c0e  mov     rcx, rbx; pszPath
0x1005e6c11  call    cs:__imp_PathIsRelativeW
0x1005e6c17  test    eax, eax
0x1005e6c19  jz      short loc_1005E6C7A
0x1005e6c1b  mov     edi, 104h
0x1005e6c20  lea     rcx, [rsp+248h+Buffer]; Buffer
0x1005e6c25  mov     r8d, edi; BufferCount
0x1005e6c28  mov     rdx, rbx; Path
0x1005e6c2b  call    cs:__imp__wfullpath
0x1005e6c31  test    rax, rax
0x1005e6c34  jz      short loc_1005E6C7A
0x1005e6c36  lea     rcx, [rsp+248h+Buffer]
0x1005e6c3b  sub     rcx, rbx
0x1005e6c3e  xchg    ax, ax
0x1005e6c40  lea     rax, [rdi+7FFFFEFAh]
0x1005e6c47  test    rax, rax
0x1005e6c4a  jz      short loc_1005E6C62
0x1005e6c4c  movzx   eax, word ptr [rbx+rcx]
0x1005e6c50  test    ax, ax
0x1005e6c53  jz      short loc_1005E6C62
0x1005e6c55  mov     [rbx], ax
0x1005e6c58  add     rbx, 2
0x1005e6c5c  sub     rdi, 1
0x1005e6c60  jnz     short loc_1005E6C40
0x1005e6c62  test    rdi, rdi
0x1005e6c65  lea     rcx, [rbx-2]
0x1005e6c69  cmovnz  rcx, rbx
0x1005e6c6d  xor     eax, eax
0x1005e6c6f  test    rdi, rdi
0x1005e6c72  mov     [rcx], ax
0x1005e6c75  setnz   al
0x1005e6c78  jmp     short loc_1005E6C7C
0x1005e6c7a  mov     eax, esi
0x1005e6c7c  mov     rcx, [rsp+248h+var_18]
0x1005e6c84  xor     rcx, rsp; StackCookie
0x1005e6c87  call    __security_check_cookie
0x1005e6c8c  lea     r11, [rsp+248h+var_8]
0x1005e6c94  mov     rbx, [r11+20h]
0x1005e6c98  mov     rsi, [r11+28h]
0x1005e6c9c  mov     rsp, r11
0x1005e6c9f  pop     rdi
0x1005e6ca0  retn
```
