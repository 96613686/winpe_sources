# PeoplePaneViewManager::IsWindowVisibleInContactPanel(HWND__ *,ushort const *,int *)

- ea: `0x180474ec4`
- end: `0x180475443`
- name: `?IsWindowVisibleInContactPanel@PeoplePaneViewManager@@AEAAJPEAUHWND__@@PEBGPEAH@Z`
- size: `1407`
- prototype: `__int64 __fastcall(PeoplePaneViewManager *__hidden this, HWND, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801c5d30`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180058d38`
- `0x18005f410`
- `0x18007b3e0`
- `0x1800d1628`
- `0x1800ed8e0`
- `0x1801b75c0`
- `0x1802cf010`
- `0x180356360`
- `0x1803c1930`
- `0x1803c7464`
- `0x1803e00d0`
- `0x180403ab0`
- `0x180474ec4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1804753ac`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1804753ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804752a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804752cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804753da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804752a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804752cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804753da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180475388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180475388`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180474fca`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180474fca`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180474f1d`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180474f1d`

## string_xrefs

- `0x180475125`: `RunningComponentUIApplicationList`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall PeoplePaneViewManager::IsWindowVisibleInContactPanel(
        PeoplePaneViewManager *this,
        HWND a2,
        const unsigned __int16 *a3,
        int *a4)
{
  int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, struct IInspectable **); // rbx
  int v19; // r14d
  WCHAR *v20; // rsi
  bool v21; // r8
  bool v22; // r9
  HSTRING v23; // rbx
  HSTRING v24; // rax
  int v25; // edx
  int v26; // ebx
  int v27; // ebx
  HSTRING v28; // rcx
  __int64 v29; // rax
  const WCHAR *p_lpStringValue; // rbx
  const WCHAR *StringRawBuffer; // rax
  int StringOrdinal; // ebx
  int cchValue; // [rsp+20h] [rbp-1E8h]
  int v34; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v35; // [rsp+38h] [rbp-1D0h] BYREF
  __int64 v36; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-1C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-1B8h] BYREF
  int v39; // [rsp+58h] [rbp-1B0h]
  __int64 v40; // [rsp+60h] [rbp-1A8h] BYREF
  const WCHAR *v41; // [rsp+68h] [rbp-1A0h] BYREF
  int v42; // [rsp+70h] [rbp-198h]
  _BYTE v43[16]; // [rsp+80h] [rbp-188h] BYREF
  _BYTE v44[8]; // [rsp+90h] [rbp-178h] BYREF
  _BYTE v45[232]; // [rsp+98h] [rbp-170h] BYREF
  LPCWSTR lpStringValue; // [rsp+180h] [rbp-88h] BYREF
  struct IInspectable *v47[3]; // [rsp+188h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1A0h] [rbp-68h] BYREF
  __int64 v49; // [rsp+1B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  *a4 = 0;
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v7 = CoreQueryWindowService(
         a2,
         &GUID_c56c5799_4bb3_7fae_7fad_4db2f6a53eff,
         &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da,
         &v35);
  if ( v7 < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return (unsigned int)v7;
  }
  v36 = 0;
  v49 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.ValueSet",
    0x28u,
    0x27u);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
         v49,
         &v36);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x419,
      (unsigned int)"pcshell\\twinui\\peoplepaneviewmanager\\lib\\peoplepaneviewmanager.cpp",
      (const char *)(unsigned int)v9,
      cchValue);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v10;
  }
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v11 = RoCreatePropertySetSerializer(&v37);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41D,
      (unsigned int)"pcshell\\twinui\\peoplepaneviewmanager\\lib\\peoplepaneviewmanager.cpp",
      (const char *)(unsigned int)v11,
      cchValue);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v12;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v37 + 56LL))(v37, v36, v35);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41E,
      (unsigned int)"pcshell\\twinui\\peoplepaneviewmanager\\lib\\peoplepaneviewmanager.cpp",
      (const char *)(unsigned int)v13,
      cchValue);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v14;
  }
  v40 = 0;
  v15 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          &v36,
          &v40);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"pcshell\\twinui\\peoplepaneviewmanager\\lib\\peoplepaneviewmanager.cpp",
      (const char *)(unsigned int)v15,
      cchValue);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v16;
  }
  v41 = 0;
  v42 = 0;
  v17 = v40;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, struct IInspectable **))(*(_QWORD *)v40 + 48LL);
  lpStringValue = (LPCWSTR)&v41;
  v47[0] = 0;
  v49 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"RunningComponentUIApplicationList",
    0x22u,
    0x21u);
  v19 = v18(v17, v49, v47);
  v49 = 0;
  v20 = (WCHAR *)lpStringValue;
  RoVariant::RoVariant((RoVariant *)&string, v47[0], v21, v22);
  v23 = string;
  string = 0;
  LODWORD(v17) = v39;
  v39 = 0;
  RoVariant::~RoVariant((RoVariant *)&string);
  v24 = *(HSTRING *)v20;
  *(_QWORD *)v20 = v23;
  string = v24;
  LODWORD(v24) = *((_DWORD *)v20 + 2);
  *((_DWORD *)v20 + 2) = v17;
  v39 = (int)v24;
  RoVariant::~RoVariant((RoVariant *)&string);
  if ( v19 < 0 )
  {
    RoVariant::~RoVariant((RoVariant *)&v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return (unsigned int)v19;
  }
  v25 = 0;
  v34 = 0;
  v26 = v42;
  if ( v42 < 0 )
    goto LABEL_18;
  if ( v42 )
  {
    if ( v42 == 1 || v42 == 3 )
    {
      v25 = 13;
      v34 = 13;
    }
    else
    {
      v26 = (*(__int64 (__fastcall **)(const WCHAR *, int *))(*(_QWORD *)v41 + 48LL))(v41, &v34);
      if ( v26 < 0 )
      {
LABEL_18:
        RoVariant::~RoVariant((RoVariant *)&v41);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        return (unsigned int)v26;
      }
      v26 = v42;
      v25 = v34;
    }
  }
  if ( v25 == 12 )
  {
    string = 0;
    lpStringValue = v41;
    LODWORD(v47[0]) = v26;
    WindowsDeleteString(0);
    string = 0;
    v27 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&lpStringValue, &string);
    if ( v27 < 0 )
    {
      WindowsDeleteString(string);
      string = 0;
      RoVariant::~RoVariant((RoVariant *)&v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      return (unsigned int)v27;
    }
    v28 = string;
    if ( string )
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v43);
      v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, a3);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L";");
      std::basic_stringbuf<unsigned short>::str(v45, &lpStringValue);
      p_lpStringValue = (const WCHAR *)&lpStringValue;
      if ( v47[2] > (struct IInspectable *)7 )
        p_lpStringValue = lpStringValue;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      StringOrdinal = FindStringOrdinal(0x400000u, StringRawBuffer, -1, p_lpStringValue, -1, 1);
      std::wstring::_Tidy_deallocate(&lpStringValue);
      if ( StringOrdinal != -1 )
        *a4 = 1;
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v43);
      v28 = string;
    }
    WindowsDeleteString(v28);
  }
  RoVariant::~RoVariant((RoVariant *)&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return 0;
}

