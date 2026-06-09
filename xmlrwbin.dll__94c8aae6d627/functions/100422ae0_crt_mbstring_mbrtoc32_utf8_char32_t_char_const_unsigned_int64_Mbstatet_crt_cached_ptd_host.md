# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x100422ae0`
- end: `0x100422cb9`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `473`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100421cec`
- `0x100421d38`

## callees

- `0x100416590`
- `0x100422ab4`
- `0x100422ac4`
- `0x100422ae0`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtoc32_utf8(
        unsigned __int64 this,
        char32_t *a2,
        unsigned __int64 a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 *v5; // r10
  __int64 v6; // r11
  __int16 *v7; // rdi
  unsigned __int64 v9; // r15
  _DWORD *v10; // r14
  int v12; // r9d
  unsigned __int8 v13; // bl
  unsigned int v14; // edx
  unsigned __int64 v15; // r9
  char v16; // cl
  _DWORD v17[6]; // [rsp+18h] [rbp-60h]

  v5 = &qword_100435E70;
  v6 = 0;
  v7 = &word_100427012;
  if ( a4 )
    v5 = a4;
  if ( a2 )
    v7 = (__int16 *)a2;
  v9 = 1;
  if ( a2 )
    v9 = a3;
  v10 = (_DWORD *)(this & -(__int64)(a2 != 0));
  if ( !v9 )
    return -2;
  if ( !*((_WORD *)v5 + 3) )
  {
    v12 = *(unsigned __int8 *)v7;
    v7 = (__int16 *)((char *)v7 + 1);
    if ( (v12 & 0x80u) == 0 )
    {
      if ( v10 )
        *v10 = v12;
      LOBYTE(v6) = (_BYTE)v12 != 0;
      return v6;
    }
    if ( (v12 & 0xE0) == 0xC0 )
    {
      LOBYTE(a3) = 2;
LABEL_20:
      v13 = a3;
      v14 = v12 & ((1 << (7 - a3)) - 1);
      goto LABEL_24;
    }
    if ( (v12 & 0xF0) == 0xE0 )
    {
      LOBYTE(a3) = 3;
      goto LABEL_20;
    }
    if ( (v12 & 0xF8) == 0xF0 )
    {
      LOBYTE(a3) = 4;
      goto LABEL_20;
    }
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  }
  LOBYTE(a3) = *((_BYTE *)v5 + 4);
  v14 = *(_DWORD *)v5;
  v13 = *((_BYTE *)v5 + 6);
  if ( (unsigned __int8)(a3 - 2) > 2u || !v13 || v13 >= (unsigned __int8)a3 )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
LABEL_24:
  v15 = v13;
  if ( v13 >= v9 )
    v15 = v9;
  while ( (char *)v7 - (char *)a2 < v15 )
  {
    v16 = *(_BYTE *)v7;
    v7 = (__int16 *)((char *)v7 + 1);
    if ( (v16 & 0xC0) != 0x80 )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
    v14 = (v14 << 6) | v16 & 0x3F;
  }
  if ( v15 < v13 )
  {
    *((_WORD *)v5 + 2) = (unsigned __int8)a3;
    *((_WORD *)v5 + 3) = (unsigned __int8)(v13 - v15);
    *(_DWORD *)v5 = v14;
    return -2;
  }
  if ( v14 - 55296 <= 0x7FF )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  if ( v14 >= 0x110000 )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  v17[2] = 128;
  v17[3] = 2048;
  v17[4] = 0x10000;
  if ( v14 < v17[(unsigned __int8)a3] )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  if ( v10 )
    *v10 = v14;
  return __crt_mbstring::reset_and_return(
           (__crt_mbstring *)(v13 & (unsigned __int64)-(__int64)(v14 != 0)),
           (unsigned __int64)v5,
           (struct _Mbstatet *)a3);
}

```

## disassembly

