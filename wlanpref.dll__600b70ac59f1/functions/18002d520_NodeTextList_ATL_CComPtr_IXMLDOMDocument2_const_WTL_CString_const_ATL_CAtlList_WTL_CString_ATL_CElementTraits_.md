# NodeTextList(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &,ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>> &)

- ea: `0x18002d520`
- end: `0x18002d69a`
- name: `?NodeTextList@@YAXAEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBVCString@WTL@@AEAV?$CAtlList@VCString@WTL@@V?$CElementTraits@VCString@WTL@@@ATL@@@2@@Z`
- size: `378`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x180003458`
- `0x1800036ac`
- `0x18000cdcc`
- `0x18000cf1c`
- `0x18002d348`
- `0x18002d520`
- `0x18002d6dc`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d56c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d64b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d56c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d64b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NodeTextList(__int64 *a1, const unsigned __int16 **a2, __int64 *a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v6; // rax
  unsigned int i; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 *v10; // rcx
  BSTR Source; // [rsp+20h] [rbp-10h] BYREF
  __int64 v13; // [rsp+28h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+20h] BYREF
  int v15; // [rsp+58h] [rbp+28h] BYREF
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF

  v16 = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 288LL);
  v6 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *a2);
  LODWORD(v5) = v5(v4, *(_QWORD *)v6, &v16);
  SysFreeString(bstrString);
  if ( (_DWORD)v5 )
    throw (XmlUtilException *)&bstrString;
  v15 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 64LL))(v16, &v15) )
    throw (XmlUtilException *)&bstrString;
  for ( i = 0; (int)i < v15; ++i )
  {
    v13 = 0;
    Source = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 56LL))(v16, i, &v13) )
      throw (XmlUtilException *)&bstrString;
    if ( (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 208LL))(v13, &Source) )
      throw (XmlUtilException *)&bstrString;
    v8 = WTL::CString::CString((WTL::CString *)&bstrString, Source);
    v9 = ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::NewNode(a3, v8, a3[1]);
    v10 = (__int64 *)a3[1];
    if ( v10 )
      *v10 = v9;
    else
      *a3 = v9;
    a3[1] = v9;
    WTL::CString::~CString((WTL::CString *)&bstrString);
    SysFreeString(Source);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  }
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
}

```

## disassembly

```asm
0x18002d520  mov     [rsp-18h+arg_10], rbx
0x18002d525  push    rbp
0x18002d526  push    rsi
0x18002d527  push    rdi
0x18002d528  mov     rbp, rsp
0x18002d52b  sub     rsp, 30h
0x18002d52f  mov     rsi, r8
0x18002d532  mov     [rbp+arg_18], 0
0x18002d53a  mov     rdi, [rcx]
0x18002d53d  mov     rax, [rdi]
0x18002d540  mov     rbx, [rax+120h]
0x18002d547  mov     rdx, [rdx]; unsigned __int16 *
0x18002d54a  lea     rcx, [rbp+bstrString]; this
0x18002d54e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002d553  nop
0x18002d554  lea     r8, [rbp+arg_18]
0x18002d558  mov     rdx, [rax]
0x18002d55b  mov     rcx, rdi
0x18002d55e  mov     rax, rbx
0x18002d561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d566  mov     ebx, eax
0x18002d568  mov     rcx, [rbp+bstrString]; bstrString
0x18002d56c  call    cs:__imp_SysFreeString
0x18002d572  test    ebx, ebx
0x18002d574  jz      short loc_18002D587
0x18002d576  lea     rdx, _TI1?AVXmlUtilException@@; pThrowInfo
0x18002d57d  lea     rcx, [rbp+bstrString]; pExceptionObject
0x18002d581  call    _CxxThrowException_0
0x18002d587  mov     [rbp+arg_8], 0
0x18002d58e  mov     rcx, [rbp+arg_18]
0x18002d592  mov     rax, [rcx]
0x18002d595  lea     rdx, [rbp+arg_8]
0x18002d599  mov     rax, [rax+40h]
0x18002d59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5a2  test    eax, eax
0x18002d5a4  jz      short loc_18002D5B7
0x18002d5a6  lea     rdx, _TI1?AVXmlUtilException@@; pThrowInfo
0x18002d5ad  lea     rcx, [rbp+bstrString]; pExceptionObject
0x18002d5b1  call    _CxxThrowException_0
0x18002d5b7  xor     ebx, ebx
0x18002d5b9  cmp     ebx, [rbp+arg_8]
0x18002d5bc  jge     loc_18002D684
0x18002d5c2  mov     [rbp+var_8], 0
0x18002d5ca  mov     [rbp+Source], 0
0x18002d5d2  mov     rcx, [rbp+arg_18]
0x18002d5d6  mov     rax, [rcx]
0x18002d5d9  lea     r8, [rbp+var_8]
0x18002d5dd  mov     edx, ebx
0x18002d5df  mov     rax, [rax+38h]
0x18002d5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5e8  test    eax, eax
0x18002d5ea  jnz     loc_18002D673
0x18002d5f0  mov     rcx, [rbp+var_8]
0x18002d5f4  mov     rax, [rcx]
0x18002d5f7  lea     rdx, [rbp+Source]
0x18002d5fb  mov     rax, [rax+0D0h]
0x18002d602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d607  test    eax, eax
0x18002d609  jnz     short loc_18002D662
0x18002d60b  mov     rdx, [rbp+Source]; Source
0x18002d60f  lea     rcx, [rbp+bstrString]; this
0x18002d613  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002d618  nop
0x18002d619  mov     r8, [rsi+8]
0x18002d61d  mov     rdx, rax
0x18002d620  mov     rcx, rsi
0x18002d623  call    ?NewNode@?$CAtlList@VCString@WTL@@V?$CElementTraits@VCString@WTL@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBVCString@WTL@@PEAV312@1@Z; ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::NewNode(WTL::CString const &,ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::CNode *,ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::CNode *)
0x18002d628  mov     rcx, [rsi+8]
0x18002d62c  test    rcx, rcx
0x18002d62f  jz      short loc_18002D636
0x18002d631  mov     [rcx], rax
0x18002d634  jmp     short loc_18002D639
0x18002d636  mov     [rsi], rax
0x18002d639  mov     [rsi+8], rax
0x18002d63d  lea     rcx, [rbp+bstrString]; this
0x18002d641  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002d646  nop
0x18002d647  mov     rcx, [rbp+Source]; bstrString
0x18002d64b  call    cs:__imp_SysFreeString
0x18002d651  nop
0x18002d652  lea     rcx, [rbp+var_8]
0x18002d656  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d65b  inc     ebx
0x18002d65d  jmp     loc_18002D5B9
0x18002d662  lea     rdx, _TI1?AVXmlUtilException@@; pThrowInfo
0x18002d669  lea     rcx, [rbp+bstrString]; pExceptionObject
0x18002d66d  call    _CxxThrowException_0
0x18002d673  lea     rdx, _TI1?AVXmlUtilException@@; pThrowInfo
0x18002d67a  lea     rcx, [rbp+bstrString]; pExceptionObject
0x18002d67e  call    _CxxThrowException_0
0x18002d684  lea     rcx, [rbp+arg_18]
0x18002d688  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d68d  mov     rbx, [rsp+30h+arg_10]
0x18002d692  add     rsp, 30h
0x18002d696  pop     rdi
0x18002d697  pop     rsi
0x18002d698  pop     rbp
0x18002d699  retn
```
