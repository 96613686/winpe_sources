# Microsoft::Diagnostics::GetWNFStateActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x1802f90b0`
- end: `0x1802f9b8d`
- name: `?Execute@GetWNFStateActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `2781`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001bf4`
- `0x18000364c`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x180026ecc`
- `0x180035698`
- `0x180052430`
- `0x180054198`
- `0x18005af1c`
- `0x18005d050`
- `0x1800707e0`
- `0x180081260`
- `0x180086f40`
- `0x18008bd1c`
- `0x1800a0654`
- `0x1800b10c8`
- `0x1800b1a08`
- `0x1800b2d34`
- `0x1800b2d68`
- `0x1800b83bc`
- `0x1800d0d7c`
- `0x1800d0df0`
- `0x1800daaac`
- `0x1800e21c4`
- `0x1800e2fd8`
- `0x1800edba8`
- `0x180108668`
- `0x18012de40`
- `0x18016ff48`
- `0x180170014`
- `0x180204fb0`
- `0x1802e50d0`
- `0x1802e58a4`
- `0x1802f90b0`
- `0x1802f9b94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802f9226`
- `ntdll!NtQueryWnfStateData` at `0x1802f9336`
- `ntdll!NtQueryWnfStateData` at `0x1802f945d`
- `ntdll!NtQueryWnfStateData` at `0x1802f9336`
- `ntdll!NtQueryWnfStateData` at `0x1802f945d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802f926f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1802f926f`

## string_xrefs

- `0x1802f9ad7`: `XML written to file: `
- `0x1802f911e`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1802f9287`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1802f93e3`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1802f94d0`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1802f972e`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`
- `0x1802f9a2d`: `onecore\base\telemetry\utc\service\scenarios\actions\getwnfstateaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetWNFStateActionDef::Execute(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int16 v7; // ax
  int *v8; // rsi
  const WCHAR *v9; // rcx
  const char *v10; // r9
  unsigned int LastError; // ebx
  void *v12; // rbx
  __int64 v13; // r12
  int WnfStateData; // r15d
  const struct std::nothrow_t *v15; // rax
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // ebx
  int v19; // r15d
  int v20; // r8d
  int v21; // r9d
  unsigned int v22; // ebx
  __int64 v23; // r13
  int *v24; // rbx
  unsigned int v25; // r15d
  const wchar_t *v26; // r14
  int SizeFromTdhType; // eax
  unsigned int v28; // r12d
  __m128i *v29; // rax
  wil *v30; // rcx
  int appended; // eax
  unsigned int v32; // ebx
  __int64 v33; // rax
  int v34; // eax
  int v35; // [rsp+20h] [rbp-1E8h]
  int v36; // [rsp+20h] [rbp-1E8h]
  int v37; // [rsp+20h] [rbp-1E8h]
  int v38; // [rsp+20h] [rbp-1E8h]
  int v39; // [rsp+20h] [rbp-1E8h]
  int v40; // [rsp+30h] [rbp-1D8h] BYREF
  unsigned int v41; // [rsp+34h] [rbp-1D4h] BYREF
  int v42; // [rsp+38h] [rbp-1D0h] BYREF
  PSID Sid; // [rsp+40h] [rbp-1C8h] BYREF
  void *v44; // [rsp+48h] [rbp-1C0h] BYREF
  _DWORD v45[4]; // [rsp+50h] [rbp-1B8h] BYREF
  __m128i v46; // [rsp+60h] [rbp-1A8h] BYREF
  int *v47; // [rsp+70h] [rbp-198h] BYREF
  int v48; // [rsp+78h] [rbp-190h] BYREF
  const wchar_t *v49; // [rsp+80h] [rbp-188h] BYREF
  __int64 v50; // [rsp+88h] [rbp-180h]
  __m128i v51; // [rsp+90h] [rbp-178h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-168h]
  _BYTE v53[16]; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-150h]
  _QWORD *v55; // [rsp+C0h] [rbp-148h]
  _QWORD *v56; // [rsp+C8h] [rbp-140h]
  __int64 v57; // [rsp+D0h] [rbp-138h]
  _BYTE v58[80]; // [rsp+E0h] [rbp-128h] BYREF
  __m128i v59; // [rsp+130h] [rbp-D8h] BYREF
  LPCWSTR StringSid[4]; // [rsp+150h] [rbp-B8h] BYREF
  WCHAR pszPath[16]; // [rsp+170h] [rbp-98h] BYREF
  _BYTE v62[48]; // [rsp+190h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v52 = a3;
  v55 = a2;
  v56 = a2;
  v57 = a3;
  v54 = a3;
  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
      (const char *)0x8007010BLL,
      v36);
    return 2147942667LL;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v62);
  Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
  v59.m128i_i64[0] = (__int64)L"result";
  v59.m128i_i64[1] = 6;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v58, v53, &v59);
  Sid = 0;
  v48 = 0;
  v59 = *(__m128i *)std::wstring::operator std::wstring_view(a1 + 192, &v46);
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a4, StringSid, &v59);
  v7 = *(_WORD *)(a1 + 224);
  if ( v7 == 1 )
  {
    v48 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(StringSid);
    v8 = &v48;
  }
  else
  {
    v8 = 0;
    if ( v7 == 2 )
    {
      Sid = 0;
      v9 = (const WCHAR *)StringSid;
      if ( StringSid[3] > (LPCWSTR)7 )
        v9 = StringSid[0];
      if ( !ConvertStringSidToSidW(v9, &Sid) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
                      v10);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)StringSid);
        wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
        Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
        Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
        return LastError;
      }
      v8 = (int *)Sid;
    }
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)StringSid);
  v41 = 0;
  v45[0] = 0;
  v12 = 0;
  v44 = 0;
  v13 = (a1 + 168) & -(__int64)(*(_BYTE *)(a1 + 184) != 0);
  v37 = 0;
  WnfStateData = NtQueryWnfStateData(a1 + 160, v13, v8, v45);
  if ( WnfStateData == -1073741789 )
  {
    v15 = (const struct std::nothrow_t *)std::make_unique<unsigned char [0],0>(&v47, v41);
    std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(&v44, v15);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v47);
    v12 = v44;
  }
  else if ( WnfStateData < 0 )
  {
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
    {
      v42 = 1;
      v40 = WnfStateData;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803DF804,
        v16,
        v17,
        (__int64)&v40,
        (__int64)&v42);
    }
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x5A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)WnfStateData,
            v37);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
    return v18;
  }
  v38 = (int)v12;
  v19 = NtQueryWnfStateData(a1 + 160, v13, v8, v45);
  if ( v19 >= 0 )
  {
    gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
      &v51,
      v12,
      v41);
    v59.m128i_i64[0] = (__int64)L"changestamp";
    v59.m128i_i64[1] = 11;
    v49 = L"info";
    v50 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v58,
      (unsigned int)&v49,
      (unsigned int)&v59,
      (unsigned int)v45,
      0);
    v59.m128i_i64[0] = (__int64)L"wnfmessagesize";
    v59.m128i_i64[1] = 14;
    v49 = L"info";
    v50 = 4;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
      (unsigned int)v58,
      (unsigned int)&v49,
      (unsigned int)&v59,
      (unsigned int)&v41,
      0);
    if ( *(_BYTE *)(a1 + 128) )
    {
      v59 = v51;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, &v59);
      v59.m128i_i64[0] = (__int64)L"wnfhex";
      v59.m128i_i64[1] = 6;
      v51.m128i_i64[0] = (__int64)L"info";
      v51.m128i_i64[1] = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v58, &v51, &v59, StringSid);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)StringSid);
      v23 = v52;
    }
    else
    {
      v24 = *(int **)(a1 + 136);
      v47 = v24;
      v25 = 0;
      v42 = 0;
      v49 = L"wnfstructure";
      v50 = 12;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v58, &v59, &v49);
      v26 = (const wchar_t *)(a1 + 144);
      while ( v25 < v51.m128i_i32[0] )
      {
        v26 = (const wchar_t *)(a1 + 144);
        v49 = (const wchar_t *)(a1 + 144);
        if ( v24 == *(int **)(a1 + 144) )
          break;
        v40 = 0;
        v46 = 0;
        SizeFromTdhType = Microsoft::Diagnostics::Utils::Xml::GetSizeFromTdhType((unsigned int)*v24, &v46, &v40);
        v28 = SizeFromTdhType;
        if ( SizeFromTdhType < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)SizeFromTdhType,
            v39);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v59);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
          wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
          return v28;
        }
        v29 = (__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(&v51, StringSid, v25, -1);
        try
        {
          v46 = *v29;
          Microsoft::Diagnostics::XmlWriterFacade::WriteTdhBufferToXml((__int64)v58, *v24, (unsigned int)v40, &v46);
          v25 += v40;
          v42 = v25;
          v47 = ++v24;
        }
        catch ( ... )
        {
          v34 = wil::ResultFromCaughtException(v30);
          v40 = v34;
          if ( v34 == -2147024785 )
          {
            v26 = v49;
            v24 = v47;
            v25 = v42;
            v55 = v56;
            v23 = v57;
            goto LABEL_32;
          }
          if ( v34 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
              (const char *)(unsigned int)v34,
              v35);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v59);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
          wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
          Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
          Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
          return (unsigned int)v40;
        }
      }
      v23 = v52;
LABEL_32:
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v59);
      if ( v24 != *(int **)v26 )
        goto LABEL_38;
      if ( v25 >= v41 )
        goto LABEL_42;
      if ( v24 == *(int **)v26 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v54 + 168));
        if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803DF78B);
      }
      else
      {
LABEL_38:
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v54 + 168));
        if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803DF75D);
      }
      v46 = v51;
      Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(StringSid, &v46);
      v59.m128i_i64[0] = (__int64)L"wnfhex";
      v59.m128i_i64[1] = 6;
      v51.m128i_i64[0] = (__int64)L"info";
      v51.m128i_i64[1] = 4;
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(v58, &v51, &v59, StringSid);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)StringSid);
    }
LABEL_42:
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    std::wstring::wstring((__int64)pszPath, v55);
    v46 = *(__m128i *)&Microsoft::Diagnostics::GetWNFStateActionDef::k_wnfInfoOutputFileName;
    appended = Microsoft::Diagnostics::Utils::String::AppendPath(pszPath);
    v32 = appended;
    if ( appended >= 0 )
    {
      v46 = *(__m128i *)std::wstring::operator std::wstring_view(pszPath, StringSid);
      Microsoft::Diagnostics::XmlWriterFacade::WriteToFile(v58, &v46);
      v46 = *(__m128i *)std::wstring::operator std::wstring_view(pszPath, StringSid);
      Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(v23, &v46);
      Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v23 + 168));
      v33 = std::operator+<wchar_t>(&v59, pszPath, L"\r\n");
      v46 = *(__m128i *)std::wstring::operator std::wstring_view(v33, StringSid);
      Microsoft::Diagnostics::WideStringStream::AppendString((void *)(v23 + 168));
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v59);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
        (const char *)(unsigned int)appended,
        v39);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
      return v32;
    }
  }
  else
  {
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
      {
        v42 = 2;
        v40 = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18042D328,
          (unsigned int)&unk_1803DF7BB,
          v20,
          v21,
          (__int64)&v40,
          (__int64)&v42);
      }
    }
    v22 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getwnfstateaction.cpp",
            (const char *)(unsigned int)v19,
            v38);
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v44);
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
    Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v53);
    Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v58);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
    return v22;
  }
}

```

