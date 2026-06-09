# __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x100436cc0`
- end: `0x100436e62`
- name: `?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `418`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, wchar_t *, const char **, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1004344e8`

## callees

- `0x100436cc0`
- `0x100437f8c`

## pseudocode

```c
__int64 __fastcall __crt_mbstring::__mbsrtowcs_utf8(
        __crt_mbstring *this,
        wchar_t *a2,
        const char **a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 v5; // rdi
  const char **v7; // rbp
  __crt_mbstring *v10; // rbx
  struct _Mbstatet *v11; // r13
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  __int16 v14; // cx
  unsigned int v15; // ecx
  __int64 i; // rbx
  struct _Mbstatet *v18; // rbp
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rax
  unsigned int v21; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a3;
  if ( !this )
  {
    v18 = a5;
    for ( i = 0; ; ++i )
    {
      if ( *(_BYTE *)v5 )
        v19 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v19 = 1;
      v20 = __crt_mbstring::__mbrtoc32_utf8(0, (char32_t *)v5, v19, a4, v18);
      if ( v20 == -1 )
        break;
      if ( !v20 )
        return i;
      if ( v20 == 4 )
        ++i;
      v5 += v20;
    }
    LOBYTE(v18[6]._Wchar) = 1;
    *(_DWORD *)&v18[5]._Byte = 42;
    return -1;
  }
  v10 = this;
  if ( a3 )
  {
    v11 = a5;
    while ( 1 )
    {
      if ( *(_BYTE *)v5 )
        v12 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v12 = 1;
      v13 = __crt_mbstring::__mbrtoc32_utf8((unsigned __int64)&v21, (char32_t *)v5, v12, a4, v11);
      if ( v13 == -1 )
        break;
      if ( !v13 )
      {
        v5 = 0;
        *(_WORD *)v10 = 0;
        goto LABEL_15;
      }
      v14 = v21;
      if ( v21 > 0xFFFF )
      {
        if ( (unsigned __int64)v7 <= 1 )
          goto LABEL_15;
        v15 = v21 - 0x10000;
        v21 = v15;
        v7 = (const char **)((char *)v7 - 1);
        *(_WORD *)v10 = (v15 >> 10) | 0xD800;
        v10 = (__crt_mbstring *)((char *)v10 + 2);
        v14 = v15 & 0x3FF | 0xDC00;
      }
      *(_WORD *)v10 = v14;
      v5 += v13;
      v10 = (__crt_mbstring *)((char *)v10 + 2);
      v7 = (const char **)((char *)v7 - 1);
      if ( !v7 )
        goto LABEL_15;
    }
    *(_QWORD *)a2 = v5;
    LOBYTE(v11[6]._Wchar) = 1;
    *(_DWORD *)&v11[5]._Byte = 42;
    return -1;
  }
LABEL_15:
  *(_QWORD *)a2 = v5;
  return (v10 - this) >> 1;
}

```

## disassembly

