# CEcsTokenBroker::GetAccessToken(HWND__ *,ushort const *,ushort const *,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,IUnknown * *)

- ea: `0x1800ce8cc`
- end: `0x1800cf8da`
- name: `?GetAccessToken@CEcsTokenBroker@@SAJPEAUHWND__@@PEBG1_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@PEAPEAUIUnknown@@@Z`
- size: `4110`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x18006d200`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180004420`
- `0x180007e10`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x180015150`
- `0x180028490`
- `0x180028984`
- `0x18002dbf4`
- `0x1800cd440`
- `0x1800cd488`
- `0x1800cd4d4`
- `0x1800cd520`
- `0x1800cd56c`
- `0x1800cd5b8`
- `0x1800cd604`
- `0x1800cd650`
- `0x1800cd734`
- `0x1800cd77c`
- `0x1800cd7c4`
- `0x1800cd804`
- `0x1800ce76c`
- `0x1800ce8cc`
- `0x1800cf8e0`
- `0x1800cfb30`
- `0x1800cfcec`
- `0x1800d04c0`
- `0x1800d0808`
- `0x1800d08ec`
- `0x18013e010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800cece5`
- `KERNEL32!RaiseException` at `0x1800cee2f`
- `KERNEL32!RaiseException` at `0x1800cef75`
- `KERNEL32!RaiseException` at `0x1800cf05d`
- `KERNEL32!RaiseException` at `0x1800cf0b3`
- `KERNEL32!RaiseException` at `0x1800cece5`
- `KERNEL32!RaiseException` at `0x1800cee2f`
- `KERNEL32!RaiseException` at `0x1800cef75`
- `KERNEL32!RaiseException` at `0x1800cf05d`
- `KERNEL32!RaiseException` at `0x1800cf0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ced00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cee4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cef90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ced00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cee4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cef90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf0cf`

## string_xrefs

- `0x1800ce9ac`: `CEcsTokenBroker::GetAccessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CEcsTokenBroker::GetAccessToken(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v9; // rcx
  _BYTE *v10; // rax
  char v11; // al
  _QWORD *v12; // r8
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // r8
  _QWORD *v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  _QWORD *v20; // rax
  int v21; // eax
  __int64 *v22; // rdi
  __int64 (__fastcall *v23)(__int64 *, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v24)[26]; // rdx
  _QWORD *v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 v31; // rax
  const WCHAR *v32; // rdi
  unsigned __int64 v33; // r12
  unsigned __int64 v34; // rbx
  HSTRING v35; // rbx
  const unsigned __int16 (*v36)[1]; // rdx
  _QWORD *v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rsi
  __int64 v41; // rax
  const WCHAR *v42; // rdi
  unsigned __int64 v43; // rbx
  HSTRING v44; // rbx
  const unsigned __int16 (*v45)[9]; // rdx
  _QWORD *v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // rdx
  __int64 v49; // rsi
  __int64 (__fastcall *v50)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v51; // rbx
  const unsigned __int16 (*v52)[18]; // rdx
  _QWORD *v53; // rax
  int v54; // eax
  __int64 v55; // rdi
  unsigned __int64 v56; // rbx
  const WCHAR *v57; // rsi
  HSTRING v58; // rbx
  const unsigned __int16 (*v59)[10]; // rdx
  _QWORD *v60; // rax
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rsi
  __int64 v64; // rax
  const WCHAR *v65; // rdi
  unsigned __int64 v66; // rbx
  HSTRING v67; // rdi
  int v68; // eax
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 *v71; // rdi
  __int64 v72; // rax
  __int64 (__fastcall *v73)(__int64 *, __int64, __int64, __int64 *); // rbx
  int v74; // eax
  __int16 v75; // cx
  __int64 (__fastcall *v76)(__int64 *, __int64, __int64 *); // rbx
  int v77; // eax
  int v78; // eax
  int v79; // eax
  PVOID *v80; // rcx
  __int64 v81; // rdi
  __int64 (__fastcall *v82)(__int64, __int64 *); // rbx
  int v83; // eax
  int v84; // ecx
  int v85; // eax
  __int64 v86; // rdi
  __int64 (__fastcall *v87)(__int64, __int64 *); // rbx
  int v88; // eax
  __int64 v89; // rdi
  __int64 (__fastcall *v90)(__int64, _QWORD, __int64 *); // rbx
  int v91; // eax
  int v92; // eax
  __int64 v93; // rbx
  __int64 v94; // rax
  __int64 v95; // rcx
  unsigned int v96; // ebx
  _BYTE v98[8]; // [rsp+40h] [rbp-228h] BYREF
  int v99; // [rsp+48h] [rbp-220h] BYREF
  int v100; // [rsp+4Ch] [rbp-21Ch]
  char v101; // [rsp+50h] [rbp-218h]
  const char *v102; // [rsp+58h] [rbp-210h]
  __int64 v103; // [rsp+60h] [rbp-208h]
  char v104; // [rsp+68h] [rbp-200h]
  int v105; // [rsp+6Ch] [rbp-1FCh] BYREF
  int v106; // [rsp+70h] [rbp-1F8h] BYREF
  __int64 v107; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v108; // [rsp+80h] [rbp-1E8h] BYREF
  __int64 v109; // [rsp+88h] [rbp-1E0h] BYREF
  __int64 v110; // [rsp+90h] [rbp-1D8h] BYREF
  __int64 *v111; // [rsp+98h] [rbp-1D0h] BYREF
  __int64 v112; // [rsp+A0h] [rbp-1C8h] BYREF
  __int64 v113; // [rsp+A8h] [rbp-1C0h] BYREF
  __int64 (__fastcall *v114)(__int64, __int64, _QWORD, HSTRING, _DWORD, __int64 *); // [rsp+B0h] [rbp-1B8h]
  __int64 v115; // [rsp+B8h] [rbp-1B0h] BYREF
  __int64 v116; // [rsp+C0h] [rbp-1A8h] BYREF
  __int64 v117; // [rsp+C8h] [rbp-1A0h] BYREF
  int v118; // [rsp+D0h] [rbp-198h] BYREF
  int v119; // [rsp+D4h] [rbp-194h] BYREF
  int v120; // [rsp+D8h] [rbp-190h] BYREF
  int v121; // [rsp+DCh] [rbp-18Ch] BYREF
  int v122; // [rsp+E0h] [rbp-188h] BYREF
  int v123; // [rsp+E4h] [rbp-184h] BYREF
  int v124; // [rsp+E8h] [rbp-180h] BYREF
  int v125; // [rsp+ECh] [rbp-17Ch] BYREF
  int v126; // [rsp+F0h] [rbp-178h] BYREF
  int v127; // [rsp+F4h] [rbp-174h] BYREF
  int v128; // [rsp+F8h] [rbp-170h] BYREF
  int v129; // [rsp+FCh] [rbp-16Ch] BYREF
  int v130; // [rsp+100h] [rbp-168h] BYREF
  int pExceptionObject; // [rsp+104h] [rbp-164h] BYREF
  int v132; // [rsp+108h] [rbp-160h] BYREF
  int v133; // [rsp+10Ch] [rbp-15Ch] BYREF
  int v134; // [rsp+110h] [rbp-158h] BYREF
  int v135; // [rsp+114h] [rbp-154h] BYREF
  int v136; // [rsp+118h] [rbp-150h] BYREF
  int v137; // [rsp+11Ch] [rbp-14Ch] BYREF
  int v138; // [rsp+120h] [rbp-148h] BYREF
  int v139; // [rsp+124h] [rbp-144h] BYREF
  int v140; // [rsp+128h] [rbp-140h] BYREF
  __int64 v141; // [rsp+130h] [rbp-138h] BYREF
  __int64 v142; // [rsp+138h] [rbp-130h] BYREF
  __int64 v143; // [rsp+140h] [rbp-128h] BYREF
  int v144; // [rsp+148h] [rbp-120h] BYREF
  PCWSTR sourceString; // [rsp+150h] [rbp-118h]
  int v146; // [rsp+158h] [rbp-110h] BYREF
  __int64 v147; // [rsp+160h] [rbp-108h]
  _QWORD *v148; // [rsp+168h] [rbp-100h]
  int v149; // [rsp+170h] [rbp-F8h] BYREF
  __int64 v150; // [rsp+178h] [rbp-F0h]
  const ATL::CAtlException *v151; // [rsp+180h] [rbp-E8h] BYREF
  HSTRING string; // [rsp+188h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+190h] [rbp-D8h] BYREF
  HSTRING v154; // [rsp+1A8h] [rbp-C0h] BYREF
  HSTRING_HEADER v155; // [rsp+1B0h] [rbp-B8h] BYREF
  _BYTE v156[32]; // [rsp+1C8h] [rbp-A0h] BYREF
  _BYTE v157[32]; // [rsp+1E8h] [rbp-80h] BYREF
  _BYTE v158[32]; // [rsp+208h] [rbp-60h] BYREF
  _BYTE v159[32]; // [rsp+228h] [rbp-40h] BYREF

  v104 = a4;
  sourceString = a2;
  v150 = a5;
  v9 = a6;
  v147 = a6;
  v148 = a7;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v10 = WPP_GLOBAL_Control;
      v9 = v147;
    }
  }
  if ( (v10[68] & 2) != 0 && v10[65] >= 6u )
  {
    v11 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v11 = 0;
LABEL_9:
  v99 = 0;
  v100 = 132;
  v101 = v11;
  v102 = "CEcsTokenBroker::GetAccessToken";
  v103 = 0;
  std::wstring::_Eos(v9, 0);
  if ( v12 )
    *v12 = 0;
  try
  {
    if ( !a2 || !*a2 )
    {
      v99 = -2147024809;
      HIWORD(v100) = 139;
      v136 = -2147024809;
      throw (long *)&v136;
    }
    v99 = 0;
    LOWORD(v100) = 139;
    std::wstring::wstring(v157);
    std::wstring::wstring(v156);
    CEcsTokenBroker::ResolveAuthRequestParameters(a3, v157, v156);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v156);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v157);
      WPP_SF_SSS(*(_QWORD *)(v15 + 56), v14, v16);
    }
    v143 = 0;
    v17 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, (const unsigned __int16 (*)[57])v13);
    v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
            *v17,
            &v143);
    v99 = v18;
    if ( v18 < 0 )
    {
      HIWORD(v100) = 156;
      pExceptionObject = v18;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v100) = 156;
    v111 = 0;
    v20 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, (const unsigned __int16 (*)[70])v19);
    v21 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
            *v20,
            &v111);
    v99 = v21;
    if ( v21 < 0 )
    {
      HIWORD(v100) = 162;
      v132 = v21;
      throw (long *)&v132;
    }
    LOWORD(v100) = 162;
    v117 = 0;
    v22 = v111;
    v23 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v111 + 88);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
    v25 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, v24);
    v26 = v23(v22, *v25, &v117);
    v99 = v26;
    if ( v26 < 0 )
    {
      HIWORD(v100) = 168;
      v133 = v26;
      throw (long *)&v133;
    }
    LOWORD(v100) = 168;
    v116 = 0;
    v27 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
            v117,
            &v116);
    v99 = v27;
    if ( v27 < 0 )
    {
      HIWORD(v100) = 171;
      v134 = v27;
      throw (long *)&v134;
    }
    LOWORD(v100) = 171;
    v99 = v27;
    v28 = v116;
    if ( !v116 )
    {
      v99 = -2147023728;
      HIWORD(v100) = 172;
      v135 = -2147023728;
      throw (long *)&v135;
    }
    v99 = 0;
    LOWORD(v100) = 172;
    if ( a5 )
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    else
      v29 = 0;
    GetWebAccount(&v113, v111, v28, v29);
    v110 = 0;
    v30 = v143;
    v114 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING, _DWORD, __int64 *))(*(_QWORD *)v143 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v157);
    v32 = (const WCHAR *)v31;
    v33 = -1;
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v31 + 2 * v34) );
    if ( v34 > 0xFFFFFFFF )
    {
      LODWORD(v34) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v32, v34, &hstringHeader, &string);
    v35 = string;
    v37 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, v36);
    v38 = v114(v30, v116, *v37, v35, 0, &v110);
    v99 = v38;
    if ( v38 < 0 )
    {
      HIWORD(v100) = 188;
      v137 = v38;
      throw (long *)&v137;
    }
    LOWORD(v100) = 188;
    v98[0] = 0;
    v108 = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v110 + 80LL))(v110, &v108);
    v99 = v39;
    if ( v39 < 0 )
    {
      HIWORD(v100) = 192;
      v138 = v39;
      throw (long *)&v138;
    }
    LOWORD(v100) = 192;
    v40 = v108;
    v114 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING, _DWORD, __int64 *))(*(_QWORD *)v108 + 80LL);
    v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v156);
    v42 = (const WCHAR *)v41;
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)(v41 + 2 * v43) );
    if ( v43 > 0xFFFFFFFF )
    {
      LODWORD(v43) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v42, v43, &hstringHeader, &string);
    v44 = string;
    v46 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, v45);
    v47 = ((__int64 (__fastcall *)(__int64, _QWORD, HSTRING, _BYTE *))v114)(v40, *v46, v44, v98);
    v99 = v47;
    if ( v47 < 0 )
    {
      HIWORD(v100) = 193;
      v139 = v47;
      throw (long *)&v139;
    }
    LOWORD(v100) = 193;
    v49 = v108;
    v50 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v108 + 80LL);
    v51 = *(_QWORD *)Windows::Internal::StringReference::StringReference(&v154, (const unsigned __int16 (*)[6])v48);
    v53 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, v52);
    v54 = v50(v49, *v53, v51, v98);
    v99 = v54;
    if ( v54 < 0 )
    {
      HIWORD(v100) = 194;
      v140 = v54;
      throw (long *)&v140;
    }
    LOWORD(v100) = 194;
    v55 = v108;
    v114 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING, _DWORD, __int64 *))(*(_QWORD *)v108 + 80LL);
    v56 = -1;
    v57 = sourceString;
    do
      ++v56;
    while ( sourceString[v56] );
    if ( v56 > 0xFFFFFFFF )
    {
      LODWORD(v56) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v57, v56, &hstringHeader, &string);
    v58 = string;
    v60 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v154, v59);
    v61 = ((__int64 (__fastcall *)(__int64, _QWORD, HSTRING, _BYTE *))v114)(v55, *v60, v58, v98);
    v99 = v61;
    if ( v61 < 0 )
    {
      HIWORD(v100) = 199;
      v144 = v61;
      throw (long *)&v144;
    }
    LOWORD(v100) = 199;
    LOBYTE(v62) = v104;
    CEcsTokenBroker::GetExtraParameterValue(v158, v62);
    v63 = v108;
    sourceString = *(PCWSTR *)(*(_QWORD *)v108 + 80LL);
    v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v158);
    v65 = (const WCHAR *)v64;
    v66 = -1;
    do
      ++v66;
    while ( *(_WORD *)(v64 + 2 * v66) );
    if ( v66 > 0xFFFFFFFF )
    {
      LODWORD(v66) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v65, v66, &hstringHeader, &string);
    v67 = string;
    do
      ++v33;
    while ( CEcsTokenBroker::c_pwszExtraParameterName[v33] );
    if ( v33 > 0xFFFFFFFF )
    {
      LODWORD(v33) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(CEcsTokenBroker::c_pwszExtraParameterName, v33, &v155, &v154);
    v68 = ((__int64 (__fastcall *)(__int64, HSTRING, HSTRING, _BYTE *))sourceString)(v63, v154, v67, v98);
    v99 = v68;
    if ( v68 < 0 )
    {
      HIWORD(v100) = 206;
      v146 = v68;
      throw (long *)&v146;
    }
    LOWORD(v100) = 206;
    v99 = v68;
    if ( v98[0] )
    {
      v99 = -2147418113;
      HIWORD(v100) = 208;
      v118 = -2147418113;
      throw (long *)&v118;
    }
    v99 = 0;
    LOWORD(v100) = 208;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v69 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v158);
      WPP_SF_llS(*(_QWORD *)(v70 + 56), v113 != 0, v70, 1, v113 != 0, v69);
    }
    v109 = 0;
    v71 = v111;
    v72 = *v111;
    if ( v113 )
    {
      v73 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v72 + 56);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
      v74 = v73(v71, v110, v113, &v109);
      v99 = v74;
      v75 = 226;
      if ( v74 < 0 )
      {
        HIWORD(v100) = 226;
        v119 = v74;
        throw (long *)&v119;
      }
    }
    else
    {
      v76 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v72 + 48);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
      v77 = v76(v71, v110, &v109);
      v99 = v77;
      v75 = 230;
      if ( v77 < 0 )
      {
        HIWORD(v100) = 230;
        v120 = v77;
        throw (long *)&v120;
      }
    }
    LOWORD(v100) = v75;
    v107 = 0;
    v78 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
            v109,
            &v107);
    v99 = v78;
    if ( v78 < 0 )
    {
      HIWORD(v100) = 256;
      v121 = v78;
      throw (long *)&v121;
    }
    LOWORD(v100) = 256;
    v106 = 0;
    v79 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v107 + 56LL))(v107, &v106);
    v99 = v79;
    if ( v79 < 0 )
    {
      HIWORD(v100) = 259;
      v122 = v79;
      throw (long *)&v122;
    }
    LOWORD(v100) = 259;
    v80 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v80 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v106 == 3 )
    {
      if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 68) & 2) != 0 && *((_BYTE *)v80 + 65) >= 4u )
        WPP_SF_(v80[7], (unsigned int)(v106 + 16), &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v99 = -2134375680;
      HIWORD(v100) = 266;
      v123 = -2134375680;
      throw (long *)&v123;
    }
    if ( v106 == 5 )
    {
      if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 68) & 2) != 0 && *((_BYTE *)v80 + 65) >= 2u )
        WPP_SF_(v80[7], (unsigned int)(v106 + 15), &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v141 = 0;
      v81 = v107;
      v82 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v107 + 64LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141);
      v83 = v82(v81, &v141);
      v99 = v83;
      if ( v83 < 0 )
      {
        HIWORD(v100) = 274;
        v130 = v83;
        throw (long *)&v130;
      }
      LOWORD(v100) = 274;
      v105 = 0;
      v84 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v141 + 48LL))(v141, &v105);
      v99 = v84;
      if ( v84 < 0 )
      {
        HIWORD(v100) = 277;
        v124 = v84;
        throw (long *)&v124;
      }
      LOWORD(v100) = 277;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      }
      v85 = v105;
      if ( v105 == -895025148 || v105 == -895025145 || v105 == -895025142 )
      {
        v85 = -2134376375;
      }
      else
      {
        if ( v105 < 0 )
          goto LABEL_107;
        v85 = -2134375619;
      }
      v105 = v85;
