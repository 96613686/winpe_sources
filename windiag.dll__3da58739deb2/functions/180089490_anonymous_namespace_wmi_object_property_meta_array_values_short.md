# _anonymous_namespace_::wmi_object_property_meta::array_values_short_

- ea: `0x180089490`
- end: `0x18008964d`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_short_`
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
- `0x180089490`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800895c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800895c0`
- `OLEAUT32!__imp_VariantCopy` at `0x18008959b`
- `OLEAUT32!__imp_VariantCopy` at `0x18008959b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800894ed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008954e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800894ed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008954e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089526`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800895e1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089526`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800895e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_short_(__int64 a1, SAFEARRAY **a2)
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
    pvargSrc.vt = 2;
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
0x180089490  mov     [rsp-28h+arg_18], rbx
0x180089495  mov     [rsp-28h+arg_0], rcx
0x18008949a  push    rbp
0x18008949b  push    rsi
0x18008949c  push    rdi
0x18008949d  push    r12
0x18008949f  push    r14
0x1800894a1  mov     rbp, rsp
0x1800894a4  sub     rsp, 40h
0x1800894a8  mov     r14, rdx
0x1800894ab  mov     rbx, rcx
0x1800894ae  mov     [rbp+var_20], 0
0x1800894b5  mov     qword ptr [rcx], 0
0x1800894bc  mov     qword ptr [rcx+8], 0
0x1800894c4  mov     qword ptr [rcx+10h], 0
0x1800894cc  mov     r12d, 1
0x1800894d2  mov     [rbp+var_20], r12d
0x1800894d6  xor     esi, esi
0x1800894d8  mov     [rbp+plLbound], esi
0x1800894db  mov     [rbp+plUbound], esi
0x1800894de  jmp     loc_1800895D7
0x1800894e3  lea     r8, [rbp+plUbound]; plUbound
0x1800894e7  mov     edx, r12d; nDim
0x1800894ea  mov     rcx, [r14]; psa
0x1800894ed  call    cs:__imp_SafeArrayGetUBound
0x1800894f3  test    eax, eax
0x1800894f5  js      loc_18008961A
0x1800894fb  mov     eax, [rbp+plUbound]
0x1800894fe  sub     eax, [rbp+plLbound]
0x180089501  add     eax, r12d
0x180089504  cmp     esi, eax
0x180089506  jnb     loc_1800895F0
0x18008950c  mov     rcx, [r14]; psa
0x18008950f  test    rcx, rcx
0x180089512  jz      loc_180089607
0x180089518  mov     [rbp+plLbound], 0
0x18008951f  lea     r8, [rbp+plLbound]; plLbound
0x180089523  mov     edx, r12d; nDim
0x180089526  call    cs:__imp_SafeArrayGetLBound
0x18008952c  test    eax, eax
0x18008952e  js      loc_180089645
0x180089534  cmp     esi, [rbp+plLbound]
0x180089537  jl      loc_18008963A
0x18008953d  mov     [rbp+plUbound], 0
0x180089544  lea     r8, [rbp+plUbound]; plUbound
0x180089548  mov     edx, r12d; nDim
0x18008954b  mov     rcx, [r14]; psa
0x18008954e  call    cs:__imp_SafeArrayGetUBound
0x180089554  test    eax, eax
0x180089556  js      loc_180089632
0x18008955c  cmp     esi, [rbp+plUbound]
0x18008955f  jg      loc_18008963A
0x180089565  mov     eax, esi
0x180089567  sub     eax, [rbp+plLbound]
0x18008956a  movsxd  rdx, eax
0x18008956d  mov     rax, [r14]
0x180089570  mov     rcx, [rax+10h]
0x180089574  movzx   eax, word ptr [rcx+rdx*2]
0x180089578  mov     ecx, 2
0x18008957d  mov     word ptr [rbp+pvargSrc], cx
0x180089581  mov     word ptr [rbp+pvargSrc+8], ax
0x180089585  mov     rdi, [rbx+8]
0x180089589  cmp     rdi, [rbx+10h]
0x18008958d  jz      short loc_1800895AC
0x18008958f  xor     eax, eax
0x180089591  mov     [rdi], ax
0x180089594  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180089598  mov     rcx, rdi; pvargDest
0x18008959b  call    cs:__imp_VariantCopy
0x1800895a1  test    eax, eax
0x1800895a3  js      short loc_180089622
0x1800895a5  add     qword ptr [rbx+8], 18h
0x1800895aa  jmp     short loc_1800895BC
0x1800895ac  lea     r8, [rbp+pvargSrc]
0x1800895b0  mov     rdx, rdi
0x1800895b3  mov     rcx, rbx
0x1800895b6  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800895bb  nop
0x1800895bc  lea     rcx, [rbp+pvargSrc]; pvarg
0x1800895c0  call    cs:__imp_VariantClear
0x1800895c6  add     esi, r12d
0x1800895c9  mov     [rbp+plLbound], 0
0x1800895d0  mov     [rbp+plUbound], 0
0x1800895d7  lea     r8, [rbp+plLbound]; plLbound
0x1800895db  mov     edx, r12d; nDim
0x1800895de  mov     rcx, [r14]; psa
0x1800895e1  call    cs:__imp_SafeArrayGetLBound
0x1800895e7  test    eax, eax
0x1800895e9  js      short loc_180089612
0x1800895eb  jmp     loc_1800894E3
0x1800895f0  mov     rax, rbx
0x1800895f3  mov     rbx, [rsp+40h+arg_18]
0x1800895fb  add     rsp, 40h
0x1800895ff  pop     r14
0x180089601  pop     r12
0x180089603  pop     rdi
0x180089604  pop     rsi
0x180089605  pop     rbp
0x180089606  retn
0x180089607  mov     ecx, 80004005h; int
0x18008960c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089612  mov     ecx, eax; int
0x180089614  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008961a  mov     ecx, eax; int
0x18008961c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089622  mov     word ptr [rdi], 0Ah
0x180089627  mov     [rdi+8], eax
0x18008962a  mov     ecx, eax; int
0x18008962c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089632  mov     ecx, eax; int
0x180089634  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008963a  mov     ecx, 80070057h; int
0x18008963f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089645  mov     ecx, eax; int
0x180089647  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
