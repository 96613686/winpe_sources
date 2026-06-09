# Windows::RebootDowntime::InputBuilder::PopulateUpdateMetadata(std::vector<std::shared_ptr<Update>,std::allocator<std::shared_ptr<Update>>> const &)

- ea: `0x1800ccaf0`
- end: `0x1800cd6f8`
- name: `?PopulateUpdateMetadata@InputBuilder@RebootDowntime@Windows@@AEAAXAEBV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@@Z`
- size: `3080`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cae90`

## callees

- `0x1800107cc`
- `0x1800108b4`
- `0x180011680`
- `0x180060054`
- `0x1800616ac`
- `0x18006ea28`
- `0x180077944`
- `0x180081858`
- `0x18008cf3c`
- `0x1800ccaf0`
- `0x1800d0c90`
- `0x1800dd930`
- `0x1800e4519`
- `0x1800e4630`

## string_xrefs

- `0x1800cd142`: `numDriverUpdates`
- `0x1800cd193`: `numOtherUpdates`
- `0x1800cd3a5`: `InstallFlowType`
- `0x1800cd2f7`: `totalOtherUpdatesSizeInBytes`
- `0x1800cd0f7`: `numOSLCUUpdates`
- `0x1800cd0aa`: `numFeatureUpdates`
- `0x1800cd50e`: `OtherUpdateCount`
- `0x1800cd4b4`: `DriverUpdateCount`
- `0x1800cd69b`: `OtherUpdateDownloadSize`
- `0x1800cd653`: `DriverUpdateDownloadSize`
- `0x1800ccbab`: `WasCommitEverNeeded`
- `0x1800ccc03`: `WasCommitEverNeeded`
- `0x1800cced7`: `Attempting to set featureUpdateBuildVersionDiff twice.`
- `0x1800ccd01`: `Attempting to set rebootDowntimeSignal twice.`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void __fastcall Windows::RebootDowntime::InputBuilder::PopulateUpdateMetadata(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v4; // r15
  __int64 v5; // r12
  int v6; // r13d
  _QWORD *v7; // rdi
  char v8; // r15
  char v9; // bl
  _QWORD *v10; // rax
  char v11; // bl
  __int64 v12; // rax
  int v13; // r14d
  char v14; // al
  char v15; // r14
  __int64 v16; // r15
  __int64 *System; // rax
  _QWORD *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  volatile signed __int32 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  char v24; // bl
  _QWORD *v25; // rax
  __int64 v26; // rax
  int v27; // ebx
  int v28; // ebx
  __int64 v29; // rax
  _OWORD *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // [rsp+20h] [rbp-E0h]
  char *v52; // [rsp+30h] [rbp-D0h]
  int v53; // [rsp+38h] [rbp-C8h]
  int v54; // [rsp+3Ch] [rbp-C4h]
  __int64 v55; // [rsp+40h] [rbp-C0h]
  __int64 v56; // [rsp+48h] [rbp-B8h]
  __int64 v57; // [rsp+50h] [rbp-B0h]
  __int64 v58; // [rsp+58h] [rbp-A8h]
  __int128 v59; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v60; // [rsp+70h] [rbp-90h]
  _QWORD *v61; // [rsp+80h] [rbp-80h]
  _OWORD v62[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v63[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v64[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v65[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v66[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v67[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v68[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v69[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v70[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v71[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v72[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v73[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v74[2]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v75[2]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v76[2]; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v77[2]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v78[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v79[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v80[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _OWORD v81[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v82[8]; // [rsp+300h] [rbp+200h] BYREF
  volatile signed __int32 *v83; // [rsp+308h] [rbp+208h]
  __int64 v84; // [rsp+310h] [rbp+210h] BYREF
  volatile signed __int32 *v85; // [rsp+318h] [rbp+218h]
  _BYTE v86[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v87[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v88[32]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v89; // [rsp+380h] [rbp+280h] BYREF
  __int128 v90; // [rsp+388h] [rbp+288h] BYREF
  __int128 v91; // [rsp+398h] [rbp+298h]
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  v54 = 0;
  v52 = 0;
  v53 = 0;
  v57 = 0;
  v3 = 0;
  v55 = 0;
  v4 = 0;
  v56 = 0;
  v5 = 0;
  v6 = 0;
  v58 = 0;
  v7 = *(_QWORD **)a2;
  v61 = *(_QWORD **)(a2 + 8);
  if ( v7 != v61 )
  {
    while ( 1 )
    {
      v89 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v7 + 664LL))(*v7, &v89);
      v8 = 1;
      v90 = 0;
      v91 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v90, L"WasCommitEverNeeded");
      v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v89 + 8LL))(v89, &v90);
      std::wstring::~wstring(&v90);
      if ( v9 )
      {
        v90 = 0;
        v91 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v90, L"WasCommitEverNeeded");
        v10 = (_QWORD *)web::json::value::at(&v89, &v90);
        v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 136LL))(*v10);
        std::wstring::~wstring(&v90);
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 552LL))(*v7);
      v12 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*v7 + 8LL))(*v7, v62);
      if ( *(_QWORD *)(v12 + 24) > 7u )
        v12 = *(_QWORD *)v12;
      v13 = wcscmp_0((const wchar_t *)v12, L"FodProvider");
      std::wstring::~wstring(v62);
      if ( v11 && !v8 && v13 )
      {
        v14 = 1;
        v11 = 0;
      }
      else
      {
        v14 = 0;
      }
      if ( v6 || (v6 = 0, v14) )
        v6 = 1;
      v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 128LL))(*v7);
      v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 256LL))(*v7);
      if ( v15 )
      {
        LOBYTE(v51) = v58 != 0;
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0xF4,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\InputBuilder.cpp",
          (const char *)0x8000FFFFLL,
          v51,
          (bool)"Attempting to set rebootDowntimeSignal twice.",
          v52);
        v58 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 760LL))(*v7);
      }
      if ( v11 )
      {
        v90 = 0;
        *(_QWORD *)&v91 = 0;
        System = SystemInterface::Service::GetSystem(&v84);
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*System + 64LL))(*System, v82);
        v19 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v18 + 104LL))(*v18, v87);
        v20 = *(_QWORD *)(v19 + 48);
        v21 = (_QWORD *)(v19 + 32);
        if ( *(_QWORD *)(v19 + 56) > 7u )
          v21 = (_QWORD *)*v21;
        v63[0] = v21;
        v63[1] = v20;
        Strings::tokenize(&v90, v63);
        std::wstring::~wstring(v88);
        std::wstring::~wstring(v87);
        v22 = v83;
        if ( v83 )
        {
          if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
        v23 = v85;
        if ( v85 )
        {
          if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
            if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
          }
        }
        if ( *((_QWORD *)&v90 + 1) - (_QWORD)v90 == 128 )
        {
          v59 = 0;
          v60 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v59, L"BuildNumber");
          v24 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v89 + 8LL))(v89, &v59);
          std::wstring::~wstring(&v59);
          if ( v24 )
          {
            LOBYTE(v51) = *(_BYTE *)(a1 + 156);
            wil::details::in1diag3::Throw_HrIfMsg(
              retaddr,
              (void *)0x103,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\InputBuilder.cpp",
              (const char *)0x8000FFFFLL,
              v51,
              (bool)"Attempting to set featureUpdateBuildVersionDiff twice.",
              v52);
            v59 = 0;
            v60 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v59, L"BuildNumber");
            v25 = (_QWORD *)web::json::value::at(&v89, &v59);
            v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 112LL))(*v25);
            if ( *(_DWORD *)(v26 + 8) == 2 )
              v27 = (int)*(double *)v26;
            else
              v27 = *(_DWORD *)v26;
            v28 = v27 - std::stol((wchar_t *)(v90 + 64));
            if ( !*(_BYTE *)(a1 + 156) )
              *(_BYTE *)(a1 + 156) = 1;
            *(_DWORD *)(a1 + 152) = v28;
            std::wstring::~wstring(&v59);
          }
        }
        v29 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v7 + 24LL))(*v7, v86);
        v30 = (_OWORD *)(a1 + 160);
        if ( *(_BYTE *)(a1 + 192) )
        {
          std::wstring::operator=(v30, v29);
        }
        else
        {
          *v30 = 0;
          *(_QWORD *)(a1 + 176) = 0;
          *(_QWORD *)(a1 + 184) = 0;
          *v30 = *(_OWORD *)v29;
          *(_OWORD *)(a1 + 176) = *(_OWORD *)(v29 + 16);
          *(_WORD *)v29 = 0;
          *(_QWORD *)(v29 + 16) = 0;
          *(_QWORD *)(v29 + 24) = 7;
          *(_BYTE *)(a1 + 192) = 1;
        }
        std::wstring::~wstring(v86);
        ++v54;
        v57 += v16;
        std::vector<std::wstring>::_Tidy(&v90);
        goto LABEL_44;
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 144LL))(*v7) )
        break;
      if ( !v15 )
      {
        ++v53;
        v5 += v16;
        goto LABEL_44;
      }
      LODWORD(v52) = (_DWORD)v52 + 1;
      v3 = v16 + v55;
      v55 += v16;
LABEL_45:
      if ( v89 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 192LL))(v89, 1);
      v7 += 2;
      if ( v7 == v61 )
      {
        v4 = v56;
        goto LABEL_49;
      }
    }
    ++HIDWORD(v52);
    v56 += v16;
LABEL_44:
    v3 = v55;
    goto LABEL_45;
  }
LABEL_49:
  v31 = a1 + 24;
  memset(v67, 0, sizeof(v67));
  std::wstring::_Construct<1,wchar_t const *>(v67, L"numFeatureUpdates");
  v32 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](a1 + 24, v67);
  if ( *(_BYTE *)(v32 + 8) )
    *(_BYTE *)(v32 + 8) = 0;
  *(_DWORD *)v32 = v54;
  std::wstring::~wstring(v67);
  memset(v68, 0, sizeof(v68));
  std::wstring::_Construct<1,wchar_t const *>(v68, L"numOSLCUUpdates");
  v33 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v68);
  if ( *(_BYTE *)(v33 + 8) )
    *(_BYTE *)(v33 + 8) = 0;
  *(_DWORD *)v33 = (_DWORD)v52;
  std::wstring::~wstring(v68);
  memset(v69, 0, sizeof(v69));
  std::wstring::_Construct<1,wchar_t const *>(v69, L"numDriverUpdates");
  v34 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v69);
  if ( *(_BYTE *)(v34 + 8) )
    *(_BYTE *)(v34 + 8) = 0;
  *(_DWORD *)v34 = HIDWORD(v52);
  std::wstring::~wstring(v69);
  memset(v70, 0, sizeof(v70));
  std::wstring::_Construct<1,wchar_t const *>(v70, L"numOtherUpdates");
  v35 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v70);
  if ( *(_BYTE *)(v35 + 8) )
    *(_BYTE *)(v35 + 8) = 0;
  *(_DWORD *)v35 = v53;
  std::wstring::~wstring(v70);
  memset(v71, 0, sizeof(v71));
  std::wstring::_Construct<1,wchar_t const *>(v71, L"totalFuSizeInBytes");
  v36 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v71);
  if ( *(_BYTE *)(v36 + 8) != 1 )
    *(_BYTE *)(v36 + 8) = 1;
  *(_QWORD *)v36 = v57;
  std::wstring::~wstring(v71);
  memset(v72, 0, sizeof(v72));
  std::wstring::_Construct<1,wchar_t const *>(v72, L"totalLCUSizeInBytes");
  v37 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v72);
  if ( *(_BYTE *)(v37 + 8) != 1 )
    *(_BYTE *)(v37 + 8) = 1;
  *(_QWORD *)v37 = v3;
  std::wstring::~wstring(v72);
  memset(v73, 0, sizeof(v73));
  std::wstring::_Construct<1,wchar_t const *>(v73, L"totalDriverSizeInBytes");
  v38 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v73);
  if ( *(_BYTE *)(v38 + 8) != 1 )
    *(_BYTE *)(v38 + 8) = 1;
  *(_QWORD *)v38 = v4;
  std::wstring::~wstring(v73);
  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,wchar_t const *>(v74, L"totalOtherUpdatesSizeInBytes");
  v39 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v74);
  if ( *(_BYTE *)(v39 + 8) != 1 )
    *(_BYTE *)(v39 + 8) = 1;
  *(_QWORD *)v39 = v5;
  std::wstring::~wstring(v74);
  memset(v75, 0, sizeof(v75));
  std::wstring::_Construct<1,wchar_t const *>(v75, L"hasEKB");
  v40 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v75);
  if ( *(_BYTE *)(v40 + 8) )
    *(_BYTE *)(v40 + 8) = 0;
  *(_DWORD *)v40 = v6;
  std::wstring::~wstring(v75);
  memset(v76, 0, sizeof(v76));
  std::wstring::_Construct<1,wchar_t const *>(v76, L"InstallFlowType");
  v41 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v76);
  if ( *(_BYTE *)(v41 + 8) != 1 )
    *(_BYTE *)(v41 + 8) = 1;
  *(_QWORD *)v41 = v58;
  std::wstring::~wstring(v76);
  memset(v77, 0, sizeof(v77));
  std::wstring::_Construct<1,wchar_t const *>(v77, L"FeatureUpgradeCount");
  v42 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v77);
  if ( *(_BYTE *)(v42 + 8) )
    *(_BYTE *)(v42 + 8) = 0;
  *(_DWORD *)v42 = v54;
  std::wstring::~wstring(v77);
  memset(v78, 0, sizeof(v78));
  std::wstring::_Construct<1,wchar_t const *>(v78, L"LCUCount");
  v43 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v78);
  if ( *(_BYTE *)(v43 + 8) )
    *(_BYTE *)(v43 + 8) = 0;
  *(_DWORD *)v43 = (_DWORD)v52;
  std::wstring::~wstring(v78);
  memset(v79, 0, sizeof(v79));
  std::wstring::_Construct<1,wchar_t const *>(v79, L"DriverUpdateCount");
  v44 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v79);
  if ( *(_BYTE *)(v44 + 8) )
    *(_BYTE *)(v44 + 8) = 0;
  *(_DWORD *)v44 = HIDWORD(v52);
  std::wstring::~wstring(v79);
  memset(v80, 0, sizeof(v80));
  std::wstring::_Construct<1,wchar_t const *>(v80, L"OtherUpdateCount");
  v45 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v80);
  if ( *(_BYTE *)(v45 + 8) )
    *(_BYTE *)(v45 + 8) = 0;
  *(_DWORD *)v45 = v53;
  std::wstring::~wstring(v80);
  memset(v81, 0, sizeof(v81));
  std::wstring::_Construct<1,wchar_t const *>(v81, L"TotalDownloadSize");
  v46 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v81);
  if ( *(_BYTE *)(v46 + 8) != 1 )
    *(_BYTE *)(v46 + 8) = 1;
  *(_QWORD *)v46 = v57 + v3 + v5 + v4;
  std::wstring::~wstring(v81);
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(v64, L"FeatureUpgradeDownloadSize");
  v47 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v64);
  if ( *(_BYTE *)(v47 + 8) != 1 )
    *(_BYTE *)(v47 + 8) = 1;
  *(_QWORD *)v47 = v57;
  std::wstring::~wstring(v64);
  memset(v65, 0, sizeof(v65));
  std::wstring::_Construct<1,wchar_t const *>(v65, L"LCUDownloadSize");
  v48 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v65);
  if ( *(_BYTE *)(v48 + 8) != 1 )
    *(_BYTE *)(v48 + 8) = 1;
  *(_QWORD *)v48 = v3;
  std::wstring::~wstring(v65);
  memset(v66, 0, sizeof(v66));
  std::wstring::_Construct<1,wchar_t const *>(v66, L"DriverUpdateDownloadSize");
  v49 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v66);
  if ( *(_BYTE *)(v49 + 8) != 1 )
    *(_BYTE *)(v49 + 8) = 1;
  *(_QWORD *)v49 = v4;
  std::wstring::~wstring(v66);
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,wchar_t const *>(v62, L"OtherUpdateDownloadSize");
  v50 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](v31, v62);
  if ( *(_BYTE *)(v50 + 8) != 1 )
    *(_BYTE *)(v50 + 8) = 1;
  *(_QWORD *)v50 = v5;
  std::wstring::~wstring(v62);
}

```

