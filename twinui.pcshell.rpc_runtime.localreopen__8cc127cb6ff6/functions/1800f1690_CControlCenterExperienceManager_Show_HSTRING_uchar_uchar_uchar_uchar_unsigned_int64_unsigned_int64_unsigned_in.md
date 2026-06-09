# CControlCenterExperienceManager::Show(HSTRING__ *,uchar,uchar,uchar,uchar,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x1800f1690`
- end: `0x1800f1d2e`
- name: `?Show@CControlCenterExperienceManager@@UEAAJPEAUHSTRING__@@EEEE_K11@Z`
- size: `1694`
- prototype: `int(CControlCenterExperienceManager *__hidden this, HSTRING, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800eecb0`
- `0x1803f0e50`

## callees

- `0x1800134f8`
- `0x18001be9c`
- `0x18001bf0c`
- `0x1800237c8`
- `0x180026e04`
- `0x18004e340`
- `0x18005d9f0`
- `0x180066030`
- `0x18008a330`
- `0x18008a6f0`
- `0x1800f1690`
- `0x1800f1d74`
- `0x1800f1dc0`
- `0x1800f39a4`
- `0x1802b6978`
- `0x1802c203c`
- `0x1802d52c0`
- `0x180356360`
- `0x18035b27c`
- `0x18039c498`
- `0x1803ef344`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f1ca6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f1cbd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f1ca6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f1cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f1925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f1a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f1925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f1a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f16db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f18b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806f33fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f16db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f18b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806f33fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1c56`

## string_xrefs

- `0x1800f191e`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CControlCenterExperienceManager::Show(
        CControlCenterExperienceManager *this,
        HSTRING a2,
        char a3,
        char a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        unsigned __int64 a9)
{
  Microsoft::WRL::Wrappers::HString *v13; // r15
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v15; // r12
  unsigned __int64 v16; // r8
  const unsigned __int16 *v17; // rdx
  char v18; // al
  const unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // rbx
  const unsigned __int16 *v21; // rdi
  __int64 v22; // rcx
  PCWSTR v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rcx
  void *v27; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64 *); // rbx
  void *v31; // rsi
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  HRESULT StringReference; // eax
  int v36; // eax
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v38)(_QWORD, GUID *, __int64 *); // rdi
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, __int64 *); // rbx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  char v53; // [rsp+60h] [rbp-A0h] BYREF
  char v54; // [rsp+68h] [rbp-98h] BYREF
  bool v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  __int64 v58; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-70h] BYREF
  void *p_pv; // [rsp+98h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  _QWORD v65[2]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v68[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v69[8]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v54 = a3;
  v53 = a4;
  v13 = (CControlCenterExperienceManager *)((char *)this + 720);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v15 = &pvData;
  if ( !StringRawBuffer )
  {
    LODWORD(v16) = 0;
    v17 = &pvData;
    goto LABEL_6;
  }
  v16 = -1;
  do
    ++v16;
  while ( StringRawBuffer[v16] );
  if ( v16 <= 0xFFFFFFFF )
  {
    v17 = StringRawBuffer;
LABEL_6:
    Microsoft::WRL::Wrappers::HString::Set(v13, v17, v16);
  }
  *((_BYTE *)this + 729) = a4 != 0;
  if ( *((_DWORD *)this + 32) == 2 || (v18 = 1, !a2) )
    v18 = 0;
  *((_BYTE *)this + 730) = v18;
  if ( a2 )
  {
    p_pv = (void *)WindowsGetStringRawBuffer(*(HSTRING *)v13, 0);
    v55 = *((_DWORD *)this + 32) == 2;
    ControlCenterUITelemetry::ControlCenterTelemetry::ShowControlCenterWithDeepLink<bool,unsigned short const *,unsigned char &,unsigned char &,unsigned char &,unsigned char &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(
      (unsigned int)&v55,
      (unsigned int)&p_pv,
      (unsigned int)&v54,
      (unsigned int)&v53,
      (__int64)&a5,
      (__int64)&a6,
      (__int64)&a7,
      (__int64)&a8,
      (__int64)&a9);
  }
  v19 = L"true";
  v20 = L"true";
  if ( !a3 )
    v20 = L"false";
  v21 = L"true";
  if ( !a5 )
    v21 = L"false";
  if ( !a6 )
    v19 = L"false";
  winrt::hstring::hstring((winrt::hstring *)&string, L"suppressAnimations");
  winrt::hstring::hstring((winrt::hstring *)&hstringHeader, v20);
  winrt::hstring::hstring((winrt::hstring *)&hstringHeader.Reserved.Reserved2[8], L"showFooter");
  winrt::hstring::hstring((winrt::hstring *)&hstringHeader.Reserved.Reserved2[16], v21);
  winrt::hstring::hstring((winrt::hstring *)v68, L"allowPageNavigation");
  winrt::hstring::hstring((winrt::hstring *)v69, v19);
  winrt::impl::make_scoped_input_iterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,std::pair<winrt::hstring const,winrt::hstring> const *>((winrt *)&pv);
  LOBYTE(v64) = 1;
  p_pv = &pv;
  v65[1] = &qword_1808D8DA8;
  _InterlockedIncrement64(&qword_1808D8DA8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory> )
  {
    winrt::impl::consume_Windows_Data_Json_IJsonObjectStatics<winrt::Windows::Data::Json::IJsonObjectStatics>::Parse(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>,
      v65,
      &pv);
    _InterlockedDecrement64(&qword_1808D8DA8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1808D8DA8);
    winrt::impl::factory_cache_entry<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>::call<_lambda_89d5cc9e848954b376ddd65d03be1168_ &>(
      v22,
      v65,
      &p_pv);
  }
  winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Data::Json::JsonObject>::ToString(v65, &p_pv);
  if ( v65[0] )
    winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(v65);
  if ( v63 )
    *v63 = 1;
  if ( !(_BYTE)v64 )
    pv = 0;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&pv);
  `eh vector destructor iterator'(
    &string,
    0x10u,
    3u,
    (void (*)(void *))winrt::Windows::UI::Xaml::Markup::XmlnsDefinition::~XmlnsDefinition);
  pv = 0;
  v63 = 0;
  v64 = 0;
  if ( p_pv )
    v15 = (const WCHAR *)*((_QWORD *)p_pv + 2);
  v23 = WindowsGetStringRawBuffer(*(HSTRING *)v13, 0);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
    &pv,
    L"%ws/%ws&%ws&%ws=%llu&%ws=%llu&%ws=%llu",
    L"ms-actioncenter:controlcenter",
    v23);
  v56 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v24 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
          string,
          &v56);
  v25 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v24,
      (int)v15);
    v26 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = pv;
    if ( !pv )
      goto LABEL_34;
    goto LABEL_33;
  }
  v57 = 0;
  v29 = v56;
  v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v56 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v31 = pv;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&string,
    (const unsigned __int16 *)pv);
  v32 = v30(v29, string, &v57);
  v25 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v32,
      (int)v15);
    v33 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
