# Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudInnerAsync$_ResumeCoro$1

- ea: `0x180064ae0`
- end: `0x180066704`
- name: `Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudInnerAsync$_ResumeCoro$1`
- size: `7204`
- prototype: ``
- caller_count: `1`
- callee_count: `55`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006670c`

## callees

- `0x180002810`
- `0x180002834`
- `0x180002840`
- `0x180002884`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x1800038f9`
- `0x180005d24`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x180010654`
- `0x1800106cc`
- `0x1800131f8`
- `0x180013724`
- `0x1800139fc`
- `0x180013af4`
- `0x180013efc`
- `0x180014364`
- `0x180016498`
- `0x1800164fc`
- `0x180016a58`
- `0x180016d38`
- `0x180016d98`
- `0x180019494`
- `0x18001c1d4`
- `0x18001cabc`
- `0x18002d8ec`
- `0x180030b2c`
- `0x1800313a4`
- `0x180031d58`
- `0x1800320c8`
- `0x1800325a8`
- `0x180032768`
- `0x18003585c`
- `0x180038b50`
- `0x180040ab0`
- `0x18004b544`
- `0x180051f38`
- `0x18005e2dc`
- `0x1800602cc`
- `0x1800603a4`
- `0x180060700`
- `0x180060b0c`
- `0x180060dcc`
- `0x1800616c4`
- `0x180064ae0`
- `0x180066c60`

## import_xrefs

- `msvcp_win!_Thrd_yield` at `0x18006521b`
- `msvcp_win!_Thrd_yield` at `0x180065450`
- `msvcp_win!_Thrd_yield` at `0x1800655d7`
- `msvcp_win!_Thrd_yield` at `0x180065869`
- `msvcp_win!_Thrd_yield` at `0x18006521b`
- `msvcp_win!_Thrd_yield` at `0x180065450`
- `msvcp_win!_Thrd_yield` at `0x1800655d7`
- `msvcp_win!_Thrd_yield` at `0x180065869`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065062`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800650b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065d8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065de9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006603d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800660a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065062`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800650b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065d8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180065de9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006603d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800660a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065fa6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180065fa6`

## string_xrefs