## disassembly

```asm
0x1802f90b0  push    rbx
0x1802f90b2  push    rsi
0x1802f90b3  push    rdi
0x1802f90b4  push    r12
0x1802f90b6  push    r13
0x1802f90b8  push    r14
0x1802f90ba  push    r15
0x1802f90bc  sub     rsp, 1D0h
0x1802f90c3  mov     rax, cs:__security_cookie
0x1802f90ca  xor     rax, rsp
0x1802f90cd  mov     [rsp+208h+var_48], rax
0x1802f90d5  mov     rbx, r9
0x1802f90d8  mov     rax, r8
0x1802f90db  mov     [rsp+208h+var_168], rax
0x1802f90e3  mov     [rsp+208h+var_148], rdx
0x1802f90eb  mov     r13, rcx
0x1802f90ee  mov     [rsp+208h+var_140], rdx
0x1802f90f6  mov     [rsp+208h+var_138], rax
0x1802f90fe  mov     [rsp+208h+var_150], rax
0x1802f9106  xor     edi, edi
0x1802f9108  cmp     [rdx+8], rdi
0x1802f910c  jnz     short loc_1802F9134
0x1802f910e  mov     rcx, [rsp+208h]; this
0x1802f9116  mov     ebx, 8007010Bh
0x1802f911b  mov     r9d, ebx; char *
0x1802f911e  lea     r8, aOnecoreBaseTel_154; "onecore\\base\\telemetry\\utc\\service"...
0x1802f9125  lea     edx, [rdi+22h]; void *
0x1802f9128  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f912d  mov     eax, ebx
0x1802f912f  jmp     loc_1802F9B69
0x1802f9134  lea     rcx, [rsp+208h+var_78]; this
0x1802f913c  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1802f9141  nop
0x1802f9142  lea     rcx, [rsp+208h+var_128]; this
0x1802f914a  call    ??0XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade(void)
0x1802f914f  nop
0x1802f9150  lea     rax, aResult_0; "result"
0x1802f9157  mov     qword ptr [rsp+208h+var_D8], rax
0x1802f915f  mov     qword ptr [rsp+208h+var_D8+8], 6
0x1802f916b  lea     r8, [rsp+208h+var_D8]
0x1802f9173  lea     rdx, [rsp+208h+var_160]
0x1802f917b  lea     rcx, [rsp+208h+var_128]
0x1802f9183  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1802f9188  nop
0x1802f9189  mov     [rsp+208h+Sid], rdi
0x1802f918e  mov     [rsp+208h+var_190], edi
0x1802f9192  lea     rcx, [r13+0C0h]
0x1802f9199  lea     rdx, [rsp+208h+var_1A8]
0x1802f919e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802f91a3  movups  xmm0, xmmword ptr [rax]
0x1802f91a6  movdqu  [rsp+208h+var_D8], xmm0
0x1802f91af  lea     r8, [rsp+208h+var_D8]
0x1802f91b7  lea     rdx, [rsp+208h+StringSid]
0x1802f91bf  mov     rcx, rbx
0x1802f91c2  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1802f91c7  movzx   eax, word ptr [r13+0E0h]
0x1802f91cf  mov     ecx, 1
0x1802f91d4  cmp     ax, cx
0x1802f91d7  jnz     short loc_1802F91FA
0x1802f91d9  lea     rcx, [rsp+208h+StringSid]
0x1802f91e1  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1802f91e6  mov     [rsp+208h+var_190], eax
0x1802f91ea  lea     rsi, [rsp+208h+var_190]
0x1802f91ef  mov     r14d, 2
0x1802f91f5  jmp     loc_1802F92E6
0x1802f91fa  mov     rsi, rdi
0x1802f91fd  mov     r14d, 2
0x1802f9203  cmp     ax, r14w
0x1802f9207  jnz     loc_1802F92E6
0x1802f920d  mov     rax, [rsp+208h+Sid]
0x1802f9212  test    rax, rax
0x1802f9215  jz      short loc_1802F924B
0x1802f9217  mov     [rsp+208h+var_198], rax
0x1802f921c  lea     rcx, [rsp+208h+var_1D0]; this
0x1802f9221  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1802f9226  mov     rax, cs:__imp_LocalFree
0x1802f922d  mov     [rsp+208h+var_1C0], rax
0x1802f9232  lea     rdx, [rsp+208h+var_198]
0x1802f9237  lea     rcx, [rsp+208h+var_1C0]
0x1802f923c  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1802f9241  lea     rcx, [rsp+208h+var_1D0]; this
0x1802f9246  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1802f924b  mov     [rsp+208h+Sid], rdi
0x1802f9250  lea     rcx, [rsp+208h+StringSid]
0x1802f9258  cmp     [rsp+208h+var_A0], 7
0x1802f9261  cmova   rcx, [rsp+208h+StringSid]; StringSid
0x1802f926a  lea     rdx, [rsp+208h+Sid]; Sid
0x1802f926f  call    cs:__imp_ConvertStringSidToSidW
0x1802f9276  nop     dword ptr [rax+rax+00h]
0x1802f927b  test    eax, eax
0x1802f927d  jnz     short loc_1802F92E1
0x1802f927f  mov     rcx, [rsp+208h]; this
0x1802f9287  lea     r8, aOnecoreBaseTel_154; "onecore\\base\\telemetry\\utc\\service"...
0x1802f928e  lea     edx, [rax+3Ch]; void *
0x1802f9291  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802f9296  mov     ebx, eax
0x1802f9298  lea     rcx, [rsp+208h+StringSid]; this
0x1802f92a0  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f92a5  nop
0x1802f92a6  lea     rcx, [rsp+208h+Sid]
0x1802f92ab  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1802f92b0  nop
0x1802f92b1  lea     rcx, [rsp+208h+var_160]; this
0x1802f92b9  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1802f92be  nop
0x1802f92bf  lea     rcx, [rsp+208h+var_128]; this
0x1802f92c7  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x1802f92cc  nop
0x1802f92cd  lea     rcx, [rsp+208h+var_78]; this
0x1802f92d5  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f92da  mov     eax, ebx
0x1802f92dc  jmp     loc_1802F9B69
0x1802f92e1  mov     rsi, [rsp+208h+Sid]
0x1802f92e6  lea     rcx, [rsp+208h+StringSid]; this
0x1802f92ee  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f92f3  mov     [rsp+208h+var_1D4], edi
0x1802f92f7  mov     [rsp+208h+var_1B8], edi
0x1802f92fb  mov     rbx, rdi
0x1802f92fe  mov     [rsp+208h+var_1C0], rbx
0x1802f9303  lea     rcx, [r13+0A8h]
0x1802f930a  mov     al, [rcx+10h]
0x1802f930d  neg     al
0x1802f930f  sbb     r12, r12
0x1802f9312  and     r12, rcx
0x1802f9315  lea     rcx, [rsp+208h+var_1D4]
0x1802f931a  mov     [rsp+208h+var_1E0], rcx
0x1802f931f  mov     qword ptr [rsp+208h+var_1E8], rdi
0x1802f9324  lea     r9, [rsp+208h+var_1B8]
0x1802f9329  mov     r8, rsi
0x1802f932c  mov     rdx, r12
0x1802f932f  lea     rcx, [r13+0A0h]
0x1802f9336  call    cs:__imp_NtQueryWnfStateData
0x1802f933d  nop     dword ptr [rax+rax+00h]
0x1802f9342  mov     r15d, eax
0x1802f9345  cmp     eax, 0C0000023h
0x1802f934a  jnz     short loc_1802F937B
0x1802f934c  mov     edx, [rsp+208h+var_1D4]
0x1802f9350  lea     rcx, [rsp+208h+var_198]
0x1802f9355  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1802f935a  mov     rdx, rax
0x1802f935d  lea     rcx, [rsp+208h+var_1C0]
0x1802f9362  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x1802f9367  lea     rcx, [rsp+208h+var_198]
0x1802f936c  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f9371  mov     rbx, [rsp+208h+var_1C0]
0x1802f9376  jmp     loc_1802F943C
0x1802f937b  test    r15d, r15d
0x1802f937e  jns     loc_1802F943C
0x1802f9384  mov     eax, cs:dword_18042D328
0x1802f938a  cmp     eax, r14d
0x1802f938d  jbe     short loc_1802F93D8
0x1802f938f  mov     edx, 4
0x1802f9394  lea     rcx, dword_18042D328
0x1802f939b  call    _tlgKeywordOn
0x1802f93a0  test    al, al
0x1802f93a2  jz      short loc_1802F93D8
0x1802f93a4  mov     [rsp+208h+var_1D0], 1
0x1802f93ac  mov     [rsp+208h+var_1D8], r15d
0x1802f93b1  lea     rax, [rsp+208h+var_1D0]
0x1802f93b6  mov     [rsp+208h+var_1E0], rax
0x1802f93bb  lea     rax, [rsp+208h+var_1D8]
0x1802f93c0  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x1802f93c5  lea     rdx, unk_1803DF804
0x1802f93cc  lea     rcx, dword_18042D328
0x1802f93d3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1802f93d8  mov     rcx, [rsp+208h]; this
0x1802f93e0  mov     r9d, r15d; char *
0x1802f93e3  lea     r8, aOnecoreBaseTel_154; "onecore\\base\\telemetry\\utc\\service"...
0x1802f93ea  mov     edx, 5Ah ; 'Z'; void *
0x1802f93ef  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802f93f4  mov     ebx, eax
0x1802f93f6  lea     rcx, [rsp+208h+var_1C0]
0x1802f93fb  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f9400  nop
0x1802f9401  lea     rcx, [rsp+208h+Sid]
0x1802f9406  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1802f940b  nop
0x1802f940c  lea     rcx, [rsp+208h+var_160]; this
0x1802f9414  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1802f9419  nop
0x1802f941a  lea     rcx, [rsp+208h+var_128]; this
0x1802f9422  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x1802f9427  nop
0x1802f9428  lea     rcx, [rsp+208h+var_78]; this
0x1802f9430  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f9435  mov     eax, ebx
0x1802f9437  jmp     loc_1802F9B69
0x1802f943c  lea     rax, [rsp+208h+var_1D4]
0x1802f9441  mov     [rsp+208h+var_1E0], rax
0x1802f9446  mov     qword ptr [rsp+208h+var_1E8], rbx
0x1802f944b  lea     r9, [rsp+208h+var_1B8]
0x1802f9450  mov     r8, rsi
0x1802f9453  mov     rdx, r12
0x1802f9456  lea     rcx, [r13+0A0h]
0x1802f945d  call    cs:__imp_NtQueryWnfStateData
0x1802f9464  nop     dword ptr [rax+rax+00h]
0x1802f9469  mov     r15d, eax
0x1802f946c  test    eax, eax
0x1802f946e  jns     loc_1802F9529
0x1802f9474  mov     ecx, cs:dword_18042D328
0x1802f947a  cmp     ecx, r14d
0x1802f947d  jbe     short loc_1802F94C5
0x1802f947f  mov     edx, 4
0x1802f9484  lea     rcx, dword_18042D328
0x1802f948b  call    _tlgKeywordOn
0x1802f9490  test    al, al
0x1802f9492  jz      short loc_1802F94C5
0x1802f9494  mov     [rsp+208h+var_1D0], r14d
0x1802f9499  mov     [rsp+208h+var_1D8], r15d
0x1802f949e  lea     rax, [rsp+208h+var_1D0]
0x1802f94a3  mov     [rsp+208h+var_1E0], rax
0x1802f94a8  lea     rax, [rsp+208h+var_1D8]
0x1802f94ad  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x1802f94b2  lea     rdx, unk_1803DF7BB
0x1802f94b9  lea     rcx, dword_18042D328
0x1802f94c0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1802f94c5  mov     rcx, [rsp+208h]; this
0x1802f94cd  mov     r9d, r15d; char *
0x1802f94d0  lea     r8, aOnecoreBaseTel_154; "onecore\\base\\telemetry\\utc\\service"...
0x1802f94d7  mov     edx, 67h ; 'g'; void *
0x1802f94dc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1802f94e1  mov     ebx, eax
0x1802f94e3  lea     rcx, [rsp+208h+var_1C0]
0x1802f94e8  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1802f94ed  nop
0x1802f94ee  lea     rcx, [rsp+208h+Sid]
0x1802f94f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1802f94f8  nop
0x1802f94f9  lea     rcx, [rsp+208h+var_160]; this
0x1802f9501  call    ??1XmlWriterAutoElement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement(void)
0x1802f9506  nop
0x1802f9507  lea     rcx, [rsp+208h+var_128]; this
0x1802f950f  call    ??1XmlWriterFacade@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade(void)
0x1802f9514  nop
0x1802f9515  lea     rcx, [rsp+208h+var_78]; this
0x1802f951d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f9522  mov     eax, ebx
0x1802f9524  jmp     loc_1802F9B69
0x1802f9529  mov     r8d, [rsp+208h+var_1D4]
0x1802f952e  mov     rdx, rbx
0x1802f9531  lea     rcx, [rsp+208h+var_178]
0x1802f9539  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x1802f953e  lea     rax, aChangestamp; "changestamp"
0x1802f9545  mov     qword ptr [rsp+208h+var_D8], rax
0x1802f954d  mov     qword ptr [rsp+208h+var_D8+8], 0Bh
0x1802f9559  lea     r12, aInfo_0; "info"
0x1802f9560  mov     [rsp+208h+var_188], r12
0x1802f9568  mov     esi, 4
0x1802f956d  mov     [rsp+208h+var_180], rsi
0x1802f9575  mov     byte ptr [rsp+208h+var_1E8], dil
0x1802f957a  lea     r9, [rsp+208h+var_1B8]
0x1802f957f  lea     r8, [rsp+208h+var_D8]
0x1802f9587  lea     rdx, [rsp+208h+var_188]
0x1802f958f  lea     rcx, [rsp+208h+var_128]
0x1802f9597  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f959c  lea     rax, aWnfmessagesize; "wnfmessagesize"
0x1802f95a3  mov     qword ptr [rsp+208h+var_D8], rax
0x1802f95ab  mov     qword ptr [rsp+208h+var_D8+8], 0Eh
0x1802f95b7  mov     [rsp+208h+var_188], r12
0x1802f95bf  mov     [rsp+208h+var_180], rsi
0x1802f95c7  mov     byte ptr [rsp+208h+var_1E8], dil; int
0x1802f95cc  lea     r9, [rsp+208h+var_1D4]
0x1802f95d1  lea     r8, [rsp+208h+var_D8]
0x1802f95d9  lea     rdx, [rsp+208h+var_188]
0x1802f95e1  lea     rcx, [rsp+208h+var_128]
0x1802f95e9  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1802f95ee  lea     rdx, [rsp+208h+var_D8]
0x1802f95f6  cmp     [r13+80h], dil
0x1802f95fd  jz      loc_1802F968D
0x1802f9603  movaps  xmm0, [rsp+208h+var_178]
0x1802f960b  movdqa  [rsp+208h+var_D8], xmm0
0x1802f9614  lea     rcx, [rsp+208h+StringSid]
0x1802f961c  call    ?ConvertBufferToHexString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Utils::String::ConvertBufferToHexString(gsl::span<gsl::byte const,-1>)
0x1802f9621  nop
0x1802f9622  lea     rax, aWnfhex; "wnfhex"
0x1802f9629  mov     qword ptr [rsp+208h+var_D8], rax
0x1802f9631  mov     qword ptr [rsp+208h+var_D8+8], 6
0x1802f963d  mov     qword ptr [rsp+208h+var_178], r12
0x1802f9645  mov     qword ptr [rsp+208h+var_178+8], rsi
0x1802f964d  lea     r9, [rsp+208h+StringSid]
0x1802f9655  lea     r8, [rsp+208h+var_D8]
0x1802f965d  lea     rdx, [rsp+208h+var_178]
0x1802f9665  lea     rcx, [rsp+208h+var_128]
0x1802f966d  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1802f9672  nop
0x1802f9673  lea     rcx, [rsp+208h+StringSid]; this
0x1802f967b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802f9680  mov     r13, [rsp+208h+var_168]
0x1802f9688  jmp     loc_1802F99C4
0x1802f968d  mov     rbx, [r13+88h]
0x1802f9694  mov     [rsp+208h+var_198], rbx
0x1802f9699  mov     r15d, edi
0x1802f969c  mov     [rsp+208h+var_1D0], edi
0x1802f96a0  lea     rax, aWnfstructure; "wnfstructure"
0x1802f96a7  mov     [rsp+208h+var_188], rax
0x1802f96af  mov     [rsp+208h+var_180], 0Ch
0x1802f96bb  lea     r8, [rsp+208h+var_188]
0x1802f96c3  lea     rcx, [rsp+208h+var_128]
0x1802f96cb  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x1802f96d0  nop
  ... truncated ...
```
