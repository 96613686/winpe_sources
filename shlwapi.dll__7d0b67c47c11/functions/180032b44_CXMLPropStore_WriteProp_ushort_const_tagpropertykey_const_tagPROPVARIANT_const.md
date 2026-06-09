# CXMLPropStore::_WriteProp(ushort const *,_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x180032b44`
- end: `0x180032dcb`
- name: `?_WriteProp@CXMLPropStore@@IEAAJPEBGAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(CXMLPropStore *__hidden this, LPCWSTR psz, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f8f0`

## callees

- `0x18000dbdc`
- `0x180010160`
- `0x180012550`
- `0x180015590`
- `0x18002d55c`
- `0x18002d5c8`
- `0x18002d858`
- `0x18002dc1c`
- `0x18002dc2c`
- `0x18002dc38`
- `0x18002e664`
- `0x18002f2e4`
- `0x18002fd70`
- `0x180030bdc`
- `0x1800322c0`
- `0x180032670`
- `0x180032b44`
- `0x180037010`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x180032c34`
- `PROPSYS!PropVariantToStringAlloc` at `0x180032c34`
- `PROPSYS!PropVariantToBSTR` at `0x180032c6d`
- `PROPSYS!PropVariantToBSTR` at `0x180032c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c57`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d7d`
- `OLEAUT32!__imp_VariantClear` at `0x180032d6a`
- `OLEAUT32!__imp_VariantClear` at `0x180032d6a`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_WriteProp(
        CXMLPropStore *this,
        LPCWSTR psz,
        const struct _tagpropertykey *a3,
        const PROPVARIANT *a4)
{
  HRESULT DOMFromStream; // ebx
  struct IStream *v8; // rdx
  void **v9; // rax
  const struct _GUID *v10; // r8
  __int64 (__fastcall ***v11)(_QWORD, GUID *, PWSTR *); // rax
  VARTYPE v12; // cx
  PWSTR v13; // rdi
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 (__fastcall *v16)(PWSTR, _QWORD, __int128 *); // rbx
  _QWORD *v17; // rax
  BSTR bstrString; // [rsp+28h] [rbp-59h] BYREF
  __int64 v20; // [rsp+30h] [rbp-51h] BYREF
  __int128 v21; // [rsp+38h] [rbp-49h] BYREF
  IRecordInfo *v22; // [rsp+48h] [rbp-39h]
  BSTR pbstrOut; // [rsp+58h] [rbp-29h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-21h] BYREF
  struct IXMLDOMNode *v25; // [rsp+68h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-11h] BYREF

  v20 = 0;
  DOMFromStream = CXmlPropSimpleXPathParser::ParseSimpleXpath((CXmlPropSimpleXPathParser *)&v20, psz);
  if ( DOMFromStream >= 0 )
  {
    if ( !(unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator!((char *)this + 56) )
      goto LABEL_5;
    v8 = (struct IStream *)*((_QWORD *)this + 8);
    if ( v8 )
    {
      DOMFromStream = CXMLPropStore::_LoadDOMFromStream(this, v8);
      if ( DOMFromStream >= 0 )
      {
LABEL_5:
        if ( !(unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator!=((char *)this + 56, 0) )
        {
          DOMFromStream = -2147418113;
          goto LABEL_23;
        }
        ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v25);
        v9 = (void **)ATL::CComPtrBase<IXMLDOMNode>::operator&(&v25);
        if ( (int)CXMLPropStore::_NodeFromXPath(this, psz, v10, v9) < 0 )
        {
          DOMFromStream = CXMLPropStore::_CreateXPath(this, psz, &v25);
          if ( DOMFromStream < 0 )
            goto LABEL_21;
        }
        pbstrOut = 0;
        if ( (*(_WORD *)a4 & 0x3000) != 0 )
        {
          ppszOut = 0;
          DOMFromStream = PropVariantToStringAlloc(a4, &ppszOut);
          if ( DOMFromStream < 0 )
          {
LABEL_21:
            ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v25);
            goto LABEL_23;
          }
          DOMFromStream = SHSysAllocString(ppszOut, &pbstrOut);
          CoTaskMemFree(ppszOut);
        }
        else
        {
          DOMFromStream = PropVariantToBSTR(a4, &pbstrOut);
        }
        if ( DOMFromStream >= 0 )
        {
          DOMFromStream = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR))v25->lpVtbl->put_text)(v25, pbstrOut);
          if ( DOMFromStream >= 0 )
          {
            ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&ppszOut);
            v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, PWSTR *))ATL::CComPtrBase<IXMLDOMNodeList>::operator->(&v25);
            DOMFromStream = (**v11)(v11, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &ppszOut);
            if ( DOMFromStream >= 0 )
            {
              v12 = *(_WORD *)a4;
              bstrString = 0;
              DOMFromStream = VarTypeToString(v12 & 0xEFFF, (const unsigned __int16 **)&bstrString);
              if ( DOMFromStream >= 0 )
              {
                memset(&pvarg, 0, sizeof(pvarg));
                DOMFromStream = InitVariantFromString(bstrString, &pvarg);
                if ( DOMFromStream >= 0 )
                {
                  v13 = ppszOut;
                  v14 = *(_OWORD *)&pvarg.vt;
                  pRecInfo = pvarg.pRecInfo;
                  v16 = *(__int64 (__fastcall **)(PWSTR, _QWORD, __int128 *))(*(_QWORD *)ppszOut + 360LL);
                  v17 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Type");
                  v21 = v14;
                  v22 = pRecInfo;
                  DOMFromStream = v16(v13, *v17, &v21);
                  SysFreeString(bstrString);
                  VariantClear(&pvarg);
                }
              }
            }
            ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&ppszOut);
          }
          SysFreeString(pbstrOut);
        }
        goto LABEL_21;
      }
    }
    else
    {
      DOMFromStream = -2147467259;
    }
  }
