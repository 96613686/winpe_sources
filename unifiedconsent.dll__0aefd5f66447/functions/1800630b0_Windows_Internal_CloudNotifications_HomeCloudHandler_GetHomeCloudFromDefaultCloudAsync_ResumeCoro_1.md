# Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudFromDefaultCloudAsync$_ResumeCoro$1

- ea: `0x1800630b0`
- end: `0x18006484c`
- name: `Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudFromDefaultCloudAsync$_ResumeCoro$1`
- size: `6044`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180064854`

## callees

- `0x180002834`
- `0x180002840`
- `0x180002884`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x180005d24`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x1800131f8`
- `0x180013af4`
- `0x180013efc`
- `0x180014364`
- `0x180016498`
- `0x1800164fc`
- `0x180016a58`
- `0x180016d38`
- `0x180016d98`
- `0x18001c1d4`
- `0x18002d8ec`
- `0x1800313a4`
- `0x180031d58`
- `0x1800320c8`
- `0x1800325a8`
- `0x180032768`
- `0x180032928`
- `0x180032eb4`
- `0x18003585c`
- `0x180038b50`
- `0x180040ab0`
- `0x18004b544`
- `0x18004c580`
- `0x18004fed8`
- `0x180051f38`
- `0x18005e2dc`
- `0x18006016c`
- `0x18006036c`
- `0x1800603a4`
- `0x180060b0c`
- `0x180061c00`
- `0x1800630b0`
- `0x18006670c`
- `0x180066c60`
- `0x180066cf8`
- `0x180067338`
- `0x18006da6c`
- `0x18006efe0`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Thrd_yield` at `0x1800637e1`
- `msvcp_win!_Thrd_yield` at `0x180063a1b`
- `msvcp_win!_Thrd_yield` at `0x180063b87`
- `msvcp_win!_Thrd_yield` at `0x180063e1c`
- `msvcp_win!_Thrd_yield` at `0x18006455a`
- `msvcp_win!_Thrd_yield` at `0x180064682`
- `msvcp_win!_Thrd_yield` at `0x1800637e1`
- `msvcp_win!_Thrd_yield` at `0x180063a1b`
- `msvcp_win!_Thrd_yield` at `0x180063b87`
- `msvcp_win!_Thrd_yield` at `0x180063e1c`
- `msvcp_win!_Thrd_yield` at `0x18006455a`
- `msvcp_win!_Thrd_yield` at `0x180064682`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063637`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063680`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006391a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063d17`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063ff1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064032`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064074`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800641a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800645d2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063637`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063680`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006391a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063d17`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180063ff1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064032`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064074`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800641a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800645d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063edd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063edd`

## string_xrefs

- `0x180063f02`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180064384`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x1800646db`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180064375`: `Unable to update service configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
void __fastcall Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudFromDefaultCloudAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r12
  __int64 v3; // r14
  __int64 v4; // rdx
  signed __int32 v5; // eax
  __int64 v6; // rcx
  signed __int32 v7; // ett
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // r11d
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // r9
  __int64 v19; // rax
  _QWORD *v20; // r8
  __int64 v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // edx
  __int64 *v25; // r13
  __int64 v26; // r14
  struct winrt::impl::shared_hstring_header *v27; // r15
  __int64 v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // edx
  __int64 *v32; // r13
  __int64 v33; // r14
  struct winrt::impl::shared_hstring_header *v34; // r15
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r13
  __int64 v38; // r15
  void *v39; // rax
  __int64 v40; // r15
  volatile signed __int32 *v41; // r14
  int v42; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v44; // r14
  int v45; // eax
  HANDLE v46; // rax
  __int64 v47; // r12
  _QWORD *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  const struct winrt::impl::slim_source_location *v52; // rax
  volatile __int64 *v53; // rbx
  volatile signed __int32 *v54; // r14
  volatile signed __int32 *v55; // r14
  volatile signed __int32 *v56; // r14
  volatile signed __int32 *v57; // r14
  int v58; // eax
  HANDLE v59; // rax
  volatile signed __int32 *v60; // r14
  __int64 v61; // rcx
  const struct winrt::impl::slim_source_location *v62; // rax
  volatile __int64 *v63; // r14
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  const struct winrt::impl::slim_source_location *v67; // rax
  volatile __int64 *v68; // rbx
  volatile signed __int32 *v69; // r14
  volatile signed __int32 *v70; // r14
  volatile signed __int32 *v71; // r14
  volatile signed __int32 *v72; // r14
  int v73; // eax
  HANDLE v74; // rax
  __int64 v75; // rcx
  const struct winrt::impl::slim_source_location *v76; // rax
  volatile signed __int32 **v77; // r12
  volatile __int64 *v78; // r14
  const WCHAR *v79; // rax
  volatile signed __int32 **v80; // r13
  __int64 v81; // rcx
  _QWORD *v82; // r8
  __int64 v83; // rax
  volatile signed __int32 **v84; // r15
  unsigned int v85; // edx
  volatile signed __int32 *v86; // r14
  int v87; // eax
  HANDLE v88; // rax
  volatile signed __int32 *v89; // r14
  int v90; // eax
  HANDLE v91; // rax
  volatile signed __int32 *v92; // r14
  int v93; // eax
  HANDLE v94; // rax
  volatile signed __int32 *v95; // r14
  volatile signed __int32 *v96; // r14
  volatile signed __int32 *v97; // r14
  volatile signed __int32 *v98; // r14
  int v99; // eax
  HANDLE v100; // rax
  volatile signed __int32 *v101; // r14
  struct winrt::impl::shared_hstring_header **v102; // rcx
  struct winrt::impl::shared_hstring_header *v103; // rbx
  unsigned int v104; // r14d
  const void *v105; // r15
  struct winrt::impl::shared_hstring_header **v106; // rcx
  struct winrt::impl::shared_hstring_header *v107; // rbx
  unsigned int v108; // r14d
  const void *v109; // r15
  struct winrt::impl::shared_hstring_header *v110; // rbx
  unsigned int v111; // r14d
  const void *v112; // r15
  unsigned int v113; // eax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  _QWORD *v117; // r9
  __int64 v118; // rax
  _QWORD *v119; // r8
  __int64 v120; // rax
  __int64 HomeCloudInnerAsync; // rax
  const struct winrt::impl::slim_source_location *v122; // rax
  volatile __int64 *v123; // rbx
  volatile signed __int32 *v124; // r14
  int v125; // ebx
  HANDLE v126; // rax
  volatile __int64 *v127; // rbx
  int bIgnoreCase; // [rsp+20h] [rbp-318h]
  const char *v129; // [rsp+28h] [rbp-310h]
  const char *v130; // [rsp+30h] [rbp-308h]
  __int64 v131; // [rsp+50h] [rbp-2E8h]
  __int64 *v132; // [rsp+B8h] [rbp-280h]
  _BYTE pExceptionObject[24]; // [rsp+150h] [rbp-1E8h] BYREF
  _BYTE v134[24]; // [rsp+168h] [rbp-1D0h] BYREF
  _BYTE v135[24]; // [rsp+180h] [rbp-1B8h] BYREF
  _BYTE v136[24]; // [rsp+198h] [rbp-1A0h] BYREF
  _BYTE v137[24]; // [rsp+1B0h] [rbp-188h] BYREF
  __int64 v138; // [rsp+1C8h] [rbp-170h]
  __int64 v139; // [rsp+1D8h] [rbp-160h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]
  int v141; // [rsp+348h] [rbp+10h]
  __int64 (__fastcall *v142)(__int64, __int64, __int64, __int64); // [rsp+348h] [rbp+10h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_273;
    case 2:
      v3 = *(_QWORD *)(a1 + 1000);
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v4 = *(_QWORD *)(v3 + 16);
      if ( !v4 )
        goto LABEL_65;
      v5 = *(_DWORD *)(v4 + 8);
      do
      {
        if ( !v5 )
LABEL_65:
          std::_Throw_bad_weak_ptr();
        v6 = (unsigned int)(v5 + 1);
        v7 = v5;
        v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v6, v5);
      }
      while ( v7 != v5 );
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(v3 + 8);
      *(_QWORD *)(a1 + 24) = *(_QWORD *)(v3 + 16);
      *(_BYTE *)(a1 - 64) = 1;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      v8 = *(_QWORD *)(a1 + 1032);
      if ( v8 )
        _InterlockedAdd((volatile signed __int32 *)(v8 + 8), 1u);
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 1024);
      *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 1032);
      Windows::Internal::CloudNotifications::HomeCloudHandler::GetDefaultHomeCloudUri(v6, a1 + 48, a1 + 32);
      *(_QWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 64) = 0;
      v9 = *(_QWORD *)(v3 + 64);
      if ( v9 )
        _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
      *(_QWORD *)(a1 + 56) = *(_QWORD *)(v3 + 56);
      *(_QWORD *)(a1 + 64) = *(_QWORD *)(v3 + 64);
      *(_QWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 80) = 0;
      v10 = *(_QWORD *)(v3 + 48);
      if ( v10 )
        _InterlockedAdd((volatile signed __int32 *)(v10 + 8), 1u);
      *(_QWORD *)(a1 + 72) = *(_QWORD *)(v3 + 40);
      *(_QWORD *)(a1 + 80) = *(_QWORD *)(v3 + 48);
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      v11 = *(_QWORD *)(a1 + 1048);
      if ( v11 )
        _InterlockedAdd((volatile signed __int32 *)(v11 + 8), 1u);
      *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 1040);
      *(_QWORD *)(a1 + 96) = *(_QWORD *)(a1 + 1048);
      Windows::Internal::CloudRequestor::CreateRequestResponseHandler(a1 + 104);
      v12 = *(_DWORD *)(v3 + 24);
      v141 = v12;
      *(_QWORD *)(a1 + 120) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      v13 = *(_QWORD *)(a1 + 1032);
      if ( v13 )
        _InterlockedAdd((volatile signed __int32 *)(v13 + 8), 1u);
      *(_QWORD *)(a1 + 120) = *(_QWORD *)(a1 + 1024);
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(a1 + 1032);
      v14 = *(_QWORD *)(v3 + 32);
      v15 = *(_QWORD *)(a1 + 1072);
      *(_QWORD *)(a1 + 136) = v15;
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v12 = v141;
      }
      *(_QWORD *)(a1 + 144) = 0;
      *(_QWORD *)(a1 + 152) = 0;
      v16 = *(_QWORD *)(v3 + 64);
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      *(_QWORD *)(a1 + 144) = *(_QWORD *)(v3 + 56);
      *(_QWORD *)(a1 + 152) = *(_QWORD *)(v3 + 64);
      *(_QWORD *)(a1 + 160) = 0;
      *(_QWORD *)(a1 + 168) = 0;
      v17 = *(_QWORD *)(a1 + 1064);
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      *(_QWORD *)(a1 + 160) = *(_QWORD *)(a1 + 1056);
      *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 1064);
      v18 = (_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = 0;
      v19 = *(_QWORD *)(a1 + 1048);
      if ( v19 )
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
      *v18 = *(_QWORD *)(a1 + 1040);
      *(_QWORD *)(a1 + 184) = *(_QWORD *)(a1 + 1048);
      v20 = (_QWORD *)(a1 + 192);
      *(_QWORD *)(a1 + 192) = 0;
      *(_QWORD *)(a1 + 200) = 0;
      v21 = *(_QWORD *)(v3 + 48);
      if ( v21 )
        _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
      *v20 = *(_QWORD *)(v3 + 40);
      *(_QWORD *)(a1 + 200) = *(_QWORD *)(v3 + 48);
      v22 = (_QWORD *)(a1 + 208);
      *(_QWORD *)(a1 + 208) = 0;
      *(_QWORD *)(a1 + 216) = 0;
      v23 = *(_QWORD *)(a1 + 112);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      *v22 = *(_QWORD *)(a1 + 104);
      *(_QWORD *)(a1 + 216) = *(_QWORD *)(a1 + 112);
      Windows::Internal::CloudRequestor::CreateCommonHTTPInterface(
        a1 + 224,
        (_DWORD)v22,
        (_DWORD)v20,
        (_DWORD)v18,
        a1 + 160,
        a1 + 144,
        a1 + 136,
        v14,
        a1 + 120,
        v12);
      v25 = (__int64 *)Windows::Internal::CloudNotifications::HomeCloudHandler::PopulateClientInfoString(v3, a1 + 336);
      v26 = -1;
      do
        ++v26;
      while ( *((_WORD *)Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader + v26) );
      if ( (_DWORD)v26 )
      {
        v27 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v26, v24);
        memcpy_s(
          (char *)v27 + 28,
          2LL * (unsigned int)v26,
          Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader,
          2LL * (unsigned int)v26);
      }
      else
      {
        v27 = 0;
      }
      *(_QWORD *)(a1 + 304) = v27;
      v28 = *v25;
      *v25 = 0;
      *(_QWORD *)(a1 + 312) = v28;
      v29 = (_QWORD *)(a1 + 344);
      *(_QWORD *)(a1 + 344) = 0;
      *(_QWORD *)(a1 + 352) = 0;
      v30 = *(_QWORD *)(a1 + 1016);
      if ( v30 )
        _InterlockedIncrement((volatile signed __int32 *)(v30 + 8));
      *v29 = *(_QWORD *)(a1 + 1008);
      *(_QWORD *)(a1 + 352) = *(_QWORD *)(a1 + 1016);
      v32 = (__int64 *)Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(a1 + 360, v29);
      v33 = -1;
      do
        ++v33;
      while ( *((_WORD *)Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader + v33) );
      if ( (_DWORD)v33 )
      {
        v34 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v33, v31);
        memcpy_s(
          (char *)v34 + 28,
          2LL * (unsigned int)v33,
          Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader,
          2LL * (unsigned int)v33);
      }
      else
      {
        v34 = 0;
      }
      *(_QWORD *)(a1 + 320) = v34;
      v35 = *v32;
      *v32 = 0;
      *(_QWORD *)(a1 + 328) = v35;
      *(_QWORD *)(a1 + 784) = a1 + 304;
      *(_QWORD *)(a1 + 792) = a1 + 336;
      v36 = std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(a1 + 240);
      v37 = winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(
              a1 + 368,
              v36);
      v38 = winrt::Windows::Web::Http::HttpMethod::Get();
      v39 = operator new(0x38u);
      *(_QWORD *)(a1 + 808) = v39;
      v40 = std::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>(
              v39,
              v38,
              v37,
              &Name,
              &Windows::Internal::CloudNotifications::HomeCloudHandler::c_defaultCloudPath,
              &Windows::Internal::CloudNotifications::HomeCloudHandler::c_defaultCloudQueryString);
      *(_QWORD *)(a1 + 800) = v40;
      *(_QWORD *)(a1 + 384) = v40 + 16;
      *(_QWORD *)(a1 + 392) = v40;
      if ( *(_QWORD *)(a1 + 376) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 376);
      if ( *(_QWORD *)(a1 + 368) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 368);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 264);
      std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(a1 + 248);
      `eh vector destructor iterator'(
        (void *)(a1 + 304),
        0x10u,
        2u,
        std::pair<winrt::hstring const,winrt::hstring>::~pair<winrt::hstring const,winrt::hstring>);
      v41 = *(volatile signed __int32 **)(a1 + 360);
      if ( v41 )
      {
        v42 = _InterlockedDecrement(v41 + 6);
        if ( v42 )
        {
          if ( v42 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v41);
        }
        *(_QWORD *)(a1 + 360) = 0;
      }
      v44 = *(volatile signed __int32 **)(a1 + 336);
      if ( v44 )
      {
        v45 = _InterlockedDecrement(v44 + 6);
        if ( v45 )
        {
          if ( v45 < 0 )
            abort();
        }
        else
        {
          v46 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v46, 0, (LPVOID)v44);
        }
        *(_QWORD *)(a1 + 336) = 0;
      }
      v47 = *(_QWORD *)(a1 + 224);
      v142 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v47 + 8LL);
      *(_QWORD *)(a1 + 416) = a1 + 400;
      *(_QWORD *)(a1 + 400) = 0;
      *(_QWORD *)(a1 + 408) = 0;
      if ( v40 )
        _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
      v138 = v40 + 16;
      *(_QWORD *)(a1 + 400) = v40 + 16;
      *(_QWORD *)(a1 + 408) = v40;
      v48 = (_QWORD *)(a1 + 432);
      *(_QWORD *)(a1 + 432) = 0;
      *(_QWORD *)(a1 + 440) = 0;
      v49 = *(_QWORD *)(a1 + 1016);
      if ( v49 )
        _InterlockedAdd((volatile signed __int32 *)(v49 + 8), 1u);
      *v48 = *(_QWORD *)(a1 + 1008);
      *(_QWORD *)(a1 + 440) = *(_QWORD *)(a1 + 1016);
      v50 = Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(a1 + 424, v48);
      v51 = v142(v47, a1 + 448, v50, a1 + 400);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v52 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 816);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v52);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 456) = 0;
      *(_QWORD *)(a1 + 464) = v51;
      *(_QWORD *)(a1 + 472) = 0;
      *(_BYTE *)(a1 + 480) = 1;
      v2 = (_WORD *)(a1 + 8);
      *(_WORD *)(a1 + 8) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                              a1 + 456,
                              a1) )
        return;
