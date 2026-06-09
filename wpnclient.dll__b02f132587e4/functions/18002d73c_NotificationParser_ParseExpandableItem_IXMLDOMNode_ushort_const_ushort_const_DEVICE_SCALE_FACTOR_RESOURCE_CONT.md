# NotificationParser::ParseExpandableItem(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18002d73c`
- end: `0x18002de75`
- name: `?ParseExpandableItem@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1849`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d370`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x180008fe0`
- `0x180009890`
- `0x18000a460`
- `0x18000dc30`
- `0x180013f00`
- `0x180014500`
- `0x18001b848`
- `0x18001ff00`
- `0x18002d280`
- `0x18002d73c`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002dc69`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dcb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dc69`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dcb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall NotificationParser::ParseExpandableItem(
        __int64 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  __int64 *v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v13; // rbx
  HSTRING *v14; // rax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r15d
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, struct IXMLDOMNode **); // rbx
  int v24; // eax
  int v25; // eax
  wchar_t *v26; // rbx
  const unsigned __int16 *v27; // r9
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v30; // rbx
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v35; // rbx
  int v36; // eax
  struct IXMLDOMNode *v37; // rdi
  HRESULT (__stdcall *get_childNodes)(IXMLDOMNode *, IXMLDOMNodeList **); // rbx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rsi
  __int64 (__fastcall *v42)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v43; // rbx
  HSTRING *v44; // rax
  int v45; // eax
  int v46; // eax
  unsigned int v47; // r12d
  unsigned int i; // r14d
  struct Windows::Foundation::Collections::IPropertySet *v49; // rdi
  __int64 (__fastcall *v50)(struct Windows::Foundation::Collections::IPropertySet *, _QWORD, __int64 *); // rbx
  int v51; // eax
  int v52; // eax
  OLECHAR *v53; // rbx
  int v54; // eax
  __int64 v55; // r9
  __int64 v56; // rsi
  __int64 (__fastcall *v57)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v58; // rbx
  int v59; // eax
  __int64 v60; // rax
  int v62; // [rsp+20h] [rbp-E0h]
  _BYTE v63[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v64; // [rsp+48h] [rbp-B8h] BYREF
  int v65; // [rsp+50h] [rbp-B0h] BYREF
  int v66; // [rsp+54h] [rbp-ACh] BYREF
  struct IXMLDOMNode *v67; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-90h] BYREF
  __int64 v71; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+80h] [rbp-80h] BYREF
  __int64 v73; // [rsp+88h] [rbp-78h] BYREF
  __int64 v74; // [rsp+90h] [rbp-70h] BYREF
  __int64 v75; // [rsp+98h] [rbp-68h] BYREF
  __int64 v76; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v78; // [rsp+B0h] [rbp-50h]
  BSTR bstrString; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v80; // [rsp+C0h] [rbp-40h]
  _QWORD *v81; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v82[16]; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v84[12]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v78 = a3;
  v8 = a1;
  v80 = a1;
  v81 = a7;
  v73 = 0;
  v72 = 0;
  v77 = 0;
  v68 = 0;
  v71 = 0;
  v63[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  NotificationParser::CreateValueSet(v9, &v73, &v72);
  NotificationParser::GetAttributes(v8, a2, v72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  NotificationParser::CreateValueSet(v10, &v77, &v68);
  v11 = v72;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v72 + 80LL);
  v13 = v77;
  v14 = Windows::Internal::StringReference::StringReference(string, L"items");
  v15 = v12(v11, *v14, v13, v63);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v62);
  v65 = 0;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
  v17 = v16(a2, &v71);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      v62);
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 64LL))(v71, &v65);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v18,
      v62);
  v19 = v65;
  if ( v65 >= 4 )
  {
    v19 = 4;
    v65 = 4;
  }
  v20 = 0;
  if ( v19 > 0 )
  {
    while ( 1 )
    {
      v21 = StringCchPrintfW(v84, 0xAu, L"%ld", v20);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x544,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v21,
          v62);
      v67 = 0;
      v22 = v71;
      v23 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v71 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
      v24 = v23(v22, v20, &v67);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x547,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v24,
          v62);
      String1 = 0;
      v25 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v67->lpVtbl->get_nodeName)(v67, &String1);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x54A,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v25,
          v62);
      v26 = String1;
      if ( !wcscmp_0(String1, L"text") )
        break;
      if ( !wcscmp_0(v26, L"image") )
      {
        v64 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
        NotificationParser::ParseImage(v8, (__int64)v67, v78, v32, a5, a6, (__int64 *)&v64);
        v33 = v68;
        v34 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)v68 + 80LL);
        v35 = v64;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v82, v84);
        v36 = v34(v33, *(_QWORD *)v82, v35, v63);
        if ( v36 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x556,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v36,
            v62);
        goto LABEL_12;
      }
      if ( !wcscmp_0(v26, L"actions") )
      {
        v64 = 0;
        v37 = v67;
        get_childNodes = v67->lpVtbl->get_childNodes;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
        v39 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct Windows::Foundation::Collections::IPropertySet **))get_childNodes)(
                v37,
                &v64);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x55B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v39,
            v62);
        v76 = 0;
        v75 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
        NotificationParser::CreateValueSet(v40, &v76, &v75);
        v41 = v68;
        v42 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v68 + 80LL);
        v43 = v76;
        v44 = Windows::Internal::StringReference::StringReference(string, L"actions");
        v45 = v42(v41, *v44, v43, v63);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x560,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v45,
            v62);
        v66 = 0;
        v46 = (*(__int64 (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *, int *))(*(_QWORD *)v64 + 64LL))(
                v64,
                &v66);
        if ( v46 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x563,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v46,
            v62);
        v47 = 0;
        for ( i = 0; (int)i < v66; ++i )
        {
          v69 = 0;
          v49 = v64;
          v50 = *(__int64 (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *, _QWORD, __int64 *))(*(_QWORD *)v64 + 56LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
          v51 = v50(v49, i, &v69);
          if ( v51 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x569,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v51,
              v62);
          bstrString = 0;
          v52 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v69 + 56LL))(v69, &bstrString);
          if ( v52 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x56B,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v52,
              v62);
          v53 = bstrString;
          if ( !wcscmp_0(bstrString, L"action") )
          {
            v54 = StringCchPrintfW(v82, 0xAu, L"%ld", v47);
            if ( v54 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x56F,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v54,
                v62);
            v74 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
            NotificationParser::ParseAction(v80, v69, v78, v55, a5, a6, &v74);
            v56 = v75;
            v57 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v75 + 80LL);
            v58 = v74;
            Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v82);
            v59 = v57(v56, string[0], v58, v63);
            if ( v59 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x572,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v59,
                v62);
            ++v47;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
            v53 = bstrString;
          }
          SysFreeString(v53);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
        v8 = v80;
        goto LABEL_29;
      }
