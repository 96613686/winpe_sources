# Windows::Settings::RefreshSettings(bool)

- ea: `0x180042130`
- end: `0x180042ef1`
- name: `?RefreshSettings@Settings@Windows@@UEAA_N_N@Z`
- size: `3521`
- prototype: `char __fastcall(Windows::Settings *this, bool)`
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dc0`
- `0x18000856c`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800210f8`
- `0x180023a58`
- `0x180024030`
- `0x180024190`
- `0x180024468`
- `0x18002778c`
- `0x180029d44`
- `0x18002d390`
- `0x18003a1f0`
- `0x18003d4d8`
- `0x18003d5d8`
- `0x18003d614`
- `0x18003e98c`
- `0x18003e9e0`
- `0x180040a8c`
- `0x180040dbc`
- `0x180040dcc`
- `0x180040ddc`
- `0x180040ee4`
- `0x180040ff0`
- `0x18004112c`
- `0x180041330`
- `0x1800414f0`
- `0x1800415c4`
- `0x180041a20`
- `0x180042130`
- `0x180042ef8`
- `0x1800437bc`
- `0x180043964`
- `0x180043d84`
- `0x18004458c`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180042722`
- `msvcp_win!_Mtx_unlock` at `0x180042e93`
- `msvcp_win!_Mtx_unlock` at `0x180042722`
- `msvcp_win!_Mtx_unlock` at `0x180042e93`
- `msvcp_win!_Mtx_lock` at `0x180042184`
- `msvcp_win!_Mtx_lock` at `0x180042184`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180042192`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800421ad`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180042192`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800421ad`

## string_xrefs

- `0x180042390`: `UpdateOrchestratorCurrentVersionRoot`
- `0x1800424b1`: `UpdateOrchestratorCurrentVersionRoot`
- `0x180042c31`: `UpdateOrchestratorCurrentVersionRoot`

## pseudocode

```c
char __fastcall Windows::Settings::RefreshSettings(Windows::Settings *this, bool a2)
{
  Windows::Settings *v3; // r12
  int v4; // r15d
  char *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, wchar_t **, __int128 *, __int128 *, __int128 *); // rbx
  __int64 v9; // rsi
  void (__fastcall *v10)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  void *v11; // rbx
  __int64 UniqueId; // rax
  const wchar_t *v13; // rdx
  wchar_t *v14; // r8
  char v15; // bl
  __int64 *v17; // rbx
  _QWORD *v18; // rsi
  _QWORD *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rsi
  _QWORD *v24; // rdx
  int v25; // r15d
  __int64 v26; // rax
  _BYTE *v27; // r9
  unsigned int v28; // r8d
  __int128 *v29; // rdx
  __int64 v30; // rax
  __int64 **v31; // rcx
  __int64 *j; // rax
  __int64 *i; // rcx
  __int64 v34; // rsi
  void (__fastcall *v35)(__int64, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int64 v36; // rax
  __int64 (__fastcall *v37)(Windows::Settings *, __int128 *); // rbx
  __int64 v38; // rbx
  _QWORD *v39; // rax
  const char *v40; // rdx
  int v41; // [rsp+40h] [rbp-428h]
  void *Block; // [rsp+48h] [rbp-420h] BYREF
  char v43; // [rsp+50h] [rbp-418h]
  __int64 *v44; // [rsp+58h] [rbp-410h]
  char *v45; // [rsp+60h] [rbp-408h]
  wchar_t *S2[4]; // [rsp+68h] [rbp-400h] BYREF
  char v47; // [rsp+88h] [rbp-3E0h]
  char v48; // [rsp+90h] [rbp-3D8h]
  _QWORD *v49; // [rsp+98h] [rbp-3D0h]
  __int64 *v50; // [rsp+A0h] [rbp-3C8h]
  char *v51; // [rsp+A8h] [rbp-3C0h]
  Windows::Settings *v52; // [rsp+B0h] [rbp-3B8h]
  __int128 v53; // [rsp+B8h] [rbp-3B0h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-3A0h]
  __int64 v55; // [rsp+D0h] [rbp-398h]
  char v56; // [rsp+D8h] [rbp-390h]
  _QWORD v57[2]; // [rsp+E0h] [rbp-388h] BYREF
  _BYTE v58[16]; // [rsp+F0h] [rbp-378h] BYREF
  _BYTE v59[8]; // [rsp+100h] [rbp-368h] BYREF
  _BYTE v60[232]; // [rsp+108h] [rbp-360h] BYREF
  __int128 v61; // [rsp+1F0h] [rbp-278h] BYREF
  __int64 v62; // [rsp+200h] [rbp-268h]
  unsigned __int64 v63; // [rsp+208h] [rbp-260h]
  __int128 v64; // [rsp+210h] [rbp-258h] BYREF
  __int64 v65; // [rsp+220h] [rbp-248h]
  __int64 v66; // [rsp+228h] [rbp-240h]
  __int128 v67; // [rsp+230h] [rbp-238h] BYREF
  __int64 v68; // [rsp+240h] [rbp-228h]
  __int64 v69; // [rsp+248h] [rbp-220h]
  _QWORD v70[4]; // [rsp+250h] [rbp-218h] BYREF
  char v71; // [rsp+270h] [rbp-1F8h]
  void **v72; // [rsp+280h] [rbp-1E8h] BYREF
  int v73; // [rsp+288h] [rbp-1E0h] BYREF
  char v74; // [rsp+28Ch] [rbp-1DCh]
  int v75; // [rsp+2B0h] [rbp-1B8h] BYREF
  const char *v76; // [rsp+2B8h] [rbp-1B0h]
  __int64 v77; // [rsp+2C0h] [rbp-1A8h]
  char v78; // [rsp+2C8h] [rbp-1A0h]
  int v79; // [rsp+2D0h] [rbp-198h]
  _BYTE v80[152]; // [rsp+2D8h] [rbp-190h] BYREF
  __int64 v81; // [rsp+370h] [rbp-F8h]
  __int64 v82; // [rsp+378h] [rbp-F0h]
  int v83; // [rsp+380h] [rbp-E8h]
  __int64 v84; // [rsp+388h] [rbp-E0h]
  int *v85; // [rsp+390h] [rbp-D8h]
  __int64 v86; // [rsp+398h] [rbp-D0h]
  __int64 v87; // [rsp+3A0h] [rbp-C8h]
  void ***v88; // [rsp+3A8h] [rbp-C0h]
  __int64 v89; // [rsp+3B0h] [rbp-B8h]
  int v90; // [rsp+3B8h] [rbp-B0h]
  int *v91; // [rsp+3C0h] [rbp-A8h]
  char v92; // [rsp+3C8h] [rbp-A0h]
  _BYTE v93[48]; // [rsp+3FAh] [rbp-6Eh] BYREF
  _BYTE v94[6]; // [rsp+42Ah] [rbp-3Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+0h]

  v3 = this;
  v52 = this;
  v4 = 0;
  v5 = (char *)this + 8;
  v51 = (char *)this + 8;
  if ( _Mtx_lock((Windows::Settings *)((char *)this + 8)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v5 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v5 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v73 = 0;
  v74 = 0;
  v78 = 0;
  v75 = 0;
  v76 = "RefreshSettings";
  v77 = 0;
  v79 = 0;
  v81 = 0;
  v82 = 0;
  memset_0(v80, 0, sizeof(v80));
  v83 = 1;
  v84 = 0;
  v85 = &v73;
  v86 = 0;
  v87 = 0;
  v88 = &v72;
  v89 = 0;
  v90 = 0;
  v91 = &v75;
  v92 = 0;
  v72 = &Windows::Telemetry::Worker::RefreshSettings::`vftable';
  v61 = 0;
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v61, L"WOSCEndpoint", 12);
  LOBYTE(v6) = a2;
  Windows::Telemetry::Worker::RefreshSettings::StartActivity(&v72, &v61, v6);
  std::wstring::_Tidy_deallocate(&v61);
  v45 = (char *)v3 + 88;
  v7 = *((_QWORD *)v3 + 11);
  v8 = *(void (__fastcall **)(__int64, wchar_t **, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v7 + 40LL);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v64, L"WOSCUniqueId", 12);
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v67, L"\\Settings", 9);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v61, L"UpdateOrchestratorCurrentVersionRoot", 36);
  v8(v7, S2, &v61, &v67, &v64);
  std::wstring::_Tidy_deallocate(&v61);
  std::wstring::_Tidy_deallocate(&v67);
  std::wstring::_Tidy_deallocate(&v64);
  WOSCSettings::GetSettings((__int64)&Block, a2);
  if ( !v43 )
  {
    v9 = *(_QWORD *)v45;
    v10 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v45 + 72LL);
    v67 = 0;
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v67, L"WOSCUniqueId", 12);
    v61 = 0;
    v62 = 0;
    v63 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v61, L"\\Settings", 9);
    v64 = 0;
    v65 = 0;
    v66 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v64, L"UpdateOrchestratorCurrentVersionRoot", 36);
    v10(v9, &v64, &v61, &v67);
    std::wstring::_Tidy_deallocate(&v64);
    std::wstring::_Tidy_deallocate(&v61);
    std::wstring::_Tidy_deallocate(&v67);
    v64 = 0;
    v65 = 0;
    v66 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v64, L"MUSE Settings Not Found", 23);
    Windows::Telemetry::Worker::RefreshSettings::Stop(&v72, &v64);
    std::wstring::_Tidy_deallocate(&v64);
    if ( !v43 )
      goto LABEL_30;
    v11 = Block;
    if ( !Block )
      goto LABEL_30;
    if ( *(_QWORD *)Block )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Block + 16LL))(*(_QWORD *)Block);
LABEL_29:
    operator delete(v11);
LABEL_30:
    if ( v48 && v47 != -1 && v47 && v47 != 1 )
      std::wstring::_Tidy_deallocate(S2);
    v72 = &Windows::Telemetry::Worker::RefreshSettings::`vftable';
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v72);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v72);
    _Mtx_unlock((_Mtx_t)v5);
    return 0;
  }
  if ( !v48 )
    goto LABEL_21;
  if ( v47 != 2 )
    std::_Throw_bad_variant_access();
  UniqueId = WOSCSettings::GetUniqueId(Block, &v64);
  v4 = 1;
  v13 = (const wchar_t *)S2;
  if ( S2[3] > (wchar_t *)7 )
    v13 = S2[0];
  v14 = *(wchar_t **)(UniqueId + 16);
  if ( *(_QWORD *)(UniqueId + 24) > 7u )
    UniqueId = *(_QWORD *)UniqueId;
  if ( v14 == S2[2] && (!v14 || !wmemcmp((const wchar_t *)UniqueId, v13, (size_t)v14)) )
    v15 = 1;
  else
