# CXMLPropStore::_CreateNode(IXMLDOMNode *,ushort *,IXMLDOMNode * *)

- ea: `0x1800306d4`
- end: `0x1800308e3`
- name: `?_CreateNode@CXMLPropStore@@IEAAJPEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z`
- size: `527`
- prototype: `__int64 __fastcall(CXMLPropStore *__hidden this, struct IXMLDOMNode *, unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800308ec`

## callees

- `0x180012550`
- `0x18002d55c`
- `0x18002d5c8`
- `0x18002d858`
- `0x18002dc2c`
- `0x18002dc38`
- `0x180030434`
- `0x180030530`
- `0x1800306d4`
- `0x180031578`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180030722`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180030722`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030737`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180030737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800308c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800308c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180030831`
- `OLEAUT32!__imp_SysFreeString` at `0x180030831`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_CreateNode(
        CXMLPropStore *this,
        struct IXMLDOMNode *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNode **a4)
{
  bool v5; // zf
  const WCHAR *v9; // rax
  const WCHAR *v10; // rbx
  HRESULT Attribute; // edi
  OLECHAR *v12; // rbx
  struct IXMLDOMDocument **v13; // rax
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(struct IXMLDOMNode *, GUID *, struct IXMLDOMElement **); // rdx
  struct IXMLDOMAttribute **v16; // rax
  LPWSTR ppwsz; // [rsp+20h] [rbp-20h] BYREF
  struct IXMLDOMElement *v19; // [rsp+28h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF

  *a4 = 0;
  v5 = *a3 == 64;
  ppwsz = 0;
  if ( v5 )
  {
    ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v19);
    Attribute = (**v15)(a2, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v19);
    if ( Attribute >= 0 )
    {
      ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&bstrString);
      v16 = (struct IXMLDOMAttribute **)ATL::CComPtrBase<IXMLDOMNode>::operator&(&bstrString);
      Attribute = CXMLPropStore::_CreateAttribute(this, v19, a3 + 1, v16);
      if ( Attribute >= 0 )
        Attribute = (**(__int64 (__fastcall ***)(BSTR, GUID *, struct IXMLDOMNode **))bstrString)(
                      bstrString,
                      &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                      a4);
      ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&bstrString);
    }
    ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v19);
    goto LABEL_21;
  }
  v9 = StrChrW(a3, 0x5Bu);
  v10 = v9;
  if ( !v9 )
  {
LABEL_5:
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
    v12 = bstrString;
    if ( bstrString )
    {
      ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&bstrString);
      v13 = (struct IXMLDOMDocument **)ATL::CComPtrBase<IXMLDOMNode>::operator&(&bstrString);
      Attribute = CXMLPropStore::_GetDocument(this, v13);
      if ( Attribute >= 0 )
      {
        ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v19);
        v14 = ATL::CComPtrBase<IXMLDOMNodeList>::operator->(&bstrString);
        Attribute = (*(__int64 (__fastcall **)(__int64, OLECHAR *, struct IXMLDOMElement **))(*(_QWORD *)v14 + 376LL))(
                      v14,
                      v12,
                      &v19);
        if ( Attribute >= 0 )
        {
          if ( !ppwsz || (Attribute = CXMLPropStore::_CreateAttributes(this, v19, ppwsz), Attribute >= 0) )
          {
            Attribute = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMElement *, _QWORD))a2->lpVtbl->appendChild)(
                          a2,
                          v19,
                          0);
            if ( Attribute >= 0 )
              Attribute = ((__int64 (__fastcall *)(struct IXMLDOMElement *, GUID *, struct IXMLDOMNode **))v19->lpVtbl->QueryInterface)(
                            v19,
                            &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                            a4);
          }
        }
        ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v19);
      }
      ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&bstrString);
    }
    else
    {
      Attribute = -2147024882;
    }
    SysFreeString(v12);
