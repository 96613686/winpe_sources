# VAR::SafeVariantShallowCopy(VAR &,VAR &)

- ea: `0x180027c00`
- end: `0x180027df2`
- name: `?SafeVariantShallowCopy@VAR@@SAJAEAV1@0@Z`
- size: `498`
- prototype: `__int64 __fastcall(struct VAR *, struct VAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180023ad0`

## callees

- `0x180027c00`
- `0x1800280f4`
- `0x180028150`
- `0x180040cc4`
- `0x180045478`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180027cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180027d98`
- `OLEAUT32!__imp_VariantClear` at `0x180027cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180027d98`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027d84`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027d84`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180027c9b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180027c9b`

## pseudocode

```c
__int64 __fastcall VAR::SafeVariantShallowCopy(struct VAR *a1, struct VAR *a2)
{
  __m128i v2; // xmm2
  IRecordInfo *v3; // xmm3_8
  __int64 v4; // xmm1_8
  unsigned __int16 v5; // dx
  unsigned int v6; // ebx
  unsigned __int64 v7; // xmm2_8
  VARIANTARG *v9; // xmm2_8
  unsigned int v10; // edi
  VAR::PropertyFuncs *v11; // xmm2_8
  VARIANTARG psa; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-30h] BYREF

  v2 = *(__m128i *)a1;
  v3 = (IRecordInfo *)*((_QWORD *)a1 + 2);
  *(_OWORD *)a1 = *(_OWORD *)a2;
  v4 = *((_QWORD *)a2 + 2);
  v5 = _mm_cvtsi128_si32(v2);
  *(__m128i *)&psa.vt = v2;
  psa.pRecInfo = v3;
  *((_QWORD *)a1 + 2) = v4;
  if ( v5 )
  {
    if ( v5 == 78 )
    {
      return (unsigned int)SafeArrayUnlock(psa.parray);
    }
    else
    {
      v6 = 0;
      if ( v5 > 0x4Fu )
      {
        if ( v5 == 24588 )
        {
          v9 = (VARIANTARG *)_mm_srli_si128(v2, 8).m128i_u64[0];
          if ( v9 == (VARIANTARG *)(&psa.decVal + 1) )
          {
            if ( *(_QWORD *)&v9->vt )
            {
              psa.vt = 0;
              *(_WORD *)(*(_QWORD *)&v9->vt + 2LL) &= ~2u;
              v10 = SafeArrayDestroy(*psa.pparray);
              if ( !psa.vt )
                return v10;
              v6 = VariantClear(&psa);
              if ( (v6 & 0x80000000) == 0 )
                return v10;
            }
          }
          return v6;
        }
        if ( v5 == 80 )
        {
          v11 = (VAR::PropertyFuncs *)_mm_srli_si128(v2, 8).m128i_u64[0];
          if ( v11 )
          {
            VAR::PropertyFuncs::~PropertyFuncs(v11);
            operator delete(v11);
          }
          return v6;
        }
        goto LABEL_13;
      }
      if ( v5 != 79 )
      {
        if ( v5 == 73 )
        {
          psa.vt = 9;
          return (unsigned int)VAR::VariantClearWrapper((VAR *)&psa);
        }
        if ( v5 != 76 )
        {
          if ( v5 == 77 )
          {
            v7 = _mm_srli_si128(v2, 8).m128i_u64[0];
            if ( v7 )
              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v7 + 16LL))(v7);
            return v6;
          }
LABEL_13:
          if ( (unsigned __int16)(v5 - 8) <= 0x40u || v5 >= 0x51u )
          {
            pvarg.pRecInfo = v3;
            psa.vt = 0;
            *(__m128i *)&pvarg.vt = v2;
            return (unsigned int)VariantClear(&pvarg);
          }
          return v6;
        }
      }
      (*(void (__fastcall **)(LONGLONG))(*psa.pllVal + 8))(psa.llVal);
    }
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180027c00  sub     rsp, 68h
0x180027c04  mov     rax, cs:__security_cookie
0x180027c0b  xor     rax, rsp
0x180027c0e  mov     [rsp+68h+var_18], rax
0x180027c13  movups  xmm2, xmmword ptr [rcx]
0x180027c16  movups  xmm0, xmmword ptr [rdx]
0x180027c19  movsd   xmm3, qword ptr [rcx+10h]
0x180027c1e  movups  xmmword ptr [rcx], xmm0
0x180027c21  movsd   xmm1, qword ptr [rdx+10h]
0x180027c26  movd    edx, xmm2
0x180027c2a  movups  xmmword ptr [rsp+68h+psa], xmm2
0x180027c2f  movsd   [rsp+68h+var_38], xmm3
0x180027c35  movsd   qword ptr [rcx+10h], xmm1
0x180027c3a  test    dx, dx
0x180027c3d  jz      loc_180027D21
0x180027c43  movzx   eax, dx
0x180027c46  mov     [rsp+68h+arg_8], rbx
0x180027c4b  mov     [rsp+68h+var_8], rdi
0x180027c50  cmp     eax, 4Eh ; 'N'
0x180027c53  jz      short loc_180027C96
0x180027c55  xor     ebx, ebx
0x180027c57  cmp     eax, 4Fh ; 'O'
0x180027c5a  ja      short loc_180027CA5
0x180027c5c  jz      loc_180027D35
0x180027c62  sub     eax, 49h ; 'I'
0x180027c65  jz      loc_180027DD7
0x180027c6b  sub     eax, 3
0x180027c6e  jz      loc_180027D35
0x180027c74  cmp     eax, 1
0x180027c77  jnz     short loc_180027CB9
0x180027c79  psrldq  xmm2, 8
0x180027c7e  movq    rcx, xmm2
0x180027c83  test    rcx, rcx
0x180027c86  jz      short loc_180027CC8
0x180027c88  mov     rax, [rcx]
0x180027c8b  mov     rax, [rax+10h]
0x180027c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c94  jmp     short loc_180027CC8
0x180027c96  mov     rcx, [rsp+68h+psa+8]; psa
0x180027c9b  call    cs:__imp_SafeArrayUnlock
0x180027ca1  mov     ebx, eax
0x180027ca3  jmp     short loc_180027CC8
0x180027ca5  cmp     eax, 600Ch
0x180027caa  jz      loc_180027D48
0x180027cb0  cmp     eax, 50h ; 'P'
0x180027cb3  jz      loc_180027DAF
0x180027cb9  lea     eax, [rdx-8]
0x180027cbc  cmp     ax, 40h ; '@'
0x180027cc0  jbe     short loc_180027CE6
0x180027cc2  cmp     dx, 51h ; 'Q'
0x180027cc6  jnb     short loc_180027CE6
0x180027cc8  mov     rdi, [rsp+68h+var_8]
0x180027ccd  mov     eax, ebx
0x180027ccf  mov     rbx, [rsp+68h+arg_8]
0x180027cd4  mov     rcx, [rsp+68h+var_18]
0x180027cd9  xor     rcx, rsp; StackCookie
0x180027cdc  call    __security_check_cookie
0x180027ce1  add     rsp, 68h
0x180027ce5  retn
0x180027ce6  xor     eax, eax
0x180027ce8  movsd   qword ptr [rsp+68h+pvarg+10h], xmm3
0x180027cee  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180027cf3  mov     word ptr [rsp+68h+psa], ax
0x180027cf8  movups  xmmword ptr [rsp+68h+pvarg], xmm2
0x180027cfd  call    cs:__imp_VariantClear
0x180027d03  mov     ebx, eax
0x180027d05  test    eax, eax
0x180027d07  js      short loc_180027CC8
0x180027d09  cmp     word ptr [rsp+68h+psa], 0
0x180027d0f  jz      short loc_180027CC8
0x180027d11  lea     rdx, [rsp+68h+psa]; struct VAR *
0x180027d16  mov     ecx, 8000FFFFh; int
0x180027d1b  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180027d21  xor     eax, eax
0x180027d23  mov     rcx, [rsp+68h+var_18]
0x180027d28  xor     rcx, rsp; StackCookie
0x180027d2b  call    __security_check_cookie
0x180027d30  add     rsp, 68h
0x180027d34  retn
0x180027d35  mov     rcx, [rsp+68h+psa+8]
0x180027d3a  mov     rax, [rcx]
0x180027d3d  mov     rax, [rax+8]
0x180027d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d46  jmp     short loc_180027CC8
0x180027d48  psrldq  xmm2, 8
0x180027d4d  lea     rax, [rsp+68h+var_38]
0x180027d52  movq    rcx, xmm2
0x180027d57  cmp     rcx, rax
0x180027d5a  jnz     loc_180027CC8
0x180027d60  cmp     [rcx], rbx
0x180027d63  jz      loc_180027CC8
0x180027d69  xor     eax, eax
0x180027d6b  mov     word ptr [rsp+68h+psa], ax
0x180027d70  mov     rax, [rcx]
0x180027d73  mov     ecx, 0FFFDh
0x180027d78  and     [rax+2], cx
0x180027d7c  mov     rcx, [rsp+68h+psa+8]
0x180027d81  mov     rcx, [rcx]; psa
0x180027d84  call    cs:__imp_SafeArrayDestroy
0x180027d8a  mov     edi, eax
0x180027d8c  cmp     word ptr [rsp+68h+psa], bx
0x180027d91  jz      short loc_180027DA8
0x180027d93  lea     rcx, [rsp+68h+psa]; pvarg
0x180027d98  call    cs:__imp_VariantClear
0x180027d9e  mov     ebx, eax
0x180027da0  test    eax, eax
0x180027da2  js      loc_180027CC8
0x180027da8  mov     ebx, edi
0x180027daa  jmp     loc_180027CC8
0x180027daf  psrldq  xmm2, 8
0x180027db4  movq    rdi, xmm2
0x180027db9  test    rdi, rdi
0x180027dbc  jz      loc_180027CC8
0x180027dc2  mov     rcx, rdi; this
0x180027dc5  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x180027dca  mov     rcx, rdi; Block
0x180027dcd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027dd2  jmp     loc_180027CC8
0x180027dd7  mov     eax, 9
0x180027ddc  lea     rcx, [rsp+68h+psa]; this
0x180027de1  mov     word ptr [rsp+68h+psa], ax
0x180027de6  call    ?VariantClearWrapper@VAR@@QEAAJXZ; VAR::VariantClearWrapper(void)
0x180027deb  mov     ebx, eax
0x180027ded  jmp     loc_180027CC8
```
