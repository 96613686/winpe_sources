# CloudFiles::UI::Toast::ProgressToast::GetNotificationData(float,unsigned __int64,ushort const *,CF_ABORT_KEY__ * const,uint)

- ea: `0x18023e048`
- end: `0x18023ec9a`
- name: `?GetNotificationData@ProgressToast@Toast@UI@CloudFiles@@YA?AV?$com_ptr_t@UINotificationData@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@wil@@M_KPEBGQEAUCF_ABORT_KEY__@@I@Z`
- size: `3154`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180391fc8`
- `0x18039c7d8`

## callees

- `0x180019e48`
- `0x18003a8e8`
- `0x180079ccc`
- `0x18007dcf0`
- `0x1800fa660`
- `0x1801356e4`
- `0x18015f938`
- `0x180174270`
- `0x1801ec1e0`
- `0x18023e048`
- `0x18023eca0`
- `0x18023ee10`
- `0x180356718`
- `0x180356c84`
- `0x18036790c`
- `0x18036a5b8`
- `0x1803747ec`
- `0x1803b1f60`
- `0x1803b243c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023e3be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023ebf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023ec12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023e3be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023ebf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023ec12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e9ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023eac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023eaff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023e9ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023eac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18023eaff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18023e0ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18023e0ef`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeW` at `0x18023e242`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeW` at `0x18023e242`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
unsigned __int64 __fastcall CloudFiles::UI::Toast::ProgressToast::GetNotificationData(
        const WCHAR *a1,
        float a2,
        LONGLONG a3,
        __int64 a4,
        _QWORD *a5,
        unsigned int a6)
{
  float v8; // xmm6_4
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int ActivationFactory; // eax
  __int64 *v13; // rbx
  void *v14; // rax
  __int64 v15; // rax
  __int64 *v16; // rdi
  int v17; // esi
  unsigned __int64 v18; // r14
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // rdi
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  int v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  WCHAR *v27; // rsi
  unsigned int v28; // eax
  UINT32 v29; // edx
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  HSTRING v33; // rdi
  HRESULT v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  int v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  __int64 *v40; // r15
  int v41; // eax
  __int64 (__fastcall *v42)(__int64 *, HSTRING, __int64, _BYTE *); // rsi
  __int64 v43; // rdi
  int v44; // eax
  int v45; // eax
  __int64 (__fastcall *v46)(__int64 *, HSTRING, __int64, _BYTE *); // rsi
  __int64 v47; // rdi
  int v48; // eax
  __int64 v49; // rsi
  unsigned __int64 v50; // rdi
  const WCHAR *v51; // r12
  unsigned int v52; // eax
  UINT32 v53; // edx
  HRESULT v54; // eax
  int v55; // edx
  unsigned int v56; // r8d
  HSTRING v57; // rdi
  HRESULT v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  int v61; // eax
  int v62; // edx
  unsigned int v63; // r8d
  __int64 v64; // rsi
  unsigned __int64 v65; // rdi
  const WCHAR *v66; // r12
  unsigned int v67; // eax
  UINT32 v68; // edx
  HRESULT v69; // eax
  int v70; // edx
  unsigned int v71; // r8d
  HSTRING v72; // rdi
  HRESULT v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  int v76; // eax
  __int64 v77; // r13
  unsigned int v78; // r8d
  const WCHAR *p_sourceString; // r12
  unsigned __int64 v80; // rdi
  unsigned int v81; // eax
  UINT32 v82; // edx
  HRESULT v83; // eax
  int v84; // edx
  unsigned int v85; // r8d
  HSTRING v86; // rdi
  HRESULT v87; // eax
  int v88; // edx
  unsigned int v89; // r8d
  int v90; // eax
  _QWORD *v91; // r12
  __int64 v92; // r15
  int v93; // edx
  unsigned int v94; // r8d
  const WCHAR *v95; // rsi
  unsigned __int64 v96; // rdi
  unsigned int v97; // eax
  UINT32 v98; // edx
  HRESULT v99; // eax
  int v100; // edx
  unsigned int v101; // r8d
  HSTRING v102; // rdi
  HRESULT v103; // eax
  int v104; // edx
  unsigned int v105; // r8d
  int v106; // eax
  __int64 v107; // r15
  int v108; // edx
  unsigned int v109; // r8d
  const WCHAR *v110; // rsi
  unsigned int v111; // eax
  UINT32 v112; // edx
  HRESULT v113; // eax
  int v114; // edx
  unsigned int v115; // r8d
  HSTRING v116; // rdi
  HRESULT v117; // eax
  int v118; // edx
  unsigned int v119; // r8d
  int v120; // eax
  __int64 v121; // r15
  int v122; // edx
  unsigned int v123; // r8d
  unsigned int v124; // eax
  UINT32 v125; // edx
  HRESULT v126; // eax
  int v127; // edx
  unsigned int v128; // r8d
  HSTRING v129; // rdi
  HRESULT v130; // eax
  int v131; // edx
  unsigned int v132; // r8d
  int v133; // eax
  __int64 v134; // rcx
  __int64 (__fastcall *v135)(__int64, _QWORD, unsigned __int64); // r9
  int v136; // eax
  int v138; // [rsp+28h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-B0h] BYREF
  PCWSTR sourceString; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v142; // [rsp+68h] [rbp-A0h]
  __int64 v143; // [rsp+70h] [rbp-98h]
  unsigned __int64 v144; // [rsp+78h] [rbp-90h]
  HSTRING_HEADER v145; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v146; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v147; // [rsp+A0h] [rbp-68h]
  PCWSTR v148; // [rsp+A8h] [rbp-60h] BYREF
  PCWSTR v149[3]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 *v150; // [rsp+C8h] [rbp-40h]
  _QWORD *v151; // [rsp+D0h] [rbp-38h]
  const WCHAR *v152; // [rsp+D8h] [rbp-30h]
  PCWSTR v153[4]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v154[8]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v155; // [rsp+108h] [rbp+0h] BYREF
  WCHAR pszBuf[264]; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+390h] [rbp+288h]

  v8 = a2;
  v152 = a1;
  v153[3] = a1;
  v151 = a5;
  v147 = a6;
  v155 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.UI.Notifications.NotificationData", 0x29u, &hstringHeader, &string);
  if ( v9 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
  ActivationFactory = RoGetActivationFactory(string, &GUID_23c1e33a_1c10_46fb_8040_dec384621cf8, &v155);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v138);
  v13 = 0;
  v150 = 0;
  v14 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v14 )
  {
    v16 = 0;
    goto LABEL_10;
  }
  v15 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(v14);
  v16 = (__int64 *)v15;
  if ( !v15 )
  {
LABEL_10:
    v17 = -2147024882;
    goto LABEL_11;
  }
  v17 = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(v15 + 144));
  if ( v17 >= 0 )
  {
    *((_BYTE *)v16 + 152) = 1;
    v13 = v16;
    v150 = v16;
    v16 = 0;
  }
LABEL_11:
  if ( v16 )
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v17,
      v138);
  memset(v149, 0, sizeof(v149));
  v18 = -1;
  if ( a2 >= 0.0 )
  {
    v8 = fminf(a2, 1.0);
    v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            v149,
            L"%f",
            v8);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v20,
        v138);
  }
  else
  {
    v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            v149,
            L"indeterminate",
            -1);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v19,
        v138);
  }
  StrFormatByteSizeW(a3, pszBuf, 0x104u);
  memset(v153, 0, 24);
  v21 = (unsigned __int64)&_ImageBase;
  v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResFormat(
          v153,
          &_ImageBase,
          1204,
          pszBuf);
  v23 = retaddr;
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v22,
      v138);
  v154[0] = 0;
  if ( a6 > 1 )
  {
    sourceString = 0;
    v142 = 0;
    v143 = 0;
    v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResFormat(
            &sourceString,
            &_ImageBase,
            1207,
            a6);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v24,
        v138);
    a4 = *v13;
    string = 0;
    v27 = (WCHAR *)sourceString;
    v21 = -1;
    do
      ++v21;
    while ( sourceString[v21] );
    if ( v21 <= 0xFFFFFFFF )
    {
      v28 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
      v29 = v28 - 1;
      if ( (unsigned int)v21 < v28 )
        v29 = v21;
      v30 = WindowsCreateStringReference(v27, v29, &hstringHeader, &string);
      if ( v30 < 0 )
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
      v33 = string;
      v146 = 0;
      v34 = WindowsCreateStringReference(L"progressStatus", 0xEu, &v145, &v146);
      if ( v34 < 0 )
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
      v37 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(a4 + 80))(v13, v146, v33, v154);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
          (const char *)(unsigned int)v37,
          v138);
      if ( v27 )
        CoTaskMemFree(v27);
      v40 = v13;
      goto LABEL_53;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v25, v26);
  }
  if ( v8 < 1.0 )
  {
    if ( !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v23);
    sourceString = 0;
    v142 = 0;
    v143 = 0;
    v45 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResFormat(
            &sourceString,
            v21,
            1202,
            a4);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v45,
        v138);
    v40 = v13;
    v46 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v13 + 80);
    v148 = sourceString;
    v47 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v145, &v148) + 24);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"progressStatus", 0xFu, 0xEu);
    v48 = v46(v13, string, v47, v154);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v48,
        v138);
  }
  else
  {
    sourceString = 0;
    v142 = 0;
    v143 = 0;
    v41 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
            &sourceString,
            v21,
            1206);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v41,
        v138);
    v40 = v13;
    v42 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, _BYTE *))(*v13 + 80);
    v148 = sourceString;
    v43 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v145, &v148) + 24);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"progressStatus", 0xFu, 0xEu);
    v44 = v42(v13, string, v43, v154);
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
        (const char *)(unsigned int)v44,
        v138);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
LABEL_53:
  v49 = *v40;
  string = 0;
  v50 = -1;
  v51 = v149[0];
  do
    ++v50;
  while ( v149[0][v50] );
  if ( v50 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v38, v39);
    JUMPOUT(0x18023EC99LL);
  }
  v52 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v50);
  v53 = v52 - 1;
  if ( (unsigned int)v50 < v52 )
    v53 = v50;
  v54 = WindowsCreateStringReference(v51, v53, &hstringHeader, &string);
  if ( v54 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v54, v55, v56);
  v57 = string;
  v146 = 0;
  v58 = WindowsCreateStringReference(L"progressValue", 0xDu, &v145, &v146);
  if ( v58 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
  v61 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v49 + 80))(v40, v146, v57, v154);
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v61,
      v138);
  v64 = *v40;
  string = 0;
  v65 = -1;
  v66 = v153[0];
  do
    ++v65;
  while ( v153[0][v65] );
  if ( v65 > 0xFFFFFFFF )
  {
LABEL_151:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v62, v63);
    __debugbreak();
  }
  v67 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v65);
  v68 = v67 - 1;
  if ( (unsigned int)v65 < v67 )
    v68 = v65;
  v69 = WindowsCreateStringReference(v66, v68, &hstringHeader, &string);
  if ( v69 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v69, v70, v71);
  v72 = string;
  v146 = 0;
  v73 = WindowsCreateStringReference(L"progressValueString", 0x13u, &v145, &v146);
  if ( v73 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
  v76 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v64 + 80))(v40, v146, v72, v154);
  if ( v76 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v76,
      v138);
  v77 = *v40;
  std::_Integral_to_string<unsigned short,unsigned int>(&sourceString, v147);
  p_sourceString = (const WCHAR *)&sourceString;
  if ( v144 > 7 )
    p_sourceString = sourceString;
  string = 0;
  v80 = -1;
  do
    ++v80;
  while ( p_sourceString[v80] );
  if ( v80 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, 0, v78);
    goto LABEL_151;
  }
  v81 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v80);
  v82 = v81 - 1;
  if ( (unsigned int)v80 < v81 )
    v82 = v80;
  v83 = WindowsCreateStringReference(p_sourceString, v82, &hstringHeader, &string);
  if ( v83 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v83, v84, v85);
  v86 = string;
  v146 = 0;
  v87 = WindowsCreateStringReference(L"fileCount", 9u, &v145, &v146);
  if ( v87 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v87, v88, v89);
  v90 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v77 + 80))(v40, v146, v86, v154);
  if ( v90 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v90,
      v138);
  v146 = 0;
  string = 0;
  if ( v144 > 7 )
    std::_Deallocate<16>(sourceString, 2 * v144 + 2);
  v91 = v151;
  if ( !v151 )
    goto LABEL_136;
  v92 = *v13;
  std::_Integral_to_string<unsigned short,__int64>(&sourceString, *v151);
  v95 = (const WCHAR *)&sourceString;
  if ( v144 > 7 )
    v95 = sourceString;
  v146 = 0;
  v96 = -1;
  do
    ++v96;
  while ( v95[v96] );
  if ( v96 > 0xFFFFFFFF )
  {
LABEL_140:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v93, v94);
    goto LABEL_141;
  }
  v97 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v96);
  v98 = v97 - 1;
  if ( (unsigned int)v96 < v97 )
    v98 = v96;
  v99 = WindowsCreateStringReference(v95, v98, &v145, &v146);
  if ( v99 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v99, v100, v101);
  v102 = v146;
  string = 0;
  v103 = WindowsCreateStringReference(L"abortKeyArg0", 0xCu, &hstringHeader, &string);
  if ( v103 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v103, v104, v105);
  v106 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v92 + 80))(v13, string, v102, v154);
  if ( v106 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v106,
      v138);
  string = 0;
  v146 = 0;
  if ( v144 > 7 )
    std::_Deallocate<16>(sourceString, 2 * v144 + 2);
  v107 = *v13;
  std::_Integral_to_string<unsigned short,__int64>(&sourceString, v91[1]);
  v110 = (const WCHAR *)&sourceString;
  if ( v144 > 7 )
    v110 = sourceString;
  v146 = 0;
  v96 = -1;
  do
    ++v96;
  while ( v110[v96] );
  if ( v96 > 0xFFFFFFFF )
  {
LABEL_139:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v108, v109);
    goto LABEL_140;
  }
  v111 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v96);
  v112 = v111 - 1;
  if ( (unsigned int)v96 < v111 )
    v112 = v96;
  v113 = WindowsCreateStringReference(v110, v112, &v145, &v146);
  if ( v113 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v113, v114, v115);
  v116 = v146;
  string = 0;
  v117 = WindowsCreateStringReference(L"abortKeyArg1", 0xCu, &hstringHeader, &string);
  if ( v117 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v117, v118, v119);
  v120 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v107 + 80))(v13, string, v116, v154);
  if ( v120 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v120,
      v138);
  string = 0;
  v146 = 0;
  if ( v144 > 7 )
    std::_Deallocate<16>(sourceString, 2 * v144 + 2);
  v121 = *v13;
  std::_Integral_to_string<unsigned short,__int64>(&sourceString, v91[2]);
  v96 = (unsigned __int64)&sourceString;
  if ( v144 > 7 )
    v96 = (unsigned __int64)sourceString;
  v146 = 0;
  do
    ++v18;
  while ( *(_WORD *)(v96 + 2 * v18) );
  if ( v18 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v122, v123);
    goto LABEL_139;
  }
  v124 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v18);
  v125 = v124 - 1;
  if ( (unsigned int)v18 < v124 )
    v125 = v18;
  v126 = WindowsCreateStringReference((PCWSTR)v96, v125, &v145, &v146);
  if ( v126 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v126, v127, v128);
  v129 = v146;
  string = 0;
  v130 = WindowsCreateStringReference(L"abortKeyArg2", 0xCu, &hstringHeader, &string);
  if ( v130 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v130, v131, v132);
  v133 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v121 + 80))(v13, string, v129, v154);
  if ( v133 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v133,
      v138);
  string = 0;
  v146 = 0;
  if ( v144 > 7 )
    std::_Deallocate<16>(sourceString, 2 * v144 + 2);
LABEL_136:
  v96 = (unsigned __int64)v152;
  *(_QWORD *)v152 = 0;
  v134 = v155;
  v135 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64))(*(_QWORD *)v155 + 56LL);
  *(_QWORD *)v96 = 0;
  v136 = v135(v134, (unsigned __int64)(v13 + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64), v96);
  if ( v136 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\cloudfilestoasts.cpp",
      (const char *)(unsigned int)v136,
      v138);
LABEL_141:
  if ( v153[0] )
    CoTaskMemFree((LPVOID)v153[0]);
  if ( v149[0] )
    CoTaskMemFree((LPVOID)v149[0]);
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  if ( v155 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v155 + 16LL))(v155);
  return v96;
}

```