LABEL_21:
    CoTaskMemFree(ppwsz);
    return (unsigned int)Attribute;
  }
  Attribute = SHStrDupW(v9, &ppwsz);
  if ( Attribute >= 0 )
  {
    *v10 = 0;
    goto LABEL_5;
  }
  return (unsigned int)Attribute;
}

```

## disassembly

```asm
0x1800306d4  push    rbp
0x1800306d6  push    rbx
0x1800306d7  push    rsi
0x1800306d8  push    rdi
0x1800306d9  push    r12
0x1800306db  push    r14
0x1800306dd  push    r15
0x1800306df  mov     rbp, rsp
0x1800306e2  sub     rsp, 40h
0x1800306e6  mov     rax, cs:__security_cookie
0x1800306ed  xor     rax, rsp
0x1800306f0  mov     [rbp+var_8], rax
0x1800306f4  mov     qword ptr [r9], 0
0x1800306fb  mov     r12, r9
0x1800306fe  cmp     word ptr [r8], 40h ; '@'
0x180030703  mov     rsi, r8
0x180030706  mov     r14, rdx
0x180030709  mov     [rbp+ppwsz], 0
0x180030711  mov     r15, rcx
0x180030714  jz      loc_18003083C
0x18003071a  mov     edx, 5Bh ; '['; wMatch
0x18003071f  mov     rcx, r8; pszStart
0x180030722  call    cs:__imp_StrChrW
0x180030728  mov     rbx, rax
0x18003072b  test    rax, rax
0x18003072e  jz      short loc_18003074C
0x180030730  lea     rdx, [rbp+ppwsz]; ppwsz
0x180030734  mov     rcx, rax; psz
0x180030737  call    cs:__imp_SHStrDupW
0x18003073d  mov     edi, eax
0x18003073f  test    eax, eax
0x180030741  js      loc_1800308C6
0x180030747  xor     ecx, ecx
0x180030749  mov     [rbx], cx
0x18003074c  mov     rdx, rsi; unsigned __int16 *
0x18003074f  lea     rcx, [rbp+bstrString]; this
0x180030753  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180030758  mov     rbx, [rbp+bstrString]
0x18003075c  test    rbx, rbx
0x18003075f  jz      loc_180030829
0x180030765  lea     rcx, [rbp+bstrString]
0x180030769  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x18003076e  lea     rcx, [rbp+bstrString]
0x180030772  call    ??I?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAPEAPEAUIXMLDOMNode@@XZ; ATL::CComPtrBase<IXMLDOMNode>::operator&(void)
0x180030777  mov     rdx, rax; struct IXMLDOMDocument **
0x18003077a  mov     rcx, r15; this
0x18003077d  call    ?_GetDocument@CXMLPropStore@@IEAAJPEAPEAUIXMLDOMDocument@@@Z; CXMLPropStore::_GetDocument(IXMLDOMDocument * *)
0x180030782  mov     edi, eax
0x180030784  test    eax, eax
0x180030786  js      loc_18003081E
0x18003078c  lea     rcx, [rbp+var_18]
0x180030790  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180030795  lea     rcx, [rbp+bstrString]
0x180030799  call    ??C?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIXMLDOMNodeList@@@1@XZ; ATL::CComPtrBase<IXMLDOMNodeList>::operator->(void)
0x18003079e  mov     r9, rax
0x1800307a1  lea     r8, [rbp+var_18]
0x1800307a5  mov     rdx, rbx
0x1800307a8  mov     rcx, [rax]
0x1800307ab  mov     rax, [rcx+178h]
0x1800307b2  mov     rcx, r9
0x1800307b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307ba  mov     edi, eax
0x1800307bc  test    eax, eax
0x1800307be  js      short loc_180030815
0x1800307c0  mov     r8, [rbp+ppwsz]; pszStart
0x1800307c4  test    r8, r8
0x1800307c7  jz      short loc_1800307DB
0x1800307c9  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x1800307cd  mov     rcx, r15; this
0x1800307d0  call    ?_CreateAttributes@CXMLPropStore@@IEAAJPEAUIXMLDOMElement@@PEAG@Z; CXMLPropStore::_CreateAttributes(IXMLDOMElement *,ushort *)
0x1800307d5  mov     edi, eax
0x1800307d7  test    eax, eax
0x1800307d9  js      short loc_180030815
0x1800307db  mov     rax, [r14]
0x1800307de  xor     r8d, r8d
0x1800307e1  mov     rdx, [rbp+var_18]
0x1800307e5  mov     rcx, r14
0x1800307e8  mov     rax, [rax+0A8h]
0x1800307ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307f4  mov     edi, eax
0x1800307f6  test    eax, eax
0x1800307f8  js      short loc_180030815
0x1800307fa  mov     rcx, [rbp+var_18]
0x1800307fe  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180030805  mov     r8, r12
0x180030808  mov     rax, [rcx]
0x18003080b  mov     rax, [rax]
0x18003080e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030813  mov     edi, eax
0x180030815  lea     rcx, [rbp+var_18]
0x180030819  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x18003081e  lea     rcx, [rbp+bstrString]
0x180030822  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180030827  jmp     short loc_18003082E
0x180030829  mov     edi, 8007000Eh
0x18003082e  mov     rcx, rbx; bstrString
0x180030831  call    cs:__imp_SysFreeString
0x180030837  jmp     loc_1800308BC
0x18003083c  lea     rcx, [rbp+var_18]
0x180030840  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180030845  mov     rcx, [rdx]
0x180030848  lea     r8, [rbp+var_18]
0x18003084c  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180030853  mov     rax, [rcx]
0x180030856  mov     rcx, r14
0x180030859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003085e  mov     edi, eax
0x180030860  test    eax, eax
0x180030862  js      short loc_1800308B3
0x180030864  lea     rcx, [rbp+bstrString]
0x180030868  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x18003086d  lea     rcx, [rbp+bstrString]
0x180030871  call    ??I?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAPEAPEAUIXMLDOMNode@@XZ; ATL::CComPtrBase<IXMLDOMNode>::operator&(void)
0x180030876  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18003087a  lea     r8, [rsi+2]; unsigned __int16 *
0x18003087e  mov     r9, rax; struct IXMLDOMAttribute **
0x180030881  mov     rcx, r15; this
0x180030884  call    ?_CreateAttribute@CXMLPropStore@@IEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUIXMLDOMAttribute@@@Z; CXMLPropStore::_CreateAttribute(IXMLDOMElement *,ushort const *,IXMLDOMAttribute * *)
0x180030889  mov     edi, eax
0x18003088b  test    eax, eax
0x18003088d  js      short loc_1800308AA
0x18003088f  mov     rcx, [rbp+bstrString]
0x180030893  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18003089a  mov     r8, r12
0x18003089d  mov     rax, [rcx]
0x1800308a0  mov     rax, [rax]
0x1800308a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308a8  mov     edi, eax
0x1800308aa  lea     rcx, [rbp+bstrString]
0x1800308ae  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x1800308b3  lea     rcx, [rbp+var_18]
0x1800308b7  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x1800308bc  mov     rcx, [rbp+ppwsz]; pv
0x1800308c0  call    cs:__imp_CoTaskMemFree
0x1800308c6  mov     eax, edi
0x1800308c8  mov     rcx, [rbp+var_8]
0x1800308cc  xor     rcx, rsp; StackCookie
0x1800308cf  call    __security_check_cookie
0x1800308d4  add     rsp, 40h
0x1800308d8  pop     r15
0x1800308da  pop     r14
0x1800308dc  pop     r12
0x1800308de  pop     rdi
0x1800308df  pop     rsi
0x1800308e0  pop     rbx
0x1800308e1  pop     rbp
0x1800308e2  retn
```