LABEL_30:
      SysFreeString(v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
      if ( (int)++v20 >= v65 )
        goto LABEL_31;
    }
    v64 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
    NotificationParser::ParseText((NotificationParser *)v8, v67, v78, v27, &v64);
    v28 = v68;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)v68 + 80LL);
    v30 = v64;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v82, v84);
    v31 = v29(v28, *(_QWORD *)v82, v30, v63);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v31,
        v62);
LABEL_12:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
LABEL_29:
    v26 = String1;
    goto LABEL_30;
  }
LABEL_31:
  v60 = v73;
  v73 = 0;
  *v81 = v60;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
}

```

## disassembly

```asm
0x18002d73c  mov     [rsp-8+arg_18], rbx
0x18002d741  push    rbp
0x18002d742  push    rsi
0x18002d743  push    rdi
0x18002d744  push    r12
0x18002d746  push    r13
0x18002d748  push    r14
0x18002d74a  push    r15
0x18002d74c  lea     rbp, [rsp-30h]
0x18002d751  sub     rsp, 130h
0x18002d758  mov     rax, cs:__security_cookie
0x18002d75f  xor     rax, rsp
0x18002d762  mov     [rbp+60h+var_38], rax
0x18002d766  mov     [rbp+60h+var_B0], r8
0x18002d76a  mov     r14, rdx
0x18002d76d  mov     r12, rcx
0x18002d770  mov     [rbp+60h+var_A0], rcx
0x18002d774  mov     rax, [rbp+60h+arg_30]
0x18002d77b  mov     [rbp+60h+var_98], rax
0x18002d77f  xor     eax, eax
0x18002d781  mov     [rbp+60h+var_D8], rax
0x18002d785  mov     [rbp+60h+var_E0], rax
0x18002d789  mov     [rbp+60h+var_B8], rax
0x18002d78d  mov     [rsp+160h+var_100], rax
0x18002d792  mov     [rsp+160h+var_E8], rax
0x18002d797  mov     [rsp+160h+var_120], al
0x18002d79b  lea     rcx, [rbp+60h+var_E0]
0x18002d79f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d7a4  lea     rcx, [rbp+60h+var_D8]
0x18002d7a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d7ad  lea     r8, [rbp+60h+var_E0]
0x18002d7b1  lea     rdx, [rbp+60h+var_D8]
0x18002d7b5  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002d7ba  mov     r8, [rbp+60h+var_E0]
0x18002d7be  mov     rdx, r14
0x18002d7c1  mov     rcx, r12
0x18002d7c4  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18002d7c9  lea     rcx, [rsp+160h+var_100]
0x18002d7ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d7d3  lea     rcx, [rbp+60h+var_B8]
0x18002d7d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d7dc  lea     r8, [rsp+160h+var_100]
0x18002d7e1  lea     rdx, [rbp+60h+var_B8]
0x18002d7e5  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002d7ea  mov     rsi, [rbp+60h+var_E0]
0x18002d7ee  mov     rax, [rsi]
0x18002d7f1  mov     rdi, [rax+50h]
0x18002d7f5  mov     rbx, [rbp+60h+var_B8]
0x18002d7f9  lea     rdx, aItems; "items"
0x18002d800  lea     rcx, [rbp+60h+string]; string
0x18002d804  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18002d809  lea     r9, [rsp+160h+var_120]
0x18002d80e  mov     r8, rbx
0x18002d811  mov     rdx, [rax]
0x18002d814  mov     rcx, rsi
0x18002d817  mov     rax, rdi
0x18002d81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d81f  mov     rcx, [rbp+68h]; this
0x18002d823  xor     esi, esi
0x18002d825  test    eax, eax
0x18002d827  js      loc_18002DD64
0x18002d82d  mov     [rsp+160h+var_110], esi
0x18002d831  mov     rax, [r14]
0x18002d834  mov     rbx, [rax+60h]
0x18002d838  lea     rcx, [rsp+160h+var_E8]
0x18002d83d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d842  lea     rdx, [rsp+160h+var_E8]
0x18002d847  mov     rcx, r14
0x18002d84a  mov     rax, rbx
0x18002d84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d852  mov     rcx, [rbp+68h]; this
0x18002d856  test    eax, eax
0x18002d858  js      loc_18002DD79
0x18002d85e  mov     rcx, [rsp+160h+var_E8]
0x18002d863  mov     rax, [rcx]
0x18002d866  lea     rdx, [rsp+160h+var_110]
0x18002d86b  mov     rax, [rax+40h]
0x18002d86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d874  mov     rcx, [rbp+68h]; this
0x18002d878  test    eax, eax
0x18002d87a  js      loc_18002DD8E
0x18002d880  mov     eax, [rsp+160h+var_110]
0x18002d884  cmp     eax, 4
0x18002d887  jl      short loc_18002D890
0x18002d889  lea     eax, [rsi+4]
0x18002d88c  mov     [rsp+160h+var_110], eax
0x18002d890  mov     r15d, esi
0x18002d893  test    eax, eax
0x18002d895  jle     loc_18002DCD1
0x18002d89b  mov     r13d, [rbp+60h+arg_28]
0x18002d8a2  mov     r9d, r15d
0x18002d8a5  lea     r8, aLd; "%ld"
0x18002d8ac  mov     edx, 0Ah; unsigned __int64
0x18002d8b1  lea     rcx, [rbp+60h+var_50]; unsigned __int16 *
0x18002d8b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d8ba  mov     rcx, [rbp+68h]; this
0x18002d8be  test    eax, eax
0x18002d8c0  js      loc_18002DD4F
0x18002d8c6  mov     [rsp+160h+var_108], rsi
0x18002d8cb  mov     rdi, [rsp+160h+var_E8]
0x18002d8d0  mov     rax, [rdi]
0x18002d8d3  mov     rbx, [rax+38h]
0x18002d8d7  lea     rcx, [rsp+160h+var_108]
0x18002d8dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d8e1  lea     r8, [rsp+160h+var_108]
0x18002d8e6  mov     edx, r15d
0x18002d8e9  mov     rcx, rdi
0x18002d8ec  mov     rax, rbx
0x18002d8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8f4  mov     rcx, [rbp+68h]; this
0x18002d8f8  test    eax, eax
0x18002d8fa  js      loc_18002DD3A
0x18002d900  mov     [rsp+160h+String1], rsi
0x18002d905  mov     rcx, [rsp+160h+var_108]
0x18002d90a  mov     rax, [rcx]
0x18002d90d  lea     rdx, [rsp+160h+String1]
0x18002d912  mov     rax, [rax+38h]
0x18002d916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d91b  mov     rcx, [rbp+68h]; this
0x18002d91f  test    eax, eax
0x18002d921  js      loc_18002DE60
0x18002d927  lea     rdx, aText; "text"
0x18002d92e  mov     rbx, [rsp+160h+String1]
0x18002d933  mov     rcx, rbx; String1
0x18002d936  call    wcscmp_0
0x18002d93b  test    eax, eax
0x18002d93d  jnz     short loc_18002D9BB
0x18002d93f  mov     [rsp+160h+var_118], rsi
0x18002d944  lea     rcx, [rsp+160h+var_118]
0x18002d949  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d94e  lea     rax, [rsp+160h+var_118]
0x18002d953  mov     [rsp+160h+var_140], rax; int
0x18002d958  mov     r8, [rbp+60h+var_B0]; unsigned __int16 *
0x18002d95c  mov     rdx, [rsp+160h+var_108]; struct IXMLDOMNode *
0x18002d961  mov     rcx, r12; this
0x18002d964  call    ?ParseText@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseText(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x18002d969  mov     rsi, [rsp+160h+var_100]
0x18002d96e  mov     rax, [rsi]
0x18002d971  mov     rdi, [rax+50h]
0x18002d975  mov     rbx, [rsp+160h+var_118]
0x18002d97a  lea     rdx, [rbp+60h+var_50]; unsigned __int16 *
0x18002d97e  lea     rcx, [rbp+60h+var_90]; this
0x18002d982  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002d987  lea     r9, [rsp+160h+var_120]
0x18002d98c  mov     r8, rbx
0x18002d98f  mov     rdx, qword ptr [rbp+60h+var_90]
0x18002d993  mov     rcx, rsi
0x18002d996  mov     rax, rdi
0x18002d999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d99e  mov     rcx, [rbp+68h]; this
0x18002d9a2  xor     esi, esi
0x18002d9a4  test    eax, eax
0x18002d9a6  js      loc_18002DDA3
0x18002d9ac  lea     rcx, [rsp+160h+var_118]
0x18002d9b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d9b6  jmp     loc_18002DCAA
0x18002d9bb  lea     rdx, aImage; "image"
0x18002d9c2  mov     rcx, rbx; String1
0x18002d9c5  call    wcscmp_0
0x18002d9ca  test    eax, eax
0x18002d9cc  jnz     loc_18002DA53
0x18002d9d2  mov     [rsp+160h+var_118], rsi
0x18002d9d7  lea     rcx, [rsp+160h+var_118]
0x18002d9dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d9e1  lea     rax, [rsp+160h+var_118]
0x18002d9e6  mov     [rsp+160h+var_130], rax
0x18002d9eb  mov     [rsp+160h+var_138], r13d
0x18002d9f0  mov     eax, [rbp+60h+arg_20]
0x18002d9f6  mov     dword ptr [rsp+160h+var_140], eax; int
0x18002d9fa  mov     r8, [rbp+60h+var_B0]
0x18002d9fe  mov     rdx, [rsp+160h+var_108]
0x18002da03  mov     rcx, r12
0x18002da06  call    ?ParseImage@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseImage(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18002da0b  mov     rsi, [rsp+160h+var_100]
0x18002da10  mov     rax, [rsi]
0x18002da13  mov     rdi, [rax+50h]
0x18002da17  mov     rbx, [rsp+160h+var_118]
0x18002da1c  lea     rdx, [rbp+60h+var_50]; unsigned __int16 *
0x18002da20  lea     rcx, [rbp+60h+var_90]; this
0x18002da24  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002da29  lea     r9, [rsp+160h+var_120]
0x18002da2e  mov     r8, rbx
0x18002da31  mov     rdx, qword ptr [rbp+60h+var_90]
0x18002da35  mov     rcx, rsi
0x18002da38  mov     rax, rdi
0x18002da3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da40  mov     rcx, [rbp+68h]; this
0x18002da44  xor     esi, esi
0x18002da46  test    eax, eax
0x18002da48  js      loc_18002DDB8
0x18002da4e  jmp     loc_18002D9AC
0x18002da53  lea     rdx, aActions; "actions"
0x18002da5a  mov     rcx, rbx; String1
0x18002da5d  call    wcscmp_0
0x18002da62  test    eax, eax
0x18002da64  jnz     loc_18002DCAF
0x18002da6a  mov     [rsp+160h+var_118], rsi
0x18002da6f  mov     rdi, [rsp+160h+var_108]
0x18002da74  mov     rax, [rdi]
0x18002da77  mov     rbx, [rax+60h]
0x18002da7b  lea     rcx, [rsp+160h+var_118]
0x18002da80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002da85  lea     rdx, [rsp+160h+var_118]
0x18002da8a  mov     rcx, rdi
0x18002da8d  mov     rax, rbx
0x18002da90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da95  mov     rcx, [rbp+68h]; this
0x18002da99  test    eax, eax
0x18002da9b  js      loc_18002DE4B
0x18002daa1  mov     [rbp+60h+var_C0], rsi
0x18002daa5  mov     [rbp+60h+var_C8], rsi
0x18002daa9  lea     rcx, [rbp+60h+var_C8]
0x18002daad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dab2  lea     rcx, [rbp+60h+var_C0]
0x18002dab6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dabb  lea     r8, [rbp+60h+var_C8]
0x18002dabf  lea     rdx, [rbp+60h+var_C0]
0x18002dac3  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18002dac8  mov     rsi, [rsp+160h+var_100]
0x18002dacd  mov     rax, [rsi]
0x18002dad0  mov     rdi, [rax+50h]
0x18002dad4  mov     rbx, [rbp+60h+var_C0]
0x18002dad8  lea     rdx, aActions; "actions"
0x18002dadf  lea     rcx, [rbp+60h+string]; string
0x18002dae3  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x18002dae8  lea     r9, [rsp+160h+var_120]
0x18002daed  mov     r8, rbx
0x18002daf0  mov     rdx, [rax]
0x18002daf3  mov     rcx, rsi
0x18002daf6  mov     rax, rdi
0x18002daf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dafe  mov     rcx, [rbp+68h]; this
0x18002db02  xor     esi, esi
0x18002db04  test    eax, eax
0x18002db06  js      loc_18002DE36
0x18002db0c  mov     [rsp+160h+var_10C], esi
0x18002db10  mov     rcx, [rsp+160h+var_118]
0x18002db15  mov     rax, [rcx]
0x18002db18  lea     rdx, [rsp+160h+var_10C]
0x18002db1d  mov     rax, [rax+40h]
0x18002db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db26  mov     rcx, [rbp+68h]; this
0x18002db2a  test    eax, eax
0x18002db2c  js      loc_18002DE21
0x18002db32  mov     r12d, esi
0x18002db35  mov     r14d, esi
0x18002db38  cmp     [rsp+160h+var_10C], esi
0x18002db3c  jle     loc_18002DC88
0x18002db42  mov     [rsp+160h+var_F8], rsi
0x18002db47  mov     rdi, [rsp+160h+var_118]
0x18002db4c  mov     rax, [rdi]
0x18002db4f  mov     rbx, [rax+38h]
0x18002db53  lea     rcx, [rsp+160h+var_F8]
0x18002db58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002db5d  lea     r8, [rsp+160h+var_F8]
0x18002db62  mov     edx, r14d
0x18002db65  mov     rcx, rdi
0x18002db68  mov     rax, rbx
0x18002db6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db70  mov     rcx, [rbp+68h]; this
0x18002db74  test    eax, eax
0x18002db76  js      loc_18002DE0C
0x18002db7c  mov     [rbp+60h+bstrString], rsi
0x18002db80  mov     rcx, [rsp+160h+var_F8]
0x18002db85  mov     rax, [rcx]
0x18002db88  lea     rdx, [rbp+60h+bstrString]
0x18002db8c  mov     rax, [rax+38h]
0x18002db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db95  mov     rcx, [rbp+68h]; this
0x18002db99  test    eax, eax
0x18002db9b  js      loc_18002DDF7
0x18002dba1  lea     rdx, aAction; "action"
0x18002dba8  mov     rbx, [rbp+60h+bstrString]
0x18002dbac  mov     rcx, rbx; String1
0x18002dbaf  call    wcscmp_0
0x18002dbb4  test    eax, eax
0x18002dbb6  jnz     loc_18002DC66
0x18002dbbc  mov     r9d, r12d
0x18002dbbf  lea     r8, aLd; "%ld"
0x18002dbc6  lea     edx, [rax+0Ah]; unsigned __int64
0x18002dbc9  lea     rcx, [rbp+60h+var_90]; unsigned __int16 *
0x18002dbcd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dbd2  mov     rcx, [rbp+68h]; this
0x18002dbd6  test    eax, eax
0x18002dbd8  js      loc_18002DDE2
0x18002dbde  mov     [rbp+60h+var_D0], rsi
0x18002dbe2  lea     rcx, [rbp+60h+var_D0]
0x18002dbe6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dbeb  lea     rax, [rbp+60h+var_D0]
0x18002dbef  mov     [rsp+160h+var_130], rax
0x18002dbf4  mov     [rsp+160h+var_138], r13d
0x18002dbf9  mov     eax, [rbp+60h+arg_20]
0x18002dbff  mov     dword ptr [rsp+160h+var_140], eax; int
0x18002dc03  mov     r8, [rbp+60h+var_B0]
0x18002dc07  mov     rdx, [rsp+160h+var_F8]
0x18002dc0c  mov     rcx, [rbp+60h+var_A0]
0x18002dc10  call    ?ParseAction@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseAction(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x18002dc15  mov     rsi, [rbp+60h+var_C8]
0x18002dc19  mov     rax, [rsi]
0x18002dc1c  mov     rdi, [rax+50h]
  ... truncated ...
```
