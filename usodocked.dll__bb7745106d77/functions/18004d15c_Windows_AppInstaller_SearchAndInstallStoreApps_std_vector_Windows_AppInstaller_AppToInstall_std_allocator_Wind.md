# Windows::AppInstaller::SearchAndInstallStoreApps(std::vector<Windows::AppInstaller::AppToInstall,std::allocator<Windows::AppInstaller::AppToInstall>>,ushort *,std::chrono::duration<__int64,std::ratio<1,1>>,std::function<void (Windows::AppInstaller::AppInstallState)>)

- ea: `0x18004d15c`
- end: `0x18004e278`
- name: `?SearchAndInstallStoreApps@AppInstaller@Windows@@YA?AV?$vector@UAppInstallState@AppInstaller@Windows@@V?$allocator@UAppInstallState@AppInstaller@Windows@@@std@@@std@@V?$vector@UAppToInstall@AppInstaller@Windows@@V?$allocator@UAppToInstall@AppInstaller@Windows@@@std@@@4@PEAGV?$duration@_JU?$ratio@$00$00@std@@@chrono@4@V?$function@$$A6AXUAppInstallState@AppInstaller@Windows@@@Z@4@@Z`
- size: `4380`
- prototype: `_QWORD *(_QWORD *, const void ***, __int64, ...)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d0b8`

## callees