LABEL_21:
    v15 = 0;
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    std::wstring::_Tidy_deallocate(&v64);
  }
  if ( v15 )
  {
    v64 = 0;
    v65 = 0;
    v66 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v64, L"No Changes", 10);
    Windows::Telemetry::Worker::RefreshSettings::Stop(&v72, &v64);
    std::wstring::_Tidy_deallocate(&v64);
    if ( !v43 )
      goto LABEL_30;
    v11 = Block;
    if ( !Block )
      goto LABEL_30;
    if ( *(_QWORD *)Block )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Block + 16LL))(*(_QWORD *)Block);
    goto LABEL_29;
  }
  if ( !v43 )
    std::_Throw_bad_optional_access();
  WOSCSettings::GetAllSettings((__int64 **)Block, v57);
  Windows::Settings::ClearSettings(v3);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v58);
  v17 = *(__int64 **)v57[0];
LABEL_38:
  v44 = v17;
  while ( !*((_BYTE *)v17 + 25) )
  {
    v18 = v17 + 4;
    v50 = v17 + 4;
    v19 = v17 + 8;
    v49 = v17 + 8;
    if ( (unsigned __int64)v17[11] > 7 )
      v19 = (_QWORD *)*v19;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v19 + v20) );
    try
    {
      std::wstring::_Construct<1,unsigned short const *>(&v64, v19, v20);
      Windows::Settings::GetValue(v21, v70, &v64);
      std::wstring::_Tidy_deallocate(&v64);
      *(_QWORD *)&v67 = v3;
      *((_QWORD *)&v67 + 1) = v17 + 4;
      if ( v71 == -1 )
        std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_void__lambda_344744ade8a7a634c9cae214d407f57b__std::variant_unsigned_int_unsigned___int64_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________1_();
      if ( v71 )
      {
        if ( v71 == 1 )
          std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_2___::_Dispatch2_void__lambda_344744ade8a7a634c9cae214d407f57b__std::variant_unsigned_int_unsigned___int64_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0_(
            &v67,
            v70);
        else
          std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_3___::_Dispatch2_void__lambda_344744ade8a7a634c9cae214d407f57b__std::variant_unsigned_int_unsigned___int64_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0_(
            &v67,
            v70);
      }
      else
      {
        std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_1___::_Dispatch2_void__lambda_344744ade8a7a634c9cae214d407f57b__std::variant_unsigned_int_unsigned___int64_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0_(
          &v67,
          v70);
      }
      if ( (unsigned __int64)v17[7] > 7 )
        v18 = (_QWORD *)*v18;
      v22 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v18, v17[6]);
      v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, ":");
      if ( v71 == -1 )
        std::_Variant_dispatcher<std::integer_sequence<unsigned __int64,0>>::_Dispatch2<std::wstring,overloaded<_lambda_713a323e86118e0abc18888f10fac820_,_lambda_fa9f837d11ad74cd4b3b5d0355766323_>,std::variant<unsigned int,unsigned __int64,std::wstring> const &,1>();
      if ( v71 )
      {
        if ( v71 == 1 )
        {
          v26 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v93, v70[0]);
          v61 = 0;
          v62 = 0;
          v63 = 0;
          if ( (_BYTE *)v26 == v93 )
          {
            v62 = 0;
            v63 = 7;
            LOWORD(v61) = 0;
          }
          else
          {
            std::wstring::_Construct<1,unsigned short const *>(&v61, v26, (__int64)&v93[-v26] >> 1);
          }
          v25 = v4 | 0x7C10;
        }
        else
        {
          v61 = 0;
          v62 = 0;
          v63 = 0;
          v24 = v70;
          if ( v70[3] > 7u )
            v24 = (_QWORD *)v70[0];
          std::wstring::_Construct<2,unsigned short const *>(&v61, v24, v70[2]);
          v25 = v4 | 0x38010;
        }
      }
      else
      {
        v27 = v94;
        v28 = v70[0];
        do
        {
          v27 -= 2;
          *(_WORD *)v27 = v28 % 0xA + 48;
          v28 /= 0xAu;
        }
        while ( v28 );
        v61 = 0;
        v62 = 0;
        v63 = 0;
        if ( v27 == v94 )
        {
          v62 = 0;
          v63 = 7;
          LOWORD(v61) = 0;
        }
        else
        {
          std::wstring::_Construct<1,unsigned short const *>(&v61, v27, (v94 - v27) >> 1);
        }
        v25 = v4 | 0x3F0;
      }
      v4 = v25 | 0xE;
      v41 = v4;
      v29 = &v61;
      if ( v63 > 7 )
        v29 = (__int128 *)v61;
      v30 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v23, v29, v62);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, ",");
      std::wstring::_Tidy_deallocate(&v61);
      if ( v71 != -1 && v71 && v71 != 1 )
        std::wstring::_Tidy_deallocate(v70);
    }
    catch ( ... )
    {
      v39 = v49;
      if ( v49[3] > 7u )
        v39 = (_QWORD *)*v49;
      v40 = (const char *)v50;
      if ( (unsigned __int64)v50[3] > 7 )
        v40 = (const char *)*v50;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\settings.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Failed to convert setting from JSON: setting name %ws, json %ws",
        v40,
        v39);
      v5 = v51;
      v17 = v44;
      v4 = v41;
      v3 = v52;
    }
    v31 = (__int64 **)v17[2];
    if ( !*((_BYTE *)v31 + 25) )
    {
      v17 = (__int64 *)v17[2];
      for ( i = *v31; !*((_BYTE *)i + 25); i = (__int64 *)*i )
        v17 = i;
      goto LABEL_38;
    }
    for ( j = (__int64 *)v17[1]; !*((_BYTE *)j + 25) && v17 == (__int64 *)j[2]; j = (__int64 *)j[1] )
      v17 = j;
    v17 = j;
    v44 = j;
  }
  if ( !v43 )
    std::_Throw_bad_optional_access();
  v34 = *(_QWORD *)v45;
  v35 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v45 + 56LL);
  v36 = WOSCSettings::GetUniqueId(Block, v70);
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v53 = *(_OWORD *)v36;
  v54 = *(_QWORD *)(v36 + 16);
  v55 = *(_QWORD *)(v36 + 24);
  *(_QWORD *)(v36 + 16) = 0;
  *(_QWORD *)(v36 + 24) = 7;
  *(_WORD *)v36 = 0;
  v56 = 2;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v67, L"WOSCUniqueId", 12);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v61, L"\\Settings", 9);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v64, L"UpdateOrchestratorCurrentVersionRoot", 36);
  v35(v34, &v64, &v61, &v67, &v53);
  std::wstring::_Tidy_deallocate(&v64);
  std::wstring::_Tidy_deallocate(&v61);
  std::wstring::_Tidy_deallocate(&v67);
  if ( v56 != -1 && v56 && v56 != 1 )
    std::wstring::_Tidy_deallocate(&v53);
  std::wstring::_Tidy_deallocate(v70);
  if ( !v43 )
    std::_Throw_bad_optional_access();
  WOSCSettings::AcknowledgeReceipt((WOSCSettings *)Block);
  Windows::Settings::RegisterDynamicInstalledProducts(v3);
  v37 = *(__int64 (__fastcall **)(Windows::Settings *, __int128 *))(*(_QWORD *)v3 + 24LL);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v64, L"ExperimentID", 12);
  LOBYTE(v37) = v37(v3, &v64);
  std::wstring::_Tidy_deallocate(&v64);
  if ( (_BYTE)v37 )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UPExperimentation>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_UPExperimentation>::GetImpl'::`2'::impl);
  std::basic_stringbuf<unsigned short>::str(v60, &v61);
  if ( !v43 )
    std::_Throw_bad_optional_access();
  v38 = WOSCSettings::GetUniqueId(Block, v70);
  v64 = 0;
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v64, L"RefreshedSettings", 17);
  Windows::Telemetry::Worker::RefreshSettings::Stop(&v72, &v64, v38, &v61);
  std::wstring::_Tidy_deallocate(&v64);
  std::wstring::_Tidy_deallocate(v70);
  std::wstring::_Tidy_deallocate(&v61);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v58);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v57);
  std::optional<std::unique_ptr<WOSCSettings>>::~optional<std::unique_ptr<WOSCSettings>>(&Block);
  if ( v48 && v47 != -1 && v47 && v47 != 1 )
    std::wstring::_Tidy_deallocate(S2);
  v72 = &Windows::Telemetry::Worker::RefreshSettings::`vftable';
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v72);
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v72);
  _Mtx_unlock((_Mtx_t)v5);
  return 1;
}

```

