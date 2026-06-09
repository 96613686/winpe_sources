# _anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short_

- ea: `0x180089654`
- end: `0x180089811`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short_`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x180088d44`
- `0x180089654`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089784`
- `OLEAUT32!__imp_VariantClear` at `0x180089784`
- `OLEAUT32!__imp_VariantCopy` at `0x18008975f`
- `OLEAUT32!__imp_VariantCopy` at `0x18008975f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800896b1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089712`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800896b1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089712`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800896ea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800897a5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800896ea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800897a5`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short_(
        __int64 a1,
        SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  SHORT v9; // ax
  VARIANTARG *v10; // rdi
  HRESULT v11; // eax
  HRESULT LBound; // eax
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+78h] [rbp+38h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+40h] BYREF

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v4 = 0;
  plLbound = 0;
  for ( plUbound = 0; ; plUbound = 0 )
  {
    LBound = SafeArrayGetLBound(*a2, 1u, &plLbound);
    if ( LBound < 0 )
      ATL::AtlThrowImpl(LBound);
    UBound = SafeArrayGetUBound(*a2, 1u, &plUbound);
    if ( UBound < 0 )
      ATL::AtlThrowImpl(UBound);
    if ( v4 >= (unsigned int)(plUbound - plLbound + 1) )
      break;
    v6 = *a2;
    if ( !*a2 )
      ATL::AtlThrowImpl(-2147467259);
    plLbound = 0;
    v7 = SafeArrayGetLBound(v6, 1u, &plLbound);
    if ( v7 < 0 )
      ATL::AtlThrowImpl(v7);
    if ( v4 < plLbound )
      goto LABEL_22;
    plUbound = 0;
    v8 = SafeArrayGetUBound(*a2, 1u, &plUbound);
    if ( v8 < 0 )
      ATL::AtlThrowImpl(v8);
    if ( v4 > plUbound )
LABEL_22:
      ATL::AtlThrowImpl(-2147024809);
    v9 = *((_WORD *)(*a2)->pvData + v4 - plLbound);
    pvargSrc.vt = 18;
    pvargSrc.iVal = v9;
    v10 = *(VARIANTARG **)(a1 + 8);
    if ( v10 == *(VARIANTARG **)(a1 + 16) )
    {
      std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        (const VARIANTARG **)a1,
        *(const VARIANTARG **)(a1 + 8),
        &pvargSrc);
    }
    else
    {
      v10->vt = 0;
      v11 = VariantCopy(v10, &pvargSrc);
      if ( v11 < 0 )
      {
        v10->vt = 10;
        v10->lVal = v11;
        ATL::AtlThrowImpl(v11);
      }
      *(_QWORD *)(a1 + 8) += 24LL;
    }
    VariantClear(&pvargSrc);
    ++v4;
    plLbound = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180089654  mov     [rsp-28h+arg_18], rbx
0x180089659  mov     [rsp-28h+arg_0], rcx
0x18008965e  push    rbp
0x18008965f  push    rsi
0x180089660  push    rdi
0x180089661  push    r12
0x180089663  push    r14
0x180089665  mov     rbp, rsp
0x180089668  sub     rsp, 40h
0x18008966c  mov     r14, rdx
0x18008966f  mov     rbx, rcx
0x180089672  mov     [rbp+var_20], 0
0x180089679  mov     qword ptr [rcx], 0
0x180089680  mov     qword ptr [rcx+8], 0
0x180089688  mov     qword ptr [rcx+10h], 0
0x180089690  mov     r12d, 1
0x180089696  mov     [rbp+var_20], r12d
0x18008969a  xor     esi, esi
0x18008969c  mov     [rbp+plLbound], esi
0x18008969f  mov     [rbp+plUbound], esi
0x1800896a2  jmp     loc_18008979B
0x1800896a7  lea     r8, [rbp+plUbound]; plUbound
0x1800896ab  mov     edx, r12d; nDim
0x1800896ae  mov     rcx, [r14]; psa
0x1800896b1  call    cs:__imp_SafeArrayGetUBound
0x1800896b7  test    eax, eax
0x1800896b9  js      loc_1800897DE
0x1800896bf  mov     eax, [rbp+plUbound]
0x1800896c2  sub     eax, [rbp+plLbound]
0x1800896c5  add     eax, r12d
0x1800896c8  cmp     esi, eax
0x1800896ca  jnb     loc_1800897B4
0x1800896d0  mov     rcx, [r14]; psa
0x1800896d3  test    rcx, rcx
0x1800896d6  jz      loc_1800897CB
0x1800896dc  mov     [rbp+plLbound], 0
0x1800896e3  lea     r8, [rbp+plLbound]; plLbound
0x1800896e7  mov     edx, r12d; nDim
0x1800896ea  call    cs:__imp_SafeArrayGetLBound
0x1800896f0  test    eax, eax
0x1800896f2  js      loc_180089809
0x1800896f8  cmp     esi, [rbp+plLbound]
0x1800896fb  jl      loc_1800897FE
0x180089701  mov     [rbp+plUbound], 0
0x180089708  lea     r8, [rbp+plUbound]; plUbound
0x18008970c  mov     edx, r12d; nDim
0x18008970f  mov     rcx, [r14]; psa
0x180089712  call    cs:__imp_SafeArrayGetUBound
0x180089718  test    eax, eax
0x18008971a  js      loc_1800897F6
0x180089720  cmp     esi, [rbp+plUbound]
0x180089723  jg      loc_1800897FE
0x180089729  mov     eax, esi
0x18008972b  sub     eax, [rbp+plLbound]
0x18008972e  movsxd  rdx, eax
0x180089731  mov     rax, [r14]
0x180089734  mov     rcx, [rax+10h]
0x180089738  movzx   eax, word ptr [rcx+rdx*2]
0x18008973c  mov     ecx, 12h
0x180089741  mov     word ptr [rbp+pvargSrc], cx
0x180089745  mov     word ptr [rbp+pvargSrc+8], ax
0x180089749  mov     rdi, [rbx+8]
0x18008974d  cmp     rdi, [rbx+10h]
0x180089751  jz      short loc_180089770
0x180089753  xor     eax, eax
0x180089755  mov     [rdi], ax
0x180089758  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18008975c  mov     rcx, rdi; pvargDest
0x18008975f  call    cs:__imp_VariantCopy
0x180089765  test    eax, eax
0x180089767  js      short loc_1800897E6
0x180089769  add     qword ptr [rbx+8], 18h
0x18008976e  jmp     short loc_180089780
0x180089770  lea     r8, [rbp+pvargSrc]
0x180089774  mov     rdx, rdi
0x180089777  mov     rcx, rbx
0x18008977a  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18008977f  nop
0x180089780  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089784  call    cs:__imp_VariantClear
0x18008978a  add     esi, r12d
0x18008978d  mov     [rbp+plLbound], 0
0x180089794  mov     [rbp+plUbound], 0
0x18008979b  lea     r8, [rbp+plLbound]; plLbound
0x18008979f  mov     edx, r12d; nDim
0x1800897a2  mov     rcx, [r14]; psa
0x1800897a5  call    cs:__imp_SafeArrayGetLBound
0x1800897ab  test    eax, eax
0x1800897ad  js      short loc_1800897D6
0x1800897af  jmp     loc_1800896A7
0x1800897b4  mov     rax, rbx
0x1800897b7  mov     rbx, [rsp+40h+arg_18]
0x1800897bf  add     rsp, 40h
0x1800897c3  pop     r14
0x1800897c5  pop     r12
0x1800897c7  pop     rdi
0x1800897c8  pop     rsi
0x1800897c9  pop     rbp
0x1800897ca  retn
0x1800897cb  mov     ecx, 80004005h; int
0x1800897d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897d6  mov     ecx, eax; int
0x1800897d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897de  mov     ecx, eax; int
0x1800897e0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897e6  mov     word ptr [rdi], 0Ah
0x1800897eb  mov     [rdi+8], eax
0x1800897ee  mov     ecx, eax; int
0x1800897f0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897f6  mov     ecx, eax; int
0x1800897f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897fe  mov     ecx, 80070057h; int
0x180089803  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089809  mov     ecx, eax; int
0x18008980b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
