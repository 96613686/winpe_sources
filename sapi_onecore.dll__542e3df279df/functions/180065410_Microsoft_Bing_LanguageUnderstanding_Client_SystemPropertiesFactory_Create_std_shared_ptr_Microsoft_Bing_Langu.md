# Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::Create(std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> &,std::shared_ptr<Halsey::SystemProperties> &)

- ea: `0x180065410`
- end: `0x180065dff`
- name: `?Create@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJAEAV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@AEAV?$shared_ptr@VSystemProperties@Halsey@@@7@@Z`
- size: `2543`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028994`

## callees

- `0x180021944`
- `0x180026508`
- `0x18002895c`
- `0x18003151c`
- `0x180034084`
- `0x18004baec`
- `0x18004c01c`
- `0x180056644`
- `0x1800567c4`
- `0x180057e28`
- `0x180064274`
- `0x180065410`
- `0x180065e08`
- `0x180065ebc`
- `0x180065f40`
- `0x180065fc4`
- `0x180079e30`
- `0x18007aae4`
- `0x1800a773c`
- `0x1801da93c`
- `0x1801da9f8`
- `0x1801dac28`
- `0x1801dacb8`
- `0x180263200`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800657e9`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800657e9`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18006578f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18006578f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006594b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065b60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006594b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180065b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065a78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065aba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065a78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065aba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065ae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065ae6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800658cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800658cc`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800657bb`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800657bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180065829`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180065829`

## string_xrefs

- `0x180065466`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`
- `0x1800654b9`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`
- `0x1800654ed`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`
- `0x1800659fe`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`
- `0x180065a37`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`
- `0x180065aa3`: `onecoreuap\enduser\nui\onecore\sapi\sapi\rnl\src\systempropertiesfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::Create(
        __int64 a1,
        struct _FILETIME **a2,
        struct _FILETIME **a3)
{
  int OsInformation; // r14d
  __int64 v7; // rdx
  int v9; // eax
  unsigned int v10; // r13d
  int DeviceFamily; // eax
  struct _FILETIME *v12; // r11
  __int64 v13; // rdx
  __int64 v14; // r11
  struct _FILETIME v15; // rax
  std::_Ref_count_base *v16; // rdx
  std::_Ref_count_base *v17; // rcx
  __int64 v18; // rax
  struct _FILETIME v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  struct _FILETIME v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  std::_Ref_count_base *v26; // rcx
  struct _FILETIME v27; // r8
  __int64 v28; // rax
  __int64 v29; // rdx
  std::_Ref_count_base *v30; // rcx
  struct _FILETIME v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  std::_Ref_count_base *v34; // rcx
  struct _FILETIME v35; // r8
  __int64 v36; // rax
  __int64 v37; // rdx
  std::_Ref_count_base *v38; // rcx
  struct _FILETIME v39; // r8
  __int64 v40; // rax
  __int64 v41; // rdx
  std::_Ref_count_base *v42; // rcx
  struct _FILETIME v43; // rbx
  const WCHAR *v44; // rax
  struct _FILETIME v45; // rbx
  struct _FILETIME v46; // rbx
  PWSTR v47; // rax
  __int64 v48; // rcx
  int Value; // eax
  char v50; // dl
  struct _FILETIME *v51; // rcx
  struct _FILETIME v52; // r8
  struct _FILETIME v53; // rax
  struct _FILETIME v54; // rdx
  std::_Ref_count_base *v55; // rcx
  DWORD dwLowDateTime; // ecx
  __int64 v57; // rax
  bool *v58; // rdx
  bool v59; // r8
  int v60; // edx
  int v61; // eax
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v62; // edx
  unsigned int v63; // ebx
  int AudioProperties; // eax
  struct Windows::Media::Speech::Internal::IAudioProperties *v65; // r14
  __int64 (__fastcall *v66)(struct Windows::Media::Speech::Internal::IAudioProperties *, HSTRING *); // rbx
  int v67; // eax
  PCWSTR StringRawBuffer; // rax
  struct _FILETIME *v69; // rbx
  unsigned int v70; // eax
  struct _FILETIME *v71; // rcx
  struct _FILETIME *v72; // r8
  struct _FILETIME v73; // rax
  struct _FILETIME v74; // rdx
  std::_Ref_count_base *v75; // rcx
  struct _FILETIME *v76; // rcx
  struct _FILETIME *v77; // r8
  struct _FILETIME v78; // rax
  struct _FILETIME v79; // rdx
  std::_Ref_count_base *v80; // rcx
  const struct Halsey::swstring *v81; // rdx
  struct _FILETIME *v82; // rax
  int v83; // ebx
  struct _FILETIME *v84; // r8
  struct _FILETIME v85; // rcx
  struct _FILETIME v86; // rdx
  std::_Ref_count_base *v87; // rcx
  const struct Halsey::swstring *v88; // rdx
  struct _FILETIME *v89; // rax
  char v90; // bl
  struct _FILETIME *v91; // r8
  struct _FILETIME v92; // rcx
  struct _FILETIME v93; // rdx
  std::_Ref_count_base *v94; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  _BYTE v97[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int pvData; // [rsp+44h] [rbp-BCh] BYREF
  int v99; // [rsp+48h] [rbp-B8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v101; // [rsp+58h] [rbp-A8h]
  struct Windows::Media::Speech::Internal::IAudioProperties *v102; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall *v104)(); // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v105; // [rsp+78h] [rbp-88h]
  struct SpeechAudioEndpointSelector *v106; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v107[40]; // [rsp+88h] [rbp-78h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v99 = 0;
  OsInformation = Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetOsInformation(
                    (struct Halsey::swstring *)a1,
                    (struct Halsey::swstring *)(a1 + 16),
                    (int)a3);
  if ( OsInformation < 0 )
  {
    v7 = 166;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
      (const char *)(unsigned int)OsInformation,
      pdwType);
    return (unsigned int)OsInformation;
  }
  OsInformation = Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetBuildBranch((struct Halsey::swstring *)(a1 + 40));
  if ( OsInformation < 0 )
  {
    v7 = 167;
    goto LABEL_3;
  }
  v9 = Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetDeviceMakeAndDeviceModel(
         (struct Halsey::swstring *)(a1 + 56),
         (struct Halsey::swstring *)(a1 + 72));
  v10 = v9;
  if ( v9 >= 0 )
  {
    DeviceFamily = Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetDeviceFamily((struct Halsey::swstring *)(a1 + 88));
    pvData = DeviceFamily;
    if ( DeviceFamily >= 0 )
    {
      std::make_shared<Halsey::SystemProperties,>(&SystemTimeAsFileTime);
      v99 = 16;
      v12 = (struct _FILETIME *)SystemTimeAsFileTime;
      *(GUID *)(*(_QWORD *)&SystemTimeAsFileTime + 40LL) = GUID_cd285b00_c8fd_405f_9d07_829e2d7a6e5b;
      v12[12] = SystemTimeAsFileTime;
      v102 = (struct Windows::Media::Speech::Internal::IAudioProperties *)SystemTimeAsFileTime;
      v104 =  Halsey::LgObject::`vcall'{56,{flat}};
      LODWORD(v105) = 0;
      std::_Compressed_pair<void (Halsey::DictationParameters::*)(Halsey::ISerializer *),std::tuple<Halsey::DictationParameters *,std::_Ph<1>>,0>::_Compressed_pair<void (Halsey::DictationParameters::*)(Halsey::ISerializer *),std::tuple<Halsey::DictationParameters *,std::_Ph<1>>,0>(
        v107,
        v13,
        &v104,
        &v102);
      std::function<void (Halsey::ISerializer *)>::operator=<std::_Binder<std::_Unforced,void (Halsey::SystemProperties::*)(Halsey::ISerializer *),Halsey::SystemProperties *,std::_Ph<1> const &>,0>(
        v14 + 120,
        v107);
      v15 = SystemTimeAsFileTime;
      v16 = v101;
      SystemTimeAsFileTime = 0;
      v101 = 0;
      *a3 = (struct _FILETIME *)v15;
      v17 = (std::_Ref_count_base *)a3[1];
      a3[1] = (struct _FILETIME *)v16;
      if ( v17 )
      {
        std::_Ref_count_base::_Decref(v17);
        if ( v101 )
          std::_Ref_count_base::_Decref(v101);
      }
      v18 = Halsey::ActionObjectBase<Halsey::SystemInformationProperties,Halsey::ActionObject>::Create(&v104);
      std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(&(*a3)[25], v18);
      if ( v105 )
        std::_Ref_count_base::_Decref(v105);
      v19 = (*a3)[25];
      v20 = *(_QWORD *)(a1 + 8);
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      v21 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(*(_QWORD *)&v19 + 216LL) = *(_QWORD *)a1;
      v22 = *(std::_Ref_count_base **)(*(_QWORD *)&v19 + 224LL);
      *(_QWORD *)(*(_QWORD *)&v19 + 224LL) = v21;
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      v23 = (*a3)[25];
      v24 = *(_QWORD *)(a1 + 24);
      if ( v24 )
        _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
      v25 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(*(_QWORD *)&v23 + 232LL) = *(_QWORD *)(a1 + 16);
      v26 = *(std::_Ref_count_base **)(*(_QWORD *)&v23 + 240LL);
      *(_QWORD *)(*(_QWORD *)&v23 + 240LL) = v25;
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      *(_DWORD *)(*(_QWORD *)&(*a3)[25] + 248LL) = *(_DWORD *)(a1 + 32);
      v27 = (*a3)[25];
      v28 = *(_QWORD *)(a1 + 64);
      if ( v28 )
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
      v29 = *(_QWORD *)(a1 + 64);
      *(_QWORD *)(*(_QWORD *)&v27 + 272LL) = *(_QWORD *)(a1 + 56);
      v30 = *(std::_Ref_count_base **)(*(_QWORD *)&v27 + 280LL);
      *(_QWORD *)(*(_QWORD *)&v27 + 280LL) = v29;
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      v31 = (*a3)[25];
      v32 = *(_QWORD *)(a1 + 80);
      if ( v32 )
        _InterlockedIncrement((volatile signed __int32 *)(v32 + 8));
      v33 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(*(_QWORD *)&v31 + 288LL) = *(_QWORD *)(a1 + 72);
      v34 = *(std::_Ref_count_base **)(*(_QWORD *)&v31 + 296LL);
      *(_QWORD *)(*(_QWORD *)&v31 + 296LL) = v33;
      if ( v34 )
        std::_Ref_count_base::_Decref(v34);
      v35 = (*a3)[25];
      v36 = *(_QWORD *)(a1 + 96);
      if ( v36 )
        _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
      v37 = *(_QWORD *)(a1 + 96);
      *(_QWORD *)(*(_QWORD *)&v35 + 304LL) = *(_QWORD *)(a1 + 88);
      v38 = *(std::_Ref_count_base **)(*(_QWORD *)&v35 + 312LL);
      *(_QWORD *)(*(_QWORD *)&v35 + 312LL) = v37;
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
      v39 = (*a3)[25];
      v40 = *(_QWORD *)(a1 + 48);
      if ( v40 )
        _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
      v41 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)(*(_QWORD *)&v39 + 256LL) = *(_QWORD *)(a1 + 40);
      v42 = *(std::_Ref_count_base **)(*(_QWORD *)&v39 + 264LL);
      *(_QWORD *)(*(_QWORD *)&v39 + 264LL) = v41;
      if ( v42 )
        std::_Ref_count_base::_Decref(v42);
      v43 = (*a3)[25];
      v44 = Halsey::swstring::c_str((Halsey::swstring *)&(*a2)[51]);
      *(_WORD *)(*(_QWORD *)&v43 + 320LL) = LocaleNameToLCID(v44, 0x8000000u);
      v45 = (*a3)[25];
      memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
      GetTimeZoneInformation(&TimeZoneInformation);
      Halsey::swstring::operator=(*(_QWORD *)&v45 + 328LL, TimeZoneInformation.StandardName);
      v46 = (*a3)[25];
      LOWORD(TimeZoneInformation.Bias) = 0;
      GetUserDefaultLocaleName((LPWSTR)&TimeZoneInformation, 260);
      Halsey::swstring::operator=(*(_QWORD *)&v46 + 344LL, &TimeZoneInformation);
      *(_BYTE *)(*(_QWORD *)&(*a3)[25] + 376LL) = (*a2)[48].dwLowDateTime;
      v97[0] = 0;
      v47 = StrChrW(L"CURRENT_USER\\SOFTWARE\\Microsoft\\Speech_OneCore\\Settings\\SpeechRecognizer", 0x5Cu);
      Value = SpeechPlatform::Settings::Details::RegistryStorage<bool>::GetValue(
                v48,
                v47 + 1,
                L"UseRelaxedRecognition",
                v97);
      v50 = v97[0];
      if ( Value < 0 )
        v50 = 0;
      *(_BYTE *)(*(_QWORD *)&(*a3)[25] + 377LL) = v50;
      v51 = *a2;
      v52 = (*a3)[25];
      v53 = (*a2)[54];
      if ( v53 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v53 + 8LL));
      v54 = v51[54];
      *(struct _FILETIME *)(*(_QWORD *)&v52 + 360LL) = v51[53];
      v55 = *(std::_Ref_count_base **)(*(_QWORD *)&v52 + 368LL);
      *(struct _FILETIME *)(*(_QWORD *)&v52 + 368LL) = v54;
      if ( v55 )
        std::_Ref_count_base::_Decref(v55);
      *(_BYTE *)(*(_QWORD *)&(*a3)[25] + 378LL) = BYTE1((*a2)[48].dwLowDateTime);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v102 = (struct Windows::Media::Speech::Internal::IAudioProperties *)SystemTimeAsFileTime;
      (*a3)[27] = SystemTimeAsFileTime;
      (*a3)[28].dwLowDateTime = (*a2)[48].dwHighDateTime;
      pvData = 6;
      SystemTimeAsFileTime.dwLowDateTime = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Speech\\ClientContextOverrides",
        L"AudioSource",
        0x18u,
        0,
        &pvData,
        (LPDWORD)&SystemTimeAsFileTime);
      dwLowDateTime = pvData;
      if ( pvData == 6 )
        dwLowDateTime = (*a2)[49].dwLowDateTime;
      (*a3)[28].dwHighDateTime = dwLowDateTime;
      v57 = Halsey::ActionObjectBase<Halsey::DataCollection,Halsey::ActionObject>::Create(&v104);
      std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(&(*a3)[45], v57);
      if ( v105 )
        std::_Ref_count_base::_Decref(v105);
      if ( LOBYTE((*a2)[74].dwLowDateTime)
        || (v97[0] = 0,
            SpeechPreferenceUtils::GetSpeechLoggingEnabled((SpeechPreferenceUtils *)v97, v58, v59) == -2147024894)
        || (v60 = 1, !v97[0]) )
      {
        v60 = 0;
      }
      *(_DWORD *)(*(_QWORD *)&(*a3)[45] + 200LL) = v60;
      v106 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v106);
      v61 = Microsoft::WRL::Details::MakeAndInitialize<SpeechAudioEndpointSelector,SpeechAudioEndpointSelector,>(&v106);
      v63 = v61;
      if ( v61 >= 0 )
      {
        v102 = 0;
        AudioProperties = Windows::Media::Speech::Internal::AudioProperties::GetAudioProperties(v106, v62, &v102);
        v63 = AudioProperties;
        if ( AudioProperties >= 0 )
        {
          string = 0;
          v65 = v102;
          v66 = *(__int64 (__fastcall **)(struct Windows::Media::Speech::Internal::IAudioProperties *, HSTRING *))(*(_QWORD *)v102 + 56LL);
          WindowsDeleteString(0);
          string = 0;
          v67 = v66(v65, &string);
          v63 = v67;
          if ( v67 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            Halsey::swstring::operator=(&(*a3)[31], StringRawBuffer);
            (*a3)[29].dwLowDateTime = (*a2)[49].dwHighDateTime;
            (*a3)[30].dwLowDateTime = (*a2)[50].dwLowDateTime;
            v69 = *a3;
            pvData = 0;
            SystemTimeAsFileTime.dwLowDateTime = 4;
            if ( RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\Maps",
                   L"LastModeOfTravel",
                   0x18u,
                   0,
                   &pvData,
                   (LPDWORD)&SystemTimeAsFileTime)
              || (v70 = pvData, pvData >= 4) )
            {
              v70 = 0;
              pvData = 0;
            }
            v69[30].dwHighDateTime = v70;
            LOBYTE((*a3)[35].dwLowDateTime) = (*a2)[50].dwHighDateTime;
            BYTE1((*a3)[35].dwLowDateTime) = BYTE1((*a2)[50].dwHighDateTime);
            HIBYTE((*a3)[35].dwLowDateTime) = BYTE2((*a2)[50].dwHighDateTime);
            v71 = *a2;
            v72 = *a3;
            v73 = (*a2)[63];
            if ( v73 )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v73 + 8LL));
            v74 = v71[63];
            v72[38] = v71[62];
            v75 = (std::_Ref_count_base *)v72[39];
            v72[39] = v74;
            if ( v75 )
              std::_Ref_count_base::_Decref(v75);
            v76 = *a2;
            v77 = *a3;
            v78 = (*a2)[61];
            if ( v78 )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v78 + 8LL));
            v79 = v76[61];
            v77[36] = v76[60];
            v80 = (std::_Ref_count_base *)v77[37];
            v77[37] = v79;
            if ( v80 )
              std::_Ref_count_base::_Decref(v80);
            LOBYTE((*a3)[40].dwLowDateTime) = (*a2)[64].dwLowDateTime;
            v81 = (const struct Halsey::swstring *)&(*a2)[65];
            if ( *(_QWORD *)v81 && *(_QWORD *)(*(_QWORD *)v81 + 16LL) )
            {
              v82 = (struct _FILETIME *)Halsey::swstring::swstring((Halsey::swstring *)&SystemTimeAsFileTime, v81);
              v83 = 17;
            }
            else
            {
              v82 = (struct _FILETIME *)Halsey::swstring::swstring((Halsey::swstring *)&v104, &cchOriginalDestLength);
              v83 = 18;
            }
            v99 = v83;
            v84 = *a3;
            v85 = v82[1];
            if ( v85 )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v85 + 8LL));
            v86 = v82[1];
            v84[41] = *v82;
            v87 = (std::_Ref_count_base *)v84[42];
            v84[42] = v86;
            if ( v87 )
              std::_Ref_count_base::_Decref(v87);
            if ( (v83 & 2) != 0 )
            {
              v83 &= ~2u;
              v99 = v83;
              if ( v105 )
                std::_Ref_count_base::_Decref(v105);
            }
            if ( (v83 & 1) != 0 )
            {
              v83 &= ~1u;
              v99 = v83;
              if ( v101 )
                std::_Ref_count_base::_Decref(v101);
            }
            v88 = (const struct Halsey::swstring *)&(*a2)[67];
            if ( *(_QWORD *)v88 && *(_QWORD *)(*(_QWORD *)v88 + 16LL) )
            {
              v89 = (struct _FILETIME *)Halsey::swstring::swstring((Halsey::swstring *)&SystemTimeAsFileTime, v88);
              v90 = v83 | 4;
            }
            else
            {
              v89 = (struct _FILETIME *)Halsey::swstring::swstring((Halsey::swstring *)&v104, &cchOriginalDestLength);
              v90 = v83 | 8;
            }
            v91 = *a3;
            v92 = v89[1];
            if ( v92 )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v92 + 8LL));
            v93 = v89[1];
            v91[43] = *v89;
            v94 = (std::_Ref_count_base *)v91[44];
            v91[44] = v93;
            if ( v94 )
              std::_Ref_count_base::_Decref(v94);
            if ( (v90 & 8) != 0 )
            {
              v90 &= ~8u;
              if ( v105 )
                std::_Ref_count_base::_Decref(v105);
            }
            if ( (v90 & 4) != 0 && v101 )
              std::_Ref_count_base::_Decref(v101);
            WindowsDeleteString(string);
            string = 0;
            if ( v65 )
              (*(void (__fastcall **)(struct Windows::Media::Speech::Internal::IAudioProperties *))(*(_QWORD *)v65 + 16LL))(v65);
            v63 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCC,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
              (const char *)(unsigned int)v67,
              pdwTypea);
            WindowsDeleteString(string);
            string = 0;
            if ( v65 )
              (*(void (__fastcall **)(struct Windows::Media::Speech::Internal::IAudioProperties *))(*(_QWORD *)v65 + 16LL))(v65);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC9,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
            (const char *)(unsigned int)AudioProperties,
            pdwTypea);
          if ( v102 )
            (*(void (__fastcall **)(struct Windows::Media::Speech::Internal::IAudioProperties *))(*(_QWORD *)v102 + 16LL))(v102);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
          (const char *)(unsigned int)v61,
          pdwTypea);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v106);
      return v63;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
        (const char *)(unsigned int)DeviceFamily,
        pdwType);
      return pvData;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\systempropertiesfactory.cpp",
      (const char *)(unsigned int)v9,
      pdwType);
    return v10;
  }
}

