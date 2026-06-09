# VAR::SafeVariantShallowCopy(VAR &,VAR &)

- ea: `0x1800014a0`
- end: `0x1800016af`
- name: `?SafeVariantShallowCopy@VAR@@SAJAEAV1@0@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct VAR *, struct VAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001f0f0`

## callees

- `0x1800014a0`
- `0x1800019d4`
- `0x180001a30`
- `0x18004237c`
- `0x18004686c`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800015a4`
- `OLEAUT32!__imp_VariantClear` at `0x18000164f`
- `OLEAUT32!__imp_VariantClear` at `0x1800015a4`
- `OLEAUT32!__imp_VariantClear` at `0x18000164f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180001635`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180001635`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000153b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000153b`

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
0x1800014a0  sub     rsp, 68h
0x1800014a4  mov     rax, cs:__security_cookie
0x1800014ab  xor     rax, rsp
0x1800014ae  mov     [rsp+68h+var_18], rax
0x1800014b3  movups  xmm2, xmmword ptr [rcx]
0x1800014b6  movups  xmm0, xmmword ptr [rdx]
0x1800014b9  movsd   xmm3, qword ptr [rcx+10h]
0x1800014be  movups  xmmword ptr [rcx], xmm0
0x1800014c1  movsd   xmm1, qword ptr [rdx+10h]
0x1800014c6  movd    edx, xmm2
0x1800014ca  movups  xmmword ptr [rsp+68h+psa], xmm2
0x1800014cf  movsd   [rsp+68h+var_38], xmm3
0x1800014d5  movsd   qword ptr [rcx+10h], xmm1
0x1800014da  test    dx, dx
0x1800014dd  jz      loc_1800015CE
0x1800014e3  movzx   eax, dx
0x1800014e6  mov     [rsp+68h+arg_8], rbx
0x1800014eb  mov     [rsp+68h+var_8], rdi
0x1800014f0  cmp     eax, 4Eh ; 'N'
0x1800014f3  jz      short loc_180001536
0x1800014f5  xor     ebx, ebx
0x1800014f7  cmp     eax, 4Fh ; 'O'
0x1800014fa  ja      short loc_18000154B
0x1800014fc  jz      loc_1800015E3
0x180001502  sub     eax, 49h ; 'I'
0x180001505  jz      loc_180001694
0x18000150b  sub     eax, 3
0x18000150e  jz      loc_1800015E3
0x180001514  cmp     eax, 1
0x180001517  jnz     short loc_18000155F
0x180001519  psrldq  xmm2, 8
0x18000151e  movq    rcx, xmm2
0x180001523  test    rcx, rcx
0x180001526  jz      short loc_18000156E
0x180001528  mov     rax, [rcx]
0x18000152b  mov     rax, [rax+10h]
0x18000152f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001534  jmp     short loc_18000156E
0x180001536  mov     rcx, [rsp+68h+psa+8]; psa
0x18000153b  call    cs:__imp_SafeArrayUnlock
0x180001542  nop     dword ptr [rax+rax+00h]
0x180001547  mov     ebx, eax
0x180001549  jmp     short loc_18000156E
0x18000154b  cmp     eax, 600Ch
0x180001550  jz      loc_1800015F9
0x180001556  cmp     eax, 50h ; 'P'
0x180001559  jz      loc_18000166C
0x18000155f  lea     eax, [rdx-8]
0x180001562  cmp     ax, 40h ; '@'
0x180001566  jbe     short loc_18000158D
0x180001568  cmp     dx, 51h ; 'Q'
0x18000156c  jnb     short loc_18000158D
0x18000156e  mov     rdi, [rsp+68h+var_8]
0x180001573  mov     eax, ebx
0x180001575  mov     rbx, [rsp+68h+arg_8]
0x18000157a  mov     rcx, [rsp+68h+var_18]
0x18000157f  xor     rcx, rsp; StackCookie
0x180001582  call    __security_check_cookie
0x180001587  add     rsp, 68h
0x18000158b  retn
0x18000158d  xor     eax, eax
0x18000158f  movsd   qword ptr [rsp+68h+pvarg+10h], xmm3
0x180001595  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000159a  mov     word ptr [rsp+68h+psa], ax
0x18000159f  movups  xmmword ptr [rsp+68h+pvarg], xmm2
0x1800015a4  call    cs:__imp_VariantClear
0x1800015ab  nop     dword ptr [rax+rax+00h]
0x1800015b0  mov     ebx, eax
0x1800015b2  test    eax, eax
0x1800015b4  js      short loc_18000156E
0x1800015b6  cmp     word ptr [rsp+68h+psa], 0
0x1800015bc  jz      short loc_18000156E
0x1800015be  lea     rdx, [rsp+68h+psa]; struct VAR *
0x1800015c3  mov     ecx, 8000FFFFh; int
0x1800015c8  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x1800015ce  xor     eax, eax
0x1800015d0  mov     rcx, [rsp+68h+var_18]
0x1800015d5  xor     rcx, rsp; StackCookie
0x1800015d8  call    __security_check_cookie
0x1800015dd  add     rsp, 68h
0x1800015e1  retn
0x1800015e3  mov     rcx, [rsp+68h+psa+8]
0x1800015e8  mov     rax, [rcx]
0x1800015eb  mov     rax, [rax+8]
0x1800015ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015f4  jmp     loc_18000156E
0x1800015f9  psrldq  xmm2, 8
0x1800015fe  lea     rax, [rsp+68h+var_38]
0x180001603  movq    rcx, xmm2
0x180001608  cmp     rcx, rax
0x18000160b  jnz     loc_18000156E
0x180001611  cmp     [rcx], rbx
0x180001614  jz      loc_18000156E
0x18000161a  xor     eax, eax
0x18000161c  mov     word ptr [rsp+68h+psa], ax
0x180001621  mov     rax, [rcx]
0x180001624  mov     ecx, 0FFFDh
0x180001629  and     [rax+2], cx
0x18000162d  mov     rcx, [rsp+68h+psa+8]
0x180001632  mov     rcx, [rcx]; psa
0x180001635  call    cs:__imp_SafeArrayDestroy
0x18000163c  nop     dword ptr [rax+rax+00h]
0x180001641  mov     edi, eax
0x180001643  cmp     word ptr [rsp+68h+psa], bx
0x180001648  jz      short loc_180001665
0x18000164a  lea     rcx, [rsp+68h+psa]; pvarg
0x18000164f  call    cs:__imp_VariantClear
0x180001656  nop     dword ptr [rax+rax+00h]
0x18000165b  mov     ebx, eax
0x18000165d  test    eax, eax
0x18000165f  js      loc_18000156E
0x180001665  mov     ebx, edi
0x180001667  jmp     loc_18000156E
0x18000166c  psrldq  xmm2, 8
0x180001671  movq    rdi, xmm2
0x180001676  test    rdi, rdi
0x180001679  jz      loc_18000156E
0x18000167f  mov     rcx, rdi; this
0x180001682  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x180001687  mov     rcx, rdi; Block
0x18000168a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000168f  jmp     loc_18000156E
0x180001694  mov     eax, 9
0x180001699  lea     rcx, [rsp+68h+psa]; this
0x18000169e  mov     word ptr [rsp+68h+psa], ax
0x1800016a3  call    ?VariantClearWrapper@VAR@@QEAAJXZ; VAR::VariantClearWrapper(void)
0x1800016a8  mov     ebx, eax
0x1800016aa  jmp     loc_18000156E
```