```asm
0x100422ae0  push    rbx
0x100422ae2  push    rbp
0x100422ae3  push    rsi
0x100422ae4  push    rdi
0x100422ae5  push    r12
0x100422ae7  push    r14
0x100422ae9  push    r15
0x100422aeb  sub     rsp, 40h
0x100422aef  mov     rax, cs:__security_cookie
0x100422af6  xor     rax, rsp
0x100422af9  mov     [rsp+78h+var_48], rax
0x100422afe  mov     rsi, [rsp+78h+arg_20]
0x100422b06  lea     r10, qword_100435E70
0x100422b0d  xor     r11d, r11d
0x100422b10  lea     rdi, word_100427012
0x100422b17  test    r9, r9
0x100422b1a  mov     rax, rdx
0x100422b1d  mov     r12, rdx
0x100422b20  cmovnz  r10, r9
0x100422b24  test    rdx, rdx
0x100422b27  lea     ebp, [r11+1]
0x100422b2b  cmovnz  rdi, rdx
0x100422b2f  mov     r15d, ebp
0x100422b32  cmovnz  r15, r8
0x100422b36  neg     rax
0x100422b39  sbb     r14, r14
0x100422b3c  and     r14, rcx
0x100422b3f  test    r15, r15
0x100422b42  jnz     short loc_100422B50
0x100422b44  mov     rax, 0FFFFFFFFFFFFFFFEh
0x100422b4b  jmp     loc_100422C9D
0x100422b50  cmp     [r10+6], r11w
0x100422b55  jnz     short loc_100422BBF
0x100422b57  movzx   r9d, byte ptr [rdi]
0x100422b5b  inc     rdi
0x100422b5e  test    r9b, r9b
0x100422b61  js      short loc_100422B7A
0x100422b63  test    r14, r14
0x100422b66  jz      short loc_100422B6B
0x100422b68  mov     [r14], r9d
0x100422b6b  test    r9b, r9b
0x100422b6e  setnz   r11b
0x100422b72  mov     rax, r11
0x100422b75  jmp     loc_100422C9D
0x100422b7a  mov     al, r9b
0x100422b7d  and     al, 0E0h
0x100422b7f  cmp     al, 0C0h
0x100422b81  jnz     short loc_100422B88
0x100422b83  mov     r8b, 2
0x100422b86  jmp     short loc_100422BA6
0x100422b88  mov     al, r9b
0x100422b8b  and     al, 0F0h
0x100422b8d  cmp     al, 0E0h
0x100422b8f  jnz     short loc_100422B96
0x100422b91  mov     r8b, 3
0x100422b94  jmp     short loc_100422BA6
0x100422b96  mov     al, r9b
0x100422b99  and     al, 0F8h
0x100422b9b  cmp     al, 0F0h
0x100422b9d  jnz     loc_100422C92
0x100422ba3  mov     r8b, 4
0x100422ba6  movzx   eax, r8b
0x100422baa  mov     ecx, 7
0x100422baf  sub     ecx, eax
0x100422bb1  mov     edx, ebp
0x100422bb3  shl     edx, cl
0x100422bb5  mov     bl, r8b
0x100422bb8  sub     edx, ebp
0x100422bba  and     edx, r9d
0x100422bbd  jmp     short loc_100422BE8
0x100422bbf  mov     r8b, [r10+4]; struct _Mbstatet *
0x100422bc3  mov     edx, [r10]
0x100422bc6  mov     bl, [r10+6]
0x100422bca  lea     eax, [r8-2]
0x100422bce  cmp     al, 2
0x100422bd0  ja      loc_100422C92
0x100422bd6  cmp     bl, bpl
0x100422bd9  jb      loc_100422C92
0x100422bdf  cmp     bl, r8b
0x100422be2  jnb     loc_100422C92
0x100422be8  movzx   ebp, bl
0x100422beb  cmp     rbp, r15
0x100422bee  mov     r9d, ebp
0x100422bf1  cmovnb  r9, r15
0x100422bf5  jmp     short loc_100422C15
0x100422bf7  movzx   ecx, byte ptr [rdi]
0x100422bfa  inc     rdi
0x100422bfd  mov     al, cl
0x100422bff  and     al, 0C0h
0x100422c01  cmp     al, 80h
0x100422c03  jnz     loc_100422C92
0x100422c09  mov     eax, edx
0x100422c0b  and     ecx, 3Fh
0x100422c0e  shl     eax, 6
0x100422c11  mov     edx, ecx
0x100422c13  or      edx, eax
0x100422c15  mov     rax, rdi
0x100422c18  sub     rax, r12
0x100422c1b  cmp     rax, r9
0x100422c1e  jb      short loc_100422BF7
0x100422c20  cmp     r9, rbp
0x100422c23  jnb     short loc_100422C41
0x100422c25  movzx   eax, r8b
0x100422c29  sub     bl, r9b
0x100422c2c  mov     [r10+4], ax
0x100422c31  movzx   eax, bl
0x100422c34  mov     [r10+6], ax
0x100422c39  mov     [r10], edx
0x100422c3c  jmp     loc_100422B44
0x100422c41  lea     eax, [rdx-0D800h]
0x100422c47  cmp     eax, 7FFh
0x100422c4c  jbe     short loc_100422C92
0x100422c4e  cmp     edx, 110000h
0x100422c54  jnb     short loc_100422C92
0x100422c56  movzx   eax, r8b
0x100422c5a  mov     [rsp+78h+var_58], 80h
0x100422c62  mov     [rsp+78h+var_54], 800h
0x100422c6a  mov     [rsp+78h+var_50], 10000h
0x100422c72  cmp     edx, [rsp+rax*4+78h+var_60]
0x100422c76  jb      short loc_100422C92
0x100422c78  test    r14, r14
0x100422c7b  jz      short loc_100422C80
0x100422c7d  mov     [r14], edx
0x100422c80  neg     edx
0x100422c82  mov     rdx, r10; unsigned __int64
0x100422c85  sbb     rcx, rcx
0x100422c88  and     rcx, rbp; this
0x100422c8b  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x100422c90  jmp     short loc_100422C9D
0x100422c92  mov     rdx, rsi; struct _Mbstatet *
0x100422c95  mov     rcx, r10; this
0x100422c98  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x100422c9d  mov     rcx, [rsp+78h+var_48]
0x100422ca2  xor     rcx, rsp; StackCookie
0x100422ca5  call    __security_check_cookie
0x100422caa  add     rsp, 40h
0x100422cae  pop     r15
0x100422cb0  pop     r14
0x100422cb2  pop     r12
0x100422cb4  pop     rdi
0x100422cb5  pop     rsi
0x100422cb6  pop     rbp
0x100422cb7  pop     rbx
0x100422cb8  retn
```
