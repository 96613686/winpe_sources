# _anonymous_namespace_::wmi_object_property_meta::array_values_char_

- ea: `0x180089108`
- end: `0x1800892c3`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_char_`
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
- `0x180089108`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089236`
- `OLEAUT32!__imp_VariantClear` at `0x180089236`
- `OLEAUT32!__imp_VariantCopy` at `0x180089211`
- `OLEAUT32!__imp_VariantCopy` at `0x180089211`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089165`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800891c6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089165`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800891c6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008919e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089257`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008919e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089257`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_char_(__int64 a1, SAFEARRAY **a2)
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
    pvargSrc.vt = 16;
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
0x180089108  mov     [rsp-28h+arg_18], rbx
0x18008910d  mov     [rsp-28h+arg_0], rcx
0x180089112  push    rbp
0x180089113  push    rsi
0x180089114  push    rdi
0x180089115  push    r12
0x180089117  push    r14
0x180089119  mov     rbp, rsp
0x18008911c  sub     rsp, 40h
0x180089120  mov     r14, rdx
0x180089123  mov     rbx, rcx
0x180089126  mov     [rbp+var_20], 0
0x18008912d  mov     qword ptr [rcx], 0
0x180089134  mov     qword ptr [rcx+8], 0
0x18008913c  mov     qword ptr [rcx+10h], 0
0x180089144  mov     r12d, 1
0x18008914a  mov     [rbp+var_20], r12d
0x18008914e  xor     esi, esi
0x180089150  mov     [rbp+plLbound], esi
0x180089153  mov     [rbp+plUbound], esi
0x180089156  jmp     loc_18008924D
0x18008915b  lea     r8, [rbp+plUbound]; plUbound
0x18008915f  mov     edx, r12d; nDim
0x180089162  mov     rcx, [r14]; psa
0x180089165  call    cs:__imp_SafeArrayGetUBound
0x18008916b  test    eax, eax
0x18008916d  js      loc_180089290
0x180089173  mov     eax, [rbp+plUbound]
0x180089176  sub     eax, [rbp+plLbound]
0x180089179  add     eax, r12d
0x18008917c  cmp     esi, eax
0x18008917e  jnb     loc_180089266
0x180089184  mov     rcx, [r14]; psa
0x180089187  test    rcx, rcx
0x18008918a  jz      loc_18008927D
0x180089190  mov     [rbp+plLbound], 0
0x180089197  lea     r8, [rbp+plLbound]; plLbound
0x18008919b  mov     edx, r12d; nDim
0x18008919e  call    cs:__imp_SafeArrayGetLBound
0x1800891a4  test    eax, eax
0x1800891a6  js      loc_1800892BB
0x1800891ac  cmp     esi, [rbp+plLbound]
0x1800891af  jl      loc_1800892B0
0x1800891b5  mov     [rbp+plUbound], 0
0x1800891bc  lea     r8, [rbp+plUbound]; plUbound
0x1800891c0  mov     edx, r12d; nDim
0x1800891c3  mov     rcx, [r14]; psa
0x1800891c6  call    cs:__imp_SafeArrayGetUBound
0x1800891cc  test    eax, eax
0x1800891ce  js      loc_1800892A8
0x1800891d4  cmp     esi, [rbp+plUbound]
0x1800891d7  jg      loc_1800892B0
0x1800891dd  mov     eax, esi
0x1800891df  sub     eax, [rbp+plLbound]
0x1800891e2  movsxd  rdx, eax
0x1800891e5  mov     rax, [r14]
0x1800891e8  mov     rcx, [rax+10h]
0x1800891ec  mov     al, [rdx+rcx]
0x1800891ef  mov     ecx, 10h
0x1800891f4  mov     word ptr [rbp+pvargSrc], cx
0x1800891f8  mov     byte ptr [rbp+pvargSrc+8], al
0x1800891fb  mov     rdi, [rbx+8]
0x1800891ff  cmp     rdi, [rbx+10h]
0x180089203  jz      short loc_180089222
0x180089205  xor     eax, eax
0x180089207  mov     [rdi], ax
0x18008920a  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18008920e  mov     rcx, rdi; pvargDest
0x180089211  call    cs:__imp_VariantCopy
0x180089217  test    eax, eax
0x180089219  js      short loc_180089298
0x18008921b  add     qword ptr [rbx+8], 18h
0x180089220  jmp     short loc_180089232
0x180089222  lea     r8, [rbp+pvargSrc]
0x180089226  mov     rdx, rdi
0x180089229  mov     rcx, rbx
0x18008922c  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180089231  nop
0x180089232  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089236  call    cs:__imp_VariantClear
0x18008923c  add     esi, r12d
0x18008923f  mov     [rbp+plLbound], 0
0x180089246  mov     [rbp+plUbound], 0
0x18008924d  lea     r8, [rbp+plLbound]; plLbound
0x180089251  mov     edx, r12d; nDim
0x180089254  mov     rcx, [r14]; psa
0x180089257  call    cs:__imp_SafeArrayGetLBound
0x18008925d  test    eax, eax
0x18008925f  js      short loc_180089288
0x180089261  jmp     loc_18008915B
0x180089266  mov     rax, rbx
0x180089269  mov     rbx, [rsp+40h+arg_18]
0x180089271  add     rsp, 40h
0x180089275  pop     r14
0x180089277  pop     r12
0x180089279  pop     rdi
0x18008927a  pop     rsi
0x18008927b  pop     rbp
0x18008927c  retn
0x18008927d  mov     ecx, 80004005h; int
0x180089282  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089288  mov     ecx, eax; int
0x18008928a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089290  mov     ecx, eax; int
0x180089292  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089298  mov     word ptr [rdi], 0Ah
0x18008929d  mov     [rdi+8], eax
0x1800892a0  mov     ecx, eax; int
0x1800892a2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800892a8  mov     ecx, eax; int
0x1800892aa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800892b0  mov     ecx, 80070057h; int
0x1800892b5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800892bb  mov     ecx, eax; int
0x1800892bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
