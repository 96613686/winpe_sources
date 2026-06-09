# _anonymous_namespace_::wmi_object_property_meta::array_values_int_

- ea: `0x180089818`
- end: `0x1800899d3`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_int_`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x180088d44`
- `0x180089818`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089946`
- `OLEAUT32!__imp_VariantClear` at `0x180089946`
- `OLEAUT32!__imp_VariantCopy` at `0x180089921`
- `OLEAUT32!__imp_VariantCopy` at `0x180089921`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089875`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800898d6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089875`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800898d6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800898ae`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089967`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800898ae`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089967`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_int_(__int64 a1, SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  LONG v9; // eax
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
    v9 = *((_DWORD *)(*a2)->pvData + v4 - plLbound);
    pvargSrc.vt = 3;
    pvargSrc.lVal = v9;
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
0x180089818  mov     [rsp-28h+arg_18], rbx
0x18008981d  mov     [rsp-28h+arg_0], rcx
0x180089822  push    rbp
0x180089823  push    rsi
0x180089824  push    rdi
0x180089825  push    r12
0x180089827  push    r14
0x180089829  mov     rbp, rsp
0x18008982c  sub     rsp, 40h
0x180089830  mov     r14, rdx
0x180089833  mov     rbx, rcx
0x180089836  mov     [rbp+var_20], 0
0x18008983d  mov     qword ptr [rcx], 0
0x180089844  mov     qword ptr [rcx+8], 0
0x18008984c  mov     qword ptr [rcx+10h], 0
0x180089854  mov     r12d, 1
0x18008985a  mov     [rbp+var_20], r12d
0x18008985e  xor     esi, esi
0x180089860  mov     [rbp+plLbound], esi
0x180089863  mov     [rbp+plUbound], esi
0x180089866  jmp     loc_18008995D
0x18008986b  lea     r8, [rbp+plUbound]; plUbound
0x18008986f  mov     edx, r12d; nDim
0x180089872  mov     rcx, [r14]; psa
0x180089875  call    cs:__imp_SafeArrayGetUBound
0x18008987b  test    eax, eax
0x18008987d  js      loc_1800899A0
0x180089883  mov     eax, [rbp+plUbound]
0x180089886  sub     eax, [rbp+plLbound]
0x180089889  add     eax, r12d
0x18008988c  cmp     esi, eax
0x18008988e  jnb     loc_180089976
0x180089894  mov     rcx, [r14]; psa
0x180089897  test    rcx, rcx
0x18008989a  jz      loc_18008998D
0x1800898a0  mov     [rbp+plLbound], 0
0x1800898a7  lea     r8, [rbp+plLbound]; plLbound
0x1800898ab  mov     edx, r12d; nDim
0x1800898ae  call    cs:__imp_SafeArrayGetLBound
0x1800898b4  test    eax, eax
0x1800898b6  js      loc_1800899CB
0x1800898bc  cmp     esi, [rbp+plLbound]
0x1800898bf  jl      loc_1800899C0
0x1800898c5  mov     [rbp+plUbound], 0
0x1800898cc  lea     r8, [rbp+plUbound]; plUbound
0x1800898d0  mov     edx, r12d; nDim
0x1800898d3  mov     rcx, [r14]; psa
0x1800898d6  call    cs:__imp_SafeArrayGetUBound
0x1800898dc  test    eax, eax
0x1800898de  js      loc_1800899B8
0x1800898e4  cmp     esi, [rbp+plUbound]
0x1800898e7  jg      loc_1800899C0
0x1800898ed  mov     eax, esi
0x1800898ef  sub     eax, [rbp+plLbound]
0x1800898f2  movsxd  rdx, eax
0x1800898f5  mov     rax, [r14]
0x1800898f8  mov     rcx, [rax+10h]
0x1800898fc  mov     eax, [rcx+rdx*4]
0x1800898ff  mov     ecx, 3
0x180089904  mov     word ptr [rbp+pvargSrc], cx
0x180089908  mov     dword ptr [rbp+pvargSrc+8], eax
0x18008990b  mov     rdi, [rbx+8]
0x18008990f  cmp     rdi, [rbx+10h]
0x180089913  jz      short loc_180089932
0x180089915  xor     eax, eax
0x180089917  mov     [rdi], ax
0x18008991a  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18008991e  mov     rcx, rdi; pvargDest
0x180089921  call    cs:__imp_VariantCopy
0x180089927  test    eax, eax
0x180089929  js      short loc_1800899A8
0x18008992b  add     qword ptr [rbx+8], 18h
0x180089930  jmp     short loc_180089942
0x180089932  lea     r8, [rbp+pvargSrc]
0x180089936  mov     rdx, rdi
0x180089939  mov     rcx, rbx
0x18008993c  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180089941  nop
0x180089942  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089946  call    cs:__imp_VariantClear
0x18008994c  add     esi, r12d
0x18008994f  mov     [rbp+plLbound], 0
0x180089956  mov     [rbp+plUbound], 0
0x18008995d  lea     r8, [rbp+plLbound]; plLbound
0x180089961  mov     edx, r12d; nDim
0x180089964  mov     rcx, [r14]; psa
0x180089967  call    cs:__imp_SafeArrayGetLBound
0x18008996d  test    eax, eax
0x18008996f  js      short loc_180089998
0x180089971  jmp     loc_18008986B
0x180089976  mov     rax, rbx
0x180089979  mov     rbx, [rsp+40h+arg_18]
0x180089981  add     rsp, 40h
0x180089985  pop     r14
0x180089987  pop     r12
0x180089989  pop     rdi
0x18008998a  pop     rsi
0x18008998b  pop     rbp
0x18008998c  retn
0x18008998d  mov     ecx, 80004005h; int
0x180089992  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089998  mov     ecx, eax; int
0x18008999a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800899a0  mov     ecx, eax; int
0x1800899a2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800899a8  mov     word ptr [rdi], 0Ah
0x1800899ad  mov     [rdi+8], eax
0x1800899b0  mov     ecx, eax; int
0x1800899b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800899b8  mov     ecx, eax; int
0x1800899ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800899c0  mov     ecx, 80070057h; int
0x1800899c5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800899cb  mov     ecx, eax; int
0x1800899cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
