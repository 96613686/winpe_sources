# _anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short___

- ea: `0x180089f30`
- end: `0x18008a157`
- name: `_anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short___`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008b420`

## callees

- `0x180058600`
- `0x180088d44`
- `0x180089f30`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008a02f`
- `OLEAUT32!__imp_VariantClear` at `0x18008a0ba`
- `OLEAUT32!__imp_VariantClear` at `0x18008a02f`
- `OLEAUT32!__imp_VariantClear` at `0x18008a0ba`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a08f`
- `OLEAUT32!__imp_VariantCopy` at `0x18008a08f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089f9e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089fff`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089f9e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180089fff`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089f86`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089fd7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a0d8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089f86`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180089fd7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008a0d8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18008a04b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18008a04b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18008a057`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18008a057`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::wmi_object_property_meta::array_values_unsigned_short___(
        __int64 a1,
        SAFEARRAY **a2)
{
  LONG v4; // esi
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  SAFEARRAY *v7; // rcx
  HRESULT v8; // eax
  HRESULT v9; // eax
  __int64 v10; // rdi
  _QWORD *pvData; // r15
  OLECHAR *v12; // rcx
  BSTR v13; // rax
  UINT v14; // eax
  VARIANTARG *v15; // rdi
  HRESULT v16; // eax
  VARIANTARG pvarg; // [rsp+28h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+48h] BYREF
  LONG plUbound; // [rsp+90h] [rbp+50h] BYREF

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v4 = 0;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(*a2, 1u, &plLbound);
  if ( LBound < 0 )
LABEL_22:
    ATL::AtlThrowImpl(LBound);
  while ( 1 )
  {
    UBound = SafeArrayGetUBound(*a2, 1u, &plUbound);
    if ( UBound < 0 )
      ATL::AtlThrowImpl(UBound);
    if ( v4 >= (unsigned int)(plUbound - plLbound + 1) )
      return a1;
    v7 = *a2;
    if ( !*a2 )
      ATL::AtlThrowImpl(-2147467259);
    plLbound = 0;
    v8 = SafeArrayGetLBound(v7, 1u, &plLbound);
    if ( v8 < 0 )
      ATL::AtlThrowImpl(v8);
    if ( v4 < plLbound )
      goto LABEL_26;
    plUbound = 0;
    v9 = SafeArrayGetUBound(*a2, 1u, &plUbound);
    if ( v9 < 0 )
      ATL::AtlThrowImpl(v9);
    if ( v4 > plUbound )
LABEL_26:
      ATL::AtlThrowImpl(-2147024809);
    v10 = v4 - plLbound;
    pvData = (*a2)->pvData;
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    v12 = (OLECHAR *)pvData[v10];
    if ( v12 )
    {
      v14 = SysStringByteLen(v12);
      v13 = SysAllocStringByteLen((LPCSTR)pvData[v10], v14);
    }
    else
    {
      v13 = 0;
    }
    pvarg.llVal = (LONGLONG)v13;
    if ( !v13 && pvData[v10] )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v15 = *(VARIANTARG **)(a1 + 8);
    if ( v15 == *(VARIANTARG **)(a1 + 16) )
    {
      std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        (const VARIANTARG **)a1,
        *(const VARIANTARG **)(a1 + 8),
        &pvarg);
    }
    else
    {
      v15->vt = 0;
      v16 = VariantCopy(v15, &pvarg);
      if ( v16 < 0 )
      {
        v15->vt = 10;
        v15->lVal = v16;
        ATL::AtlThrowImpl(v16);
      }
      *(_QWORD *)(a1 + 8) += 24LL;
    }
    VariantClear(&pvarg);
    plLbound = 0;
    plUbound = 0;
    LBound = SafeArrayGetLBound(*a2, 1u, &plLbound);
    if ( LBound < 0 )
      goto LABEL_22;
    ++v4;
  }
}