LABEL_94:
      *(_DWORD *)(a1 + 840) = 0;
      *(_QWORD *)(a1 + 848) = 0;
      *(_QWORD *)(a1 + 856) = 0;
      v61 = *(unsigned int *)(a1 + 476);
      if ( (int)v61 < 0 )
        winrt::throw_hresult(v61, a1 + 840);
      if ( *(_DWORD *)(a1 + 472) == 2 )
      {
        v62 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 864);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v134, v62);
        throw (winrt::hresult_canceled *)v134;
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
        *(_QWORD *)(a1 + 464),
        a1 + 488);
      v63 = *(volatile __int64 **)(a1 + 456);
      if ( v63 )
      {
        while ( _InterlockedExchange64(v63, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 448) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 448);
      if ( *(int *)winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(
                     a1 + 488,
                     a1 + 496) < 0 )
      {
        if ( *(_QWORD *)(a1 + 488) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 384);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 224);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 104);
        winrt::hstring::operator=(a1 - 8, a1 + 48);
        winrt::hstring::~hstring((winrt::hstring *)(a1 + 48));
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
        goto LABEL_272;
      }
      v64 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
              a1 + 488,
              a1 + 504);
      v65 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
              v64,
              a1 + 512);
      v66 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
              v65,
              a1 + 520);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v67 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 888);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v135, v67);
        throw (winrt::hresult_canceled *)v135;
      }
      *(_QWORD *)(a1 + 528) = 0;
      *(_QWORD *)(a1 + 536) = v66;
      *(_QWORD *)(a1 + 544) = 0;
      *(_BYTE *)(a1 + 552) = 1;
      *v2 = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                              a1 + 528,
                              a1) )
        return;
