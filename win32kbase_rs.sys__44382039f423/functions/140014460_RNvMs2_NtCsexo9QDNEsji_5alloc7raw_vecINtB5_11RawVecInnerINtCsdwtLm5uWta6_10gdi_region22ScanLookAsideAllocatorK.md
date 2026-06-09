# _RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCsdcpJtfrLhSH_7rgncore

- ea: `0x140014460`
- end: `0x140014559`
- name: `_RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCsdcpJtfrLhSH_7rgncore`
- size: `249`
- prototype: `unsigned __int64 __fastcall(unsigned __int64 *, __int64, unsigned __int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ca10`

## callees

- `0x140014460`
- `0x140017a10`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCsdcpJtfrLhSH_7rgncore(
        unsigned __int64 *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 result; // rax
  unsigned __int64 v7; // rdx
  bool v8; // cf
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rsi
  __int64 v13; // [rsp+0h] [rbp-68h] BYREF
  int v14; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-30h]
  __int64 v16; // [rsp+48h] [rbp-20h]

  result = 0x8000000000000001uLL;
  v7 = *a1;
  if ( a3 > (*a1 | -(__int64)(a5 == 0)) - a2 )
  {
    if ( !a5 || (v8 = __CFADD__(a2, a3), v9 = a2 + a3, v8) )
    {
      result = 0;
    }
    else
    {
      v10 = 2 * v7;
      if ( v9 > 2 * v7 )
        v10 = v9;
      v11 = 8;
      if ( a5 != 1 )
        v11 = 3LL * (a5 < 0x401) + 1;
      if ( v10 > v11 )
        v11 = v10;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        &v14,
        v7,
        a1[1],
        v11,
        a4,
        a5);
      if ( v14 == 1 )
      {
        result = v15;
      }
      else
      {
        a1[1] = v15;
        *a1 = v11;
        result = 0x8000000000000001uLL;
      }
    }
  }
  if ( _security_cookie != ((unsigned __int64)&v13 ^ v16) )
    JUMPOUT(0x140014558LL);
  return result;
}

```

## disassembly

```asm
0x140014460  push    rsi
0x140014461  push    rdi
0x140014462  push    rbx
0x140014463  sub     rsp, 50h
0x140014467  mov     r10, rdx
0x14001446a  mov     r11, [rsp+68h+arg_20]
0x140014472  mov     rax, cs:__security_cookie
0x140014479  xor     rax, rsp
0x14001447c  mov     [rsp+68h+var_20], rax
0x140014481  mov     rax, 8000000000000001h
0x14001448b  xor     esi, esi
0x14001448d  cmp     r11, 1
0x140014491  sbb     rsi, rsi
0x140014494  mov     rdx, [rcx]
0x140014497  or      rsi, rdx
0x14001449a  sub     rsi, r10
0x14001449d  cmp     r8, rsi
0x1400144a0  jbe     short loc_1400144A9
0x1400144a2  test    r11, r11
0x1400144a5  jnz     short loc_1400144C9
0x1400144a7  xor     eax, eax
0x1400144a9  mov     rcx, [rsp+68h+var_20]
0x1400144ae  xor     rcx, rsp
0x1400144b1  mov     r8, cs:__security_cookie
0x1400144b8  cmp     r8, rcx
0x1400144bb  jnz     loc_14001454B
0x1400144c1  add     rsp, 50h
0x1400144c5  pop     rbx
0x1400144c6  pop     rdi
0x1400144c7  pop     rsi
0x1400144c8  retn
0x1400144c9  add     r8, r10
0x1400144cc  jb      short loc_1400144A7
0x1400144ce  mov     rdi, rax
0x1400144d1  lea     rax, [rdx+rdx]
0x1400144d5  cmp     r8, rax
0x1400144d8  cmova   rax, r8
0x1400144dc  xor     r8d, r8d
0x1400144df  cmp     r11, 401h
0x1400144e6  setb    r8b
0x1400144ea  cmp     r11, 1
0x1400144ee  lea     r8, [r8+r8*2+1]
0x1400144f3  mov     esi, 8
0x1400144f8  cmovnz  rsi, r8
0x1400144fc  cmp     rax, rsi
0x1400144ff  cmova   rsi, rax
0x140014503  mov     rbx, rcx
0x140014506  mov     r8, [rcx+8]
0x14001450a  mov     [rsp+68h+var_40], r11
0x14001450f  mov     [rsp+68h+var_48], r9
0x140014514  lea     rcx, [rsp+68h+var_38]
0x140014519  mov     r9, rsi
0x14001451c  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140014521  cmp     [rsp+68h+var_38], 1
0x140014526  jnz     short loc_140014537
0x140014528  mov     rax, [rsp+68h+var_30]
0x14001452d  mov     rdx, [rsp+68h+var_28]
0x140014532  jmp     loc_1400144A9
0x140014537  mov     rax, [rsp+68h+var_30]
0x14001453c  mov     [rbx+8], rax
0x140014540  mov     [rbx], rsi
0x140014543  mov     rax, rdi
0x140014546  jmp     loc_1400144A9
0x14001454b  mov     rcx, [rsp+68h+var_20]
0x140014550  xor     rcx, rsp; StackCookie
0x140014553  call    __security_check_cookie
```