## disassembly

```asm
0x180042130  mov     [rsp+arg_10], rbx
0x180042135  mov     [rsp+arg_18], rsi
0x18004213a  push    rdi
0x18004213b  push    r12
0x18004213d  push    r13
0x18004213f  push    r14
0x180042141  push    r15
0x180042143  sub     rsp, 440h
0x18004214a  mov     rax, cs:__security_cookie
0x180042151  xor     rax, rsp
0x180042154  mov     [rsp+468h+var_38], rax
0x18004215c  mov     r13b, dl
0x18004215f  mov     r12, rcx
0x180042162  mov     [rsp+468h+var_3B8], rcx
0x18004216a  xor     r14d, r14d
0x18004216d  mov     r15d, r14d
0x180042170  mov     [rsp+468h+var_428], r14d
0x180042175  lea     rdi, [rcx+8]
0x180042179  mov     [rsp+468h+var_3C0], rdi
0x180042181  mov     rcx, rdi; _Mtx_t
0x180042184  call    cs:__imp__Mtx_lock
0x18004218a  test    eax, eax
0x18004218c  jz      short loc_180042199
0x18004218e  lea     ecx, [r14+5]
0x180042192  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180042198  int     3; Trap to Debugger
0x180042199  mov     eax, [rdi+4Ch]
0x18004219c  cmp     eax, 7FFFFFFFh
0x1800421a1  jnz     short loc_1800421B4
0x1800421a3  dec     eax
0x1800421a5  mov     [rdi+4Ch], eax
0x1800421a8  mov     ecx, 6
0x1800421ad  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800421b3  nop
0x1800421b4  mov     [rsp+468h+var_1E0], r14d
0x1800421bc  mov     [rsp+468h+var_1DC], r14b
0x1800421c4  mov     [rsp+468h+var_1A0], r14b
0x1800421cc  mov     [rsp+468h+var_1B8], r14d
0x1800421d4  lea     rax, aRefreshsetting; "RefreshSettings"
0x1800421db  mov     [rsp+468h+var_1B0], rax
0x1800421e3  mov     [rsp+468h+var_1A8], r14
0x1800421eb  mov     [rsp+468h+var_198], r14d
0x1800421f3  mov     [rsp+468h+var_F8], r14
0x1800421fb  mov     [rsp+468h+var_F0], r14
0x180042203  xor     edx, edx; Val
0x180042205  mov     r8d, 98h; Size
0x18004220b  lea     rcx, [rsp+468h+var_190]; void *
0x180042213  call    memset_0
0x180042218  mov     [rsp+468h+var_E8], 1
0x180042223  xor     eax, eax
0x180042225  mov     [rsp+468h+var_E0], rax
0x18004222d  lea     rax, [rsp+468h+var_1E0]
0x180042235  mov     [rsp+468h+var_D8], rax
0x18004223d  mov     [rsp+468h+var_D0], r14
0x180042245  mov     [rsp+468h+var_C8], r14
0x18004224d  lea     rax, [rsp+468h+var_1E8]
0x180042255  mov     [rsp+468h+var_C0], rax
0x18004225d  mov     [rsp+468h+var_B8], r14
0x180042265  mov     [rsp+468h+var_B0], r14d
0x18004226d  lea     rax, [rsp+468h+var_1B8]
0x180042275  mov     [rsp+468h+var_A8], rax
0x18004227d  mov     [rsp+468h+var_A0], r14b
0x180042285  lea     rax, ??_7RefreshSettings@Worker@Telemetry@Windows@@6B@; const Windows::Telemetry::Worker::RefreshSettings::`vftable'
0x18004228c  mov     [rsp+468h+var_1E8], rax
0x180042294  xorps   xmm0, xmm0
0x180042297  movups  [rsp+468h+var_278], xmm0
0x18004229f  mov     [rsp+468h+var_268], r14
0x1800422a7  mov     [rsp+468h+var_260], r14
0x1800422af  mov     r8d, 0Ch
0x1800422b5  lea     rdx, aWoscendpoint; "WOSCEndpoint"
0x1800422bc  lea     rcx, [rsp+468h+var_278]
0x1800422c4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800422c9  mov     r8b, r13b
0x1800422cc  lea     rdx, [rsp+468h+var_278]
0x1800422d4  lea     rcx, [rsp+468h+var_1E8]
0x1800422dc  call    ?StartActivity@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Windows::Telemetry::Worker::RefreshSettings::StartActivity(std::wstring const &,bool)
0x1800422e1  lea     rcx, [rsp+468h+var_278]
0x1800422e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800422ee  nop
0x1800422ef  lea     rax, [r12+58h]
0x1800422f4  mov     [rsp+468h+var_408], rax
0x1800422f9  mov     rsi, [rax]
0x1800422fc  mov     rax, [rsi]
0x1800422ff  mov     rbx, [rax+28h]
0x180042303  xorps   xmm0, xmm0
0x180042306  movups  [rsp+468h+var_258], xmm0
0x18004230e  mov     [rsp+468h+var_248], r14
0x180042316  mov     [rsp+468h+var_240], r14
0x18004231e  mov     r8d, 0Ch
0x180042324  lea     rdx, aWoscuniqueid; "WOSCUniqueId"
0x18004232b  lea     rcx, [rsp+468h+var_258]
0x180042333  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042338  nop
0x180042339  xorps   xmm0, xmm0
0x18004233c  movups  [rsp+468h+var_238], xmm0
0x180042344  mov     [rsp+468h+var_228], r14
0x18004234c  mov     [rsp+468h+var_220], r14
0x180042354  mov     r8d, 9
0x18004235a  lea     rdx, aSettings; "\\Settings"
0x180042361  lea     rcx, [rsp+468h+var_238]
0x180042369  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004236e  nop
0x18004236f  xorps   xmm0, xmm0
0x180042372  movups  [rsp+468h+var_278], xmm0
0x18004237a  mov     [rsp+468h+var_268], r14
0x180042382  mov     [rsp+468h+var_260], r14
0x18004238a  mov     r8d, 24h ; '$'
0x180042390  lea     rdx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x180042397  lea     rcx, [rsp+468h+var_278]
0x18004239f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800423a4  nop
0x1800423a5  lea     rax, [rsp+468h+var_258]
0x1800423ad  mov     [rsp+468h+var_448], rax
0x1800423b2  lea     r9, [rsp+468h+var_238]
0x1800423ba  lea     r8, [rsp+468h+var_278]
0x1800423c2  lea     rdx, [rsp+468h+S2]
0x1800423c7  mov     rcx, rsi
0x1800423ca  mov     rax, rbx
0x1800423cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423d2  nop
0x1800423d3  lea     rcx, [rsp+468h+var_278]
0x1800423db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800423e0  nop
0x1800423e1  lea     rcx, [rsp+468h+var_238]
0x1800423e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800423ee  nop
0x1800423ef  lea     rcx, [rsp+468h+var_258]
0x1800423f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800423fc  mov     dl, r13b
0x1800423ff  lea     rcx, [rsp+468h+Block]
0x180042404  call    ?GetSettings@WOSCSettings@@SA?AV?$optional@V?$unique_ptr@VWOSCSettings@@U?$default_delete@VWOSCSettings@@@std@@@std@@@std@@_N@Z; WOSCSettings::GetSettings(bool)
0x180042409  nop
0x18004240a  cmp     [rsp+468h+var_418], r14b
0x18004240f  jnz     loc_18004259E
0x180042415  mov     rsi, [rsp+468h+var_408]
0x18004241a  mov     rsi, [rsi]
0x18004241d  mov     rax, [rsi]
0x180042420  mov     rbx, [rax+48h]
0x180042424  xorps   xmm0, xmm0
0x180042427  movups  [rsp+468h+var_238], xmm0
0x18004242f  mov     [rsp+468h+var_228], r14
0x180042437  mov     [rsp+468h+var_220], r14
0x18004243f  mov     r8d, 0Ch
0x180042445  lea     rdx, aWoscuniqueid; "WOSCUniqueId"
0x18004244c  lea     rcx, [rsp+468h+var_238]
0x180042454  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042459  nop
0x18004245a  xorps   xmm0, xmm0
0x18004245d  movups  [rsp+468h+var_278], xmm0
0x180042465  mov     [rsp+468h+var_268], r14
0x18004246d  mov     [rsp+468h+var_260], r14
0x180042475  mov     r8d, 9
0x18004247b  lea     rdx, aSettings; "\\Settings"
0x180042482  lea     rcx, [rsp+468h+var_278]
0x18004248a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004248f  nop
0x180042490  xorps   xmm0, xmm0
0x180042493  movups  [rsp+468h+var_258], xmm0
0x18004249b  mov     [rsp+468h+var_248], r14
0x1800424a3  mov     [rsp+468h+var_240], r14
0x1800424ab  mov     r8d, 24h ; '$'
0x1800424b1  lea     rdx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x1800424b8  lea     rcx, [rsp+468h+var_258]
0x1800424c0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800424c5  nop
0x1800424c6  lea     r9, [rsp+468h+var_238]
0x1800424ce  lea     r8, [rsp+468h+var_278]
0x1800424d6  lea     rdx, [rsp+468h+var_258]
0x1800424de  mov     rcx, rsi
0x1800424e1  mov     rax, rbx
0x1800424e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424e9  nop
0x1800424ea  lea     rcx, [rsp+468h+var_258]
0x1800424f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800424f7  nop
0x1800424f8  lea     rcx, [rsp+468h+var_278]
0x180042500  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042505  nop
0x180042506  lea     rcx, [rsp+468h+var_238]
0x18004250e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042513  xorps   xmm0, xmm0
0x180042516  movups  [rsp+468h+var_258], xmm0
0x18004251e  mov     [rsp+468h+var_248], r14
0x180042526  mov     [rsp+468h+var_240], r14
0x18004252e  mov     r8d, 17h
0x180042534  lea     rdx, aMuseSettingsNo; "MUSE Settings Not Found"
0x18004253b  lea     rcx, [rsp+468h+var_258]
0x180042543  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042548  lea     rdx, [rsp+468h+var_258]
0x180042550  lea     rcx, [rsp+468h+var_1E8]
0x180042558  call    ?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Telemetry::Worker::RefreshSettings::Stop(std::wstring const &)
0x18004255d  lea     rcx, [rsp+468h+var_258]
0x180042565  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004256a  nop
0x18004256b  cmp     [rsp+468h+var_418], r14b
0x180042570  jz      loc_1800426C5
0x180042576  mov     rbx, [rsp+468h+Block]
0x18004257b  test    rbx, rbx
0x18004257e  jz      loc_1800426C5
0x180042584  mov     rcx, [rbx]
0x180042587  test    rcx, rcx
0x18004258a  jz      short loc_180042599
0x18004258c  mov     rax, [rcx]
0x18004258f  mov     rax, [rax+10h]
0x180042593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042598  nop
0x180042599  jmp     loc_1800426B7
0x18004259e  cmp     [rsp+468h+var_3D8], r14b
0x1800425a6  jz      short loc_180042612
0x1800425a8  cmp     [rsp+468h+var_3E0], 2
0x1800425b0  jnz     loc_180042EC8
0x1800425b6  lea     rdx, [rsp+468h+var_258]
0x1800425be  mov     rcx, [rsp+468h+Block]
0x1800425c3  call    ?GetUniqueId@WOSCSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WOSCSettings::GetUniqueId(void)
0x1800425c8  mov     r15d, 1
0x1800425ce  mov     [rsp+468h+var_428], r15d
0x1800425d3  lea     rdx, [rsp+468h+S2]
0x1800425d8  cmp     [rsp+468h+var_3E8], 7
0x1800425e1  cmova   rdx, [rsp+468h+S2]; S2
0x1800425e7  mov     r8, [rax+10h]; N
0x1800425eb  cmp     qword ptr [rax+18h], 7
0x1800425f0  jbe     short loc_1800425F5
0x1800425f2  mov     rax, [rax]
0x1800425f5  cmp     r8, [rsp+468h+var_3F0]
0x1800425fa  jnz     short loc_180042612
0x1800425fc  test    r8, r8
0x1800425ff  jz      short loc_18004260D
0x180042601  mov     rcx, rax; S1
0x180042604  call    wmemcmp
0x180042609  test    eax, eax
0x18004260b  jnz     short loc_180042612
0x18004260d  mov     bl, r15b
0x180042610  jmp     short loc_180042615
0x180042612  mov     bl, r14b
0x180042615  test    r15b, 1
0x180042619  jz      short loc_180042631
0x18004261b  and     r15d, 0FFFFFFFEh
0x18004261f  mov     [rsp+468h+var_428], r15d
0x180042624  lea     rcx, [rsp+468h+var_258]
0x18004262c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042631  test    bl, bl
0x180042633  jz      loc_18004272F
0x180042639  xorps   xmm0, xmm0
0x18004263c  movups  [rsp+468h+var_258], xmm0
0x180042644  mov     [rsp+468h+var_248], r14
0x18004264c  mov     [rsp+468h+var_240], r14
0x180042654  mov     r8d, 0Ah
0x18004265a  lea     rdx, aNoChanges; "No Changes"
0x180042661  lea     rcx, [rsp+468h+var_258]
0x180042669  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004266e  lea     rdx, [rsp+468h+var_258]
0x180042676  lea     rcx, [rsp+468h+var_1E8]
0x18004267e  call    ?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Telemetry::Worker::RefreshSettings::Stop(std::wstring const &)
0x180042683  lea     rcx, [rsp+468h+var_258]
0x18004268b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042690  nop
0x180042691  cmp     [rsp+468h+var_418], r14b
0x180042696  jz      short loc_1800426C5
0x180042698  mov     rbx, [rsp+468h+Block]
0x18004269d  test    rbx, rbx
0x1800426a0  jz      short loc_1800426C5
0x1800426a2  mov     rcx, [rbx]
0x1800426a5  test    rcx, rcx
0x1800426a8  jz      short loc_1800426B7
0x1800426aa  mov     rax, [rcx]
0x1800426ad  mov     rax, [rax+10h]
0x1800426b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426b6  nop
0x1800426b7  mov     edx, 58h ; 'X'
0x1800426bc  mov     rcx, rbx; Block
0x1800426bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800426c4  nop
0x1800426c5  cmp     [rsp+468h+var_3D8], r14b
0x1800426cd  jz      short loc_1800426F5
0x1800426cf  movsx   rax, [rsp+468h+var_3E0]
0x1800426d8  add     rax, 1
0x1800426dc  jz      short loc_1800426F5
0x1800426de  sub     rax, 1
0x1800426e2  jz      short loc_1800426F5
0x1800426e4  cmp     rax, 1
0x1800426e8  jz      short loc_1800426F5
0x1800426ea  lea     rcx, [rsp+468h+S2]
0x1800426ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800426f4  nop
0x1800426f5  lea     r13, ??_7RefreshSettings@Worker@Telemetry@Windows@@6B@; const Windows::Telemetry::Worker::RefreshSettings::`vftable'
0x1800426fc  mov     [rsp+468h+var_1E8], r13
0x180042704  lea     rcx, [rsp+468h+var_1E8]
0x18004270c  call    ?Destroy@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180042711  lea     rcx, [rsp+468h+var_1E8]
0x180042719  call    ??1?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004271e  nop
0x18004271f  mov     rcx, rdi; _Mtx_t
0x180042722  call    cs:__imp__Mtx_unlock
0x180042728  xor     al, al
0x18004272a  jmp     loc_180042E9B
0x18004272f  cmp     [rsp+468h+var_418], r14b
0x180042734  jz      loc_180042ECE
0x18004273a  lea     rdx, [rsp+468h+var_388]
0x180042742  mov     rcx, [rsp+468h+Block]
0x180042747  call    ?GetAllSettings@WOSCSettings@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; WOSCSettings::GetAllSettings(void)
  ... truncated ...
```
