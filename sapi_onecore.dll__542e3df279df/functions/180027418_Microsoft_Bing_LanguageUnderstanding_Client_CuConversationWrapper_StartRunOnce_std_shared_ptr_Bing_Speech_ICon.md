# Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::StartRunOnce(std::shared_ptr<Bing::Speech::IConversation> const &)

- ea: `0x180027418`
- end: `0x18002834b`
- name: `?StartRunOnce@CuConversationWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEBV?$shared_ptr@VIConversation@Speech@Bing@@@std@@@Z`
- size: `3891`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801d3a20`

## callees

- `0x180021444`
- `0x18002168c`
- `0x180021944`
- `0x180026508`
- `0x180026c10`
- `0x180027418`
- `0x18002895c`
- `0x180028994`
- `0x180029860`
- `0x18002b750`
- `0x18002f130`
- `0x180030738`
- `0x1800315fc`
- `0x1800316ac`
- `0x180034084`
- `0x1800370d4`
- `0x180038150`
- `0x180039c98`
- `0x180039cbc`
- `0x18003b3bc`
- `0x18003b44c`
- `0x18003b510`
- `0x18003b590`
- `0x18003b69c`
- `0x18003b94c`
- `0x180064db8`
- `0x18006a058`
- `0x18006d2c4`
- `0x180075a70`
- `0x180079e30`
- `0x18007aae4`
- `0x180089ce4`
- `0x1800e3670`
- `0x1800e3ad0`
- `0x180116800`
- `0x1801d05d4`
- `0x1801d1738`
- `0x1801d1e64`
- `0x1801d1ec4`
- `0x1801d2ce0`
- `0x1801d3518`
- `0x1801d3750`
- `0x1801d87cc`
- `0x1801d8838`
- `0x1801d88a8`
- `0x1801df1f4`
- `0x180266034`
- `0x18026aff4`
- `0x180272924`
- `0x18027b398`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002802d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002811d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800281e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002828e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002802d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002811d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800281e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002828e`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::StartRunOnce(
        __int64 a1,
        _QWORD *a2)
{
  Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession *v4; // r12
  __int64 v5; // rax
  __int64 v6; // rdi
  struct _GUID *LanguageTagDataSource; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // rbx
  __int64 *Instance; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, struct _GUID *); // r15
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v21; // rbx
  const unsigned __int16 *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rbx
  Halsey::swstring *ClientID; // rax
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rbx
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  const unsigned __int16 *v33; // rax
  __int64 *v34; // r10
  int v35; // ebx
  const unsigned __int16 *v36; // rdx
  const unsigned __int16 *v37; // rax
  int v38; // r8d
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, _BYTE *, _DWORD *); // r14
  int v41; // ebx
  __int64 v42; // rbx
  __int64 (__fastcall *v43)(__int64, _BYTE *, _DWORD *); // rdi
  int v44; // ebx
  int v45; // eax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, void **, __int64, _QWORD); // rbx
  int v51; // eax
  unsigned int v52; // ebx
  struct tWAVEFORMATEX *v53; // rbx
  unsigned int v54; // r14d
  int v55; // eax
  unsigned int v56; // edi
  int v57; // [rsp+30h] [rbp-488h] BYREF
  __int64 v58; // [rsp+38h] [rbp-480h] BYREF
  std::_Ref_count_base *v59; // [rsp+40h] [rbp-478h]
  __int64 v60; // [rsp+48h] [rbp-470h] BYREF
  std::_Ref_count_base *v61; // [rsp+50h] [rbp-468h]
  _BYTE v62[8]; // [rsp+58h] [rbp-460h] BYREF
  std::_Ref_count_base *v63; // [rsp+60h] [rbp-458h]
  _BYTE v64[8]; // [rsp+68h] [rbp-450h] BYREF
  std::_Ref_count_base *v65; // [rsp+70h] [rbp-448h]
  struct _GUID v66; // [rsp+78h] [rbp-440h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-430h]
  int v68; // [rsp+90h] [rbp-428h]
  struct _GUID *v69; // [rsp+B0h] [rbp-408h]
  const wchar_t *v70; // [rsp+B8h] [rbp-400h] BYREF
  std::_Ref_count_base *v71; // [rsp+C0h] [rbp-3F8h]
  unsigned __int16 *v72[4]; // [rsp+D8h] [rbp-3E0h] BYREF
  _BYTE v73[32]; // [rsp+F8h] [rbp-3C0h] BYREF
  _BYTE v74[32]; // [rsp+118h] [rbp-3A0h] BYREF
  _BYTE v75[40]; // [rsp+138h] [rbp-380h] BYREF
  _QWORD v76[8]; // [rsp+160h] [rbp-358h] BYREF
  _BYTE v77[64]; // [rsp+1A0h] [rbp-318h] BYREF
  _DWORD v78[24]; // [rsp+1E0h] [rbp-2D8h] BYREF
  __int128 v79; // [rsp+240h] [rbp-278h]
  __int16 v80; // [rsp+250h] [rbp-268h] BYREF
  char *v81; // [rsp+258h] [rbp-260h]
  __int64 v82; // [rsp+260h] [rbp-258h]
  __int64 v83; // [rsp+268h] [rbp-250h]
  char v84; // [rsp+270h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v4 = (Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession *)(a1 + 7184);
  Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession::StartRunOnce((Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession *)(a1 + 7184));
  SpPerfTelemetry::CuConversationWrapper_Run_Enter();
  v5 = std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(&v66, a1 + 104);
  Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(a1, v5);
  v6 = a1 + 48;
  LanguageTagDataSource = (struct _GUID *)Microsoft::Bing::LanguageUnderstanding::Client::MakeLanguageTagDataSource(
                                            &v70,
                                            *(_QWORD *)(a1 + 48) + 408LL);
  v66 = 0;
  v66 = *LanguageTagDataSource;
  *(_QWORD *)&LanguageTagDataSource->Data1 = 0;
  *(_QWORD *)LanguageTagDataSource->Data4 = 0;
  Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(a1, &v66);
  if ( v71 )
    std::_Ref_count_base::_Decref(v71);
  v8 = a2[1];
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  v9 = a2[1];
  *(_QWORD *)(a1 + 7168) = *a2;
  v10 = *(std::_Ref_count_base **)(a1 + 7176);
  *(_QWORD *)(a1 + 7176) = v9;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = _RTDynamicCast_0(
          *(_QWORD *)(a1 + 7168),
          0,
          &Bing::Speech::IConversation `RTTI Type Descriptor',
          &MockCUConversation `RTTI Type Descriptor');
  if ( !v11 )
    goto LABEL_14;
  Instance = (__int64 *)Microsoft::Bing::LanguageUnderstanding::Client::MockCuOutputCreator::GetInstance(&v66);
  v13 = *Instance;
  v14 = Instance[1];
  *Instance = 0;
  Instance[1] = 0;
  *(_QWORD *)(a1 + 80) = v13;
  v15 = *(std::_Ref_count_base **)(a1 + 88);
  *(_QWORD *)(a1 + 88) = v14;
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( *(_QWORD *)v66.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v66.Data4);
  v16 = *(_QWORD *)(a1 + 80);
  v17 = *(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v16 + 8LL);
  v66 = 0;
  pv = 0;
  std::vector<Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse>::_Construct_n<Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &,Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &>(
    &v66,
    0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v11 + 512) - *(_QWORD *)(v11 + 504)) >> 4));
  v18 = v17(v16, &v66);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
      (const char *)(unsigned int)v18,
      0);
    return v19;
  }
  else
  {
LABEL_14:
    Halsey::swstring::UUIDToString(v64, *(_QWORD *)v6 + 200LL);
    Halsey::swstring::UUIDToString(v62, *(_QWORD *)v6 + 216LL);
    std::wstring::wstring(&v66, L"D.NLAPI");
    Microsoft::Bing::Platform::Logging::PropertyObject::CreateInstance(&v58, &v66);
    std::wstring::_Tidy_deallocate(&v66);
    v21 = v58;
    v22 = Halsey::swstring::c_strsafe((Halsey::swstring *)v64);
    std::wstring::wstring(v73, v22);
    std::wstring::wstring(&v70, L"RequestConversationID");
    Microsoft::Bing::Platform::Logging::PropertyObject::AddString(v21, &v70, v73);
    std::wstring::_Tidy_deallocate(&v70);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v74);
    std::wstring::wstring(v73, L"ApplicationId");
    LODWORD(v21) = Bing::Speech::ReadProperty<std::wstring>(*(_QWORD *)(a1 + 7168), v73, v74);
    std::wstring::_Tidy_deallocate(v73);
    if ( (int)v21 >= 0 )
    {
      v23 = v58;
      std::wstring::wstring(v73, L"ApplicationID");
      Microsoft::Bing::Platform::Logging::PropertyObject::AddString(v23, v73, v74);
      std::wstring::_Tidy_deallocate(v73);
    }
    v24 = v58;
    ClientID = (Halsey::swstring *)Microsoft::Bing::LanguageUnderstanding::Client::GetClientID(&v66);
    v26 = Halsey::swstring::c_strsafe(ClientID);
    std::wstring::wstring(&v70, v26);
    std::wstring::wstring(v73, L"RequestClientID");
    Microsoft::Bing::Platform::Logging::PropertyObject::AddString(v24, v73, &v70);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::_Tidy_deallocate(&v70);
    if ( *(_QWORD *)v66.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v66.Data4);
    v27 = v58;
    v70 = L"Invalid";
    *(_QWORD *)&v66.Data1 = &std::_Func_impl_no_alloc<_lambda_4c711cb21c7115867863b2d1a95cd84f_,void,int,unsigned short const *>::`vftable';
    *(_QWORD *)v66.Data4 = *(_QWORD *)v6;
    pv = &v70;
    v69 = &v66;
    Halsey::CuInputBase::LockStateMap(&v66);
    std::wstring::wstring(v75, v70);
    std::wstring::wstring(v73, L"LockScreenState");
    Microsoft::Bing::Platform::Logging::PropertyObject::AddString(v27, v73, v75);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::_Tidy_deallocate(v75);
    Microsoft::Bing::Platform::Logging::DataSourceEvent::CreateInstance(&v60);
    v28 = v60;
    v29 = Halsey::swstring::c_strsafe((Halsey::swstring *)v62);
    std::wstring::wstring(v75, v29);
    std::wstring::operator=(v28 + 72, v75);
    std::wstring::_Tidy_deallocate(v75);
    v30 = std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(&v66, &v58);
    Microsoft::Bing::Platform::Logging::DataSourceEvent::AddProperty(v31, v30);
    v32 = std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(&v66, &v60);
    Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(a1, v32);
    std::wstring::wstring(v72);
    Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::GetInstance(&v66);
    v33 = Halsey::swstring::c_str((Halsey::swstring *)(a1 + 7680));
    v35 = Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::Create(
            *v34,
            (__int64)v33,
            (__int64 *)(a1 + 48),
            (__int64)v72);
    if ( *(_QWORD *)v66.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v66.Data4);
    if ( v35 >= 0 )
    {
      v36 = (const unsigned __int16 *)v72;
      if ( v72[3] > (unsigned __int16 *)7 )
        v36 = v72[0];
      Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession::ClientContext(v4, v36);
      FileCaptureBase::FileCaptureBase((FileCaptureBase *)v76);
      v76[0] = &Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCapture::`vftable';
      if ( FileCaptureBase::Open((FileCaptureBase *)v76, 0) >= 0 )
      {
        v80 = 0;
        v83 = 0;
        v81 = &v84;
        v82 = 260;
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, L"Conversation ID: ");
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, (const struct Halsey::swstring *)v64);
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, L"\r\n");
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, L"Impression ID: ");
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, (const struct Halsey::swstring *)v62);
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, L"\r\n");
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, L"\r\n");
        Halsey::swstring::swstring(&v70, v72);
        Halsey::StringBuilder::append((Halsey::StringBuilder *)&v80, (const struct Halsey::swstring *)&v70);
        if ( v71 )
          std::_Ref_count_base::_Decref(v71);
        Halsey::StringBuilder::to_str(&v80, &v66);
        v37 = Halsey::swstring::c_str((Halsey::swstring *)&v66);
        FileCaptureBase::Write((FileCaptureBase *)v76, v37, 2 * v38);
        FileCaptureBase::Close((FileCaptureBase *)v76);
        if ( *(_QWORD *)v66.Data4 )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v66.Data4);
        Halsey::StringBuilder::~StringBuilder((Halsey::StringBuilder *)&v80);
      }
      std::variant_ext::variant_ext((std::variant_ext *)v78);
      v78[0] = 6;
      v79 = *(_OWORD *)(*(_QWORD *)v6 + 216LL);
      v39 = *(_QWORD *)(a1 + 7168);
      v40 = *(__int64 (__fastcall **)(__int64, _BYTE *, _DWORD *))(*(_QWORD *)v39 + 16LL);
      std::wstring::wstring(v75, L"ImpressionId");
      v41 = v40(v39, v75, v78);
      std::wstring::_Tidy_deallocate(v75);
      if ( v41 >= 0 )
      {
        v79 = *(_OWORD *)(*(_QWORD *)v6 + 200LL);
        v42 = *(_QWORD *)(a1 + 7168);
        v43 = *(__int64 (__fastcall **)(__int64, _BYTE *, _DWORD *))(*(_QWORD *)v42 + 16LL);
        std::wstring::wstring(v75, L"ConversationId");
        v44 = v43(v42, v75, v78);
        std::wstring::_Tidy_deallocate(v75);
        if ( v44 >= 0 )
        {
          Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession::TransmitClientContext(v4);
          SpPerfTelemetry::CuConversationWrapper_Run_SendClientContext();
          Bing::Speech::TextStream::TextStream(v77, v72);
          v45 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _BYTE *, _QWORD))(**(_QWORD **)(a1 + 7168) + 40LL))(
                  *(_QWORD *)(a1 + 7168),
                  &Bing::Speech::kContentType_ClientContext,
                  v77,
                  0);
          v46 = v45;
          if ( v45 >= 0 )
          {
            v66 = GUID_NULL;
            pv = 0;
            v68 = 0;
            v47 = CSpStreamFormat::AssignFormat(&v66, SPSF_NUM_FORMATS);
            v48 = v47;
            if ( v47 >= 0 )
            {
              memset_0((void *)(a1 + 152), 0, 0x280u);
              si_encode_init();
              v49 = *(_QWORD *)(a1 + 7168);
              v50 = *(__int64 (__fastcall **)(__int64, void **, __int64, _QWORD))(*(_QWORD *)v49 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 7056);
              v51 = v50(v49, &Bing::Speech::kContentType_AudioWave, a1 + 7056, 0);
              v52 = v51;
              if ( v51 >= 0 )
              {
                v53 = (struct tWAVEFORMATEX *)pv;
                v54 = *((unsigned __int16 *)pv + 8) + 18;
                v57 = 0;
                v55 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD, int *))(**(_QWORD **)(a1 + 7056) + 32LL))(
                        *(_QWORD *)(a1 + 7056),
                        pv,
                        v54,
                        &v57);
                v56 = v55;
                if ( v55 >= 0 )
                {
                  if ( v54 == v57 )
                  {
                    Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession::TransmitWaveHeader(v4);
                    FileCaptureBase::Open((FileCaptureBase *)(a1 + 7064), v53);
                    CoTaskMemFree(v53);
                    Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
                    std::variant_ext::~variant_ext((std::variant_ext *)v78);
                    FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
                    std::wstring::_Tidy_deallocate(v72);
                    if ( v61 )
                      std::_Ref_count_base::_Decref(v61);
                    std::wstring::_Tidy_deallocate(v74);
                    if ( v59 )
                      std::_Ref_count_base::_Decref(v59);
                    if ( v63 )
                      std::_Ref_count_base::_Decref(v63);
                    if ( v65 )
                      std::_Ref_count_base::_Decref(v65);
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x170,
                      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
                      (const char *)0x8000FFFFLL,
                      0);
                    CoTaskMemFree(v53);
                    Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
                    std::variant_ext::~variant_ext((std::variant_ext *)v78);
                    FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
                    std::wstring::_Tidy_deallocate(v72);
                    if ( v61 )
                      std::_Ref_count_base::_Decref(v61);
                    std::wstring::_Tidy_deallocate(v74);
                    if ( v59 )
                      std::_Ref_count_base::_Decref(v59);
                    if ( v63 )
                      std::_Ref_count_base::_Decref(v63);
                    if ( v65 )
                      std::_Ref_count_base::_Decref(v65);
                    return 2147549183LL;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x16F,
                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
                    (const char *)(unsigned int)v55,
                    0);
                  CoTaskMemFree(v53);
                  Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
                  std::variant_ext::~variant_ext((std::variant_ext *)v78);
                  FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
                  std::wstring::_Tidy_deallocate(v72);
                  if ( v61 )
                    std::_Ref_count_base::_Decref(v61);
                  std::wstring::_Tidy_deallocate(v74);
                  if ( v59 )
                    std::_Ref_count_base::_Decref(v59);
                  if ( v63 )
                    std::_Ref_count_base::_Decref(v63);
                  if ( v65 )
                    std::_Ref_count_base::_Decref(v65);
                  return v56;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x16B,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
                  (const char *)(unsigned int)v51,
                  0);
                CoTaskMemFree(pv);
                Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
                std::variant_ext::~variant_ext((std::variant_ext *)v78);
                FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
                std::wstring::_Tidy_deallocate(v72);
                if ( v61 )
                  std::_Ref_count_base::_Decref(v61);
                std::wstring::_Tidy_deallocate(v74);
                if ( v59 )
                  std::_Ref_count_base::_Decref(v59);
                if ( v63 )
                  std::_Ref_count_base::_Decref(v63);
                if ( v65 )
                  std::_Ref_count_base::_Decref(v65);
                return v52;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x169,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
                (const char *)(unsigned int)v47,
                0);
              CoTaskMemFree(pv);
              Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
              std::variant_ext::~variant_ext((std::variant_ext *)v78);
              FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
              std::wstring::_Tidy_deallocate(v72);
              if ( v61 )
                std::_Ref_count_base::_Decref(v61);
              std::wstring::_Tidy_deallocate(v74);
              if ( v59 )
                std::_Ref_count_base::_Decref(v59);
              if ( v63 )
                std::_Ref_count_base::_Decref(v63);
              if ( v65 )
                std::_Ref_count_base::_Decref(v65);
              return v48;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x166,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
              (const char *)(unsigned int)v45,
              0);
            Bing::Speech::TextStream::~TextStream((Bing::Speech::TextStream *)v77);
            std::variant_ext::~variant_ext((std::variant_ext *)v78);
            FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
            std::wstring::_Tidy_deallocate(v72);
            if ( v61 )
              std::_Ref_count_base::_Decref(v61);
            std::wstring::_Tidy_deallocate(v74);
            if ( v59 )
              std::_Ref_count_base::_Decref(v59);
            if ( v63 )
              std::_Ref_count_base::_Decref(v63);
            if ( v65 )
              std::_Ref_count_base::_Decref(v65);
            return v46;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x160,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
            (const char *)(unsigned int)v44,
            0);
          std::variant_ext::~variant_ext((std::variant_ext *)v78);
          FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
          std::wstring::_Tidy_deallocate(v72);
          if ( v61 )
            std::_Ref_count_base::_Decref(v61);
          std::wstring::_Tidy_deallocate(v74);
          if ( v59 )
            std::_Ref_count_base::_Decref(v59);
          if ( v63 )
            std::_Ref_count_base::_Decref(v63);
          if ( v65 )
            std::_Ref_count_base::_Decref(v65);
          return (unsigned int)v44;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
          (const char *)(unsigned int)v41,
          0);
        std::variant_ext::~variant_ext((std::variant_ext *)v78);
        FileCaptureBase::~FileCaptureBase((FileCaptureBase *)v76);
        std::wstring::_Tidy_deallocate(v72);
        if ( v61 )
          std::_Ref_count_base::_Decref(v61);
        std::wstring::_Tidy_deallocate(v74);
        if ( v59 )
          std::_Ref_count_base::_Decref(v59);
        if ( v63 )
          std::_Ref_count_base::_Decref(v63);
        if ( v65 )
          std::_Ref_count_base::_Decref(v65);
        return (unsigned int)v41;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\cuconversationwrapper.cpp",
        (const char *)(unsigned int)v35,
        0);
      std::wstring::_Tidy_deallocate(v72);
      if ( v61 )
        std::_Ref_count_base::_Decref(v61);
      std::wstring::_Tidy_deallocate(v74);
      if ( v59 )
        std::_Ref_count_base::_Decref(v59);
      if ( v63 )
        std::_Ref_count_base::_Decref(v63);
      if ( v65 )
        std::_Ref_count_base::_Decref(v65);
      return (unsigned int)v35;
    }
  }
}