```

## disassembly

```asm
0x180474ec4  push    rbx
0x180474ec6  push    rsi
0x180474ec7  push    rdi
0x180474ec8  push    r12
0x180474eca  push    r13
0x180474ecc  push    r14
0x180474ece  push    r15
0x180474ed0  sub     rsp, 1D0h
0x180474ed7  mov     rax, cs:__security_cookie
0x180474ede  xor     rax, rsp
0x180474ee1  mov     [rsp+208h+var_48], rax
0x180474ee9  mov     r15, r9
0x180474eec  mov     r12, r8
0x180474eef  mov     rbx, rdx
0x180474ef2  xor     r13d, r13d
0x180474ef5  mov     [r9], r13d
0x180474ef8  mov     [rsp+208h+var_1D0], r13
0x180474efd  lea     rcx, [rsp+208h+var_1D0]
0x180474f02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474f07  lea     r9, [rsp+208h+var_1D0]
0x180474f0c  lea     r8, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x180474f13  lea     rdx, _GUID_c56c5799_4bb3_7fae_7fad_4db2f6a53eff
0x180474f1a  mov     rcx, rbx
0x180474f1d  call    cs:__imp_CoreQueryWindowService
0x180474f23  mov     ebx, eax
0x180474f25  test    eax, eax
0x180474f27  jns     short loc_180474F3A
0x180474f29  lea     rcx, [rsp+208h+var_1D0]
0x180474f2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474f33  mov     eax, ebx
0x180474f35  jmp     loc_18047541F
0x180474f3a  mov     [rsp+208h+var_1C8], r13
0x180474f3f  mov     [rsp+208h+var_50], r13
0x180474f47  mov     r9d, 27h ; '''; unsigned int
0x180474f4d  lea     r8d, [r9+1]; unsigned int
0x180474f51  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180474f58  lea     rcx, [rsp+208h+hstringHeader]; hstringHeader
0x180474f60  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180474f65  lea     rdx, [rsp+208h+var_1C8]
0x180474f6a  mov     rcx, [rsp+208h+var_50]
0x180474f72  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180474f77  mov     ebx, eax
0x180474f79  test    eax, eax
0x180474f7b  jns     short loc_180474FB6
0x180474f7d  mov     rcx, [rsp+208h]; this
0x180474f85  mov     r9d, eax; char *
0x180474f88  lea     r8, aPcshellTwinuiP_14; "pcshell\\twinui\\peoplepaneviewmanager"...
0x180474f8f  mov     edx, 419h; void *
0x180474f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180474f99  nop
0x180474f9a  lea     rcx, [rsp+208h+var_1C8]
0x180474f9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474fa4  nop
0x180474fa5  lea     rcx, [rsp+208h+var_1D0]
0x180474faa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474faf  mov     eax, ebx
0x180474fb1  jmp     loc_18047541F
0x180474fb6  mov     [rsp+208h+var_1C0], r13
0x180474fbb  lea     rcx, [rsp+208h+var_1C0]
0x180474fc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474fc5  lea     rcx, [rsp+208h+var_1C0]
0x180474fca  call    cs:__imp_RoCreatePropertySetSerializer
0x180474fd0  mov     ebx, eax
0x180474fd2  test    eax, eax
0x180474fd4  jns     short loc_18047501A
0x180474fd6  mov     rcx, [rsp+208h]; this
0x180474fde  mov     r9d, eax; char *
0x180474fe1  lea     r8, aPcshellTwinuiP_14; "pcshell\\twinui\\peoplepaneviewmanager"...
0x180474fe8  mov     edx, 41Dh; void *
0x180474fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180474ff2  nop
0x180474ff3  lea     rcx, [rsp+208h+var_1C0]
0x180474ff8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180474ffd  nop
0x180474ffe  lea     rcx, [rsp+208h+var_1C8]
0x180475003  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475008  nop
0x180475009  lea     rcx, [rsp+208h+var_1D0]
0x18047500e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475013  mov     eax, ebx
0x180475015  jmp     loc_18047541F
0x18047501a  mov     rcx, [rsp+208h+var_1C0]
0x18047501f  mov     rax, [rcx]
0x180475022  mov     r8, [rsp+208h+var_1D0]
0x180475027  mov     rdx, [rsp+208h+var_1C8]
0x18047502c  mov     rax, [rax+38h]
0x180475030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180475035  mov     ebx, eax
0x180475037  test    eax, eax
0x180475039  jns     short loc_18047507F
0x18047503b  mov     rcx, [rsp+208h]; this
0x180475043  mov     r9d, eax; char *
0x180475046  lea     r8, aPcshellTwinuiP_14; "pcshell\\twinui\\peoplepaneviewmanager"...
0x18047504d  mov     edx, 41Eh; void *
0x180475052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180475057  nop
0x180475058  lea     rcx, [rsp+208h+var_1C0]
0x18047505d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475062  nop
0x180475063  lea     rcx, [rsp+208h+var_1C8]
0x180475068  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18047506d  nop
0x18047506e  lea     rcx, [rsp+208h+var_1D0]
0x180475073  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475078  mov     eax, ebx
0x18047507a  jmp     loc_18047541F
0x18047507f  mov     [rsp+208h+var_1A8], r13
0x180475084  lea     rdx, [rsp+208h+var_1A8]
0x180475089  lea     rcx, [rsp+208h+var_1C8]
0x18047508e  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180475093  mov     ebx, eax
0x180475095  test    eax, eax
0x180475097  jns     short loc_1804750E8
0x180475099  mov     rcx, [rsp+208h]; this
0x1804750a1  mov     r9d, eax; char *
0x1804750a4  lea     r8, aPcshellTwinuiP_14; "pcshell\\twinui\\peoplepaneviewmanager"...
0x1804750ab  mov     edx, 421h; void *
0x1804750b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804750b5  nop
0x1804750b6  lea     rcx, [rsp+208h+var_1A8]
0x1804750bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804750c0  nop
0x1804750c1  lea     rcx, [rsp+208h+var_1C0]
0x1804750c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804750cb  nop
0x1804750cc  lea     rcx, [rsp+208h+var_1C8]
0x1804750d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804750d6  nop
0x1804750d7  lea     rcx, [rsp+208h+var_1D0]
0x1804750dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804750e1  mov     eax, ebx
0x1804750e3  jmp     loc_18047541F
0x1804750e8  mov     [rsp+208h+var_1A0], r13
0x1804750ed  mov     [rsp+208h+var_198], r13d
0x1804750f2  mov     rdi, [rsp+208h+var_1A8]
0x1804750f7  mov     rax, [rdi]
0x1804750fa  mov     rbx, [rax+30h]
0x1804750fe  lea     rax, [rsp+208h+var_1A0]
0x180475103  mov     [rsp+208h+lpStringValue], rax
0x18047510b  mov     [rsp+208h+var_80], r13
0x180475113  mov     [rsp+208h+var_50], r13
0x18047511b  mov     r9d, 21h ; '!'; unsigned int
0x180475121  lea     r8d, [r9+1]; unsigned int
0x180475125  lea     rdx, aRunningcompone; "RunningComponentUIApplicationList"
0x18047512c  lea     rcx, [rsp+208h+hstringHeader]; hstringHeader
0x180475134  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180475139  nop
0x18047513a  lea     r8, [rsp+208h+var_80]
0x180475142  mov     rdx, [rsp+208h+var_50]
0x18047514a  mov     rcx, rdi
0x18047514d  mov     rax, rbx
0x180475150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180475155  mov     r14d, eax
0x180475158  mov     [rsp+208h+var_50], r13
0x180475160  mov     rsi, [rsp+208h+lpStringValue]
0x180475168  mov     rdx, [rsp+208h+var_80]; struct IInspectable *
0x180475170  lea     rcx, [rsp+208h+string]; this
0x180475175  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18047517a  mov     rbx, [rsp+208h+string]
0x18047517f  mov     [rsp+208h+string], r13
0x180475184  mov     edi, [rsp+208h+var_1B0]
0x180475188  mov     [rsp+208h+var_1B0], r13d
0x18047518d  lea     rcx, [rsp+208h+string]; this
0x180475192  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180475197  mov     rax, [rsi]
0x18047519a  mov     [rsi], rbx
0x18047519d  mov     [rsp+208h+string], rax
0x1804751a2  mov     eax, [rsi+8]
0x1804751a5  mov     [rsi+8], edi
0x1804751a8  mov     [rsp+208h+var_1B0], eax
0x1804751ac  lea     rcx, [rsp+208h+string]; this
0x1804751b1  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804751b6  nop
0x1804751b7  test    r14d, r14d
0x1804751ba  jns     short loc_1804751FA
0x1804751bc  lea     rcx, [rsp+208h+var_1A0]; this
0x1804751c1  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804751c6  nop
0x1804751c7  lea     rcx, [rsp+208h+var_1A8]
0x1804751cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804751d1  nop
0x1804751d2  lea     rcx, [rsp+208h+var_1C0]
0x1804751d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804751dc  nop
0x1804751dd  lea     rcx, [rsp+208h+var_1C8]
0x1804751e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804751e7  nop
0x1804751e8  lea     rcx, [rsp+208h+var_1D0]
0x1804751ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804751f2  mov     eax, r14d
0x1804751f5  jmp     loc_18047541F
0x1804751fa  mov     edx, r13d
0x1804751fd  mov     [rsp+208h+var_1D8], edx
0x180475201  mov     ebx, [rsp+208h+var_198]
0x180475205  test    ebx, ebx
0x180475207  js      short loc_180475233
0x180475209  mov     ecx, ebx
0x18047520b  jz      short loc_180475283
0x18047520d  sub     ecx, 1
0x180475210  jz      short loc_18047527A
0x180475212  cmp     ecx, 2
0x180475215  jz      short loc_18047527A
0x180475217  mov     rcx, [rsp+208h+var_1A0]
0x18047521c  mov     rax, [rcx]
0x18047521f  lea     rdx, [rsp+208h+var_1D8]
0x180475224  mov     rax, [rax+30h]
0x180475228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047522d  mov     ebx, eax
0x18047522f  test    eax, eax
0x180475231  jns     short loc_180475270
0x180475233  lea     rcx, [rsp+208h+var_1A0]; this
0x180475238  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18047523d  nop
0x18047523e  lea     rcx, [rsp+208h+var_1A8]
0x180475243  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475248  nop
0x180475249  lea     rcx, [rsp+208h+var_1C0]
0x18047524e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475253  nop
0x180475254  lea     rcx, [rsp+208h+var_1C8]
0x180475259  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18047525e  nop
0x18047525f  lea     rcx, [rsp+208h+var_1D0]
0x180475264  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475269  mov     eax, ebx
0x18047526b  jmp     loc_18047541F
0x180475270  mov     ebx, [rsp+208h+var_198]
0x180475274  mov     edx, [rsp+208h+var_1D8]
0x180475278  jmp     short loc_180475283
0x18047527a  mov     edx, 0Dh
0x18047527f  mov     [rsp+208h+var_1D8], edx
0x180475283  cmp     edx, 0Ch
0x180475286  jnz     loc_1804753E1
0x18047528c  mov     [rsp+208h+string], r13
0x180475291  mov     rax, [rsp+208h+var_1A0]
0x180475296  mov     [rsp+208h+lpStringValue], rax
0x18047529e  mov     dword ptr [rsp+208h+var_80], ebx
0x1804752a5  xor     ecx, ecx; string
0x1804752a7  call    cs:__imp_WindowsDeleteString
0x1804752ad  mov     [rsp+208h+string], r13
0x1804752b2  lea     rdx, [rsp+208h+string]; HSTRING *
0x1804752b7  lea     rcx, [rsp+208h+lpStringValue]; this
0x1804752bf  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1804752c4  mov     ebx, eax
0x1804752c6  test    eax, eax
0x1804752c8  jns     short loc_180475317
0x1804752ca  mov     rcx, [rsp+208h+string]; string
0x1804752cf  call    cs:__imp_WindowsDeleteString
0x1804752d5  mov     [rsp+208h+string], r13
0x1804752da  lea     rcx, [rsp+208h+var_1A0]; this
0x1804752df  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804752e4  nop
0x1804752e5  lea     rcx, [rsp+208h+var_1A8]
0x1804752ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804752ef  nop
0x1804752f0  lea     rcx, [rsp+208h+var_1C0]
0x1804752f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804752fa  nop
0x1804752fb  lea     rcx, [rsp+208h+var_1C8]
0x180475300  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475305  nop
0x180475306  lea     rcx, [rsp+208h+var_1D0]
0x18047530b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180475310  mov     eax, ebx
0x180475312  jmp     loc_18047541F
0x180475317  mov     rcx, [rsp+208h+string]
0x18047531c  test    rcx, rcx
0x18047531f  jz      loc_1804753DA
0x180475325  lea     rcx, [rsp+208h+var_188]
0x18047532d  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180475332  nop
0x180475333  mov     rdx, r12
0x180475336  lea     rcx, [rsp+208h+var_178]
0x18047533e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180475343  lea     rdx, asc_180770D48; ";"
0x18047534a  mov     rcx, rax
0x18047534d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180475352  lea     rdx, [rsp+208h+lpStringValue]
0x18047535a  lea     rcx, [rsp+208h+var_170]
0x180475362  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180475367  lea     rbx, [rsp+208h+lpStringValue]
0x18047536f  cmp     [rsp+208h+var_70], 7
0x180475378  cmova   rbx, [rsp+208h+lpStringValue]
0x180475381  xor     edx, edx; length
0x180475383  mov     rcx, [rsp+208h+string]; string
0x180475388  call    cs:__imp_WindowsGetStringRawBuffer
0x18047538e  mov     esi, 1
0x180475393  mov     [rsp+208h+bIgnoreCase], esi; bIgnoreCase
0x180475397  or      edi, 0FFFFFFFFh
0x18047539a  mov     [rsp+208h+cchValue], edi; cchValue
0x18047539e  mov     r9, rbx; lpStringValue
0x1804753a1  mov     r8d, edi; cchSource
0x1804753a4  mov     rdx, rax; lpStringSource
0x1804753a7  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x1804753ac  call    cs:__imp_FindStringOrdinal
0x1804753b2  mov     ebx, eax
0x1804753b4  lea     rcx, [rsp+208h+lpStringValue]
0x1804753bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1804753c1  cmp     ebx, edi
0x1804753c3  jz      short loc_1804753C8
  ... truncated ...
```
