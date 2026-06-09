# UnBCL::XmlDocument::XmlDocument(void)

- ea: `0x180064d80`
- end: `0x180064f53`
- name: `??0XmlDocument@UnBCL@@QEAA@XZ`
- size: `467`
- prototype: `__int64 __fastcall(UnBCL::XmlDocument *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800475e0`
- `0x1800477d0`
- `0x180063eb0`
- `0x180064d80`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180064e37`
- `OLEAUT32!__imp_SysAllocString` at `0x180064e48`
- `OLEAUT32!__imp_SysAllocString` at `0x180064e37`
- `OLEAUT32!__imp_SysAllocString` at `0x180064e48`
- `OLEAUT32!__imp_SysFreeString` at `0x180064e8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180064e8f`
- `OLEAUT32!__imp_VariantInit` at `0x180064e21`
- `OLEAUT32!__imp_VariantInit` at `0x180064e21`
- `OLEAUT32!__imp_VariantClear` at `0x180064e81`
- `OLEAUT32!__imp_VariantClear` at `0x180064e81`
- `ole32!CoCreateInstance` at `0x180064e00`
- `ole32!CoCreateInstance` at `0x180064e00`

## string_xrefs

- `0x180064f2f`: `struct IXMLDOMDocument3 *__cdecl UnBCL::MSXmlModule::CreateDOMDocument(void)`
- `0x180064e30`: `XPath`
- `0x180064eec`: `__cdecl UnBCL::XmlDocument::XmlDocument(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
UnBCL::XmlDocument *__fastcall UnBCL::XmlDocument::XmlDocument(UnBCL::XmlDocument *this)
{
  HRESULT v2; // eax
  unsigned __int16 v3; // di
  OLECHAR *v4; // rdi
  unsigned int (__fastcall ***v5)(LPVOID, GUID *, char *); // rcx
  UnBCL::NotSupportedException *v7; // rax
  UnBCL::Win32Exception *v8; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF
  VARIANTARG v10; // [rsp+50h] [rbp-28h] BYREF
  LPVOID pExceptionObject; // [rsp+A8h] [rbp+30h] BYREF
  __int64 v12; // [rsp+B0h] [rbp+38h] BYREF
  UnBCL::Win32Exception *v13; // [rsp+B8h] [rbp+40h]

  *(_QWORD *)this = &UnBCL::Object::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = _InterlockedIncrement(&dword_1800FFC68);
  *(_QWORD *)this = &UnBCL::XmlNode::`vftable';
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &UnBCL::XmlDocument::`vftable';
  pExceptionObject = 0;
  v2 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, &pExceptionObject);
  v3 = v2;
  if ( v2 < 0 )
  {
    v8 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v13 = v8;
    if ( v8 )
      v8 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(v8, v3);
    v12 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v8,
            "struct IXMLDOMDocument3 *__cdecl UnBCL::MSXmlModule::CreateDOMDocument(void)");
    throw (UnBCL::Win32Exception **)&v12;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"XPath");
  v4 = SysAllocString(L"SelectionLanguage");
  v10 = pvarg;
  (*(void (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)pExceptionObject + 640LL))(
    pExceptionObject,
    v4,
    &v10);
  VariantClear(&pvarg);
  if ( v4 )
    SysFreeString(v4);
  v5 = (unsigned int (__fastcall ***)(LPVOID, GUID *, char *))pExceptionObject;
  *((_QWORD *)this + 3) = pExceptionObject;
  if ( v5 && (**v5)(v5, &IID_IXMLDOMNode, (char *)this + 16) )
  {
    v7 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
    v12 = (__int64)v7;
    if ( v7 )
      v7 = (UnBCL::NotSupportedException *)UnBCL::NotSupportedException::NotSupportedException(v7);
    pExceptionObject = (LPVOID)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                 v7,
                                 "__cdecl UnBCL::XmlDocument::XmlDocument(void)");
    throw (UnBCL::NotSupportedException **)&pExceptionObject;
  }
  *((_QWORD *)this + 4) = 0;
  return this;
}

