# UxUpdateManager::RebootToCompleteInstall(ulong,int,ulong *,int,int,double)

- ea: `0x18003b5e0`
- end: `0x18003cc0a`
- name: `?RebootToCompleteInstall@UxUpdateManager@@UEAAJKHPEAKHHN@Z`
- size: `5674`
- prototype: `__int64 __fastcall(UxUpdateManager *this, int, int, unsigned int *, int, int, HKEY)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008e64`
- `0x1800107cc`
- `0x180010890`
- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18001b064`
- `0x18002deb8`
- `0x18002e168`
- `0x18003a028`
- `0x18003a1bc`
- `0x18003b5e0`
- `0x18003cc10`
- `0x18003cf2c`
- `0x18003e168`
- `0x18003e814`
- `0x18003ecb8`
- `0x18003f520`
- `0x180040290`
- `0x1800420e0`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18003c751`
- `ntdll!RtlPublishWnfStateData` at `0x18003c751`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c75c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c75c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c3f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c3f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c3c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c3c6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!IsSystemResumeAutomatic` at `0x18003ba0b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!IsSystemResumeAutomatic` at `0x18003ba0b`

## string_xrefs

- `0x18003cbf7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18003b75c`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003bda1`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003bf9b`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003bfe4`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003c3db`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003c8f3`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003c930`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003cbdd`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003ba15`: `Machine woke up automatically to run reboot task, ignoring power checks`
- `0x18003bff5`: `Preventing machine from sleeping: Reboot To Complete Install`
- `0x18003c0f9`: `Reboot To Complete Install`
- `0x18003c507`: `UpdateUX`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UxUpdateManager::RebootToCompleteInstall(
        UxUpdateManager *this,
        int a2,
        int a3,
        unsigned int *a4,
        int a5,
        int a6,
        HKEY a7)
{
  volatile signed __int32 *v8; // r13
  __int64 *System; // rax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rsi
  volatile signed __int32 *v13; // rsi
  int v14; // eax
  unsigned int v15; // esi
  const char *v16; // r9
  __int64 result; // rax
  unsigned int v18; // r14d
  __int64 *v19; // rax
  _QWORD *v20; // rax
  char v21; // al
  __int64 v22; // r8
  bool v23; // r12
  volatile signed __int32 *v24; // rsi
  volatile signed __int32 *v27; // rsi
  bool v30; // r14
  __int64 *v31; // rax
  _QWORD *v32; // rax
  volatile signed __int32 *v33; // rsi
  volatile signed __int32 *v34; // rsi
  char v35; // si
  int v36; // eax
  unsigned int v37; // r15d
  __int64 *v38; // rax
  __int64 (__fastcall *v39)(__int64, __int128 *, int *); // rsi
  __int64 *traits_2_unsigned_short; // rax
  const char *v41; // r9
  __int64 v42; // r11
  __int64 v43; // rax
  char v44; // r14
  volatile signed __int32 *v45; // rsi
  volatile signed __int32 *v46; // rsi
  HKEY v47; // xmm0_8
  __int64 *v48; // rax
  __int64 v49; // rcx
  unsigned int *v50; // rsi
  const char *v51; // r9
  volatile signed __int32 *v52; // rsi
  volatile signed __int32 *v53; // rsi
  HKEY v54; // r14
  int v55; // eax
  __int64 *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rsi
  void (__fastcall *v59)(__int64, _QWORD, _QWORD, _QWORD, DWORD, char, __int128 *); // r14
  _QWORD *v60; // rax
  __int64 v61; // rcx
  volatile signed __int32 *v62; // rsi
  volatile signed __int32 *v63; // rsi
  int v64; // eax
  int v65; // eax
  __int64 *v66; // rax
  _QWORD *v67; // rax
  volatile signed __int32 *v68; // rsi
  volatile signed __int32 *v69; // rsi
  __int64 v70; // r8
  const char *v71; // r9
  __int64 *v72; // rax
  _QWORD *v73; // rax
  char v74; // r15
  volatile signed __int32 *v75; // rsi
  volatile signed __int32 *v76; // rsi
  __int64 *v77; // rax
  __int64 **v78; // rax
  __int64 *v79; // rcx
  __int64 v80; // rax
  __int64 v81; // r8
  __int64 v82; // rdx
  volatile signed __int32 *v83; // rsi
  volatile signed __int32 *v84; // rsi
  const WCHAR *v85; // rdx
  unsigned int v86; // eax
  __int64 *v87; // rax
  _QWORD *v88; // rax
  char v89; // r14
  volatile signed __int32 *v90; // rsi
  volatile signed __int32 *v91; // rsi
  int v92; // r9d
  int v93; // ecx
  __int64 *v94; // rax
  _QWORD *v95; // rax
  volatile signed __int32 *v96; // rsi
  volatile signed __int32 *v97; // rsi
  __int64 *v98; // rax
  _QWORD *v99; // rax
  char v100; // r14
  volatile signed __int32 *v101; // rsi
  volatile signed __int32 *v102; // rsi
  __int64 *v103; // rax
  _QWORD *v104; // rax
  bool v105; // r14
  char v106; // r15
  volatile signed __int32 *v107; // rsi
  volatile signed __int32 *v108; // rsi
  __int64 v109; // r9
  unsigned int v110; // esi
  __int64 v111; // r8
  unsigned int v112; // eax
  unsigned int v113; // r14d
  int v114; // eax
  int v115; // eax
  __int64 *v116; // rax
  __int64 v117; // rax
  __int64 v118; // rsi
  void (__fastcall *v119)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, REGSAM, __int128 *); // r15
  _QWORD *v120; // rax
  __int64 v121; // rcx
  volatile signed __int32 *v122; // rsi
  volatile signed __int32 *v123; // rsi
  __int64 v124; // r8
  __int64 v125; // rcx
  __int64 *v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  char v130; // bl
  wil *v131; // rcx
  int v132; // eax
  int v133; // ecx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-2B8h]
  REGSAM samDesired; // [rsp+28h] [rbp-2B0h]
  char v136; // [rsp+50h] [rbp-288h]
  char v137; // [rsp+51h] [rbp-287h]
  char v138; // [rsp+52h] [rbp-286h]
  char v139; // [rsp+53h] [rbp-285h]
  __int128 v140; // [rsp+60h] [rbp-278h] BYREF
  int v141; // [rsp+70h] [rbp-268h] BYREF
  unsigned int v142; // [rsp+74h] [rbp-264h]
  unsigned int v143; // [rsp+78h] [rbp-260h]
  int v144; // [rsp+7Ch] [rbp-25Ch]
  int v145; // [rsp+80h] [rbp-258h]
  __int64 v146; // [rsp+88h] [rbp-250h] BYREF
  volatile signed __int32 *v147; // [rsp+90h] [rbp-248h]
  volatile signed __int32 *v148; // [rsp+98h] [rbp-240h] BYREF
  __int64 v149; // [rsp+A0h] [rbp-238h]
  int v150; // [rsp+A8h] [rbp-230h]
  HKEY v151; // [rsp+B0h] [rbp-228h]
  volatile signed __int32 *v152; // [rsp+B8h] [rbp-220h]
  __int128 v153; // [rsp+C0h] [rbp-218h] BYREF
  __int64 v154; // [rsp+D0h] [rbp-208h] BYREF
  volatile signed __int32 *v155; // [rsp+D8h] [rbp-200h]
  _QWORD v156[2]; // [rsp+E0h] [rbp-1F8h] BYREF
  char v157[8]; // [rsp+F0h] [rbp-1E8h] BYREF
  char v158[32]; // [rsp+F8h] [rbp-1E0h] BYREF
  char v159[32]; // [rsp+118h] [rbp-1C0h] BYREF
  char v160[32]; // [rsp+138h] [rbp-1A0h] BYREF
  char v161[40]; // [rsp+158h] [rbp-180h] BYREF
  unsigned int v162; // [rsp+180h] [rbp-158h] BYREF
  HKEY hKey; // [rsp+188h] [rbp-150h] BYREF
  int v164; // [rsp+190h] [rbp-148h] BYREF
  int v165; // [rsp+194h] [rbp-144h] BYREF
  int v166; // [rsp+198h] [rbp-140h] BYREF
  __int64 v167; // [rsp+1A0h] [rbp-138h] BYREF
  __int128 v168; // [rsp+1A8h] [rbp-130h] BYREF
  __int64 v169; // [rsp+1B8h] [rbp-120h]
  _OWORD v170[2]; // [rsp+1C0h] [rbp-118h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+1E0h] [rbp-F8h] BYREF
  __int128 v172; // [rsp+1F0h] [rbp-E8h]
  unsigned int v173; // [rsp+200h] [rbp-D8h] BYREF
  __int128 v174; // [rsp+208h] [rbp-D0h] BYREF
  __int64 v175; // [rsp+218h] [rbp-C0h]
  __int64 v176; // [rsp+220h] [rbp-B8h]
  __int128 v177; // [rsp+228h] [rbp-B0h] BYREF
  __int64 v178; // [rsp+238h] [rbp-A0h]
  __int64 v179; // [rsp+240h] [rbp-98h]
  __int128 v180; // [rsp+248h] [rbp-90h] BYREF
  __int64 v181; // [rsp+258h] [rbp-80h]
  __int64 v182; // [rsp+260h] [rbp-78h]
  __int128 v183; // [rsp+268h] [rbp-70h] BYREF
  __int64 v184; // [rsp+278h] [rbp-60h]
  __int64 v185; // [rsp+280h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  try
  {
    v151 = (HKEY)a4;
    v8 = (volatile signed __int32 *)this;
    v156[0] = this;
    hKey = (HKEY)a4;
    v145 = 0;
    v144 = 0;
    System = SystemInterface::Service::GetSystem((__int64 *)&v140);
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, volatile signed __int32 **))(*(_QWORD *)*System + 56LL))(
                      *System,
                      &v148);
    v137 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    v12 = (volatile signed __int32 *)v149;
    if ( v149 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v149 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = (volatile signed __int32 *)*((_QWORD *)&v140 + 1);
    if ( *((_QWORD *)&v140 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v140 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v168 = 0;
    v169 = 0;
    UxUpdateManager::GetRestartRequiredUpdateIdentifiers(v11, &v168);
    v165 = 0;
    v164 = 0;
    v14 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, int *, int *))(*(_QWORD *)v8 + 32LL))(
            v8,
            18,
            &v165,
            &v164);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
        (const char *)(unsigned int)v14,
        dwOptions[0]);
      std::vector<UxUpdateManager::UxUpdateIdentifier>::~vector<UxUpdateManager::UxUpdateIdentifier>(&v168);
      return v15;
    }
    v18 = v164 != 0 ? v165 : 0;
    v143 = v18;
    v19 = SystemInterface::Service::GetSystem((__int64 *)&v140);
    v20 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, volatile signed __int32 **))*v19)(*v19, &v148);
    v21 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 16LL))(*v20);
    v23 = v21 == 0;
    v139 = v21 == 0;
    v24 = (volatile signed __int32 *)v149;
    if ( v149 )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v149 + 8)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( !_InterlockedDecrement(v24 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v27 = (volatile signed __int32 *)*((_QWORD *)&v140 + 1);
    if ( *((_QWORD *)&v140 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v140 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( !_InterlockedDecrement(v27 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    try
    {
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 7;
      LOWORD(v174) = 0;
      v177 = 0;
      v178 = 0;
      v179 = 7;
      LOWORD(v177) = 0;
      v180 = 0;
      v181 = 0;
      v182 = 7;
      LOWORD(v180) = 0;
      v183 = 0;
      v184 = 0;
      v185 = 7;
      LOWORD(v183) = 0;
      LOBYTE(v22) = v23;
      UxUpdateManager::LogInitiatingRebootEvent(v8, &v168, v22, v18);
      v152 = v8 + 4;
      if ( _InterlockedCompareExchange(v8 + 4, 1, 0) == 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)0x8024A112LL,
          dwOptions[0]);
      v148 = v8;
      v149 = 1;
      v30 = UxUpdateManager::DidUXRebootTaskWakeUpDevice(retaddr);
      v31 = SystemInterface::Service::GetSystem(&v146);
      v32 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, __int128 *))*v31)(*v31, &v140);
      v136 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 8LL))(*v32);
      v138 = v136;
      v33 = (volatile signed __int32 *)*((_QWORD *)&v140 + 1);
      if ( *((_QWORD *)&v140 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v140 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      v34 = v147;
      if ( v147 )
      {
        if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      v35 = v136;
      if ( !v136 && v30 && IsSystemResumeAutomatic() )
      {
        *(_QWORD *)&v140 = L"Machine woke up automatically to run reboot task, ignoring power checks";
        *((_QWORD *)&v140 + 1) = 71;
        SystemInterface::Log<>(&v140);
        v35 = 1;
        v136 = 1;
        v138 = 1;
      }
      v36 = -5;
      if ( !v35 )
        v36 = a2;
      v142 = v36;
      v37 = v36;
      v150 = v36;
      v38 = SystemInterface::Service::GetSystem((__int64 *)&v153);
      v39 = *(__int64 (__fastcall **)(__int64, __int128 *, int *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v38 + 40LL))(
                                                                                  *v38,
                                                                                  &v146)
                                                                 + 56LL);
      v141 = 40;
      traits_2_unsigned_short = (__int64 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                             L"MinimumBatteryLevel",
                                             &qword_1801005C8,
                                             0);
      if ( traits_2_unsigned_short == &qword_1801005C8
        || (v43 = ((char *)traits_2_unsigned_short - (char *)L"MinimumBatteryLevel") >> 1, v43 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v41);
      }
      *(_QWORD *)&v140 = L"MinimumBatteryLevel";
      *((_QWORD *)&v140 + 1) = v43;
      v44 = v39(v42, &v140, &v141);
      v45 = v147;
      if ( v147 )
      {
        if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
          if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
        }
      }
      v46 = (volatile signed __int32 *)*((_QWORD *)&v153 + 1);
      if ( *((_QWORD *)&v153 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v153 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
      if ( a6 )
        v47 = hKey;
      else
        v47 = a7;
      try
      {
        *(_QWORD *)&v140 = v47;
        BYTE8(v140) = a6 == 0;
        *(_DWORD *)((char *)&v140 + 9) = *(_DWORD *)((char *)&v149 + 1);
        *(_WORD *)((char *)&v140 + 13) = *(_WORD *)((char *)&v149 + 5);
        HIBYTE(v140) = HIBYTE(v149);
        v48 = SystemInterface::Service::GetSystem(&v154);
        v49 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v48 + 72LL))(*v48, &v146);
        v153 = v140;
        LOBYTE(dwOptions[0]) = v44;
        v50 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, char *, _QWORD, __int128 *))(*(_QWORD *)v49 + 184LL))(
                                v49,
                                v157,
                                v37,
                                &v153);
        v173 = *v50;
        std::wstring::operator=(&v174, v50 + 2);
        std::wstring::operator=(&v177, v50 + 10);
        std::wstring::operator=(&v180, v50 + 18);
        std::wstring::operator=(&v183, v50 + 26);
        std::wstring::~wstring(v161);
        std::wstring::~wstring(v160);
        std::wstring::~wstring(v159);
        std::wstring::~wstring(v158);
        v52 = v147;
        if ( v147 )
        {
          if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
        v53 = v155;
        if ( v155 )
        {
          if ( _InterlockedExchangeAdd(v155 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
            if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
          }
        }
        v54 = v151;
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x2C2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          v51);
        v136 = v138;
        v145 = v144;
        v37 = v150;
        v142 = v150;
        v8 = (volatile signed __int32 *)v156[0];
        v54 = hKey;
        v151 = hKey;
      }
      v55 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, _QWORD))(*(_QWORD *)v8 + 56LL))(v8, 9, v173);
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C4,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)(unsigned int)v55,
          dwOptions[0]);
      if ( v173 )
      {
        LogDeferReasonTelemetryEventForAllUpdates(&v168, &v173, v37);
        *(_DWORD *)v54 = v173;
        v56 = SystemInterface::Service::GetSystem((__int64 *)&v153);
        v57 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v56 + 104LL))(*v56, &v154);
        v58 = *(_QWORD *)v57;
        v59 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, DWORD, char, __int128 *))(**(_QWORD **)v57 + 32LL);
        v60 = (_QWORD *)to_wstring(lpSubKey, v143);
        v61 = v60[2];
        if ( v60[3] > 7u )
          v60 = (_QWORD *)*v60;
        *(_QWORD *)&v140 = v60;
        *((_QWORD *)&v140 + 1) = v61;
        LOBYTE(dwOptions[0]) = v137;
        v59(v58, v173, v37, 0, dwOptions[0], v139, &v140);
        std::wstring::~wstring(lpSubKey);
        v62 = v155;
        if ( v155 )
        {
          if ( _InterlockedExchangeAdd(v155 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
            if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
          }
        }
        v63 = (volatile signed __int32 *)*((_QWORD *)&v153 + 1);
        if ( *((_QWORD *)&v153 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v153 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
            if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
          }
        }
        _InterlockedCompareExchange(v152, 0, 1);
        std::wstring::~wstring(&v183);
        std::wstring::~wstring(&v180);
        std::wstring::~wstring(&v177);
        std::wstring::~wstring(&v174);
        std::vector<UxUpdateManager::UxUpdateIdentifier>::~vector<UxUpdateManager::UxUpdateIdentifier>(&v168);
        return 2149884174LL;
      }
      v162 = 0;
      v166 = 0;
      v64 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, unsigned int *, int *))(*(_QWORD *)v8 + 32LL))(
              v8,
              24,
              &v162,
              &v166);
      if ( v64 >= 0 )
      {
        if ( v166 )
        {
LABEL_75:
          v65 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 24);
          if ( v65 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2E1,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
              (const char *)(unsigned int)v65,
              dwOptions[0]);
          *(_QWORD *)&v140 = L"Preventing machine from sleeping: Reboot To Complete Install";
          *((_QWORD *)&v140 + 1) = 60;
          SystemInterface::Log<>(&v140);
          v167 = 0;
          v66 = SystemInterface::Service::GetSystem((__int64 *)&v153);
          v67 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v66 + 56LL))(*v66, &v154);
          (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v67 + 8LL))(*v67, &v167);
          v68 = v155;
          if ( v155 )
          {
            if ( _InterlockedExchangeAdd(v155 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
              if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
            }
          }
          v69 = (volatile signed __int32 *)*((_QWORD *)&v153 + 1);
          if ( *((_QWORD *)&v153 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v153 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
              if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
            }
          }
          try
          {
            memset(v170, 0, sizeof(v170));
            std::wstring::_Construct<1,wchar_t const *>(v170, L"Reboot To Complete Install");
            LOBYTE(v70) = 1;
            (*(void (__fastcall **)(__int64, _OWORD *, __int64))(*(_QWORD *)v167 + 8LL))(v167, v170, v70);
            std::wstring::~wstring(v170);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x2EB,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
              v71);
            v136 = v138;
            v145 = v144;
            v142 = v150;
            v8 = (volatile signed __int32 *)v156[0];
            v151 = hKey;
          }
          v72 = SystemInterface::Service::GetSystem((__int64 *)&v140);
          v73 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v72 + 72LL))(*v72, &v146);
          v74 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v73 + 24LL))(*v73);
          v75 = v147;
          if ( v147 )
          {
            if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
              if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
            }
          }
          v76 = (volatile signed __int32 *)*((_QWORD *)&v140 + 1);
          if ( *((_QWORD *)&v140 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v140 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
              if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
            }
          }
          if ( a3 )
          {
            *(_QWORD *)&v140 = L"Attributing this reboot to Enterprise Policy";
            *((_QWORD *)&v140 + 1) = 44;
            SystemInterface::Log<>(&v140);
            v77 = SystemInterface::Service::GetSystem((__int64 *)v170);
            v78 = (__int64 **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v77 + 32LL))(*v77, &v146);
            v79 = *v78;
            v80 = **v78;
            v81 = -1;
            do
              ++v81;
            while ( SystemInterface::Registry::ENTERPRISE_ATTRIBUTION_ROOT[v81] );
            v82 = -1;
            do
              ++v82;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v82] );
            *(_QWORD *)&v140 = SystemInterface::Registry::ENTERPRISE_ATTRIBUTION_ROOT;
            *((_QWORD *)&v140 + 1) = v81;
            v156[0] = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v156[1] = v82;
            (*(void (__fastcall **)(__int64 *, LPCWSTR *, _QWORD *, __int128 *))(v80 + 96))(v79, lpSubKey, v156, &v140);
            v83 = v147;
            if ( v147 )
            {
              if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
                if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
              }
            }
            v84 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
            if ( *((_QWORD *)&v170[0] + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
                if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
              }
            }
            hKey = 0;
            v85 = (const WCHAR *)lpSubKey;
            if ( *((_QWORD *)&v172 + 1) > 7u )
              v85 = lpSubKey[0];
            v86 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v85, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
            if ( v86 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x302,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                (const char *)v86,
                dwOptions[0]);
            if ( hKey )
              RegCloseKey(hKey);
            std::wstring::~wstring(lpSubKey);
          }
          else
          {
            *(_QWORD *)&v140 = L"Not attributing this reboot to Enterprise Policy";
            *((_QWORD *)&v140 + 1) = 48;
            SystemInterface::Log<>(&v140);
          }
          v87 = SystemInterface::Service::GetSystem(&v146);
          v88 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v87 + 48LL))(*v87, v170);
          v89 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v88 + 96LL))(*v88);
          v90 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
          if ( *((_QWORD *)&v170[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
              if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
            }
          }
          v91 = v147;
          if ( v147 )
          {
            if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
              if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
            }
          }
          if ( v89 )
          {
            *(_OWORD *)lpSubKey = 0;
            v172 = 0;
            std::wstring::_Construct<1,wchar_t const *>(lpSubKey, L"UpdateUX");
            LOBYTE(v92) = v137;
            UxUpdateManager::LogRebootInvokedEvent(v93, (unsigned int)&v168, (unsigned int)lpSubKey, v92, 1);
            std::wstring::~wstring(lpSubKey);
            v94 = SystemInterface::Service::GetSystem(&v146);
            v95 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v94 + 48LL))(*v94, v170);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v95 + 104LL))(*v95);
            v96 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
            if ( *((_QWORD *)&v170[0] + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
                if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
              }
            }
            v97 = v147;
            if ( v147 )
            {
              if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
                if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
              }
            }
            if ( v167 )
              (**(void (__fastcall ***)(__int64, __int64))v167)(v167, 1);
          }
          else
          {
            v98 = SystemInterface::Service::GetSystem(&v146);
            v99 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v98 + 64LL))(*v98, v170);
            v100 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v99 + 72LL))(*v99);
            v101 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
            if ( *((_QWORD *)&v170[0] + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v101)(v101);
                if ( !_InterlockedDecrement(v101 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v101 + 8LL))(v101);
              }
            }
            v102 = v147;
            if ( v147 )
            {
              if ( !_InterlockedDecrement(v147 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v102)(v102);
                if ( !_InterlockedDecrement(v102 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v102 + 8LL))(v102);
              }
            }
            if ( v100 )
            {
              v141 = 1;
              *(_QWORD *)dwOptions = 0;
              RtlPublishWnfStateData(WNF_CSHL_PENDING_SHUTDOWN_STARTED, 0, &v141, 4);
              Sleep(0xBB8u);
            }
            v105 = 0;
            if ( !v136 )
            {
              v103 = SystemInterface::Service::GetSystem(&v146);
              v144 = 1;
              v104 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v103 + 72LL))(*v103, v170);
              v145 = 3;
              v144 = 3;
              if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v104 + 128LL))(*v104) )
              {
                if ( (v142 & 0x800) == 0 || v74 )
                  v105 = 1;
              }
            }
            v106 = v145;
            if ( (v145 & 2) != 0 )
            {
              v106 = v145 & 0xFD;
              v107 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
              if ( *((_QWORD *)&v170[0] + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v107)(v107);
                  if ( _InterlockedExchangeAdd(v107 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v107 + 8LL))(v107);
                }
              }
            }
            if ( (v106 & 1) != 0 )
            {
              v108 = v147;
              if ( v147 )
              {
                if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v108)(v108);
                  if ( _InterlockedExchangeAdd(v108 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v108 + 8LL))(v108);
                }
              }
            }
            if ( v105 )
            {
              *(_QWORD *)&v140 = L"Rebooting with active user";
              *((_QWORD *)&v140 + 1) = 26;
              SystemInterface::Log<>(&v140);
              LOBYTE(v109) = a5 != 0;
              v110 = v142;
              v111 = v142 >> 13;
              LOBYTE(v111) = (v142 & 0x2000) != 0;
              v112 = UxUpdateManager::CommitAndRebootWithLoggedOnUser(v8, &v168, v111, v109);
              v113 = v112;
              if ( v112 )
              {
                v173 = v112;
                v114 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, _QWORD))(*(_QWORD *)v8 + 56LL))(
                         v8,
                         9,
                         v112);
                if ( v114 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x32F,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                    (const char *)(unsigned int)v114,
                    dwOptions[0]);
                v115 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, _QWORD))(*(_QWORD *)v8 + 56LL))(
                         v8,
                         24,
                         v162);
                if ( v115 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x332,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                    (const char *)(unsigned int)v115,
                    dwOptions[0]);
                LogDeferReasonTelemetryEventForAllUpdates(&v168, &v173, v110);
                *(_DWORD *)v151 = v173;
                v116 = SystemInterface::Service::GetSystem(&v146);
                v117 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v116 + 104LL))(*v116, v170);
                v118 = *(_QWORD *)v117;
                v119 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, REGSAM, __int128 *))(**(_QWORD **)v117 + 32LL);
                v120 = (_QWORD *)to_wstring(lpSubKey, v143);
                v121 = v120[2];
                if ( v120[3] > 7u )
                  v120 = (_QWORD *)*v120;
                *(_QWORD *)&v140 = v120;
                *((_QWORD *)&v140 + 1) = v121;
                LOBYTE(samDesired) = v139;
                LOBYTE(dwOptions[0]) = v137;
                v119(v118, v173, v142, 0, *(_QWORD *)dwOptions, samDesired, &v140);
                std::wstring::~wstring(lpSubKey);
                v122 = (volatile signed __int32 *)*((_QWORD *)&v170[0] + 1);
                if ( *((_QWORD *)&v170[0] + 1) )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v170[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v122)(v122);
                    if ( _InterlockedExchangeAdd(v122 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v122 + 8LL))(v122);
                  }
                }
                v123 = v147;
                if ( v147 )
                {
                  if ( _InterlockedExchangeAdd(v147 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v123)(v123);
                    if ( _InterlockedExchangeAdd(v123 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v123 + 8LL))(v123);
                  }
                }
                if ( v167 )
                  (**(void (__fastcall ***)(__int64, __int64))v167)(v167, 1);
                _InterlockedCompareExchange(v152, 0, 1);
                std::wstring::~wstring(&v183);
                std::wstring::~wstring(&v180);
                std::wstring::~wstring(&v177);
                std::wstring::~wstring(&v174);
                std::vector<UxUpdateManager::UxUpdateIdentifier>::~vector<UxUpdateManager::UxUpdateIdentifier>(&v168);
                return (unsigned int)(-(v113 != 0x2000) - 2145083108);
              }
            }
            else
            {
              *(_QWORD *)&v140 = L"Rebooting with inactive user";
              *((_QWORD *)&v140 + 1) = 28;
              SystemInterface::Log<>(&v140);
              LOBYTE(v124) = a5 != 0;
              UxUpdateManager::CommitAndReboot(v125, &v168, v124);
            }
            if ( v167 )
              (**(void (__fastcall ***)(__int64, __int64))v167)(v167, 1);
          }
          _InterlockedCompareExchange(v152, 0, 1);
          std::wstring::~wstring(&v183);
          std::wstring::~wstring(&v180);
          std::wstring::~wstring(&v177);
          std::wstring::~wstring(&v174);
          std::vector<UxUpdateManager::UxUpdateIdentifier>::~vector<UxUpdateManager::UxUpdateIdentifier>(&v168);
          return 0;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2DD,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)(unsigned int)v64,
          dwOptions[0]);
      }
      v162 = 0;
      goto LABEL_75;
    }
    catch ( ... )
    {
      v126 = SystemInterface::Service::GetSystem(&v154);
      v127 = std::shared_ptr<SystemInterface::Service::System>::operator-><SystemInterface::Service::System,0>(v126);
      v128 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v127 + 64LL))(v127, v170);
      v129 = std::shared_ptr<SystemInterface::Service::System>::operator-><SystemInterface::Service::System,0>(v128);
      v130 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v129 + 72LL))(v129);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v170);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v154);
      if ( v130 )
      {
        v141 = 2;
        wil::wnf_publish_nothrow<enum tagCShellRestartUXOptions>(v131, &v141);
      }
      v132 = wil::ResultFromCaughtException(v131);
      UxUpdateManager::LogRebootFailedEvent(v133, (unsigned int)&v168, v132, v173, v137, v139, v143);
      throw;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x361,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18003b5e0  mov     [rsp+arg_10], r8d
0x18003b5e5  push    rbx
0x18003b5e6  push    rsi
0x18003b5e7  push    rdi
0x18003b5e8  push    r12
0x18003b5ea  push    r13
0x18003b5ec  push    r14
0x18003b5ee  push    r15
0x18003b5f0  sub     rsp, 2A0h
0x18003b5f7  mov     rax, cs:__security_cookie
0x18003b5fe  xor     rax, rsp
0x18003b601  mov     [rsp+2D8h+var_48], rax
0x18003b609  mov     rax, r9
0x18003b60c  mov     [rsp+2D8h+var_228], rax
0x18003b614  mov     r15d, edx
0x18003b617  mov     r13, rcx
0x18003b61a  mov     [rsp+2D8h+var_1F8], rcx
0x18003b622  mov     [rsp+2D8h+hKey], rax
0x18003b62a  xor     edi, edi
0x18003b62c  mov     ecx, edi
0x18003b62e  mov     [rsp+2D8h+var_258], ecx
0x18003b635  mov     [rsp+2D8h+var_25C], ecx
0x18003b639  lea     rcx, [rsp+2D8h+var_278]
0x18003b63e  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003b643  nop
0x18003b644  mov     rcx, [rax]
0x18003b647  mov     rax, [rcx]
0x18003b64a  lea     rdx, [rsp+2D8h+var_240]
0x18003b652  mov     rax, [rax+38h]
0x18003b656  call    _guard_dispatch_icall
0x18003b65b  nop
0x18003b65c  mov     rcx, [rax]
0x18003b65f  mov     rax, [rcx]
0x18003b662  mov     rax, [rax+10h]
0x18003b666  call    _guard_dispatch_icall
0x18003b66b  mov     [rsp+2D8h+var_287], al
0x18003b66f  mov     [rsp+2D8h+var_284], al
0x18003b673  mov     rsi, qword ptr [rsp+2D8h+var_240+8]
0x18003b67b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003b67f  test    rsi, rsi
0x18003b682  jz      short loc_18003B6B8
0x18003b684  mov     eax, ebx
0x18003b686  lock xadd [rsi+8], eax
0x18003b68b  add     eax, ebx
0x18003b68d  jnz     short loc_18003B6B8
0x18003b68f  mov     rax, [rsi]
0x18003b692  mov     rcx, rsi
0x18003b695  mov     rax, [rax]
0x18003b698  call    _guard_dispatch_icall
0x18003b69d  mov     eax, ebx
0x18003b69f  lock xadd [rsi+0Ch], eax
0x18003b6a4  add     eax, ebx
0x18003b6a6  jnz     short loc_18003B6B8
0x18003b6a8  mov     rax, [rsi]
0x18003b6ab  mov     rcx, rsi
0x18003b6ae  mov     rax, [rax+8]
0x18003b6b2  call    _guard_dispatch_icall
0x18003b6b7  nop
0x18003b6b8  mov     rsi, qword ptr [rsp+2D8h+var_278+8]
0x18003b6bd  test    rsi, rsi
0x18003b6c0  jz      short loc_18003B6F5
0x18003b6c2  mov     eax, ebx
0x18003b6c4  lock xadd [rsi+8], eax
0x18003b6c9  add     eax, ebx
0x18003b6cb  jnz     short loc_18003B6F5
0x18003b6cd  mov     rax, [rsi]
0x18003b6d0  mov     rcx, rsi
0x18003b6d3  mov     rax, [rax]
0x18003b6d6  call    _guard_dispatch_icall
0x18003b6db  mov     eax, ebx
0x18003b6dd  lock xadd [rsi+0Ch], eax
0x18003b6e2  add     eax, ebx
0x18003b6e4  jnz     short loc_18003B6F5
0x18003b6e6  mov     rax, [rsi]
0x18003b6e9  mov     rcx, rsi
0x18003b6ec  mov     rax, [rax+8]
0x18003b6f0  call    _guard_dispatch_icall
0x18003b6f5  xorps   xmm0, xmm0
0x18003b6f8  xor     eax, eax
0x18003b6fa  movups  [rsp+2D8h+var_130], xmm0
0x18003b702  mov     [rsp+2D8h+var_120], rax
0x18003b70a  lea     rdx, [rsp+2D8h+var_130]
0x18003b712  call    ?GetRestartRequiredUpdateIdentifiers@UxUpdateManager@@AEAA?AV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@XZ; UxUpdateManager::GetRestartRequiredUpdateIdentifiers(void)
0x18003b717  nop
0x18003b718  mov     [rsp+2D8h+var_144], edi
0x18003b71f  mov     [rsp+2D8h+var_148], edi
0x18003b726  mov     rax, [r13+0]
0x18003b72a  lea     r9, [rsp+2D8h+var_148]
0x18003b732  lea     r8, [rsp+2D8h+var_144]
0x18003b73a  mov     edx, 12h
0x18003b73f  mov     rcx, r13
0x18003b742  mov     rax, [rax+20h]
0x18003b746  call    _guard_dispatch_icall
0x18003b74b  mov     esi, eax
0x18003b74d  test    eax, eax
0x18003b74f  jns     short loc_18003B782
0x18003b751  mov     rcx, [rsp+2D8h]; this
0x18003b759  mov     r9d, eax; char *
0x18003b75c  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003b763  mov     edx, 28Fh; void *
0x18003b768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b76d  nop
0x18003b76e  lea     rcx, [rsp+2D8h+var_130]
0x18003b776  call    ??1?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@QEAA@XZ; std::vector<UxUpdateManager::UxUpdateIdentifier>::~vector<UxUpdateManager::UxUpdateIdentifier>(void)
0x18003b77b  mov     eax, esi
0x18003b77d  jmp     loc_18003CBB4
0x18003b782  mov     eax, [rsp+2D8h+var_148]
0x18003b789  neg     eax
0x18003b78b  sbb     r14d, r14d
0x18003b78e  and     r14d, [rsp+2D8h+var_144]
0x18003b796  mov     [rsp+2D8h+var_260], r14d
0x18003b79b  lea     rcx, [rsp+2D8h+var_278]
0x18003b7a0  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003b7a5  nop
0x18003b7a6  mov     rcx, [rax]
0x18003b7a9  mov     rax, [rcx]
0x18003b7ac  lea     rdx, [rsp+2D8h+var_240]
0x18003b7b4  mov     rax, [rax]
0x18003b7b7  call    _guard_dispatch_icall
0x18003b7bc  nop
0x18003b7bd  mov     rcx, [rax]
0x18003b7c0  mov     rax, [rcx]
0x18003b7c3  mov     rax, [rax+10h]
0x18003b7c7  call    _guard_dispatch_icall
0x18003b7cc  test    al, al
0x18003b7ce  setz    r12b
0x18003b7d2  mov     [rsp+2D8h+var_285], r12b
0x18003b7d7  mov     rsi, qword ptr [rsp+2D8h+var_240+8]
0x18003b7df  test    rsi, rsi
0x18003b7e2  jz      short loc_18003B818
0x18003b7e4  mov     eax, ebx
0x18003b7e6  lock xadd [rsi+8], eax
0x18003b7eb  add     eax, ebx
0x18003b7ed  jnz     short loc_18003B818
0x18003b7ef  mov     rax, [rsi]
0x18003b7f2  mov     rcx, rsi
0x18003b7f5  mov     rax, [rax]
0x18003b7f8  call    _guard_dispatch_icall
0x18003b7fd  mov     eax, ebx
0x18003b7ff  lock xadd [rsi+0Ch], eax
0x18003b804  add     eax, ebx
0x18003b806  jnz     short loc_18003B818
0x18003b808  mov     rax, [rsi]
0x18003b80b  mov     rcx, rsi
0x18003b80e  mov     rax, [rax+8]
0x18003b812  call    _guard_dispatch_icall
0x18003b817  nop
0x18003b818  mov     rsi, qword ptr [rsp+2D8h+var_278+8]
0x18003b81d  test    rsi, rsi
0x18003b820  jz      short loc_18003B855
0x18003b822  mov     eax, ebx
0x18003b824  lock xadd [rsi+8], eax
0x18003b829  add     eax, ebx
0x18003b82b  jnz     short loc_18003B855
0x18003b82d  mov     rax, [rsi]
0x18003b830  mov     rcx, rsi
0x18003b833  mov     rax, [rax]
0x18003b836  call    _guard_dispatch_icall
0x18003b83b  mov     eax, ebx
0x18003b83d  lock xadd [rsi+0Ch], eax
0x18003b842  add     eax, ebx
0x18003b844  jnz     short loc_18003B855
0x18003b846  mov     rax, [rsi]
0x18003b849  mov     rcx, rsi
0x18003b84c  mov     rax, [rax+8]
0x18003b850  call    _guard_dispatch_icall
0x18003b855  mov     [rsp+2D8h+var_D8], edi
0x18003b85c  xorps   xmm0, xmm0
0x18003b85f  movups  [rsp+2D8h+var_D0], xmm0
0x18003b867  mov     [rsp+2D8h+var_C0], rdi
0x18003b86f  mov     eax, 7
0x18003b874  mov     [rsp+2D8h+var_B8], rax
0x18003b87c  mov     word ptr [rsp+2D8h+var_D0], di
0x18003b884  movups  [rsp+2D8h+var_B0], xmm0
0x18003b88c  mov     [rsp+2D8h+var_A0], rdi
0x18003b894  mov     [rsp+2D8h+var_98], rax
0x18003b89c  mov     word ptr [rsp+2D8h+var_B0], di
0x18003b8a4  movups  [rsp+2D8h+var_90], xmm0
0x18003b8ac  mov     [rsp+2D8h+var_80], rdi
0x18003b8b4  mov     [rsp+2D8h+var_78], rax
0x18003b8bc  mov     word ptr [rsp+2D8h+var_90], di
0x18003b8c4  movups  [rsp+2D8h+var_70], xmm0
0x18003b8cc  mov     [rsp+2D8h+var_60], rdi
0x18003b8d4  mov     [rsp+2D8h+var_58], rax
0x18003b8dc  mov     word ptr [rsp+2D8h+var_70], di
0x18003b8e4  mov     r9d, r14d
0x18003b8e7  mov     r8b, r12b
0x18003b8ea  lea     rdx, [rsp+2D8h+var_130]
0x18003b8f2  mov     rcx, r13
0x18003b8f5  call    ?LogInitiatingRebootEvent@UxUpdateManager@@AEAAXAEBV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@_NW4tagUXRebootState@@@Z; UxUpdateManager::LogInitiatingRebootEvent(std::vector<UxUpdateManager::UxUpdateIdentifier> const &,bool,tagUXRebootState)
0x18003b8fa  lea     rdx, [r13+10h]
0x18003b8fe  mov     [rsp+2D8h+var_220], rdx
0x18003b906  mov     rcx, [rsp+2D8h]; this
0x18003b90e  xor     eax, eax
0x18003b910  lea     r12d, [rax+1]
0x18003b914  lock cmpxchg [rdx], r12d
0x18003b919  cmp     eax, r12d
0x18003b91c  jz      loc_18003CBD7
0x18003b922  xorps   xmm0, xmm0
0x18003b925  movups  [rsp+2D8h+var_240], xmm0
0x18003b92d  mov     qword ptr [rsp+2D8h+var_240], r13
0x18003b935  mov     byte ptr [rsp+2D8h+var_240+8], r12b
0x18003b93d  call    ?DidUXRebootTaskWakeUpDevice@UxUpdateManager@@AEAA_NXZ; UxUpdateManager::DidUXRebootTaskWakeUpDevice(void)
0x18003b942  mov     r14b, al
0x18003b945  lea     rcx, [rsp+2D8h+var_250]
0x18003b94d  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003b952  nop
0x18003b953  mov     rcx, [rax]
0x18003b956  mov     rax, [rcx]
0x18003b959  lea     rdx, [rsp+2D8h+var_278]
0x18003b95e  mov     rax, [rax]
0x18003b961  call    _guard_dispatch_icall
0x18003b966  nop
0x18003b967  mov     rcx, [rax]
0x18003b96a  mov     rax, [rcx]
0x18003b96d  mov     rax, [rax+8]
0x18003b971  call    _guard_dispatch_icall
0x18003b976  mov     [rsp+2D8h+var_288], al
0x18003b97a  mov     [rsp+2D8h+var_286], al
0x18003b97e  mov     rsi, qword ptr [rsp+2D8h+var_278+8]
0x18003b983  test    rsi, rsi
0x18003b986  jz      short loc_18003B9BC
0x18003b988  mov     ecx, ebx
0x18003b98a  lock xadd [rsi+8], ecx
0x18003b98f  add     ecx, ebx
0x18003b991  jnz     short loc_18003B9BC
0x18003b993  mov     rax, [rsi]
0x18003b996  mov     rcx, rsi
0x18003b999  mov     rax, [rax]
0x18003b99c  call    _guard_dispatch_icall
0x18003b9a1  mov     eax, ebx
0x18003b9a3  lock xadd [rsi+0Ch], eax
0x18003b9a8  add     eax, ebx
0x18003b9aa  jnz     short loc_18003B9BC
0x18003b9ac  mov     rax, [rsi]
0x18003b9af  mov     rcx, rsi
0x18003b9b2  mov     rax, [rax+8]
0x18003b9b6  call    _guard_dispatch_icall
0x18003b9bb  nop
0x18003b9bc  mov     rsi, [rsp+2D8h+var_248]
0x18003b9c4  test    rsi, rsi
0x18003b9c7  jz      short loc_18003B9FC
0x18003b9c9  mov     eax, ebx
0x18003b9cb  lock xadd [rsi+8], eax
0x18003b9d0  add     eax, ebx
0x18003b9d2  jnz     short loc_18003B9FC
0x18003b9d4  mov     rax, [rsi]
0x18003b9d7  mov     rcx, rsi
0x18003b9da  mov     rax, [rax]
0x18003b9dd  call    _guard_dispatch_icall
0x18003b9e2  mov     eax, ebx
0x18003b9e4  lock xadd [rsi+0Ch], eax
0x18003b9e9  add     eax, ebx
0x18003b9eb  jnz     short loc_18003B9FC
0x18003b9ed  mov     rax, [rsi]
0x18003b9f0  mov     rcx, rsi
0x18003b9f3  mov     rax, [rax+8]
0x18003b9f7  call    _guard_dispatch_icall
0x18003b9fc  mov     sil, [rsp+2D8h+var_288]
0x18003ba01  test    sil, sil
0x18003ba04  jnz     short loc_18003BA41
0x18003ba06  test    r14b, r14b
0x18003ba09  jz      short loc_18003BA41
0x18003ba0b  call    cs:__imp_IsSystemResumeAutomatic
0x18003ba11  test    eax, eax
0x18003ba13  jz      short loc_18003BA41
0x18003ba15  lea     rax, aMachineWokeUpA; "Machine woke up automatically to run re"...
0x18003ba1c  mov     qword ptr [rsp+2D8h+var_278], rax
0x18003ba21  mov     qword ptr [rsp+2D8h+var_278+8], 47h ; 'G'
0x18003ba2a  lea     rcx, [rsp+2D8h+var_278]
0x18003ba2f  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x18003ba34  mov     sil, r12b
0x18003ba37  mov     [rsp+2D8h+var_288], r12b
0x18003ba3c  mov     [rsp+2D8h+var_286], r12b
0x18003ba41  mov     eax, 0FFFFFFFBh
0x18003ba46  test    sil, sil
0x18003ba49  cmovz   eax, r15d
0x18003ba4d  mov     [rsp+2D8h+var_264], eax
0x18003ba51  mov     r15d, eax
0x18003ba54  mov     [rsp+2D8h+var_230], eax
0x18003ba5b  lea     rcx, [rsp+2D8h+var_218]
0x18003ba63  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003ba68  nop
0x18003ba69  mov     rcx, [rax]
0x18003ba6c  mov     rax, [rcx]
0x18003ba6f  lea     rdx, [rsp+2D8h+var_250]
0x18003ba77  mov     rax, [rax+28h]
0x18003ba7b  call    _guard_dispatch_icall
0x18003ba80  nop
0x18003ba81  mov     r11, [rax]
0x18003ba84  mov     rax, [r11]
0x18003ba87  mov     rsi, [rax+38h]
0x18003ba8b  mov     [rsp+2D8h+var_268], 28h ; '('
0x18003ba93  xor     r8d, r8d
0x18003ba96  lea     r14, qword_1801005C8
0x18003ba9d  mov     rdx, r14
0x18003baa0  lea     rcx, aMinimumbattery; "MinimumBatteryLevel"
0x18003baa7  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003baac  cmp     rax, r14
0x18003baaf  jz      loc_18003CBEF
  ... truncated ...
```