- `0x180006a08`
- `0x180007660`
- `0x180007dfc`
- `0x18000856c`
- `0x180011515`
- `0x180011575`
- `0x1800157f4`
- `0x180016128`
- `0x180018f08`
- `0x180019e48`
- `0x18001a5a4`
- `0x18001ba70`
- `0x18001ee04`
- `0x18001fab0`
- `0x1800209fc`
- `0x180023a18`
- `0x18002765c`
- `0x180028330`
- `0x180028888`
- `0x180029eac`
- `0x18002bce4`
- `0x18002bd54`
- `0x18002c8b4`
- `0x180031be0`
- `0x180031fcc`
- `0x180032548`
- `0x180033434`
- `0x180035528`
- `0x180036214`
- `0x18003b360`
- `0x18003b528`
- `0x18003bc28`
- `0x18003bf74`
- `0x1800494b8`
- `0x1800497d0`
- `0x1800499e4`
- `0x18004a018`
- `0x18004a2cc`
- `0x18004aa60`
- `0x18004aac4`
- `0x18004c7d8`
- `0x18004d15c`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Thrd_join` at `0x18004e06e`
- `msvcp_win!_Thrd_join` at `0x18004e06e`
- `msvcp_win!_Thrd_id` at `0x18004e03a`
- `msvcp_win!_Thrd_id` at `0x18004e03a`
- `msvcp_win!_Cnd_broadcast` at `0x18004e023`
- `msvcp_win!_Cnd_broadcast` at `0x18004e023`
- `msvcp_win!_Mtx_unlock` at `0x18004da31`
- `msvcp_win!_Mtx_unlock` at `0x18004e016`
- `msvcp_win!_Mtx_unlock` at `0x18004da31`
- `msvcp_win!_Mtx_unlock` at `0x18004e016`
- `msvcp_win!_Mtx_lock` at `0x18004d9d4`
- `msvcp_win!_Mtx_lock` at `0x18004d9d4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d6d6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d9f6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e033`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e07d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e1c7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d6d6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004d9f6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e033`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e07d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004e1c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004de25`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004de25`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d8db`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004dc47`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004de02`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d8db`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004dc47`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004de02`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004d64d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004e110`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004d64d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004e110`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004d62a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004d62a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004d278`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004d278`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004e12a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004e12a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004d239`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004d239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e147`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e161`
- `ntdll!RtlPublishWnfStateData` at `0x18004dea4`
- `ntdll!RtlPublishWnfStateData` at `0x18004dea4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d1f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d1f3`

## string_xrefs

- `0x18004d22e`: `Global\SearchAndInstallMutex`
- `0x18004e1d9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\appinstaller\appinstaller.cpp`
- `0x18004e1ee`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\appinstaller\appinstaller.cpp`
- `0x18004e20d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\appinstaller\appinstaller.cpp`
- `0x18004e225`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\appinstaller\appinstaller.cpp`
- `0x18004e23d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\appinstaller\appinstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
_QWORD *Windows::AppInstaller::SearchAndInstallStoreApps(_QWORD *a1, const void ***a2, __int64 a3, ...)
{
  _QWORD *v4; // r12
  const char *v5; // r9
  void *v6; // rdi
  wil::details *v7; // rcx
  HANDLE v8; // rbx
  int LastErrorFailHr; // eax
  DWORD v10; // eax
  const char *v11; // r9
  void *v12; // rcx
  volatile signed __int32 *v13; // r14
  _QWORD *v14; // rax
  int v15; // r15d
  volatile signed __int32 *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _BYTE *); // r8
  _BYTE *v20; // rax
  _BYTE *v21; // rdx
  _BYTE *v22; // r10
  _BYTE *v23; // r11
  _BYTE *v24; // r9
  _BYTE *v25; // r8
  _BYTE *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  _BYTE *v29; // rdx
  _BYTE *v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // rdx
  __int64 v35; // rcx
  const void **v36; // rsi
  const void **v37; // r13
  const void *v38; // r12
  __int64 v39; // r14
  volatile signed __int32 *v40; // rbx
  int v41; // eax
  HANDLE ProcessHeap; // rax
  __int64 *v43; // rax
  __int64 *v44; // rcx
  __int64 *v45; // rax
  int v46; // r15d
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v49; // r14
  _QWORD *v50; // rsi
  __int64 v51; // rcx
  __int64 v52; // rdx
  _QWORD *v53; // rsi
  _QWORD *v54; // r14
  unsigned int v55; // eax
  __int64 v56; // rax
  const wchar_t *v57; // rdx
  __int64 v58; // r8
  __int64 CurrentStatus; // rax
  int v60; // ebx
  __int64 v61; // rax
  int v62; // ecx
  __int64 v63; // rdx
  void *v64; // rbx
  int v65; // eax
  HANDLE v66; // rax
  _QWORD *v67; // rsi
  _QWORD *v68; // r14
  __int64 v69; // rax
  const wchar_t *v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rax
  int v73; // ebx
  __int64 v74; // rax
  int v75; // ecx
  __int64 v76; // rdx
  void *v77; // rbx
  int v78; // eax
  HANDLE v79; // rax
  __int64 *v80; // r12
  _QWORD *v81; // r13
  __int64 *v82; // rsi
  const void ***v83; // r13
  __int64 *v84; // rbx
  const void **i; // r14
  __int64 *v86; // rdx
  __int64 *v87; // rcx
  const unsigned __int16 *v88; // r8
  int v89; // r11d
  _QWORD *v90; // rbx
  _QWORD *v91; // rbx
  _QWORD *v92; // rsi
  LPVOID v93; // rbx
  int v94; // eax
  int v95; // eax
  unsigned int v96; // r8d
  const char *v97; // r9
  BOOL v98; // eax
  unsigned int v99; // r8d
  const char *v100; // r9
  wil::details::in1diag3 *v101; // rcx
  __int64 v102; // rbx
  __int64 *v103; // rcx
  __int64 v104; // rdx
  int v106; // [rsp+20h] [rbp-E0h]
  __int64 v107; // [rsp+28h] [rbp-D8h]
  __int64 v108; // [rsp+28h] [rbp-D8h]
  __int64 v109; // [rsp+30h] [rbp-D0h]
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v111; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v112; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v113; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v114[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v115; // [rsp+80h] [rbp-80h] BYREF
  __int64 v116; // [rsp+90h] [rbp-70h]
  __int64 v117; // [rsp+98h] [rbp-68h]
  char v118; // [rsp+A0h] [rbp-60h]
  __int64 v119; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v120; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v121; // [rsp+B8h] [rbp-48h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v123; // [rsp+C8h] [rbp-38h]
  HANDLE hMutex; // [rsp+D0h] [rbp-30h]
  const void ***v125; // [rsp+D8h] [rbp-28h]
  __int64 v126; // [rsp+E0h] [rbp-20h]
  __int128 v127; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v128; // [rsp+F8h] [rbp-8h]
  __int128 v129; // [rsp+100h] [rbp+0h] BYREF
  __int64 v130; // [rsp+110h] [rbp+10h]
  _OWORD v131[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v132; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v133; // [rsp+148h] [rbp+48h]
  __int64 v134; // [rsp+158h] [rbp+58h] BYREF
  __int64 v135; // [rsp+160h] [rbp+60h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+170h] [rbp+70h] BYREF
  _QWORD *v137; // [rsp+188h] [rbp+88h] BYREF
  _QWORD *v138; // [rsp+190h] [rbp+90h]
  __int64 v139; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v140; // [rsp+1A8h] [rbp+A8h]
  _QWORD *v141; // [rsp+1B8h] [rbp+B8h]
  const void ***v142; // [rsp+1C0h] [rbp+C0h]
  void *v143; // [rsp+1C8h] [rbp+C8h]
  __int64 v144; // [rsp+1D0h] [rbp+D0h]
  _BYTE v145[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v146; // [rsp+1F8h] [rbp+F8h]
  int v147; // [rsp+200h] [rbp+100h]
  int v148; // [rsp+204h] [rbp+104h]
  _BYTE v149[56]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE *v150; // [rsp+248h] [rbp+148h]
  _BYTE v151[56]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE *v152; // [rsp+288h] [rbp+188h]
  unsigned __int16 v153[256]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]
  __int64 v155; // [rsp+4F8h] [rbp+3F8h] BYREF
  va_list va; // [rsp+4F8h] [rbp+3F8h]
  __int64 v157; // [rsp+500h] [rbp+400h]
  va_list va1; // [rsp+508h] [rbp+408h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v155 = va_arg(va1, _QWORD);
  v157 = va_arg(va1, _QWORD);
  *(_QWORD *)v145 = a3;
  v125 = a2;
  v4 = a1;
  v121 = a1;
  v141 = a1;
  v142 = a2;
  v126 = v157;
  v144 = v157;
  memset(&MutexAttributes, 0, sizeof(MutexAttributes));
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\appinstaller\\appinstaller.cpp",
      v5);
  MutexAttributes.nLength = 24;
  MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
  MutexAttributes.bInheritHandle = 0;
  v6 = 0;
  v123 = 0;
  v8 = CreateMutexExW(&MutexAttributes, L"Global\\SearchAndInstallMutex", 0, 0x1F0001u);
  if ( v8 )
  {
    GetLastError();
    v6 = v8;
    v123 = v8;
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
  }
  if ( LastErrorFailHr < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\appinstaller\\appinstaller.cpp",
      (const char *)(unsigned int)LastErrorFailHr,
      v106);
  v10 = WaitForSingleObjectEx(v6, 0x1B7740u, 0);
  if ( v10 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v10 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xFFFFFF7FLL, 0x102u, v11);
    v12 = v6;
  }
  hMutex = v12;
  v143 = v12;
  if ( v10 == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\appinstaller\\appinstaller.cpp",
      v11);
  if ( v10 == 258 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\appinstaller\\appinstaller.cpp",
      (const char *)0x8024A22ELL,
      v106);
  if ( (v10 & 0xFFFFFF7F) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\appinstaller\\appinstaller.cpp",
      (const char *)0x80070005LL,
      v106);
  v13 = (volatile signed __int32 *)operator new(0x108u);
  lpMem[0] = (LPVOID)v13;
  *(_OWORD *)v13 = 0;
  *((_DWORD *)v13 + 2) = 1;
  *((_DWORD *)v13 + 3) = 1;
  *(_QWORD *)v13 = &std::_Ref_count_obj2<Windows::AppInstaller::InstallTrackingInfo>::`vftable';
  memset_0((void *)(v13 + 4), 0, 0xF8u);
  *((_DWORD *)v13 + 4) = -1;
  v14 = operator new(0x48u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *((_QWORD *)v13 + 4) = v14;
  *((_QWORD *)v13 + 6) = 0;
  *((_QWORD *)v13 + 7) = 0;
  *((_OWORD *)v13 + 4) = 0;
  *((_OWORD *)v13 + 5) = 0;
  *((_OWORD *)v13 + 6) = 0;
  *((_QWORD *)v13 + 14) = 0;
  *((_QWORD *)v13 + 15) = 2;
  *((_OWORD *)v13 + 9) = 0;
  *((_OWORD *)v13 + 10) = 0;
  *((_OWORD *)v13 + 11) = 0;
  *((_QWORD *)v13 + 16) = 0;
  *((_QWORD *)v13 + 17) = 0;
  *((_DWORD *)v13 + 48) = -1;
  *((_DWORD *)v13 + 49) = 0;
  *((_QWORD *)v13 + 32) = 0;
  v15 = 2;
  *(_QWORD *)&v115 = v13 + 4;
  *((_QWORD *)&v115 + 1) = v13;
  _InterlockedIncrement(v13 + 3);
  *(_QWORD *)&Windows::AppInstaller::g_installTrackingInfo = v13 + 4;
  v16 = (volatile signed __int32 *)*((_QWORD *)&Windows::AppInstaller::g_installTrackingInfo + 1);
  *((_QWORD *)&Windows::AppInstaller::g_installTrackingInfo + 1) = v13;
  if ( v16 && _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
  v17 = v115 + 184;
  v18 = 0;
  v150 = 0;
  v19 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v126 + 56);
  if ( v19 )
  {
    v20 = (_BYTE *)(**v19)(*(_QWORD *)(v126 + 56), v149);
    v18 = (__int64)v20;
    v150 = v20;
    v21 = v20;
    v22 = v20;
    v23 = v20;
    v24 = v20;
  }
  else
  {
    v20 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v21 = 0;
  }
  v25 = v149;
  if ( v20 != v149 && *(_QWORD *)(v115 + 240) != (_QWORD)v115 + 184LL )
  {
    v18 = *(_QWORD *)(v115 + 240);
    v150 = (_BYTE *)v18;
    *(_QWORD *)(v115 + 240) = v21;
    goto LABEL_41;
  }
  v25 = 0;
  v152 = 0;
  if ( v22 )
  {
    if ( v23 == v149 )
    {
      v25 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)v24 + 8LL))(v24, v151, 0);
      v152 = v25;
      v18 = (__int64)v150;
      if ( !v150 )
        goto LABEL_28;
      v26 = v149;
      LOBYTE(v26) = v150 != v149;
      (*(void (__fastcall **)(_BYTE *, _BYTE *, _BYTE *))(*(_QWORD *)v150 + 32LL))(v150, v26, v25);
      v25 = v152;
    }
    else
    {
      v25 = (_BYTE *)v18;
      v152 = (_BYTE *)v18;
    }
    v18 = 0;
    v150 = 0;
  }
LABEL_28:
  v24 = *(_BYTE **)(v115 + 240);
  if ( !v24 )
    goto LABEL_35;
  v18 = *(_QWORD *)(v115 + 240);
  if ( v24 == (_BYTE *)v17 )
  {
    v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v24 + 8LL))(v18, v149, v25);
    v150 = (_BYTE *)v18;
    v28 = *(_QWORD *)(v115 + 240);
    if ( !v28 )
    {
      v25 = v152;
      goto LABEL_35;
    }
    LOBYTE(v27) = v28 != v17;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v28 + 32LL))(*(_QWORD *)(v115 + 240), v27);
    v18 = (__int64)v150;
    v25 = v152;
  }
  else
  {
    v150 = *(_BYTE **)(v115 + 240);
  }
  *(_QWORD *)(v115 + 240) = 0;
LABEL_35:
  if ( v25 )
  {
    if ( v25 == v151 )
    {
      *(_QWORD *)(v17 + 56) = (*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v25 + 8LL))(v25, v17);
      if ( v152 )
      {
        v29 = v151;
        LOBYTE(v29) = v152 != v151;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v152 + 32LL))(v152, v29);
      }
      v18 = (__int64)v150;
    }
    else
    {
      *(_QWORD *)(v17 + 56) = v25;
    }
  }
LABEL_41:
  if ( v18 )
  {
    v30 = v149;
    LOBYTE(v30) = v18 != (_QWORD)v149;
    (*(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _BYTE *))(*(_QWORD *)v18 + 32LL))(v18, v30, v25, v24);
  }
  v118 = 0;
  if ( *(_QWORD *)(v115 + 240) )
  {
    v31 = operator new(8u);
    *v31 = Windows::AppInstaller::CallbackThreadProc;
    lpMem[0] = v31;
    v15 = 6;
    v32 = _o__beginthreadex(0, 0, std::thread::_Invoke<std::tuple<void (*)(void)>,0>, v31, 0, (char *)&v111 + 8, 6);
    *(_QWORD *)&v111 = v32;
    if ( !v32 )
    {
      DWORD2(v111) = 0;
      std::_Throw_Cpp_error(6);
      goto LABEL_53;
    }
    if ( v118 )
    {
      if ( (_DWORD)v117 )
      {
        _o_terminate(v33, v32);
        __debugbreak();
      }
    }
    else
    {
      v118 = 1;
    }
    v18 = DWORD2(v111);
    v117 = *((_QWORD *)&v111 + 1);
    v116 = v32;
    v111 = 0;
    DWORD2(v111) = 0;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  lpMem[0] = &qword_180095D98;
  _InterlockedIncrement64(&qword_180095D98);
  v15 |= 9u;
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::operator()(
      v18,
      &v120,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>,
      v24);
    _InterlockedDecrement64(&qword_180095D98);
    goto LABEL_54;
  }
LABEL_53:
  _InterlockedDecrement64(&qword_180095D98);
  lpMem[0] = _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::_lambda_invoker_cdecl_;
  winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
    v18,
    &v120,
    lpMem,
    v24);
LABEL_54:
  v129 = 0;
  v130 = 0;
  v127 = 0;
  v128 = 0;
  v36 = *a2;
  v37 = a2[1];
  if ( v36 == v37 )
    goto LABEL_84;
  do
  {
    if ( (unsigned __int64)v36[3] <= 7 )
      v38 = v36;
    else
      v38 = *v36;
    v39 = *((unsigned int *)v36 + 4);
    if ( (_DWORD)v39 )
    {
      v40 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap(
                                         (winrt::impl *)(unsigned int)v39,
                                         (unsigned int)v34);
      memcpy_s((void *const)(v40 + 7), 2 * v39, v38, 2 * v39);
    }
    else
    {
      v40 = 0;
    }
    lpMem[0] = (LPVOID)v40;
    *(_QWORD *)&v131[0] = v40;
    winrt::impl::consume_Windows_Management_Deployment_Internal_IPackageManagerInternal<winrt::Windows::Management::Deployment::Internal::IPackageManagerInternal>::FindPackagesByPackageFamilyName(
      &v120,
      &v112,
      v131);
    if ( v40 )
    {
      v41 = _InterlockedDecrement(v40 + 6);
      if ( v41 )
      {
        if ( v41 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v40);
      }
    }
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(
      &v112,
      &v113);
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::HasCurrent(&v113) )
    {
      if ( *((_BYTE *)v36 + 32) )
      {
        v43 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(
                           &v113,
                           &v119);
        v34 = (_QWORD *)*((_QWORD *)&v129 + 1);
        if ( *((_QWORD *)&v129 + 1) == v130 )
        {
          std::vector<winrt::Windows::ApplicationModel::Package>::_Emplace_reallocate<winrt::Windows::ApplicationModel::Package>(
            &v129,
            *((_QWORD *)&v129 + 1),
            v43);
        }
        else
        {
          v35 = *v43;
          *v43 = 0;
          *v34 = v35;
          *((_QWORD *)&v129 + 1) += 8LL;
        }
        if ( v119 )
        {
          v44 = &v119;
LABEL_77:
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v44);
        }
      }
      else
      {
        v45 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(
                           &v113,
                           &v111);
        v34 = (_QWORD *)*((_QWORD *)&v127 + 1);
        if ( *((_QWORD *)&v127 + 1) == v128 )
        {
          std::vector<winrt::Windows::ApplicationModel::Package>::_Emplace_reallocate<winrt::Windows::ApplicationModel::Package>(
            &v127,
            *((_QWORD *)&v127 + 1),
            v45);
        }
        else
        {
          v35 = *v45;
          *v45 = 0;
          *v34 = v35;
          *((_QWORD *)&v127 + 1) += 8LL;
        }
        if ( (_QWORD)v111 )
        {
          v44 = (__int64 *)&v111;
          goto LABEL_77;
        }
      }
    }
    if ( v113 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v113);
    if ( v112 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v112);
    v36 += 5;
  }
  while ( v36 != v37 );
  v4 = v121;
LABEL_84:
  lpMem[0] = &qword_180095A38;
  _InterlockedIncrement64(&qword_180095A38);
  v46 = v15 | 0x10;
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_145d7b08a85782a985a0b0a38cc4c355_::operator()(
      v35,
      v114,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    LODWORD(v109) = v46;
    _InterlockedDecrement64(&qword_180095A38);
  }
  else
  {
    _InterlockedDecrement64(&qword_180095A38);
    lpMem[0] = _lambda_145d7b08a85782a985a0b0a38cc4c355_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v35,
      v114,
      lpMem);
    LODWORD(v109) = v46;
  }
  *(_QWORD *)&v111 = v114[0];
  if ( v114[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v114[0] + 8LL))(v114[0]);
  *(_OWORD *)lpMem = 0;
  if ( *((_QWORD *)&v115 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL));
  *(_OWORD *)lpMem = v115;
  LOBYTE(v107) = 0;
  v47 = *(_QWORD *)v145;
  Windows::AppInstaller::SearchAndBeginInstall(
    (unsigned int)&v132,
    (unsigned int)lpMem,
    (unsigned int)&v111,
    (unsigned int)&v127,
    *(__int64 *)v145,
    v107,
    v109);
  v119 = v114[0];
  if ( v114[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v114[0] + 8LL))(v114[0]);
  v131[0] = 0;
  if ( *((_QWORD *)&v115 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL));
  v131[0] = v115;
  LOBYTE(v108) = 1;
  Windows::AppInstaller::SearchAndBeginInstall(
    (unsigned int)&v137,
    (unsigned int)v131,
    (unsigned int)&v119,
    (unsigned int)&v129,
    v47,
    v108);
  v48 = v115 + 104;
  if ( _Mtx_lock((_Mtx_t)(v115 + 104)) )
    goto LABEL_216;
  if ( *(_DWORD *)(v48 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v48 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v49 = v115;
  v50 = (_QWORD *)std::_To_absolute_time<__int64,std::ratio<1,1>>(lpMem, (__int64 *)va);
LABEL_100:
  v51 = 0;
  v52 = v115;
  while ( *(_DWORD *)(v115 + 4 * v51) == -1 )
  {
    if ( ++v51 )
      goto LABEL_103;
  }
  while ( 1 )
  {
    std::chrono::steady_clock::now(&v111, v52);
    if ( (__int64)v111 >= *v50 )
      break;
    *(_QWORD *)v145 = *v50 - v111;
    v55 = std::_Clamped_rel_time_ms_count<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v145);
    if ( !(unsigned int)Cnd_timedwait_for_unchecked(v49 + 32, v48, v55) )
      goto LABEL_100;
  }
LABEL_103:
  _Mtx_unlock((_Mtx_t)v48);
  v53 = v137;
  v54 = v138;
  while ( v53 != v54 )
  {
    v56 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::PackageFamilyName(
            v53,
            lpMem);
    if ( *(_QWORD *)v56 )
      v57 = *(const wchar_t **)(*(_QWORD *)v56 + 16LL);
    else
      v57 = &psz;
    memset(v145, 0, sizeof(v145));
    v146 = 0;
    v58 = -1;
    do
      ++v58;
    while ( v57[v58] );
    std::wstring::_Construct<1,unsigned short const *>(v145, v57, v58);
    CurrentStatus = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(
                      v53,
                      &v112);
    v60 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::InstallState(CurrentStatus);
    v147 = v60;
    v61 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(
            v53,
            &v111);
    v62 = *(_DWORD *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                       v61,
                       &v113);
    v148 = v62;
    v63 = v4[1];
    if ( v63 == v4[2] )
    {
      std::vector<Windows::AppInstaller::AppInstallState>::_Emplace_reallocate<Windows::AppInstaller::AppInstallState>(
        v4,
        v63,
        v145);
    }
    else
    {
      *(_WORD *)v63 = *(_WORD *)v145;
      *(_QWORD *)(v63 + 2) = *(_QWORD *)&v145[2];
      *(_DWORD *)(v63 + 10) = *(_DWORD *)&v145[10];
      *(_WORD *)(v63 + 14) = *(_WORD *)&v145[14];
      *(_QWORD *)(v63 + 16) = *(_QWORD *)&v145[16];
      *(_QWORD *)(v63 + 24) = v146;
      *(_QWORD *)&v145[16] = 0;
      v146 = 7;
      *(_WORD *)v145 = 0;
      *(_DWORD *)(v63 + 32) = v60;
      *(_DWORD *)(v63 + 36) = v62;
      v4[1] += 40LL;
    }
    std::wstring::_Tidy_deallocate(v145);
    if ( (_QWORD)v111 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v111);
    if ( v112 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v112);
    v64 = lpMem[0];
    if ( lpMem[0] )
    {
      v65 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v65 )
      {
        if ( v65 < 0 )
          abort();
      }
      else
      {
        v66 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v66, 0, v64);
      }
      lpMem[0] = 0;
    }
    ++v53;
  }
  v67 = v132;
  v68 = v133;
  if ( v132 != v133 )
  {
    do
    {
      v69 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::PackageFamilyName(
              v67,
              &v112);
      if ( *(_QWORD *)v69 )
        v70 = *(const wchar_t **)(*(_QWORD *)v69 + 16LL);
      else
        v70 = &psz;
      memset(v145, 0, sizeof(v145));
      v146 = 0;
      v71 = -1;
      do
        ++v71;
      while ( v70[v71] );
      std::wstring::_Construct<1,unsigned short const *>(v145, v70, v71);
      v72 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(
              v67,
              &v111);
      v73 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::InstallState(v72);
      v147 = v73;
      v74 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(
              v67,
              lpMem);
      v75 = *(_DWORD *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::ErrorCode(
                         v74,
                         &v113);
      v148 = v75;
      v76 = v4[1];
      if ( v76 == v4[2] )
      {
        std::vector<Windows::AppInstaller::AppInstallState>::_Emplace_reallocate<Windows::AppInstaller::AppInstallState>(
          v4,
          v76,
          v145);
      }
      else
      {
        *(_WORD *)v76 = *(_WORD *)v145;
        *(_QWORD *)(v76 + 2) = *(_QWORD *)&v145[2];
        *(_DWORD *)(v76 + 10) = *(_DWORD *)&v145[10];
        *(_WORD *)(v76 + 14) = *(_WORD *)&v145[14];
        *(_QWORD *)(v76 + 16) = *(_QWORD *)&v145[16];
        *(_QWORD *)(v76 + 24) = v146;
        *(_QWORD *)&v145[16] = 0;
        v146 = 7;
        *(_WORD *)v145 = 0;
        *(_DWORD *)(v76 + 32) = v73;
        *(_DWORD *)(v76 + 36) = v75;
        v4[1] += 40LL;
      }
      std::wstring::_Tidy_deallocate(v145);
      if ( lpMem[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(lpMem);
      if ( (_QWORD)v111 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v111);
      v77 = v112;
      if ( v112 )
      {
        v78 = _InterlockedDecrement((volatile signed __int32 *)v112 + 6);
        if ( v78 )
        {
          if ( v78 < 0 )
            abort();
        }
        else
        {
          v79 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v79, 0, v77);
        }
        v112 = 0;
      }
      ++v67;
    }
    while ( v67 != v68 );
    v68 = v133;
  }
  v80 = (__int64 *)v4[1];
  v81 = v121;
  v82 = (__int64 *)*v121;
  if ( (__int64 *)*v121 != v80 )
  {
    v83 = v125;
    do
    {
      if ( *((_DWORD *)v82 + 8) == 9 && *((_DWORD *)v82 + 9) == -2147009278 )
      {
        v84 = (__int64 *)v83[1];
        for ( i = *v83; i != (const void **)v84; i += 5 )
        {
          if ( (unsigned __int64)i[3] <= 7 )
            v86 = (__int64 *)i;
          else
            v86 = (__int64 *)*i;
          v87 = v82;
          if ( (unsigned __int64)v82[3] > 7 )
            v87 = (__int64 *)*v82;
          if ( !(unsigned int)_o__wcsicmp(v87, v86) )
            break;
        }
        if ( *((_BYTE *)i + 33) )
        {
          memset_0(v153, 0, sizeof(v153));
          v88 = (unsigned __int64)v82[3] <= 7 ? (const unsigned __int16 *)v82 : (const unsigned __int16 *)*v82;
          v89 = StringCchCopyW(v153, 0x100u, v88);
          if ( (int)(v89 + 0x80000000) < 0 || v89 == -2147024774 )
            RtlPublishWnfStateData(WNF_USO_STORE_APP_REQUIRES_RESTART, 0, v153, 512, 0);
        }
      }
      v82 += 5;
    }
    while ( v82 != v80 );
    v68 = v133;
    v6 = v123;
    v81 = v121;
  }
  if ( v134 != v135 )
    v135 = v134;
  if ( v139 != v140 )
    v140 = v139;
  v90 = v132;
  if ( v132 != v68 )
  {
    do
    {
      if ( *v90 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v90);
      ++v90;
    }
    while ( v90 != v68 );
    v133 = v132;
  }
  v91 = v137;
  v92 = v138;
  if ( v137 != v138 )
  {
    do
    {
      if ( *v91 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v91);
      ++v91;
    }
    while ( v91 != v92 );
    v138 = v137;
  }
  lpMem[0] = 0;
  if ( v114[0] )
  {
    *(_DWORD *)v145 = 0;
    *(_OWORD *)&v145[8] = 0;
    v94 = (**(__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))v114[0])(
            v114[0],
            winrt::impl::guid_v<winrt::Windows::Foundation::IClosable>,
            lpMem);
    if ( v94 < 0 )
      winrt::throw_hresult((unsigned int)v94, v145);
    v93 = lpMem[0];
  }
  else
  {
    v93 = 0;
  }
  *(_DWORD *)v145 = 0;
  *(_OWORD *)&v145[8] = 0;
  v95 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v93 + 48LL))(v93);
  if ( v95 < 0 )
    winrt::throw_hresult((unsigned int)v95, v145);
  if ( v93 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(lpMem);
  if ( *(_QWORD *)(v115 + 240) )
  {
    std::unique_lock<std::mutex>::unique_lock<std::mutex>(v145, &Windows::AppInstaller::g_callbackQueueMutex);
    Windows::AppInstaller::g_callbackProcShutdown = 1;
    if ( v145[8] )
      _Mtx_unlock(*(_Mtx_t *)v145);
    _Cnd_broadcast((_Cnd_t)&Windows::AppInstaller::g_callbackProcCV);
    if ( !(_DWORD)v117 )
    {
      std::_Throw_Cpp_error(1);
      __debugbreak();
    }
    if ( (_DWORD)v117 != _Thrd_id() )
    {
      *(_QWORD *)v145 = v116;
      *(_QWORD *)&v145[8] = v117;
      if ( _Thrd_join((_Thrd_t *)v145, 0) )
      {
        std::_Throw_Cpp_error(2);
        __debugbreak();
      }
      v131[0] = 0;
      v116 = 0;
      v117 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      goto LABEL_200;
    }
LABEL_216:
    std::_Throw_Cpp_error(5);
LABEL_217:
    wil::details::in1diag3::_FailFast_GetLastError(v101, (void *)0xA0B, v99, v100);
  }
LABEL_200:
  std::vector<void *>::~vector<void *>(&v139);
  std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::_Tidy(&v137);
  std::vector<void *>::~vector<void *>(&v134);
  std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::_Tidy(&v132);
  if ( v114[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v114);
  std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::_Tidy(&v127);
  std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::_Tidy(&v129);
  if ( v120 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v120);
  if ( v118 && (_DWORD)v117 )
    ((void (*)(void))_o_terminate)();
  std::shared_ptr<SystemInterface::Service::System>::~shared_ptr<SystemInterface::Service::System>(&v115);
  if ( hMutex && !ReleaseMutex(hMutex) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v96, v97);
  if ( v6 )
  {
    v98 = CloseHandle(v6);
    v101 = retaddr;
    if ( !v98 )
      goto LABEL_217;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  std::vector<Windows::AppInstaller::AppToInstall>::_Tidy(v125);
  v102 = v126;
  v103 = *(__int64 **)(v126 + 56);
  if ( v103 )
  {
    v104 = *v103;
    LOBYTE(v104) = v103 != (__int64 *)v126;
    (*(void (__fastcall **)(__int64 *, __int64))(*v103 + 32))(v103, v104);
    *(_QWORD *)(v102 + 56) = 0;
  }
  return v81;
}

```