```

## disassembly

```asm
0x180089f30  mov     [rsp-38h+arg_0], rcx
0x180089f35  push    rbp
0x180089f36  push    rbx
0x180089f37  push    rsi
0x180089f38  push    rdi
0x180089f39  push    r13
0x180089f3b  push    r14
0x180089f3d  push    r15
0x180089f3f  mov     rbp, rsp
0x180089f42  sub     rsp, 40h
0x180089f46  mov     r14, rdx
0x180089f49  mov     rbx, rcx
0x180089f4c  mov     [rbp+var_20], 0
0x180089f53  mov     qword ptr [rcx], 0
0x180089f5a  mov     qword ptr [rcx+8], 0
0x180089f62  mov     qword ptr [rcx+10h], 0
0x180089f6a  mov     r13d, 1
0x180089f70  mov     [rbp+var_20], r13d
0x180089f74  xor     esi, esi
0x180089f76  mov     [rbp+plLbound], esi
0x180089f79  mov     [rbp+plUbound], esi
0x180089f7c  lea     r8, [rbp+plLbound]; plLbound
0x180089f80  mov     edx, r13d; nDim
0x180089f83  mov     rcx, [r14]; psa
0x180089f86  call    cs:__imp_SafeArrayGetLBound
0x180089f8c  test    eax, eax
0x180089f8e  js      loc_18008A104
0x180089f94  lea     r8, [rbp+plUbound]; plUbound
0x180089f98  mov     edx, r13d; nDim
0x180089f9b  mov     rcx, [r14]; psa
0x180089f9e  call    cs:__imp_SafeArrayGetUBound
0x180089fa4  test    eax, eax
0x180089fa6  js      loc_18008A0FC
0x180089fac  mov     eax, [rbp+plUbound]
0x180089faf  sub     eax, [rbp+plLbound]
0x180089fb2  add     eax, r13d
0x180089fb5  cmp     esi, eax
0x180089fb7  jnb     loc_18008A0EA
0x180089fbd  mov     rcx, [r14]; psa
0x180089fc0  test    rcx, rcx
0x180089fc3  jz      loc_18008A14C
0x180089fc9  mov     [rbp+plLbound], 0
0x180089fd0  lea     r8, [rbp+plLbound]; plLbound
0x180089fd4  mov     edx, r13d; nDim
0x180089fd7  call    cs:__imp_SafeArrayGetLBound
0x180089fdd  test    eax, eax
0x180089fdf  js      loc_18008A144
0x180089fe5  cmp     esi, [rbp+plLbound]
0x180089fe8  jl      loc_18008A139
0x180089fee  mov     [rbp+plUbound], 0
0x180089ff5  lea     r8, [rbp+plUbound]; plUbound
0x180089ff9  mov     edx, r13d; nDim
0x180089ffc  mov     rcx, [r14]; psa
0x180089fff  call    cs:__imp_SafeArrayGetUBound
0x18008a005  test    eax, eax
0x18008a007  js      loc_18008A131
0x18008a00d  cmp     esi, [rbp+plUbound]
0x18008a010  jg      loc_18008A139
0x18008a016  mov     eax, esi
0x18008a018  sub     eax, [rbp+plLbound]
0x18008a01b  movsxd  rdi, eax
0x18008a01e  mov     rax, [r14]
0x18008a021  mov     r15, [rax+10h]
0x18008a025  xor     eax, eax
0x18008a027  mov     word ptr [rbp+pvarg], ax
0x18008a02b  lea     rcx, [rbp+pvarg]; pvarg
0x18008a02f  call    cs:__imp_VariantClear
0x18008a035  mov     eax, 8
0x18008a03a  mov     word ptr [rbp+pvarg], ax
0x18008a03e  mov     rcx, [r15+rdi*8]; bstr
0x18008a042  test    rcx, rcx
0x18008a045  jnz     short loc_18008A04B
0x18008a047  xor     eax, eax
0x18008a049  jmp     short loc_18008A05D
0x18008a04b  call    cs:__imp_SysStringByteLen
0x18008a051  mov     edx, eax; len
0x18008a053  mov     rcx, [r15+rdi*8]; psz
0x18008a057  call    cs:__imp_SysAllocStringByteLen
0x18008a05d  mov     dword ptr [rbp+pvarg+8], eax
0x18008a060  mov     rcx, rax
0x18008a063  sar     rcx, 20h
0x18008a067  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18008a06a  test    rax, rax
0x18008a06d  jnz     short loc_18008A079
0x18008a06f  cmp     [r15+rdi*8], rax
0x18008a073  jnz     loc_18008A10C
0x18008a079  mov     rdi, [rbx+8]
0x18008a07d  cmp     rdi, [rbx+10h]
0x18008a081  jz      short loc_18008A0A6
0x18008a083  xor     eax, eax
0x18008a085  mov     [rdi], ax
0x18008a088  lea     rdx, [rbp+pvarg]; pvargSrc
0x18008a08c  mov     rcx, rdi; pvargDest
0x18008a08f  call    cs:__imp_VariantCopy
0x18008a095  mov     ecx, eax; int
0x18008a097  test    eax, eax
0x18008a099  js      loc_18008A123
0x18008a09f  add     qword ptr [rbx+8], 18h
0x18008a0a4  jmp     short loc_18008A0B6
0x18008a0a6  lea     r8, [rbp+pvarg]
0x18008a0aa  mov     rdx, rdi
0x18008a0ad  mov     rcx, rbx
0x18008a0b0  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18008a0b5  nop
0x18008a0b6  lea     rcx, [rbp+pvarg]; pvarg
0x18008a0ba  call    cs:__imp_VariantClear
0x18008a0c0  mov     [rbp+plLbound], 0
0x18008a0c7  mov     [rbp+plUbound], 0
0x18008a0ce  lea     r8, [rbp+plLbound]; plLbound
0x18008a0d2  mov     edx, r13d; nDim
0x18008a0d5  mov     rcx, [r14]; psa
0x18008a0d8  call    cs:__imp_SafeArrayGetLBound
0x18008a0de  test    eax, eax
0x18008a0e0  js      short loc_18008A104
0x18008a0e2  add     esi, r13d
0x18008a0e5  jmp     loc_180089F94
0x18008a0ea  mov     rax, rbx
0x18008a0ed  add     rsp, 40h
0x18008a0f1  pop     r15
0x18008a0f3  pop     r14
0x18008a0f5  pop     r13
0x18008a0f7  pop     rdi
0x18008a0f8  pop     rsi
0x18008a0f9  pop     rbx
0x18008a0fa  pop     rbp
0x18008a0fb  retn
0x18008a0fc  mov     ecx, eax; int
0x18008a0fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a104  mov     ecx, eax; int
0x18008a106  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a10c  mov     eax, 0Ah
0x18008a111  mov     word ptr [rbp+pvarg], ax
0x18008a115  mov     ecx, 8007000Eh; int
0x18008a11a  mov     dword ptr [rbp+pvarg+8], ecx
0x18008a11d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a123  mov     word ptr [rdi], 0Ah
0x18008a128  mov     [rdi+8], ecx
0x18008a12b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a131  mov     ecx, eax; int
0x18008a133  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a139  mov     ecx, 80070057h; int
0x18008a13e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a144  mov     ecx, eax; int
0x18008a146  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008a14c  mov     ecx, 80004005h; int
0x18008a151  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
