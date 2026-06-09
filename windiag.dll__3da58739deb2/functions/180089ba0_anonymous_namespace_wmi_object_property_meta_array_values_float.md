# _anonymous_namespace_::wmi_object_property_meta::array_values_float_

- ea: `0x180089ba0`
- end: `0x180089d5f`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_float_`
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
- `0x180089ba0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089cd2`
- `OLEAUT32!__imp_VariantClear` at `0x180089cd2`
- `OLEAUT32!__imp_VariantCopy` at `0x180089cad`
- `OLEAUT32!__imp_VariantCopy` at `0x180089cad`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089bfd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089c5e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089bfd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089c5e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089c36`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089cf3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089c36`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089cf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_float_(__int64 a1, SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  LONG v9; // xmm0_4
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
    pvargSrc.vt = 4;
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
0x180089ba0  mov     [rsp-28h+arg_18], rbx
0x180089ba5  mov     [rsp-28h+arg_0], rcx
0x180089baa  push    rbp
0x180089bab  push    rsi
0x180089bac  push    rdi
0x180089bad  push    r12
0x180089baf  push    r14
0x180089bb1  mov     rbp, rsp
0x180089bb4  sub     rsp, 40h
0x180089bb8  mov     r14, rdx
0x180089bbb  mov     rbx, rcx
0x180089bbe  mov     [rbp+var_20], 0
0x180089bc5  mov     qword ptr [rcx], 0
0x180089bcc  mov     qword ptr [rcx+8], 0
0x180089bd4  mov     qword ptr [rcx+10h], 0
0x180089bdc  mov     r12d, 1
0x180089be2  mov     [rbp+var_20], r12d
0x180089be6  xor     esi, esi
0x180089be8  mov     [rbp+plLbound], esi
0x180089beb  mov     [rbp+plUbound], esi
0x180089bee  jmp     loc_180089CE9
0x180089bf3  lea     r8, [rbp+plUbound]; plUbound
0x180089bf7  mov     edx, r12d; nDim
0x180089bfa  mov     rcx, [r14]; psa
0x180089bfd  call    cs:__imp_SafeArrayGetUBound
0x180089c03  test    eax, eax
0x180089c05  js      loc_180089D2C
0x180089c0b  mov     eax, [rbp+plUbound]
0x180089c0e  sub     eax, [rbp+plLbound]
0x180089c11  add     eax, r12d
0x180089c14  cmp     esi, eax
0x180089c16  jnb     loc_180089D02
0x180089c1c  mov     rcx, [r14]; psa
0x180089c1f  test    rcx, rcx
0x180089c22  jz      loc_180089D19
0x180089c28  mov     [rbp+plLbound], 0
0x180089c2f  lea     r8, [rbp+plLbound]; plLbound
0x180089c33  mov     edx, r12d; nDim
0x180089c36  call    cs:__imp_SafeArrayGetLBound
0x180089c3c  test    eax, eax
0x180089c3e  js      loc_180089D57
0x180089c44  cmp     esi, [rbp+plLbound]
0x180089c47  jl      loc_180089D4C
0x180089c4d  mov     [rbp+plUbound], 0
0x180089c54  lea     r8, [rbp+plUbound]; plUbound
0x180089c58  mov     edx, r12d; nDim
0x180089c5b  mov     rcx, [r14]; psa
0x180089c5e  call    cs:__imp_SafeArrayGetUBound
0x180089c64  test    eax, eax
0x180089c66  js      loc_180089D44
0x180089c6c  cmp     esi, [rbp+plUbound]
0x180089c6f  jg      loc_180089D4C
0x180089c75  mov     eax, esi
0x180089c77  sub     eax, [rbp+plLbound]
0x180089c7a  movsxd  rdx, eax
0x180089c7d  mov     rax, [r14]
0x180089c80  mov     rcx, [rax+10h]
0x180089c84  movss   xmm0, dword ptr [rcx+rdx*4]
0x180089c89  mov     eax, 4
0x180089c8e  mov     word ptr [rbp+pvargSrc], ax
0x180089c92  movss   dword ptr [rbp+pvargSrc+8], xmm0
0x180089c97  mov     rdi, [rbx+8]
0x180089c9b  cmp     rdi, [rbx+10h]
0x180089c9f  jz      short loc_180089CBE
0x180089ca1  xor     eax, eax
0x180089ca3  mov     [rdi], ax
0x180089ca6  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180089caa  mov     rcx, rdi; pvargDest
0x180089cad  call    cs:__imp_VariantCopy
0x180089cb3  test    eax, eax
0x180089cb5  js      short loc_180089D34
0x180089cb7  add     qword ptr [rbx+8], 18h
0x180089cbc  jmp     short loc_180089CCE
0x180089cbe  lea     r8, [rbp+pvargSrc]
0x180089cc2  mov     rdx, rdi
0x180089cc5  mov     rcx, rbx
0x180089cc8  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180089ccd  nop
0x180089cce  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089cd2  call    cs:__imp_VariantClear
0x180089cd8  add     esi, r12d
0x180089cdb  mov     [rbp+plLbound], 0
0x180089ce2  mov     [rbp+plUbound], 0
0x180089ce9  lea     r8, [rbp+plLbound]; plLbound
0x180089ced  mov     edx, r12d; nDim
0x180089cf0  mov     rcx, [r14]; psa
0x180089cf3  call    cs:__imp_SafeArrayGetLBound
0x180089cf9  test    eax, eax
0x180089cfb  js      short loc_180089D24
0x180089cfd  jmp     loc_180089BF3
0x180089d02  mov     rax, rbx
0x180089d05  mov     rbx, [rsp+40h+arg_18]
0x180089d0d  add     rsp, 40h
0x180089d11  pop     r14
0x180089d13  pop     r12
0x180089d15  pop     rdi
0x180089d16  pop     rsi
0x180089d17  pop     rbp
0x180089d18  retn
0x180089d19  mov     ecx, 80004005h; int
0x180089d1e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d24  mov     ecx, eax; int
0x180089d26  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d2c  mov     ecx, eax; int
0x180089d2e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d34  mov     word ptr [rdi], 0Ah
0x180089d39  mov     [rdi+8], eax
0x180089d3c  mov     ecx, eax; int
0x180089d3e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d44  mov     ecx, eax; int
0x180089d46  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d4c  mov     ecx, 80070057h; int
0x180089d51  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089d57  mov     ecx, eax; int
0x180089d59  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
