# _anonymous_namespace_::wmi_object_property_meta::array_values_unsigned___int64_

- ea: `0x18008a324`
- end: `0x18008a4e1`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_unsigned___int64_`
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
- `0x18008a324`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008a454`
- `OLEAUT32!__imp_VariantClear` at `0x18008a454`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a42f`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a42f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a381`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a3e2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a381`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a3e2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a3ba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a475`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a3ba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a475`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_unsigned___int64_(
        __int64 a1,
        SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  LONGLONG v9; // rax
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
    v9 = *((_QWORD *)(*a2)->pvData + v4 - plLbound);
    pvargSrc.vt = 21;
    pvargSrc.llVal = v9;
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
0x18008a324  mov     [rsp-28h+arg_18], rbx
0x18008a329  mov     [rsp-28h+arg_0], rcx
0x18008a32e  push    rbp
0x18008a32f  push    rsi
0x18008a330  push    rdi
0x18008a331  push    r12
0x18008a333  push    r14
0x18008a335  mov     rbp, rsp
0x18008a338  sub     rsp, 40h
0x18008a33c  mov     r14, rdx
0x18008a33f  mov     rbx, rcx
0x18008a342  mov     [rbp+var_20], 0
0x18008a349  mov     qword ptr [rcx], 0
0x18008a350  mov     qword ptr [rcx+8], 0
0x18008a358  mov     qword ptr [rcx+10h], 0
0x18008a360  mov     r12d, 1
0x18008a366  mov     [rbp+var_20], r12d
0x18008a36a  xor     esi, esi
0x18008a36c  mov     [rbp+plLbound], esi
0x18008a36f  mov     [rbp+plUbound], esi
0x18008a372  jmp     loc_18008A46B
0x18008a377  lea     r8, [rbp+plUbound]; plUbound
0x18008a37b  mov     edx, r12d; nDim
0x18008a37e  mov     rcx, [r14]; psa
0x18008a381  call    cs:__imp_SafeArrayGetUBound
0x18008a387  test    eax, eax
0x18008a389  js      loc_18008A4AE
0x18008a38f  mov     eax, [rbp+plUbound]
0x18008a392  sub     eax, [rbp+plLbound]
0x18008a395  add     eax, r12d
0x18008a398  cmp     esi, eax
0x18008a39a  jnb     loc_18008A484
0x18008a3a0  mov     rcx, [r14]; psa
0x18008a3a3  test    rcx, rcx
0x18008a3a6  jz      loc_18008A49B
0x18008a3ac  mov     [rbp+plLbound], 0
0x18008a3b3  lea     r8, [rbp+plLbound]; plLbound
0x18008a3b7  mov     edx, r12d; nDim
0x18008a3ba  call    cs:__imp_SafeArrayGetLBound
0x18008a3c0  test    eax, eax
0x18008a3c2  js      loc_18008A4D9
0x18008a3c8  cmp     esi, [rbp+plLbound]
0x18008a3cb  jl      loc_18008A4CE
0x18008a3d1  mov     [rbp+plUbound], 0
0x18008a3d8  lea     r8, [rbp+plUbound]; plUbound
0x18008a3dc  mov     edx, r12d; nDim
0x18008a3df  mov     rcx, [r14]; psa
0x18008a3e2  call    cs:__imp_SafeArrayGetUBound
0x18008a3e8  test    eax, eax
0x18008a3ea  js      loc_18008A4C6
0x18008a3f0  cmp     esi, [rbp+plUbound]
0x18008a3f3  jg      loc_18008A4CE
0x18008a3f9  mov     eax, esi
0x18008a3fb  sub     eax, [rbp+plLbound]
0x18008a3fe  movsxd  rdx, eax
0x18008a401  mov     rax, [r14]
0x18008a404  mov     rcx, [rax+10h]
0x18008a408  mov     rax, [rcx+rdx*8]
0x18008a40c  mov     ecx, 15h
0x18008a411  mov     word ptr [rbp+pvargSrc], cx
0x18008a415  mov     qword ptr [rbp+pvargSrc+8], rax
0x18008a419  mov     rdi, [rbx+8]
0x18008a41d  cmp     rdi, [rbx+10h]
0x18008a421  jz      short loc_18008A440
0x18008a423  xor     eax, eax
0x18008a425  mov     [rdi], ax
0x18008a428  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18008a42c  mov     rcx, rdi; pvargDest
0x18008a42f  call    cs:__imp_VariantCopy
0x18008a435  test    eax, eax
0x18008a437  js      short loc_18008A4B6
0x18008a439  add     qword ptr [rbx+8], 18h
0x18008a43e  jmp     short loc_18008A450
0x18008a440  lea     r8, [rbp+pvargSrc]
0x18008a444  mov     rdx, rdi
0x18008a447  mov     rcx, rbx
0x18008a44a  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18008a44f  nop
0x18008a450  lea     rcx, [rbp+pvargSrc]; pvarg
0x18008a454  call    cs:__imp_VariantClear
0x18008a45a  add     esi, r12d
0x18008a45d  mov     [rbp+plLbound], 0
0x18008a464  mov     [rbp+plUbound], 0
0x18008a46b  lea     r8, [rbp+plLbound]; plLbound
0x18008a46f  mov     edx, r12d; nDim
0x18008a472  mov     rcx, [r14]; psa
0x18008a475  call    cs:__imp_SafeArrayGetLBound
0x18008a47b  test    eax, eax
0x18008a47d  js      short loc_18008A4A6
0x18008a47f  jmp     loc_18008A377
0x18008a484  mov     rax, rbx
0x18008a487  mov     rbx, [rsp+40h+arg_18]
0x18008a48f  add     rsp, 40h
0x18008a493  pop     r14
0x18008a495  pop     r12
0x18008a497  pop     rdi
0x18008a498  pop     rsi
0x18008a499  pop     rbp
0x18008a49a  retn
0x18008a49b  mov     ecx, 80004005h; int
0x18008a4a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4a6  mov     ecx, eax; int
0x18008a4a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4ae  mov     ecx, eax; int
0x18008a4b0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4b6  mov     word ptr [rdi], 0Ah
0x18008a4bb  mov     [rdi+8], eax
0x18008a4be  mov     ecx, eax; int
0x18008a4c0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4c6  mov     ecx, eax; int
0x18008a4c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4ce  mov     ecx, 80070057h; int
0x18008a4d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a4d9  mov     ecx, eax; int
0x18008a4db  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