```asm
0x100436cc0  mov     [rsp+arg_8], rbx
0x100436cc5  mov     [rsp+arg_10], rbp
0x100436cca  push    rdi
0x100436ccb  push    r12
0x100436ccd  push    r13
0x100436ccf  push    r14
0x100436cd1  push    r15
0x100436cd3  sub     rsp, 30h
0x100436cd7  mov     rdi, [rdx]
0x100436cda  xor     eax, eax
0x100436cdc  mov     r12, r9
0x100436cdf  mov     rbp, r8
0x100436ce2  mov     r15, rdx
0x100436ce5  mov     r14, rcx
0x100436ce8  test    rcx, rcx
0x100436ceb  jz      loc_100436DD8
0x100436cf1  mov     rbx, rcx
0x100436cf4  test    r8, r8
0x100436cf7  jz      loc_100436DAD
0x100436cfd  mov     r13, [rsp+58h+arg_20]
0x100436d05  cmp     [rdi], al
0x100436d07  jnz     short loc_100436D11
0x100436d09  mov     r8d, 1
0x100436d0f  jmp     short loc_100436D2D
0x100436d11  cmp     [rdi+1], al
0x100436d14  jnz     short loc_100436D1E
0x100436d16  mov     r8d, 2
0x100436d1c  jmp     short loc_100436D2D
0x100436d1e  mov     al, [rdi+2]
0x100436d21  neg     al
0x100436d23  sbb     r8, r8
0x100436d26  neg     r8
0x100436d29  add     r8, 3; char *
0x100436d2d  mov     r9, r12; unsigned __int64
0x100436d30  mov     [rsp+58h+var_38], r13; struct _Mbstatet *
0x100436d35  mov     rdx, rdi; char32_t *
0x100436d38  lea     rcx, [rsp+58h+arg_0]; this
0x100436d3d  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100436d42  mov     rdx, rax
0x100436d45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100436d49  jz      short loc_100436DC6
0x100436d4b  xor     eax, eax
0x100436d4d  test    rdx, rdx
0x100436d50  jz      short loc_100436DBE
0x100436d52  mov     ecx, [rsp+58h+arg_0]
0x100436d56  cmp     ecx, 0FFFFh
0x100436d5c  jbe     short loc_100436D99
0x100436d5e  cmp     rbp, 1
0x100436d62  jbe     short loc_100436DAD
0x100436d64  add     ecx, 0FFFF0000h
0x100436d6a  mov     r8d, 0D800h
0x100436d70  mov     eax, ecx
0x100436d72  mov     [rsp+58h+arg_0], ecx
0x100436d76  shr     eax, 0Ah
0x100436d79  dec     rbp
0x100436d7c  or      ax, r8w
0x100436d80  mov     [rbx], ax
0x100436d83  mov     eax, 3FFh
0x100436d88  and     cx, ax
0x100436d8b  add     rbx, 2
0x100436d8f  mov     eax, 0DC00h
0x100436d94  or      cx, ax
0x100436d97  xor     eax, eax
0x100436d99  mov     [rbx], cx
0x100436d9c  add     rdi, rdx
0x100436d9f  add     rbx, 2
0x100436da3  sub     rbp, 1
0x100436da7  jnz     loc_100436D05
0x100436dad  sub     rbx, r14
0x100436db0  mov     [r15], rdi
0x100436db3  sar     rbx, 1
0x100436db6  mov     rax, rbx
0x100436db9  jmp     loc_100436E4A
0x100436dbe  mov     rdi, rax
0x100436dc1  mov     [rbx], ax
0x100436dc4  jmp     short loc_100436DAD
0x100436dc6  mov     [r15], rdi
0x100436dc9  mov     byte ptr [r13+30h], 1
0x100436dce  mov     dword ptr [r13+2Ch], 2Ah ; '*'
0x100436dd6  jmp     short loc_100436E46
0x100436dd8  mov     rbp, [rsp+58h+arg_20]
0x100436de0  mov     rbx, rax
0x100436de3  cmp     [rdi], al
0x100436de5  jnz     short loc_100436DEF
0x100436de7  mov     r8d, 1
0x100436ded  jmp     short loc_100436E0B
0x100436def  cmp     [rdi+1], al
0x100436df2  jnz     short loc_100436DFC
0x100436df4  mov     r8d, 2
0x100436dfa  jmp     short loc_100436E0B
0x100436dfc  mov     al, [rdi+2]
0x100436dff  neg     al
0x100436e01  sbb     r8, r8
0x100436e04  neg     r8
0x100436e07  add     r8, 3; char *
0x100436e0b  mov     r9, r12; unsigned __int64
0x100436e0e  mov     [rsp+58h+var_38], rbp; struct _Mbstatet *
0x100436e13  mov     rdx, rdi; char32_t *
0x100436e16  xor     ecx, ecx; this
0x100436e18  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100436e1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100436e21  jz      short loc_100436E3B
0x100436e23  test    rax, rax
0x100436e26  jz      short loc_100436DB6
0x100436e28  cmp     rax, 4
0x100436e2c  jnz     short loc_100436E31
0x100436e2e  inc     rbx
0x100436e31  add     rdi, rax
0x100436e34  inc     rbx
0x100436e37  xor     eax, eax
0x100436e39  jmp     short loc_100436DE3
0x100436e3b  mov     byte ptr [rbp+30h], 1
0x100436e3f  mov     dword ptr [rbp+2Ch], 2Ah ; '*'
0x100436e46  or      rax, 0FFFFFFFFFFFFFFFFh
0x100436e4a  mov     rbx, [rsp+58h+arg_8]
0x100436e4f  mov     rbp, [rsp+58h+arg_10]
0x100436e54  add     rsp, 30h
0x100436e58  pop     r15
0x100436e5a  pop     r14
0x100436e5c  pop     r13
0x100436e5e  pop     r12
0x100436e60  pop     rdi
0x100436e61  retn
```
