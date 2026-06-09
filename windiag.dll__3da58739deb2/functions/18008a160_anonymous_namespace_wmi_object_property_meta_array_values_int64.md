# _anonymous_namespace_::wmi_object_property_meta::array_values___int64_

- ea: `0x18008a160`
- end: `0x18008a31d`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values___int64_`
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
- `0x18008a160`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008a290`
- `OLEAUT32!__imp_VariantClear` at `0x18008a290`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a26b`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a26b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a1bd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a21e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a1bd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008a21e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a1f6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a2b1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a1f6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a2b1`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values___int64_(__int64 a1, SAFEARRAY **a2)
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
    pvargSrc.vt = 20;
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
0x18008a160  mov     [rsp-28h+arg_18], rbx
0x18008a165  mov     [rsp-28h+arg_0], rcx
0x18008a16a  push    rbp
0x18008a16b  push    rsi
0x18008a16c  push    rdi
0x18008a16d  push    r12
0x18008a16f  push    r14
0x18008a171  mov     rbp, rsp
0x18008a174  sub     rsp, 40h
0x18008a178  mov     r14, rdx
0x18008a17b  mov     rbx, rcx
0x18008a17e  mov     [rbp+var_20], 0
0x18008a185  mov     qword ptr [rcx], 0
0x18008a18c  mov     qword ptr [rcx+8], 0
0x18008a194  mov     qword ptr [rcx+10h], 0
0x18008a19c  mov     r12d, 1
0x18008a1a2  mov     [rbp+var_20], r12d
0x18008a1a6  xor     esi, esi
0x18008a1a8  mov     [rbp+plLbound], esi
0x18008a1ab  mov     [rbp+plUbound], esi
0x18008a1ae  jmp     loc_18008A2A7
0x18008a1b3  lea     r8, [rbp+plUbound]; plUbound
0x18008a1b7  mov     edx, r12d; nDim
0x18008a1ba  mov     rcx, [r14]; psa
0x18008a1bd  call    cs:__imp_SafeArrayGetUBound
0x18008a1c3  test    eax, eax
0x18008a1c5  js      loc_18008A2EA
0x18008a1cb  mov     eax, [rbp+plUbound]
0x18008a1ce  sub     eax, [rbp+plLbound]
0x18008a1d1  add     eax, r12d
0x18008a1d4  cmp     esi, eax
0x18008a1d6  jnb     loc_18008A2C0
0x18008a1dc  mov     rcx, [r14]; psa
0x18008a1df  test    rcx, rcx
0x18008a1e2  jz      loc_18008A2D7
0x18008a1e8  mov     [rbp+plLbound], 0
0x18008a1ef  lea     r8, [rbp+plLbound]; plLbound
0x18008a1f3  mov     edx, r12d; nDim
0x18008a1f6  call    cs:__imp_SafeArrayGetLBound
0x18008a1fc  test    eax, eax
0x18008a1fe  js      loc_18008A315
0x18008a204  cmp     esi, [rbp+plLbound]
0x18008a207  jl      loc_18008A30A
0x18008a20d  mov     [rbp+plUbound], 0
0x18008a214  lea     r8, [rbp+plUbound]; plUbound
0x18008a218  mov     edx, r12d; nDim
0x18008a21b  mov     rcx, [r14]; psa
0x18008a21e  call    cs:__imp_SafeArrayGetUBound
0x18008a224  test    eax, eax
0x18008a226  js      loc_18008A302
0x18008a22c  cmp     esi, [rbp+plUbound]
0x18008a22f  jg      loc_18008A30A
0x18008a235  mov     eax, esi
0x18008a237  sub     eax, [rbp+plLbound]
0x18008a23a  movsxd  rdx, eax
0x18008a23d  mov     rax, [r14]
0x18008a240  mov     rcx, [rax+10h]
0x18008a244  mov     rax, [rcx+rdx*8]
0x18008a248  mov     ecx, 14h
0x18008a24d  mov     word ptr [rbp+pvargSrc], cx
0x18008a251  mov     qword ptr [rbp+pvargSrc+8], rax
0x18008a255  mov     rdi, [rbx+8]
0x18008a259  cmp     rdi, [rbx+10h]
0x18008a25d  jz      short loc_18008A27C
0x18008a25f  xor     eax, eax
0x18008a261  mov     [rdi], ax
0x18008a264  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18008a268  mov     rcx, rdi; pvargDest
0x18008a26b  call    cs:__imp_VariantCopy
0x18008a271  test    eax, eax
0x18008a273  js      short loc_18008A2F2
0x18008a275  add     qword ptr [rbx+8], 18h
0x18008a27a  jmp     short loc_18008A28C
0x18008a27c  lea     r8, [rbp+pvargSrc]
0x18008a280  mov     rdx, rdi
0x18008a283  mov     rcx, rbx
0x18008a286  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18008a28b  nop
0x18008a28c  lea     rcx, [rbp+pvargSrc]; pvarg
0x18008a290  call    cs:__imp_VariantClear
0x18008a296  add     esi, r12d
0x18008a299  mov     [rbp+plLbound], 0
0x18008a2a0  mov     [rbp+plUbound], 0
0x18008a2a7  lea     r8, [rbp+plLbound]; plLbound
0x18008a2ab  mov     edx, r12d; nDim
0x18008a2ae  mov     rcx, [r14]; psa
0x18008a2b1  call    cs:__imp_SafeArrayGetLBound
0x18008a2b7  test    eax, eax
0x18008a2b9  js      short loc_18008A2E2
0x18008a2bb  jmp     loc_18008A1B3
0x18008a2c0  mov     rax, rbx
0x18008a2c3  mov     rbx, [rsp+40h+arg_18]
0x18008a2cb  add     rsp, 40h
0x18008a2cf  pop     r14
0x18008a2d1  pop     r12
0x18008a2d3  pop     rdi
0x18008a2d4  pop     rsi
0x18008a2d5  pop     rbp
0x18008a2d6  retn
0x18008a2d7  mov     ecx, 80004005h; int
0x18008a2dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a2e2  mov     ecx, eax; int
0x18008a2e4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a2ea  mov     ecx, eax; int
0x18008a2ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a2f2  mov     word ptr [rdi], 0Ah
0x18008a2f7  mov     [rdi+8], eax
0x18008a2fa  mov     ecx, eax; int
0x18008a2fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a302  mov     ecx, eax; int
0x18008a304  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a30a  mov     ecx, 80070057h; int
0x18008a30f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a315  mov     ecx, eax; int
0x18008a317  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