## disassembly

```asm
0x1800ccaf0  mov     [rsp-8+arg_10], rbx
0x1800ccaf5  push    rbp
0x1800ccaf6  push    rsi
0x1800ccaf7  push    rdi
0x1800ccaf8  push    r12
0x1800ccafa  push    r13
0x1800ccafc  push    r14
0x1800ccafe  push    r15
0x1800ccb00  lea     rbp, [rsp-2B0h]
0x1800ccb08  sub     rsp, 3B0h
0x1800ccb0f  mov     rax, cs:__security_cookie
0x1800ccb16  xor     rax, rsp
0x1800ccb19  mov     [rbp+2E0h+var_38], rax
0x1800ccb20  mov     rsi, rcx
0x1800ccb23  xor     ebx, ebx
0x1800ccb25  mov     [rsp+3E0h+var_3A4], ebx
0x1800ccb29  mov     dword ptr [rsp+3E0h+var_3B0], ebx; char *
0x1800ccb2d  mov     dword ptr [rsp+3E0h+var_3B0+4], ebx
0x1800ccb31  mov     [rsp+3E0h+var_3A8], ebx
0x1800ccb35  mov     [rsp+3E0h+var_390], rbx
0x1800ccb3a  mov     r14d, ebx
0x1800ccb3d  mov     [rsp+3E0h+var_3A0], rbx
0x1800ccb42  mov     r15d, ebx
0x1800ccb45  mov     [rsp+3E0h+var_398], rbx
0x1800ccb4a  mov     r12d, ebx
0x1800ccb4d  mov     r13d, ebx
0x1800ccb50  mov     [rsp+3E0h+var_388], rbx
0x1800ccb55  mov     rdi, [rdx]
0x1800ccb58  mov     rax, [rdx+8]
0x1800ccb5c  mov     [rbp+2E0h+var_360], rax
0x1800ccb60  cmp     rdi, rax
0x1800ccb63  jz      loc_1800CD091
0x1800ccb69  mov     [rbp+2E0h+var_60], rbx
0x1800ccb70  mov     rcx, [rdi]
0x1800ccb73  mov     rax, [rcx]
0x1800ccb76  lea     rdx, [rbp+2E0h+var_60]
0x1800ccb7d  mov     rax, [rax+298h]
0x1800ccb84  call    _guard_dispatch_icall
0x1800ccb89  nop
0x1800ccb8a  mov     r15b, 1
0x1800ccb8d  xorps   xmm0, xmm0
0x1800ccb90  movups  [rbp+2E0h+var_58], xmm0
0x1800ccb97  xorps   xmm1, xmm1
0x1800ccb9a  movdqu  [rbp+2E0h+var_48], xmm1
0x1800ccba2  mov     r14d, 13h
0x1800ccba8  mov     r8d, r14d
0x1800ccbab  lea     rdx, aWascommitevern; "WasCommitEverNeeded"
0x1800ccbb2  lea     rcx, [rbp+2E0h+var_58]
0x1800ccbb9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ccbbe  nop
0x1800ccbbf  mov     rcx, [rbp+2E0h+var_60]
0x1800ccbc6  mov     rax, [rcx]
0x1800ccbc9  lea     rdx, [rbp+2E0h+var_58]
0x1800ccbd0  mov     rax, [rax+8]
0x1800ccbd4  call    _guard_dispatch_icall
0x1800ccbd9  mov     bl, al
0x1800ccbdb  lea     rcx, [rbp+2E0h+var_58]; void *
0x1800ccbe2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccbe7  test    bl, bl
0x1800ccbe9  jz      short loc_1800CCC4B
0x1800ccbeb  xorps   xmm0, xmm0
0x1800ccbee  movups  [rbp+2E0h+var_58], xmm0
0x1800ccbf5  xorps   xmm1, xmm1
0x1800ccbf8  movdqu  [rbp+2E0h+var_48], xmm1
0x1800ccc00  mov     r8d, r14d
0x1800ccc03  lea     rdx, aWascommitevern; "WasCommitEverNeeded"
0x1800ccc0a  lea     rcx, [rbp+2E0h+var_58]
0x1800ccc11  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ccc16  nop
0x1800ccc17  lea     rdx, [rbp+2E0h+var_58]
0x1800ccc1e  lea     rcx, [rbp+2E0h+var_60]
0x1800ccc25  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800ccc2a  mov     rcx, [rax]
0x1800ccc2d  mov     rax, [rcx]
0x1800ccc30  mov     rax, [rax+88h]
0x1800ccc37  call    _guard_dispatch_icall
0x1800ccc3c  mov     r15b, al
0x1800ccc3f  lea     rcx, [rbp+2E0h+var_58]; void *
0x1800ccc46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccc4b  mov     rcx, [rdi]
0x1800ccc4e  mov     rax, [rcx]
0x1800ccc51  mov     rax, [rax+228h]
0x1800ccc58  call    _guard_dispatch_icall
0x1800ccc5d  mov     bl, al
0x1800ccc5f  mov     rcx, [rdi]
0x1800ccc62  mov     rax, [rcx]
0x1800ccc65  lea     rdx, [rbp+2E0h+var_358]
0x1800ccc69  mov     rax, [rax+8]
0x1800ccc6d  call    _guard_dispatch_icall
0x1800ccc72  cmp     qword ptr [rax+18h], 7
0x1800ccc77  jbe     short loc_1800CCC7C
0x1800ccc79  mov     rax, [rax]
0x1800ccc7c  lea     rdx, aFodprovider; "FodProvider"
0x1800ccc83  mov     rcx, rax; String1
0x1800ccc86  call    wcscmp_0
0x1800ccc8b  mov     r14d, eax
0x1800ccc8e  lea     rcx, [rbp+2E0h+var_358]; void *
0x1800ccc92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccc97  xor     ecx, ecx
0x1800ccc99  test    bl, bl
0x1800ccc9b  jz      short loc_1800CCCAD
0x1800ccc9d  test    r15b, r15b
0x1800ccca0  jnz     short loc_1800CCCAD
0x1800ccca2  test    r14d, r14d
0x1800ccca5  jz      short loc_1800CCCAD
0x1800ccca7  mov     al, 1
0x1800ccca9  mov     bl, cl
0x1800cccab  jmp     short loc_1800CCCAF
0x1800cccad  mov     al, cl
0x1800cccaf  test    r13d, r13d
0x1800cccb2  jnz     short loc_1800CCCBB
0x1800cccb4  test    al, al
0x1800cccb6  mov     r13d, ecx
0x1800cccb9  jz      short loc_1800CCCC1
0x1800cccbb  mov     r13d, 1
0x1800cccc1  mov     rcx, [rdi]
0x1800cccc4  mov     rax, [rcx]
0x1800cccc7  mov     rax, [rax+80h]
0x1800cccce  call    _guard_dispatch_icall
0x1800cccd3  mov     r14b, al
0x1800cccd6  mov     rcx, [rdi]
0x1800cccd9  mov     rax, [rcx]
0x1800cccdc  mov     rax, [rax+100h]
0x1800ccce3  call    _guard_dispatch_icall
0x1800ccce8  mov     r15, rax
0x1800ccceb  xor     eax, eax
0x1800ccced  test    r14b, r14b
0x1800cccf0  jz      short loc_1800CCD3F
0x1800cccf2  cmp     [rsp+3E0h+var_388], rax
0x1800cccf7  setnz   dl
0x1800cccfa  mov     rcx, [rbp+2E8h]; this
0x1800ccd01  lea     rax, aAttemptingToSe_0; "Attempting to set rebootDowntimeSignal "...
0x1800ccd08  mov     qword ptr [rsp+3E0h+var_3B8], rax; bool
0x1800ccd0d  mov     byte ptr [rsp+3E0h+var_3C0], dl; int
0x1800ccd11  mov     r9d, 8000FFFFh; char *
0x1800ccd17  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800ccd1e  mov     edx, 0F4h; void *
0x1800ccd23  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800ccd28  mov     rcx, [rdi]
0x1800ccd2b  mov     rax, [rcx]
0x1800ccd2e  mov     rax, [rax+2F8h]
0x1800ccd35  call    _guard_dispatch_icall
0x1800ccd3a  mov     [rsp+3E0h+var_388], rax
0x1800ccd3f  test    bl, bl
0x1800ccd41  jz      loc_1800CD017
0x1800ccd47  xorps   xmm0, xmm0
0x1800ccd4a  xor     eax, eax
0x1800ccd4c  movups  [rbp+2E0h+var_58], xmm0
0x1800ccd53  mov     qword ptr [rbp+2E0h+var_48], rax
0x1800ccd5a  lea     rcx, [rbp+2E0h+var_D0]
0x1800ccd61  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800ccd66  nop
0x1800ccd67  mov     rcx, [rax]
0x1800ccd6a  mov     rax, [rcx]
0x1800ccd6d  lea     rdx, [rbp+2E0h+var_E0]
0x1800ccd74  mov     rax, [rax+40h]
0x1800ccd78  call    _guard_dispatch_icall
0x1800ccd7d  nop
0x1800ccd7e  mov     rcx, [rax]
0x1800ccd81  mov     rax, [rcx]
0x1800ccd84  lea     rdx, [rbp+2E0h+var_A0]
0x1800ccd8b  mov     rax, [rax+68h]
0x1800ccd8f  call    _guard_dispatch_icall
0x1800ccd94  nop
0x1800ccd95  mov     rdx, [rax+30h]
0x1800ccd99  lea     rcx, [rax+20h]
0x1800ccd9d  cmp     qword ptr [rax+38h], 7
0x1800ccda2  jbe     short loc_1800CCDA7
0x1800ccda4  mov     rcx, [rcx]
0x1800ccda7  mov     [rbp+2E0h+var_330], rcx
0x1800ccdab  mov     [rbp+2E0h+var_328], rdx
0x1800ccdaf  lea     rdx, [rbp+2E0h+var_330]
0x1800ccdb3  lea     rcx, [rbp+2E0h+var_58]
0x1800ccdba  call    ?tokenize@Strings@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$basic_zstring_view@_W@wil@@_W_N@Z; Strings::tokenize(wil::basic_zstring_view<wchar_t>,wchar_t,bool)
0x1800ccdbf  nop
0x1800ccdc0  lea     rcx, [rbp+2E0h+var_80]; void *
0x1800ccdc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccdcc  lea     rcx, [rbp+2E0h+var_A0]; void *
0x1800ccdd3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccdd8  nop
0x1800ccdd9  mov     rbx, [rbp+2E0h+var_D8]
0x1800ccde0  xor     r14d, r14d
0x1800ccde3  test    rbx, rbx
0x1800ccde6  jz      short loc_1800CCE20
0x1800ccde8  or      eax, 0FFFFFFFFh
0x1800ccdeb  lock xadd [rbx+8], eax
0x1800ccdf0  cmp     eax, 1
0x1800ccdf3  jnz     short loc_1800CCE20
0x1800ccdf5  mov     rax, [rbx]
0x1800ccdf8  mov     rcx, rbx
0x1800ccdfb  mov     rax, [rax]
0x1800ccdfe  call    _guard_dispatch_icall
0x1800cce03  or      eax, 0FFFFFFFFh
0x1800cce06  lock xadd [rbx+0Ch], eax
0x1800cce0b  cmp     eax, 1
0x1800cce0e  jnz     short loc_1800CCE20
0x1800cce10  mov     rax, [rbx]
0x1800cce13  mov     rcx, rbx
0x1800cce16  mov     rax, [rax+8]
0x1800cce1a  call    _guard_dispatch_icall
0x1800cce1f  nop
0x1800cce20  mov     rbx, [rbp+2E0h+var_C8]
0x1800cce27  test    rbx, rbx
0x1800cce2a  jz      short loc_1800CCE63
0x1800cce2c  or      eax, 0FFFFFFFFh
0x1800cce2f  lock xadd [rbx+8], eax
0x1800cce34  cmp     eax, 1
0x1800cce37  jnz     short loc_1800CCE63
0x1800cce39  mov     rax, [rbx]
0x1800cce3c  mov     rcx, rbx
0x1800cce3f  mov     rax, [rax]
0x1800cce42  call    _guard_dispatch_icall
0x1800cce47  or      eax, 0FFFFFFFFh
0x1800cce4a  lock xadd [rbx+0Ch], eax
0x1800cce4f  cmp     eax, 1
0x1800cce52  jnz     short loc_1800CCE63
0x1800cce54  mov     rax, [rbx]
0x1800cce57  mov     rcx, rbx
0x1800cce5a  mov     rax, [rax+8]
0x1800cce5e  call    _guard_dispatch_icall
0x1800cce63  mov     rax, qword ptr [rbp+2E0h+var_58+8]
0x1800cce6a  sub     rax, qword ptr [rbp+2E0h+var_58]
0x1800cce71  cmp     rax, 80h
0x1800cce77  jnz     loc_1800CCF8E
0x1800cce7d  xorps   xmm0, xmm0
0x1800cce80  movups  [rsp+3E0h+var_380], xmm0
0x1800cce85  xorps   xmm1, xmm1
0x1800cce88  movdqu  [rsp+3E0h+var_370], xmm1
0x1800cce8e  lea     r8d, [rax-75h]
0x1800cce92  lea     rdx, aBuildnumber; "BuildNumber"
0x1800cce99  lea     rcx, [rsp+3E0h+var_380]
0x1800cce9e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ccea3  nop
0x1800ccea4  mov     rcx, [rbp+2E0h+var_60]
0x1800cceab  mov     rax, [rcx]
0x1800cceae  lea     rdx, [rsp+3E0h+var_380]
0x1800cceb3  mov     rax, [rax+8]
0x1800cceb7  call    _guard_dispatch_icall
0x1800ccebc  mov     bl, al
0x1800ccebe  lea     rcx, [rsp+3E0h+var_380]; void *
0x1800ccec3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccec8  test    bl, bl
0x1800cceca  jz      loc_1800CCF8E
0x1800cced0  mov     rcx, [rbp+2E8h]; this
0x1800cced7  lea     rax, aAttemptingToSe; "Attempting to set featureUpdateBuildVer"...
0x1800ccede  mov     qword ptr [rsp+3E0h+var_3B8], rax; bool
0x1800ccee3  mov     al, [rsi+9Ch]
0x1800ccee9  mov     byte ptr [rsp+3E0h+var_3C0], al; int
0x1800cceed  mov     r9d, 8000FFFFh; char *
0x1800ccef3  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800ccefa  mov     edx, 103h; void *
0x1800cceff  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800ccf04  xorps   xmm0, xmm0
0x1800ccf07  movups  [rsp+3E0h+var_380], xmm0
0x1800ccf0c  xorps   xmm1, xmm1
0x1800ccf0f  movdqu  [rsp+3E0h+var_370], xmm1
0x1800ccf15  mov     r8d, 0Bh
0x1800ccf1b  lea     rdx, aBuildnumber; "BuildNumber"
0x1800ccf22  lea     rcx, [rsp+3E0h+var_380]
0x1800ccf27  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800ccf2c  nop
0x1800ccf2d  lea     rdx, [rsp+3E0h+var_380]
0x1800ccf32  lea     rcx, [rbp+2E0h+var_60]
0x1800ccf39  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800ccf3e  mov     rcx, [rax]
0x1800ccf41  mov     rax, [rcx]
0x1800ccf44  mov     rax, [rax+70h]
0x1800ccf48  call    _guard_dispatch_icall
0x1800ccf4d  cmp     dword ptr [rax+8], 2
0x1800ccf51  jnz     short loc_1800CCF5A
0x1800ccf53  cvttsd2si rbx, qword ptr [rax]
0x1800ccf58  jmp     short loc_1800CCF5C
0x1800ccf5a  mov     ebx, [rax]
0x1800ccf5c  mov     rcx, qword ptr [rbp+2E0h+var_58]
0x1800ccf63  add     rcx, 40h ; '@'; String
0x1800ccf67  call    ?stol@std@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stol(std::wstring const &,unsigned __int64 *,int)
0x1800ccf6c  sub     ebx, eax
0x1800ccf6e  cmp     [rsi+9Ch], r14b
0x1800ccf75  jnz     short loc_1800CCF7E
0x1800ccf77  mov     byte ptr [rsi+9Ch], 1
0x1800ccf7e  mov     [rsi+98h], ebx
0x1800ccf84  lea     rcx, [rsp+3E0h+var_380]; void *
0x1800ccf89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccf8e  mov     rcx, [rdi]
0x1800ccf91  mov     rax, [rcx]
0x1800ccf94  lea     rdx, [rbp+2E0h+var_C0]
0x1800ccf9b  mov     rax, [rax+18h]
0x1800ccf9f  call    _guard_dispatch_icall
0x1800ccfa4  lea     rcx, [rsi+0A0h]
0x1800ccfab  xor     ebx, ebx
0x1800ccfad  cmp     [rsi+0C0h], bl
0x1800ccfb3  jz      short loc_1800CCFBF
0x1800ccfb5  mov     rdx, rax
0x1800ccfb8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800ccfbd  jmp     short loc_1800CCFF4
0x1800ccfbf  xorps   xmm0, xmm0
0x1800ccfc2  movups  xmmword ptr [rcx], xmm0
0x1800ccfc5  mov     [rsi+0B0h], rbx
0x1800ccfcc  mov     [rsi+0B8h], rbx
0x1800ccfd3  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
