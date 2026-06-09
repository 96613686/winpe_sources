# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)

- ea: `0x180088d44`
- end: `0x180089098`
- name: `??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z`
- size: `852`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180089108`
- `0x1800892cc`
- `0x180089490`
- `0x180089654`
- `0x180089818`
- `0x1800899dc`
- `0x180089ba0`
- `0x180089d68`
- `0x180089f30`
- `0x18008a160`
- `0x18008a324`

## callees

- `0x1800048e0`
- `0x18000491c`
- `0x18003d6e0`
- `0x18003f8ec`
- `0x180058600`
- `0x180088d44`
- `0x18008b128`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180088f9a`
- `OLEAUT32!__imp_VariantClear` at `0x180088f9a`
- `OLEAUT32!__imp_VariantCopy` at `0x180088e82`
- `OLEAUT32!__imp_VariantCopy` at `0x180088ec7`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f08`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f62`
- `OLEAUT32!__imp_VariantCopy` at `0x180088e82`
- `OLEAUT32!__imp_VariantCopy` at `0x180088ec7`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f08`
- `OLEAUT32!__imp_VariantCopy` at `0x180088f62`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        const VARIANTARG **a1,
        const VARIANTARG *a2,
        const VARIANTARG *a3)
{
  const VARIANTARG *v5; // r14
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r15
  _QWORD *v11; // rdi
  void *v12; // rax
  __int64 v13; // r13
  VARIANTARG *v14; // r14
  HRESULT v15; // eax
  const VARIANTARG *v16; // rax
  const VARIANTARG *v17; // rsi
  VARIANTARG *v18; // r14
  const VARIANTARG *v19; // r12
  HRESULT v20; // eax
  __int64 v21; // r14
  HRESULT v22; // eax
  VARIANTARG *v23; // rsi
  const VARIANTARG *v24; // r13
  HRESULT v25; // eax
  VARIANTARG *v26; // rsi
  VARIANTARG *v27; // r12
  const VARIANTARG *v28; // rcx
  VARIANTARG *pRecInfo; // rax
  const VARIANTARG **v31; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-20h]
  unsigned __int64 v33; // [rsp+48h] [rbp-18h]
  VARIANTARG *v34; // [rsp+50h] [rbp-10h]
  VARIANTARG *v35; // [rsp+58h] [rbp-8h]
  unsigned __int64 v36; // [rsp+A8h] [rbp+48h]

  v5 = *a1;
  v6 = 0xAAAAAAAAAAAAAAABuLL * (((char *)a1[1] - (char *)*a1) >> 3);
  if ( v6 == 0xAAAAAAAAAAAAAAALL )
    std::vector<ATL::CComVariant>::_Xlength();
  v7 = 0xAAAAAAAAAAAAAAABuLL * (((char *)a1[2] - (char *)v5) >> 3);
  v8 = v7 >> 1;
  if ( v7 > 0xAAAAAAAAAAAAAAALL - (v7 >> 1) )
    goto LABEL_40;
  v36 = v6 + 1;
  v9 = v6 + 1;
  if ( v7 + v8 >= v6 + 1 )
    v9 = v7 + v8;
  if ( v9 > 0xAAAAAAAAAAAAAAALL )
    goto LABEL_40;
  v10 = 24 * v9;
  if ( !(24 * v9) )
  {
    v11 = 0;
    goto LABEL_14;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(24 * v9);
    goto LABEL_14;
  }
  if ( v10 + 39 < v10 )
LABEL_40:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    __fastfail(5u);
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_14:
  v13 = a2 - v5;
  v14 = (VARIANTARG *)&v11[3 * v13];
  v31 = a1;
  v32 = v11;
  v33 = v9;
  v34 = v14 + 1;
  v35 = v14 + 1;
  v14->vt = 0;
  v15 = VariantCopy(v14, a3);
  if ( v15 < 0 )
  {
    v14->vt = 10;
    v14->lVal = v15;
    ATL::AtlThrowImpl(v15);
  }
  v34 = (VARIANTARG *)&v11[3 * v13];
  v16 = a1[1];
  v17 = *a1;
  v18 = (VARIANTARG *)v11;
  if ( a2 == v16 )
  {
    if ( v17 != v16 )
    {
      v19 = a1[1];
      do
      {
        v18->vt = 0;
        v20 = VariantCopy(v18, v17);
        if ( v20 < 0 )
        {
          v18->vt = 10;
          v18->lVal = v20;
          ATL::AtlThrowImpl(v20);
        }
        ++v18;
        ++v17;
      }
      while ( v17 != v19 );
    }
    v21 = 3 * v13;
  }
  else
  {
    while ( v17 != a2 )
    {
      v18->vt = 0;
      v22 = VariantCopy(v18, v17);
      if ( v22 < 0 )
      {
        v18->vt = 10;
        v18->lVal = v22;
        ATL::AtlThrowImpl(v22);
      }
      ++v18;
      ++v17;
    }
    v34 = (VARIANTARG *)v11;
    v21 = 3 * v13;
    v23 = (VARIANTARG *)&v11[3 * v13 + 3];
    v24 = a1[1];
    while ( a2 != v24 )
    {
      v23->vt = 0;
      v25 = VariantCopy(v23, a2);
      if ( v25 < 0 )
      {
        v23->vt = 10;
        v23->lVal = v25;
        ATL::AtlThrowImpl(v25);
      }
      ++v23;
      ++a2;
    }
  }
  v32 = 0;
  v26 = (VARIANTARG *)*a1;
  if ( *a1 )
  {
    v27 = (VARIANTARG *)a1[1];
    while ( v26 != v27 )
      VariantClear(v26++);
    v28 = *a1;
    if ( (unsigned __int64)(8 * (((char *)a1[2] - (char *)*a1) >> 3)) < 0x1000 )
    {
      pRecInfo = (VARIANTARG *)*a1;
    }
    else
    {
      pRecInfo = (VARIANTARG *)v28[-1].pRecInfo;
      if ( (unsigned __int64)((char *)v28 - (char *)pRecInfo - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(pRecInfo);
  }
  *a1 = (const VARIANTARG *)v11;
  a1[1] = (const VARIANTARG *)&v11[3 * v36];
  a1[2] = (const VARIANTARG *)&v11[v10 / 8];
  std::vector<ATL::CComVariant>::_Reallocation_guard::~_Reallocation_guard(&v31);
  return (char *)&v11[v21];
}

```