LABEL_146:
      *(_DWORD *)(a1 + 912) = 0;
      *(_QWORD *)(a1 + 920) = 0;
      *(_QWORD *)(a1 + 928) = 0;
      v75 = *(unsigned int *)(a1 + 548);
      if ( (int)v75 < 0 )
        winrt::throw_hresult(v75, a1 + 912);
      if ( *(_DWORD *)(a1 + 544) == 2 )
      {
        v76 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 936);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v136, v76);
        throw (winrt::hresult_canceled *)v136;
      }
      v77 = (volatile signed __int32 **)(a1 + 560);
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,winrt::hstring,unsigned __int64>::GetResults(
        *(_QWORD *)(a1 + 536),
        a1 + 560);
      v78 = *(volatile __int64 **)(a1 + 528);
      if ( v78 )
      {
        while ( _InterlockedExchange64(v78, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 520) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 520);
      if ( *(_QWORD *)(a1 + 512) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 512);
      if ( *(_QWORD *)(a1 + 504) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 504);
      if ( *v77 )
        v79 = (const WCHAR *)*((_QWORD *)*v77 + 2);
      else
        v79 = &Name;
      v80 = (volatile signed __int32 **)(a1 + 568);
      Windows::Internal::CloudRequestor::Common::JsonParser::ParseDefaultCloudString(a1 + 568, v79);
      if ( !*(_QWORD *)(a1 + 568)
        || CompareStringOrdinal(L"https://", -1, *(LPCWCH *)(*(_QWORD *)(a1 + 568) + 16LL), 8, 1) != 2 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1C3,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
          (const char *)0x8007139FLL,
          (int)"DefaultCloud empty or not valid",
          v129);
      }
      v81 = *(_QWORD *)(a1 + 1072);
      *(_QWORD *)(a1 + 576) = v81;
      if ( v81 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 8LL))(v81);
      v82 = (_QWORD *)(a1 + 584);
      *(_QWORD *)(a1 + 584) = 0;
      *(_QWORD *)(a1 + 592) = 0;
      v83 = *(_QWORD *)(a1 + 1032);
      if ( v83 )
        _InterlockedIncrement((volatile signed __int32 *)(v83 + 8));
      *v82 = *(_QWORD *)(a1 + 1024);
      *(_QWORD *)(a1 + 592) = *(_QWORD *)(a1 + 1032);
      v84 = (volatile signed __int32 **)(a1 + 600);
      Windows::Internal::CloudNotifications::HomeCloudHandler::TryGetHomeCloud(
        *(_QWORD *)(a1 + 1000),
        a1 + 600,
        v82,
        a1 + 576);
      if ( *(_BYTE *)(a1 + 608) )
      {
        winrt::hstring::operator=(a1 - 8, a1 + 600);
        if ( *(_BYTE *)(a1 + 608) )
        {
          v86 = *v84;
          if ( *v84 )
          {
            v87 = _InterlockedDecrement(v86 + 6);
            if ( v87 )
            {
              if ( v87 < 0 )
                abort();
            }
            else
            {
              v88 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v88, 0, (LPVOID)v86);
            }
            *v84 = 0;
          }
        }
        v89 = *v80;
        if ( *v80 )
        {
          v90 = _InterlockedDecrement(v89 + 6);
          if ( v90 )
          {
            if ( v90 < 0 )
              abort();
          }
          else
          {
            v91 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v91, 0, (LPVOID)v89);
          }
          *v80 = 0;
        }
        v92 = *v77;
        if ( *v77 )
        {
          v93 = _InterlockedDecrement(v92 + 6);
          if ( v93 )
          {
            if ( v93 < 0 )
              abort();
          }
          else
          {
            v94 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v94, 0, (LPVOID)v92);
          }
          *v77 = 0;
        }
        if ( *(_QWORD *)(a1 + 488) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
        v95 = *(volatile signed __int32 **)(a1 + 800);
        if ( v95 )
        {
          if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
            if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
          }
        }
        v96 = *(volatile signed __int32 **)(a1 + 232);
        if ( v96 )
        {
          if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
            if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
          }
        }
        v97 = *(volatile signed __int32 **)(a1 + 112);
        if ( v97 )
        {
          if ( _InterlockedExchangeAdd(v97 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
            if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
          }
        }
        v98 = *(volatile signed __int32 **)(a1 + 48);
        if ( v98 )
        {
          v99 = _InterlockedDecrement(v98 + 6);
          if ( v99 )
          {
            if ( v99 < 0 )
              abort();
          }
          else
          {
            v100 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v100, 0, (LPVOID)v98);
          }
          *(_QWORD *)(a1 + 48) = 0;
        }
        v101 = *(volatile signed __int32 **)(a1 + 24);
        if ( v101 )
        {
          if ( _InterlockedExchangeAdd(v101 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v101)(v101);
            if ( _InterlockedExchangeAdd(v101 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v101 + 8LL))(v101);
          }
        }
        v2 = (_WORD *)(a1 + 8);
        goto LABEL_272;
      }
      v132 = *(__int64 **)(a1 + 1040);
      v131 = *v132;
      v102 = (struct winrt::impl::shared_hstring_header **)(a1 + 616);
      *(_QWORD *)(a1 + 624) = a1 + 616;
      v103 = *(struct winrt::impl::shared_hstring_header **)(*(_QWORD *)(a1 + 1024) + 8LL);
      if ( !v103 )
        goto LABEL_216;
      if ( (*(_DWORD *)v103 & 1) != 0 )
      {
        v104 = *((_DWORD *)v103 + 1);
        if ( v104 )
        {
          v105 = (const void *)*((_QWORD *)v103 + 2);
          v103 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v104, v85);
          memcpy_s((char *)v103 + 28, 2LL * v104, v105, 2LL * v104);
          v102 = (struct winrt::impl::shared_hstring_header **)(a1 + 616);
        }
        else
        {
LABEL_216:
          v103 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v103 + 6);
      }
      *v102 = v103;
      v106 = (struct winrt::impl::shared_hstring_header **)(a1 + 632);
      *(_QWORD *)(a1 + 640) = a1 + 632;
      v107 = **(struct winrt::impl::shared_hstring_header ***)(a1 + 1024);
      if ( !v107 )
        goto LABEL_222;
      if ( (*(_DWORD *)v107 & 1) != 0 )
      {
        v108 = *((_DWORD *)v107 + 1);
        if ( v108 )
        {
          v109 = (const void *)*((_QWORD *)v107 + 2);
          v107 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v108, v85);
          memcpy_s((char *)v107 + 28, 2LL * v108, v109, 2LL * v108);
          v106 = (struct winrt::impl::shared_hstring_header **)(a1 + 632);
        }
        else
        {
LABEL_222:
          v107 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v107 + 6);
      }
      *v106 = v107;
      v110 = (struct winrt::impl::shared_hstring_header *)*v80;
      if ( !*v80 )
        goto LABEL_228;
      if ( (*(_DWORD *)v110 & 1) != 0 )
      {
        v111 = *((_DWORD *)v110 + 1);
        if ( v111 )
        {
          v112 = (const void *)*((_QWORD *)v110 + 2);
          v110 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v111, v85);
          memcpy_s((char *)v110 + 28, 2LL * v111, v112, 2LL * v111);
          v106 = (struct winrt::impl::shared_hstring_header **)(a1 + 632);
        }
        else
        {
LABEL_228:
          v110 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v110 + 6);
      }
      *(_QWORD *)(a1 + 648) = v110;
      v113 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct winrt::impl::shared_hstring_header **, __int64))(v131 + 32))(
               v132,
               a1 + 648,
               v106,
               a1 + 616);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
        (const char *)v113,
        (int)"Unable to update service configuration",
        v129);
      v114 = *(_QWORD *)(a1 + 1072);
      *(_QWORD *)(a1 + 656) = v114;
      if ( v114 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 8LL))(v114);
      *(_QWORD *)(a1 + 664) = 0;
      *(_QWORD *)(a1 + 672) = 0;
      v115 = *(_QWORD *)(a1 + 1064);
      if ( v115 )
        _InterlockedAdd((volatile signed __int32 *)(v115 + 8), 1u);
      *(_QWORD *)(a1 + 664) = *(_QWORD *)(a1 + 1056);
      *(_QWORD *)(a1 + 672) = *(_QWORD *)(a1 + 1064);
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 688) = 0;
      v116 = *(_QWORD *)(a1 + 1048);
      if ( v116 )
        _InterlockedAdd((volatile signed __int32 *)(v116 + 8), 1u);
      *(_QWORD *)(a1 + 680) = *(_QWORD *)(a1 + 1040);
      *(_QWORD *)(a1 + 688) = *(_QWORD *)(a1 + 1048);
      v117 = (_QWORD *)(a1 + 696);
      *(_QWORD *)(a1 + 696) = 0;
      *(_QWORD *)(a1 + 704) = 0;
      v118 = *(_QWORD *)(a1 + 1032);
      if ( v118 )
        _InterlockedAdd((volatile signed __int32 *)(v118 + 8), 1u);
      *v117 = *(_QWORD *)(a1 + 1024);
      *(_QWORD *)(a1 + 704) = *(_QWORD *)(a1 + 1032);
      v119 = (_QWORD *)(a1 + 712);
      *(_QWORD *)(a1 + 712) = 0;
      *(_QWORD *)(a1 + 720) = 0;
      v120 = *(_QWORD *)(a1 + 1016);
      if ( v120 )
        _InterlockedAdd((volatile signed __int32 *)(v120 + 8), 1u);
      *v119 = *(_QWORD *)(a1 + 1008);
      *(_QWORD *)(a1 + 720) = *(_QWORD *)(a1 + 1016);
      v2 = (_WORD *)(a1 + 8);
      HomeCloudInnerAsync = Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudInnerAsync(
                              *(_QWORD *)(a1 + 1000),
                              (int)a1 + 728,
                              (_DWORD)v119,
                              (_DWORD)v117,
                              a1 + 680,
                              a1 + 664,
                              a1 + 656);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v122 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 960);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v137, v122);
        throw (winrt::hresult_canceled *)v137;
      }
      *(_QWORD *)(a1 + 736) = 0;
      *(_QWORD *)(a1 + 744) = HomeCloudInnerAsync;
      *(_QWORD *)(a1 + 752) = 0;
      *(_BYTE *)(a1 + 760) = 1;
      *v2 = 10;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                              a1 + 736,
                              a1) )
        return;
