# CXMLPropStore::_LoadDOMFromStream(IStream *)

- ea: `0x1800322c0`
- end: `0x180032490`
- name: `?_LoadDOMFromStream@CXMLPropStore@@IEAAJPEAUIStream@@@Z`
- size: `464`
- prototype: `int(CXMLPropStore *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e6f0`
- `0x180032b44`

## callees

- `0x180012550`
- `0x18002d55c`
- `0x18002d604`
- `0x18002d858`
- `0x18002dc0c`
- `0x18002dc2c`
- `0x18002dc38`
- `0x18002dea0`
- `0x18002e0ac`
- `0x1800322c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032319`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032319`
- `OLEAUT32!__imp_SysFreeString` at `0x18003245b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003245b`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_LoadDOMFromStream(CXMLPropStore *this, struct IUnknown *a2)
{
  LPVOID *ppv; // rax
  const unsigned __int16 *v5; // rdx
  HRESULT Instance; // ebx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64 *, BSTR, VARIANTARG *); // rax
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // eax
  BSTR bstrString[2]; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-39h] BYREF
  __int16 v15; // [rsp+60h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v17[2]; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp+7h] BYREF
  VARIANTARG v19; // [rsp+A0h] [rbp+27h] BYREF

  ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v16);
  ppv = (LPVOID *)ATL::CComPtrBase<IXMLDOMNode>::operator&(&v16);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, ppv);
  if ( Instance >= 0 )
  {
    bstrString[0] = 0;
    Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)bstrString, v5, 11);
    if ( Instance < 0 )
    {
LABEL_13:
      SysFreeString(bstrString[0]);
      goto LABEL_14;
    }
    v19.vt = 2;
    v19.iVal = -1;
    v7 = *v16;
    pvarg.pRecInfo = v19.pRecInfo;
    v8 = *(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *))(v7 + 640);
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&v19.vt;
    Instance = v8(v16, bstrString[0], &pvarg);
    if ( Instance < 0 )
    {
LABEL_12:
      ATL::CComVariant::Clear(&v19);
      goto LABEL_13;
    }
    ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, a2);
    v15 = 0;
    v9 = *v16;
    v14 = pvarg;
    Instance = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int16 *))(v9 + 464))(v16, &v14, &v15);
    if ( Instance < 0 || (Instance = -2147467259, v15 != -1) )
    {
LABEL_11:
      ATL::CComVariant::Clear(&pvarg);
      goto LABEL_12;
    }
    ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(v17);
    v10 = ATL::CComPtrBase<IXMLDOMNodeList>::operator->(&v16);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 360LL))(v10, v17);
    if ( v11 >= 0 )
    {
      if ( !(unsigned __int8)ATL::CComPtrBase<IXMLDOMNodeList>::operator!=(v17) )
      {
LABEL_10:
        ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(v17);
        goto LABEL_11;
      }
      v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))v17[0])(
              v17[0],
              &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
              (char *)this + 56);
    }
    Instance = v11;
    goto LABEL_10;
  }
LABEL_14:
  ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v16);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800322c0  mov     [rsp-8+arg_10], rbx
0x1800322c5  mov     [rsp-8+arg_18], rsi
0x1800322ca  push    rbp
0x1800322cb  push    rdi
0x1800322cc  push    r14
0x1800322ce  lea     rbp, [rsp-47h]
0x1800322d3  sub     rsp, 0C0h
0x1800322da  mov     rax, cs:__security_cookie
0x1800322e1  xor     rax, rsp
0x1800322e4  mov     [rbp+57h+var_18], rax
0x1800322e8  mov     rdi, rcx
0x1800322eb  mov     rsi, rdx
0x1800322ee  lea     rcx, [rbp+57h+var_68]
0x1800322f2  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x1800322f7  lea     rcx, [rbp+57h+var_68]
0x1800322fb  call    ??I?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAPEAPEAUIXMLDOMNode@@XZ; ATL::CComPtrBase<IXMLDOMNode>::operator&(void)
0x180032300  xor     edx, edx; pUnkOuter
0x180032302  mov     [rsp+0D0h+ppv], rax; ppv
0x180032307  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18003230e  lea     rcx, CLSID_DOMDocument60; rclsid
0x180032315  lea     r8d, [rdx+1]; dwClsContext
0x180032319  call    cs:__imp_CoCreateInstance
0x18003231f  mov     ebx, eax
0x180032321  test    eax, eax
0x180032323  js      loc_180032461
0x180032329  mov     r8d, 0Bh; int
0x18003232f  mov     [rbp+57h+bstrString], 0
0x180032337  lea     rcx, [rbp+57h+bstrString]; this
0x18003233b  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180032340  mov     ebx, eax
0x180032342  test    eax, eax
0x180032344  js      loc_180032457
0x18003234a  mov     rcx, [rbp+57h+var_68]
0x18003234e  lea     r8, [rbp+57h+pvarg]
0x180032352  movsd   xmm1, qword ptr [rbp+57h+var_30+10h]
0x180032357  mov     eax, 2
0x18003235c  mov     rdx, [rbp+57h+bstrString]
0x180032360  or      r14d, 0FFFFFFFFh
0x180032364  mov     word ptr [rbp+57h+var_30], ax
0x180032368  mov     word ptr [rbp+57h+var_30+8], r14w
0x18003236d  mov     rax, [rcx]
0x180032370  movups  xmm0, xmmword ptr [rbp+57h+var_30]
0x180032374  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x180032379  mov     rax, [rax+280h]
0x180032380  movaps  xmmword ptr [rbp+57h+pvarg], xmm0
0x180032384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032389  mov     ebx, eax
0x18003238b  test    eax, eax
0x18003238d  js      loc_18003244E
0x180032393  mov     rdx, rsi; struct IUnknown *
0x180032396  lea     rcx, [rbp+57h+pvarg]; this
0x18003239a  call    ??0CComVariant@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComVariant::CComVariant(IUnknown *)
0x18003239f  mov     rcx, [rbp+57h+var_68]
0x1800323a3  lea     r8, [rbp+57h+var_70]
0x1800323a7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800323ab  lea     rdx, [rbp+57h+var_90]
0x1800323af  xor     eax, eax
0x1800323b1  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800323b6  mov     [rbp+57h+var_70], ax
0x1800323ba  mov     rax, [rcx]
0x1800323bd  movaps  [rbp+57h+var_90], xmm0
0x1800323c1  movsd   [rbp+57h+var_80], xmm1
0x1800323c6  mov     rax, [rax+1D0h]
0x1800323cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323d2  mov     ebx, eax
0x1800323d4  test    eax, eax
0x1800323d6  js      short loc_180032445
0x1800323d8  mov     ebx, 80004005h
0x1800323dd  cmp     [rbp+57h+var_70], r14w
0x1800323e2  jnz     short loc_180032445
0x1800323e4  lea     rcx, [rbp+57h+var_60]
0x1800323e8  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x1800323ed  lea     rcx, [rbp+57h+var_68]
0x1800323f1  call    ??C?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIXMLDOMNodeList@@@1@XZ; ATL::CComPtrBase<IXMLDOMNodeList>::operator->(void)
0x1800323f6  mov     r8, rax
0x1800323f9  lea     rdx, [rbp+57h+var_60]
0x1800323fd  mov     rcx, [rax]
0x180032400  mov     rax, [rcx+168h]
0x180032407  mov     rcx, r8
0x18003240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003240f  test    eax, eax
0x180032411  js      short loc_18003243A
0x180032413  lea     rcx, [rbp+57h+var_60]
0x180032417  call    ??9?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBA_NPEAUIXMLDOMNodeList@@@Z; ATL::CComPtrBase<IXMLDOMNodeList>::operator!=(IXMLDOMNodeList *)
0x18003241c  test    al, al
0x18003241e  jz      short loc_18003243C
0x180032420  mov     rcx, [rbp+57h+var_60]
0x180032424  lea     r8, [rdi+38h]
0x180032428  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18003242f  mov     rax, [rcx]
0x180032432  mov     rax, [rax]
0x180032435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003243a  mov     ebx, eax
0x18003243c  lea     rcx, [rbp+57h+var_60]
0x180032440  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180032445  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180032449  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18003244e  lea     rcx, [rbp+57h+var_30]; pvarg
0x180032452  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180032457  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18003245b  call    cs:__imp_SysFreeString
0x180032461  lea     rcx, [rbp+57h+var_68]
0x180032465  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x18003246a  mov     eax, ebx
0x18003246c  mov     rcx, [rbp+57h+var_18]
0x180032470  xor     rcx, rsp; StackCookie
0x180032473  call    __security_check_cookie
0x180032478  lea     r11, [rsp+0D0h+var_10]
0x180032480  mov     rbx, [r11+30h]
0x180032484  mov     rsi, [r11+38h]
0x180032488  mov     rsp, r11
0x18003248b  pop     r14
0x18003248d  pop     rdi
0x18003248e  pop     rbp
0x18003248f  retn
```
