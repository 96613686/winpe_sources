# NodeText(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &)

- ea: `0x18002d458`
- end: `0x18002d518`
- name: `?NodeText@@YA?AVCString@WTL@@AEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV12@@Z`
- size: `192`
- prototype: `__int64 __fastcall(WTL::CString *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x180003458`
- `0x18000cdcc`
- `0x18000cf1c`
- `0x18002d458`
- `0x18002d6dc`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WTL::CString *__fastcall NodeText(WTL::CString *this, _QWORD *a2, const unsigned __int16 **a3)
{
  BSTR v6; // [rsp+28h] [rbp-8h] BYREF
  char pExceptionObject; // [rsp+58h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF
  __int64 v9; // [rsp+68h] [rbp+38h] BYREF

  v9 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v6, *a3);
  bstrString = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, BSTR, __int64 *))(*(_QWORD *)*a2 + 296LL))(*a2, v6, &v9) )
    throw (XmlNodeNotFoundException *)&pExceptionObject;
  if ( (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 208LL))(v9, &bstrString) )
    throw (XmlUtilException *)&pExceptionObject;
  WTL::CString::CString(this, bstrString);
  SysFreeString(bstrString);
  SysFreeString(v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  return this;
}

```

## disassembly

```asm
0x18002d458  push    rbp
0x18002d45a  push    rbx
0x18002d45b  push    rdi
0x18002d45c  mov     rbp, rsp
0x18002d45f  sub     rsp, 30h
0x18002d463  mov     rbx, rdx
0x18002d466  mov     rdi, rcx
0x18002d469  mov     [rbp+arg_18], 0
0x18002d471  mov     rdx, [r8]; unsigned __int16 *
0x18002d474  lea     rcx, [rbp+var_8]; this
0x18002d478  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002d47d  nop
0x18002d47e  mov     [rbp+bstrString], 0
0x18002d486  mov     rcx, [rbx]
0x18002d489  mov     rax, [rcx]
0x18002d48c  lea     r8, [rbp+arg_18]
0x18002d490  mov     rdx, [rbp+var_8]
0x18002d494  mov     rax, [rax+128h]
0x18002d49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4a0  test    eax, eax
0x18002d4a2  jz      short loc_18002D4B5
0x18002d4a4  lea     rdx, _TI2?AVXmlNodeNotFoundException@@; pThrowInfo
0x18002d4ab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002d4af  call    _CxxThrowException_0
0x18002d4b5  mov     rcx, [rbp+arg_18]
0x18002d4b9  mov     rax, [rcx]
0x18002d4bc  lea     rdx, [rbp+bstrString]
0x18002d4c0  mov     rax, [rax+0D0h]
0x18002d4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4cc  test    eax, eax
0x18002d4ce  jz      short loc_18002D4E1
0x18002d4d0  lea     rdx, _TI1?AVXmlUtilException@@; pThrowInfo
0x18002d4d7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002d4db  call    _CxxThrowException_0
0x18002d4e1  mov     rdx, [rbp+bstrString]; Source
0x18002d4e5  mov     rcx, rdi; this
0x18002d4e8  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002d4ed  nop
0x18002d4ee  mov     rcx, [rbp+bstrString]; bstrString
0x18002d4f2  call    cs:__imp_SysFreeString
0x18002d4f8  nop
0x18002d4f9  mov     rcx, [rbp+var_8]; bstrString
0x18002d4fd  call    cs:__imp_SysFreeString
0x18002d503  nop
0x18002d504  lea     rcx, [rbp+arg_18]
0x18002d508  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d50d  mov     rax, rdi
0x18002d510  add     rsp, 30h
0x18002d514  pop     rdi
0x18002d515  pop     rbx
0x18002d516  pop     rbp
0x18002d517  retn
```
