# _anonymous_namespace_::wmi_object_property_meta::array_values_double_

- ea: `0x180089d68`
- end: `0x180089f27`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_double_`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x180088d44`
- `0x180089d68`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089e9a`
- `OLEAUT32!__imp_VariantClear` at `0x180089e9a`
- `OLEAUT32!__imp_VariantCopy` at `0x180089e75`
- `OLEAUT32!__imp_VariantCopy` at `0x180089e75`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089dc5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089e26`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089dc5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089e26`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089dfe`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089ebb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089dfe`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089ebb`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_double_(__int64 a1, SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  LONGLONG v9; // xmm0_8
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
    pvargSrc.vt = 5;
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
0x180089d68  mov     [rsp-28h+arg_18], rbx
0x180089d6d  mov     [rsp-28h+arg_0], rcx
0x180089d72  push    rbp
0x180089d73  push    rsi
0x180089d74  push    rdi
0x180089d75  push    r12
0x180089d77  push    r14
0x180089d79  mov     rbp, rsp
0x180089d7c  sub     rsp, 40h
0x180089d80  mov     r14, rdx
0x180089d83  mov     rbx, rcx
0x180089d86  mov     [rbp+var_20], 0
0x180089d8d  mov     qword ptr [rcx], 0
0x180089d94  mov     qword ptr [rcx+8], 0
0x180089d9c  mov     qword ptr [rcx+10h], 0
0x180089da4  mov     r12d, 1
0x180089daa  mov     [rbp+var_20], r12d
0x180089dae  xor     esi, esi
0x180089db0  mov     [rbp+plLbound], esi
0x180089db3  mov     [rbp+plUbound], esi
0x180089db6  jmp     loc_180089EB1
0x180089dbb  lea     r8, [rbp+plUbound]; plUbound
0x180089dbf  mov     edx, r12d; nDim
0x180089dc2  mov     rcx, [r14]; psa
0x180089dc5  call    cs:__imp_SafeArrayGetUBound
0x180089dcb  test    eax, eax
0x180089dcd  js      loc_180089EF4
0x180089dd3  mov     eax, [rbp+plUbound]
0x180089dd6  sub     eax, [rbp+plLbound]
0x180089dd9  add     eax, r12d
0x180089ddc  cmp     esi, eax
0x180089dde  jnb     loc_180089ECA
0x180089de4  mov     rcx, [r14]; psa
0x180089de7  test    rcx, rcx
0x180089dea  jz      loc_180089EE1
0x180089df0  mov     [rbp+plLbound], 0
0x180089df7  lea     r8, [rbp+plLbound]; plLbound
0x180089dfb  mov     edx, r12d; nDim
0x180089dfe  call    cs:__imp_SafeArrayGetLBound
0x180089e04  test    eax, eax
0x180089e06  js      loc_180089F1F
0x180089e0c  cmp     esi, [rbp+plLbound]
0x180089e0f  jl      loc_180089F14
0x180089e15  mov     [rbp+plUbound], 0
0x180089e1c  lea     r8, [rbp+plUbound]; plUbound
0x180089e20  mov     edx, r12d; nDim
0x180089e23  mov     rcx, [r14]; psa
0x180089e26  call    cs:__imp_SafeArrayGetUBound
0x180089e2c  test    eax, eax
0x180089e2e  js      loc_180089F0C
0x180089e34  cmp     esi, [rbp+plUbound]
0x180089e37  jg      loc_180089F14
0x180089e3d  mov     eax, esi
0x180089e3f  sub     eax, [rbp+plLbound]
0x180089e42  movsxd  rdx, eax
0x180089e45  mov     rax, [r14]
0x180089e48  mov     rcx, [rax+10h]
0x180089e4c  movsd   xmm0, qword ptr [rcx+rdx*8]
0x180089e51  mov     eax, 5
0x180089e56  mov     word ptr [rbp+pvargSrc], ax
0x180089e5a  movsd   qword ptr [rbp+pvargSrc+8], xmm0
0x180089e5f  mov     rdi, [rbx+8]
0x180089e63  cmp     rdi, [rbx+10h]
0x180089e67  jz      short loc_180089E86
0x180089e69  xor     eax, eax
0x180089e6b  mov     [rdi], ax
0x180089e6e  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180089e72  mov     rcx, rdi; pvargDest
0x180089e75  call    cs:__imp_VariantCopy
0x180089e7b  test    eax, eax
0x180089e7d  js      short loc_180089EFC
0x180089e7f  add     qword ptr [rbx+8], 18h
0x180089e84  jmp     short loc_180089E96
0x180089e86  lea     r8, [rbp+pvargSrc]
0x180089e8a  mov     rdx, rdi
0x180089e8d  mov     rcx, rbx
0x180089e90  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180089e95  nop
0x180089e96  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089e9a  call    cs:__imp_VariantClear
0x180089ea0  add     esi, r12d
0x180089ea3  mov     [rbp+plLbound], 0
0x180089eaa  mov     [rbp+plUbound], 0
0x180089eb1  lea     r8, [rbp+plLbound]; plLbound
0x180089eb5  mov     edx, r12d; nDim
0x180089eb8  mov     rcx, [r14]; psa
0x180089ebb  call    cs:__imp_SafeArrayGetLBound
0x180089ec1  test    eax, eax
0x180089ec3  js      short loc_180089EEC
0x180089ec5  jmp     loc_180089DBB
0x180089eca  mov     rax, rbx
0x180089ecd  mov     rbx, [rsp+40h+arg_18]
0x180089ed5  add     rsp, 40h
0x180089ed9  pop     r14
0x180089edb  pop     r12
0x180089edd  pop     rdi
0x180089ede  pop     rsi
0x180089edf  pop     rbp
0x180089ee0  retn
0x180089ee1  mov     ecx, 80004005h; int
0x180089ee6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089eec  mov     ecx, eax; int
0x180089eee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089ef4  mov     ecx, eax; int
0x180089ef6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089efc  mov     word ptr [rdi], 0Ah
0x180089f01  mov     [rdi+8], eax
0x180089f04  mov     ecx, eax; int
0x180089f06  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089f0c  mov     ecx, eax; int
0x180089f0e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089f14  mov     ecx, 80070057h; int
0x180089f19  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089f1f  mov     ecx, eax; int
0x180089f21  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