LABEL_23:
  CXmlPropSimpleXPathParser::~CXmlPropSimpleXPathParser((CXmlPropSimpleXPathParser *)&v20);
  return (unsigned int)DOMFromStream;
}

```

## disassembly

```asm
0x180032b44  mov     rax, rsp
0x180032b47  mov     [rax+18h], rbx
0x180032b4b  push    rbp
0x180032b4c  push    rsi
0x180032b4d  push    rdi
0x180032b4e  push    r14
0x180032b50  push    r15
0x180032b52  lea     rbp, [rax-5Fh]
0x180032b56  sub     rsp, 0B0h
0x180032b5d  movaps  xmmword ptr [rax-38h], xmm6
0x180032b61  movaps  xmmword ptr [rax-48h], xmm7
0x180032b65  mov     rax, cs:__security_cookie
0x180032b6c  xor     rax, rsp
0x180032b6f  mov     [rbp+57h+var_50], rax
0x180032b73  mov     rdi, rcx
0x180032b76  mov     [rbp+57h+var_A8], 0
0x180032b7e  lea     rcx, [rbp+57h+var_A8]; this
0x180032b82  mov     rsi, r9
0x180032b85  mov     r15, rdx
0x180032b88  call    ?ParseSimpleXpath@CXmlPropSimpleXPathParser@@QEAAJPEBG@Z; CXmlPropSimpleXPathParser::ParseSimpleXpath(ushort const *)
0x180032b8d  mov     ebx, eax
0x180032b8f  test    eax, eax
0x180032b91  js      loc_180032D93
0x180032b97  lea     rcx, [rdi+38h]
0x180032b9b  call    ??7?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IXMLDOMNode>::operator!(void)
0x180032ba0  test    al, al
0x180032ba2  jz      short loc_180032BC3
0x180032ba4  mov     rdx, [rdi+40h]; struct IStream *
0x180032ba8  test    rdx, rdx
0x180032bab  jz      loc_180032C5F
0x180032bb1  mov     rcx, rdi; this
0x180032bb4  call    ?_LoadDOMFromStream@CXMLPropStore@@IEAAJPEAUIStream@@@Z; CXMLPropStore::_LoadDOMFromStream(IStream *)
0x180032bb9  mov     ebx, eax
0x180032bbb  test    eax, eax
0x180032bbd  js      loc_180032D93
0x180032bc3  xor     edx, edx
0x180032bc5  lea     rcx, [rdi+38h]
0x180032bc9  call    ??9?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEBA_NPEAUIXMLDOMNode@@@Z; ATL::CComPtrBase<IXMLDOMNode>::operator!=(IXMLDOMNode *)
0x180032bce  test    al, al
0x180032bd0  jz      loc_180032D8E
0x180032bd6  lea     rcx, [rbp+57h+var_70]
0x180032bda  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180032bdf  lea     rcx, [rbp+57h+var_70]
0x180032be3  call    ??I?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAPEAPEAUIXMLDOMNode@@XZ; ATL::CComPtrBase<IXMLDOMNode>::operator&(void)
0x180032be8  mov     r9, rax; void **
0x180032beb  mov     rdx, r15; unsigned __int16 *
0x180032bee  mov     rcx, rdi; this
0x180032bf1  call    ?_NodeFromXPath@CXMLPropStore@@IEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CXMLPropStore::_NodeFromXPath(ushort const *,_GUID const &,void * *)
0x180032bf6  test    eax, eax
0x180032bf8  jns     short loc_180032C13
0x180032bfa  lea     r8, [rbp+57h+var_70]; struct IXMLDOMNode **
0x180032bfe  mov     rdx, r15; psz
0x180032c01  mov     rcx, rdi; this
0x180032c04  call    ?_CreateXPath@CXMLPropStore@@IEAAJPEBGPEAPEAUIXMLDOMNode@@@Z; CXMLPropStore::_CreateXPath(ushort const *,IXMLDOMNode * *)
0x180032c09  mov     ebx, eax
0x180032c0b  test    eax, eax
0x180032c0d  js      loc_180032D83
0x180032c13  mov     eax, 3000h
0x180032c18  mov     [rbp+57h+pbstrOut], 0
0x180032c20  mov     rcx, rsi; propvar
0x180032c23  test    [rsi], ax
0x180032c26  jz      short loc_180032C69
0x180032c28  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x180032c2c  mov     [rbp+57h+ppszOut], 0
0x180032c34  call    cs:__imp_PropVariantToStringAlloc
0x180032c3a  mov     ebx, eax
0x180032c3c  test    eax, eax
0x180032c3e  js      loc_180032D83
0x180032c44  mov     rcx, [rbp+57h+ppszOut]; unsigned __int16 *
0x180032c48  lea     rdx, [rbp+57h+pbstrOut]; unsigned __int16 **
0x180032c4c  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180032c51  mov     rcx, [rbp+57h+ppszOut]; pv
0x180032c55  mov     ebx, eax
0x180032c57  call    cs:__imp_CoTaskMemFree
0x180032c5d  jmp     short loc_180032C75
0x180032c5f  mov     ebx, 80004005h
0x180032c64  jmp     loc_180032D93
0x180032c69  lea     rdx, [rbp+57h+pbstrOut]; pbstrOut
0x180032c6d  call    cs:__imp_PropVariantToBSTR
0x180032c73  mov     ebx, eax
0x180032c75  test    ebx, ebx
0x180032c77  js      loc_180032D83
0x180032c7d  mov     rcx, [rbp+57h+var_70]
0x180032c81  mov     rdx, [rbp+57h+pbstrOut]
0x180032c85  mov     rax, [rcx]
0x180032c88  mov     rax, [rax+0D8h]
0x180032c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c94  mov     ebx, eax
0x180032c96  test    eax, eax
0x180032c98  js      loc_180032D79
0x180032c9e  lea     rcx, [rbp+57h+ppszOut]
0x180032ca2  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180032ca7  lea     rcx, [rbp+57h+var_70]
0x180032cab  call    ??C?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIXMLDOMNodeList@@@1@XZ; ATL::CComPtrBase<IXMLDOMNodeList>::operator->(void)
0x180032cb0  mov     r9, rax
0x180032cb3  lea     r8, [rbp+57h+ppszOut]
0x180032cb7  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180032cbe  mov     rcx, [rax]
0x180032cc1  mov     rax, [rcx]
0x180032cc4  mov     rcx, r9
0x180032cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ccc  mov     ebx, eax
0x180032cce  test    eax, eax
0x180032cd0  js      loc_180032D70
0x180032cd6  movzx   ecx, word ptr [rsi]
0x180032cd9  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180032cdd  mov     eax, 0EFFFh
0x180032ce2  mov     [rbp+57h+bstrString], 0
0x180032cea  and     cx, ax; unsigned __int16
0x180032ced  call    ?VarTypeToString@@YAJGPEAPEBG@Z; VarTypeToString(ushort,ushort const * *)
0x180032cf2  mov     ebx, eax
0x180032cf4  test    eax, eax
0x180032cf6  js      short loc_180032D70
0x180032cf8  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180032cfc  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180032d00  xorps   xmm0, xmm0
0x180032d03  xor     eax, eax
0x180032d05  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180032d09  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180032d0d  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x180032d12  mov     ebx, eax
0x180032d14  test    eax, eax
0x180032d16  js      short loc_180032D70
0x180032d18  mov     rdi, [rbp+57h+ppszOut]
0x180032d1c  lea     rdx, aType; "Type"
0x180032d23  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180032d27  lea     rcx, [rbp+57h+bstrString]; this
0x180032d2b  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180032d30  mov     rax, [rdi]
0x180032d33  mov     rbx, [rax+168h]
0x180032d3a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180032d3f  lea     r8, [rbp+57h+var_A0]
0x180032d43  movaps  [rbp+57h+var_A0], xmm6
0x180032d47  mov     rcx, rdi
0x180032d4a  movsd   [rbp+57h+var_90], xmm7
0x180032d4f  mov     rdx, [rax]
0x180032d52  mov     rax, rbx
0x180032d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d5a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180032d5e  mov     ebx, eax
0x180032d60  call    cs:__imp_SysFreeString
0x180032d66  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180032d6a  call    cs:__imp_VariantClear
0x180032d70  lea     rcx, [rbp+57h+ppszOut]
0x180032d74  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180032d79  mov     rcx, [rbp+57h+pbstrOut]; bstrString
0x180032d7d  call    cs:__imp_SysFreeString
0x180032d83  lea     rcx, [rbp+57h+var_70]
0x180032d87  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180032d8c  jmp     short loc_180032D93
0x180032d8e  mov     ebx, 8000FFFFh
0x180032d93  lea     rcx, [rbp+57h+var_A8]; this
0x180032d97  call    ??1CXmlPropSimpleXPathParser@@QEAA@XZ; CXmlPropSimpleXPathParser::~CXmlPropSimpleXPathParser(void)
0x180032d9c  mov     eax, ebx
0x180032d9e  mov     rcx, [rbp+57h+var_50]
0x180032da2  xor     rcx, rsp; StackCookie
0x180032da5  call    __security_check_cookie
0x180032daa  lea     r11, [rsp+0D0h+var_20]
0x180032db2  mov     rbx, [r11+40h]
0x180032db6  movaps  xmm6, xmmword ptr [r11-10h]
0x180032dbb  movaps  xmm7, xmmword ptr [r11-20h]
0x180032dc0  mov     rsp, r11
0x180032dc3  pop     r15
0x180032dc5  pop     r14
0x180032dc7  pop     rdi
0x180032dc8  pop     rsi
0x180032dc9  pop     rbp
0x180032dca  retn
```
