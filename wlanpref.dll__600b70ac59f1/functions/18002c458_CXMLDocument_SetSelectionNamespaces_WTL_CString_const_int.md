# CXMLDocument::SetSelectionNamespaces(WTL::CString const &,int)

- ea: `0x18002c458`
- end: `0x18002c551`
- name: `?SetSelectionNamespaces@CXMLDocument@@QEAAJAEBVCString@WTL@@H@Z`
- size: `249`
- prototype: `__int64 __fastcall(CXMLDocument *__hidden this, const struct WTL::CString *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x1800036ac`
- `0x1800054a0`
- `0x18000cdcc`
- `0x18000d360`
- `0x18002c458`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002c4c7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c4c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c539`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c539`
- `OLEAUT32!__imp_VariantInit` at `0x18002c485`
- `OLEAUT32!__imp_VariantInit` at `0x18002c485`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a7`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4b5`
- `OLEAUT32!__imp_VariantClear` at `0x18002c52e`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a7`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4b5`
- `OLEAUT32!__imp_VariantClear` at `0x18002c52e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXMLDocument::SetSelectionNamespaces(CXMLDocument *this, const struct WTL::CString *a2)
{
  OLECHAR *v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  BSTR bstrString; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v10; // [rsp+40h] [rbp-20h] BYREF
  OLECHAR *psz; // [rsp+88h] [rbp+28h] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
  VariantInit(&pvarg);
  psz = (OLECHAR *)WTL::_atltmpPchNil;
  WTL::CString::operator+=(&psz, a2);
  VariantClear(&pvarg);
  v4 = psz;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v4);
  if ( !pvarg.llVal && v4 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v5 = *(_QWORD *)this;
  v10 = pvarg;
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v5 + 640LL))(v5, bstrString, &v10);
  WTL::CString::~CString((WTL::CString *)&psz);
  VariantClear(&pvarg);
  SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x18002c458  mov     [rsp-8+arg_0], rbx
0x18002c45d  mov     [rsp-8+arg_8], rdi
0x18002c462  push    rbp
0x18002c463  mov     rbp, rsp
0x18002c466  sub     rsp, 60h
0x18002c46a  mov     rbx, rdx
0x18002c46d  mov     rdi, rcx
0x18002c470  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002c477  lea     rcx, [rbp+bstrString]; this
0x18002c47b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c480  nop
0x18002c481  lea     rcx, [rbp+pvarg]; pvarg
0x18002c485  call    cs:__imp_VariantInit
0x18002c48b  nop
0x18002c48c  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18002c493  mov     [rbp+psz], rax
0x18002c497  mov     rdx, rbx
0x18002c49a  lea     rcx, [rbp+psz]
0x18002c49e  call    ??YCString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator+=(WTL::CString const &)
0x18002c4a3  lea     rcx, [rbp+pvarg]; pvarg
0x18002c4a7  call    cs:__imp_VariantClear
0x18002c4ad  mov     rbx, [rbp+psz]
0x18002c4b1  lea     rcx, [rbp+pvarg]; pvarg
0x18002c4b5  call    cs:__imp_VariantClear
0x18002c4bb  mov     eax, 8
0x18002c4c0  mov     word ptr [rbp+pvarg], ax
0x18002c4c4  mov     rcx, rbx; psz
0x18002c4c7  call    cs:__imp_SysAllocString
0x18002c4cd  mov     qword ptr [rbp+pvarg+8], rax
0x18002c4d1  test    rax, rax
0x18002c4d4  jnz     short loc_18002C4F2
0x18002c4d6  test    rbx, rbx
0x18002c4d9  jz      short loc_18002C4F2
0x18002c4db  mov     eax, 0Ah
0x18002c4e0  mov     word ptr [rbp+pvarg], ax
0x18002c4e4  mov     ecx, 8007000Eh; int
0x18002c4e9  mov     dword ptr [rbp+pvarg+8], ecx
0x18002c4ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c4f2  mov     rcx, [rdi]
0x18002c4f5  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002c4f9  movaps  [rbp+var_20], xmm0
0x18002c4fd  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002c502  movsd   [rbp+var_10], xmm1
0x18002c507  mov     rax, [rcx]
0x18002c50a  lea     r8, [rbp+var_20]
0x18002c50e  mov     rdx, [rbp+bstrString]
0x18002c512  mov     rax, [rax+280h]
0x18002c519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c51e  mov     ebx, eax
0x18002c520  lea     rcx, [rbp+psz]; this
0x18002c524  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c529  nop
0x18002c52a  lea     rcx, [rbp+pvarg]; pvarg
0x18002c52e  call    cs:__imp_VariantClear
0x18002c534  nop
0x18002c535  mov     rcx, [rbp+bstrString]; bstrString
0x18002c539  call    cs:__imp_SysFreeString
0x18002c53f  mov     eax, ebx
0x18002c541  mov     rbx, [rsp+60h+arg_0]
0x18002c546  mov     rdi, [rsp+60h+arg_8]
0x18002c54b  add     rsp, 60h
0x18002c54f  pop     rbp
0x18002c550  retn
```
