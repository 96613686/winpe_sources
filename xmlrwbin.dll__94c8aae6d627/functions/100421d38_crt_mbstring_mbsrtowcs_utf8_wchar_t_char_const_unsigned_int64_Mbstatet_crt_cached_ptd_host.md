# __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x100421d38`
- end: `0x100421eda`
- name: `?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `418`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, wchar_t *, const char **, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100420f38`

## callees

- `0x100421d38`
- `0x100422ae0`

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
0x100421d38  mov     [rsp+arg_8], rbx
0x100421d3d  mov     [rsp+arg_10], rbp
0x100421d42  push    rdi
0x100421d43  push    r12
0x100421d45  push    r13
0x100421d47  push    r14
0x100421d49  push    r15
0x100421d4b  sub     rsp, 30h
0x100421d4f  mov     rdi, [rdx]
0x100421d52  xor     eax, eax
0x100421d54  mov     r12, r9
0x100421d57  mov     rbp, r8
0x100421d5a  mov     r15, rdx
0x100421d5d  mov     r14, rcx
0x100421d60  test    rcx, rcx
0x100421d63  jz      loc_100421E50
0x100421d69  mov     rbx, rcx
0x100421d6c  test    r8, r8
0x100421d6f  jz      loc_100421E25
0x100421d75  mov     r13, [rsp+58h+arg_20]
0x100421d7d  cmp     [rdi], al
0x100421d7f  jnz     short loc_100421D89
0x100421d81  mov     r8d, 1
0x100421d87  jmp     short loc_100421DA5
0x100421d89  cmp     [rdi+1], al
0x100421d8c  jnz     short loc_100421D96
0x100421d8e  mov     r8d, 2
0x100421d94  jmp     short loc_100421DA5
0x100421d96  mov     al, [rdi+2]
0x100421d99  neg     al
0x100421d9b  sbb     r8, r8
0x100421d9e  neg     r8
0x100421da1  add     r8, 3; char *
0x100421da5  mov     r9, r12; unsigned __int64
0x100421da8  mov     [rsp+58h+var_38], r13; struct _Mbstatet *
0x100421dad  mov     rdx, rdi; char32_t *
0x100421db0  lea     rcx, [rsp+58h+arg_0]; this
0x100421db5  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100421dba  mov     rdx, rax
0x100421dbd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100421dc1  jz      short loc_100421E3E
0x100421dc3  xor     eax, eax
0x100421dc5  test    rdx, rdx
0x100421dc8  jz      short loc_100421E36
0x100421dca  mov     ecx, [rsp+58h+arg_0]
0x100421dce  cmp     ecx, 0FFFFh
0x100421dd4  jbe     short loc_100421E11
0x100421dd6  cmp     rbp, 1
0x100421dda  jbe     short loc_100421E25
0x100421ddc  add     ecx, 0FFFF0000h
0x100421de2  mov     r8d, 0D800h
0x100421de8  mov     eax, ecx
0x100421dea  mov     [rsp+58h+arg_0], ecx
0x100421dee  shr     eax, 0Ah
0x100421df1  dec     rbp
0x100421df4  or      ax, r8w
0x100421df8  mov     [rbx], ax
0x100421dfb  mov     eax, 3FFh
0x100421e00  and     cx, ax
0x100421e03  add     rbx, 2
0x100421e07  mov     eax, 0DC00h
0x100421e0c  or      cx, ax
0x100421e0f  xor     eax, eax
0x100421e11  mov     [rbx], cx
0x100421e14  add     rdi, rdx
0x100421e17  add     rbx, 2
0x100421e1b  sub     rbp, 1
0x100421e1f  jnz     loc_100421D7D
0x100421e25  sub     rbx, r14
0x100421e28  mov     [r15], rdi
0x100421e2b  sar     rbx, 1
0x100421e2e  mov     rax, rbx
0x100421e31  jmp     loc_100421EC2
0x100421e36  mov     rdi, rax
0x100421e39  mov     [rbx], ax
0x100421e3c  jmp     short loc_100421E25
0x100421e3e  mov     [r15], rdi
0x100421e41  mov     byte ptr [r13+30h], 1
0x100421e46  mov     dword ptr [r13+2Ch], 2Ah ; '*'
0x100421e4e  jmp     short loc_100421EBE
0x100421e50  mov     rbp, [rsp+58h+arg_20]
0x100421e58  mov     rbx, rax
0x100421e5b  cmp     [rdi], al
0x100421e5d  jnz     short loc_100421E67
0x100421e5f  mov     r8d, 1
0x100421e65  jmp     short loc_100421E83
0x100421e67  cmp     [rdi+1], al
0x100421e6a  jnz     short loc_100421E74
0x100421e6c  mov     r8d, 2
0x100421e72  jmp     short loc_100421E83
0x100421e74  mov     al, [rdi+2]
0x100421e77  neg     al
0x100421e79  sbb     r8, r8
0x100421e7c  neg     r8
0x100421e7f  add     r8, 3; char *
0x100421e83  mov     r9, r12; unsigned __int64
0x100421e86  mov     [rsp+58h+var_38], rbp; struct _Mbstatet *
0x100421e8b  mov     rdx, rdi; char32_t *
0x100421e8e  xor     ecx, ecx; this
0x100421e90  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100421e95  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100421e99  jz      short loc_100421EB3
0x100421e9b  test    rax, rax
0x100421e9e  jz      short loc_100421E2E
0x100421ea0  cmp     rax, 4
0x100421ea4  jnz     short loc_100421EA9
0x100421ea6  inc     rbx
0x100421ea9  add     rdi, rax
0x100421eac  inc     rbx
0x100421eaf  xor     eax, eax
0x100421eb1  jmp     short loc_100421E5B
0x100421eb3  mov     byte ptr [rbp+30h], 1
0x100421eb7  mov     dword ptr [rbp+2Ch], 2Ah ; '*'
0x100421ebe  or      rax, 0FFFFFFFFFFFFFFFFh
0x100421ec2  mov     rbx, [rsp+58h+arg_8]
0x100421ec7  mov     rbp, [rsp+58h+arg_10]
0x100421ecc  add     rsp, 30h
0x100421ed0  pop     r15
0x100421ed2  pop     r14
0x100421ed4  pop     r13
0x100421ed6  pop     r12
0x100421ed8  pop     rdi
0x100421ed9  retn
```
