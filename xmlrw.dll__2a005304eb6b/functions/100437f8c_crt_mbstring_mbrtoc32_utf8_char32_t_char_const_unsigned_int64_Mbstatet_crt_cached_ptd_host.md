# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x100437f8c`
- end: `0x100438165`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `473`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100436c74`
- `0x100436cc0`

## callees

- `0x100426580`
- `0x100437f60`
- `0x100437f70`
- `0x100437f8c`

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

  v5 = &qword_100451DE8;
  v6 = 0;
  v7 = &word_10043D4A2;
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
0x100437f8c  push    rbx
0x100437f8e  push    rbp
0x100437f8f  push    rsi
0x100437f90  push    rdi
0x100437f91  push    r12
0x100437f93  push    r14
0x100437f95  push    r15
0x100437f97  sub     rsp, 40h
0x100437f9b  mov     rax, cs:__security_cookie
0x100437fa2  xor     rax, rsp
0x100437fa5  mov     [rsp+78h+var_48], rax
0x100437faa  mov     rsi, [rsp+78h+arg_20]
0x100437fb2  lea     r10, qword_100451DE8
0x100437fb9  xor     r11d, r11d
0x100437fbc  lea     rdi, word_10043D4A2
0x100437fc3  test    r9, r9
0x100437fc6  mov     rax, rdx
0x100437fc9  mov     r12, rdx
0x100437fcc  cmovnz  r10, r9
0x100437fd0  test    rdx, rdx
0x100437fd3  lea     ebp, [r11+1]
0x100437fd7  cmovnz  rdi, rdx
0x100437fdb  mov     r15d, ebp
0x100437fde  cmovnz  r15, r8
0x100437fe2  neg     rax
0x100437fe5  sbb     r14, r14
0x100437fe8  and     r14, rcx
0x100437feb  test    r15, r15
0x100437fee  jnz     short loc_100437FFC
0x100437ff0  mov     rax, 0FFFFFFFFFFFFFFFEh
0x100437ff7  jmp     loc_100438149
0x100437ffc  cmp     [r10+6], r11w
0x100438001  jnz     short loc_10043806B
0x100438003  movzx   r9d, byte ptr [rdi]
0x100438007  inc     rdi
0x10043800a  test    r9b, r9b
0x10043800d  js      short loc_100438026
0x10043800f  test    r14, r14
0x100438012  jz      short loc_100438017
0x100438014  mov     [r14], r9d
0x100438017  test    r9b, r9b
0x10043801a  setnz   r11b
0x10043801e  mov     rax, r11
0x100438021  jmp     loc_100438149
0x100438026  mov     al, r9b
0x100438029  and     al, 0E0h
0x10043802b  cmp     al, 0C0h
0x10043802d  jnz     short loc_100438034
0x10043802f  mov     r8b, 2
0x100438032  jmp     short loc_100438052
0x100438034  mov     al, r9b
0x100438037  and     al, 0F0h
0x100438039  cmp     al, 0E0h
0x10043803b  jnz     short loc_100438042
0x10043803d  mov     r8b, 3
0x100438040  jmp     short loc_100438052
0x100438042  mov     al, r9b
0x100438045  and     al, 0F8h
0x100438047  cmp     al, 0F0h
0x100438049  jnz     loc_10043813E
0x10043804f  mov     r8b, 4
0x100438052  movzx   eax, r8b
0x100438056  mov     ecx, 7
0x10043805b  sub     ecx, eax
0x10043805d  mov     edx, ebp
0x10043805f  shl     edx, cl
0x100438061  mov     bl, r8b
0x100438064  sub     edx, ebp
0x100438066  and     edx, r9d
0x100438069  jmp     short loc_100438094
0x10043806b  mov     r8b, [r10+4]; struct _Mbstatet *
0x10043806f  mov     edx, [r10]
0x100438072  mov     bl, [r10+6]
0x100438076  lea     eax, [r8-2]
0x10043807a  cmp     al, 2
0x10043807c  ja      loc_10043813E
0x100438082  cmp     bl, bpl
0x100438085  jb      loc_10043813E
0x10043808b  cmp     bl, r8b
0x10043808e  jnb     loc_10043813E
0x100438094  movzx   ebp, bl
0x100438097  cmp     rbp, r15
0x10043809a  mov     r9d, ebp
0x10043809d  cmovnb  r9, r15
0x1004380a1  jmp     short loc_1004380C1
0x1004380a3  movzx   ecx, byte ptr [rdi]
0x1004380a6  inc     rdi
0x1004380a9  mov     al, cl
0x1004380ab  and     al, 0C0h
0x1004380ad  cmp     al, 80h
0x1004380af  jnz     loc_10043813E
0x1004380b5  mov     eax, edx
0x1004380b7  and     ecx, 3Fh
0x1004380ba  shl     eax, 6
0x1004380bd  mov     edx, ecx
0x1004380bf  or      edx, eax
0x1004380c1  mov     rax, rdi
0x1004380c4  sub     rax, r12
0x1004380c7  cmp     rax, r9
0x1004380ca  jb      short loc_1004380A3
0x1004380cc  cmp     r9, rbp
0x1004380cf  jnb     short loc_1004380ED
0x1004380d1  movzx   eax, r8b
0x1004380d5  sub     bl, r9b
0x1004380d8  mov     [r10+4], ax
0x1004380dd  movzx   eax, bl
0x1004380e0  mov     [r10+6], ax
0x1004380e5  mov     [r10], edx
0x1004380e8  jmp     loc_100437FF0
0x1004380ed  lea     eax, [rdx-0D800h]
0x1004380f3  cmp     eax, 7FFh
0x1004380f8  jbe     short loc_10043813E
0x1004380fa  cmp     edx, 110000h
0x100438100  jnb     short loc_10043813E
0x100438102  movzx   eax, r8b
0x100438106  mov     [rsp+78h+var_58], 80h
0x10043810e  mov     [rsp+78h+var_54], 800h
0x100438116  mov     [rsp+78h+var_50], 10000h
0x10043811e  cmp     edx, [rsp+rax*4+78h+var_60]
0x100438122  jb      short loc_10043813E
0x100438124  test    r14, r14
0x100438127  jz      short loc_10043812C
0x100438129  mov     [r14], edx
0x10043812c  neg     edx
0x10043812e  mov     rdx, r10; unsigned __int64
0x100438131  sbb     rcx, rcx
0x100438134  and     rcx, rbp; this
0x100438137  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x10043813c  jmp     short loc_100438149
0x10043813e  mov     rdx, rsi; struct _Mbstatet *
0x100438141  mov     rcx, r10; this
0x100438144  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x100438149  mov     rcx, [rsp+78h+var_48]
0x10043814e  xor     rcx, rsp; StackCookie
0x100438151  call    __security_check_cookie
0x100438156  add     rsp, 40h
0x10043815a  pop     r15
0x10043815c  pop     r14
0x10043815e  pop     r12
0x100438160  pop     rdi
0x100438161  pop     rsi
0x100438162  pop     rbp
0x100438163  pop     rbx
0x100438164  retn
```