- `0x180065a11`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180065d2a`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180065fdb`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180066481`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x180066578`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`
- `0x1800659ff`: `Protocol Config Missing Config for %ls`
- `0x180066569`: `Unable to update service configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=40 #try_helpers=2
void __fastcall Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudInnerAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // r14
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // r8
  __int64 v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // r10
  unsigned int v20; // edx
  __int64 *v21; // r13
  __int64 v22; // r14
  struct winrt::impl::shared_hstring_header *v23; // r15
  __int64 v24; // rax
  _QWORD *v25; // rdx
  __int64 v26; // rax
  unsigned int v27; // edx
  __int64 *v28; // r13
  __int64 v29; // r14
  struct winrt::impl::shared_hstring_header *v30; // r15
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r13
  __int64 v34; // r14
  void *v35; // rax
  __int64 v36; // r14
  __int64 v37; // r12
  void *v38; // r15
  int v39; // eax
  HANDLE ProcessHeap; // rax
  __int64 v41; // r12
  void *v42; // r15
  int v43; // eax
  HANDLE v44; // rax
  __int64 v45; // r12
  _QWORD *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  const struct winrt::impl::slim_source_location *v50; // rax
  _WORD *v51; // r12
  volatile __int64 *v52; // rbx
  volatile signed __int32 *v53; // r14
  volatile signed __int32 *v54; // r14
  volatile signed __int32 *v55; // r14
  volatile signed __int32 *v56; // r14
  const WCHAR *v57; // r13
  __int64 v58; // rcx
  const struct winrt::impl::slim_source_location *v59; // rax
  volatile __int64 *v60; // r15
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  const struct winrt::impl::slim_source_location *v64; // rax
  volatile __int64 *v65; // rbx
  volatile signed __int32 *v66; // r14
  volatile signed __int32 *v67; // r14
  volatile signed __int32 *v68; // r14
  __int64 v69; // rcx
  const struct winrt::impl::slim_source_location *v70; // rax
  __int64 v71; // r12
  volatile __int64 *v72; // r14
  __int64 *v73; // r14
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r9
  unsigned __int64 v77; // r8
  unsigned __int64 i; // rdx
  __int64 v79; // r13
  volatile signed __int32 *v80; // r14
  int v81; // eax
  HANDLE v82; // rax
  void *v83; // r14
  int v84; // eax
  HANDLE v85; // rax
  volatile signed __int32 *v86; // r14
  volatile signed __int32 *v87; // r14
  volatile signed __int32 *v88; // r14
  volatile signed __int32 *v89; // r14
  __int64 *v90; // r14
  __int64 v91; // rdx
  __int64 v92; // rcx
  unsigned __int64 v93; // r8
  unsigned __int64 v94; // rdx
  __int64 v95; // rax
  __int64 v96; // r15
  volatile signed __int32 *v97; // r14
  int v98; // eax
  HANDLE v99; // rax
  void *v100; // r14
  int v101; // eax
  HANDLE v102; // rax
  volatile signed __int32 *v103; // r14
  volatile signed __int32 *v104; // r14
  volatile signed __int32 *v105; // r14
  const WCHAR **v106; // r14
  const WCHAR *v107; // r8
  volatile signed __int32 *v108; // r15
  int v109; // eax
  HANDLE v110; // rax
  void *v111; // r14
  int v112; // eax
  HANDLE v113; // rax
  volatile signed __int32 *v114; // r14
  volatile signed __int32 *v115; // r14
  volatile signed __int32 *v116; // r14
  const WCHAR *v117; // rcx
  __int64 v118; // r15
  int v119; // eax
  __int64 v120; // rbx
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 *v123; // rdx
  unsigned __int64 v124; // rax
  char *v125; // r13
  size_t v126; // rbx
  __int64 v127; // r15
  __int64 v128; // rcx
  _QWORD *v129; // rdx
  __int64 v130; // rax
  int HomeCloudRegistryCache; // eax
  const WCHAR *v132; // rax
  __int64 v133; // r15
  __int64 v134; // r13
  __int64 v135; // rax
  unsigned int v136; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-398h]
  char *v138; // [rsp+28h] [rbp-390h]
  __int64 v139; // [rsp+50h] [rbp-368h]
  __int64 v140; // [rsp+50h] [rbp-368h]
  __int64 (__fastcall *Src)(__int64, __int64, __int64, __int64, const unsigned __int16 *const *, const WCHAR *); // [rsp+58h] [rbp-360h]
  unsigned __int64 Srca; // [rsp+58h] [rbp-360h]
  const WCHAR *Srcb; // [rsp+58h] [rbp-360h]
  __int64 (__fastcall *Srcc)(__int64, __int64, __int64, __int64); // [rsp+58h] [rbp-360h]
  int v145; // [rsp+60h] [rbp-358h]
  __int64 v146; // [rsp+68h] [rbp-350h]
  int v147; // [rsp+80h] [rbp-338h]
  _BYTE v148[24]; // [rsp+160h] [rbp-258h] BYREF
  _BYTE v149[24]; // [rsp+178h] [rbp-240h] BYREF
  _BYTE v150[24]; // [rsp+190h] [rbp-228h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1A8h] [rbp-210h] BYREF
  __int64 v152; // [rsp+1C0h] [rbp-1F8h]
  __int64 v153; // [rsp+1D8h] [rbp-1E0h]
  const WCHAR *v154; // [rsp+210h] [rbp-1A8h]
  __int64 v155; // [rsp+220h] [rbp-198h]
  unsigned __int64 v156; // [rsp+228h] [rbp-190h]
  __int64 v157; // [rsp+230h] [rbp-188h]
  __int64 v158; // [rsp+240h] [rbp-178h]
  unsigned __int64 v159; // [rsp+248h] [rbp-170h]
  __int64 v160; // [rsp+250h] [rbp-168h]
  __int64 v161; // [rsp+260h] [rbp-158h]
  unsigned __int64 v162; // [rsp+268h] [rbp-150h]
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v146 = a1 + 8;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 0xAu )
  {
LABEL_296:
    __debugbreak();
    return;
  }
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_294;
    case 0:
    case 4:
    case 5:
      goto LABEL_296;
    case 2:
      *(_DWORD *)(a1 + 960) = 0;
      v2 = *(_QWORD *)(a1 + 1176);
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v3 = *(_QWORD *)(v2 + 16);
      if ( !v3 )
        goto LABEL_64;
      v4 = *(_DWORD *)(v3 + 8);
      do
      {
        if ( !v4 )
LABEL_64:
          std::_Throw_bad_weak_ptr();
        v5 = v4;
        v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
      }
      while ( v5 != v4 );
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(v2 + 8);
      *(_QWORD *)(a1 + 24) = *(_QWORD *)(v2 + 16);
      *(_BYTE *)(a1 - 64) = 1;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      v6 = *(_QWORD *)(v2 + 64);
      if ( v6 )
        _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(v2 + 56);
      *(_QWORD *)(a1 + 40) = *(_QWORD *)(v2 + 64);
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      v7 = *(_QWORD *)(v2 + 48);
      if ( v7 )
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(v2 + 40);
      *(_QWORD *)(a1 + 56) = *(_QWORD *)(v2 + 48);
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      v8 = *(_QWORD *)(a1 + 1224);
      if ( v8 )
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
      *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 1216);
      *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 1224);
      Windows::Internal::CloudRequestor::CreateRequestResponseHandler(a1 + 80);
      v145 = *(_DWORD *)(v2 + 24);
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 104) = 0;
      v9 = *(_QWORD *)(a1 + 1208);
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      *(_QWORD *)(a1 + 96) = *(_QWORD *)(a1 + 1200);
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 1208);
      v10 = *(_QWORD *)(v2 + 32);
      v11 = *(_QWORD *)(a1 + 1248);
      *(_QWORD *)(a1 + 112) = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      *(_QWORD *)(a1 + 120) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      v12 = *(_QWORD *)(v2 + 64);
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      *(_QWORD *)(a1 + 120) = *(_QWORD *)(v2 + 56);
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(v2 + 64);
      *(_QWORD *)(a1 + 136) = 0;
      *(_QWORD *)(a1 + 144) = 0;
      v13 = *(_QWORD *)(a1 + 1240);
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
      *(_QWORD *)(a1 + 136) = *(_QWORD *)(a1 + 1232);
      *(_QWORD *)(a1 + 144) = *(_QWORD *)(a1 + 1240);
      v14 = (_QWORD *)(a1 + 152);
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = 0;
      v15 = *(_QWORD *)(a1 + 1224);
      if ( v15 )
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
      *v14 = *(_QWORD *)(a1 + 1216);
      *(_QWORD *)(a1 + 160) = *(_QWORD *)(a1 + 1224);
      v16 = (_QWORD *)(a1 + 168);
      *(_QWORD *)(a1 + 168) = 0;
      *(_QWORD *)(a1 + 176) = 0;
      v17 = *(_QWORD *)(v2 + 48);
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      *v16 = *(_QWORD *)(v2 + 40);
      *(_QWORD *)(a1 + 176) = *(_QWORD *)(v2 + 48);
      v18 = (_QWORD *)(a1 + 184);
      v19 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 192) = 0;
      if ( *(_QWORD *)(a1 + 88) )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 88) + 8LL));
      *v18 = v19;
      *(_QWORD *)(a1 + 192) = *(_QWORD *)(a1 + 88);
      Windows::Internal::CloudRequestor::CreateCommonHTTPInterface(
        a1 + 200,
        (_DWORD)v18,
        (_DWORD)v16,
        (_DWORD)v14,
        a1 + 136,
        a1 + 120,
        a1 + 112,
        v10,
        a1 + 96,
        v145);
      v21 = (__int64 *)Windows::Internal::CloudNotifications::HomeCloudHandler::PopulateClientInfoString(v2, a1 + 312);
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader + v22) );
      if ( (_DWORD)v22 )
      {
        v23 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v22, v20);
        memcpy_s(
          (char *)v23 + 28,
          2LL * (unsigned int)v22,
          Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader,
          2LL * (unsigned int)v22);
      }
      else
      {
        v23 = 0;
      }
      *(_QWORD *)(a1 + 280) = v23;
      v24 = *v21;
      *v21 = 0;
      *(_QWORD *)(a1 + 288) = v24;
      v25 = (_QWORD *)(a1 + 320);
      *(_QWORD *)(a1 + 320) = 0;
      *(_QWORD *)(a1 + 328) = 0;
      v26 = *(_QWORD *)(a1 + 1192);
      if ( v26 )
        _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
      *v25 = *(_QWORD *)(a1 + 1184);
      *(_QWORD *)(a1 + 328) = *(_QWORD *)(a1 + 1192);
      v28 = (__int64 *)Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(a1 + 336, v25);
      v29 = -1;
      do
        ++v29;
      while ( *((_WORD *)Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader + v29) );
      if ( (_DWORD)v29 )
      {
        v30 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v29, v27);
        memcpy_s(
          (char *)v30 + 28,
          2LL * (unsigned int)v29,
          Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader,
          2LL * (unsigned int)v29);
      }
      else
      {
        v30 = 0;
      }
      *(_QWORD *)(a1 + 296) = v30;
      v31 = *v28;
      *v28 = 0;
      *(_QWORD *)(a1 + 304) = v31;
      *(_QWORD *)(a1 + 944) = a1 + 280;
      *(_QWORD *)(a1 + 952) = a1 + 312;
      v32 = std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(a1 + 216);
      v33 = winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(
              a1 + 344,
              v32);
      v34 = winrt::Windows::Web::Http::HttpMethod::Get();
      v35 = operator new(0x38u);
      *(_QWORD *)(a1 + 976) = v35;
      v36 = std::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>(
              v35,
              v34,
              v33);
      *(_QWORD *)(a1 + 968) = v36;
      *(_QWORD *)(a1 + 360) = v36 + 16;
      *(_QWORD *)(a1 + 368) = v36;
      if ( *(_QWORD *)(a1 + 352) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 352);
      if ( *(_QWORD *)(a1 + 344) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 344);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 240);
      std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(a1 + 224);
      `eh vector destructor iterator'(
        (void *)(a1 + 280),
        0x10u,
        2u,
        std::pair<winrt::hstring const,winrt::hstring>::~pair<winrt::hstring const,winrt::hstring>);
      v37 = a1 + 336;
      if ( *(_QWORD *)(a1 + 336) )
      {
        v38 = *(void **)v37;
        v39 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v37 + 24LL));
        if ( v39 )
        {
          if ( v39 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v38);
        }
        *(_QWORD *)v37 = 0;
      }
      v41 = a1 + 312;
      if ( *(_QWORD *)(a1 + 312) )
      {
        v42 = *(void **)v41;
        v43 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v41 + 24LL));
        if ( v43 )
        {
          if ( v43 < 0 )
            abort();
        }
        else
        {
          v44 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v44, 0, v42);
        }
        *(_QWORD *)v41 = 0;
      }
      v45 = *(_QWORD *)(a1 + 200);
      Src = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, const unsigned __int16 *const *, const WCHAR *))(*(_QWORD *)v45 + 8LL);
      *(_QWORD *)(a1 + 392) = a1 + 376;
      *(_QWORD *)(a1 + 376) = 0;
      *(_QWORD *)(a1 + 384) = 0;
      if ( v36 )
        _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
      v152 = v36 + 16;
      *(_QWORD *)(a1 + 376) = v36 + 16;
      *(_QWORD *)(a1 + 384) = v36;
      v46 = (_QWORD *)(a1 + 408);
      *(_QWORD *)(a1 + 408) = 0;
      *(_QWORD *)(a1 + 416) = 0;
      v47 = *(_QWORD *)(a1 + 1192);
      if ( v47 )
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
      *v46 = *(_QWORD *)(a1 + 1184);
      *(_QWORD *)(a1 + 416) = *(_QWORD *)(a1 + 1192);
      v48 = Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(a1 + 400, v46);
      v49 = Src(
              v45,
              a1 + 424,
              v48,
              a1 + 376,
              &Windows::Internal::CloudNotifications::HomeCloudHandler::c_protocolConfigPath,
              &Name);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v50 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 984);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v50);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 432) = 0;
      *(_QWORD *)(a1 + 440) = v49;
      *(_QWORD *)(a1 + 448) = 0;
      *(_BYTE *)(a1 + 456) = 1;
      v51 = (_WORD *)v146;
      *(_WORD *)v146 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                              a1 + 432,
                              a1) )
        return;
LABEL_88:
      v57 = &Name;
      *(_DWORD *)(a1 + 1008) = 0;
      *(_QWORD *)(a1 + 1016) = 0;
      *(_QWORD *)(a1 + 1024) = 0;
      v58 = *(unsigned int *)(a1 + 452);
      if ( (int)v58 < 0 )
        winrt::throw_hresult(v58, a1 + 1008);
      if ( *(_DWORD *)(a1 + 448) == 2 )
      {
        v59 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1032);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v148, v59);
        throw (winrt::hresult_canceled *)v148;
      }
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
        *(_QWORD *)(a1 + 440),
        a1 + 464);
      if ( *(_QWORD *)(a1 + 432) )
      {
        v60 = *(volatile __int64 **)(a1 + 432);
        while ( _InterlockedExchange64(v60, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 424) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 424);
      if ( *(int *)winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(
                     a1 + 464,
                     a1 + 472) < 0 )
      {
        if ( *(_QWORD *)(a1 + 464) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 360);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 200);
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 80);
        *(_QWORD *)(a1 + 920) = 0;
        winrt::hstring::operator=(a1 - 8, a1 + 920);
        winrt::hstring::~hstring((winrt::hstring *)(a1 + 920));
        std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
        goto LABEL_293;
      }
      v61 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
              a1 + 464,
              a1 + 480);
      v62 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
              v61,
              a1 + 488);
      v63 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
              v62,
              a1 + 496);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v64 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1056);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v149, v64);
        throw (winrt::hresult_canceled *)v149;
      }
      *(_QWORD *)(a1 + 504) = 0;
      *(_QWORD *)(a1 + 512) = v63;
      *(_QWORD *)(a1 + 520) = 0;
      *(_BYTE *)(a1 + 528) = 1;
      *v51 = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                              a1 + 504,
                              a1) )
        return;
LABEL_135:
      *(_DWORD *)(a1 + 1080) = 0;
      *(_QWORD *)(a1 + 1088) = 0;
      *(_QWORD *)(a1 + 1096) = 0;
      v69 = *(unsigned int *)(a1 + 524);
      if ( (int)v69 < 0 )
        winrt::throw_hresult(v69, a1 + 1080);
      if ( *(_DWORD *)(a1 + 520) == 2 )
      {
        v70 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1104);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v150, v70);
        throw (winrt::hresult_canceled *)v150;
      }
      v71 = a1 + 536;
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,winrt::hstring,unsigned __int64>::GetResults(
        *(_QWORD *)(a1 + 512),
        a1 + 536);
      *(_DWORD *)(a1 + 960) = 60;
      if ( *(_QWORD *)(a1 + 504) )
      {
        v72 = *(volatile __int64 **)(a1 + 504);
        while ( _InterlockedExchange64(v72, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 496) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
      if ( *(_QWORD *)(a1 + 488) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
      if ( *(_QWORD *)(a1 + 480) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 480);
      if ( *(_QWORD *)v71 )
        v57 = *(const WCHAR **)(*(_QWORD *)v71 + 16LL);
      Windows::Internal::CloudRequestor::Common::JsonParser::ParseProtocolConfig(a1 + 544, v57);
      v73 = (__int64 *)(a1 + 608);
      *(_OWORD *)(a1 + 608) = 0;
      *(_QWORD *)(a1 + 624) = 0;
      *(_QWORD *)(a1 + 632) = 0;
      std::wstring::_Construct<1,unsigned short const *>(a1 + 608, L"cr");
      v74 = *(_QWORD *)(a1 + 624);
      v158 = v74;
      v159 = *(_QWORD *)(a1 + 632);
      if ( v159 <= 7 )
      {
        v75 = a1 + 608;
      }
      else
      {
        v75 = *v73;
        v157 = *v73;
      }
      Srca = 0xCBF29CE484222325uLL;
      v76 = 0xCBF29CE484222325uLL;
      v77 = 2 * v74;
      for ( i = 0; i < v77; ++i )
        v76 = 0x100000001B3LL * (*(unsigned __int8 *)(v75 + i) ^ (unsigned __int64)v76);
      v79 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                          a1 + 544,
                          a1 + 1128,
                          a1 + 608,
                          v76)
                      + 8);
      if ( !v79 )
      {
        v79 = *(_QWORD *)(a1 + 552);
        v153 = v79;
      }
      std::wstring::_Tidy_deallocate(a1 + 608);
      v153 = *(_QWORD *)(a1 + 552);
      if ( v79 != v153 )
      {
        v90 = (__int64 *)(a1 + 648);
        *(_OWORD *)(a1 + 648) = 0;
        *(_QWORD *)(a1 + 664) = 0;
        *(_QWORD *)(a1 + 672) = 0;
        std::wstring::_Construct<1,unsigned short const *>(a1 + 648, L"homecloud");
        v91 = *(_QWORD *)(a1 + 664);
        v161 = v91;
        v162 = *(_QWORD *)(a1 + 672);
        if ( v162 <= 7 )
        {
          v92 = a1 + 648;
        }
        else
        {
          v92 = *v90;
          v160 = *v90;
        }
        v93 = 2 * v91;
        v94 = 0;
        if ( v93 )
        {
          do
          {
            v95 = 0x100000001B3LL * (Srca ^ *(unsigned __int8 *)(v92 + v94));
            Srca = v95;
            ++v94;
          }
          while ( v94 < v93 );
        }
        else
        {
          v95 = 0xCBF29CE484222325uLL;
        }
        v96 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                            v79 + 48,
                            a1 + 1144,
                            a1 + 648,
                            v95)
                        + 8);
        if ( !v96 )
          v96 = *(_QWORD *)(v79 + 56);
        std::wstring::_Tidy_deallocate(a1 + 648);
        if ( v96 != *(_QWORD *)(v79 + 56) )
        {
          v106 = (const WCHAR **)(a1 + 688);
          std::wstring::wstring(a1 + 688, v96 + 48);
          v156 = *(_QWORD *)(a1 + 712);
          if ( v156 <= 7 )
          {
            v107 = (const WCHAR *)(a1 + 688);
          }
          else
          {
            v107 = *v106;
            v154 = *v106;
          }
          if ( CompareStringOrdinal(L"https://", -1, v107, 8, 1) == 2 )
          {
            v156 = *(_QWORD *)(a1 + 712);
            if ( v156 <= 7 )
            {
              v117 = (const WCHAR *)(a1 + 688);
            }
            else
            {
              v117 = *v106;
              v154 = *v106;
            }
            v155 = *(_QWORD *)(a1 + 704);
            if ( v117[v155 - 1] == 47 )
            {
              v118 = std::wstring::wstring(a1 + 728, a1 + 688);
              v119 = 61;
            }
            else
            {
              v120 = *(_QWORD *)(a1 + 704);
              v155 = v120;
              v121 = 0x7FFFFFFFFFFFFFFELL;
              if ( v120 == 0x7FFFFFFFFFFFFFFELL )
                std::_Xlen_string();
              v156 = *(_QWORD *)(a1 + 712);
              if ( v156 <= 7 )
              {
                Srcb = (const WCHAR *)(a1 + 688);
              }
              else
              {
                Srcb = *v106;
                v154 = *v106;
              }
              v118 = a1 + 760;
              *(_OWORD *)(a1 + 760) = 0;
              *(_QWORD *)(a1 + 776) = 0;
              *(_QWORD *)(a1 + 784) = 0;
              v122 = v120 + 1;
              v139 = v120 + 1;
              v123 = (__int64 *)(a1 + 1160);
              *(_QWORD *)(a1 + 1160) = 7;
              if ( (unsigned __int64)(v120 + 1) <= 7 )
              {
                v125 = (char *)(a1 + 760);
              }
              else
              {
                v124 = v122 | 7;
                if ( v124 <= 0x7FFFFFFFFFFFFFFELL )
                {
                  v121 = v124;
                  if ( v124 < 0xA )
                    v121 = 10;
                }
                *v123 = v121;
                v125 = (char *)std::wstring::_Allocate_for_capacity<0>();
                *(_QWORD *)v118 = v125;
                v123 = (__int64 *)(a1 + 1160);
                v122 = v120 + 1;
              }
              *(_QWORD *)(a1 + 776) = v122;
              *(_QWORD *)(a1 + 784) = *v123;
              v126 = 2 * v120;
              memcpy_0(v125, Srcb, v126);
              *(_WORD *)&v125[v126] = asc_180082844[0];
              *(_WORD *)&v125[2 * v139] = 0;
              v119 = 126;
            }
            *(_DWORD *)(a1 + 960) = v119;
            if ( v106 != (const WCHAR **)v118 )
            {
              std::wstring::_Tidy_deallocate(a1 + 688);
              *(_OWORD *)v106 = *(_OWORD *)v118;
              *(_OWORD *)(a1 + 704) = *(_OWORD *)(v118 + 16);
              *(_QWORD *)(v118 + 16) = 0;
              *(_QWORD *)(v118 + 24) = 7;
              *(_WORD *)v118 = 0;
            }
            v147 = *(_DWORD *)(a1 + 960);
            if ( (v147 & 2) != 0 )
            {
              *(_DWORD *)(a1 + 960) = v147 & 0xFFFFFFFD;
              std::wstring::_Tidy_deallocate(a1 + 760);
            }
            if ( (*(_DWORD *)(a1 + 960) & 1) != 0 )
              std::wstring::_Tidy_deallocate(a1 + 728);
            v127 = std::wstring::wstring(a1 + 792, a1 + 688);
            v128 = *(_QWORD *)(a1 + 1248);
            *(_QWORD *)(a1 + 824) = v128;
            if ( v128 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 8LL))(v128);
            v129 = (_QWORD *)(a1 + 832);
            *(_QWORD *)(a1 + 832) = 0;
            *(_QWORD *)(a1 + 840) = 0;
            v130 = *(_QWORD *)(a1 + 1208);
            if ( v130 )
              _InterlockedIncrement((volatile signed __int32 *)(v130 + 8));
            *v129 = *(_QWORD *)(a1 + 1200);
            *(_QWORD *)(a1 + 840) = *(_QWORD *)(a1 + 1208);
            HomeCloudRegistryCache = Windows::Internal::CloudNotifications::HomeCloudHandler::CreateHomeCloudRegistryCache(
                                       *(_QWORD *)(v146 + 1168),
                                       v129,
                                       a1 + 824,
                                       v127);
            if ( HomeCloudRegistryCache < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x232,
                (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
                (const char *)(unsigned int)HomeCloudRegistryCache,
                bIgnoreCase);
            v156 = *(_QWORD *)(a1 + 712);
            if ( v156 <= 7 )
            {
              v132 = (const WCHAR *)(a1 + 688);
            }
            else
            {
              v132 = *v106;
              v154 = *v106;
            }
            *(_QWORD *)(a1 + 856) = v132;
            v155 = *(_QWORD *)(a1 + 704);
            *(_QWORD *)(a1 + 864) = v155;
            winrt::hstring::hstring(a1 + 848);
            v133 = *(_QWORD *)(a1 + 1216);
            Srcc = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v133 + 32LL);
            *(_QWORD *)(a1 + 880) = a1 + 872;
            v140 = winrt::hstring::hstring(
                     (winrt::hstring *)(a1 + 872),
                     (const struct winrt::hstring *)(*(_QWORD *)(a1 + 1200) + 8LL));
            *(_QWORD *)(a1 + 896) = a1 + 888;
            v134 = winrt::hstring::hstring((winrt::hstring *)(a1 + 888), *(const struct winrt::hstring **)(a1 + 1200));
            v135 = winrt::hstring::hstring((winrt::hstring *)(a1 + 904), (const struct winrt::hstring *)(a1 + 848));
            v136 = Srcc(v133, v135, v134, v140);
            wil::details::in1diag3::Throw_IfFailedMsg(
              retaddr,
              (void *)0x239,
              (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
              (const char *)v136,
              (int)"Unable to update service configuration",
              v138);
            winrt::hstring::operator=(a1 - 8, a1 + 848);
            winrt::hstring::~hstring((winrt::hstring *)(a1 + 848));
            std::wstring::_Tidy_deallocate(a1 + 688);
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 568);
            __1__list_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std__V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__std__QEAA_XZ(a1 + 552);
            winrt::hstring::~hstring((winrt::hstring *)(a1 + 536));
            if ( *(_QWORD *)(a1 + 464) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
            std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 360);
            std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 200);
            std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 80);
            std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
          }
          else
          {
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x22D,
              (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
              (const char *)0x8007139FLL,
              (int)"CR Home Cloud Does Not Start With HTTPS:// in %ls",
              L"cr");
            *(_QWORD *)(a1 + 720) = 0;
            winrt::hstring::operator=(a1 - 8, a1 + 720);
            if ( *(_QWORD *)(a1 + 720) )
            {
              v108 = *(volatile signed __int32 **)(a1 + 720);
              v109 = _InterlockedDecrement(v108 + 6);
              if ( v109 )
              {
                if ( v109 < 0 )
                  abort();
              }
              else
              {
                v110 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v110, 0, (LPVOID)v108);
              }
            }
            std::wstring::_Tidy_deallocate(a1 + 688);
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 568);
            __1__list_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std__V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__std__QEAA_XZ(a1 + 552);
            if ( *(_QWORD *)v71 )
            {
              v111 = *(void **)v71;
              v112 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v71 + 24LL));
              if ( v112 )
              {
                if ( v112 < 0 )
                  abort();
              }
              else
              {
                v113 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v113, 0, v111);
              }
              *(_QWORD *)v71 = 0;
            }
            if ( *(_QWORD *)(a1 + 464) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
            v114 = *(volatile signed __int32 **)(a1 + 968);
            if ( v114 )
            {
              if ( _InterlockedExchangeAdd(v114 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v114)(v114);
                if ( _InterlockedExchangeAdd(v114 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v114 + 8LL))(v114);
              }
            }
            if ( *(_QWORD *)(a1 + 208) )
            {
              v115 = *(volatile signed __int32 **)(a1 + 208);
              if ( _InterlockedExchangeAdd(v115 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v115)(v115);
                if ( _InterlockedExchangeAdd(v115 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v115 + 8LL))(v115);
              }
            }
            if ( *(_QWORD *)(a1 + 88) )
            {
              v116 = *(volatile signed __int32 **)(a1 + 88);
              if ( _InterlockedExchangeAdd(v116 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v116)(v116);
                if ( _InterlockedExchangeAdd(v116 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v116 + 8LL))(v116);
              }
            }
            if ( *(_QWORD *)(a1 + 24) )
            {
              v89 = *(volatile signed __int32 **)(a1 + 24);
              if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
                if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
                  goto LABEL_257;
              }
            }
          }
          goto LABEL_293;
        }
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x225,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
          (const char *)0x8007139FLL,
          (int)"CR Home Cloud Not Found for %ls",
          L"cr");
        *(_QWORD *)(a1 + 680) = 0;
        winrt::hstring::operator=(a1 - 8, a1 + 680);
        if ( *(_QWORD *)(a1 + 680) )
        {
          v97 = *(volatile signed __int32 **)(a1 + 680);
          v98 = _InterlockedDecrement(v97 + 6);
          if ( v98 )
          {
            if ( v98 < 0 )
              goto LABEL_200;
          }
          else
          {
            v99 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v99, 0, (LPVOID)v97);
          }
        }
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 568);
        __1__list_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std__V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__std__QEAA_XZ(a1 + 552);
        if ( *(_QWORD *)v71 )
        {
          v100 = *(void **)v71;
          v101 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v71 + 24LL));
          if ( v101 )
          {
            if ( v101 < 0 )
              goto LABEL_205;
          }
          else
          {
            v102 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v102, 0, v100);
          }
          *(_QWORD *)v71 = 0;
        }
        if ( *(_QWORD *)(a1 + 464) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
        v103 = *(volatile signed __int32 **)(a1 + 968);
        if ( v103 )
        {
          if ( _InterlockedExchangeAdd(v103 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
            if ( _InterlockedExchangeAdd(v103 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
          }
        }
        if ( *(_QWORD *)(a1 + 208) )
        {
          v104 = *(volatile signed __int32 **)(a1 + 208);
          if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
            if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
          }
        }
        if ( *(_QWORD *)(a1 + 88) )
        {
          v105 = *(volatile signed __int32 **)(a1 + 88);
          if ( _InterlockedExchangeAdd(v105 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v105)(v105);
            if ( _InterlockedExchangeAdd(v105 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v105 + 8LL))(v105);
          }
        }
        if ( *(_QWORD *)(a1 + 24) )
        {
          v89 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
            if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_257;
          }
        }
        goto LABEL_293;
      }
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
        (const char *)0x80070490LL,
        (int)"Protocol Config Missing Config for %ls",
        L"cr");
      *(_QWORD *)(a1 + 640) = 0;
      winrt::hstring::operator=(a1 - 8, a1 + 640);
      if ( !*(_QWORD *)(a1 + 640) )
        goto LABEL_163;
      v80 = *(volatile signed __int32 **)(a1 + 640);
      v81 = _InterlockedDecrement(v80 + 6);
      if ( !v81 )
      {
        v82 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v82, 0, (LPVOID)v80);
        goto LABEL_163;
      }
      if ( v81 < 0 )
LABEL_200:
        abort();
LABEL_163:
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 568);
      __1__list_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std__V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__std__QEAA_XZ(a1 + 552);
      if ( !*(_QWORD *)v71 )
        goto LABEL_168;
      v83 = *(void **)v71;
      v84 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v71 + 24LL));
      if ( v84 )
      {
        if ( v84 >= 0 )
          goto LABEL_167;
LABEL_205:
        abort();
      }
      v85 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v85, 0, v83);
LABEL_167:
      *(_QWORD *)v71 = 0;
LABEL_168:
      if ( *(_QWORD *)(a1 + 464) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
      v86 = *(volatile signed __int32 **)(a1 + 968);
      if ( v86 )
      {
        if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
          if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
        }
      }
      if ( *(_QWORD *)(a1 + 208) )
      {
        v87 = *(volatile signed __int32 **)(a1 + 208);
        if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
          if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
        }
      }
      if ( *(_QWORD *)(a1 + 88) )
      {
        v88 = *(volatile signed __int32 **)(a1 + 88);
        if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v89 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
          if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
LABEL_257:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
        }
      }
LABEL_293:
      *(_QWORD *)(a1 + 928) = a1 - 112;
      *(_WORD *)v146 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::final_suspend_awaiter::await_suspend() )
      {
LABEL_294:
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::~promise_type(a1 - 112);
        Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudFromDefaultCloudAsync_::_14_::_parameters_::__parameters_(v146 + 1168);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x560u);
      }
      return;
    case 6:
      v51 = (_WORD *)(a1 + 8);
      goto LABEL_88;
    case 7:
      if ( *(_QWORD *)(a1 + 432) )
      {
        v52 = *(volatile __int64 **)(a1 + 432);
        while ( _InterlockedExchange64(v52, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 424) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 424);
      v53 = *(volatile signed __int32 **)(a1 + 968);
      if ( v53 )
      {
        if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
          if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
        }
      }
      if ( *(_QWORD *)(a1 + 208) )
      {
        v54 = *(volatile signed __int32 **)(a1 + 208);
        if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
      if ( *(_QWORD *)(a1 + 88) )
      {
        v55 = *(volatile signed __int32 **)(a1 + 88);
        if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
          if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v56 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_86;
        }
      }
      goto LABEL_294;
    case 8:
      v57 = &Name;
      goto LABEL_135;
    case 9:
      if ( *(_QWORD *)(a1 + 504) )
      {
        v65 = *(volatile __int64 **)(a1 + 504);
        while ( _InterlockedExchange64(v65, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 496) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
      if ( *(_QWORD *)(a1 + 488) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
      if ( *(_QWORD *)(a1 + 480) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 480);
      if ( *(_QWORD *)(a1 + 464) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
      v66 = *(volatile signed __int32 **)(a1 + 968);
      if ( v66 )
      {
        if ( _InterlockedExchangeAdd(v66 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
          if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
        }
      }
      if ( *(_QWORD *)(a1 + 208) )
      {
        v67 = *(volatile signed __int32 **)(a1 + 208);
        if ( _InterlockedExchangeAdd(v67 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
          if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
        }
      }
      if ( *(_QWORD *)(a1 + 88) )
      {
        v68 = *(volatile signed __int32 **)(a1 + 88);
        if ( _InterlockedExchangeAdd(v68 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
          if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v56 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
LABEL_86:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      goto LABEL_294;
  }
}

```

