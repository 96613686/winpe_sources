# Microsoft::Diagnostics::Tracer::SaveTraceToFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,bool,Microsoft::Diagnostics::MergeType)

- ea: `0x180270918`
- end: `0x1802713bf`
- name: `?SaveTraceToFile@Tracer@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N1VMergeType@23@@Z`
- size: `2727`
- prototype: `__int64 __usercall@<rax>(Microsoft::Diagnostics::Tracer *this@<rcx>, char)`
- caller_count: `4`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180267df0`
- `0x18026a7f0`
- `0x18026d5e0`
- `0x18026e680`

## callees

- `0x180001d28`
- `0x18000ab04`
- `0x18001d160`
- `0x180026ecc`
- `0x180032688`
- `0x180035698`
- `0x18004ab70`
- `0x1800552e4`
- `0x180055fa4`
- `0x180057f58`
- `0x18005d050`
- `0x18007fae8`
- `0x1800807c8`
- `0x180081a4c`
- `0x1800b2ccc`
- `0x1800e9798`
- `0x1800f748c`
- `0x1800f8288`
- `0x18012de40`
- `0x1801f06b0`
- `0x180201d5c`
- `0x18022b424`
- `0x18026ecfc`
- `0x18026eff8`
- `0x18026f018`
- `0x18026f2a4`
- `0x18026fd64`
- `0x18027061c`
- `0x180270918`
- `0x180271a20`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180270ac2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180270c77`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180270ac2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180270c77`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180270c8a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180270c8a`

## string_xrefs

