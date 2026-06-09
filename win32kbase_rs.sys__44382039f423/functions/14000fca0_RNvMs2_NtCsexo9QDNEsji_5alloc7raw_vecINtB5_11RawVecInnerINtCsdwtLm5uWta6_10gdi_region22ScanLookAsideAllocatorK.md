# _RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCs7vXzV21FY6F_8gdi_rust

- ea: `0x14000fca0`
- end: `0x14000fd90`
- name: `_RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCs7vXzV21FY6F_8gdi_rust`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005340`

## callees

- `0x14000fca0`
- `0x140017a10`
- `0x140018ab0`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCs7vXzV21FY6F_8gdi_rust(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 result; // rax
  bool v6; // cf
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r11
  unsigned __int64 v9; // rsi
  __int64 v11; // [rsp+0h] [rbp-68h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-20h]

  result = 0x8000000000000001uLL;
  if ( a3 > (*a1 | (unsigned __int64)-(__int64)(a5 == 0)) - a2 )
  {
    if ( !a5 || (v6 = __CFADD__(a2, a3), v7 = a2 + a3, v6) )
    {
      result = 0;
    }
    else
    {
      v8 = 2 * *a1;
      if ( v7 > v8 )
        v8 = v7;
      v9 = 8;
      if ( a5 != 1 )
        v9 = 3LL * (a5 < 0x401) + 1;
      if ( v8 > v9 )
        v9 = v8;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
        &v12,
        a1,
        v9,
        a4,
        a5);
      if ( (_DWORD)v12 == 1 )
      {
        result = v13;
      }
      else
      {
        a1[1] = v13;
        *a1 = v9;
        result = 0x8000000000000001uLL;
      }
    }
  }
  if ( _security_cookie != ((unsigned __int64)&v11 ^ v14) )
    JUMPOUT(0x14000FD8FLL);
  return result;
}

```

## disassembly

```asm
0x14000fca0  push    rsi
0x14000fca1  push    rdi
0x14000fca2  push    rbx
0x14000fca3  sub     rsp, 50h
0x14000fca7  mov     r10, [rsp+68h+arg_20]
0x14000fcaf  mov     rax, cs:__security_cookie
0x14000fcb6  xor     rax, rsp
0x14000fcb9  mov     [rsp+68h+var_20], rax
0x14000fcbe  mov     rax, 8000000000000001h
0x14000fcc8  xor     esi, esi
0x14000fcca  cmp     r10, 1
0x14000fcce  sbb     rsi, rsi
0x14000fcd1  mov     r11, [rcx]
0x14000fcd4  or      rsi, r11
0x14000fcd7  sub     rsi, rdx
0x14000fcda  cmp     r8, rsi
0x14000fcdd  jbe     short loc_14000FCE6
0x14000fcdf  test    r10, r10
0x14000fce2  jnz     short loc_14000FD06
0x14000fce4  xor     eax, eax
0x14000fce6  mov     rcx, [rsp+68h+var_20]
0x14000fceb  xor     rcx, rsp
0x14000fcee  mov     r8, cs:__security_cookie
0x14000fcf5  cmp     r8, rcx
0x14000fcf8  jnz     loc_14000FD82
0x14000fcfe  add     rsp, 50h
0x14000fd02  pop     rbx
0x14000fd03  pop     rdi
0x14000fd04  pop     rsi
0x14000fd05  retn
0x14000fd06  add     r8, rdx
0x14000fd09  jb      short loc_14000FCE4
0x14000fd0b  mov     rdi, rax
0x14000fd0e  add     r11, r11
0x14000fd11  cmp     r8, r11
0x14000fd14  cmova   r11, r8
0x14000fd18  xor     eax, eax
0x14000fd1a  cmp     r10, 401h
0x14000fd21  setb    al
0x14000fd24  cmp     r10, 1
0x14000fd28  lea     rax, [rax+rax*2+1]
0x14000fd2d  mov     esi, 8
0x14000fd32  cmovnz  rsi, rax
0x14000fd36  cmp     r11, rsi
0x14000fd39  cmova   rsi, r11
0x14000fd3d  mov     [rsp+68h+var_48], r10
0x14000fd42  lea     rax, [rsp+68h+var_38]
0x14000fd47  mov     rdx, rcx
0x14000fd4a  mov     rcx, rax
0x14000fd4d  mov     rbx, rdx
0x14000fd50  mov     r8, rsi
0x14000fd53  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x14000fd58  cmp     dword ptr [rsp+68h+var_38], 1
0x14000fd5d  jnz     short loc_14000FD6E
0x14000fd5f  mov     rax, [rsp+68h+var_30]
0x14000fd64  mov     rdx, [rsp+68h+var_28]
0x14000fd69  jmp     loc_14000FCE6
0x14000fd6e  mov     rax, [rsp+68h+var_30]
0x14000fd73  mov     [rbx+8], rax
0x14000fd77  mov     [rbx], rsi
0x14000fd7a  mov     rax, rdi
0x14000fd7d  jmp     loc_14000FCE6
0x14000fd82  mov     rcx, [rsp+68h+var_20]
0x14000fd87  xor     rcx, rsp; StackCookie
0x14000fd8a  call    __security_check_cookie
```