## disassembly

```asm
0x180064ae0  mov     r11, rsp
0x180064ae3  mov     [r11+10h], rbx
0x180064ae7  mov     [r11+18h], rsi
0x180064aeb  mov     [r11+8], rcx
0x180064aef  push    rdi
0x180064af0  push    r12
0x180064af2  push    r13
0x180064af4  push    r14
0x180064af6  push    r15
0x180064af8  sub     rsp, 390h
0x180064aff  mov     rax, cs:__security_cookie
0x180064b06  xor     rax, rsp
0x180064b09  mov     [rsp+3B8h+var_38], rax
0x180064b11  mov     rdi, rcx
0x180064b14  mov     [rsp+3B8h+var_318], rcx
0x180064b1c  lea     rdx, [rdi+8]
0x180064b20  mov     [rsp+3B8h+var_350], rdx
0x180064b25  movzx   eax, word ptr [rdx]
0x180064b28  mov     [rsp+3B8h+var_300], ax
0x180064b30  mov     r15d, 1
0x180064b36  add     ax, r15w
0x180064b3a  lea     ecx, [r15+9]
0x180064b3e  cmp     ax, cx
0x180064b41  ja      loc_1800666A6; jumptable 0000000180064B65 cases 1,5,6
0x180064b47  mov     [rsp+3B8h+var_2F8], rdx
0x180064b4f  movsx   rax, ax
0x180064b53  lea     r8, cs:180000000h
0x180064b5a  mov     ecx, ds:(jpt_180064B65 - 180000000h)[r8+rax*4]; switch 11 cases
0x180064b62  add     rcx, r8
0x180064b65  jmp     rcx; switch jump
0x180064b67  xor     esi, esi; jumptable 0000000180064B65 case 4
0x180064b69  jmp     loc_180066676
0x180064b6e  xor     esi, esi; jumptable 0000000180064B65 case 3
0x180064b70  mov     [rdi+3C0h], esi
0x180064b76  mov     r14, [rdx+490h]
0x180064b7d  mov     [rdi+10h], rsi
0x180064b81  mov     [rdi+18h], rsi
0x180064b85  mov     rdx, [r14+10h]
0x180064b89  test    rdx, rdx
0x180064b8c  jz      loc_1800651EE
0x180064b92  mov     eax, [rdx+8]
0x180064b95  jmp     short loc_180064BA1
0x180064b97  lea     ecx, [rax+1]
0x180064b9a  lock cmpxchg [rdx+8], ecx
0x180064b9f  jz      short loc_180064BAA
0x180064ba1  test    eax, eax
0x180064ba3  jnz     short loc_180064B97
0x180064ba5  jmp     loc_1800651EE
0x180064baa  mov     rax, [r14+8]
0x180064bae  mov     [rdi+10h], rax
0x180064bb2  mov     rax, [r14+10h]
0x180064bb6  mov     [rdi+18h], rax
0x180064bba  mov     [rdi-40h], r15b
0x180064bbe  lea     rbx, [rdi+20h]
0x180064bc2  mov     [rbx], rsi
0x180064bc5  mov     [rdi+28h], rsi
0x180064bc9  mov     rax, [r14+40h]
0x180064bcd  test    rax, rax
0x180064bd0  jz      short loc_180064BD7
0x180064bd2  lock add [rax+8], r15d
0x180064bd7  mov     rax, [r14+38h]
0x180064bdb  mov     [rbx], rax
0x180064bde  mov     rax, [r14+40h]
0x180064be2  mov     [rdi+28h], rax
0x180064be6  lea     r15, [rdi+30h]
0x180064bea  mov     [r15], rsi
0x180064bed  mov     [rdi+38h], rsi
0x180064bf1  mov     rax, [r14+30h]
0x180064bf5  test    rax, rax
0x180064bf8  jz      short loc_180064BFE
0x180064bfa  lock inc dword ptr [rax+8]
0x180064bfe  mov     rax, [r14+28h]
0x180064c02  mov     [r15], rax
0x180064c05  mov     rax, [r14+30h]
0x180064c09  mov     [rdi+38h], rax
0x180064c0d  lea     r12, [rdi+40h]
0x180064c11  mov     [r12], rsi
0x180064c15  mov     [rdi+48h], rsi
0x180064c19  mov     rax, [r15+498h]
0x180064c20  test    rax, rax
0x180064c23  jz      short loc_180064C29
0x180064c25  lock inc dword ptr [rax+8]
0x180064c29  mov     rax, [r15+490h]
0x180064c30  mov     [r12], rax
0x180064c34  mov     rax, [r15+498h]
0x180064c3b  mov     [rdi+48h], rax
0x180064c3f  lea     rcx, [rdi+50h]
0x180064c43  mov     r9, rbx
0x180064c46  mov     r8, r15
0x180064c49  mov     rdx, r12
0x180064c4c  call    ?CreateRequestResponseHandler@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VIRequestResponseHandler@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VITokenBroker@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@5@@Z; Windows::Internal::CloudRequestor::CreateRequestResponseHandler(std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::ITokenBroker>,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>)
0x180064c51  nop
0x180064c52  mov     eax, [r14+18h]
0x180064c56  mov     dword ptr [rsp+3B8h+var_358], eax
0x180064c5a  lea     r13, [rdi+60h]
0x180064c5e  mov     [r13+0], rsi
0x180064c62  mov     [rdi+68h], rsi
0x180064c66  mov     rax, [rbx+498h]
0x180064c6d  test    rax, rax
0x180064c70  jz      short loc_180064C76
0x180064c72  lock inc dword ptr [rax+8]
0x180064c76  mov     rax, [rbx+490h]
0x180064c7d  mov     [r13+0], rax
0x180064c81  mov     rax, [rbx+498h]
0x180064c88  mov     [rdi+68h], rax
0x180064c8c  mov     rbx, [r14+20h]
0x180064c90  mov     rcx, [rdi+4E0h]
0x180064c97  mov     [rdi+70h], rcx
0x180064c9b  test    rcx, rcx
0x180064c9e  jz      short loc_180064CAC
0x180064ca0  mov     rax, [rcx]
0x180064ca3  mov     rax, [rax+8]
0x180064ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cac  lea     rcx, [rdi+78h]
0x180064cb0  mov     [rcx], rsi
0x180064cb3  mov     [rdi+80h], rsi
0x180064cba  mov     rax, [r14+40h]
0x180064cbe  test    rax, rax
0x180064cc1  jz      short loc_180064CC7
0x180064cc3  lock inc dword ptr [rax+8]
0x180064cc7  mov     rax, [r14+38h]
0x180064ccb  mov     [rcx], rax
0x180064cce  mov     rax, [r14+40h]
0x180064cd2  mov     [rdi+80h], rax
0x180064cd9  lea     r11, [rdi+88h]
0x180064ce0  mov     [r11], rsi
0x180064ce3  mov     [rdi+90h], rsi
0x180064cea  mov     rax, [r12+498h]
0x180064cf2  test    rax, rax
0x180064cf5  jz      short loc_180064CFB
0x180064cf7  lock inc dword ptr [rax+8]
0x180064cfb  mov     rax, [r12+490h]
0x180064d03  mov     [r11], rax
0x180064d06  mov     rax, [r12+498h]
0x180064d0e  mov     [rdi+90h], rax
0x180064d15  lea     r9, [rdi+98h]
0x180064d1c  mov     [r9], rsi
0x180064d1f  mov     [rdi+0A0h], rsi
0x180064d26  mov     rax, [r15+498h]
0x180064d2d  test    rax, rax
0x180064d30  jz      short loc_180064D36
0x180064d32  lock inc dword ptr [rax+8]
0x180064d36  mov     rax, [r15+490h]
0x180064d3d  mov     [r9], rax
0x180064d40  mov     rax, [r15+498h]
0x180064d47  mov     [rdi+0A0h], rax
0x180064d4e  lea     r8, [rdi+0A8h]
0x180064d55  mov     [r8], rsi
0x180064d58  mov     [rdi+0B0h], rsi
0x180064d5f  mov     rax, [r14+30h]
0x180064d63  test    rax, rax
0x180064d66  jz      short loc_180064D6C
0x180064d68  lock inc dword ptr [rax+8]
0x180064d6c  mov     rax, [r14+28h]
0x180064d70  mov     [r8], rax
0x180064d73  mov     rax, [r14+30h]
0x180064d77  mov     [rdi+0B0h], rax
0x180064d7e  lea     rdx, [rdi+0B8h]
0x180064d85  mov     r10, [rdi+50h]
0x180064d89  mov     [rsp+3B8h+var_348], r10
0x180064d8e  mov     [rdx], rsi
0x180064d91  mov     [rdi+0C0h], rsi
0x180064d98  mov     rax, [rdi+58h]
0x180064d9c  mov     [rsp+3B8h+var_340], rax
0x180064da1  test    rax, rax
0x180064da4  jz      short loc_180064DB3
0x180064da6  mov     rax, [rdi+58h]
0x180064daa  mov     [rsp+3B8h+var_340], rax
0x180064daf  lock inc dword ptr [rax+8]
0x180064db3  mov     [rdx], r10
0x180064db6  mov     rax, [rdi+58h]
0x180064dba  mov     [rsp+3B8h+var_340], rax
0x180064dbf  mov     [rdi+0C0h], rax
0x180064dc6  mov     eax, dword ptr [rsp+3B8h+var_358]
0x180064dca  mov     [rsp+3B8h+var_370], eax
0x180064dce  mov     [rsp+3B8h+var_378], r13
0x180064dd3  mov     [rsp+3B8h+var_380], rbx
0x180064dd8  lea     rax, [rdi+70h]
0x180064ddc  mov     [rsp+3B8h+var_388], rax
0x180064de1  mov     [rsp+3B8h+var_390], rcx
0x180064de6  mov     qword ptr [rsp+3B8h+bIgnoreCase], r11
0x180064deb  lea     rcx, [rdi+0C8h]
0x180064df2  call    ?CreateCommonHTTPInterface@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VICommonHttpInterface@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIRequestResponseHandler@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VITokenBroker@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@5@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@5@UIWebAccount@Credentials@Security@3winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@5@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@5@W4TokenRefreshOption@123@@Z; Windows::Internal::CloudRequestor::CreateCommonHTTPInterface(std::shared_ptr<Windows::Internal::CloudRequestor::IRequestResponseHandler>,std::shared_ptr<Windows::Internal::CloudRequestor::ITokenBroker>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>,winrt::Windows::Security::Credentials::IWebAccount,std::chrono::duration<__int64,std::ratio<1,10000000>>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,Windows::Internal::CloudRequestor::TokenRefreshOption)
0x180064df7  nop
0x180064df8  lea     rdx, [rdi+138h]
0x180064dff  mov     rcx, r14
0x180064e02  call    ?PopulateClientInfoString@HomeCloudHandler@CloudNotifications@Internal@Windows@@AEAA?AUhstring@winrt@@XZ; Windows::Internal::CloudNotifications::HomeCloudHandler::PopulateClientInfoString(void)
0x180064e07  mov     r13, rax
0x180064e0a  mov     r12, cs:?c_afsClientInfoHeader@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsClientInfoHeader
0x180064e11  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180064e15  mov     r14, rbx
0x180064e18  inc     r14
0x180064e1b  cmp     [r12+r14*2], si
0x180064e20  jnz     short loc_180064E18
0x180064e22  test    r14d, r14d
0x180064e25  jnz     short loc_180064E2C
0x180064e27  mov     r15, rsi
0x180064e2a  jmp     short loc_180064E4C
0x180064e2c  mov     ecx, r14d; this
0x180064e2f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180064e34  mov     r15, rax
0x180064e37  mov     edx, r14d
0x180064e3a  add     rdx, rdx; DestinationSize
0x180064e3d  lea     rcx, [rax+1Ch]; Destination
0x180064e41  mov     r9, rdx; SourceSize
0x180064e44  mov     r8, r12; Source
0x180064e47  call    memcpy_s
0x180064e4c  mov     [rdi+118h], r15
0x180064e53  mov     rax, [r13+0]
0x180064e57  mov     [r13+0], rsi
0x180064e5b  mov     [rdi+120h], rax
0x180064e62  lea     rdx, [rdi+140h]
0x180064e69  mov     [rdx], rsi
0x180064e6c  mov     [rdi+148h], rsi
0x180064e73  mov     rax, [rdi+4A8h]
0x180064e7a  test    rax, rax
0x180064e7d  jz      short loc_180064E83
0x180064e7f  lock inc dword ptr [rax+8]
0x180064e83  mov     rax, [rdi+4A0h]
0x180064e8a  mov     [rdx], rax
0x180064e8d  mov     rax, [rdi+4A8h]
0x180064e94  mov     [rdi+148h], rax
0x180064e9b  lea     rcx, [rdi+150h]
0x180064ea2  call    ?ToString@CorrelationVectorUtils@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@Z; Windows::Internal::CloudRequestor::CorrelationVectorUtils::ToString(std::shared_ptr<TraceLoggingCorrelationVector>)
0x180064ea7  mov     r13, rax
0x180064eaa  mov     r12, cs:?c_afsCvHeader@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_afsCvHeader
0x180064eb1  mov     r14, rbx
0x180064eb4  inc     r14
0x180064eb7  cmp     [r12+r14*2], si
0x180064ebc  jnz     short loc_180064EB4
0x180064ebe  test    r14d, r14d
0x180064ec1  jnz     short loc_180064EC8
0x180064ec3  mov     r15, rsi
0x180064ec6  jmp     short loc_180064EE8
0x180064ec8  mov     ecx, r14d; this
0x180064ecb  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180064ed0  mov     r15, rax
0x180064ed3  mov     edx, r14d
0x180064ed6  add     rdx, rdx; DestinationSize
0x180064ed9  lea     rcx, [rax+1Ch]; Destination
0x180064edd  mov     r9, rdx; SourceSize
0x180064ee0  mov     r8, r12; Source
0x180064ee3  call    memcpy_s
0x180064ee8  mov     [rdi+128h], r15
0x180064eef  mov     rax, [r13+0]
0x180064ef3  mov     [r13+0], rsi
0x180064ef7  mov     [rdi+130h], rax
0x180064efe  lea     rdx, [rdi+3B0h]
0x180064f05  lea     rax, [rdi+118h]
0x180064f0c  mov     [rdx], rax
0x180064f0f  lea     rax, [rdi+138h]
0x180064f16  mov     [rdi+3B8h], rax
0x180064f1d  lea     rcx, [rdi+0D8h]
0x180064f24  call    ??0?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@QEAA@V?$initializer_list@U?$pair@$$CBUhstring@winrt@@U12@@std@@@1@@Z; std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(std::initializer_list<std::pair<winrt::hstring const,winrt::hstring>>)
0x180064f29  nop
0x180064f2a  lea     r12, [rdi+158h]
0x180064f31  mov     rdx, rax
0x180064f34  mov     rcx, r12
0x180064f37  call    ??$single_threaded_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@winrt@@YA?AU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@Windows@0@$$QEAV?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@@Z; winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(std::unordered_map<winrt::hstring,winrt::hstring> &&)
0x180064f3c  mov     r13, rax
0x180064f3f  lea     r15, [rdi+160h]
0x180064f46  mov     rcx, r15
0x180064f49  call    ?Get@HttpMethod@Http@Web@Windows@winrt@@SA@XZ; winrt::Windows::Web::Http::HttpMethod::Get(void)
0x180064f4e  mov     r14, rax
0x180064f51  mov     ecx, 38h ; '8'; Size
0x180064f56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064f5b  mov     [rdi+3D0h], rax
0x180064f62  mov     [rsp+3B8h+var_280], rax
0x180064f6a  lea     rcx, Name
0x180064f71  mov     [rsp+3B8h+var_390], rcx
0x180064f76  lea     rdx, ?c_protocolConfigPath@HomeCloudHandler@CloudNotifications@Internal@Windows@@0QEBGEB; ushort const * const Windows::Internal::CloudNotifications::HomeCloudHandler::c_protocolConfigPath
0x180064f7d  mov     qword ptr [rsp+3B8h+bIgnoreCase], rdx
0x180064f82  mov     r9, rcx
0x180064f85  mov     r8, r13
0x180064f88  mov     rdx, r14
0x180064f8b  mov     rcx, rax
0x180064f8e  call    ??$?0UHttpMethod@Http@Web@Windows@winrt@@U?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@34@AEAY00$$CBGAEBQEBGAEAY00$$CBG@?$_Ref_count_obj2@URequestItem@CloudRequestor@Internal@Windows@@@std@@QEAA@$$QEAUHttpMethod@Http@Web@Windows@winrt@@$$QEAU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@56@AEAY00$$CBGAEBQEBG2@Z; std::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>(winrt::Windows::Web::Http::HttpMethod &&,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::hstring> &&,ushort const (&)[1],ushort const * const &,ushort const (&)[1])
0x180064f93  mov     r14, rax
0x180064f96  mov     [rdi+3C8h], rax
0x180064f9d  lea     r13, [rax+10h]
0x180064fa1  mov     [rdi+168h], r13
0x180064fa8  mov     [rdi+170h], rax
0x180064faf  mov     rdx, [r15]
0x180064fb2  mov     [rsp+3B8h+var_278], rdx
0x180064fba  test    rdx, rdx
0x180064fbd  jz      short loc_180064FC8
0x180064fbf  mov     rcx, r15
0x180064fc2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180064fc7  nop
0x180064fc8  mov     rax, [r12]
0x180064fcc  mov     [rsp+3B8h+var_270], rax
0x180064fd4  test    rax, rax
0x180064fd7  jz      short loc_180064FE2
0x180064fd9  mov     rcx, r12
0x180064fdc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180064fe1  nop
0x180064fe2  lea     rcx, [rdi+0F0h]
0x180064fe9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(void)
0x180064fee  lea     rcx, [rdi+0E0h]
0x180064ff5  call    ??1?$list@U?$pair@$$CBUhstring@winrt@@U12@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(void)
  ... truncated ...
```