```

## disassembly

```asm
0x180064d80  mov     [rsp-20h+arg_0], rcx
0x180064d85  push    rbp
0x180064d86  push    rbx
0x180064d87  push    rsi
0x180064d88  push    rdi
0x180064d89  mov     rbp, rsp
0x180064d8c  sub     rsp, 78h
0x180064d90  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFEh
0x180064d98  mov     rbx, rcx
0x180064d9b  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180064da2  mov     [rcx], rax
0x180064da5  mov     dword ptr [rcx+8], 0
0x180064dac  mov     r8d, 1; dwClsContext
0x180064db2  mov     eax, r8d
0x180064db5  lock xadd cs:dword_1800FFC68, eax
0x180064dbd  add     eax, r8d
0x180064dc0  mov     [rcx+0Ch], eax
0x180064dc3  lea     rax, ??_7XmlNode@UnBCL@@6B@; const UnBCL::XmlNode::`vftable'
0x180064dca  mov     [rcx], rax
0x180064dcd  mov     qword ptr [rcx+10h], 0
0x180064dd5  lea     rax, ??_7XmlDocument@UnBCL@@6B@; const UnBCL::XmlDocument::`vftable'
0x180064ddc  mov     [rcx], rax
0x180064ddf  mov     [rbp+pExceptionObject], 0
0x180064de7  lea     rax, [rbp+pExceptionObject]
0x180064deb  mov     [rsp+78h+ppv], rax; ppv
0x180064df0  lea     r9, IID_IXMLDOMDocument3; riid
0x180064df7  xor     edx, edx; pUnkOuter
0x180064df9  lea     rcx, CLSID_DOMDocument60; rclsid
0x180064e00  call    cs:__imp_CoCreateInstance
0x180064e06  mov     edi, eax
0x180064e08  test    eax, eax
0x180064e0a  js      loc_180064F10
0x180064e10  xorps   xmm0, xmm0
0x180064e13  xor     eax, eax
0x180064e15  movups  xmmword ptr [rbp+pvarg], xmm0
0x180064e19  mov     qword ptr [rbp+pvarg+10h], rax
0x180064e1d  lea     rcx, [rbp+pvarg]; pvarg
0x180064e21  call    cs:__imp_VariantInit
0x180064e27  mov     eax, 8
0x180064e2c  mov     word ptr [rbp+pvarg], ax
0x180064e30  lea     rcx, aXpath; "XPath"
0x180064e37  call    cs:__imp_SysAllocString
0x180064e3d  mov     qword ptr [rbp+pvarg+8], rax
0x180064e41  lea     rcx, aSelectionlangu; "SelectionLanguage"
0x180064e48  call    cs:__imp_SysAllocString
0x180064e4e  mov     rdi, rax
0x180064e51  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180064e55  movaps  [rbp+var_28], xmm0
0x180064e59  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180064e5e  movsd   [rbp+var_18], xmm1
0x180064e63  mov     rcx, [rbp+pExceptionObject]
0x180064e67  mov     rdx, [rcx]
0x180064e6a  mov     rax, [rdx+280h]
0x180064e71  lea     r8, [rbp+var_28]
0x180064e75  mov     rdx, rdi
0x180064e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e7d  lea     rcx, [rbp+pvarg]; pvarg
0x180064e81  call    cs:__imp_VariantClear
0x180064e87  test    rdi, rdi
0x180064e8a  jz      short loc_180064E95
0x180064e8c  mov     rcx, rdi; bstrString
0x180064e8f  call    cs:__imp_SysFreeString
0x180064e95  mov     rcx, [rbp+pExceptionObject]
0x180064e99  mov     [rbx+18h], rcx
0x180064e9d  test    rcx, rcx
0x180064ea0  jz      short loc_180064EBC
0x180064ea2  mov     rax, [rcx]
0x180064ea5  lea     r8, [rbx+10h]
0x180064ea9  lea     rdx, IID_IXMLDOMNode
0x180064eb0  mov     rax, [rax]
0x180064eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064eb8  test    eax, eax
0x180064eba  jnz     short loc_180064ED0
0x180064ebc  mov     qword ptr [rbx+20h], 0
0x180064ec4  mov     rax, rbx
0x180064ec7  add     rsp, 78h
0x180064ecb  pop     rdi
0x180064ecc  pop     rsi
0x180064ecd  pop     rbx
0x180064ece  pop     rbp
0x180064ecf  retn
0x180064ed0  mov     ecx, 38h ; '8'; unsigned __int64
0x180064ed5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180064eda  mov     [rbp+arg_10], rax
0x180064ede  test    rax, rax
0x180064ee1  jz      short loc_180064EEC
0x180064ee3  mov     rcx, rax; this
0x180064ee6  call    ??0NotSupportedException@UnBCL@@QEAA@XZ; UnBCL::NotSupportedException::NotSupportedException(void)
0x180064eeb  nop
0x180064eec  lea     rdx, aCdeclUnbclXmld_0; "__cdecl UnBCL::XmlDocument::XmlDocument"...
0x180064ef3  mov     rcx, rax
0x180064ef6  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180064efb  mov     [rbp+pExceptionObject], rax
0x180064eff  lea     rdx, _TI5PEAVNotSupportedException@UnBCL@@; pThrowInfo
0x180064f06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180064f0a  call    _CxxThrowException_0
0x180064f10  mov     ecx, 40h ; '@'; unsigned __int64
0x180064f15  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180064f1a  mov     [rbp+arg_18], rax
0x180064f1e  test    rax, rax
0x180064f21  jz      short loc_180064F2F
0x180064f23  movzx   edx, di; dwMessageId
0x180064f26  mov     rcx, rax; this
0x180064f29  call    ??0Win32Exception@UnBCL@@QEAA@K@Z; UnBCL::Win32Exception::Win32Exception(ulong)
0x180064f2e  nop
0x180064f2f  lea     rdx, aStructIxmldomd; "struct IXMLDOMDocument3 *__cdecl UnBCL:"...
0x180064f36  mov     rcx, rax
0x180064f39  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180064f3e  mov     [rbp+arg_10], rax
0x180064f42  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x180064f49  lea     rcx, [rbp+arg_10]; pExceptionObject
0x180064f4d  call    _CxxThrowException_0
```
