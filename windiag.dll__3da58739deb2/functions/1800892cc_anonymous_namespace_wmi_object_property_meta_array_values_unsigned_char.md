# _anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_char_

- ea: `0x1800892cc`
- end: `0x180089487`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_char_`
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
- `0x1800892cc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800893fa`
- `OLEAUT32!__imp_VariantClear` at `0x1800893fa`
- `OLEAUT32!__imp_VariantCopy` at `0x1800893d5`
- `OLEAUT32!__imp_VariantCopy` at `0x1800893d5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089329`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008938a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089329`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008938a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089362`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008941b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089362`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008941b`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_char_(
        __int64 a1,
        SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT UBound; // eax
  SAFEARRAY *v6; // rcx
  HRESULT v7; // eax
  HRESULT v8; // eax
  BYTE v9; // al
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
    v9 = *((_BYTE *)(*a2)->pvData + v4 - plLbound);
    pvargSrc.vt = 17;
    pvargSrc.bVal = v9;
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
0x1800892cc  mov     [rsp-28h+arg_18], rbx
0x1800892d1  mov     [rsp-28h+arg_0], rcx
0x1800892d6  push    rbp
0x1800892d7  push    rsi
0x1800892d8  push    rdi
0x1800892d9  push    r12
0x1800892db  push    r14
0x1800892dd  mov     rbp, rsp
0x1800892e0  sub     rsp, 40h
0x1800892e4  mov     r14, rdx
0x1800892e7  mov     rbx, rcx
0x1800892ea  mov     [rbp+var_20], 0
0x1800892f1  mov     qword ptr [rcx], 0
0x1800892f8  mov     qword ptr [rcx+8], 0
0x180089300  mov     qword ptr [rcx+10h], 0
0x180089308  mov     r12d, 1
0x18008930e  mov     [rbp+var_20], r12d
0x180089312  xor     esi, esi
0x180089314  mov     [rbp+plLbound], esi
0x180089317  mov     [rbp+plUbound], esi
0x18008931a  jmp     loc_180089411
0x18008931f  lea     r8, [rbp+plUbound]; plUbound
0x180089323  mov     edx, r12d; nDim
0x180089326  mov     rcx, [r14]; psa
0x180089329  call    cs:__imp_SafeArrayGetUBound
0x18008932f  test    eax, eax
0x180089331  js      loc_180089454
0x180089337  mov     eax, [rbp+plUbound]
0x18008933a  sub     eax, [rbp+plLbound]
0x18008933d  add     eax, r12d
0x180089340  cmp     esi, eax
0x180089342  jnb     loc_18008942A
0x180089348  mov     rcx, [r14]; psa
0x18008934b  test    rcx, rcx
0x18008934e  jz      loc_180089441
0x180089354  mov     [rbp+plLbound], 0
0x18008935b  lea     r8, [rbp+plLbound]; plLbound
0x18008935f  mov     edx, r12d; nDim
0x180089362  call    cs:__imp_SafeArrayGetLBound
0x180089368  test    eax, eax
0x18008936a  js      loc_18008947F
0x180089370  cmp     esi, [rbp+plLbound]
0x180089373  jl      loc_180089474
0x180089379  mov     [rbp+plUbound], 0
0x180089380  lea     r8, [rbp+plUbound]; plUbound
0x180089384  mov     edx, r12d; nDim
0x180089387  mov     rcx, [r14]; psa
0x18008938a  call    cs:__imp_SafeArrayGetUBound
0x180089390  test    eax, eax
0x180089392  js      loc_18008946C
0x180089398  cmp     esi, [rbp+plUbound]
0x18008939b  jg      loc_180089474
0x1800893a1  mov     eax, esi
0x1800893a3  sub     eax, [rbp+plLbound]
0x1800893a6  movsxd  rdx, eax
0x1800893a9  mov     rax, [r14]
0x1800893ac  mov     rcx, [rax+10h]
0x1800893b0  mov     al, [rdx+rcx]
0x1800893b3  mov     ecx, 11h
0x1800893b8  mov     word ptr [rbp+pvargSrc], cx
0x1800893bc  mov     byte ptr [rbp+pvargSrc+8], al
0x1800893bf  mov     rdi, [rbx+8]
0x1800893c3  cmp     rdi, [rbx+10h]
0x1800893c7  jz      short loc_1800893E6
0x1800893c9  xor     eax, eax
0x1800893cb  mov     [rdi], ax
0x1800893ce  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x1800893d2  mov     rcx, rdi; pvargDest
0x1800893d5  call    cs:__imp_VariantCopy
0x1800893db  test    eax, eax
0x1800893dd  js      short loc_18008945C
0x1800893df  add     qword ptr [rbx+8], 18h
0x1800893e4  jmp     short loc_1800893F6
0x1800893e6  lea     r8, [rbp+pvargSrc]
0x1800893ea  mov     rdx, rdi
0x1800893ed  mov     rcx, rbx
0x1800893f0  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x1800893f5  nop
0x1800893f6  lea     rcx, [rbp+pvargSrc]; pvarg
0x1800893fa  call    cs:__imp_VariantClear
0x180089400  add     esi, r12d
0x180089403  mov     [rbp+plLbound], 0
0x18008940a  mov     [rbp+plUbound], 0
0x180089411  lea     r8, [rbp+plLbound]; plLbound
0x180089415  mov     edx, r12d; nDim
0x180089418  mov     rcx, [r14]; psa
0x18008941b  call    cs:__imp_SafeArrayGetLBound
0x180089421  test    eax, eax
0x180089423  js      short loc_18008944C
0x180089425  jmp     loc_18008931F
0x18008942a  mov     rax, rbx
0x18008942d  mov     rbx, [rsp+40h+arg_18]
0x180089435  add     rsp, 40h
0x180089439  pop     r14
0x18008943b  pop     r12
0x18008943d  pop     rdi
0x18008943e  pop     rsi
0x18008943f  pop     rbp
0x180089440  retn
0x180089441  mov     ecx, 80004005h; int
0x180089446  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008944c  mov     ecx, eax; int
0x18008944e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089454  mov     ecx, eax; int
0x180089456  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008945c  mov     word ptr [rdi], 0Ah
0x180089461  mov     [rdi+8], eax
0x180089464  mov     ecx, eax; int
0x180089466  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008946c  mov     ecx, eax; int
0x18008946e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089474  mov     ecx, 80070057h; int
0x180089479  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008947f  mov     ecx, eax; int
0x180089481  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