## disassembly

```asm
0x18004d15c  mov     [rsp-8+arg_10], rbx
0x18004d161  mov     [rsp-8+arg_18], r9
0x18004d166  push    rbp
0x18004d167  push    rsi
0x18004d168  push    rdi
0x18004d169  push    r12
0x18004d16b  push    r13
0x18004d16d  push    r14
0x18004d16f  push    r15
0x18004d171  lea     rbp, [rsp-3A0h]
0x18004d179  sub     rsp, 4A0h
0x18004d180  mov     rax, cs:__security_cookie
0x18004d187  xor     rax, rsp
0x18004d18a  mov     [rbp+3D0h+var_40], rax
0x18004d191  mov     [rbp+3D0h+var_2F0], r8
0x18004d198  mov     r13, rdx
0x18004d19b  mov     [rbp+3D0h+var_3F8], rdx
0x18004d19f  mov     r12, rcx
0x18004d1a2  mov     [rbp+3D0h+var_418], rcx
0x18004d1a6  mov     [rbp+3D0h+var_318], rcx
0x18004d1ad  mov     [rbp+3D0h+var_310], rdx
0x18004d1b4  mov     rax, [rbp+3D0h+arg_20]
0x18004d1bb  mov     [rbp+3D0h+var_3F0], rax
0x18004d1bf  mov     [rbp+3D0h+var_300], rax
0x18004d1c6  xor     r15d, r15d
0x18004d1c9  mov     [rsp+4D0h+var_4A0], r15d
0x18004d1ce  xorps   xmm0, xmm0
0x18004d1d1  xor     eax, eax
0x18004d1d3  movups  xmmword ptr [rbp+3D0h+MutexAttributes.nLength], xmm0
0x18004d1d7  mov     qword ptr [rbp+3D0h+MutexAttributes.bInheritHandle], rax
0x18004d1de  mov     [rbp+3D0h+SecurityDescriptor], r15
0x18004d1e2  xor     r9d, r9d; SecurityDescriptorSize
0x18004d1e5  lea     r8, [rbp+3D0h+SecurityDescriptor]; SecurityDescriptor
0x18004d1e9  lea     edx, [rax+1]; StringSDRevision
0x18004d1ec  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x18004d1f3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d1f9  mov     rcx, [rbp+3D8h]; this
0x18004d200  test    eax, eax
0x18004d202  jz      loc_18004E1D9
0x18004d208  mov     [rbp+3D0h+MutexAttributes.nLength], 18h
0x18004d20f  mov     rax, [rbp+3D0h+SecurityDescriptor]
0x18004d213  mov     [rbp+3D0h+MutexAttributes.lpSecurityDescriptor], rax
0x18004d217  mov     [rbp+3D0h+MutexAttributes.bInheritHandle], r15d
0x18004d21e  mov     edi, r15d
0x18004d221  mov     [rbp+3D0h+var_408], r15
0x18004d225  mov     r9d, 1F0001h; dwDesiredAccess
0x18004d22b  xor     r8d, r8d; dwFlags
0x18004d22e  lea     rdx, Name; "Global\\SearchAndInstallMutex"
0x18004d235  lea     rcx, [rbp+3D0h+MutexAttributes]; lpMutexAttributes
0x18004d239  call    cs:__imp_CreateMutexExW
0x18004d23f  mov     rbx, rax
0x18004d242  test    rax, rax
0x18004d245  jz      short loc_18004D259
0x18004d247  call    cs:__imp_GetLastError
0x18004d24d  mov     rdi, rbx
0x18004d250  mov     [rbp+3D0h+var_408], rbx
0x18004d254  mov     eax, r15d
0x18004d257  jmp     short loc_18004D25E
0x18004d259  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004d25e  mov     rcx, [rbp+3D8h]; this
0x18004d265  test    eax, eax
0x18004d267  js      loc_18004E1EB
0x18004d26d  xor     r8d, r8d; bAlertable
0x18004d270  mov     edx, 1B7740h; dwMilliseconds
0x18004d275  mov     rcx, rdi; hHandle
0x18004d278  call    cs:__imp_WaitForSingleObjectEx
0x18004d27e  mov     edx, 0FFFFFF7Fh; void *
0x18004d283  mov     r8d, 102h; unsigned int
0x18004d289  cmp     eax, r8d
0x18004d28c  jz      short loc_18004D29B
0x18004d28e  test    edx, eax
0x18004d290  jnz     loc_18004E200
0x18004d296  mov     rcx, rdi
0x18004d299  jmp     short loc_18004D29E
0x18004d29b  mov     rcx, r15
0x18004d29e  mov     [rbp+3D0h+hMutex], rcx
0x18004d2a2  mov     [rbp+3D0h+var_308], rcx
0x18004d2a9  mov     rcx, [rbp+3D8h]; this
0x18004d2b0  or      ebx, 0FFFFFFFFh
0x18004d2b3  cmp     eax, ebx
0x18004d2b5  jz      loc_18004E20D
0x18004d2bb  mov     rcx, [rbp+3D8h]; this
0x18004d2c2  cmp     eax, r8d
0x18004d2c5  jz      loc_18004E21F
0x18004d2cb  test    edx, eax
0x18004d2cd  setnz   al
0x18004d2d0  mov     rcx, [rbp+3D8h]; this
0x18004d2d7  test    al, al
0x18004d2d9  jnz     loc_18004E237
0x18004d2df  mov     ecx, 108h; Size
0x18004d2e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d2e9  mov     r14, rax
0x18004d2ec  mov     [rsp+4D0h+lpMem], rax
0x18004d2f1  xorps   xmm0, xmm0
0x18004d2f4  movups  xmmword ptr [rax], xmm0
0x18004d2f7  mov     dword ptr [rax+8], 1
0x18004d2fe  mov     dword ptr [rax+0Ch], 1
0x18004d305  lea     rax, ??_7?$_Ref_count_obj2@UInstallTrackingInfo@AppInstaller@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::AppInstaller::InstallTrackingInfo>::`vftable'
0x18004d30c  mov     [r14], rax
0x18004d30f  lea     rsi, [r14+10h]
0x18004d313  xor     edx, edx; Val
0x18004d315  mov     r8d, 0F8h; Size
0x18004d31b  mov     rcx, rsi; void *
0x18004d31e  call    memset_0
0x18004d323  mov     [rsi], ebx
0x18004d325  mov     ecx, 48h ; 'H'; Size
0x18004d32a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d32f  mov     [rax], rax
0x18004d332  mov     [rax+8], rax
0x18004d336  mov     [rax+10h], rax
0x18004d33a  mov     word ptr [rax+18h], 101h
0x18004d340  mov     [rsi+10h], rax
0x18004d344  mov     [rsi+20h], r15
0x18004d348  mov     [rsi+28h], r15
0x18004d34c  xorps   xmm0, xmm0
0x18004d34f  xor     eax, eax
0x18004d351  movups  xmmword ptr [rsi+30h], xmm0
0x18004d355  movups  xmmword ptr [rsi+40h], xmm0
0x18004d359  movups  xmmword ptr [rsi+50h], xmm0
0x18004d35d  mov     [rsi+60h], rax
0x18004d361  mov     qword ptr [rsi+68h], 2
0x18004d369  movups  xmmword ptr [rsi+80h], xmm0
0x18004d370  movups  xmmword ptr [rsi+90h], xmm0
0x18004d377  movups  xmmword ptr [rsi+0A0h], xmm0
0x18004d37e  mov     [rsi+70h], r15
0x18004d382  mov     [rsi+78h], r15
0x18004d386  mov     dword ptr [rsi+0B0h], 0FFFFFFFFh
0x18004d390  mov     eax, 2
0x18004d395  mov     [rsi+0B4h], r15d
0x18004d39c  mov     [rsi+0F0h], r15
0x18004d3a3  mov     r15d, eax
0x18004d3a6  mov     [rsp+4D0h+var_4A0], eax
0x18004d3aa  mov     qword ptr [rbp+3D0h+var_450], rsi
0x18004d3ae  mov     qword ptr [rbp+3D0h+var_450+8], r14
0x18004d3b2  lock inc dword ptr [r14+0Ch]
0x18004d3b7  mov     qword ptr cs:?g_installTrackingInfo@AppInstaller@Windows@@3V?$weak_ptr@UInstallTrackingInfo@AppInstaller@Windows@@@std@@A, rsi; std::weak_ptr<Windows::AppInstaller::InstallTrackingInfo> Windows::AppInstaller::g_installTrackingInfo
0x18004d3be  mov     rcx, qword ptr cs:?g_installTrackingInfo@AppInstaller@Windows@@3V?$weak_ptr@UInstallTrackingInfo@AppInstaller@Windows@@@std@@A+8; std::weak_ptr<Windows::AppInstaller::InstallTrackingInfo> Windows::AppInstaller::g_installTrackingInfo
0x18004d3c5  mov     qword ptr cs:?g_installTrackingInfo@AppInstaller@Windows@@3V?$weak_ptr@UInstallTrackingInfo@AppInstaller@Windows@@@std@@A+8, r14; std::weak_ptr<Windows::AppInstaller::InstallTrackingInfo> Windows::AppInstaller::g_installTrackingInfo
0x18004d3cc  xor     r14d, r14d
0x18004d3cf  test    rcx, rcx
0x18004d3d2  jz      short loc_18004D3ED
0x18004d3d4  or      eax, 0FFFFFFFFh
0x18004d3d7  lock xadd [rcx+0Ch], eax
0x18004d3dc  cmp     eax, 1
0x18004d3df  jnz     short loc_18004D3ED
0x18004d3e1  mov     rax, [rcx]
0x18004d3e4  mov     rax, [rax+8]
0x18004d3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3ed  mov     rbx, qword ptr [rbp+3D0h+var_450]
0x18004d3f1  add     rbx, 0B8h
0x18004d3f8  mov     rcx, r14
0x18004d3fb  mov     [rbp+3D0h+var_288], rcx
0x18004d402  mov     r8, [rbp+3D0h+var_3F0]
0x18004d406  mov     r8, [r8+38h]
0x18004d40a  test    r8, r8
0x18004d40d  jz      short loc_18004D43C
0x18004d40f  mov     rax, [r8]
0x18004d412  lea     rdx, [rbp+3D0h+var_2C0]
0x18004d419  mov     rcx, r8
0x18004d41c  mov     rax, [rax]
0x18004d41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d424  mov     rcx, rax
0x18004d427  mov     [rbp+3D0h+var_288], rax
0x18004d42e  mov     rdx, rax
0x18004d431  mov     r10, rax
0x18004d434  mov     r11, rax
0x18004d437  mov     r9, rax
0x18004d43a  jmp     short loc_18004D44B
0x18004d43c  mov     rax, r14
0x18004d43f  mov     r10, r14
0x18004d442  mov     r11, r14
0x18004d445  mov     r9, r14
0x18004d448  mov     rdx, r14
0x18004d44b  lea     r8, [rbp+3D0h+var_2C0]
0x18004d452  cmp     rax, r8
0x18004d455  jz      short loc_18004D471
0x18004d457  cmp     [rbx+38h], rbx
0x18004d45b  jz      short loc_18004D471
0x18004d45d  mov     rcx, [rbx+38h]
0x18004d461  mov     [rbp+3D0h+var_288], rcx
0x18004d468  mov     [rbx+38h], rdx
0x18004d46c  jmp     loc_18004D5B7
0x18004d471  mov     r8, r14
0x18004d474  mov     [rbp+3D0h+var_248], r14
0x18004d47b  test    r10, r10
0x18004d47e  jz      short loc_18004D4EE
0x18004d480  lea     rax, [rbp+3D0h+var_2C0]
0x18004d487  cmp     r11, rax
0x18004d48a  jnz     short loc_18004D4DA
0x18004d48c  mov     rax, [r9]
0x18004d48f  lea     rdx, [rbp+3D0h+var_280]
0x18004d496  mov     rcx, r9
0x18004d499  mov     rax, [rax+8]
0x18004d49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4a2  mov     r8, rax
0x18004d4a5  mov     [rbp+3D0h+var_248], rax
0x18004d4ac  mov     rcx, [rbp+3D0h+var_288]
0x18004d4b3  test    rcx, rcx
0x18004d4b6  jz      short loc_18004D4EE
0x18004d4b8  mov     rax, [rcx]
0x18004d4bb  lea     rdx, [rbp+3D0h+var_2C0]
0x18004d4c2  cmp     rcx, rdx
0x18004d4c5  setnz   dl
0x18004d4c8  mov     rax, [rax+20h]
0x18004d4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4d1  mov     r8, [rbp+3D0h+var_248]
0x18004d4d8  jmp     short loc_18004D4E4
0x18004d4da  mov     r8, rcx
0x18004d4dd  mov     [rbp+3D0h+var_248], rcx
0x18004d4e4  mov     rcx, r14
0x18004d4e7  mov     [rbp+3D0h+var_288], rcx
0x18004d4ee  mov     r9, [rbx+38h]
0x18004d4f2  test    r9, r9
0x18004d4f5  jz      short loc_18004D55E
0x18004d4f7  mov     rcx, r9
0x18004d4fa  cmp     r9, rbx
0x18004d4fd  jnz     short loc_18004D553
0x18004d4ff  mov     rax, [r9]
0x18004d502  lea     rdx, [rbp+3D0h+var_2C0]
0x18004d509  mov     rax, [rax+8]
0x18004d50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d512  mov     rcx, rax
0x18004d515  mov     [rbp+3D0h+var_288], rax
0x18004d51c  mov     r8, [rbx+38h]
0x18004d520  test    r8, r8
0x18004d523  jz      short loc_18004D54A
0x18004d525  mov     rax, [r8]
0x18004d528  cmp     r8, rbx
0x18004d52b  setnz   dl
0x18004d52e  mov     rcx, r8
0x18004d531  mov     rax, [rax+20h]
0x18004d535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d53a  mov     rcx, [rbp+3D0h+var_288]
0x18004d541  mov     r8, [rbp+3D0h+var_248]
0x18004d548  jmp     short loc_18004D55A
0x18004d54a  mov     r8, [rbp+3D0h+var_248]
0x18004d551  jmp     short loc_18004D55E
0x18004d553  mov     [rbp+3D0h+var_288], rcx
0x18004d55a  mov     [rbx+38h], r14
0x18004d55e  test    r8, r8
0x18004d561  jz      short loc_18004D5B7
0x18004d563  lea     rax, [rbp+3D0h+var_280]
0x18004d56a  cmp     r8, rax
0x18004d56d  jnz     short loc_18004D5B3
0x18004d56f  mov     rax, [r8]
0x18004d572  mov     rdx, rbx
0x18004d575  mov     rcx, r8
0x18004d578  mov     rax, [rax+8]
0x18004d57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d581  mov     [rbx+38h], rax
0x18004d585  mov     rcx, [rbp+3D0h+var_248]
0x18004d58c  test    rcx, rcx
0x18004d58f  jz      short loc_18004D5AA
0x18004d591  mov     rax, [rcx]
0x18004d594  lea     rdx, [rbp+3D0h+var_280]
0x18004d59b  cmp     rcx, rdx
0x18004d59e  setnz   dl
0x18004d5a1  mov     rax, [rax+20h]
0x18004d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5aa  mov     rcx, [rbp+3D0h+var_288]
0x18004d5b1  jmp     short loc_18004D5B7
0x18004d5b3  mov     [rbx+38h], r8
0x18004d5b7  test    rcx, rcx
0x18004d5ba  jz      short loc_18004D5D5
0x18004d5bc  mov     rax, [rcx]
0x18004d5bf  lea     rdx, [rbp+3D0h+var_2C0]
0x18004d5c6  cmp     rcx, rdx
0x18004d5c9  setnz   dl
0x18004d5cc  mov     rax, [rax+20h]
0x18004d5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5d5  mov     [rbp+3D0h+var_430], r14b
0x18004d5d9  mov     ebx, 6
0x18004d5de  mov     rax, qword ptr [rbp+3D0h+var_450]
0x18004d5e2  cmp     [rax+0F0h], r14
0x18004d5e9  jz      loc_18004D678
0x18004d5ef  lea     ecx, [rbx+2]; Size
0x18004d5f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d5f7  lea     rcx, ?CallbackThreadProc@AppInstaller@Windows@@YAXXZ; Windows::AppInstaller::CallbackThreadProc(void)
0x18004d5fe  mov     [rax], rcx
0x18004d601  mov     [rsp+4D0h+lpMem], rax
0x18004d606  mov     r15d, ebx
0x18004d609  mov     [rsp+4D0h+var_4A0], ebx
0x18004d60d  lea     rcx, [rsp+4D0h+var_480+8]
0x18004d612  mov     [rsp+4D0h+var_4A8], rcx
0x18004d617  mov     dword ptr [rsp+4D0h+var_4B0], r14d
0x18004d61c  mov     r9, rax
0x18004d61f  lea     r8, ??$_Invoke@V?$tuple@P6AXXZ@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (*)(void)>,0>(void *)
0x18004d626  xor     edx, edx
0x18004d628  xor     ecx, ecx
0x18004d62a  call    cs:__imp__o__beginthreadex
0x18004d630  mov     rdx, rax
0x18004d633  mov     qword ptr [rsp+4D0h+var_480], rax
0x18004d638  test    rax, rax
0x18004d63b  jz      loc_18004D6CF
0x18004d641  cmp     [rbp+3D0h+var_430], r14b
0x18004d645  jz      short loc_18004D654
0x18004d647  cmp     dword ptr [rbp+3D0h+var_438], r14d
0x18004d64b  jz      short loc_18004D658
0x18004d64d  call    cs:__imp__o_terminate
0x18004d653  int     3; Trap to Debugger
  ... truncated ...
```
