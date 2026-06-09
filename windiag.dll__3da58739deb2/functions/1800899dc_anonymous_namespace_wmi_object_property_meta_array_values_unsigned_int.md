# _anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_int_

- ea: `0x1800899dc`
- end: `0x180089b97`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_int_`
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
- `0x1800899dc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180089b0a`
- `OLEAUT32!__imp_VariantClear` at `0x180089b0a`
- `OLEAUT32!__imp_VariantCopy` at `0x180089ae5`
- `OLEAUT32!__imp_VariantCopy` at `0x180089ae5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089a39`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089a9a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089a39`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089a9a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089a72`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089b2b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089a72`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089b2b`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_int_(
        __int64 a1,
        SAFEARRAY **a2)
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
    pvargSrc.vt = 19;
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
0x1800899dc  mov     [rsp-28h+arg_18], rbx
0x1800899e1  mov     [rsp-28h+arg_0], rcx
0x1800899e6  push    rbp
0x1800899e7  push    rsi
0x1800899e8  push    rdi
0x1800899e9  push    r12
0x1800899eb  push    r14
0x1800899ed  mov     rbp, rsp
0x1800899f0  sub     rsp, 40h
0x1800899f4  mov     r14, rdx
0x1800899f7  mov     rbx, rcx
0x1800899fa  mov     [rbp+var_20], 0
0x180089a01  mov     qword ptr [rcx], 0
0x180089a08  mov     qword ptr [rcx+8], 0
0x180089a10  mov     qword ptr [rcx+10h], 0
0x180089a18  mov     r12d, 1
0x180089a1e  mov     [rbp+var_20], r12d
0x180089a22  xor     esi, esi
0x180089a24  mov     [rbp+plLbound], esi
0x180089a27  mov     [rbp+plUbound], esi
0x180089a2a  jmp     loc_180089B21
0x180089a2f  lea     r8, [rbp+plUbound]; plUbound
0x180089a33  mov     edx, r12d; nDim
0x180089a36  mov     rcx, [r14]; psa
0x180089a39  call    cs:__imp_SafeArrayGetUBound
0x180089a3f  test    eax, eax
0x180089a41  js      loc_180089B64
0x180089a47  mov     eax, [rbp+plUbound]
0x180089a4a  sub     eax, [rbp+plLbound]
0x180089a4d  add     eax, r12d
0x180089a50  cmp     esi, eax
0x180089a52  jnb     loc_180089B3A
0x180089a58  mov     rcx, [r14]; psa
0x180089a5b  test    rcx, rcx
0x180089a5e  jz      loc_180089B51
0x180089a64  mov     [rbp+plLbound], 0
0x180089a6b  lea     r8, [rbp+plLbound]; plLbound
0x180089a6f  mov     edx, r12d; nDim
0x180089a72  call    cs:__imp_SafeArrayGetLBound
0x180089a78  test    eax, eax
0x180089a7a  js      loc_180089B8F
0x180089a80  cmp     esi, [rbp+plLbound]
0x180089a83  jl      loc_180089B84
0x180089a89  mov     [rbp+plUbound], 0
0x180089a90  lea     r8, [rbp+plUbound]; plUbound
0x180089a94  mov     edx, r12d; nDim
0x180089a97  mov     rcx, [r14]; psa
0x180089a9a  call    cs:__imp_SafeArrayGetUBound
0x180089aa0  test    eax, eax
0x180089aa2  js      loc_180089B7C
0x180089aa8  cmp     esi, [rbp+plUbound]
0x180089aab  jg      loc_180089B84
0x180089ab1  mov     eax, esi
0x180089ab3  sub     eax, [rbp+plLbound]
0x180089ab6  movsxd  rdx, eax
0x180089ab9  mov     rax, [r14]
0x180089abc  mov     rcx, [rax+10h]
0x180089ac0  mov     eax, [rcx+rdx*4]
0x180089ac3  mov     ecx, 13h
0x180089ac8  mov     word ptr [rbp+pvargSrc], cx
0x180089acc  mov     dword ptr [rbp+pvargSrc+8], eax
0x180089acf  mov     rdi, [rbx+8]
0x180089ad3  cmp     rdi, [rbx+10h]
0x180089ad7  jz      short loc_180089AF6
0x180089ad9  xor     eax, eax
0x180089adb  mov     [rdi], ax
0x180089ade  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180089ae2  mov     rcx, rdi; pvargDest
0x180089ae5  call    cs:__imp_VariantCopy
0x180089aeb  test    eax, eax
0x180089aed  js      short loc_180089B6C
0x180089aef  add     qword ptr [rbx+8], 18h
0x180089af4  jmp     short loc_180089B06
0x180089af6  lea     r8, [rbp+pvargSrc]
0x180089afa  mov     rdx, rdi
0x180089afd  mov     rcx, rbx
0x180089b00  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180089b05  nop
0x180089b06  lea     rcx, [rbp+pvargSrc]; pvarg
0x180089b0a  call    cs:__imp_VariantClear
0x180089b10  add     esi, r12d
0x180089b13  mov     [rbp+plLbound], 0
0x180089b1a  mov     [rbp+plUbound], 0
0x180089b21  lea     r8, [rbp+plLbound]; plLbound
0x180089b25  mov     edx, r12d; nDim
0x180089b28  mov     rcx, [r14]; psa
0x180089b2b  call    cs:__imp_SafeArrayGetLBound
0x180089b31  test    eax, eax
0x180089b33  js      short loc_180089B5C
0x180089b35  jmp     loc_180089A2F
0x180089b3a  mov     rax, rbx
0x180089b3d  mov     rbx, [rsp+40h+arg_18]
0x180089b45  add     rsp, 40h
0x180089b49  pop     r14
0x180089b4b  pop     r12
0x180089b4d  pop     rdi
0x180089b4e  pop     rsi
0x180089b4f  pop     rbp
0x180089b50  retn
0x180089b51  mov     ecx, 80004005h; int
0x180089b56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b5c  mov     ecx, eax; int
0x180089b5e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b64  mov     ecx, eax; int
0x180089b66  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b6c  mov     word ptr [rdi], 0Ah
0x180089b71  mov     [rdi+8], eax
0x180089b74  mov     ecx, eax; int
0x180089b76  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b7c  mov     ecx, eax; int
0x180089b7e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b84  mov     ecx, 80070057h; int
0x180089b89  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180089b8f  mov     ecx, eax; int
0x180089b91  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
