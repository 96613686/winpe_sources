# _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecNtB5_11RawVecInner11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263

- ea: `0x140018c00`
- end: `0x140018cb1`
- name: `_RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecNtB5_11RawVecInner11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003860`
- `0x1400147a0`
- `0x1400160b0`

## callees

- `0x14000fbf0`
- `0x14000fc30`
- `0x140017450`
- `0x140018c00`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecNtB5_11RawVecInner11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
        __int64 *a1,
        __int64 a2,
        void *a3,
        unsigned __int64 a4,
        __int64 a5,
        unsigned __int64 a6)
{
  __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  __int64 result; // rax
  __int64 v11; // rax

  v7 = a4 * a6;
  v8 = 0x8000000000000000uLL - a5;
  LOBYTE(v8) = (a4 * (unsigned __int128)a6) >> 64 != 0 || a4 * a6 > 0x8000000000000000uLL - a5;
  v9 = 1;
  if ( !(_BYTE)v8 )
  {
    if ( a2 )
    {
      v11 = RNvCskrXTfrW5pjd_7___rustc14___rust_realloc(a3, a2 * a6);
      if ( !v11 )
        goto LABEL_8;
    }
    else if ( v7 )
    {
      RNvCskrXTfrW5pjd_7___rustc35___rust_no_alloc_shim_is_unstable_v2(v8);
      v11 = RNvCskrXTfrW5pjd_7___rustc12___rust_alloc(v7, a5);
      if ( !v11 )
      {
LABEL_8:
        a1[1] = a5;
        result = 2;
        goto LABEL_11;
      }
    }
    else
    {
      v11 = a5;
    }
    a1[1] = v11;
    result = 2;
    v9 = 0;
    goto LABEL_11;
  }
  result = 1;
  v7 = 0;
LABEL_11:
  a1[result] = v7;
  *a1 = v9;
  return result * 8;
}

```

## disassembly

```asm
0x140018c00  push    r14
0x140018c02  push    rsi
0x140018c03  push    rdi
0x140018c04  push    rbx
0x140018c05  sub     rsp, 28h
0x140018c09  mov     r11, rdx
0x140018c0c  mov     rsi, rcx
0x140018c0f  mov     rbx, [rsp+48h+arg_20]
0x140018c14  mov     r10, [rsp+48h+arg_28]
0x140018c19  mov     rax, r10
0x140018c1c  mul     r9
0x140018c1f  mov     rdi, rax
0x140018c22  seto    al
0x140018c25  mov     rcx, 8000000000000000h
0x140018c2f  sub     rcx, rbx
0x140018c32  cmp     rdi, rcx
0x140018c35  setnbe  cl
0x140018c38  or      cl, al
0x140018c3a  mov     r14d, 1
0x140018c40  jz      short loc_140018C4B
0x140018c42  mov     eax, 8
0x140018c47  xor     edi, edi
0x140018c49  jmp     short loc_140018CA0
0x140018c4b  test    r11, r11
0x140018c4e  jz      short loc_140018C6C
0x140018c50  imul    r10, r11
0x140018c54  mov     rcx, r8; Src
0x140018c57  mov     rdx, r10; Size
0x140018c5a  mov     r8, rbx
0x140018c5d  mov     r9, rdi
0x140018c60  call    _RNvCskrXTfrW5pjd_7___rustc14___rust_realloc
0x140018c65  test    rax, rax
0x140018c68  jnz     short loc_140018C94
0x140018c6a  jmp     short loc_140018C86
0x140018c6c  test    rdi, rdi
0x140018c6f  jz      short loc_140018C91
0x140018c71  call    _RNvCskrXTfrW5pjd_7___rustc35___rust_no_alloc_shim_is_unstable_v2
0x140018c76  mov     rcx, rdi
0x140018c79  mov     rdx, rbx
0x140018c7c  call    _RNvCskrXTfrW5pjd_7___rustc12___rust_alloc
0x140018c81  test    rax, rax
0x140018c84  jnz     short loc_140018C94
0x140018c86  mov     [rsi+8], rbx
0x140018c8a  mov     eax, 10h
0x140018c8f  jmp     short loc_140018CA0
0x140018c91  mov     rax, rbx
0x140018c94  mov     [rsi+8], rax
0x140018c98  mov     eax, 10h
0x140018c9d  xor     r14d, r14d
0x140018ca0  mov     [rsi+rax], rdi
0x140018ca4  mov     [rsi], r14
0x140018ca7  add     rsp, 28h
0x140018cab  pop     rbx
0x140018cac  pop     rdi
0x140018cad  pop     rsi
0x140018cae  pop     r14
0x140018cb0  retn
```
