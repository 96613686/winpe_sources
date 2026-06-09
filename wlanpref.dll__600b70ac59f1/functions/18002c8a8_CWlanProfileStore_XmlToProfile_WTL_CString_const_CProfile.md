# CWlanProfileStore::XmlToProfile(WTL::CString const &,CProfile &)

- ea: `0x18002c8a8`
- end: `0x18002d190`
- name: `?XmlToProfile@CWlanProfileStore@@IEAAJAEBVCString@WTL@@AEAVCProfile@@@Z`
- size: `2280`
- prototype: `__int64 __fastcall(CWlanProfileStore *this, const unsigned __int16 **, struct CProfile *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bb40`

## callees

- `0x180001e2c`
- `0x180001e9c`
- `0x180003458`
- `0x1800036ac`
- `0x1800036fc`
- `0x180008484`
- `0x18000cdcc`
- `0x18000cf1c`
- `0x18000d1d0`
- `0x18000d360`
- `0x180012d4c`
- `0x18002780c`
- `0x180028100`
- `0x180029cc8`
- `0x18002b1d4`
- `0x18002be00`
- `0x18002c458`
- `0x18002c8a8`
- `0x18002d3f0`
- `0x18002d458`
- `0x18002d520`
- `0x18002d7f6`
- `0x18002d81a`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002c92e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d142`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c92e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d142`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c947`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d15b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002c947`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d15b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c9bc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c9bc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c8e9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002c8e9`

## string_xrefs

- `0x18002c954`: `xmlns:p='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:wps='http://www.microsoft.com/networking/WPSSettings/v1' `
- `0x18002ceb8`: `//p:IHV/p:security`

## pseudocode