LABEL_107:
      v99 = v85;
      HIWORD(v100) = 290;
      v125 = v85;
      throw (long *)&v125;
    }
    if ( v106 )
    {
      if ( v80 != &WPP_GLOBAL_Control && (*((_BYTE *)v80 + 68) & 2) != 0 && *((_BYTE *)v80 + 65) >= 2u )
        WPP_SF_(v80[7], 22, &WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids);
      v99 = -2134375619;
      HIWORD(v100) = 296;
      v126 = -2134375619;
      throw (long *)&v126;
    }
    v115 = 0;
    v86 = v107;
    v87 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v107 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
    v88 = v87(v86, &v115);
    v99 = v88;
    if ( v88 < 0 )
    {
      HIWORD(v100) = 300;
      v127 = v88;
      throw (long *)&v127;
    }
    LOWORD(v100) = 300;
    v112 = 0;
    v89 = v115;
    v90 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v115 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
    v91 = v90(v89, 0, &v112);
    v99 = v91;
    if ( v91 < 0 )
    {
      HIWORD(v100) = 303;
      v128 = v91;
      throw (long *)&v128;
    }
    LOWORD(v100) = 303;
    v142 = 0;
    v92 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v112 + 48LL))(v112, &v142);
    v99 = v92;
    if ( v92 < 0 )
    {
      HIWORD(v100) = 306;
      v129 = v92;
      throw (long *)&v129;
    }
    LOWORD(v100) = 306;
    WstringFromString(v159, &v142);
    v93 = v150;
    if ( v150 && !v113 )
    {
      GetAccountId(&v154, v112);
      std::wstring::swap(v93, &v154);
      std::wstring::~wstring(&v154);
    }
    std::wstring::swap(v147, v159);
    if ( v148 )
    {
      v94 = v107;
      v107 = 0;
      *v148 = v94;
    }
    std::wstring::~wstring(v159);
    Windows::Internal::String::~String((Windows::Internal::String *)&v142);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
    std::wstring::~wstring(v158);
    v95 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v143);
    std::wstring::~wstring(v156);
    std::wstring::~wstring(v157);
  }
  catch ( long v149 )
  {
    v99 = v149;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v100) = 325;
    v99 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v100) = 325;
    v99 = -2147418113;
  }
  catch ( const ATL::CAtlException *v151 )
  {
    HIWORD(v100) = 325;
    v99 = *(_DWORD *)v151;
  }
  v96 = v99;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v99);
  return v96;
}