## disassembly

```asm
0x18023e048  mov     rax, rsp
0x18023e04b  push    rbp
0x18023e04c  push    rbx
0x18023e04d  push    rsi
0x18023e04e  push    rdi
0x18023e04f  push    r12
0x18023e051  push    r13
0x18023e053  push    r14
0x18023e055  push    r15
0x18023e057  lea     rbp, [rax-288h]
0x18023e05e  sub     rsp, 348h
0x18023e065  movaps  xmmword ptr [rax-58h], xmm6
0x18023e069  mov     rax, cs:__security_cookie
0x18023e070  xor     rax, rsp
0x18023e073  mov     [rbp+280h+var_60], rax
0x18023e07a  mov     r15, r9
0x18023e07d  mov     r12, r8
0x18023e080  movaps  xmm6, xmm1
0x18023e083  mov     [rbp+280h+var_2B0], rcx
0x18023e087  mov     [rbp+280h+var_290], rcx
0x18023e08b  mov     rax, [rbp+280h+arg_20]
0x18023e092  mov     [rbp+280h+var_2B8], rax
0x18023e096  mov     r13d, [rbp+280h+arg_28]
0x18023e09d  mov     [rbp+280h+var_2E8], r13d
0x18023e0a1  xor     r14d, r14d
0x18023e0a4  mov     dword ptr [rsp+380h+var_350], r14d
0x18023e0a9  mov     [rbp+280h+var_280], r14
0x18023e0ad  mov     [rsp+380h+string], r14
0x18023e0b2  lea     r9, [rsp+380h+string]; string
0x18023e0b7  lea     r8, [rsp+380h+hstringHeader]; hstringHeader
0x18023e0bc  lea     edx, [r14+29h]; length
0x18023e0c0  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_NotificationData@@3QBGB; "Windows.UI.Notifications.NotificationDa"...
0x18023e0c7  call    cs:__imp_WindowsCreateStringReference
0x18023e0ce  nop     dword ptr [rax+rax+00h]
0x18023e0d3  test    eax, eax
0x18023e0d5  jns     short loc_18023E0DF
0x18023e0d7  mov     ecx, eax; this
0x18023e0d9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18023e0de  nop
0x18023e0df  lea     r8, [rbp+280h+var_280]
0x18023e0e3  lea     rdx, _GUID_23c1e33a_1c10_46fb_8040_dec384621cf8
0x18023e0ea  mov     rcx, [rsp+380h+string]
0x18023e0ef  call    cs:__imp_RoGetActivationFactory
0x18023e0f6  nop     dword ptr [rax+rax+00h]
0x18023e0fb  mov     rcx, [rbp+288h]; this
0x18023e102  test    eax, eax
0x18023e104  jns     short loc_18023E11B
0x18023e106  mov     r9d, eax; char *
0x18023e109  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e110  mov     edx, 160h; void *
0x18023e115  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e11b  mov     rbx, r14
0x18023e11e  mov     [rbp+280h+var_2C0], rbx
0x18023e122  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18023e129  mov     ecx, 0A0h; unsigned __int64
0x18023e12e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18023e133  test    rax, rax
0x18023e136  jz      short loc_18023E16D
0x18023e138  mov     rcx, rax
0x18023e13b  call    ??0?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultHash@PEAUHSTRING__@@@1234@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission)
0x18023e140  mov     rdi, rax
0x18023e143  test    rax, rax
0x18023e146  jz      short loc_18023E170
0x18023e148  lea     rcx, [rax+90h]; this
0x18023e14f  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18023e154  mov     esi, eax
0x18023e156  test    eax, eax
0x18023e158  js      short loc_18023E175
0x18023e15a  mov     byte ptr [rdi+98h], 1
0x18023e161  mov     rbx, rdi
0x18023e164  mov     [rbp+280h+var_2C0], rbx
0x18023e168  mov     rdi, r14
0x18023e16b  jmp     short loc_18023E175
0x18023e16d  mov     rdi, r14
0x18023e170  mov     esi, 8007000Eh
0x18023e175  test    rdi, rdi
0x18023e178  jz      short loc_18023E18A
0x18023e17a  mov     rax, [rdi]
0x18023e17d  mov     rcx, rdi
0x18023e180  mov     rax, [rax+10h]
0x18023e184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023e189  nop
0x18023e18a  mov     rcx, [rbp+288h]; this
0x18023e191  test    esi, esi
0x18023e193  jns     short loc_18023E1AA
0x18023e195  mov     r9d, esi; char *
0x18023e198  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e19f  mov     edx, 163h; void *
0x18023e1a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e1aa  mov     [rbp+280h+var_2D8], r14
0x18023e1ae  mov     [rbp+280h+var_2D0], r14
0x18023e1b2  mov     [rbp+280h+var_2C8], r14
0x18023e1b6  xorps   xmm0, xmm0
0x18023e1b9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18023e1bd  lea     rcx, [rbp+280h+var_2D8]
0x18023e1c1  comiss  xmm0, xmm6
0x18023e1c4  jbe     short loc_18023E1F5
0x18023e1c6  mov     r8, r14
0x18023e1c9  lea     rdx, aIndeterminate; "indeterminate"
0x18023e1d0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18023e1d5  mov     rcx, [rbp+288h]; this
0x18023e1dc  test    eax, eax
0x18023e1de  jns     short loc_18023E235
0x18023e1e0  mov     r9d, eax; char *
0x18023e1e3  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e1ea  mov     edx, 169h; void *
0x18023e1ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e1f5  minss   xmm6, cs:__real@3f800000
0x18023e1fd  xorps   xmm2, xmm2
0x18023e200  cvtss2sd xmm2, xmm6
0x18023e204  movq    r8, xmm2
0x18023e209  lea     rdx, asc_180729688; "%f"
0x18023e210  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18023e215  mov     rcx, [rbp+288h]; this
0x18023e21c  test    eax, eax
0x18023e21e  jns     short loc_18023E235
0x18023e220  mov     r9d, eax; char *
0x18023e223  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e22a  mov     edx, 16Eh; void *
0x18023e22f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e235  mov     r8d, 104h; cchBuf
0x18023e23b  lea     rdx, [rbp+280h+pszBuf]; pszBuf
0x18023e23f  mov     rcx, r12; qdw
0x18023e242  call    cs:__imp_StrFormatByteSizeW
0x18023e249  nop     dword ptr [rax+rax+00h]
0x18023e24e  xor     r12d, r12d
0x18023e251  mov     [rbp+280h+var_2A8], r12
0x18023e255  mov     [rbp+280h+var_2A0], r12
0x18023e259  mov     [rbp+280h+var_298], r12
0x18023e25d  lea     r9, [rbp+280h+pszBuf]
0x18023e261  mov     r8d, 4B4h
0x18023e267  lea     rdi, __ImageBase
0x18023e26e  mov     rdx, rdi
0x18023e271  lea     rcx, [rbp+280h+var_2A8]
0x18023e275  call    ?InitializeResFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResFormat(HINSTANCE__ *,int,...)
0x18023e27a  mov     rcx, [rbp+288h]; this
0x18023e281  test    eax, eax
0x18023e283  jns     short loc_18023E29A
0x18023e285  mov     r9d, eax; char *
0x18023e288  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e28f  mov     edx, 179h; void *
0x18023e294  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e29a  mov     [rbp+280h+var_288], r12b
0x18023e29e  cmp     r13d, 1
0x18023e2a2  jbe     loc_18023E3DD
0x18023e2a8  mov     [rsp+380h+sourceString], r12
0x18023e2ad  mov     [rsp+380h+var_320], r12
0x18023e2b2  mov     [rsp+380h+var_318], r12
0x18023e2b7  mov     r9d, r13d
0x18023e2ba  mov     r8d, 4B7h
0x18023e2c0  mov     rdx, rdi
0x18023e2c3  lea     rcx, [rsp+380h+sourceString]
0x18023e2c8  call    ?InitializeResFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResFormat(HINSTANCE__ *,int,...)
0x18023e2cd  mov     rcx, [rbp+288h]; this
0x18023e2d4  test    eax, eax
0x18023e2d6  jns     short loc_18023E2ED
0x18023e2d8  mov     r9d, eax; char *
0x18023e2db  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e2e2  mov     edx, 183h; void *
0x18023e2e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e2ed  mov     r15, [rbx]
0x18023e2f0  mov     [rsp+380h+string], r12
0x18023e2f5  mov     rsi, [rsp+380h+sourceString]
0x18023e2fa  mov     rdi, r14
0x18023e2fd  inc     rdi
0x18023e300  cmp     [rsi+rdi*2], r12w
0x18023e305  jnz     short loc_18023E2FD
0x18023e307  mov     eax, 0FFFFFFFFh
0x18023e30c  cmp     rdi, rax
0x18023e30f  ja      loc_18023E3D2
0x18023e315  mov     ecx, edi; unsigned int
0x18023e317  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18023e31c  lea     edx, [rax-1]
0x18023e31f  cmp     edi, eax
0x18023e321  cmovb   edx, edi; length
0x18023e324  lea     r9, [rsp+380h+string]; string
0x18023e329  lea     r8, [rsp+380h+hstringHeader]; hstringHeader
0x18023e32e  mov     rcx, rsi; sourceString
0x18023e331  call    cs:__imp_WindowsCreateStringReference
0x18023e338  nop     dword ptr [rax+rax+00h]
0x18023e33d  test    eax, eax
0x18023e33f  jns     short loc_18023E349
0x18023e341  mov     ecx, eax; this
0x18023e343  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18023e348  nop
0x18023e349  mov     rdi, [rsp+380h+string]
0x18023e34e  mov     [rbp+280h+var_2F0], r12
0x18023e352  lea     r9, [rbp+280h+var_2F0]; string
0x18023e356  lea     r8, [rsp+380h+var_308]; hstringHeader
0x18023e35b  mov     edx, 0Eh; length
0x18023e360  lea     rcx, aProgressstatus; "progressStatus"
0x18023e367  call    cs:__imp_WindowsCreateStringReference
0x18023e36e  nop     dword ptr [rax+rax+00h]
0x18023e373  test    eax, eax
0x18023e375  jns     short loc_18023E37F
0x18023e377  mov     ecx, eax; this
0x18023e379  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18023e37e  nop
0x18023e37f  lea     r9, [rbp+280h+var_288]
0x18023e383  mov     r8, rdi
0x18023e386  mov     rdx, [rbp+280h+var_2F0]
0x18023e38a  mov     rcx, rbx
0x18023e38d  mov     rax, [r15+50h]
0x18023e391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023e396  mov     rcx, [rbp+288h]; this
0x18023e39d  test    eax, eax
0x18023e39f  jns     short loc_18023E3B6
0x18023e3a1  mov     r9d, eax; char *
0x18023e3a4  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e3ab  mov     edx, 185h; void *
0x18023e3b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e3b6  test    rsi, rsi
0x18023e3b9  jz      short loc_18023E3CA
0x18023e3bb  mov     rcx, rsi; pv
0x18023e3be  call    cs:__imp_CoTaskMemFree
0x18023e3c5  nop     dword ptr [rax+rax+00h]
0x18023e3ca  mov     r15, rbx
0x18023e3cd  jmp     loc_18023E586
0x18023e3d2  mov     ecx, 80070216h; this
0x18023e3d7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18023e3dc  nop
0x18023e3dd  comiss  xmm6, cs:__real@3f800000
0x18023e3e4  jb      loc_18023E4AF
0x18023e3ea  mov     [rsp+380h+sourceString], r12
0x18023e3ef  mov     [rsp+380h+var_320], r12
0x18023e3f4  mov     [rsp+380h+var_318], r12
0x18023e3f9  mov     r8d, 4B6h
0x18023e3ff  mov     rdx, rdi
0x18023e402  lea     rcx, [rsp+380h+sourceString]
0x18023e407  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18023e40c  mov     rcx, [rbp+288h]; this
0x18023e413  test    eax, eax
0x18023e415  jns     short loc_18023E42C
0x18023e417  mov     r9d, eax; char *
0x18023e41a  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e421  mov     edx, 18Bh; void *
0x18023e426  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e42c  mov     r15, rbx
0x18023e42f  mov     rax, [rbx]
0x18023e432  mov     rsi, [rax+50h]
0x18023e436  mov     rax, [rsp+380h+sourceString]
0x18023e43b  mov     [rbp+280h+var_2E0], rax
0x18023e43f  lea     rdx, [rbp+280h+var_2E0]
0x18023e443  lea     rcx, [rsp+380h+var_308]
0x18023e448  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18023e44d  nop
0x18023e44e  mov     rdi, [rax+18h]
0x18023e452  mov     [rsp+380h+string], r12
0x18023e457  mov     r9d, 0Eh; unsigned int
0x18023e45d  lea     r8d, [r9+1]; unsigned int
0x18023e461  lea     rdx, aProgressstatus; "progressStatus"
0x18023e468  lea     rcx, [rsp+380h+hstringHeader]; hstringHeader
0x18023e46d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18023e472  nop
0x18023e473  lea     r9, [rbp+280h+var_288]
0x18023e477  mov     r8, rdi
0x18023e47a  mov     rdx, [rsp+380h+string]
0x18023e47f  mov     rcx, rbx
0x18023e482  mov     rax, rsi
0x18023e485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023e48a  mov     rcx, [rbp+288h]; this
0x18023e491  test    eax, eax
0x18023e493  jns     short loc_18023E4AA
0x18023e495  mov     r9d, eax; char *
0x18023e498  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e49f  mov     edx, 18Ch; void *
0x18023e4a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e4aa  jmp     loc_18023E57C
0x18023e4af  test    r15, r15
0x18023e4b2  jnz     short loc_18023E4B9
0x18023e4b4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "currentDownloadingFileName != nullptr")
0x18023e4b9  mov     [rsp+380h+sourceString], r12
0x18023e4be  mov     [rsp+380h+var_320], r12
0x18023e4c3  mov     [rsp+380h+var_318], r12
0x18023e4c8  mov     r9, r15
0x18023e4cb  mov     r8d, 4B2h
0x18023e4d1  mov     rdx, rdi
0x18023e4d4  lea     rcx, [rsp+380h+sourceString]
0x18023e4d9  call    ?InitializeResFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResFormat(HINSTANCE__ *,int,...)
0x18023e4de  mov     rcx, [rbp+288h]; this
0x18023e4e5  test    eax, eax
0x18023e4e7  jns     short loc_18023E4FE
0x18023e4e9  mov     r9d, eax; char *
0x18023e4ec  lea     r8, aOnecoreuapShel_162; "onecoreuap\\shell\\windows.storage\\clo"...
0x18023e4f3  mov     edx, 198h; void *
0x18023e4f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023e4fe  mov     r15, rbx
0x18023e501  mov     rax, [rbx]
0x18023e504  mov     rsi, [rax+50h]
0x18023e508  mov     rax, [rsp+380h+sourceString]
0x18023e50d  mov     [rbp+280h+var_2E0], rax
0x18023e511  lea     rdx, [rbp+280h+var_2E0]
0x18023e515  lea     rcx, [rsp+380h+var_308]
0x18023e51a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18023e51f  nop
0x18023e520  mov     rdi, [rax+18h]
0x18023e524  mov     [rsp+380h+string], r12
0x18023e529  mov     r9d, 0Eh; unsigned int
0x18023e52f  lea     r8d, [r9+1]; unsigned int
0x18023e533  lea     rdx, aProgressstatus; "progressStatus"
  ... truncated ...
```