```c
__int64 __fastcall CWlanProfileStore::XmlToProfile(
        CWlanProfileStore *this,
        const unsigned __int16 **a2,
        struct CProfile *a3)
{
  CProfile *v3; // r13
  HRESULT v5; // edi
  struct IXMLDOMParseError **v6; // r8
  int XML; // ebx
  int v9; // r8d
  unsigned int v10; // r15d
  DWORD v11; // ebx
  UINT v12; // edx
  unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r14
  wchar_t **p_String1; // rcx
  _QWORD *i; // rbx
  char v17; // bl
  char v18; // r14
  char v19; // bl
  __int64 v20; // r9
  wchar_t *v21; // rbx
  int v22; // ecx
  LPVOID v23; // [rsp+20h] [rbp-188h] BYREF
  const unsigned __int16 *v24; // [rsp+28h] [rbp-180h] BYREF
  const unsigned __int16 *v25; // [rsp+30h] [rbp-178h] BYREF
  const unsigned __int16 *v26; // [rsp+38h] [rbp-170h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-168h]
  const unsigned __int16 *v28; // [rsp+48h] [rbp-160h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-158h] BYREF
  HRESULT v30; // [rsp+58h] [rbp-150h]
  wchar_t *v31; // [rsp+60h] [rbp-148h] BYREF
  _BYTE v32[8]; // [rsp+68h] [rbp-140h] BYREF
  struct _tagpropertykey Buf1; // [rsp+70h] [rbp-138h] BYREF
  LPVOID ppv[2]; // [rsp+88h] [rbp-120h] BYREF
  _BYTE v35[8]; // [rsp+98h] [rbp-110h] BYREF
  _BYTE v36[8]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v37[8]; // [rsp+A8h] [rbp-100h] BYREF
  wchar_t *String1; // [rsp+B0h] [rbp-F8h] BYREF
  _BYTE v39[8]; // [rsp+B8h] [rbp-F0h] BYREF
  _BYTE v40[8]; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE v41[8]; // [rsp+C8h] [rbp-E0h] BYREF
  _BYTE v42[8]; // [rsp+D0h] [rbp-D8h] BYREF
  _BYTE v43[8]; // [rsp+D8h] [rbp-D0h] BYREF
  _BYTE v44[8]; // [rsp+E0h] [rbp-C8h] BYREF
  _BYTE v45[8]; // [rsp+E8h] [rbp-C0h] BYREF
  CProfile *v46; // [rsp+F0h] [rbp-B8h]
  _BYTE v47[8]; // [rsp+100h] [rbp-A8h] BYREF
  _BYTE v48[8]; // [rsp+108h] [rbp-A0h] BYREF
  _BYTE v49[8]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v50[8]; // [rsp+118h] [rbp-90h] BYREF
  _BYTE v51[8]; // [rsp+120h] [rbp-88h] BYREF
  _BYTE v52[8]; // [rsp+128h] [rbp-80h] BYREF
  __int128 v53; // [rsp+130h] [rbp-78h] BYREF
  __int64 v54; // [rsp+140h] [rbp-68h]
  __int128 v55; // [rsp+148h] [rbp-60h]
  int v56; // [rsp+158h] [rbp-50h]
  GUID pguid; // [rsp+160h] [rbp-48h] BYREF
  __int64 v58; // [rsp+170h] [rbp-38h] BYREF

  v3 = a3;
  v46 = a3;
  v5 = CoInitializeEx(0, 2u);
  v30 = v5;
  *(_OWORD *)ppv = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *a2);
  XML = CXMLDocument::LoadXML(ppv, (const struct ATL::CComBSTR *)&bstrString, v6);
  if ( XML < 0 )
  {
LABEL_2:
    SysFreeString(bstrString);
    CXMLDocument::~CXMLDocument((CXMLDocument *)ppv);
    if ( v5 >= 0 )
      CoUninitialize();
    return (unsigned int)XML;
  }
  WTL::CString::CString(
    (WTL::CString *)v32,
    L"xmlns:p='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:wps='http://www.microsoft.com/networking/WPSSettings/v1' ");
  XML = CXMLDocument::SetSelectionNamespaces((CXMLDocument *)ppv, (const struct WTL::CString *)v32, v9);
  if ( XML < 0 )
  {
    WTL::CString::~CString((WTL::CString *)v32);
    goto LABEL_2;
  }
  v23 = ppv[0];
  if ( ppv[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 8LL))(ppv[0]);
  pguid = 0;
  CoCreateGuid(&pguid);
  *(GUID *)((char *)v3 + 12) = pguid;
  if ( dword_1800407E4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800407E4);
    if ( dword_1800407E4 == -1 )
    {
      xmmword_1800406F0 = xmmword_180038750;
      dword_180040700 = 2;
      dword_180040704 = 19005;
      xmmword_180040708 = xmmword_180038720;
      dword_180040718 = 5;
      dword_18004071C = 19004;
      xmmword_180040720 = xmmword_1800386F0;
      dword_180040730 = 9;
      dword_180040734 = 19002;
      xmmword_180040738 = xmmword_180038738;
      dword_180040748 = 4;
      dword_18004074C = 19001;
      xmmword_180040750 = xmmword_180038708;
      dword_180040760 = 6;
      dword_180040764 = 0;
      xmmword_180040768 = xmmword_1800386D8;
      dword_180040778 = 12;
      dword_18004077C = 0;
      Init_thread_footer(&dword_1800407E4);
    }
  }
  v10 = 0;
  v27 = 0;
  while ( v10 < 6 )
  {
    Buf1.fmtid = *(GUID *)((char *)&xmmword_1800406F0 + 24 * v10);
    v11 = *((_DWORD *)&xmmword_1800406F0 + 6 * v10 + 4);
    Buf1.pid = v11;
    v26 = WTL::_atltmpPchNil;
    v12 = *((_DWORD *)&xmmword_1800406F0 + 6 * v10 + 5);
    if ( !v12 )
    {
      v13 = L"false";
LABEL_18:
      WTL::CString::operator=((WTL::CString *)&v26, v13);
      goto LABEL_63;
    }
    if ( v12 == 1 )
    {
      v13 = L"true";
      goto LABEL_18;
    }
    WTL::CString::LoadStringW((WTL::CString *)&v26, v12);
LABEL_63:
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v14 = WTL::_atltmpPchNil;
      v25 = WTL::_atltmpPchNil;
      switch ( v11 )
      {
        case 2u:
          if ( !memcmp_0(&Buf1, &xmmword_180038750, 0x10u) )
          {
            WTL::CString::CString((WTL::CString *)v35, L"//p:WLANProfile/p:name");
            NodeText((WTL::CString *)v47);
            WTL::CString::operator=((WTL::CString *)&v25);
            WTL::CString::~CString((WTL::CString *)v47);
            p_String1 = (wchar_t **)v35;
            break;
          }
LABEL_57:
          CProfile::SetProperty(v3, &Buf1, (const struct WTL::CString *)&v25);
          WTL::CString::~CString((WTL::CString *)&v25);
          goto LABEL_65;
        case 5u:
          if ( !memcmp_0(&Buf1, &xmmword_180038720, 0x10u) )
          {
            v53 = 0;
            v54 = 0;
            v55 = 0;
            v56 = 10;
            v24 = v14;
            WTL::CString::CString((WTL::CString *)v36, L"//p:phyType");
            NodeTextList(&v23, v36, &v53);
            WTL::CString::~CString((WTL::CString *)v36);
            if ( v54 )
            {
              WTL::CString::operator=((WTL::CString *)&v24, L"802.11");
              for ( i = (_QWORD *)v53; i; i = (_QWORD *)*i )
                WTL::CString::operator+=(&v24, i + 2);
            }
            else
            {
              WTL::CString::operator=((WTL::CString *)&v24);
            }
            WTL::CString::operator=((WTL::CString *)&v25);
            WTL::CString::~CString((WTL::CString *)&v24);
            ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::RemoveAll(&v53);
          }
          goto LABEL_57;
        case 0xCu:
          if ( memcmp_0(&Buf1, &xmmword_1800386D8, 0x10u) )
            goto LABEL_57;
          WTL::CString::CString((WTL::CString *)v37, L"//p:connectionType");
          NodeText((WTL::CString *)&String1);
          WTL::CString::~CString((WTL::CString *)v37);
          if ( !wcscmp_0(String1, L"IBSS") )
            WTL::CString::operator=((WTL::CString *)&v25, L"true");
          else
            WTL::CString::operator=((WTL::CString *)&v25, L"false");
          p_String1 = &String1;
          break;
        case 6u:
          if ( memcmp_0(&Buf1, &xmmword_180038708, 0x10u) )
            goto LABEL_57;
          WTL::CString::CString((WTL::CString *)v39, L"//wps:WPSDomain");
          NodeText((WTL::CString *)v48);
          WTL::CString::operator=((WTL::CString *)&v25);
          WTL::CString::~CString((WTL::CString *)v48);
          p_String1 = (wchar_t **)v39;
          break;
        case 9u:
          if ( memcmp_0(&Buf1, &xmmword_1800386F0, 0x10u) )
            goto LABEL_57;
          WTL::CString::CString((WTL::CString *)v40, L"//p:connectionMode");
          NodeText((WTL::CString *)v49);
          WTL::CString::operator=((WTL::CString *)&v25);
          WTL::CString::~CString((WTL::CString *)v49);
          p_String1 = (wchar_t **)v40;
          break;
        default:
          if ( v11 != 4 || memcmp_0(&Buf1, &xmmword_180038738, 0x10u) )
            goto LABEL_57;
          v28 = v14;
          v24 = v14;
          WTL::CString::CString((WTL::CString *)v41, L"//p:IHV/p:security");
          v17 = NodeExists(&v23, v41);
          WTL::CString::~CString((WTL::CString *)v41);
          if ( v17 )
          {
            WTL::CString::operator=((WTL::CString *)&v28, L"IHV");
            WTL::CString::operator=((WTL::CString *)&v24, L"IHV");
          }
          else
          {
            WTL::CString::CString((WTL::CString *)v42, L"//p:authentication");
            NodeText((WTL::CString *)v50);
            WTL::CString::operator=((WTL::CString *)&v28);
            WTL::CString::~CString((WTL::CString *)v50);
            WTL::CString::~CString((WTL::CString *)v42);
            WTL::CString::CString((WTL::CString *)v43, L"//p:encryption");
            NodeText((WTL::CString *)v51);
            WTL::CString::operator=((WTL::CString *)&v24);
            WTL::CString::~CString((WTL::CString *)v51);
            WTL::CString::~CString((WTL::CString *)v43);
          }
          v18 = 0;
          WTL::CString::CString((WTL::CString *)v44, L"//p:useOneX");
          v19 = NodeExists(&v23, v44);
          WTL::CString::~CString((WTL::CString *)v44);
          if ( v19 )
          {
            WTL::CString::CString((WTL::CString *)v45, L"//p:useOneX");
            NodeText((WTL::CString *)&v31);
            WTL::CString::~CString((WTL::CString *)v45);
            WTL::CString::MakeLower((WTL::CString *)&v31);
            v21 = v31;
            if ( !wcscmp_0(v31, L"true") )
              goto LABEL_53;
            v22 = *v21 - 49;
            if ( *v21 == 49 )
              v22 = v21[1];
            if ( !v22 )
LABEL_53:
              v18 = 1;
            WTL::CString::~CString((WTL::CString *)&v31);
          }
          LOBYTE(v20) = v18;
          CProfile::GetFriendlySecurity(v52, &v28, &v24, v20, v23, v24, v25, v26);
          WTL::CString::operator=((WTL::CString *)&v25);
          WTL::CString::~CString((WTL::CString *)v52);
          WTL::CString::~CString((WTL::CString *)&v24);
          p_String1 = (wchar_t **)&v28;
          break;
      }
      WTL::CString::~CString((WTL::CString *)p_String1);
      goto LABEL_57;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &XmlUtilException `RTTI Type Descriptor', (XmlUtilException *)&v58) )
      {
        CProfile::SetProperty(v46, &Buf1, (const struct WTL::CString *)&v26);
        v5 = v30;
        v10 = v27;
        v3 = v46;
        __eh34_try_continuation(0, &XmlUtilException `RTTI Type Descriptor', &loc_18002D0F2);
      }
    }
LABEL_65:
    WTL::CString::~CString((WTL::CString *)&v26);
    v27 = ++v10;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  WTL::CString::~CString((WTL::CString *)v32);
  SysFreeString(bstrString);
  CXMLDocument::~CXMLDocument((CXMLDocument *)ppv);
  if ( v5 >= 0 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18002c8a8  mov     [rsp+arg_0], rbx
0x18002c8ad  mov     [rsp+arg_18], rsi
0x18002c8b2  push    rdi
0x18002c8b3  push    r12
0x18002c8b5  push    r13
0x18002c8b7  push    r14
0x18002c8b9  push    r15
0x18002c8bb  sub     rsp, 180h
0x18002c8c2  mov     rax, cs:__security_cookie
0x18002c8c9  xor     rax, rsp
0x18002c8cc  mov     [rsp+1A8h+var_30], rax
0x18002c8d4  mov     r13, r8
0x18002c8d7  mov     rbx, rdx
0x18002c8da  mov     [rsp+1A8h+var_B8], r8
0x18002c8e2  mov     edx, 2; dwCoInit
0x18002c8e7  xor     ecx, ecx; pvReserved
0x18002c8e9  call    cs:__imp_CoInitializeEx
0x18002c8ef  mov     edi, eax
0x18002c8f1  mov     [rsp+1A8h+var_150], eax
0x18002c8f5  xorps   xmm0, xmm0
0x18002c8f8  movdqu  xmmword ptr [rsp+1A8h+ppv], xmm0
0x18002c901  mov     rdx, [rbx]; unsigned __int16 *
0x18002c904  lea     rcx, [rsp+1A8h+bstrString]; this
0x18002c909  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c90e  nop
0x18002c90f  lea     rdx, [rsp+1A8h+bstrString]; struct ATL::CComBSTR *
0x18002c914  lea     rcx, [rsp+1A8h+ppv]; ppv
0x18002c91c  call    ?LoadXML@CXMLDocument@@QEAAJAEBVCComBSTR@ATL@@PEAPEAUIXMLDOMParseError@@@Z; CXMLDocument::LoadXML(ATL::CComBSTR const &,IXMLDOMParseError * *)
0x18002c921  mov     ebx, eax
0x18002c923  xor     esi, esi
0x18002c925  test    eax, eax
0x18002c927  jns     short loc_18002C954
0x18002c929  mov     rcx, [rsp+1A8h+bstrString]; bstrString
0x18002c92e  call    cs:__imp_SysFreeString
0x18002c934  nop
0x18002c935  lea     rcx, [rsp+1A8h+ppv]; this
0x18002c93d  call    ??1CXMLDocument@@QEAA@XZ; CXMLDocument::~CXMLDocument(void)
0x18002c942  nop
0x18002c943  test    edi, edi
0x18002c945  js      short loc_18002C94D
0x18002c947  call    cs:__imp_CoUninitialize
0x18002c94d  mov     eax, ebx
0x18002c94f  jmp     loc_18002D163
0x18002c954  lea     rdx, aXmlnsPHttpWwwM; "xmlns:p='http://www.microsoft.com/netwo"...
0x18002c95b  lea     rcx, [rsp+1A8h+var_140]; this
0x18002c960  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002c965  nop
0x18002c966  lea     rdx, [rsp+1A8h+var_140]; struct WTL::CString *
0x18002c96b  lea     rcx, [rsp+1A8h+ppv]; this
0x18002c973  call    ?SetSelectionNamespaces@CXMLDocument@@QEAAJAEBVCString@WTL@@H@Z; CXMLDocument::SetSelectionNamespaces(WTL::CString const &,int)
0x18002c978  mov     ebx, eax
0x18002c97a  test    eax, eax
0x18002c97c  jns     short loc_18002C98A
0x18002c97e  lea     rcx, [rsp+1A8h+var_140]; this
0x18002c983  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002c988  jmp     short loc_18002C929
0x18002c98a  mov     rcx, [rsp+1A8h+ppv]
0x18002c992  mov     [rsp+1A8h+var_188], rcx
0x18002c997  test    rcx, rcx
0x18002c99a  jz      short loc_18002C9A9
0x18002c99c  mov     rax, [rcx]
0x18002c99f  mov     rax, [rax+8]
0x18002c9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9a8  nop
0x18002c9a9  xorps   xmm0, xmm0
0x18002c9ac  movups  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x18002c9b4  lea     rcx, [rsp+1A8h+pguid]; pguid
0x18002c9bc  call    cs:__imp_CoCreateGuid
0x18002c9c2  movups  xmm0, xmmword ptr [rsp+1A8h+pguid.Data1]
0x18002c9ca  movdqu  xmmword ptr [r13+0Ch], xmm0
0x18002c9d0  mov     ecx, cs:_tls_index
0x18002c9d6  mov     rax, gs:58h
0x18002c9df  mov     edx, 4
0x18002c9e4  mov     rax, [rax+rcx*8]
0x18002c9e8  mov     ecx, [rdx+rax]
0x18002c9eb  cmp     cs:dword_1800407E4, ecx
0x18002c9f1  jle     loc_18002CAEC
0x18002c9f7  lea     rcx, dword_1800407E4
0x18002c9fe  call    _Init_thread_header
0x18002ca03  cmp     cs:dword_1800407E4, 0FFFFFFFFh
0x18002ca0a  jnz     loc_18002CAEC
0x18002ca10  movups  xmm0, cs:xmmword_180038750
0x18002ca17  movaps  cs:xmmword_1800406F0, xmm0
0x18002ca1e  mov     eax, cs:dword_180038760
0x18002ca24  mov     cs:dword_180040700, eax
0x18002ca2a  mov     cs:dword_180040704, 4A3Dh
0x18002ca34  movups  xmm0, cs:xmmword_180038720
0x18002ca3b  movups  cs:xmmword_180040708, xmm0
0x18002ca42  mov     eax, cs:dword_180038730
0x18002ca48  mov     cs:dword_180040718, eax
0x18002ca4e  mov     cs:dword_18004071C, 4A3Ch
0x18002ca58  movups  xmm0, cs:xmmword_1800386F0
0x18002ca5f  movaps  cs:xmmword_180040720, xmm0
0x18002ca66  mov     eax, cs:dword_180038700
0x18002ca6c  mov     cs:dword_180040730, eax
0x18002ca72  mov     cs:dword_180040734, 4A3Ah
0x18002ca7c  movups  xmm0, cs:xmmword_180038738
0x18002ca83  movups  cs:xmmword_180040738, xmm0
0x18002ca8a  mov     eax, cs:dword_180038748
0x18002ca90  mov     cs:dword_180040748, eax
0x18002ca96  mov     cs:dword_18004074C, 4A39h
0x18002caa0  movups  xmm0, cs:xmmword_180038708
0x18002caa7  movaps  cs:xmmword_180040750, xmm0
0x18002caae  mov     eax, cs:dword_180038718
0x18002cab4  mov     cs:dword_180040760, eax
0x18002caba  mov     cs:dword_180040764, esi
0x18002cac0  movups  xmm0, cs:xmmword_1800386D8
0x18002cac7  movups  cs:xmmword_180040768, xmm0
0x18002cace  mov     eax, cs:dword_1800386E8
0x18002cad4  mov     cs:dword_180040778, eax
0x18002cada  mov     cs:dword_18004077C, esi
0x18002cae0  lea     rcx, dword_1800407E4
0x18002cae7  call    _Init_thread_footer
0x18002caec  mov     r15d, esi
0x18002caef  mov     [rsp+1A8h+var_168], esi
0x18002caf3  lea     r14, xmmword_1800406F0
0x18002cafa  mov     r12d, 10h
0x18002cb00  cmp     r15d, 6
0x18002cb04  jnb     loc_18002D127
0x18002cb0a  mov     eax, r15d
0x18002cb0d  lea     rcx, [rax+rax*2]
0x18002cb11  movups  xmm0, xmmword ptr [r14+rcx*8]
0x18002cb16  movups  [rsp+1A8h+Buf1], xmm0
0x18002cb1b  mov     ebx, [r14+rcx*8+10h]
0x18002cb20  mov     [rsp+1A8h+var_128], ebx
0x18002cb27  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18002cb2e  mov     [rsp+1A8h+var_170], rax
0x18002cb33  mov     edx, [r14+rcx*8+14h]; uID
0x18002cb38  lea     rcx, [rsp+1A8h+var_170]; this
0x18002cb3d  test    edx, edx
0x18002cb3f  jnz     short loc_18002CB4A
0x18002cb41  lea     rdx, aFalse; "false"
0x18002cb48  jmp     short loc_18002CB56
0x18002cb4a  cmp     edx, 1
0x18002cb4d  jnz     short loc_18002CB5D
0x18002cb4f  lea     rdx, aTrue; "true"
0x18002cb56  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18002cb5b  jmp     short loc_18002CB63
0x18002cb5d  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18002cb62  nop
0x18002cb63  mov     r14, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18002cb6a  mov     [rsp+1A8h+var_178], r14
0x18002cb6f  cmp     ebx, 2
0x18002cb72  jnz     short loc_18002CBE9
0x18002cb74  mov     r8, r12; Size
0x18002cb77  lea     rdx, xmmword_180038750; Buf2
0x18002cb7e  lea     rcx, [rsp+1A8h+Buf1]; Buf1
0x18002cb83  call    memcmp_0
0x18002cb88  test    eax, eax
0x18002cb8a  jnz     loc_18002D0D2
0x18002cb90  lea     rdx, aPWlanprofilePN; "//p:WLANProfile/p:name"
0x18002cb97  lea     rcx, [rsp+1A8h+var_110]; this
0x18002cb9f  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002cba4  nop
0x18002cba5  lea     r8, [rsp+1A8h+var_110]
0x18002cbad  lea     rdx, [rsp+1A8h+var_188]
0x18002cbb2  lea     rcx, [rsp+1A8h+var_A8]; this
0x18002cbba  call    ?NodeText@@YA?AVCString@WTL@@AEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV12@@Z; NodeText(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &)
0x18002cbbf  nop
0x18002cbc0  mov     rdx, rax
0x18002cbc3  lea     rcx, [rsp+1A8h+var_178]; this
0x18002cbc8  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18002cbcd  nop
0x18002cbce  lea     rcx, [rsp+1A8h+var_A8]; this
0x18002cbd6  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002cbdb  nop
0x18002cbdc  lea     rcx, [rsp+1A8h+var_110]
0x18002cbe4  jmp     loc_18002D0CD
0x18002cbe9  cmp     ebx, 5
0x18002cbec  jnz     loc_18002CCEE
0x18002cbf2  mov     r8, r12; Size
0x18002cbf5  lea     rdx, xmmword_180038720; Buf2
0x18002cbfc  lea     rcx, [rsp+1A8h+Buf1]; Buf1
0x18002cc01  call    memcmp_0
0x18002cc06  test    eax, eax
0x18002cc08  jnz     loc_18002D0D2
0x18002cc0e  xorps   xmm0, xmm0
0x18002cc11  movdqu  [rsp+1A8h+var_78], xmm0
0x18002cc1a  mov     [rsp+1A8h+var_68], rsi
0x18002cc22  xorps   xmm1, xmm1
0x18002cc25  movdqu  [rsp+1A8h+var_60], xmm1
0x18002cc2e  mov     [rsp+1A8h+var_50], 0Ah
0x18002cc39  mov     [rsp+1A8h+var_180], r14
0x18002cc3e  lea     rdx, aPPhytype; "//p:phyType"
0x18002cc45  lea     rcx, [rsp+1A8h+var_108]; this
0x18002cc4d  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002cc52  nop
0x18002cc53  lea     r8, [rsp+1A8h+var_78]
0x18002cc5b  lea     rdx, [rsp+1A8h+var_108]
0x18002cc63  lea     rcx, [rsp+1A8h+var_188]
0x18002cc68  call    ?NodeTextList@@YAXAEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBVCString@WTL@@AEAV?$CAtlList@VCString@WTL@@V?$CElementTraits@VCString@WTL@@@ATL@@@2@@Z; NodeTextList(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &,ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>> &)
0x18002cc6d  nop
0x18002cc6e  lea     rcx, [rsp+1A8h+var_108]; this
0x18002cc76  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002cc7b  lea     rcx, [rsp+1A8h+var_180]; this
0x18002cc80  cmp     [rsp+1A8h+var_68], rsi
0x18002cc88  jnz     short loc_18002CCC1
0x18002cc8a  lea     rdx, [rsp+1A8h+var_170]
0x18002cc8f  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18002cc94  lea     rdx, [rsp+1A8h+var_180]
0x18002cc99  lea     rcx, [rsp+1A8h+var_178]; this
0x18002cc9e  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18002cca3  nop
0x18002cca4  lea     rcx, [rsp+1A8h+var_180]; this
0x18002cca9  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002ccae  nop
0x18002ccaf  lea     rcx, [rsp+1A8h+var_78]
0x18002ccb7  call    ?RemoveAll@?$CAtlList@VCString@WTL@@V?$CElementTraits@VCString@WTL@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<WTL::CString,ATL::CElementTraits<WTL::CString>>::RemoveAll(void)
0x18002ccbc  jmp     loc_18002D0D2
0x18002ccc1  lea     rdx, a80211; "802.11"
0x18002ccc8  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18002cccd  mov     rbx, qword ptr [rsp+1A8h+var_78]
0x18002ccd5  test    rbx, rbx
0x18002ccd8  jz      short loc_18002CC94
0x18002ccda  lea     rdx, [rbx+10h]
0x18002ccde  lea     rcx, [rsp+1A8h+var_180]
0x18002cce3  call    ??YCString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator+=(WTL::CString const &)
0x18002cce8  nop
0x18002cce9  mov     rbx, [rbx]
0x18002ccec  jmp     short loc_18002CCD5
0x18002ccee  cmp     ebx, 0Ch
0x18002ccf1  jnz     loc_18002CD95
0x18002ccf7  mov     r8, r12; Size
0x18002ccfa  lea     rdx, xmmword_1800386D8; Buf2
0x18002cd01  lea     rcx, [rsp+1A8h+Buf1]; Buf1
0x18002cd06  call    memcmp_0
0x18002cd0b  test    eax, eax
0x18002cd0d  jnz     loc_18002D0D2
0x18002cd13  lea     rdx, aPConnectiontyp; "//p:connectionType"
0x18002cd1a  lea     rcx, [rsp+1A8h+var_100]; this
0x18002cd22  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002cd27  nop
0x18002cd28  lea     r8, [rsp+1A8h+var_100]
0x18002cd30  lea     rdx, [rsp+1A8h+var_188]
0x18002cd35  lea     rcx, [rsp+1A8h+String1]; this
0x18002cd3d  call    ?NodeText@@YA?AVCString@WTL@@AEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV12@@Z; NodeText(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &)
0x18002cd42  nop
0x18002cd43  lea     rcx, [rsp+1A8h+var_100]; this
0x18002cd4b  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002cd50  lea     rdx, aIbss; "IBSS"
0x18002cd57  mov     rcx, [rsp+1A8h+String1]; String1
0x18002cd5f  call    wcscmp_0
0x18002cd64  lea     rcx, [rsp+1A8h+var_178]; this
0x18002cd69  test    eax, eax
0x18002cd6b  jnz     short loc_18002CD7B
0x18002cd6d  lea     rdx, aTrue; "true"
0x18002cd74  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18002cd79  jmp     short loc_18002CD88
0x18002cd7b  lea     rdx, aFalse; "false"
0x18002cd82  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18002cd87  nop
0x18002cd88  lea     rcx, [rsp+1A8h+String1]
0x18002cd90  jmp     loc_18002D0CD
0x18002cd95  cmp     ebx, 6
0x18002cd98  jnz     short loc_18002CE0F
0x18002cd9a  mov     r8, r12; Size
0x18002cd9d  lea     rdx, xmmword_180038708; Buf2
0x18002cda4  lea     rcx, [rsp+1A8h+Buf1]; Buf1
0x18002cda9  call    memcmp_0
0x18002cdae  test    eax, eax
0x18002cdb0  jnz     loc_18002D0D2
0x18002cdb6  lea     rdx, aWpsWpsdomain; "//wps:WPSDomain"
0x18002cdbd  lea     rcx, [rsp+1A8h+var_F0]; this
0x18002cdc5  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002cdca  nop
0x18002cdcb  lea     r8, [rsp+1A8h+var_F0]
0x18002cdd3  lea     rdx, [rsp+1A8h+var_188]
0x18002cdd8  lea     rcx, [rsp+1A8h+var_A0]; this
0x18002cde0  call    ?NodeText@@YA?AVCString@WTL@@AEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV12@@Z; NodeText(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &)
0x18002cde5  nop
0x18002cde6  mov     rdx, rax
0x18002cde9  lea     rcx, [rsp+1A8h+var_178]; this
0x18002cdee  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18002cdf3  nop
0x18002cdf4  lea     rcx, [rsp+1A8h+var_A0]; this
0x18002cdfc  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002ce01  nop
0x18002ce02  lea     rcx, [rsp+1A8h+var_F0]
0x18002ce0a  jmp     loc_18002D0CD
0x18002ce0f  cmp     ebx, 9
0x18002ce12  jnz     short loc_18002CE89
0x18002ce14  mov     r8, r12; Size
0x18002ce17  lea     rdx, xmmword_1800386F0; Buf2
0x18002ce1e  lea     rcx, [rsp+1A8h+Buf1]; Buf1
0x18002ce23  call    memcmp_0
0x18002ce28  test    eax, eax
0x18002ce2a  jnz     loc_18002D0D2
0x18002ce30  lea     rdx, aPConnectionmod; "//p:connectionMode"
0x18002ce37  lea     rcx, [rsp+1A8h+var_E8]; this
0x18002ce3f  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002ce44  nop
0x18002ce45  lea     r8, [rsp+1A8h+var_E8]
0x18002ce4d  lea     rdx, [rsp+1A8h+var_188]
0x18002ce52  lea     rcx, [rsp+1A8h+var_98]; this
0x18002ce5a  call    ?NodeText@@YA?AVCString@WTL@@AEBV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV12@@Z; NodeText(ATL::CComPtr<IXMLDOMDocument2> const &,WTL::CString const &)
0x18002ce5f  nop
0x18002ce60  mov     rdx, rax
0x18002ce63  lea     rcx, [rsp+1A8h+var_178]; this
0x18002ce68  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18002ce6d  nop
  ... truncated ...
```