```

## disassembly

```asm
0x1800ce8cc  mov     [rsp+arg_0], rbx
0x1800ce8d1  mov     [rsp+arg_18], rsi
0x1800ce8d6  push    rdi
0x1800ce8d7  push    r12
0x1800ce8d9  push    r14
0x1800ce8db  sub     rsp, 250h
0x1800ce8e2  mov     rax, cs:__security_cookie
0x1800ce8e9  xor     rax, rsp
0x1800ce8ec  mov     [rsp+268h+var_20], rax
0x1800ce8f4  mov     [rsp+268h+var_200], r9b
0x1800ce8f9  mov     rbx, r8
0x1800ce8fc  mov     rdi, rdx
0x1800ce8ff  mov     [rsp+268h+sourceString], rdx
0x1800ce907  mov     rsi, [rsp+268h+arg_20]
0x1800ce90f  mov     [rsp+268h+var_F0], rsi
0x1800ce917  mov     rcx, [rsp+268h+arg_28]
0x1800ce91f  mov     [rsp+268h+var_108], rcx
0x1800ce927  mov     r8, [rsp+268h+arg_30]
0x1800ce92f  mov     [rsp+268h+var_100], r8
0x1800ce937  lea     r12, WPP_GLOBAL_Control
0x1800ce93e  mov     rax, cs:WPP_GLOBAL_Control
0x1800ce945  cmp     rax, r12
0x1800ce948  jz      short loc_1800CE982
0x1800ce94a  test    byte ptr [rax+44h], 2
0x1800ce94e  jz      short loc_1800CE995
0x1800ce950  cmp     byte ptr [rax+41h], 6
0x1800ce954  jb      short loc_1800CE982
0x1800ce956  mov     edx, 0Fh
0x1800ce95b  lea     r8, WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids
0x1800ce962  mov     rcx, [rax+38h]
0x1800ce966  call    WPP_SF_
0x1800ce96b  mov     rax, cs:WPP_GLOBAL_Control
0x1800ce972  mov     r8, [rsp+268h+var_100]
0x1800ce97a  mov     rcx, [rsp+268h+var_108]
0x1800ce982  test    byte ptr [rax+44h], 2
0x1800ce986  jz      short loc_1800CE995
0x1800ce988  cmp     byte ptr [rax+41h], 6
0x1800ce98c  jb      short loc_1800CE995
0x1800ce98e  mov     al, 1
0x1800ce990  xor     r14d, r14d
0x1800ce993  jmp     short loc_1800CE99B
0x1800ce995  xor     r14d, r14d
0x1800ce998  mov     al, r14b
0x1800ce99b  mov     [rsp+268h+var_220], r14d
0x1800ce9a0  mov     [rsp+268h+var_21C], 84h
0x1800ce9a8  mov     [rsp+268h+var_218], al
0x1800ce9ac  lea     rax, aCecstokenbroke_2; "CEcsTokenBroker::GetAccessToken"
0x1800ce9b3  mov     [rsp+268h+var_210], rax
0x1800ce9b8  mov     [rsp+268h+var_208], r14
0x1800ce9bd  xor     edx, edx
0x1800ce9bf  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800ce9c4  test    r8, r8
0x1800ce9c7  jz      short loc_1800CE9CC
0x1800ce9c9  mov     [r8], r14
0x1800ce9cc  mov     eax, [rsp+268h+var_220]
0x1800ce9d0  mov     [rsp+268h+var_220], eax
0x1800ce9d4  test    rdi, rdi
0x1800ce9d7  jz      loc_1800CF86C
0x1800ce9dd  cmp     [rdi], r14w
0x1800ce9e1  jz      loc_1800CF86C
0x1800ce9e7  mov     [rsp+268h+var_220], r14d
0x1800ce9ec  mov     eax, 8Bh
0x1800ce9f1  mov     word ptr [rsp+268h+var_21C], ax
0x1800ce9f6  lea     rcx, [rsp+268h+var_80]
0x1800ce9fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cea03  nop
0x1800cea04  lea     rcx, [rsp+268h+var_A0]
0x1800cea0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cea11  nop
0x1800cea12  lea     r8, [rsp+268h+var_A0]
0x1800cea1a  lea     rdx, [rsp+268h+var_80]
0x1800cea22  mov     rcx, rbx
0x1800cea25  call    ?ResolveAuthRequestParameters@CEcsTokenBroker@@SAXPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CEcsTokenBroker::ResolveAuthRequestParameters(ushort const *,std::wstring *,std::wstring *)
0x1800cea2a  mov     r10, cs:WPP_GLOBAL_Control
0x1800cea31  cmp     r10, r12
0x1800cea34  jz      short loc_1800CEA83
0x1800cea36  test    byte ptr [r10+44h], 2
0x1800cea3b  jz      short loc_1800CEA83
0x1800cea3d  cmp     byte ptr [r10+41h], 4
0x1800cea42  jb      short loc_1800CEA83
0x1800cea44  lea     rcx, [rsp+268h+var_A0]
0x1800cea4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cea51  mov     r8, rax
0x1800cea54  lea     rcx, [rsp+268h+var_80]
0x1800cea5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cea61  mov     edx, 10h
0x1800cea66  mov     [rsp+268h+var_240], r8; __int64
0x1800cea6b  mov     [rsp+268h+var_248], rax; __int64
0x1800cea70  mov     r9, rdi
0x1800cea73  lea     r8, WPP_8c5b6bd21cdc370d89616d2bd57ae836_Traceguids
0x1800cea7a  mov     rcx, [r10+38h]; LoggerHandle
0x1800cea7e  call    WPP_SF_SSS
0x1800cea83  mov     [rsp+268h+var_128], r14
0x1800cea8b  lea     rcx, [rsp+268h+var_C0]; string
0x1800cea93  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x1800cea98  lea     rdx, [rsp+268h+var_128]
0x1800ceaa0  mov     rcx, [rax]
0x1800ceaa3  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x1800ceaa8  mov     [rsp+268h+var_220], eax
0x1800ceaac  mov     [rsp+268h+var_220], eax
0x1800ceab0  mov     ecx, 9Ch
0x1800ceab5  test    eax, eax
0x1800ceab7  jns     short loc_1800CEAD9
0x1800ceab9  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800ceabe  mov     [rsp+268h+pExceptionObject], eax
0x1800ceac5  lea     rdx, _TI1J; pThrowInfo
0x1800ceacc  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x1800cead4  call    _CxxThrowException_0
0x1800cead9  mov     word ptr [rsp+268h+var_21C], cx
0x1800ceade  mov     [rsp+268h+var_1D0], r14
0x1800ceae6  lea     rcx, [rsp+268h+var_C0]; string
0x1800ceaee  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x1800ceaf3  lea     rdx, [rsp+268h+var_1D0]
0x1800ceafb  mov     rcx, [rax]
0x1800ceafe  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x1800ceb03  mov     [rsp+268h+var_220], eax
0x1800ceb07  mov     [rsp+268h+var_220], eax
0x1800ceb0b  mov     ecx, 0A2h
0x1800ceb10  test    eax, eax
0x1800ceb12  jns     short loc_1800CEB34
0x1800ceb14  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800ceb19  mov     [rsp+268h+var_160], eax
0x1800ceb20  lea     rdx, _TI1J; pThrowInfo
0x1800ceb27  lea     rcx, [rsp+268h+var_160]; pExceptionObject
0x1800ceb2f  call    _CxxThrowException_0
0x1800ceb34  mov     word ptr [rsp+268h+var_21C], cx
0x1800ceb39  mov     [rsp+268h+var_1A0], r14
0x1800ceb41  mov     rdi, [rsp+268h+var_1D0]
0x1800ceb49  mov     rax, [rdi]
0x1800ceb4c  mov     rbx, [rax+58h]
0x1800ceb50  lea     rcx, [rsp+268h+var_1A0]
0x1800ceb58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ceb5d  lea     rcx, [rsp+268h+var_C0]; string
0x1800ceb65  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x1800ceb6a  lea     r8, [rsp+268h+var_1A0]
0x1800ceb72  mov     rdx, [rax]
0x1800ceb75  mov     rcx, rdi
0x1800ceb78  mov     rax, rbx
0x1800ceb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb80  mov     [rsp+268h+var_220], eax
0x1800ceb84  mov     [rsp+268h+var_220], eax
0x1800ceb88  mov     ecx, 0A8h
0x1800ceb8d  test    eax, eax
0x1800ceb8f  jns     short loc_1800CEBB1
0x1800ceb91  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800ceb96  mov     [rsp+268h+var_15C], eax
0x1800ceb9d  lea     rdx, _TI1J; pThrowInfo
0x1800ceba4  lea     rcx, [rsp+268h+var_15C]; pExceptionObject
0x1800cebac  call    _CxxThrowException_0
0x1800cebb1  mov     word ptr [rsp+268h+var_21C], cx
0x1800cebb6  mov     [rsp+268h+var_1A8], r14
0x1800cebbe  lea     rdx, [rsp+268h+var_1A8]
0x1800cebc6  mov     rcx, [rsp+268h+var_1A0]
0x1800cebce  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x1800cebd3  mov     [rsp+268h+var_220], eax
0x1800cebd7  mov     [rsp+268h+var_220], eax
0x1800cebdb  mov     ecx, 0ABh
0x1800cebe0  test    eax, eax
0x1800cebe2  jns     short loc_1800CEC04
0x1800cebe4  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800cebe9  mov     [rsp+268h+var_158], eax
0x1800cebf0  lea     rdx, _TI1J; pThrowInfo
0x1800cebf7  lea     rcx, [rsp+268h+var_158]; pExceptionObject
0x1800cebff  call    _CxxThrowException_0
0x1800cec04  mov     word ptr [rsp+268h+var_21C], cx
0x1800cec09  mov     [rsp+268h+var_220], eax
0x1800cec0d  mov     r8, [rsp+268h+var_1A8]
0x1800cec15  mov     eax, 0ACh
0x1800cec1a  test    r8, r8
0x1800cec1d  jnz     short loc_1800CEC48
0x1800cec1f  mov     ecx, 80070490h
0x1800cec24  mov     [rsp+268h+var_220], ecx
0x1800cec28  mov     word ptr [rsp+268h+var_21C+2], ax
0x1800cec2d  mov     [rsp+268h+var_154], ecx
0x1800cec34  lea     rdx, _TI1J; pThrowInfo
0x1800cec3b  lea     rcx, [rsp+268h+var_154]; pExceptionObject
0x1800cec43  call    _CxxThrowException_0
0x1800cec48  mov     [rsp+268h+var_220], r14d
0x1800cec4d  mov     word ptr [rsp+268h+var_21C], ax
0x1800cec52  test    rsi, rsi
0x1800cec55  jz      short loc_1800CEC61
0x1800cec57  mov     rcx, rsi
0x1800cec5a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cec5f  jmp     short loc_1800CEC64
0x1800cec61  mov     rax, r14
0x1800cec64  mov     r9, rax
0x1800cec67  mov     rdx, [rsp+268h+var_1D0]
0x1800cec6f  lea     rcx, [rsp+268h+var_1C0]
0x1800cec77  call    GetWebAccount
0x1800cec7c  nop
0x1800cec7d  mov     [rsp+268h+var_1D8], r14
0x1800cec85  mov     rsi, [rsp+268h+var_128]
0x1800cec8d  mov     rax, [rsi]
0x1800cec90  mov     rax, [rax+38h]
0x1800cec94  mov     [rsp+268h+var_1B8], rax
0x1800cec9c  lea     rcx, [rsp+268h+var_1D8]
0x1800ceca4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ceca9  lea     rcx, [rsp+268h+var_80]
0x1800cecb1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cecb6  mov     rdi, rax
0x1800cecb9  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800cecbd  mov     rbx, r12
0x1800cecc0  inc     rbx
0x1800cecc3  cmp     [rax+rbx*2], r14w
0x1800cecc8  jnz     short loc_1800CECC0
0x1800cecca  mov     eax, 0FFFFFFFFh
0x1800ceccf  cmp     rbx, rax
0x1800cecd2  jbe     short loc_1800CECEB
0x1800cecd4  mov     ebx, eax
0x1800cecd6  xor     r9d, r9d; lpArguments
0x1800cecd9  xor     r8d, r8d; nNumberOfArguments
0x1800cecdc  lea     edx, [r9+1]; dwExceptionFlags
0x1800cece0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cece5  call    cs:__imp_RaiseException
0x1800ceceb  lea     r9, [rsp+268h+string]; string
0x1800cecf3  lea     r8, [rsp+268h+hstringHeader]; hstringHeader
0x1800cecfb  mov     edx, ebx; length
0x1800cecfd  mov     rcx, rdi; sourceString
0x1800ced00  call    cs:__imp_WindowsCreateStringReference
0x1800ced06  mov     rbx, [rsp+268h+string]
0x1800ced0e  lea     rcx, [rsp+268h+var_C0]; string
0x1800ced16  call    ??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[1])
0x1800ced1b  lea     rcx, [rsp+268h+var_1D8]
0x1800ced23  mov     [rsp+268h+var_240], rcx
0x1800ced28  mov     dword ptr [rsp+268h+var_248], r14d
0x1800ced2d  mov     r9, rbx
0x1800ced30  mov     r8, [rax]
0x1800ced33  mov     rdx, [rsp+268h+var_1A8]
0x1800ced3b  mov     rcx, rsi
0x1800ced3e  mov     rax, [rsp+268h+var_1B8]
0x1800ced46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced4b  mov     [rsp+268h+var_220], eax
0x1800ced4f  mov     [rsp+268h+var_220], eax
0x1800ced53  mov     ecx, 0BCh
0x1800ced58  test    eax, eax
0x1800ced5a  jns     short loc_1800CED7C
0x1800ced5c  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800ced61  mov     [rsp+268h+var_14C], eax
0x1800ced68  lea     rdx, _TI1J; pThrowInfo
0x1800ced6f  lea     rcx, [rsp+268h+var_14C]; pExceptionObject
0x1800ced77  call    _CxxThrowException_0
0x1800ced7c  mov     word ptr [rsp+268h+var_21C], cx
0x1800ced81  mov     [rsp+268h+var_228], r14b
0x1800ced86  mov     [rsp+268h+var_1E8], r14
0x1800ced8e  mov     rcx, [rsp+268h+var_1D8]
0x1800ced96  mov     rax, [rcx]
0x1800ced99  lea     rdx, [rsp+268h+var_1E8]
0x1800ceda1  mov     rax, [rax+50h]
0x1800ceda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cedaa  mov     [rsp+268h+var_220], eax
0x1800cedae  mov     [rsp+268h+var_220], eax
0x1800cedb2  mov     ecx, 0C0h
0x1800cedb7  test    eax, eax
0x1800cedb9  jns     short loc_1800CEDDB
0x1800cedbb  mov     word ptr [rsp+268h+var_21C+2], cx
0x1800cedc0  mov     [rsp+268h+var_148], eax
0x1800cedc7  lea     rdx, _TI1J; pThrowInfo
0x1800cedce  lea     rcx, [rsp+268h+var_148]; pExceptionObject
0x1800cedd6  call    _CxxThrowException_0
0x1800ceddb  mov     word ptr [rsp+268h+var_21C], cx
0x1800cede0  mov     rsi, [rsp+268h+var_1E8]
0x1800cede8  mov     rax, [rsi]
0x1800cedeb  mov     rax, [rax+50h]
0x1800cedef  mov     [rsp+268h+var_1B8], rax
0x1800cedf7  lea     rcx, [rsp+268h+var_A0]
0x1800cedff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cee04  mov     rdi, rax
0x1800cee07  mov     rbx, r12
0x1800cee0a  inc     rbx
0x1800cee0d  cmp     [rax+rbx*2], r14w
0x1800cee12  jnz     short loc_1800CEE0A
0x1800cee14  mov     eax, 0FFFFFFFFh
0x1800cee19  cmp     rbx, rax
0x1800cee1c  jbe     short loc_1800CEE35
0x1800cee1e  mov     ebx, eax
0x1800cee20  xor     r9d, r9d; lpArguments
0x1800cee23  xor     r8d, r8d; nNumberOfArguments
0x1800cee26  lea     edx, [r9+1]; dwExceptionFlags
0x1800cee2a  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cee2f  call    cs:__imp_RaiseException
0x1800cee35  lea     r9, [rsp+268h+string]; string
0x1800cee3d  lea     r8, [rsp+268h+hstringHeader]; hstringHeader
0x1800cee45  mov     edx, ebx; length
0x1800cee47  mov     rcx, rdi; sourceString
0x1800cee4a  call    cs:__imp_WindowsCreateStringReference
0x1800cee50  mov     rbx, [rsp+268h+string]
0x1800cee58  lea     rcx, [rsp+268h+var_C0]; string
0x1800cee60  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x1800cee65  lea     r9, [rsp+268h+var_228]
0x1800cee6a  mov     r8, rbx
0x1800cee6d  mov     rdx, [rax]
0x1800cee70  mov     rcx, rsi
0x1800cee73  mov     rax, [rsp+268h+var_1B8]
0x1800cee7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee80  mov     [rsp+268h+var_220], eax
0x1800cee84  mov     [rsp+268h+var_220], eax
0x1800cee88  mov     ecx, 0C1h
0x1800cee8d  test    eax, eax
0x1800cee8f  jns     short loc_1800CEEB1
0x1800cee91  mov     word ptr [rsp+268h+var_21C+2], cx
  ... truncated ...
```