LABEL_263:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,1>::await_resume(
        a1 + 736,
        a1 + 768);
      v127 = *(volatile __int64 **)(a1 + 736);
      if ( v127 )
      {
        v139 = *(_QWORD *)(a1 + 736);
        while ( _InterlockedExchange64(v127, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 728) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 728);
      LOBYTE(bIgnoreCase) = *(_QWORD *)(a1 + 768) == 0;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
        (const char *)0x8007139FLL,
        bIgnoreCase,
        (bool)"Empty Url from GetHomeCloudInnerAsync",
        v130);
      winrt::hstring::operator=(a1 - 8, a1 + 768);
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 768));
      std::optional<winrt::hstring>::~optional<winrt::hstring>(a1 + 600);
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 568));
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 560));
      if ( *(_QWORD *)(a1 + 488) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 384);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 224);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 104);
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 48));
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
LABEL_272:
      *(_QWORD *)(a1 + 776) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::final_suspend_awaiter::await_suspend() )
      {
LABEL_273:
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::~promise_type(a1 - 112);
        Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudFromDefaultCloudAsync_::_14_::_parameters_::__parameters_(v2 + 496);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x4B0u);
      }
      return;
    case 6:
      goto LABEL_94;
    case 7:
      v53 = *(volatile __int64 **)(a1 + 456);
      if ( v53 )
      {
        while ( _InterlockedExchange64(v53, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 448) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 448);
      v54 = *(volatile signed __int32 **)(a1 + 800);
      if ( v54 )
      {
        if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
      v55 = *(volatile signed __int32 **)(a1 + 232);
      if ( v55 )
      {
        if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
          if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
        }
      }
      v56 = *(volatile signed __int32 **)(a1 + 112);
      if ( v56 )
      {
        if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      v57 = *(volatile signed __int32 **)(a1 + 48);
      if ( v57 )
      {
        v58 = _InterlockedDecrement(v57 + 6);
        if ( v58 )
        {
          if ( v58 < 0 )
            abort();
        }
        else
        {
          v59 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v59, 0, (LPVOID)v57);
        }
        *(_QWORD *)(a1 + 48) = 0;
      }
      v60 = *(volatile signed __int32 **)(a1 + 24);
      if ( v60 )
      {
        if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
          if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_93;
        }
      }
      goto LABEL_273;
    case 8:
      goto LABEL_146;
    case 9:
      v68 = *(volatile __int64 **)(a1 + 528);
      if ( v68 )
      {
        while ( _InterlockedExchange64(v68, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 520) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 520);
      if ( *(_QWORD *)(a1 + 512) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 512);
      if ( *(_QWORD *)(a1 + 504) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 504);
      if ( *(_QWORD *)(a1 + 488) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
      v69 = *(volatile signed __int32 **)(a1 + 800);
      if ( v69 )
      {
        if ( _InterlockedExchangeAdd(v69 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
          if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
        }
      }
      v70 = *(volatile signed __int32 **)(a1 + 232);
      if ( v70 )
      {
        if ( _InterlockedExchangeAdd(v70 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
          if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
        }
      }
      v71 = *(volatile signed __int32 **)(a1 + 112);
      if ( v71 )
      {
        if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
          if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
        }
      }
      v72 = *(volatile signed __int32 **)(a1 + 48);
      if ( v72 )
      {
        v73 = _InterlockedDecrement(v72 + 6);
        if ( v73 )
        {
          if ( v73 < 0 )
            abort();
        }
        else
        {
          v74 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v74, 0, (LPVOID)v72);
        }
        *(_QWORD *)(a1 + 48) = 0;
      }
      v60 = *(volatile signed __int32 **)(a1 + 24);
      if ( v60 )
      {
        if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
          if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
LABEL_93:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
        }
      }
      goto LABEL_273;
    case 0xA:
      goto LABEL_263;
    case 0xB:
      v123 = *(volatile __int64 **)(a1 + 736);
      if ( v123 )
      {
        v139 = *(_QWORD *)(a1 + 736);
        while ( _InterlockedExchange64(v123, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 728) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 728);
      if ( *(_BYTE *)(a1 + 608) )
      {
        v124 = *(volatile signed __int32 **)(a1 + 600);
        if ( v124 )
        {
          v125 = _InterlockedDecrement(v124 + 6);
          if ( v125 )
          {
            if ( v125 < 0 )
              abort();
          }
          else
          {
            v126 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v126, 0, (LPVOID)v124);
          }
          *(_QWORD *)(a1 + 600) = 0;
        }
      }
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 568));
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 560));
      if ( *(_QWORD *)(a1 + 488) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 384);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 224);
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 104);
      winrt::hstring::~hstring((winrt::hstring *)(a1 + 48));
      std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
      goto LABEL_273;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1800630b0  mov     rax, rsp