LABEL_40:
    if ( !v31 )
      goto LABEL_34;
    v27 = v31;
LABEL_33:
    CoTaskMemFree(v27);
LABEL_34:
    winrt::handle_type<winrt::impl::hstring_traits>::close(&p_pv);
    return v25;
  }
  v59 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.System.Launcher",
                      0x17u,
                      (HSTRING_HEADER *)&string,
                      (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v36 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
          &v59);
  v25 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v36,
      (int)v15);
LABEL_77:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    goto LABEL_34;
  }
  v58 = 0;
  v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  v38 = **v59;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v39 = v38(v37, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v58);
  v25 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v39,
      (int)v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    goto LABEL_77;
  }
  CSingleViewShellExperience::BoostPriority((char *)this + 88, *((_DWORD *)this + 32) == 1);
  v61 = 0;
  v40 = v58;
  v41 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v58 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v42 = v41(v40, v57, &v61);
  v25 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v42,
      (int)v15);
    v43 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v45)[2])(v45);
    }
    v46 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    goto LABEL_40;
  }
  v48 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  if ( v59 )
  {
    v59 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v50)[2])(v50);
  }
  v51 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v52 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  if ( v31 )
    CoTaskMemFree(v31);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&p_pv);
  return 0;
}

```

## disassembly

```asm
0x1800f1690  push    rbp
0x1800f1692  push    rbx
0x1800f1693  push    rsi
0x1800f1694  push    rdi
0x1800f1695  push    r12
0x1800f1697  push    r13
0x1800f1699  push    r14
0x1800f169b  push    r15
0x1800f169d  lea     rbp, [rsp-18h]
0x1800f16a2  sub     rsp, 118h
0x1800f16a9  mov     rax, cs:__security_cookie
0x1800f16b0  xor     rax, rsp
0x1800f16b3  mov     [rbp+50h+var_50], rax
0x1800f16b7  mov     dil, r9b
0x1800f16ba  mov     r13b, r8b
0x1800f16bd  mov     rbx, rdx
0x1800f16c0  mov     r14, rcx
0x1800f16c3  mov     [rsp+150h+var_E8], r8b
0x1800f16c8  mov     [rsp+150h+var_F0], r9b
0x1800f16cd  xor     esi, esi
0x1800f16cf  lea     r15, [rcx+2D0h]
0x1800f16d6  xor     edx, edx; length
0x1800f16d8  mov     rcx, rbx; string
0x1800f16db  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f16e1  lea     r12, pvData
0x1800f16e8  test    rax, rax
0x1800f16eb  jz      loc_1800F1A59
0x1800f16f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f16f5  inc     r8; unsigned int
0x1800f16f8  cmp     [rax+r8*2], si
0x1800f16fd  jnz     short loc_1800F16F5
0x1800f16ff  mov     ecx, 0FFFFFFFFh
0x1800f1704  cmp     r8, rcx
0x1800f1707  ja      short loc_1800F1714
0x1800f1709  mov     rdx, rax; unsigned __int16 *
0x1800f170c  mov     rcx, r15; this
0x1800f170f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800f1714  test    dil, dil
0x1800f1717  setnz   al
0x1800f171a  mov     [r14+2D9h], al
0x1800f1721  cmp     dword ptr [r14+80h], 2
0x1800f1729  jnz     loc_1800F1C6D
0x1800f172f  mov     al, sil
0x1800f1732  mov     [r14+2DAh], al
0x1800f1739  test    rbx, rbx
0x1800f173c  jnz     loc_1806F33F6
0x1800f1742  lea     rsi, aTrue; "true"
0x1800f1749  mov     rbx, rsi
0x1800f174c  lea     rax, aFalse; "false"
0x1800f1753  test    r13b, r13b
0x1800f1756  cmovz   rbx, rax
0x1800f175a  mov     rdi, rsi
0x1800f175d  xor     r13d, r13d
0x1800f1760  cmp     [rbp+50h+arg_20], r13b
0x1800f1767  cmovz   rdi, rax
0x1800f176b  cmp     [rbp+50h+arg_28], r13b
0x1800f1772  cmovz   rsi, rax
0x1800f1776  mov     rdx, cs:off_180709490; unsigned __int16 *
0x1800f177d  lea     rcx, [rbp+50h+string]; this
0x1800f1781  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f1786  nop
0x1800f1787  mov     rdx, rbx; unsigned __int16 *
0x1800f178a  lea     rcx, [rbp+50h+hstringHeader]; this
0x1800f178e  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f1793  nop
0x1800f1794  mov     rdx, cs:off_1807094A0; unsigned __int16 *
0x1800f179b  lea     rcx, [rbp+50h+hstringHeader.Reserved+8]; this
0x1800f179f  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f17a4  nop
0x1800f17a5  mov     rdx, rdi; unsigned __int16 *
0x1800f17a8  lea     rcx, [rbp+50h+hstringHeader.Reserved+10h]; this
0x1800f17ac  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f17b1  nop
0x1800f17b2  mov     rdx, cs:off_180709498; unsigned __int16 *
0x1800f17b9  lea     rcx, [rbp+50h+var_60]; this
0x1800f17bd  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f17c2  nop
0x1800f17c3  mov     rdx, rsi; unsigned __int16 *
0x1800f17c6  lea     rcx, [rbp+50h+var_58]; this
0x1800f17ca  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800f17cf  nop
0x1800f17d0  lea     r8, [rbp+50h+var_50]
0x1800f17d4  lea     rdx, [rbp+50h+string]
0x1800f17d8  lea     rcx, [rbp+50h+pv]; this
0x1800f17dc  call    ??$make_scoped_input_iterable@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@PEBU?$pair@$$CBUhstring@winrt@@U12@@std@@@impl@winrt@@YA?A_PPEBU?$pair@$$CBUhstring@winrt@@U12@@std@@0@Z
0x1800f17e1  mov     byte ptr [rbp+50h+var_98], 1
0x1800f17e5  lea     rax, [rbp+50h+pv]
0x1800f17e9  mov     [rbp+50h+var_B8], rax
0x1800f17ed  lea     rax, qword_1808D8DA8
0x1800f17f4  mov     [rbp+50h+var_88], rax
0x1800f17f8  lock inc cs:qword_1808D8DA8
0x1800f1800  cmp     cs:??$factory_cache_entry_v@UHttpFormUrlEncodedContent@Http@Web@Windows@winrt@@UIHttpFormUrlEncodedContentFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UHttpFormUrlEncodedContent@Http@Web@Windows@winrt@@UIHttpFormUrlEncodedContentFactory@2345@@12@A, r13; factory_cache_entry<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>::winrt::factory_cache_entry<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>
0x1800f1807  jz      loc_1800F1C7D
0x1800f180d  lea     r8, [rbp+50h+pv]
0x1800f1811  lea     rdx, [rbp+50h+var_90]
0x1800f1815  lea     rcx, ??$factory_cache_entry_v@UHttpFormUrlEncodedContent@Http@Web@Windows@winrt@@UIHttpFormUrlEncodedContentFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UHttpFormUrlEncodedContent@Http@Web@Windows@winrt@@UIHttpFormUrlEncodedContentFactory@2345@@12@A; factory_cache_entry<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>::winrt::factory_cache_entry<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpFormUrlEncodedContent,winrt::Windows::Web::Http::IHttpFormUrlEncodedContentFactory>
0x1800f181c  call    ?Parse@?$consume_Windows_Data_Json_IJsonObjectStatics@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectStatics<winrt::Windows::Data::Json::IJsonObjectStatics>::Parse(winrt::param::hstring const &)
0x1800f1821  nop
0x1800f1822  lock dec cs:qword_1808D8DA8
0x1800f182a  lea     rdx, [rbp+50h+var_B8]
0x1800f182e  lea     rcx, [rbp+50h+var_90]
0x1800f1832  call    ?ToString@?$consume_Windows_Foundation_IStringable@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Data::Json::JsonObject>::ToString(void)
0x1800f1837  nop
0x1800f1838  cmp     [rbp+50h+var_90], r13
0x1800f183c  jz      short loc_1800F1848
0x1800f183e  lea     rcx, [rbp+50h+var_90]
0x1800f1842  call    ?unconditional_release_ref@?$com_ptr@UAppBackupListener@implementation@Shell@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(void)
0x1800f1847  nop
0x1800f1848  mov     rax, [rbp+50h+var_A0]
0x1800f184c  test    rax, rax
0x1800f184f  jz      short loc_1800F1854
0x1800f1851  mov     byte ptr [rax], 1
0x1800f1854  cmp     byte ptr [rbp+50h+var_98], r13b
0x1800f1858  jnz     short loc_1800F185E
0x1800f185a  mov     [rbp+50h+pv], r13
0x1800f185e  lea     rcx, [rbp+50h+pv]; this
0x1800f1862  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f1867  nop
0x1800f1868  lea     r9, ??1XmlnsDefinition@Markup@Xaml@UI@Windows@winrt@@QEAA@XZ; void (*)(void *)
0x1800f186f  mov     edx, 10h; unsigned __int64
0x1800f1874  lea     r8d, [rdx-0Dh]; unsigned __int64
0x1800f1878  lea     rcx, [rbp+50h+string]; void *
0x1800f187c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800f1881  mov     [rbp+50h+pv], r13
0x1800f1885  mov     [rbp+50h+var_A0], r13
0x1800f1889  mov     [rbp+50h+var_98], r13
0x1800f188d  mov     rbx, [rbp+50h+arg_40]
0x1800f1894  mov     rdi, [rbp+50h+arg_38]
0x1800f189b  mov     rsi, [rbp+50h+arg_30]
0x1800f18a2  mov     rax, [rbp+50h+var_B8]
0x1800f18a6  test    rax, rax
0x1800f18a9  jz      short loc_1800F18AF
0x1800f18ab  mov     r12, [rax+10h]
0x1800f18af  xor     edx, edx; length
0x1800f18b1  mov     rcx, [r15]; string
0x1800f18b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f18ba  mov     [rsp+150h+var_100], rbx
0x1800f18bf  lea     rcx, aInputanimation; "inputAnimationProviderId"
0x1800f18c6  mov     [rsp+150h+var_108], rcx
0x1800f18cb  mov     [rsp+150h+var_110], rdi
0x1800f18d0  lea     rcx, aInputanimation_2; "inputAnimationSourceId"
0x1800f18d7  mov     [rsp+150h+var_118], rcx
0x1800f18dc  mov     [rsp+150h+var_120], rsi
0x1800f18e1  lea     rcx, aEdgegestureoff_0; "edgeGestureOffset"
0x1800f18e8  mov     [rsp+150h+var_128], rcx
0x1800f18ed  mov     qword ptr [rsp+150h+var_130], r12; int
0x1800f18f2  mov     r9, rax
0x1800f18f5  lea     r8, aMsActioncenter; "ms-actioncenter:controlcenter"
0x1800f18fc  lea     rdx, aWsWsWsWsLluWsL; "%ws/%ws&%ws&%ws=%llu&%ws=%llu&%ws=%llu"
0x1800f1903  lea     rcx, [rbp+50h+pv]
0x1800f1907  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800f190c  mov     [rsp+150h+var_D8], r13
0x1800f1911  lea     r9, [rbp+50h+string]; string
0x1800f1915  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x1800f1919  mov     edx, 16h; length
0x1800f191e  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800f1925  call    cs:__imp_WindowsCreateStringReference
0x1800f192b  test    eax, eax
0x1800f192d  js      loc_1800F1C97
0x1800f1933  lea     rdx, [rsp+150h+var_D8]
0x1800f1938  mov     rcx, [rbp+50h+string]
0x1800f193c  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800f1941  mov     ebx, eax
0x1800f1943  test    eax, eax
0x1800f1945  jns     short loc_1800F19B7
0x1800f1947  mov     rcx, [rbp+58h]; this
0x1800f194b  mov     r9d, eax; char *
0x1800f194e  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800f1955  mov     edx, 230h; void *
0x1800f195a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f195f  nop
0x1800f1960  mov     rcx, [rsp+150h+var_D8]
0x1800f1965  test    rcx, rcx
0x1800f1968  jz      short loc_1800F197C
0x1800f196a  mov     [rsp+150h+var_D8], r13
0x1800f196f  mov     rax, [rcx]
0x1800f1972  mov     rax, [rax+10h]
0x1800f1976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f197b  nop
0x1800f197c  mov     rcx, [rbp+50h+pv]; pv
0x1800f1980  test    rcx, rcx
0x1800f1983  jz      short loc_1800F198C
0x1800f1985  call    cs:__imp_CoTaskMemFree
0x1800f198b  nop
0x1800f198c  lea     rcx, [rbp+50h+var_B8]
0x1800f1990  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800f1995  mov     eax, ebx
0x1800f1997  mov     rcx, [rbp+50h+var_50]
0x1800f199b  xor     rcx, rsp; StackCookie
0x1800f199e  call    __security_check_cookie
0x1800f19a3  add     rsp, 118h
0x1800f19aa  pop     r15
0x1800f19ac  pop     r14
0x1800f19ae  pop     r13
0x1800f19b0  pop     r12
0x1800f19b2  pop     rdi
0x1800f19b3  pop     rsi
0x1800f19b4  pop     rbx
0x1800f19b5  pop     rbp
0x1800f19b6  retn
0x1800f19b7  mov     [rbp+50h+var_D0], r13
0x1800f19bb  mov     rdi, [rsp+150h+var_D8]
0x1800f19c0  mov     rax, [rdi]
0x1800f19c3  mov     rbx, [rax+30h]
0x1800f19c7  lea     rcx, [rbp+50h+var_D0]
0x1800f19cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f19d0  mov     rsi, [rbp+50h+pv]
0x1800f19d4  mov     rdx, rsi; unsigned __int16 *
0x1800f19d7  lea     rcx, [rbp+50h+string]; this
0x1800f19db  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800f19e0  lea     r8, [rbp+50h+var_D0]
0x1800f19e4  mov     rdx, [rbp+50h+string]
0x1800f19e8  mov     rcx, rdi
0x1800f19eb  mov     rax, rbx
0x1800f19ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f19f3  mov     ebx, eax
0x1800f19f5  test    eax, eax
0x1800f19f7  jns     short loc_1800F1A64
0x1800f19f9  mov     rcx, [rbp+58h]; this
0x1800f19fd  mov     r9d, eax; char *
0x1800f1a00  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800f1a07  mov     edx, 232h; void *
0x1800f1a0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1a11  nop
0x1800f1a12  mov     rcx, [rbp+50h+var_D0]
0x1800f1a16  test    rcx, rcx
0x1800f1a19  jz      short loc_1800F1A2C
0x1800f1a1b  mov     [rbp+50h+var_D0], r13
0x1800f1a1f  mov     rax, [rcx]
0x1800f1a22  mov     rax, [rax+10h]
0x1800f1a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a2b  nop
0x1800f1a2c  mov     rcx, [rsp+150h+var_D8]
0x1800f1a31  test    rcx, rcx
0x1800f1a34  jz      short loc_1800F1A48
0x1800f1a36  mov     [rsp+150h+var_D8], r13
0x1800f1a3b  mov     rax, [rcx]
0x1800f1a3e  mov     rax, [rax+10h]
0x1800f1a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a47  nop
0x1800f1a48  test    rsi, rsi
0x1800f1a4b  jz      loc_1800F198C
0x1800f1a51  mov     rcx, rsi
0x1800f1a54  jmp     loc_1800F1985
0x1800f1a59  xor     r8d, r8d
0x1800f1a5c  mov     rdx, r12
0x1800f1a5f  jmp     loc_1800F170C
0x1800f1a64  mov     [rbp+50h+var_C0], r13
0x1800f1a68  mov     qword ptr [rbp+50h+hstringHeader.Reserved+10h], r13
0x1800f1a6c  lea     r9, [rbp+50h+hstringHeader.Reserved+10h]; string
0x1800f1a70  lea     r8, [rbp+50h+string]; hstringHeader
0x1800f1a74  mov     edx, 17h; length
0x1800f1a79  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1800f1a80  call    cs:__imp_WindowsCreateStringReference
0x1800f1a86  test    eax, eax
0x1800f1a88  js      loc_1800F1CB1
0x1800f1a8e  lea     rdx, [rbp+50h+var_C0]
0x1800f1a92  mov     rcx, qword ptr [rbp+50h+hstringHeader.Reserved+10h]
0x1800f1a96  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x1800f1a9b  mov     ebx, eax
0x1800f1a9d  test    eax, eax
0x1800f1a9f  js      loc_1800F1CC4
0x1800f1aa5  mov     [rbp+50h+var_C8], r13
0x1800f1aa9  mov     rbx, [rbp+50h+var_C0]
0x1800f1aad  mov     rax, [rbx]
0x1800f1ab0  mov     rdi, [rax]
0x1800f1ab3  lea     rcx, [rbp+50h+var_C8]
0x1800f1ab7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1abc  lea     r8, [rbp+50h+var_C8]
0x1800f1ac0  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x1800f1ac7  mov     rcx, rbx
0x1800f1aca  mov     rax, rdi
0x1800f1acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1ad2  mov     ebx, eax
0x1800f1ad4  test    eax, eax
0x1800f1ad6  js      loc_1800F1CDE
0x1800f1adc  mov     edx, r13d
0x1800f1adf  cmp     dword ptr [r14+80h], 1
0x1800f1ae7  setz    dl
0x1800f1aea  lea     rcx, [r14+58h]
0x1800f1aee  call    ?BoostPriority@CSingleViewShellExperience@@QEAAXW4PriorityBoostReason@1@@Z; CSingleViewShellExperience::BoostPriority(CSingleViewShellExperience::PriorityBoostReason)
0x1800f1af3  mov     [rbp+50h+var_B0], r13
0x1800f1af7  mov     rdi, [rbp+50h+var_C8]
0x1800f1afb  mov     rax, [rdi]
0x1800f1afe  mov     rbx, [rax+40h]
0x1800f1b02  lea     rcx, [rbp+50h+var_B0]
0x1800f1b06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1b0b  lea     r8, [rbp+50h+var_B0]
0x1800f1b0f  mov     rdx, [rbp+50h+var_D0]
0x1800f1b13  mov     rcx, rdi
0x1800f1b16  mov     rax, rbx
0x1800f1b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b1e  mov     ebx, eax
0x1800f1b20  test    eax, eax
0x1800f1b22  jns     loc_1800F1BCA
0x1800f1b28  mov     rcx, [rbp+58h]; this
0x1800f1b2c  mov     r9d, eax; char *
0x1800f1b2f  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800f1b36  mov     edx, 241h; void *
0x1800f1b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