- `0x180270a0a`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180270bf0`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180270cce`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180270d7f`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180270e5e`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x18027101c`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180271188`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x1802713ac`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Microsoft::Diagnostics::Tracer::SaveTraceToFile(
        Microsoft::Diagnostics::Tracer *this,
        _QWORD *a2,
        char a3,
        int a4,
        char a5)
{
  char v5; // r12
  __int64 v9; // r8
  int CurrentTraceProfileCollection; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r9d
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // esi
  const char *v22; // r9
  __int64 result; // rax
  BSTR v24; // rax
  const char *v25; // r9
  BSTR v26; // r14
  int v27; // eax
  int v28; // eax
  __int64 v29; // rsi
  __int64 v30; // rax
  _QWORD *v31; // rdx
  int v32; // eax
  unsigned int v33; // r14d
  __int64 v34; // r9
  __m128i v35; // xmm6
  int v36; // eax
  __int64 v37; // rax
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // [rsp+20h] [rbp-768h]
  __int64 v41; // [rsp+40h] [rbp-748h] BYREF
  char v42; // [rsp+48h] [rbp-740h] BYREF
  LPCWSTR lpPathName; // [rsp+50h] [rbp-738h] BYREF
  __int64 v44; // [rsp+58h] [rbp-730h] BYREF
  _BYTE v45[8]; // [rsp+60h] [rbp-728h] BYREF
  __int128 v46; // [rsp+68h] [rbp-720h] BYREF
  __int64 v47; // [rsp+78h] [rbp-710h]
  __int128 v48; // [rsp+80h] [rbp-708h] BYREF
  _QWORD v49[2]; // [rsp+90h] [rbp-6F8h] BYREF
  __int128 v50; // [rsp+A0h] [rbp-6E8h] BYREF
  __int64 *v51; // [rsp+B0h] [rbp-6D8h]
  Microsoft::Diagnostics::Tracer *v52; // [rsp+B8h] [rbp-6D0h]
  char v53; // [rsp+C0h] [rbp-6C8h]
  _BYTE v54[72]; // [rsp+C8h] [rbp-6C0h] BYREF
  _OWORD v55[2]; // [rsp+110h] [rbp-678h] BYREF
  _BYTE Src[32]; // [rsp+130h] [rbp-658h] BYREF
  _QWORD v57[7]; // [rsp+150h] [rbp-638h] BYREF
  _QWORD *v58; // [rsp+188h] [rbp-600h]
  _BYTE v59[1440]; // [rsp+190h] [rbp-5F8h] BYREF
  char v60; // [rsp+730h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  try
  {
    v5 = a4;
    v41 = 0;
    v51 = &v41;
    v52 = this;
    v53 = 1;
    *(_QWORD *)&v48 = L"ErrorCode";
    *((_QWORD *)&v48 + 1) = 9;
    v49[0] = L"Tracer_FailedToSaveTrace_0";
    v49[1] = 26;
    Microsoft::Diagnostics::SyntheticOnFailure::SyntheticOnFailure(
      (unsigned int)v59,
      (unsigned int)v49,
      (unsigned int)&v48,
      a4,
      0,
      0);
    v60 = 1;
    Microsoft::Diagnostics::Tracer::InitializeWpr(this, v45);
    if ( !*((_QWORD *)this + 25) )
    {
      CurrentTraceProfileCollection = Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(this, 1);
      v11 = CurrentTraceProfileCollection;
      if ( CurrentTraceProfileCollection < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)CurrentTraceProfileCollection,
          v40);
        Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
        Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
        if ( v41 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
LABEL_53:
        std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(&v41);
        return v11;
      }
    }
    LOBYTE(v9) = a5;
    Microsoft::Diagnostics::Tracer::GetTraceMergeProperties(this, &v44, v9);
    v12 = std::wstring_view::rfind(a2, L"\\");
    v13 = (_QWORD *)std::wstring_view::substr(a2, &v50, 0, v12);
    v14 = std::wstring::wstring((__int64)v55, v13);
    if ( *(_QWORD *)(v14 + 24) > 7u )
      v14 = *(_QWORD *)v14;
    CreateDirectoryW((LPCWSTR)v14, 0);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
    std::wstring::wstring(v55);
    v15 = std::wstring_view::rfind(a2, L"\\");
    v48 = *(_OWORD *)std::wstring_view::substr(a2, &v50, 0, v15 + 1);
    Microsoft::Diagnostics::operator+(Src);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
    if ( a3 )
    {
      v42 = 1;
      v17 = (__int64 *)std::make_unique<Microsoft::Diagnostics::TraceMergeTextClientHandler,std::wstring_view &,bool,wchar_t const (&)[1],std::wstring &,0>(
                         (unsigned int)v49,
                         (_DWORD)a2,
                         (unsigned int)&v42,
                         v16,
                         (__int64)Src);
      v18 = *v17;
      *v17 = 0;
      v19 = v41;
      v41 = v18;
      if ( v19 )
        std::default_delete<Microsoft::Diagnostics::TraceMergeTextClientHandler>::operator()();
      std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(v49);
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), v41);
    }
    lpPathName = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)this + 23) + 144LL))(
            *((_QWORD *)this + 23),
            &lpPathName);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
        (const char *)(unsigned int)v20,
        v40);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
      Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
      Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
      if ( v41 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
LABEL_16:
      std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(&v41);
      return v21;
    }
    CreateDirectoryW(lpPathName, 0);
    v24 = SysAllocStringLen((const OLECHAR *)*a2, *((_DWORD *)a2 + 2));
    v26 = v24;
    if ( !v24 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
        v25);
    v49[0] = v24;
    v27 = *((_DWORD *)this + 40);
    if ( !v27 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2A7,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
              (const char *)0x139F,
              v40);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
      Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
      Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
      if ( v41 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
      goto LABEL_53;
    }
    if ( v27 == 2 && !v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B1,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
        (const char *)0x87C52009LL,
        v40);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
      Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
      Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
      if ( v41 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
      std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(&v41);
      return 2277842953LL;
    }
    v46 = 0;
    v47 = 0;
    if ( v5 )
    {
      v54[64] = 0;
      v57[0] = off_180359780;
      v57[1] = &v46;
      v58 = v57;
      v29 = -1;
      v30 = -1;
      do
        ++v30;
      while ( lpPathName[v30] );
      v55[0] = *(_OWORD *)&Microsoft::Diagnostics::Tracer::k_diagTrackTraceFilePattern;
      *(_QWORD *)&v48 = lpPathName;
      *((_QWORD *)&v48 + 1) = v30;
      Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(&v48, v55, v57, v54);
      if ( v58 )
      {
        v31 = v57;
        LOBYTE(v31) = v58 != v57;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v58 + 32LL))(v58, v31);
      }
      v32 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, __int64))(**((_QWORD **)this + 23) + 104LL))(
              *((_QWORD *)this + 23),
              v26,
              *((_QWORD *)this + 25),
              v44);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v32,
          v40);
        if ( (_QWORD)v46 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v46,
            *((_QWORD *)&v46 + 1));
          std::_Deallocate<16>((void *)v46, (const struct std::nothrow_t *)((v47 - v46) & 0xFFFFFFFFFFFFFFF8uLL));
          v46 = 0;
          v47 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
        Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
        Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
        if ( v41 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
        std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(&v41);
        return v33;
      }
    }
    else
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, __int64))(**((_QWORD **)this + 23) + 96LL))(
              *((_QWORD *)this + 23),
              v26,
              *((_QWORD *)this + 25),
              v44);
      v21 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B7,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v28,
          v40);
        if ( (_QWORD)v46 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v46,
            *((_QWORD *)&v46 + 1));
          std::_Deallocate<16>((void *)v46, (const struct std::nothrow_t *)((v47 - v46) & 0xFFFFFFFFFFFFFFF8uLL));
          v46 = 0;
          v47 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
        Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
        Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
        if ( v41 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
        goto LABEL_16;
      }
      v29 = -1;
    }
    if ( !a5 )
    {
      v34 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(*a2, a2[1], -1, 92);
      std::wstring_view::substr(a2, v55, 0, v34);
      do
        ++v29;
      while ( lpPathName[v29] );
      v50 = *(_OWORD *)&Microsoft::Diagnostics::Tracer::k_diagTrackTraceFilePattern;
      v35 = (__m128i)v55[0];
      *(_QWORD *)&v48 = lpPathName;
      *((_QWORD *)&v48 + 1) = v29;
      v36 = Microsoft::Diagnostics::Utils::FileSystem::MoveAllFilesWithPattern(&v48, v55, &v50);
      v11 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v36,
          v40);
        if ( (_QWORD)v46 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
            v46,
            *((_QWORD *)&v46 + 1));
          std::_Deallocate<16>((void *)v46, (const struct std::nothrow_t *)((v47 - v46) & 0xFFFFFFFFFFFFFFF8uLL));
          v46 = 0;
          v47 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
        Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
        Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
        if ( v41 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
        goto LABEL_53;
      }
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 72) )
      {
        v37 = _tlgWrapBinary<wchar_t,2>(&v50, v35.m128i_i64[0], _mm_srli_si128(v35, 8).m128i_u32[0]);
        *(_QWORD *)&v48 = lpPathName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>>(
          (_DWORD)lpPathName,
          (unsigned int)&unk_1803D6248,
          v38,
          v39,
          (__int64)&v48,
          v37);
      }
    }
    v60 = 0;
    if ( (_QWORD)v46 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
        v46,
        *((_QWORD *)&v46 + 1));
      std::_Deallocate<16>((void *)v46, (const struct std::nothrow_t *)((v47 - v46) & 0xFFFFFFFFFFFFFFF8uLL));
      v46 = 0;
      v47 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&lpPathName);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v44);
    Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr((Microsoft::Diagnostics::Tracer::AutoUninitializeWpr *)v45);
    Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure((Microsoft::Diagnostics::SyntheticOnFailure *)v59);
    if ( v41 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 136LL))(*((_QWORD *)this + 23), 0);
    std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(&v41);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2EE,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180270918  mov     r11, rsp
0x18027091b  mov     [r11+18h], rbx
0x18027091f  mov     [r11+20h], rsi
0x180270923  push    rdi
0x180270924  push    r12
0x180270926  push    r13
0x180270928  push    r14
0x18027092a  push    r15
0x18027092c  sub     rsp, 760h
0x180270933  movaps  xmmword ptr [r11-38h], xmm6
0x180270938  mov     rax, cs:__security_cookie
0x18027093f  xor     rax, rsp
0x180270942  mov     [rsp+788h+var_48], rax
0x18027094a  mov     r12b, r9b
0x18027094d  mov     sil, r8b
0x180270950  mov     r15, rdx
0x180270953  mov     rdi, rcx
0x180270956  xor     r13d, r13d
0x180270959  mov     [rsp+788h+var_748], r13
0x18027095e  lea     rax, [rsp+788h+var_748]
0x180270963  mov     [r11-6D8h], rax
0x18027096a  mov     [r11-6D0h], rcx
0x180270971  mov     [rsp+788h+var_6C8], 1
0x180270979  lea     rdx, aErrorcode; "ErrorCode"
0x180270980  mov     [r11-708h], rdx
0x180270987  mov     qword ptr [r11-700h], 9
0x180270992  lea     rdx, aTracerFailedto_2; "Tracer_FailedToSaveTrace_0"
0x180270999  mov     [r11-6F8h], rdx
0x1802709a0  mov     qword ptr [r11-6F0h], 1Ah
0x1802709ab  mov     byte ptr [rsp+788h+var_760], r13b
0x1802709b0  mov     byte ptr [rsp+788h+var_768], r13b; int
0x1802709b5  lea     r8, [r11-708h]
0x1802709bc  lea     rdx, [r11-6F8h]
0x1802709c3  lea     rcx, [r11-5F8h]
0x1802709ca  call    ??0SyntheticOnFailure@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::SyntheticOnFailure::SyntheticOnFailure(std::wstring_view,std::wstring_view,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1802709cf  nop
0x1802709d0  mov     [rsp+788h+var_58], 1
0x1802709d8  lea     rdx, [rsp+788h+var_728]
0x1802709dd  mov     rcx, rdi
0x1802709e0  call    ?InitializeWpr@Tracer@Diagnostics@Microsoft@@AEAA?AVAutoUninitializeWpr@123@XZ; Microsoft::Diagnostics::Tracer::InitializeWpr(void)
0x1802709e5  nop
0x1802709e6  cmp     [rdi+0C8h], r13
0x1802709ed  jnz     short loc_180270A66
0x1802709ef  mov     dl, 1; bool
0x1802709f1  mov     rcx, rdi; this
0x1802709f4  call    ?QueryCurrentTraceProfileCollection@Tracer@Diagnostics@Microsoft@@AEAAJ_N@Z; Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(bool)
0x1802709f9  mov     ebx, eax
0x1802709fb  test    eax, eax
0x1802709fd  jns     short loc_180270A66
0x1802709ff  mov     rcx, [rsp+788h]; this
0x180270a07  mov     r9d, eax; char *
0x180270a0a  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180270a11  mov     edx, 28Fh; void *
0x180270a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270a1b  nop
0x180270a1c  lea     rcx, [rsp+788h+var_728]; this
0x180270a21  call    ??1AutoUninitializeWpr@Tracer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr(void)
0x180270a26  nop
0x180270a27  lea     rcx, [rsp+788h+var_5F8]; this
0x180270a2f  call    ??1SyntheticOnFailure@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure(void)
0x180270a34  nop
0x180270a35  cmp     [rsp+788h+var_748], r13
0x180270a3a  jz      short loc_180270A55
0x180270a3c  mov     rcx, [rdi+0B8h]
0x180270a43  mov     rax, [rcx]
0x180270a46  xor     edx, edx
0x180270a48  mov     rax, [rax+88h]
0x180270a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270a54  nop
0x180270a55  lea     rcx, [rsp+788h+var_748]
0x180270a5a  call    ??1?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(void)
0x180270a5f  mov     eax, ebx
0x180270a61  jmp     loc_180271379
0x180270a66  mov     bl, [rsp+788h+arg_20]
0x180270a6d  mov     r8b, bl
0x180270a70  lea     rdx, [rsp+788h+var_730]
0x180270a75  mov     rcx, rdi
0x180270a78  call    ?GetTraceMergeProperties@Tracer@Diagnostics@Microsoft@@AEAA?AV?$com_ptr_t@UITraceMergeProperties@@Uerr_exception_policy@wil@@@wil@@VMergeType@23@@Z; Microsoft::Diagnostics::Tracer::GetTraceMergeProperties(Microsoft::Diagnostics::MergeType)
0x180270a7d  nop
0x180270a7e  lea     rdx, asc_1803772C8; "\\"
0x180270a85  mov     rcx, r15
0x180270a88  call    ?rfind@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::rfind(wchar_t const * const,unsigned __int64)
0x180270a8d  mov     r9, rax
0x180270a90  xor     r8d, r8d
0x180270a93  lea     rdx, [rsp+788h+var_6E8]
0x180270a9b  mov     rcx, r15
0x180270a9e  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180270aa3  mov     rdx, rax
0x180270aa6  lea     rcx, [rsp+788h+var_678]
0x180270aae  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180270ab3  cmp     qword ptr [rax+18h], 7
0x180270ab8  jbe     short loc_180270ABD
0x180270aba  mov     rax, [rax]
0x180270abd  xor     edx, edx; lpSecurityAttributes
0x180270abf  mov     rcx, rax; lpPathName
0x180270ac2  call    cs:__imp_CreateDirectoryW
0x180270ac9  nop     dword ptr [rax+rax+00h]
0x180270ace  lea     rcx, [rsp+788h+var_678]; this
0x180270ad6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180270adb  lea     rdx, aNgenpdb; ".NGENPDB"
0x180270ae2  lea     rcx, [rsp+788h+var_678]
0x180270aea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180270aef  nop
0x180270af0  lea     rdx, asc_1803772C8; "\\"
0x180270af7  mov     rcx, r15
0x180270afa  call    ?rfind@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::rfind(wchar_t const * const,unsigned __int64)
0x180270aff  lea     r9, [rax+1]
0x180270b03  xor     r8d, r8d
0x180270b06  lea     rdx, [rsp+788h+var_6E8]
0x180270b0e  mov     rcx, r15
0x180270b11  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180270b16  movups  xmm0, xmmword ptr [rax]
0x180270b19  movdqu  [rsp+788h+var_708], xmm0
0x180270b22  lea     r8, [rsp+788h+var_678]
0x180270b2a  lea     rdx, [rsp+788h+var_708]
0x180270b32  lea     rcx, [rsp+788h+Src]; Src
0x180270b3a  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@$$QEAV23@@Z; Microsoft::Diagnostics::operator+(std::wstring_view,std::wstring &&)
0x180270b3f  nop
0x180270b40  lea     rcx, [rsp+788h+var_678]; this
0x180270b48  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180270b4d  test    sil, sil
0x180270b50  jz      short loc_180270BBB
0x180270b52  mov     [rsp+788h+var_740], 1
0x180270b57  lea     rax, [rsp+788h+Src]
0x180270b5f  mov     qword ptr [rsp+788h+var_768], rax; int
0x180270b64  lea     r8, [rsp+788h+var_740]
0x180270b69  mov     rdx, r15
0x180270b6c  lea     rcx, [rsp+788h+var_6F8]
0x180270b74  call    ??$make_unique@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@AEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NAEAY00$$CB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@$0A@@std@@YA?AV?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@0@AEAV?$basic_string_view@_WU?$char_traits@_W@std@@@0@$$QEA_NAEAY00$$CB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_unique<Microsoft::Diagnostics::TraceMergeTextClientHandler,std::wstring_view &,bool,wchar_t const (&)[1],std::wstring &,0>(std::wstring_view &,bool &&,wchar_t const (&)[1],std::wstring &)
0x180270b79  mov     rcx, [rax]
0x180270b7c  mov     [rax], r13
0x180270b7f  mov     rdx, [rsp+788h+var_748]
0x180270b84  mov     [rsp+788h+var_748], rcx
0x180270b89  test    rdx, rdx
0x180270b8c  jz      short loc_180270B93
0x180270b8e  call    ??R?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@QEBAXPEAVTraceMergeTextClientHandler@Diagnostics@Microsoft@@@Z; std::default_delete<Microsoft::Diagnostics::TraceMergeTextClientHandler>::operator()(Microsoft::Diagnostics::TraceMergeTextClientHandler *)
0x180270b93  lea     rcx, [rsp+788h+var_6F8]
0x180270b9b  call    ??1?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(void)
0x180270ba0  mov     rcx, [rdi+0B8h]
0x180270ba7  mov     rax, [rcx]
0x180270baa  mov     rdx, [rsp+788h+var_748]
0x180270baf  mov     rax, [rax+88h]
0x180270bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270bbb  mov     [rsp+788h+lpPathName], r13
0x180270bc0  mov     rcx, [rdi+0B8h]
0x180270bc7  mov     rax, [rcx]
0x180270bca  lea     rdx, [rsp+788h+lpPathName]
0x180270bcf  mov     rax, [rax+90h]
0x180270bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270bdb  mov     esi, eax
0x180270bdd  test    eax, eax
0x180270bdf  jns     loc_180270C70
0x180270be5  mov     rcx, [rsp+788h]; this
0x180270bed  mov     r9d, eax; char *
0x180270bf0  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180270bf7  mov     edx, 29Fh; void *
0x180270bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270c01  nop
0x180270c02  lea     rcx, [rsp+788h+lpPathName]
0x180270c07  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180270c0c  nop
0x180270c0d  lea     rcx, [rsp+788h+Src]; this
0x180270c15  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180270c1a  nop
0x180270c1b  lea     rcx, [rsp+788h+var_730]
0x180270c20  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180270c25  nop
0x180270c26  lea     rcx, [rsp+788h+var_728]; this
0x180270c2b  call    ??1AutoUninitializeWpr@Tracer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr(void)
0x180270c30  nop
0x180270c31  lea     rcx, [rsp+788h+var_5F8]; this
0x180270c39  call    ??1SyntheticOnFailure@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure(void)
0x180270c3e  nop
0x180270c3f  cmp     [rsp+788h+var_748], r13
0x180270c44  jz      short loc_180270C5F
0x180270c46  mov     rcx, [rdi+0B8h]
0x180270c4d  mov     rax, [rcx]
0x180270c50  xor     edx, edx
0x180270c52  mov     rax, [rax+88h]
0x180270c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270c5e  nop
0x180270c5f  lea     rcx, [rsp+788h+var_748]
0x180270c64  call    ??1?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(void)
0x180270c69  mov     eax, esi
0x180270c6b  jmp     loc_180271379
0x180270c70  xor     edx, edx; lpSecurityAttributes
0x180270c72  mov     rcx, [rsp+788h+lpPathName]; lpPathName
0x180270c77  call    cs:__imp_CreateDirectoryW
0x180270c7e  nop     dword ptr [rax+rax+00h]
0x180270c83  mov     edx, [r15+8]; ui
0x180270c87  mov     rcx, [r15]; strIn
0x180270c8a  call    cs:__imp_SysAllocStringLen
0x180270c91  nop     dword ptr [rax+rax+00h]
0x180270c96  mov     r14, rax
0x180270c99  mov     rcx, [rsp+788h]; this
0x180270ca1  test    rax, rax
0x180270ca4  jz      loc_1802713AC
0x180270caa  mov     [rsp+788h+var_6F8], r14
0x180270cb2  mov     eax, [rdi+0A0h]
0x180270cb8  test    eax, eax
0x180270cba  jnz     loc_180270D5D
0x180270cc0  mov     rcx, [rsp+788h]; this
0x180270cc8  mov     r9d, 139Fh; char *
0x180270cce  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180270cd5  mov     edx, 2A7h; void *
0x180270cda  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180270cdf  mov     ebx, eax
0x180270ce1  lea     rcx, [rsp+788h+var_6F8]
0x180270ce9  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180270cee  nop
0x180270cef  lea     rcx, [rsp+788h+lpPathName]
0x180270cf4  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180270cf9  nop
0x180270cfa  lea     rcx, [rsp+788h+Src]; this
0x180270d02  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180270d07  nop
0x180270d08  lea     rcx, [rsp+788h+var_730]
0x180270d0d  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180270d12  nop
0x180270d13  lea     rcx, [rsp+788h+var_728]; this
0x180270d18  call    ??1AutoUninitializeWpr@Tracer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr(void)
0x180270d1d  nop
0x180270d1e  lea     rcx, [rsp+788h+var_5F8]; this
0x180270d26  call    ??1SyntheticOnFailure@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure(void)
0x180270d2b  nop
0x180270d2c  cmp     [rsp+788h+var_748], r13
0x180270d31  jz      short loc_180270D4C
0x180270d33  mov     rcx, [rdi+0B8h]
0x180270d3a  mov     rax, [rcx]
0x180270d3d  xor     edx, edx
0x180270d3f  mov     rax, [rax+88h]
0x180270d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270d4b  nop
0x180270d4c  lea     rcx, [rsp+788h+var_748]
0x180270d51  call    ??1?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(void)
0x180270d56  mov     eax, ebx
0x180270d58  jmp     loc_180271379
0x180270d5d  cmp     eax, 2
0x180270d60  jnz     loc_180270E10
0x180270d66  test    r12b, r12b
0x180270d69  jnz     loc_180270E10
0x180270d6f  mov     rcx, [rsp+788h]; this
0x180270d77  mov     ebx, 87C52009h
0x180270d7c  mov     r9d, ebx; char *
0x180270d7f  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180270d86  mov     edx, 2B1h; void *
0x180270d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270d90  nop
0x180270d91  lea     rcx, [rsp+788h+var_6F8]
0x180270d99  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180270d9e  nop
0x180270d9f  lea     rcx, [rsp+788h+lpPathName]
0x180270da4  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180270da9  nop
0x180270daa  lea     rcx, [rsp+788h+Src]; this
0x180270db2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180270db7  nop
0x180270db8  lea     rcx, [rsp+788h+var_730]
0x180270dbd  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180270dc2  nop
0x180270dc3  lea     rcx, [rsp+788h+var_728]; this
0x180270dc8  call    ??1AutoUninitializeWpr@Tracer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Tracer::AutoUninitializeWpr::~AutoUninitializeWpr(void)
0x180270dcd  nop
0x180270dce  lea     rcx, [rsp+788h+var_5F8]; this
0x180270dd6  call    ??1SyntheticOnFailure@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::SyntheticOnFailure::~SyntheticOnFailure(void)
0x180270ddb  nop
0x180270ddc  cmp     [rsp+788h+var_748], r13
0x180270de1  jz      short loc_180270DFF
0x180270de3  mov     r8, [rdi+0B8h]
0x180270dea  mov     rcx, [r8]
0x180270ded  mov     rax, [rcx+88h]
0x180270df4  xor     edx, edx
0x180270df6  mov     rcx, r8
0x180270df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270dfe  nop
0x180270dff  lea     rcx, [rsp+788h+var_748]
0x180270e04  call    ??1?$unique_ptr@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@U?$default_delete@VTraceMergeTextClientHandler@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>::~unique_ptr<Microsoft::Diagnostics::TraceMergeTextClientHandler>(void)
0x180270e09  mov     eax, ebx
0x180270e0b  jmp     loc_180271379
0x180270e10  xorps   xmm0, xmm0
0x180270e13  movdqu  [rsp+788h+var_720], xmm0
0x180270e19  mov     [rsp+788h+var_710], r13
0x180270e1e  test    r12b, r12b
0x180270e21  jnz     loc_180270F2D
0x180270e27  mov     rcx, [rdi+0B8h]
0x180270e2e  mov     rax, [rcx]
0x180270e31  mov     r9, [rsp+788h+var_730]
0x180270e36  mov     r8, [rdi+0C8h]
0x180270e3d  mov     rdx, r14
0x180270e40  mov     rax, [rax+60h]
0x180270e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270e49  mov     esi, eax
0x180270e4b  test    eax, eax
0x180270e4d  jns     loc_180270F24
0x180270e53  mov     rcx, [rsp+788h]; this
0x180270e5b  mov     r9d, eax; char *
0x180270e5e  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180270e65  mov     edx, 2B7h; void *
0x180270e6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270e6f  nop
  ... truncated ...
```