```

## disassembly

```asm
0x180065410  mov     [rsp-8+arg_18], rbx
0x180065415  push    rbp
0x180065416  push    rsi
0x180065417  push    rdi
0x180065418  push    r12
0x18006541a  push    r13
0x18006541c  push    r14
0x18006541e  push    r15
0x180065420  lea     rbp, [rsp-1D0h]
0x180065428  sub     rsp, 2D0h
0x18006542f  mov     rax, cs:__security_cookie
0x180065436  xor     rax, rsp
0x180065439  mov     [rbp+200h+var_40], rax
0x180065440  mov     rdi, r8
0x180065443  mov     rsi, rdx
0x180065446  mov     rbx, rcx
0x180065449  mov     [rsp+300h+var_2B8], 0
0x180065451  lea     rdx, [rcx+10h]; struct Halsey::swstring *
0x180065455  call    ?GetOsInformation@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAVswstring@Halsey@@0H@Z; Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetOsInformation(Halsey::swstring &,Halsey::swstring &,int)
0x18006545a  mov     r14d, eax
0x18006545d  test    eax, eax
0x18006545f  jns     short loc_180065484
0x180065461  mov     edx, 0A6h; void *
0x180065466  lea     r8, aOnecoreuapEndu_208; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18006546d  mov     r9d, r14d; char *
0x180065470  mov     rcx, [rbp+208h]; this
0x180065477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006547c  mov     eax, r14d
0x18006547f  jmp     loc_180065DD5
0x180065484  lea     rcx, [rbx+28h]; struct Halsey::swstring *
0x180065488  call    ?GetBuildBranch@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAVswstring@Halsey@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetBuildBranch(Halsey::swstring &)
0x18006548d  mov     r14d, eax
0x180065490  test    eax, eax
0x180065492  jns     short loc_18006549B
0x180065494  mov     edx, 0A7h
0x180065499  jmp     short loc_180065466
0x18006549b  lea     rdx, [rbx+48h]; struct Halsey::swstring *
0x18006549f  lea     rcx, [rbx+38h]; struct Halsey::swstring *
0x1800654a3  call    ?GetDeviceMakeAndDeviceModel@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAVswstring@Halsey@@0@Z; Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetDeviceMakeAndDeviceModel(Halsey::swstring &,Halsey::swstring &)
0x1800654a8  mov     r13d, eax
0x1800654ab  test    eax, eax
0x1800654ad  jns     short loc_1800654D2
0x1800654af  mov     rcx, [rbp+208h]; this
0x1800654b6  mov     r9d, eax; char *
0x1800654b9  lea     r8, aOnecoreuapEndu_208; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800654c0  mov     edx, 0A8h; void *
0x1800654c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800654ca  mov     eax, r13d
0x1800654cd  jmp     loc_180065DD5
0x1800654d2  lea     rcx, [rbx+58h]; this
0x1800654d6  call    ?GetDeviceFamily@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAVswstring@Halsey@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::GetDeviceFamily(Halsey::swstring &)
0x1800654db  mov     [rsp+300h+var_2BC], eax
0x1800654df  test    eax, eax
0x1800654e1  jns     short loc_180065507
0x1800654e3  mov     rcx, [rbp+208h]; this
0x1800654ea  mov     r9d, eax; char *
0x1800654ed  lea     r8, aOnecoreuapEndu_208; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800654f4  mov     edx, 0A9h; void *
0x1800654f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800654fe  mov     eax, [rsp+300h+var_2BC]
0x180065502  jmp     loc_180065DD5
0x180065507  lea     rcx, [rsp+300h+SystemTimeAsFileTime]
0x18006550c  call    ??$make_shared@VSystemProperties@Halsey@@$$V@std@@YA?AV?$shared_ptr@VSystemProperties@Halsey@@@0@XZ; std::make_shared<Halsey::SystemProperties,>(void)
0x180065511  mov     [rsp+300h+var_2B8], 10h
0x180065519  mov     r11, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x18006551e  movups  xmm0, xmmword ptr cs:_GUID_cd285b00_c8fd_405f_9d07_829e2d7a6e5b.Data1
0x180065525  movdqu  xmmword ptr [r11+28h], xmm0
0x18006552b  mov     rax, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180065530  mov     [r11+60h], rax
0x180065534  mov     rax, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180065539  mov     [rsp+300h+var_2A0], rax
0x18006553e  lea     rax, ??_9LgObject@Halsey@@$BDI@AA; [thunk]: Halsey::LgObject::`vcall'{56,{flat}}
0x180065545  mov     [rsp+300h+var_290], rax
0x18006554a  mov     dword ptr [rsp+300h+var_288], 0
0x180065552  mov     eax, dword ptr [rsp+300h+var_288+4]
0x180065556  mov     dword ptr [rsp+300h+var_288+4], eax
0x18006555a  lea     r9, [rsp+300h+var_2A0]
0x18006555f  lea     r8, [rsp+300h+var_290]
0x180065564  lea     rcx, [rbp+200h+var_278]
0x180065568  call    ??$?0P8DictationParameters@Halsey@@EAAXPEAVISerializer@1@@ZPEAV01@AEBU?$_Ph@$00@std@@@?$_Compressed_pair@P8DictationParameters@Halsey@@EAAXPEAVISerializer@2@@ZV?$tuple@PEAVDictationParameters@Halsey@@U?$_Ph@$00@std@@@std@@$0A@@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAP8DictationParameters@Halsey@@EAAXPEAVISerializer@4@@Z$$QEAPEAV34@AEBU?$_Ph@$00@1@@Z; std::_Compressed_pair<void (Halsey::DictationParameters::*)(Halsey::ISerializer *),std::tuple<Halsey::DictationParameters *,std::_Ph<1>>,0>::_Compressed_pair<void (Halsey::DictationParameters::*)(Halsey::ISerializer *),std::tuple<Halsey::DictationParameters *,std::_Ph<1>>,0>(std::_One_then_variadic_args_t,void (Halsey::DictationParameters::*&&)(Halsey::ISerializer *),Halsey::DictationParameters * &&,std::_Ph<1> const &)
0x18006556d  lea     rcx, [r11+78h]
0x180065571  lea     rdx, [rbp+200h+var_278]
0x180065575  call    ??$?4V?$_Binder@U_Unforced@std@@P8SystemProperties@Halsey@@EAAXPEAVISerializer@4@@ZPEAV34@AEBU?$_Ph@$00@2@@std@@$0A@@?$function@$$A6AXPEAVISerializer@Halsey@@@Z@std@@QEAAAEAV01@$$QEAV?$_Binder@U_Unforced@std@@P8SystemProperties@Halsey@@EAAXPEAVISerializer@4@@ZPEAV34@AEBU?$_Ph@$00@2@@1@@Z; std::function<void (Halsey::ISerializer *)>::operator=<std::_Binder<std::_Unforced,void (Halsey::SystemProperties::*)(Halsey::ISerializer *),Halsey::SystemProperties *,std::_Ph<1> const &>,0>(std::_Binder<std::_Unforced,void (Halsey::SystemProperties::*)(Halsey::ISerializer *),Halsey::SystemProperties *,std::_Ph<1> const &> &&)
0x18006557a  mov     rax, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x18006557f  mov     rdx, [rsp+300h+var_2A8]
0x180065584  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006558d  mov     [rsp+300h+var_2A8], 0
0x180065596  mov     [rdi], rax
0x180065599  mov     rcx, [rdi+8]; this
0x18006559d  mov     [rdi+8], rdx
0x1800655a1  test    rcx, rcx
0x1800655a4  jz      short loc_1800655BA
0x1800655a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800655ab  mov     rcx, [rsp+300h+var_2A8]; this
0x1800655b0  test    rcx, rcx
0x1800655b3  jz      short loc_1800655BA
0x1800655b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800655ba  lea     rcx, [rsp+300h+var_290]
0x1800655bf  call    ?Create@?$ActionObjectBase@VSystemInformationProperties@Halsey@@VActionObject@2@@Halsey@@SA?AV?$shared_ptr@VSystemInformationProperties@Halsey@@@std@@XZ; Halsey::ActionObjectBase<Halsey::SystemInformationProperties,Halsey::ActionObject>::Create(void)
0x1800655c4  mov     rcx, [rdi]
0x1800655c7  add     rcx, 0C8h
0x1800655ce  mov     rdx, rax
0x1800655d1  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x1800655d6  mov     rcx, [rsp+300h+var_288]; this
0x1800655db  test    rcx, rcx
0x1800655de  jz      short loc_1800655E5
0x1800655e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800655e5  mov     rax, [rdi]
0x1800655e8  mov     r8, [rax+0C8h]
0x1800655ef  mov     rax, [rbx+8]
0x1800655f3  test    rax, rax
0x1800655f6  jz      short loc_1800655FC
0x1800655f8  lock inc dword ptr [rax+8]
0x1800655fc  mov     rdx, [rbx+8]
0x180065600  mov     rax, [rbx]
0x180065603  mov     [r8+0D8h], rax
0x18006560a  mov     rcx, [r8+0E0h]; this
0x180065611  mov     [r8+0E0h], rdx
0x180065618  test    rcx, rcx
0x18006561b  jz      short loc_180065622
0x18006561d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065622  mov     rax, [rdi]
0x180065625  mov     r8, [rax+0C8h]
0x18006562c  mov     rcx, [rbx+18h]
0x180065630  test    rcx, rcx
0x180065633  jz      short loc_180065639
0x180065635  lock inc dword ptr [rcx+8]
0x180065639  mov     rdx, [rbx+18h]
0x18006563d  mov     rax, [rbx+10h]
0x180065641  mov     [r8+0E8h], rax
0x180065648  mov     rcx, [r8+0F0h]; this
0x18006564f  mov     [r8+0F0h], rdx
0x180065656  test    rcx, rcx
0x180065659  jz      short loc_180065660
0x18006565b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065660  mov     rax, [rdi]
0x180065663  mov     rcx, [rax+0C8h]
0x18006566a  mov     eax, [rbx+20h]
0x18006566d  mov     [rcx+0F8h], eax
0x180065673  mov     rax, [rdi]
0x180065676  mov     r8, [rax+0C8h]
0x18006567d  mov     rax, [rbx+40h]
0x180065681  test    rax, rax
0x180065684  jz      short loc_18006568A
0x180065686  lock inc dword ptr [rax+8]
0x18006568a  mov     rdx, [rbx+40h]
0x18006568e  mov     rax, [rbx+38h]
0x180065692  mov     [r8+110h], rax
0x180065699  mov     rcx, [r8+118h]; this
0x1800656a0  mov     [r8+118h], rdx
0x1800656a7  xor     r12d, r12d
0x1800656aa  test    rcx, rcx
0x1800656ad  jz      short loc_1800656B4
0x1800656af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800656b4  mov     rax, [rdi]
0x1800656b7  mov     r8, [rax+0C8h]
0x1800656be  mov     rax, [rbx+50h]
0x1800656c2  test    rax, rax
0x1800656c5  jz      short loc_1800656CB
0x1800656c7  lock inc dword ptr [rax+8]
0x1800656cb  mov     rdx, [rbx+50h]
0x1800656cf  mov     rax, [rbx+48h]
0x1800656d3  mov     [r8+120h], rax
0x1800656da  mov     rcx, [r8+128h]; this
0x1800656e1  mov     [r8+128h], rdx
0x1800656e8  test    rcx, rcx
0x1800656eb  jz      short loc_1800656F2
0x1800656ed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800656f2  mov     rax, [rdi]
0x1800656f5  mov     r8, [rax+0C8h]
0x1800656fc  mov     rax, [rbx+60h]
0x180065700  test    rax, rax
0x180065703  jz      short loc_180065709
0x180065705  lock inc dword ptr [rax+8]
0x180065709  mov     rdx, [rbx+60h]
0x18006570d  mov     rax, [rbx+58h]
0x180065711  mov     [r8+130h], rax
0x180065718  mov     rcx, [r8+138h]; this
0x18006571f  mov     [r8+138h], rdx
0x180065726  test    rcx, rcx
0x180065729  jz      short loc_180065730
0x18006572b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065730  mov     rax, [rdi]
0x180065733  mov     r8, [rax+0C8h]
0x18006573a  mov     rax, [rbx+30h]
0x18006573e  test    rax, rax
0x180065741  jz      short loc_180065747
0x180065743  lock inc dword ptr [rax+8]
0x180065747  mov     rdx, [rbx+30h]
0x18006574b  mov     rax, [rbx+28h]
0x18006574f  mov     [r8+100h], rax
0x180065756  mov     rcx, [r8+108h]; this
0x18006575d  mov     [r8+108h], rdx
0x180065764  test    rcx, rcx
0x180065767  jz      short loc_18006576E
0x180065769  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006576e  mov     rax, [rdi]
0x180065771  mov     rbx, [rax+0C8h]
0x180065778  mov     rcx, [rsi]
0x18006577b  add     rcx, 198h; this
0x180065782  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x180065787  mov     rcx, rax; lpName
0x18006578a  mov     edx, 8000000h; dwFlags
0x18006578f  call    cs:__imp_LocaleNameToLCID
0x180065795  mov     [rbx+140h], ax
0x18006579c  mov     rax, [rdi]
0x18006579f  mov     rbx, [rax+0C8h]
0x1800657a6  xor     edx, edx; Val
0x1800657a8  mov     r8d, 0ACh; Size
0x1800657ae  lea     rcx, [rbp+200h+TimeZoneInformation]; void *
0x1800657b2  call    memset_0
0x1800657b7  lea     rcx, [rbp+200h+TimeZoneInformation]; lpTimeZoneInformation
0x1800657bb  call    cs:__imp_GetTimeZoneInformation
0x1800657c1  lea     rdx, [rbp+200h+TimeZoneInformation.StandardName]
0x1800657c5  lea     rcx, [rbx+148h]
0x1800657cc  call    ??4swstring@Halsey@@QEAAAEBV01@PEBG@Z; Halsey::swstring::operator=(ushort const *)
0x1800657d1  mov     rax, [rdi]
0x1800657d4  mov     rbx, [rax+0C8h]
0x1800657db  mov     word ptr [rbp+200h+TimeZoneInformation.Bias], r12w
0x1800657e0  mov     edx, 104h; cchLocaleName
0x1800657e5  lea     rcx, [rbp+200h+TimeZoneInformation]; lpLocaleName
0x1800657e9  call    cs:__imp_GetUserDefaultLocaleName
0x1800657ef  lea     rdx, [rbp+200h+TimeZoneInformation]
0x1800657f3  lea     rcx, [rbx+158h]
0x1800657fa  call    ??4swstring@Halsey@@QEAAAEBV01@PEBG@Z; Halsey::swstring::operator=(ushort const *)
0x1800657ff  mov     rdx, [rsi]
0x180065802  mov     rax, [rdi]
0x180065805  mov     rcx, [rax+0C8h]
0x18006580c  mov     al, [rdx+180h]
0x180065812  mov     [rcx+178h], al
0x180065818  mov     [rsp+300h+var_2C0], r12b
0x18006581d  mov     edx, 5Ch ; '\'; wMatch
0x180065822  lea     rcx, pszStart; "CURRENT_USER\\SOFTWARE\\Microsoft\\Spee"...
0x180065829  call    cs:__imp_StrChrW
0x18006582f  lea     rdx, [rax+2]
0x180065833  lea     r9, [rsp+300h+var_2C0]
0x180065838  lea     r8, aUserelaxedreco; "UseRelaxedRecognition"
0x18006583f  call    ?GetValue@?$RegistryStorage@_N@Details@Settings@SpeechPlatform@@SAJQEAUHKEY__@@QEBG1AEA_N@Z; SpeechPlatform::Settings::Details::RegistryStorage<bool>::GetValue(HKEY__ * const,ushort const * const,ushort const * const,bool &)
0x180065844  movzx   edx, [rsp+300h+var_2C0]
0x180065849  test    eax, eax
0x18006584b  cmovs   edx, r12d
0x18006584f  mov     rax, [rdi]
0x180065852  mov     rcx, [rax+0C8h]
0x180065859  mov     [rcx+179h], dl
0x18006585f  mov     rcx, [rsi]
0x180065862  mov     rax, [rdi]
0x180065865  mov     r8, [rax+0C8h]
0x18006586c  mov     rax, [rcx+1B0h]
0x180065873  test    rax, rax
0x180065876  jz      short loc_18006587C
0x180065878  lock inc dword ptr [rax+8]
0x18006587c  mov     rdx, [rcx+1B0h]
0x180065883  mov     rax, [rcx+1A8h]
0x18006588a  mov     [r8+168h], rax
0x180065891  mov     rcx, [r8+170h]; this
0x180065898  mov     [r8+170h], rdx
0x18006589f  test    rcx, rcx
0x1800658a2  jz      short loc_1800658A9
0x1800658a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800658a9  mov     rdx, [rsi]
0x1800658ac  mov     rax, [rdi]
0x1800658af  mov     rcx, [rax+0C8h]
0x1800658b6  mov     al, [rdx+181h]
0x1800658bc  mov     [rcx+17Ah], al
0x1800658c2  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800658c7  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800658cc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800658d2  mov     ecx, [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x1800658d6  mov     eax, [rsp+300h+SystemTimeAsFileTime.dwHighDateTime]
0x1800658da  mov     dword ptr [rsp+300h+var_2A0+4], eax
0x1800658de  mov     dword ptr [rsp+300h+var_2A0], ecx
0x1800658e2  mov     rcx, [rdi]
0x1800658e5  mov     rax, [rsp+300h+var_2A0]
0x1800658ea  mov     [rcx+0D8h], rax
0x1800658f1  mov     rax, [rsi]
0x1800658f4  mov     rcx, [rdi]
0x1800658f7  mov     eax, [rax+184h]
0x1800658fd  mov     [rcx+0E0h], eax
0x180065903  mov     [rsp+300h+var_2BC], 6
0x18006590b  mov     r15d, 4
0x180065911  mov     [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x180065916  lea     rax, [rsp+300h+SystemTimeAsFileTime]
0x18006591b  mov     [rsp+300h+pcbData], rax; pcbData
0x180065920  lea     rax, [rsp+300h+var_2BC]
0x180065925  mov     [rsp+300h+pvData], rax; pvData
0x18006592a  mov     [rsp+300h+pdwType], r12; int
0x18006592f  lea     r13d, [r15+14h]
0x180065933  mov     r9d, r13d; dwFlags
0x180065936  lea     r8, aAudiosource; "AudioSource"
0x18006593d  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Speech\\ClientCont"...
0x180065944  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18006594b  call    cs:__imp_RegGetValueW
0x180065951  mov     ecx, [rsp+300h+var_2BC]
0x180065955  cmp     ecx, 6
0x180065958  jnz     short loc_180065963
0x18006595a  mov     rax, [rsi]
0x18006595d  mov     ecx, [rax+188h]
0x180065963  mov     rax, [rdi]
0x180065966  mov     [rax+0E4h], ecx
0x18006596c  lea     rcx, [rsp+300h+var_290]
  ... truncated ...
```
