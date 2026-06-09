# _RINvCs3PyRTeGQ7Na_12fallible_vec20try_with_capacity_inNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EEBW_

- ea: `0x14000f4c0`
- end: `0x14000f5a5`
- name: `_RINvCs3PyRTeGQ7Na_12fallible_vec20try_with_capacity_inNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EEBW_`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400101f0`

## callees

- `0x14000f4c0`
- `0x140017a10`
- `0x1400189a0`

## pseudocode

```c
__int64 *__fastcall RINvCs3PyRTeGQ7Na_12fallible_vec20try_with_capacity_inNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EEBW_(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // [rsp+0h] [rbp-78h] BYREF
  __int64 v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+38h] [rbp-40h]
  __int64 v8; // [rsp+40h] [rbp-38h]
  char v9; // [rsp+48h] [rbp-30h] BYREF
  __int128 v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  v6 = 0;
  v7 = 8;
  v8 = 0;
  if ( !a2 )
    goto LABEL_2;
  v3 = a1;
  v4 = 4;
  if ( a2 >= 5 )
    v4 = a2;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
    (unsigned int)&v9,
    (unsigned int)&v6,
    v4,
    8,
    48);
  if ( !v9 )
  {
    v7 = v10;
    v6 = v4;
    a1 = v3;
LABEL_2:
    a1[2] = v8;
    *a1 = v6;
    a1[1] = v7;
    goto LABEL_3;
  }
  a1 = v3;
  *(_OWORD *)(v3 + 1) = v10;
  *v3 = 0x8000000000000000uLL;
LABEL_3:
  if ( _security_cookie != ((unsigned __int64)&v5 ^ v11) )
    JUMPOUT(0x14000F5A4LL);
  return a1;
}

```

## disassembly

```asm
0x14000f4c0  push    rsi
0x14000f4c1  push    rdi
0x14000f4c2  sub     rsp, 68h
0x14000f4c6  mov     rax, cs:__security_cookie
0x14000f4cd  xor     rax, rsp
0x14000f4d0  mov     [rsp+78h+var_18], rax
0x14000f4d5  mov     [rsp+78h+var_48], 0
0x14000f4de  mov     [rsp+78h+var_40], 8
0x14000f4e7  mov     [rsp+78h+var_38], 0
0x14000f4f0  test    rdx, rdx
0x14000f4f3  jnz     short loc_14000F52D
0x14000f4f5  mov     rax, [rsp+78h+var_38]
0x14000f4fa  mov     [rcx+10h], rax
0x14000f4fe  mov     rax, [rsp+78h+var_48]
0x14000f503  mov     [rcx], rax
0x14000f506  mov     rax, [rsp+78h+var_40]
0x14000f50b  mov     [rcx+8], rax
0x14000f50f  mov     rax, [rsp+78h+var_18]
0x14000f514  xor     rax, rsp
0x14000f517  mov     rdx, cs:__security_cookie
0x14000f51e  cmp     rdx, rax
0x14000f521  jnz     short loc_14000F597
0x14000f523  mov     rax, rcx
0x14000f526  add     rsp, 68h
0x14000f52a  pop     rdi
0x14000f52b  pop     rsi
0x14000f52c  retn
0x14000f52d  mov     rdi, rcx
0x14000f530  cmp     rdx, 5
0x14000f534  mov     esi, 4
0x14000f539  cmovnb  rsi, rdx
0x14000f53d  mov     [rsp+78h+var_58], 30h ; '0'
0x14000f546  lea     rcx, [rsp+78h+var_30]
0x14000f54b  lea     rdx, [rsp+78h+var_48]
0x14000f550  mov     r9d, 8
0x14000f556  mov     r8, rsi
0x14000f559  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x14000f55e  cmp     [rsp+78h+var_30], 0
0x14000f563  jz      short loc_14000F580
0x14000f565  movups  xmm0, [rsp+78h+var_28]
0x14000f56a  mov     rcx, rdi
0x14000f56d  movups  xmmword ptr [rdi+8], xmm0
0x14000f571  mov     rax, 8000000000000000h
0x14000f57b  mov     [rdi], rax
0x14000f57e  jmp     short loc_14000F50F
0x14000f580  mov     rax, qword ptr [rsp+78h+var_28]
0x14000f585  mov     [rsp+78h+var_40], rax
0x14000f58a  mov     [rsp+78h+var_48], rsi
0x14000f58f  mov     rcx, rdi
0x14000f592  jmp     loc_14000F4F5
0x14000f597  mov     rcx, [rsp+78h+var_18]
0x14000f59c  xor     rcx, rsp; StackCookie
0x14000f59f  call    __security_check_cookie
```
