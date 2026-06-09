# CXMLPropStore::_ReadProp(ushort const *,ushort,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18000d980`
- end: `0x18000dbd4`
- name: `?_ReadProp@CXMLPropStore@@IEAAJPEBGGAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `596`
- prototype: `__int64 __usercall@<rax>(CXMLPropStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, const struct _tagpropertykey *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d5e0`
- `0x18002e570`

## callees

- `0x18000d580`
- `0x18000d980`
- `0x18000dbdc`
- `0x180012550`
- `0x18002d55c`
- `0x18002d5c8`
- `0x18002d858`
- `0x18002dbe0`
- `0x18002dc1c`
- `0x18002fcf4`
- `0x180031490`
- `0x180032670`
- `0x1800340e8`
- `0x180036148`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000da85`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000da85`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18000dae5`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18000dae5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000db81`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000db81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da71`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db05`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da71`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db05`
- `OLEAUT32!__imp_VariantClear` at `0x18000daa5`
- `OLEAUT32!__imp_VariantClear` at `0x18000daa5`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_ReadProp(
        CXMLPropStore *this,
        const unsigned __int16 *a2,
        VARTYPE a3,
        OLECHAR *a4,
        PROPVARIANT *ppropvar)
{
  HRESULT v8; // ebx
  const struct _GUID *v9; // r8
  unsigned __int16 **v10; // rax
  bool v11; // bl
  const WCHAR *bstrVal; // rbx
  int v13; // eax
  int v14; // eax
  OLECHAR *v15; // rcx
  HRESULT inited; // eax
  int *v17; // rcx
  int v18; // r12d
  int i; // edi
  char *Ptr; // rax
  char *v21; // rsi
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  HDSA hdsa; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG lpString; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 v26; // [rsp+58h] [rbp-28h] BYREF
  PCWSTR psz; // [rsp+60h] [rbp-20h] BYREF
  struct IXMLDOMNode *v28; // [rsp+68h] [rbp-18h] BYREF

  bstrString = a4;
  *(_OWORD *)ppropvar = 0;
  ppropvar[2] = 0;
  hdsa = 0;
  v8 = CXmlPropSimpleXPathParser::ParseSimpleXpath((CXmlPropSimpleXPathParser *)&hdsa, a2);
  if ( v8 >= 0 )
  {
    if ( (unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator!=((char *)this + 56, 0) )
    {
      v8 = 0;
      ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&v28);
      if ( (int)CXMLPropStore::_NodeFromXPath(this, a2, v9, (void **)&v28) < 0 )
      {
LABEL_18:
        ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&v28);
        goto LABEL_30;
      }
      if ( a3 == 1 )
      {
        a3 = 8;
        v26 = 8;
        memset(&lpString, 0, sizeof(lpString));
        v10 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Type");
        v11 = (int)CXMLPropStore::_GetAttributeFromNode((CXMLPropStore *)&lpString, v28, *v10, 8u, &lpString) >= 0;
        SysFreeString(bstrString);
        if ( v11 )
        {
          bstrVal = lpString.bstrVal;
          v13 = lstrlenW(lpString.bstrVal);
          if ( (int)VarTypeFromStringCch(bstrVal, v13, &v26) >= 0 )
            a3 = v26;
          VariantClear(&lpString);
        }
      }
      psz = 0;
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, PCWSTR *))v28->lpVtbl->get_text)(v28, &psz);
      v15 = (OLECHAR *)psz;
      v8 = v14;
      if ( v14 )
      {
        if ( v14 < 0 )
        {
LABEL_17:
          SysFreeString(v15);
          goto LABEL_18;
        }
      }
      else if ( *psz )
      {
        if ( (a3 & 0x1000) != 0 )
          inited = InitPropVariantFromStringAsVector(psz, ppropvar);
        else
          inited = InitPropVariantFromStringEx((unsigned __int16 *)psz, a3, (struct tagPROPVARIANT *)ppropvar);
        v15 = (OLECHAR *)psz;
        v8 = inited;
        goto LABEL_17;
      }
      v8 = 0;
      goto LABEL_17;
    }
    v17 = *(int **)(*((_QWORD *)this + 20) + 24LL);
    if ( v17 )
      v18 = *v17;
    else
      v18 = 0;
    v8 = 0;
    for ( i = 0; v8 >= 0 && i < v18; ++i )
    {
      Ptr = (char *)DPA_GetPtr(*(HDPA *)(*((_QWORD *)this + 20) + 24LL), i);
      v21 = Ptr;
      if ( Ptr )
      {
        v8 = 0;
        if ( (unsigned int)operator==(Ptr + 56, bstrString) && *((_WORD *)v21 + 40) )
        {
          v8 = PropVariantCopy(ppropvar, (const PROPVARIANT *)v21 + 10);
          if ( v8 >= 0 )
            v8 = *((_DWORD *)v21 + 26);
          break;
        }
      }
      else
      {
        v8 = -2147024809;
      }
    }
  }
LABEL_30:
  if ( hdsa )
    DSA_Destroy(hdsa);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d980  mov     [rsp-38h+arg_18], rbx
0x18000d985  push    rbp
0x18000d986  push    rsi
0x18000d987  push    rdi
0x18000d988  push    r12
0x18000d98a  push    r13
0x18000d98c  push    r14
0x18000d98e  push    r15
0x18000d990  mov     rbp, rsp
0x18000d993  sub     rsp, 80h
0x18000d99a  mov     rax, cs:__security_cookie
0x18000d9a1  xor     rax, rsp
0x18000d9a4  mov     [rbp+var_10], rax
0x18000d9a8  mov     r13, [rbp+ppropvar]
0x18000d9ac  xorps   xmm0, xmm0
0x18000d9af  mov     r15, rcx
0x18000d9b2  mov     [rbp+bstrString], r9
0x18000d9b6  xor     eax, eax
0x18000d9b8  lea     rcx, [rbp+hdsa]; this
0x18000d9bc  xor     r14d, r14d
0x18000d9bf  movzx   edi, r8w
0x18000d9c3  movups  xmmword ptr [r13+0], xmm0
0x18000d9c8  mov     [r13+10h], rax
0x18000d9cc  mov     rsi, rdx
0x18000d9cf  mov     [rbp+hdsa], r14
0x18000d9d3  call    ?ParseSimpleXpath@CXmlPropSimpleXPathParser@@QEAAJPEBG@Z; CXmlPropSimpleXPathParser::ParseSimpleXpath(ushort const *)
0x18000d9d8  mov     ebx, eax
0x18000d9da  test    eax, eax
0x18000d9dc  js      loc_18000DB90
0x18000d9e2  lea     rcx, [r15+38h]
0x18000d9e6  xor     edx, edx
0x18000d9e8  call    ??9?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEBA_NPEAUIXMLDOMNode@@@Z; ATL::CComPtrBase<IXMLDOMNode>::operator!=(IXMLDOMNode *)
0x18000d9ed  test    al, al
0x18000d9ef  jz      loc_18000DB16
0x18000d9f5  lea     rcx, [rbp+var_18]
0x18000d9f9  mov     ebx, r14d
0x18000d9fc  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x18000da01  lea     r9, [rbp+var_18]; void **
0x18000da05  mov     rdx, rsi; unsigned __int16 *
0x18000da08  mov     rcx, r15; this
0x18000da0b  call    ?_NodeFromXPath@CXMLPropStore@@IEAAJPEBGAEBU_GUID@@PEAPEAX@Z; CXMLPropStore::_NodeFromXPath(ushort const *,_GUID const &,void * *)
0x18000da10  test    eax, eax
0x18000da12  js      loc_18000DB0B
0x18000da18  mov     r14d, 1
0x18000da1e  cmp     r14w, di
0x18000da22  jnz     loc_18000DAAD
0x18000da28  xorps   xmm0, xmm0
0x18000da2b  lea     edi, [r14+7]
0x18000da2f  xor     eax, eax
0x18000da31  mov     [rbp+var_28], di
0x18000da35  lea     rdx, aType; "Type"
0x18000da3c  mov     [rbp+var_30], rax
0x18000da40  lea     rcx, [rbp+bstrString]; this
0x18000da44  movups  xmmword ptr [rbp+lpString], xmm0
0x18000da48  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000da4d  mov     rdx, [rbp+var_18]; struct IXMLDOMNode *
0x18000da51  lea     rcx, [rbp+lpString]; this
0x18000da55  mov     r9d, edi; unsigned __int16
0x18000da58  mov     [rsp+80h+pvargDest], rcx; pvargDest
0x18000da5d  mov     r8, [rax]; unsigned __int16 *
0x18000da60  call    ?_GetAttributeFromNode@CXMLPropStore@@IEAAJPEAUIXMLDOMNode@@PEAGGPEAUtagVARIANT@@@Z; CXMLPropStore::_GetAttributeFromNode(IXMLDOMNode *,ushort *,ushort,tagVARIANT *)
0x18000da65  mov     rcx, [rbp+bstrString]; bstrString
0x18000da69  mov     ebx, eax
0x18000da6b  shr     ebx, 1Fh
0x18000da6e  xor     bl, r14b
0x18000da71  call    cs:__imp_SysFreeString
0x18000da77  xor     r14d, r14d
0x18000da7a  test    bl, bl
0x18000da7c  jz      short loc_18000DAB0
0x18000da7e  mov     rbx, [rbp+lpString+8]
0x18000da82  mov     rcx, rbx; lpString
0x18000da85  call    cs:__imp_lstrlenW
0x18000da8b  lea     r8, [rbp+var_28]; unsigned __int16 *
0x18000da8f  mov     rcx, rbx; psz1
0x18000da92  mov     edx, eax; nChar
0x18000da94  call    ?VarTypeFromStringCch@@YAJPEBGHPEAG@Z; VarTypeFromStringCch(ushort const *,int,ushort *)
0x18000da99  test    eax, eax
0x18000da9b  js      short loc_18000DAA1
0x18000da9d  movzx   edi, [rbp+var_28]
0x18000daa1  lea     rcx, [rbp+lpString]; pvarg
0x18000daa5  call    cs:__imp_VariantClear
0x18000daab  jmp     short loc_18000DAB0
0x18000daad  xor     r14d, r14d
0x18000dab0  mov     rcx, [rbp+var_18]
0x18000dab4  lea     rdx, [rbp+psz]
0x18000dab8  mov     [rbp+psz], r14
0x18000dabc  mov     rax, [rcx]
0x18000dabf  mov     rax, [rax+0D0h]
0x18000dac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dacb  mov     rcx, [rbp+psz]; unsigned __int16 *
0x18000dacf  mov     ebx, eax
0x18000dad1  test    eax, eax
0x18000dad3  jnz     short loc_18000DB00
0x18000dad5  cmp     [rcx], r14w
0x18000dad9  jz      short loc_18000DB02
0x18000dadb  bt      di, 0Ch
0x18000dae0  jnb     short loc_18000DAED
0x18000dae2  mov     rdx, r13; ppropvar
0x18000dae5  call    cs:__imp_InitPropVariantFromStringAsVector
0x18000daeb  jmp     short loc_18000DAF8
0x18000daed  mov     r8, r13
0x18000daf0  movzx   edx, di
0x18000daf3  call    InitPropVariantFromStringEx
0x18000daf8  mov     rcx, [rbp+psz]
0x18000dafc  mov     ebx, eax
0x18000dafe  jmp     short loc_18000DB05
0x18000db00  js      short loc_18000DB05
0x18000db02  mov     ebx, r14d
0x18000db05  call    cs:__imp_SysFreeString
0x18000db0b  lea     rcx, [rbp+var_18]
0x18000db0f  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x18000db14  jmp     short loc_18000DB90
0x18000db16  mov     rax, [r15+0A0h]
0x18000db1d  mov     rcx, [rax+18h]
0x18000db21  test    rcx, rcx
0x18000db24  jz      short loc_18000DB2B
0x18000db26  mov     r12d, [rcx]
0x18000db29  jmp     short loc_18000DB2E
0x18000db2b  mov     r12d, r14d
0x18000db2e  mov     ebx, r14d
0x18000db31  mov     edi, r14d
0x18000db34  mov     r14d, 1
0x18000db3a  test    ebx, ebx
0x18000db3c  js      short loc_18000DB90
0x18000db3e  cmp     edi, r12d
0x18000db41  jge     short loc_18000DB90
0x18000db43  mov     rcx, [r15+0A0h]
0x18000db4a  movsxd  rdx, edi; i
0x18000db4d  mov     rcx, [rcx+18h]; hdpa
0x18000db51  call    DPA_GetPtr
0x18000db56  xor     ecx, ecx
0x18000db58  mov     rsi, rax
0x18000db5b  test    rax, rax
0x18000db5e  jz      short loc_18000DBC7
0x18000db60  mov     rdx, [rbp+bstrString]
0x18000db64  mov     ebx, ecx
0x18000db66  lea     rcx, [rax+38h]
0x18000db6a  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db6f  xor     ecx, ecx
0x18000db71  test    eax, eax
0x18000db73  jz      short loc_18000DBCC
0x18000db75  lea     rdx, [rsi+50h]; pvarSrc
0x18000db79  cmp     [rdx], cx
0x18000db7c  jz      short loc_18000DBCC
0x18000db7e  mov     rcx, r13; pvarDest
0x18000db81  call    cs:__imp_PropVariantCopy
0x18000db87  mov     ebx, eax
0x18000db89  test    eax, eax
0x18000db8b  js      short loc_18000DB90
0x18000db8d  mov     ebx, [rsi+68h]
0x18000db90  mov     rcx, [rbp+hdsa]; hdsa
0x18000db94  test    rcx, rcx
0x18000db97  jz      short loc_18000DB9E
0x18000db99  call    DSA_Destroy
0x18000db9e  mov     eax, ebx
0x18000dba0  mov     rcx, [rbp+var_10]
0x18000dba4  xor     rcx, rsp; StackCookie
0x18000dba7  call    __security_check_cookie
0x18000dbac  mov     rbx, [rsp+80h+arg_18]
0x18000dbb4  add     rsp, 80h
0x18000dbbb  pop     r15
0x18000dbbd  pop     r14
0x18000dbbf  pop     r13
0x18000dbc1  pop     r12
0x18000dbc3  pop     rdi
0x18000dbc4  pop     rsi
0x18000dbc5  pop     rbp
0x18000dbc6  retn
0x18000dbc7  mov     ebx, 80070057h
0x18000dbcc  add     edi, r14d
0x18000dbcf  jmp     loc_18000DB3A
```