```

## disassembly

```asm
0x180027418  mov     [rsp+arg_10], rbx
0x18002741d  push    rsi
0x18002741e  push    rdi
0x18002741f  push    r12
0x180027421  push    r14
0x180027423  push    r15
0x180027425  sub     rsp, 490h
0x18002742c  mov     rax, cs:__security_cookie
0x180027433  xor     rax, rsp
0x180027436  mov     [rsp+4B8h+var_38], rax
0x18002743e  mov     rbx, rdx
0x180027441  mov     rsi, rcx
0x180027444  lea     r12, [rcx+1C10h]
0x18002744b  mov     rcx, r12; this
0x18002744e  call    ?StartRunOnce@CuConversationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXXZ; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::CuConversationSession::StartRunOnce(void)
0x180027453  call    ?CuConversationWrapper_Run_Enter@SpPerfTelemetry@@SAXXZ; SpPerfTelemetry::CuConversationWrapper_Run_Enter(void)
0x180027458  lea     rdx, [rsi+68h]
0x18002745c  lea     rcx, [rsp+4B8h+var_440]
0x180027461  call    ??0?$shared_ptr@UIJsonValue@Speech@Bing@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(std::shared_ptr<Bing::Speech::IJsonValue> const &)
0x180027466  mov     rdx, rax
0x180027469  mov     rcx, rsi
0x18002746c  call    ?PushInstrumentationEvent@CuConversationWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAXV?$shared_ptr@VInstrumentationClientEvent@Logging@Platform@Bing@Microsoft@@@std@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(std::shared_ptr<Microsoft::Bing::Platform::Logging::InstrumentationClientEvent>)
0x180027471  lea     rdi, [rsi+30h]
0x180027475  mov     rdx, [rdi]
0x180027478  add     rdx, 198h
0x18002747f  lea     rcx, [rsp+4B8h+var_400]
0x180027487  call    ?MakeLanguageTagDataSource@Client@LanguageUnderstanding@Bing@Microsoft@@YA?AV?$shared_ptr@VDataSourceEvent@Logging@Platform@Bing@Microsoft@@@std@@AEAVswstring@Halsey@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::MakeLanguageTagDataSource(Halsey::swstring &)
0x18002748c  nop
0x18002748d  xorps   xmm0, xmm0
0x180027490  movdqu  xmmword ptr [rsp+4B8h+var_440.Data1], xmm0
0x180027496  mov     rcx, [rax]
0x180027499  mov     qword ptr [rsp+4B8h+var_440.Data1], rcx
0x18002749e  mov     rcx, [rax+8]
0x1800274a2  mov     qword ptr [rsp+4B8h+var_440.Data4], rcx
0x1800274aa  mov     qword ptr [rax], 0
0x1800274b1  mov     qword ptr [rax+8], 0
0x1800274b9  lea     rdx, [rsp+4B8h+var_440]
0x1800274be  mov     rcx, rsi
0x1800274c1  call    ?PushInstrumentationEvent@CuConversationWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAXV?$shared_ptr@VInstrumentationClientEvent@Logging@Platform@Bing@Microsoft@@@std@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(std::shared_ptr<Microsoft::Bing::Platform::Logging::InstrumentationClientEvent>)
0x1800274c6  nop
0x1800274c7  mov     rcx, [rsp+4B8h+var_3F8]; this
0x1800274cf  test    rcx, rcx
0x1800274d2  jz      short loc_1800274D9
0x1800274d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800274d9  mov     rax, [rbx+8]
0x1800274dd  test    rax, rax
0x1800274e0  jz      short loc_1800274E6
0x1800274e2  lock inc dword ptr [rax+8]
0x1800274e6  mov     rdx, [rbx+8]
0x1800274ea  mov     rax, [rbx]
0x1800274ed  mov     [rsi+1C00h], rax
0x1800274f4  mov     rcx, [rsi+1C08h]; this
0x1800274fb  mov     [rsi+1C08h], rdx
0x180027502  test    rcx, rcx
0x180027505  jz      short loc_18002750C
0x180027507  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002750c  mov     [rsp+4B8h+var_498], 0; int
0x180027514  lea     r9, ??_R0?AVMockCUConversation@@@8; MockCUConversation `RTTI Type Descriptor'
0x18002751b  lea     r8, ??_R0?AVIConversation@Speech@Bing@@@8; Bing::Speech::IConversation `RTTI Type Descriptor'
0x180027522  xor     edx, edx
0x180027524  mov     rcx, [rsi+1C00h]
0x18002752b  call    __RTDynamicCast_0
0x180027530  mov     rbx, rax
0x180027533  test    rax, rax
0x180027536  jz      loc_18002760A
0x18002753c  lea     rcx, [rsp+4B8h+var_440]
0x180027541  call    ?GetInstance@MockCuOutputCreator@Client@LanguageUnderstanding@Bing@Microsoft@@SA?AV?$shared_ptr@VMockCuOutputCreator@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@XZ; Microsoft::Bing::LanguageUnderstanding::Client::MockCuOutputCreator::GetInstance(void)
0x180027546  mov     rcx, [rax]
0x180027549  mov     rdx, [rax+8]
0x18002754d  mov     qword ptr [rax], 0
0x180027554  mov     qword ptr [rax+8], 0
0x18002755c  mov     [rsi+50h], rcx
0x180027560  mov     rcx, [rsi+58h]; this
0x180027564  mov     [rsi+58h], rdx
0x180027568  test    rcx, rcx
0x18002756b  jz      short loc_180027572
0x18002756d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027572  mov     rcx, qword ptr [rsp+4B8h+var_440.Data4]; this
0x18002757a  test    rcx, rcx
0x18002757d  jz      short loc_180027584
0x18002757f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027584  mov     r14, [rsi+50h]
0x180027588  mov     rax, [r14]
0x18002758b  mov     r15, [rax+8]
0x18002758f  xorps   xmm0, xmm0
0x180027592  movdqu  xmmword ptr [rsp+4B8h+var_440.Data1], xmm0
0x180027598  mov     [rsp+4B8h+pv], 0
0x1800275a4  lea     r8, [rbx+1F8h]
0x1800275ab  lea     r9, [r8+8]
0x1800275af  mov     rdx, [r9]
0x1800275b2  sub     rdx, [r8]
0x1800275b5  sar     rdx, 4
0x1800275b9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800275c3  imul    rdx, rax
0x1800275c7  lea     rcx, [rsp+4B8h+var_440]
0x1800275cc  call    ??$_Construct_n@AEBQEAUConversationResponse@Client@LanguageUnderstanding@Bing@Microsoft@@AEBQEAU12345@@?$vector@UConversationResponse@Client@LanguageUnderstanding@Bing@Microsoft@@V?$allocator@UConversationResponse@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@@std@@AEAAX_KAEBQEAUConversationResponse@Client@LanguageUnderstanding@Bing@Microsoft@@1@Z; std::vector<Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse>::_Construct_n<Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &,Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &>(unsigned __int64,Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &,Microsoft::Bing::LanguageUnderstanding::Client::ConversationResponse * const &)
0x1800275d1  lea     rdx, [rsp+4B8h+var_440]
0x1800275d6  mov     rcx, r14
0x1800275d9  mov     rax, r15
0x1800275dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275e1  mov     ebx, eax
0x1800275e3  test    eax, eax
0x1800275e5  jns     short loc_18002760A
0x1800275e7  mov     rcx, [rsp+4B8h]; this
0x1800275ef  mov     r9d, eax; char *
0x1800275f2  lea     r8, aOnecoreuapEndu_230; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800275f9  mov     edx, 12Bh; void *
0x1800275fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027603  mov     eax, ebx
0x180027605  jmp     loc_180028322
0x18002760a  mov     rdx, [rdi]
0x18002760d  add     rdx, 0C8h
0x180027614  lea     rcx, [rsp+4B8h+var_450]
0x180027619  call    ?UUIDToString@swstring@Halsey@@SA?AV12@AEBU_GUID@@_N@Z; Halsey::swstring::UUIDToString(_GUID const &,bool)
0x18002761e  nop
0x18002761f  mov     rdx, [rdi]
0x180027622  add     rdx, 0D8h
0x180027629  lea     rcx, [rsp+4B8h+var_460]
0x18002762e  call    ?UUIDToString@swstring@Halsey@@SA?AV12@AEBU_GUID@@_N@Z; Halsey::swstring::UUIDToString(_GUID const &,bool)
0x180027633  nop
0x180027634  lea     rdx, aDNlapi; "D.NLAPI"
0x18002763b  lea     rcx, [rsp+4B8h+var_440]
0x180027640  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027645  nop
0x180027646  lea     rdx, [rsp+4B8h+var_440]
0x18002764b  lea     rcx, [rsp+4B8h+var_480]
0x180027650  call    ?CreateInstance@PropertyObject@Logging@Platform@Bing@Microsoft@@SA?AV?$shared_ptr@VPropertyObject@Logging@Platform@Bing@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Bing::Platform::Logging::PropertyObject::CreateInstance(std::wstring const &)
0x180027655  nop
0x180027656  lea     rcx, [rsp+4B8h+var_440]
0x18002765b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027660  mov     rbx, [rsp+4B8h+var_480]
0x180027665  lea     rcx, [rsp+4B8h+var_450]; this
0x18002766a  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x18002766f  mov     rdx, rax
0x180027672  lea     rcx, [rsp+4B8h+var_3C0]
0x18002767a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002767f  nop
0x180027680  lea     rdx, aRequestconvers; "RequestConversationID"
0x180027687  lea     rcx, [rsp+4B8h+var_400]
0x18002768f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027694  nop
0x180027695  lea     r8, [rsp+4B8h+var_3C0]
0x18002769d  lea     rdx, [rsp+4B8h+var_400]
0x1800276a5  mov     rcx, rbx
0x1800276a8  call    ?AddString@PropertyObject@Logging@Platform@Bing@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Bing::Platform::Logging::PropertyObject::AddString(std::wstring const &,std::wstring const &)
0x1800276ad  nop
0x1800276ae  lea     rcx, [rsp+4B8h+var_400]
0x1800276b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276bb  nop
0x1800276bc  lea     rcx, [rsp+4B8h+var_3C0]
0x1800276c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800276c9  lea     rcx, [rsp+4B8h+var_3A0]
0x1800276d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800276d6  nop
0x1800276d7  lea     rdx, aApplicationid; "ApplicationId"
0x1800276de  lea     rcx, [rsp+4B8h+var_3C0]
0x1800276e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800276eb  nop
0x1800276ec  lea     r8, [rsp+4B8h+var_3A0]
0x1800276f4  lea     rdx, [rsp+4B8h+var_3C0]
0x1800276fc  mov     rcx, [rsi+1C00h]
0x180027703  call    ??$ReadProperty@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Speech@Bing@@YAJPEAVINameValueCollection@01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; Bing::Speech::ReadProperty<std::wstring>(Bing::Speech::INameValueCollection *,std::wstring const &,std::wstring &)
0x180027708  mov     ebx, eax
0x18002770a  lea     rcx, [rsp+4B8h+var_3C0]
0x180027712  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027717  shr     ebx, 1Fh
0x18002771a  xor     bl, 1
0x18002771d  jz      short loc_18002775F
0x18002771f  mov     rbx, [rsp+4B8h+var_480]
0x180027724  lea     rdx, aApplicationid_0; "ApplicationID"
0x18002772b  lea     rcx, [rsp+4B8h+var_3C0]
0x180027733  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027738  nop
0x180027739  lea     r8, [rsp+4B8h+var_3A0]
0x180027741  lea     rdx, [rsp+4B8h+var_3C0]
0x180027749  mov     rcx, rbx
0x18002774c  call    ?AddString@PropertyObject@Logging@Platform@Bing@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Bing::Platform::Logging::PropertyObject::AddString(std::wstring const &,std::wstring const &)
0x180027751  nop
0x180027752  lea     rcx, [rsp+4B8h+var_3C0]
0x18002775a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002775f  mov     rbx, [rsp+4B8h+var_480]
0x180027764  lea     rcx, [rsp+4B8h+var_440]
0x180027769  call    ?GetClientID@Client@LanguageUnderstanding@Bing@Microsoft@@YA?AVswstring@Halsey@@XZ; Microsoft::Bing::LanguageUnderstanding::Client::GetClientID(void)
0x18002776e  nop
0x18002776f  mov     rcx, rax; this
0x180027772  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x180027777  mov     rdx, rax
0x18002777a  lea     rcx, [rsp+4B8h+var_400]
0x180027782  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027787  nop
0x180027788  lea     rdx, aRequestclienti; "RequestClientID"
0x18002778f  lea     rcx, [rsp+4B8h+var_3C0]
0x180027797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002779c  nop
0x18002779d  lea     r8, [rsp+4B8h+var_400]
0x1800277a5  lea     rdx, [rsp+4B8h+var_3C0]
0x1800277ad  mov     rcx, rbx
0x1800277b0  call    ?AddString@PropertyObject@Logging@Platform@Bing@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Bing::Platform::Logging::PropertyObject::AddString(std::wstring const &,std::wstring const &)
0x1800277b5  nop
0x1800277b6  lea     rcx, [rsp+4B8h+var_3C0]
0x1800277be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277c3  nop
0x1800277c4  lea     rcx, [rsp+4B8h+var_400]
0x1800277cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800277d1  nop
0x1800277d2  mov     rcx, qword ptr [rsp+4B8h+var_440.Data4]; this
0x1800277da  test    rcx, rcx
0x1800277dd  jz      short loc_1800277E4
0x1800277df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800277e4  mov     rbx, [rsp+4B8h+var_480]
0x1800277e9  lea     rax, aInvalid; "Invalid"
0x1800277f0  mov     [rsp+4B8h+var_400], rax
0x1800277f8  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4c711cb21c7115867863b2d1a95cd84f_@@XHPEBG@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4c711cb21c7115867863b2d1a95cd84f_,void,int,ushort const *>::`vftable'
0x1800277ff  mov     qword ptr [rsp+4B8h+var_440.Data1], rax
0x180027804  mov     rax, [rdi]
0x180027807  mov     qword ptr [rsp+4B8h+var_440.Data4], rax
0x18002780f  lea     rax, [rsp+4B8h+var_400]
0x180027817  mov     [rsp+4B8h+pv], rax
0x18002781f  lea     rax, [rsp+4B8h+var_440]
0x180027824  mov     [rsp+4B8h+var_408], rax
0x18002782c  lea     rcx, [rsp+4B8h+var_440]
0x180027831  call    ?LockStateMap@CuInputBase@Halsey@@SAXV?$function@$$A6AXHPEBG@Z@std@@@Z; Halsey::CuInputBase::LockStateMap(std::function<void (int,ushort const *)>)
0x180027836  mov     rdx, [rsp+4B8h+var_400]
0x18002783e  lea     rcx, [rsp+4B8h+var_380]
0x180027846  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002784b  nop
0x18002784c  lea     rdx, aLockscreenstat; "LockScreenState"
0x180027853  lea     rcx, [rsp+4B8h+var_3C0]
0x18002785b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027860  nop
0x180027861  lea     r8, [rsp+4B8h+var_380]
0x180027869  lea     rdx, [rsp+4B8h+var_3C0]
0x180027871  mov     rcx, rbx
0x180027874  call    ?AddString@PropertyObject@Logging@Platform@Bing@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Bing::Platform::Logging::PropertyObject::AddString(std::wstring const &,std::wstring const &)
0x180027879  nop
0x18002787a  lea     rcx, [rsp+4B8h+var_3C0]
0x180027882  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027887  nop
0x180027888  lea     rcx, [rsp+4B8h+var_380]
0x180027890  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027895  lea     rcx, [rsp+4B8h+var_470]
0x18002789a  call    ?CreateInstance@DataSourceEvent@Logging@Platform@Bing@Microsoft@@SA?AV?$shared_ptr@VDataSourceEvent@Logging@Platform@Bing@Microsoft@@@std@@XZ; Microsoft::Bing::Platform::Logging::DataSourceEvent::CreateInstance(void)
0x18002789f  nop
0x1800278a0  mov     rbx, [rsp+4B8h+var_470]
0x1800278a5  lea     rcx, [rsp+4B8h+var_460]; this
0x1800278aa  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x1800278af  mov     rdx, rax
0x1800278b2  lea     rcx, [rsp+4B8h+var_380]
0x1800278ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800278bf  nop
0x1800278c0  lea     rcx, [rbx+48h]
0x1800278c4  lea     rdx, [rsp+4B8h+var_380]
0x1800278cc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800278d1  nop
0x1800278d2  lea     rcx, [rsp+4B8h+var_380]
0x1800278da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800278df  mov     r8, [rsp+4B8h+var_470]
0x1800278e4  lea     rdx, [rsp+4B8h+var_480]
0x1800278e9  lea     rcx, [rsp+4B8h+var_440]
0x1800278ee  call    ??0?$shared_ptr@UIJsonValue@Speech@Bing@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(std::shared_ptr<Bing::Speech::IJsonValue> const &)
0x1800278f3  mov     rdx, rax
0x1800278f6  mov     rcx, r8
0x1800278f9  call    ?AddProperty@DataSourceEvent@Logging@Platform@Bing@Microsoft@@QEAAXV?$shared_ptr@VPropertyObject@Logging@Platform@Bing@Microsoft@@@std@@@Z; Microsoft::Bing::Platform::Logging::DataSourceEvent::AddProperty(std::shared_ptr<Microsoft::Bing::Platform::Logging::PropertyObject>)
0x1800278fe  lea     rdx, [rsp+4B8h+var_470]
0x180027903  lea     rcx, [rsp+4B8h+var_440]
0x180027908  call    ??0?$shared_ptr@UIJsonValue@Speech@Bing@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(std::shared_ptr<Bing::Speech::IJsonValue> const &)
0x18002790d  mov     rdx, rax
0x180027910  mov     rcx, rsi
0x180027913  call    ?PushInstrumentationEvent@CuConversationWrapper@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAXV?$shared_ptr@VInstrumentationClientEvent@Logging@Platform@Bing@Microsoft@@@std@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::CuConversationWrapper::PushInstrumentationEvent(std::shared_ptr<Microsoft::Bing::Platform::Logging::InstrumentationClientEvent>)
0x180027918  lea     rcx, [rsp+4B8h+var_3E0]
0x180027920  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027925  nop
0x180027926  lea     rcx, [rsp+4B8h+var_440]
0x18002792b  call    ?GetInstance@ClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@SA?AV?$shared_ptr@VClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@XZ; Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::GetInstance(void)
0x180027930  mov     r10, rax
0x180027933  lea     rcx, [rsi+1E00h]; this
0x18002793a  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x18002793f  lea     r9, [rsp+4B8h+var_3E0]
0x180027947  mov     r8, rdi
0x18002794a  mov     rdx, rax
0x18002794d  mov     rcx, [r10]
0x180027950  call    ?Create@ClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJPEBGAEAV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::Create(ushort const *,std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> &,std::wstring &)
0x180027955  mov     ebx, eax
0x180027957  mov     rcx, qword ptr [rsp+4B8h+var_440.Data4]; this
0x18002795f  test    rcx, rcx
0x180027962  jz      short loc_180027969
0x180027964  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027969  test    ebx, ebx
0x18002796b  jns     short loc_1800279EC
0x18002796d  mov     rcx, [rsp+4B8h]; this
0x180027975  mov     r9d, ebx; char *
0x180027978  lea     r8, aOnecoreuapEndu_230; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18002797f  mov     edx, 143h; void *
0x180027984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027989  nop
0x18002798a  lea     rcx, [rsp+4B8h+var_3E0]
0x180027992  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027997  nop
0x180027998  mov     rcx, [rsp+4B8h+var_468]; this
0x18002799d  test    rcx, rcx
  ... truncated ...
```