0x1800630b3  mov     [rax+8], rcx
0x1800630b7  push    rbx
0x1800630b8  push    rsi
0x1800630b9  push    rdi
0x1800630ba  push    r12
0x1800630bc  push    r13
0x1800630be  push    r14
0x1800630c0  push    r15
0x1800630c2  sub     rsp, 300h
0x1800630c9  mov     rdi, rcx
0x1800630cc  lea     r12, [rdi+8]
0x1800630d0  movzx   eax, word ptr [r12]
0x1800630d5  mov     [rsp+338h+var_2D8], ax
0x1800630da  mov     r13d, 1
0x1800630e0  add     ax, r13w
0x1800630e4  cmp     ax, 0Ch; switch 13 cases
0x1800630e8  ja      def_180063108; jumptable 0000000180063108 default case, cases 1,5,6
0x1800630ee  mov     [rsp+338h+var_2D0], r12
0x1800630f3  movsx   rax, ax
0x1800630f7  lea     rdx, cs:180000000h
0x1800630fe  mov     ecx, ds:(jpt_180063108 - 180000000h)[rdx+rax*4]
0x180063105  add     rcx, rdx
0x180063108  jmp     rcx; switch jump
0x18006310a  xor     esi, esi; jumptable 0000000180063108 case 4
0x18006310c  jmp     loc_1800647D6
0x180063111  xor     esi, esi; jumptable 0000000180063108 case 3
0x180063113  mov     r14, [r12+3E0h]
0x18006311b  mov     [rdi+10h], rsi
0x18006311f  mov     [rdi+18h], rsi
0x180063123  mov     rdx, [r14+10h]
0x180063127  test    rdx, rdx
0x18006312a  jz      loc_1800637C3
0x180063130  mov     eax, [rdx+8]
0x180063133  jmp     short loc_18006313F
0x180063135  lea     ecx, [rax+1]
0x180063138  lock cmpxchg [rdx+8], ecx
0x18006313d  jz      short loc_180063148
0x18006313f  test    eax, eax
0x180063141  jnz     short loc_180063135
0x180063143  jmp     loc_1800637C3
0x180063148  mov     rax, [r14+8]
0x18006314c  mov     [rdi+10h], rax
0x180063150  mov     rax, [r14+10h]
0x180063154  mov     [rdi+18h], rax
0x180063158  mov     [rdi-40h], r13b
0x18006315c  lea     rbx, [rdi+20h]
0x180063160  mov     [rbx], rsi
0x180063163  mov     [rdi+28h], rsi
0x180063167  mov     rax, [rbx+3E8h]
0x18006316e  test    rax, rax
0x180063171  jz      short loc_180063178
0x180063173  lock add [rax+8], r13d
0x180063178  mov     rax, [rbx+3E0h]
0x18006317f  mov     [rbx], rax
0x180063182  mov     rax, [rbx+3E8h]
0x180063189  mov     [rdi+28h], rax
0x18006318d  mov     r8, rbx
0x180063190  lea     rdx, [rdi+30h]
0x180063194  call    ?GetDefaultHomeCloudUri@HomeCloudHandler@CloudNotifications@Internal@Windows@@AEAA?AUhstring@winrt@@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z; Windows::Internal::CloudNotifications::HomeCloudHandler::GetDefaultHomeCloudUri(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)
0x180063199  nop
0x18006319a  lea     r9, [rdi+38h]
0x18006319e  mov     [r9], rsi
0x1800631a1  mov     [rdi+40h], rsi
0x1800631a5  mov     rax, [r14+40h]
0x1800631a9  test    rax, rax
0x1800631ac  jz      short loc_1800631B3
0x1800631ae  lock add [rax+8], r13d
0x1800631b3  mov     rax, [r14+38h]
0x1800631b7  mov     [r9], rax
0x1800631ba  mov     rax, [r14+40h]
0x1800631be  mov     [rdi+40h], rax
0x1800631c2  lea     r8, [rdi+48h]
0x1800631c6  mov     [r8], rsi
0x1800631c9  mov     [rdi+50h], rsi
0x1800631cd  mov     rax, [r14+30h]
0x1800631d1  test    rax, rax
0x1800631d4  jz      short loc_1800631DB
0x1800631d6  lock add [rax+8], r13d
0x1800631db  mov     rax, [r14+28h]
0x1800631df  mov     [r8], rax
0x1800631e2  mov     rax, [r14+30h]
0x1800631e6  mov     [rdi+50h], rax
0x1800631ea  lea     rdx, [rdi+58h]
0x1800631ee  mov     [rdx], rsi
0x1800631f1  mov     [rdi+60h], rsi
0x1800631f5  mov     rax, [rdi+418h]
0x1800631fc  test    rax, rax
0x1800631ff  jz      short loc_180063206
0x180063201  lock add [rax+8], r13d
0x180063206  mov     rax, [rdi+410h]
0x18006320d  mov     [rdx], rax
0x180063210  mov     rax, [rdi+418h]
0x180063217  mov     [rdi+60h], rax
0x18006321b  lea     rcx, [rdi+68h]
0x18006321f  call    ?CreateRequestResponseHandler@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VIRequestResponseHandler@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VITokenBroker@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@5@@Z; Windows::Internal::CloudRequestor::CreateRequestResponseHandler(std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::ITokenBroker>,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>)
0x180063224  nop
0x180063225  mov     r11d, [r14+18h]
0x180063229  mov     dword ptr [rsp+338h+arg_8], r11d
0x180063231  lea     r12, [rdi+78h]
0x180063235  mov     [r12], rsi
0x180063239  mov     [rdi+80h], rsi
0x180063240  mov     rax, [rbx+3E8h]
0x180063247  test    rax, rax
0x18006324a  jz      short loc_180063251
0x18006324c  lock add [rax+8], r13d
0x180063251  mov     rax, [rbx+3E0h]
0x180063258  mov     [r12], rax
0x18006325c  mov     rax, [rbx+3E8h]
0x180063263  mov     [rdi+80h], rax
0x18006326a  mov     rbx, [r14+20h]
0x18006326e  lea     r13, [rdi+88h]
0x180063275  mov     rcx, [rdi+430h]
0x18006327c  mov     [r13+0], rcx
0x180063280  test    rcx, rcx
0x180063283  jz      short loc_180063299
0x180063285  mov     rax, [rcx]
0x180063288  mov     rax, [rax+8]
0x18006328c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063291  mov     r11d, dword ptr [rsp+338h+arg_8]
0x180063299  lea     rcx, [rdi+90h]
0x1800632a0  mov     [rcx], rsi
0x1800632a3  mov     [rdi+98h], rsi
0x1800632aa  mov     rax, [r14+40h]
0x1800632ae  test    rax, rax
0x1800632b1  jz      short loc_1800632B7
0x1800632b3  lock inc dword ptr [rax+8]
0x1800632b7  mov     rax, [r14+38h]
0x1800632bb  mov     [rcx], rax
0x1800632be  mov     rax, [r14+40h]
0x1800632c2  mov     [rdi+98h], rax
0x1800632c9  lea     r10, [rdi+0A0h]
0x1800632d0  mov     [r10], rsi
0x1800632d3  mov     [rdi+0A8h], rsi
0x1800632da  mov     rax, [rdi+428h]
0x1800632e1  test    rax, rax
0x1800632e4  jz      short loc_1800632EA
0x1800632e6  lock inc dword ptr [rax+8]
0x1800632ea  mov     rax, [rdi+420h]
0x1800632f1  mov     [r10], rax
0x1800632f4  mov     rax, [rdi+428h]
0x1800632fb  mov     [rdi+0A8h], rax
0x180063302  lea     r9, [rdi+0B0h]
0x180063309  mov     [r9], rsi
0x18006330c  mov     [rdi+0B8h], rsi
0x180063313  mov     rax, [rdi+418h]
0x18006331a  test    rax, rax
0x18006331d  jz      short loc_180063323
0x18006331f  lock inc dword ptr [rax+8]
0x180063323  mov     rax, [rdi+410h]
0x18006332a  mov     [r9], rax
0x18006332d  mov     rax, [rdi+418h]
0x180063334  mov     [rdi+0B8h], rax
0x18006333b  lea     r8, [rdi+0C0h]
0x180063342  mov     [r8], rsi
0x180063345  mov     [rdi+0C8h], rsi
0x18006334c  mov     rax, [r14+30h]
0x180063350  test    rax, rax
0x180063353  jz      short loc_180063359
0x180063355  lock inc dword ptr [rax+8]
0x180063359  mov     rax, [r14+28h]
0x18006335d  mov     [r8], rax
0x180063360  mov     rax, [r14+30h]
0x180063364  mov     [rdi+0C8h], rax
0x18006336b  lea     rdx, [rdi+0D0h]
0x180063372  mov     [rdx], rsi
0x180063375  mov     [rdi+0D8h], rsi
0x18006337c  mov     rax, [rdi+70h]
0x180063380  test    rax, rax
0x180063383  jz      short loc_18006338E
0x180063385  mov     [rsp+338h+var_2C0], rax
0x18006338a  lock inc dword ptr [rax+8]
0x18006338e  mov     rax, [rdi+68h]
0x180063392  mov     [rsp+338h+var_2C8], rax
0x180063397  mov     [rdx], rax
0x18006339a  mov     rax, [rdi+70h]
0x18006339e  mov     [rsp+338h+var_2C0], rax
0x1800633a3  mov     [rdi+0D8h], rax
0x1800633aa  mov     [rsp+338h+var_2F0], r11d
0x1800633af  mov     [rsp+338h+var_2F8], r12
0x1800633b4  mov     [rsp+338h+var_300], rbx
0x1800633b9  mov     [rsp+338h+var_308], r13
0x1800633be  mov     qword ptr [rsp+338h+var_310], rcx
0x1800633c3  mov     qword ptr [rsp+338h+bIgnoreCase], r10
0x1800633c8  lea     rcx, [rdi+0E0h]
0x1800633cf  call    ?CreateCommonHTTPInterface@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VICommonHttpInterface@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIRequestResponseHandler@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VITokenBroker@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@5@UIWebAccount@Credentials@Security@3winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@5@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@5@W4TokenRefreshOption@123@@Z; Windows::Internal::CloudRequestor::CreateCommonHTTPInterface(std::shared_ptr<Windows::Internal::CloudRequestor::IRequestResponseHandler>,std::shared_ptr<Windows::Internal::CloudRequestor::ITokenBroker>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>,winrt::Windows::Security::Credentials::IWebAccount,std::chrono::duration<__int64,std::ratio<1,10000000>>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,Windows::Internal::CloudRequestor::TokenRefreshOption)
0x1800633d4  nop
0x1800633d5  lea     rdx, [rdi+150h]
0x1800633dc  mov     rcx, r14
0x1800633df  call    ?PopulateClientInfoString@HomeCloudHandler@CloudNotifications@Internal@Windows@@AEAA?AUhstring@winrt@@XZ; Windows::Internal::CloudNotifications::HomeCloudHandler::PopulateClientInfoString(void)
0x1800633e4  mov     r13, rax
0x1800633e7  mov     r12, cs:?c_afsClientInfoHeader@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader
0x1800633ee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800633f2  mov     r14, rbx
0x1800633f5  inc     r14
0x1800633f8  cmp     [r12+r14*2], si
0x1800633fd  jnz     short loc_1800633F5
0x1800633ff  test    r14d, r14d
0x180063402  jnz     short loc_180063409
0x180063404  mov     r15, rsi
0x180063407  jmp     short loc_180063429
0x180063409  mov     ecx, r14d; this
0x18006340c  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180063411  mov     r15, rax
0x180063414  mov     edx, r14d
0x180063417  add     rdx, rdx; DestinationSize
0x18006341a  lea     rcx, [rax+1Ch]; Destination
0x18006341e  mov     r9, rdx; SourceSize
0x180063421  mov     r8, r12; Source
0x180063424  call    memcpy_s
0x180063429  mov     [rdi+130h], r15
0x180063430  mov     rax, [r13+0]
0x180063434  mov     [r13+0], rsi
0x180063438  mov     [rdi+138h], rax
0x18006343f  lea     rdx, [rdi+158h]
0x180063446  mov     [rdx], rsi
0x180063449  mov     [rdi+160h], rsi
0x180063450  mov     rax, [rdi+3F8h]
0x180063457  test    rax, rax
0x18006345a  jz      short loc_180063460
0x18006345c  lock inc dword ptr [rax+8]
0x180063460  mov     rax, [rdi+3F0h]
0x180063467  mov     [rdx], rax
0x18006346a  mov     rax, [rdi+3F8h]
0x180063471  mov     [rdi+160h], rax
0x180063478  lea     rcx, [rdi+168h]
0x18006347f  call    ?ToString@CorrelationVectorUtils@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@Z; Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(std::shared_ptr<TraceLoggingCorrelationVector>)
0x180063484  mov     r13, rax
0x180063487  mov     r12, cs:?c_afsCvHeader@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader
0x18006348e  mov     r14, rbx
0x180063491  inc     r14
0x180063494  cmp     [r12+r14*2], si
0x180063499  jnz     short loc_180063491
0x18006349b  test    r14d, r14d
0x18006349e  jnz     short loc_1800634A5
0x1800634a0  mov     r15, rsi
0x1800634a3  jmp     short loc_1800634C5
0x1800634a5  mov     ecx, r14d; this
0x1800634a8  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800634ad  mov     r15, rax
0x1800634b0  mov     edx, r14d
0x1800634b3  add     rdx, rdx; DestinationSize
0x1800634b6  lea     rcx, [rax+1Ch]; Destination
0x1800634ba  mov     r9, rdx; SourceSize
0x1800634bd  mov     r8, r12; Source
0x1800634c0  call    memcpy_s
0x1800634c5  mov     [rdi+140h], r15
0x1800634cc  mov     rax, [r13+0]
0x1800634d0  mov     [r13+0], rsi
0x1800634d4  mov     [rdi+148h], rax
0x1800634db  lea     rdx, [rdi+310h]
0x1800634e2  lea     rax, [rdi+130h]
0x1800634e9  mov     [rdx], rax
0x1800634ec  lea     rax, [rdi+150h]
0x1800634f3  mov     [rdi+318h], rax
0x1800634fa  lea     rcx, [rdi+0F0h]
0x180063501  call    ??0?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@QEAA@V?$initializer_list@U?$pair@$$CBUhstring@winrt@@U12@@std@@@1@@Z; std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(std::initializer_list<std::pair<winrt::hstring const,winrt::hstring>>)
0x180063506  nop
0x180063507  lea     r12, [rdi+170h]
0x18006350e  mov     rdx, rax
0x180063511  mov     rcx, r12
0x180063514  call    ??$single_threaded_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@winrt@@YA?AU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@Windows@0@$$QEAV?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@@Z; winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(std::unordered_map<winrt::hstring,winrt::hstring> &&)
0x180063519  mov     r13, rax
0x18006351c  lea     r14, [rdi+178h]
0x180063523  mov     rcx, r14
0x180063526  call    ?Get@HttpMethod@Http@Web@Windows@winrt@@SA@XZ; winrt::Windows::Web::Http::HttpMethod::Get(void)
0x18006352b  mov     r15, rax
0x18006352e  mov     ecx, 38h ; '8'; Size
0x180063533  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063538  mov     [rdi+328h], rax
0x18006353f  mov     [rsp+338h+var_218], rax
0x180063547  lea     rcx, ?c_defaultCloudQueryString@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_defaultCloudQueryString
0x18006354e  mov     qword ptr [rsp+338h+var_310], rcx
0x180063553  lea     rcx, ?c_defaultCloudPath@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_defaultCloudPath
0x18006355a  mov     qword ptr [rsp+338h+bIgnoreCase], rcx
0x18006355f  lea     r9, Name
0x180063566  mov     r8, r13
0x180063569  mov     rdx, r15
0x18006356c  mov     rcx, rax
0x18006356f  call    ??$?0UHttpMethod@Http@Web@Windows@winrt@@U?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@34@AEAY00$$CBGAEBQEBGAEBQEBG@?$_Ref_count_obj2@URequestItem@CloudRequestor@Internal@Windows@@@std@@QEAA@$$QEAUHttpMethod@Http@Web@Windows@winrt@@$$QEAU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@56@AEAY00$$CBGAEBQEBG3@Z; std::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>(winrt::Windows::Web::Http::HttpMethod &&,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::hstring> &&,ushort const (&)[1],ushort const * const &,ushort const * const &)
0x180063574  mov     r15, rax
0x180063577  mov     [rdi+320h], rax
0x18006357e  lea     r13, [rax+10h]
0x180063582  mov     [rdi+180h], r13
0x180063589  mov     [rdi+188h], rax
0x180063590  mov     rdx, [r14]
0x180063593  mov     [rsp+338h+var_210], rdx
0x18006359b  test    rdx, rdx
0x18006359e  jz      short loc_1800635A9
0x1800635a0  mov     rcx, r14
0x1800635a3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800635a8  nop
0x1800635a9  mov     rax, [r12]
0x1800635ad  mov     [rsp+338h+var_208], rax
0x1800635b5  test    rax, rax
0x1800635b8  jz      short loc_1800635C3
0x1800635ba  mov     rcx, r12
0x1800635bd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800635c2  nop
0x1800635c3  lea     rcx, [rdi+108h]
  ... truncated ...
```