## disassembly

```asm
0x180088d44  mov     [rsp-38h+arg_18], rbx
0x180088d49  mov     [rsp-38h+pvargSrc], r8
0x180088d4e  push    rbp
0x180088d4f  push    rsi
0x180088d50  push    rdi
0x180088d51  push    r12
0x180088d53  push    r13
0x180088d55  push    r14
0x180088d57  push    r15
0x180088d59  mov     rbp, rsp
0x180088d5c  sub     rsp, 60h
0x180088d60  mov     r12, rdx
0x180088d63  mov     rbx, rcx
0x180088d66  mov     r14, [rcx]
0x180088d69  mov     rdx, [rcx+8]
0x180088d6d  sub     rdx, r14
0x180088d70  sar     rdx, 3
0x180088d74  mov     rax, 0AAAAAAAAAAAAAAABh
0x180088d7e  imul    rdx, rax
0x180088d82  mov     r9, 0AAAAAAAAAAAAAAAh
0x180088d8c  cmp     rdx, r9
0x180088d8f  jz      loc_18008905C
0x180088d95  mov     rcx, [rcx+10h]
0x180088d99  sub     rcx, r14
0x180088d9c  sar     rcx, 3
0x180088da0  imul    rcx, rax
0x180088da4  mov     r8, rcx
0x180088da7  shr     r8, 1
0x180088daa  mov     rax, r9
0x180088dad  sub     rax, r8
0x180088db0  cmp     rcx, rax
0x180088db3  ja      loc_180089056
0x180088db9  inc     rdx
0x180088dbc  mov     [rbp+arg_8], rdx
0x180088dc0  lea     rax, [rcx+r8]
0x180088dc4  mov     rsi, rdx
0x180088dc7  cmp     rax, rdx
0x180088dca  cmovnb  rsi, rax
0x180088dce  cmp     rsi, r9
0x180088dd1  ja      loc_180089056
0x180088dd7  lea     rax, [rsi+rsi*2]
0x180088ddb  lea     r15, ds:0[rax*8]
0x180088de3  test    r15, r15
0x180088de6  jnz     short loc_180088DEC
0x180088de8  xor     edi, edi
0x180088dea  jmp     short loc_180088E2A
0x180088dec  cmp     r15, 1000h
0x180088df3  jb      short loc_180088E1F
0x180088df5  lea     rcx, [r15+27h]; Size
0x180088df9  cmp     rcx, r15
0x180088dfc  jbe     loc_180089056
0x180088e02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180088e07  test    rax, rax
0x180088e0a  jnz     short loc_180088E11
0x180088e0c  lea     ecx, [rax+5]
0x180088e0f  int     29h; Win8: RtlFailFast(ecx)
0x180088e11  lea     rdi, [rax+27h]
0x180088e15  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180088e19  mov     [rdi-8], rax
0x180088e1d  jmp     short loc_180088E2A
0x180088e1f  mov     rcx, r15; Size
0x180088e22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180088e27  mov     rdi, rax
0x180088e2a  mov     rcx, r12
0x180088e2d  sub     rcx, r14
0x180088e30  mov     rax, 2AAAAAAAAAAAAAABh
0x180088e3a  imul    rcx
0x180088e3d  mov     r13, rdx
0x180088e40  sar     r13, 2
0x180088e44  mov     rcx, r13
0x180088e47  shr     rcx, 3Fh
0x180088e4b  add     r13, rcx
0x180088e4e  lea     rax, ds:0[r13*2]
0x180088e56  add     rax, r13
0x180088e59  lea     r14, [rdi+rax*8]
0x180088e5d  lea     rax, [r14+18h]
0x180088e61  mov     [rbp+var_28], rbx
0x180088e65  mov     [rbp+var_20], rdi
0x180088e69  mov     [rbp+var_18], rsi
0x180088e6d  mov     [rbp+var_10], rax
0x180088e71  mov     [rbp+var_8], rax
0x180088e75  xor     eax, eax
0x180088e77  mov     [r14], ax
0x180088e7b  mov     rdx, [rbp+pvargSrc]; pvargSrc
0x180088e7f  mov     rcx, r14; pvargDest
0x180088e82  call    cs:__imp_VariantCopy
0x180088e88  test    eax, eax
0x180088e8a  js      loc_180089062
0x180088e90  mov     [rbp+var_10], r14
0x180088e94  mov     rax, [rbx+8]
0x180088e98  mov     [rbp+arg_0], rax
0x180088e9c  mov     rsi, [rbx]
0x180088e9f  mov     [rbp+var_40], rdi
0x180088ea3  mov     r14, rdi
0x180088ea6  mov     [rbp+var_38], rdi
0x180088eaa  mov     [rbp+var_30], rbx
0x180088eae  cmp     r12, rax
0x180088eb1  jnz     short loc_180088EFA
0x180088eb3  cmp     rsi, rax
0x180088eb6  jz      short loc_180088EE6
0x180088eb8  mov     r12, rax
0x180088ebb  xor     eax, eax
0x180088ebd  mov     [r14], ax
0x180088ec1  mov     rdx, rsi; pvargSrc
0x180088ec4  mov     rcx, r14; pvargDest
0x180088ec7  call    cs:__imp_VariantCopy
0x180088ecd  test    eax, eax
0x180088ecf  js      loc_180089074
0x180088ed5  add     r14, 18h
0x180088ed9  mov     [rbp+var_38], r14
0x180088edd  add     rsi, 18h
0x180088ee1  cmp     rsi, r12
0x180088ee4  jnz     short loc_180088EBB
0x180088ee6  lea     r14, ds:0[r13*2]
0x180088eee  add     r14, r13
0x180088ef1  shl     r14, 3
0x180088ef5  jmp     loc_180088F81
0x180088efa  jmp     short loc_180088F22
0x180088efc  xor     eax, eax
0x180088efe  mov     [r14], ax
0x180088f02  mov     rdx, rsi; pvargSrc
0x180088f05  mov     rcx, r14; pvargDest
0x180088f08  call    cs:__imp_VariantCopy
0x180088f0e  test    eax, eax
0x180088f10  js      loc_180089086
0x180088f16  add     r14, 18h
0x180088f1a  mov     [rbp+var_38], r14
0x180088f1e  add     rsi, 18h
0x180088f22  cmp     rsi, r12
0x180088f25  jnz     short loc_180088EFC
0x180088f27  mov     [rbp+var_10], rdi
0x180088f2b  lea     rax, ds:0[r13*2]
0x180088f33  add     rax, r13
0x180088f36  lea     r14, ds:0[rax*8]
0x180088f3e  lea     rsi, [r14+18h]
0x180088f42  add     rsi, rdi
0x180088f45  mov     r13, [rbx+8]
0x180088f49  mov     [rbp+var_40], rsi
0x180088f4d  mov     [rbp+var_38], rsi
0x180088f51  mov     [rbp+var_30], rbx
0x180088f55  jmp     short loc_180088F7C
0x180088f57  xor     eax, eax
0x180088f59  mov     [rsi], ax
0x180088f5c  mov     rdx, r12; pvargSrc
0x180088f5f  mov     rcx, rsi; pvargDest
0x180088f62  call    cs:__imp_VariantCopy
0x180088f68  test    eax, eax
0x180088f6a  js      loc_180089046
0x180088f70  add     rsi, 18h
0x180088f74  mov     [rbp+var_38], rsi
0x180088f78  add     r12, 18h
0x180088f7c  cmp     r12, r13
0x180088f7f  jnz     short loc_180088F57
0x180088f81  mov     [rbp+var_20], 0
0x180088f89  mov     rsi, [rbx]
0x180088f8c  test    rsi, rsi
0x180088f8f  jz      short loc_180089003
0x180088f91  mov     r12, [rbx+8]
0x180088f95  jmp     short loc_180088FA4
0x180088f97  mov     rcx, rsi; pvarg
0x180088f9a  call    cs:__imp_VariantClear
0x180088fa0  add     rsi, 18h
0x180088fa4  cmp     rsi, r12
0x180088fa7  jnz     short loc_180088F97
0x180088fa9  mov     rcx, [rbx]
0x180088fac  mov     rax, [rbx+10h]
0x180088fb0  sub     rax, rcx
0x180088fb3  sar     rax, 3
0x180088fb7  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180088fc1  imul    rax, rdx
0x180088fc5  lea     rax, [rax+rax*2]
0x180088fc9  lea     rdx, ds:0[rax*8]
0x180088fd1  cmp     rdx, 1000h
0x180088fd8  jb      short loc_180088FF8
0x180088fda  mov     rax, [rcx-8]
0x180088fde  sub     rcx, rax
0x180088fe1  sub     rcx, 8
0x180088fe5  cmp     rcx, 1Fh
0x180088fe9  ja      short loc_180088FF1
0x180088feb  add     rdx, 27h ; '''
0x180088fef  jmp     short loc_180088FFB
0x180088ff1  mov     ecx, 5
0x180088ff6  int     29h; Win8: RtlFailFast(ecx)
0x180088ff8  mov     rax, rcx
0x180088ffb  mov     rcx, rax; Block
0x180088ffe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180089003  mov     [rbx], rdi
0x180089006  mov     rax, [rbp+arg_8]
0x18008900a  lea     rax, [rax+rax*2]
0x18008900e  lea     rcx, [rdi+rax*8]
0x180089012  mov     [rbx+8], rcx
0x180089016  lea     rax, [r15+rdi]
0x18008901a  mov     [rbx+10h], rax
0x18008901e  lea     rbx, [r14+rdi]
0x180089022  lea     rcx, [rbp+var_28]
0x180089026  call    ??1_Reallocation_guard@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::_Reallocation_guard::~_Reallocation_guard(void)
0x18008902b  mov     rax, rbx
0x18008902e  mov     rbx, [rsp+60h+arg_18]
0x180089036  add     rsp, 60h
0x18008903a  pop     r15
0x18008903c  pop     r14
0x18008903e  pop     r13
0x180089040  pop     r12
0x180089042  pop     rdi
0x180089043  pop     rsi
0x180089044  pop     rbp
0x180089045  retn
0x180089046  mov     word ptr [rsi], 0Ah
0x18008904b  mov     [rsi+8], eax
0x18008904e  mov     ecx, eax; int
0x180089050  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089056  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18008905c  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x180089062  mov     word ptr [r14], 0Ah
0x180089068  mov     [r14+8], eax
0x18008906c  mov     ecx, eax; int
0x18008906e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089074  mov     word ptr [r14], 0Ah
0x18008907a  mov     [r14+8], eax
0x18008907e  mov     ecx, eax; int
0x180089080  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089086  mov     word ptr [r14], 0Ah
0x18008908c  mov     [r14+8], eax
0x180089090  mov     ecx, eax; int
0x180089092  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
