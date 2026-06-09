# ReplicationCoordinator::ValidateAndUpdateReplicationSettings(IGroupRepository *,int)

- ea: `0x14020d218`
- end: `0x14020ee20`
- name: `?ValidateAndUpdateReplicationSettings@ReplicationCoordinator@@QEAAJPEAUIGroupRepository@@H@Z`
- size: `7176`
- prototype: `__int64 __fastcall(ReplicationCoordinator *__hidden this, struct IGroupRepository *, int)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1405f95c4`

## callees

- `0x140022640`
- `0x140041630`
- `0x1400419e4`
- `0x140043dc8`
- `0x14005c630`
- `0x1400634f4`
- `0x140064a48`
- `0x14006cc70`
- `0x140071534`
- `0x140073cd0`
- `0x14007bb80`
- `0x14008fc80`
- `0x1400916d8`
- `0x1400df0d8`
- `0x14017902c`
- `0x1401879a4`
- `0x140188e18`
- `0x14019f188`
- `0x1401cc838`
- `0x1401cedfc`
- `0x14020c060`
- `0x14020d218`
- `0x1402407a4`
- `0x14029db54`
- `0x1402a05e4`
- `0x1402b6d28`
- `0x1403b49bc`
- `0x1404713a0`
- `0x1404828e0`
- `0x140486541`
- `0x1404d5640`
- `0x140613b6c`
- `0x14061595c`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14020e457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14020e457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14020ecfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14020ecfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14020d36e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14020d36e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d331`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d3ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d3fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d616`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d7fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e26d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e30d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e3ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e40c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d331`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d3ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d3fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d616`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020d7fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e26d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e30d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e3ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14020e40c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d3db`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d62d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d650`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d822`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d919`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e332`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e397`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e423`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e444`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020ecd8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d3db`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d62d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d650`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d822`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020d919`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e332`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e397`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e423`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020e444`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14020ecd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020d5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020d7ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020e29a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020d5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020d7ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14020e29a`
- `RPCRT4!UuidCompare` at `0x14020e076`
- `RPCRT4!UuidCompare` at `0x14020e240`
- `RPCRT4!UuidCompare` at `0x14020e076`
- `RPCRT4!UuidCompare` at `0x14020e240`

## string_xrefs

- `0x14020d70e`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x14020d8ed`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x14020e4af`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall ReplicationCoordinator::ValidateAndUpdateReplicationSettings(
        ReplicationCoordinator *this,
        struct IGroupRepository *a2,
        int a3)
{
  ReplicationCoordinator *v3; // r13
  __m128i si128; // xmm6
  _QWORD *v5; // r12
  const char *v6; // r9
  char v7; // al
  char v8; // bl
  DWORD v9; // edi
  const char *v10; // r9
  struct IGroupRepository *v11; // rbx
  int v12; // eax
  int v13; // eax
  volatile signed __int32 *v14; // r13
  signed __int32 v15; // eax
  signed __int32 v16; // ebx
  DWORD v17; // esi
  unsigned int Value; // edi
  unsigned int ReplicationPhaseFlags; // ebx
  signed __int32 v20; // edx
  signed __int32 *v21; // rdi
  signed __int32 v22; // eax
  signed __int32 v23; // ebx
  char v24; // al
  char v25; // bl
  DWORD v26; // esi
  unsigned int v27; // r13d
  signed __int32 v28; // edx
  unsigned int v29; // esi
  unsigned __int64 i; // rbx
  __int128 *p_Src; // rdx
  const unsigned __int16 *v32; // rdx
  __int128 *v33; // rbx
  __int64 v34; // rcx
  UUID *j; // rbx
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rax
  unsigned __int64 v39; // rcx
  unsigned __int64 k; // rdi
  unsigned __int16 **v41; // rdx
  int v42; // ebx
  const unsigned __int16 *v43; // rdx
  __int128 *m; // rbx
  int v45; // ebx
  int IsDebugTraceEnabled; // eax
  const unsigned __int16 *v47; // rdx
  int v48; // ebx
  int v49; // eax
  const unsigned __int16 *v50; // rdx
  const char *v51; // r9
  unsigned __int32 *v52; // rbx
  DWORD CurrentThreadId; // edi
  __int64 v54; // r8
  unsigned __int32 v55; // eax
  unsigned __int32 v56; // edx
  char v57; // al
  char v58; // di
  DWORD v59; // esi
  unsigned int v60; // r13d
  int v61; // eax
  const char *v62; // r9
  DWORD v63; // edi
  unsigned int v64; // ebx
  int updated; // eax
  __int64 v66; // rax
  unsigned __int64 v67; // rsi
  Vml::VmComMemStreamBase *v68; // rbx
  int v69; // eax
  __int64 v70; // rdx
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  _QWORD *v73; // rax
  __int64 v74; // rdx
  int v75; // eax
  __int64 v76; // rax
  unsigned __int64 v77; // rdi
  Vml::VmComMemStreamBase *v78; // rbx
  int v79; // eax
  int v80; // eax
  struct IGroupRepository *v81; // rbx
  int v82; // eax
  int v83; // eax
  int v84; // eax
  int v85; // eax
  const struct Vml::ExceptionTraceParameters *v86; // r8
  unsigned int v87; // r12d
  unsigned int v89; // [rsp+20h] [rbp-298h]
  int HResultFromThrownExceptionAndTrace; // [rsp+30h] [rbp-288h]
  UUID *p_Uuid2; // [rsp+48h] [rbp-270h] BYREF
  unsigned __int16 **v94; // [rsp+50h] [rbp-268h]
  DWORD dwTlsIndex; // [rsp+58h] [rbp-260h]
  union _LARGE_INTEGER v96; // [rsp+60h] [rbp-258h]
  unsigned __int64 v97; // [rsp+68h] [rbp-250h] BYREF
  unsigned __int64 v98; // [rsp+70h] [rbp-248h] BYREF
  struct IGroupRepository *v99; // [rsp+78h] [rbp-240h] BYREF
  DWORD v100; // [rsp+80h] [rbp-238h]
  int v101; // [rsp+84h] [rbp-234h]
  unsigned int v102; // [rsp+88h] [rbp-230h]
  char v103; // [rsp+8Ch] [rbp-22Ch]
  DWORD v104; // [rsp+90h] [rbp-228h]
  unsigned int v105; // [rsp+94h] [rbp-224h]
  int v106; // [rsp+98h] [rbp-220h]
  char v107; // [rsp+9Ch] [rbp-21Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-218h]
  char v109; // [rsp+A8h] [rbp-210h]
  char *v110[2]; // [rsp+B0h] [rbp-208h] BYREF
  char *v111[2]; // [rsp+C0h] [rbp-1F8h] BYREF
  struct IGroupRepository *v112; // [rsp+D0h] [rbp-1E8h]
  LPVOID lpTlsValue; // [rsp+D8h] [rbp-1E0h]
  char *v114; // [rsp+E0h] [rbp-1D8h]
  char *v115; // [rsp+E8h] [rbp-1D0h]
  _QWORD *v116; // [rsp+F0h] [rbp-1C8h]
  char v117[8]; // [rsp+F8h] [rbp-1C0h] BYREF
  char v118[8]; // [rsp+100h] [rbp-1B8h] BYREF
  char v119[8]; // [rsp+108h] [rbp-1B0h] BYREF
  char v120[8]; // [rsp+110h] [rbp-1A8h] BYREF
  _OWORD v121[2]; // [rsp+118h] [rbp-1A0h] BYREF
  __int64 v122; // [rsp+138h] [rbp-180h] BYREF
  RPC_STATUS Status[2]; // [rsp+140h] [rbp-178h] BYREF
  unsigned __int16 *v124[2]; // [rsp+148h] [rbp-170h] BYREF
  __m128i v125; // [rsp+158h] [rbp-160h]
  unsigned __int16 *v126[2]; // [rsp+168h] [rbp-150h] BYREF
  __m128i v127; // [rsp+178h] [rbp-140h]
  __int128 Src; // [rsp+188h] [rbp-130h] BYREF
  __m128i v129; // [rsp+198h] [rbp-120h]
  __int128 v130; // [rsp+1A8h] [rbp-110h] BYREF
  __int64 v131; // [rsp+1B8h] [rbp-100h] BYREF
  __int128 v132; // [rsp+1C0h] [rbp-F8h] BYREF
  __int64 v133; // [rsp+1D0h] [rbp-E8h]
  UUID Uuid2; // [rsp+1E0h] [rbp-D8h] BYREF
  UUID v135; // [rsp+1F0h] [rbp-C8h] BYREF
  unsigned __int64 v136; // [rsp+200h] [rbp-B8h] BYREF
  struct Vml::VmGuid *v137[2]; // [rsp+210h] [rbp-A8h] BYREF
  __int128 v138; // [rsp+220h] [rbp-98h] BYREF
  __int128 v139; // [rsp+230h] [rbp-88h] BYREF
  __int64 v140; // [rsp+240h] [rbp-78h]
  unsigned __int64 v141; // [rsp+248h] [rbp-70h] BYREF
  __int128 v142; // [rsp+250h] [rbp-68h] BYREF
  __int64 v143; // [rsp+260h] [rbp-58h]
  _BYTE v144[16]; // [rsp+268h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v112 = a2;
  v3 = this;
  v99 = 0;
  Vml::VmGuid::Assign((Vml::VmGuid *)v144, L"82CEFEFE-9D05-4D0E-A9FE-6C0A1D33299F");
  v131 = 0;
  v122 = 0;
  v98 = 0;
  v97 = 0;
  v96.QuadPart = 0;
  v132 = 0;
  v133 = 0;
  v139 = 0;
  v140 = 0;
  v141 = 0;
  v121[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v121[1] = si128;
  LOWORD(v121[0]) = 0;
  v5 = (_QWORD *)((char *)v3 + 96);
  v114 = (char *)v3 + 96;
  v115 = (char *)v3 + 120;
  if ( *((_QWORD *)v3 + 15) > 7u )
    v5 = (_QWORD *)*v5;
  v116 = v5;
  ReplicationCoordinator::GetName(v3, v121);
  if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 0x1E) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6995,
      (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
      v6);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v3 + 1472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 1472));
  v7 = 1;
  v109 = 1;
  try
  {
LABEL_6:
    if ( v7 )
    {
      v8 = 1;
      v103 = 1;
      v9 = ReplicationCoordinator::gm_RcTlsIndex;
      dwTlsIndex = ReplicationCoordinator::gm_RcTlsIndex;
      v100 = ReplicationCoordinator::gm_RcTlsIndex;
      lpTlsValue = TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      v101 = (int)lpTlsValue;
      v102 = (unsigned int)lpTlsValue | 1;
      TlsSetValue(v9, (LPVOID)((unsigned int)lpTlsValue | 1));
      while ( 1 )
      {
        if ( !v8 )
        {
          TlsSetValue(dwTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
          v7 = 0;
          v109 = 0;
          goto LABEL_6;
        }
        if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x6997,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            v10);
        if ( (unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 64) )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            v89 = (unsigned int)v5;
            VmlDebugTraceWithError(16808, &off_14091DD88, 2147500036LL);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6997,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80004004LL,
            v89);
        }
        *(_OWORD *)v110 = 0;
        v11 = v112;
        GroupRepositoryAutoLock::GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v110, v112, 0);
        if ( SLODWORD(v110[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69A0,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)LODWORD(v110[1]),
            v89);
        v12 = (*(__int64 (__fastcall **)(struct IGroupRepository *, _BYTE *, __int64 *))(*(_QWORD *)v11 + 312LL))(
                v11,
                v144,
                &v122);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69A5,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v12,
            v89);
        (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)v3 + 98) + 88LL))(
          *((_QWORD *)v3 + 98),
          &v139,
          0);
        if ( *((_QWORD *)&v139 + 1) != (_QWORD)v139 )
        {
          v13 = *((_DWORD *)v3 + 198);
          if ( a3 )
          {
            if ( v13 != 1 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DDA0, 2147947423LL);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69B7,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v89);
            }
            v14 = (volatile signed __int32 *)((char *)v3 + 1424);
            v15 = _InterlockedCompareExchange(v14, 4, 0);
            v16 = v15;
            if ( v15 )
            {
              if ( (v15 & 1) != 0 && *((_DWORD *)v14 + 1) == GetCurrentThreadId() )
              {
                _InterlockedAdd(v14 + 2, 1u);
              }
              else
              {
                do
                {
                  while ( (v16 & 1) != 0 )
                  {
                    if ( !(unsigned int)RrwpLockWait(v14, 0xFFFFFFFFLL, 0) )
                      wil::details::in1diag3::Throw_Win32(
                        retaddr,
                        (void *)0x249,
                        (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                        (const char *)0x102,
                        v89);
                    _m_prefetchw((const void *)v14);
                    v16 = *v14;
                  }
                  v20 = v16;
                  v16 = _InterlockedCompareExchange(v14, v16 + 4, v16);
                }
                while ( v16 != v20 );
              }
            }
            v17 = ReplicationCoordinator::gm_RcTlsIndex;
            Value = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
            TlsSetValue(v17, (LPVOID)(Value | 8LL));
            ReplicationPhaseFlags = ReplicationPhaseManager::GetReplicationPhaseFlags(*((ReplicationPhaseManager **)this
                                                                                      + 97));
            TlsSetValue(v17, (LPVOID)Value);
            RrwLockRelease(v14);
            if ( ReplicationPhaseFlags != 0x10000 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DDB8, 2147947423LL);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69C8,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v89);
            }
          }
          else
          {
            if ( v13 != 2 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DDD0, 2147947423LL);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69D6,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v89);
            }
            v21 = (signed __int32 *)((char *)v3 + 1424);
            v22 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 356, 4, 0);
            v23 = v22;
            if ( v22 )
            {
              if ( (v22 & 1) != 0 && *((_DWORD *)v3 + 357) == GetCurrentThreadId() )
              {
                _InterlockedAdd((volatile signed __int32 *)v3 + 358, 1u);
              }
              else
              {
                do
                {
                  while ( (v23 & 1) != 0 )
                  {
                    if ( !(unsigned int)RrwpLockWait((char *)v3 + 1424, 0xFFFFFFFFLL, 0) )
                      wil::details::in1diag3::Throw_Win32(
                        retaddr,
                        (void *)0x249,
                        (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                        (const char *)0x102,
                        v89);
                    _m_prefetchw(v21);
                    v23 = *v21;
                  }
                  v28 = v23;
                  v23 = _InterlockedCompareExchange(v21, v23 + 4, v23);
                }
                while ( v23 != v28 );
              }
            }
            *(_QWORD *)&v130 = (char *)v3 + 1424;
            v24 = 1;
            BYTE8(v130) = 1;
            while ( v24 )
            {
              v25 = 1;
              v107 = 1;
              v26 = ReplicationCoordinator::gm_RcTlsIndex;
              v104 = ReplicationCoordinator::gm_RcTlsIndex;
              v27 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
              v105 = v27;
              v106 = v27 | 8;
              TlsSetValue(v26, (LPVOID)(v27 | 8));
              while ( v25 )
              {
                if ( !(unsigned int)ReplicationPhaseManager::IsWaitingForIr(*((ReplicationPhaseManager **)this + 97)) )
                {
                  if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
                  {
                    v89 = (unsigned int)v5;
                    VmlDebugTraceWithError(16808, &off_14091DDE8, 2147947423LL);
                  }
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x69E4,
                    (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                    (const char *)0x8007139FLL,
                    v89);
                }
                v25 = 0;
                v107 = 0;
              }
              TlsSetValue(v26, (LPVOID)v27);
              v24 = 0;
              BYTE8(v130) = 0;
            }
            RrwLockRelease(v21);
          }
          v29 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v122
                                                                                                 + 168LL))(
                  v122,
                  L"topology/vm/count",
                  &v141);
          if ( (v29 & 0x80000000) != 0 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v89 = (unsigned int)v5;
              VmlDebugTraceWithError(16808, &off_14091DE00, v29);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x69F6,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)v29,
              v89);
          }
          for ( i = 0; i < v141; ++i )
          {
            Src = 0;
            v129 = si128;
            LOWORD(Src) = 0;
            *(_OWORD *)v124 = 0;
            v125 = si128;
            LOWORD(v124[0]) = 0;
            v135 = 0;
            Vml::FormatString(&Src, (wchar_t *)L"topology/vm/vm%llu/guid");
            p_Src = &Src;
            if ( v129.m128i_i64[1] > 7uLL )
              p_Src = (__int128 *)Src;
            v29 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int16 **))(*(_QWORD *)v122 + 152LL))(
                    v122,
                    p_Src,
                    v124);
            if ( (v29 & 0x80000000) != 0 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DCA8, v29);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A10,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v29,
                v89);
            }
            v32 = (const unsigned __int16 *)v124;
            if ( v125.m128i_i64[1] > 7uLL )
              v32 = v124[0];
            Vml::VmGuid::Assign((Vml::VmGuid *)&v135, v32);
            VmGuidSet::insert(&v132, v117, *((_QWORD *)&v132 + 1), &v135);
            std::wstring::_Tidy_deallocate(v124);
            std::wstring::_Tidy_deallocate(&Src);
          }
          v33 = (__int128 *)v139;
          v34 = *((_QWORD *)&v132 + 1);
          while ( v33 != *((__int128 **)&v139 + 1) )
          {
            v73 = (_QWORD *)VmGuidSet::find(&v132, v120, v33);
            v34 = *((_QWORD *)&v132 + 1);
            if ( *v73 == *((_QWORD *)&v132 + 1) )
            {
              v130 = *v33;
              *(_OWORD *)v126 = 0;
              v127 = si128;
              LOWORD(v126[0]) = 0;
              p_Uuid2 = (UUID *)&v130;
              v94 = v126;
              v124[0] = (unsigned __int16 *)retaddr;
              v124[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
              v125.m128i_i64[0] = 0;
              v125.m128i_i16[4] = 27169;
              *(_QWORD *)&Uuid2.Data1 = &wil::details::functor_wrapper_void<_lambda_5c4d8d808dfae828cbf8d5e573fbfa90_>::`vftable';
              *(_QWORD *)Uuid2.Data4 = &p_Uuid2;
              wil::details::ResultFromException(v124, v74, &Uuid2);
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DCC0, 2147943568LL);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A2A,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x80070490LL,
                v89);
            }
            ++v33;
          }
          v3 = this;
          for ( j = (UUID *)*((_QWORD *)this + 16); j != *((UUID **)this + 17); ++j )
          {
            Uuid2 = *j;
            *(_QWORD *)Status = 0;
            VmGuidSet::find(&v132, Status, &Uuid2);
            if ( *(_QWORD *)Status == *((_QWORD *)&v132 + 1) )
            {
              *(_OWORD *)v126 = 0;
              v127 = si128;
              LOWORD(v126[0]) = 0;
              p_Uuid2 = &Uuid2;
              v94 = v126;
              v124[0] = (unsigned __int16 *)retaddr;
              v124[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
              v125.m128i_i64[0] = 0;
              v125.m128i_i16[4] = 27194;
              *(_QWORD *)&v130 = &wil::details::functor_wrapper_void<_lambda_8133ae184a6f14abd9aed618c3ff868c_>::`vftable';
              *((_QWORD *)&v130 + 1) = &p_Uuid2;
              wil::details::ResultFromException(v124, v72, &v130);
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DCD8, 2147943568LL);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A43,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x80070490LL,
                v89);
            }
            memmove_0(
              *(void **)Status,
              (const void *)(*(_QWORD *)Status + 16LL),
              *((_QWORD *)&v132 + 1) - (*(_QWORD *)Status + 16LL));
            v34 = *((_QWORD *)&v132 + 1) - 16LL;
            *((_QWORD *)&v132 + 1) -= 16LL;
          }
          if ( (_QWORD)v132 != v34 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v89 = (unsigned int)v5;
              VmlDebugTraceWithError(16808, &off_14091DCF0, v29);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6A52,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)v29,
              v89);
          }
          v136 = 0;
          v36 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v122
                                                                                                 + 168LL))(
                  v122,
                  L"topology/shared_vhd_vm/count",
                  &v136);
          v37 = v36;
          if ( v36 < 0 )
          {
            if ( v36 != -2147024894 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DD08, v37);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A64,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v37,
                v89);
            }
            if ( (__int64)(*((_QWORD *)this + 64) - *((_QWORD *)this + 63)) >> 4 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v89 = (unsigned int)v5;
                VmlDebugTraceWithError(16808, &off_14091DD20, v37);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A6F,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v37,
                v89);
            }
          }
          v38 = (__int64)(*((_QWORD *)this + 64) - *((_QWORD *)this + 63)) >> 4;
          v39 = v136;
          if ( v38 != v136 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v89 = (unsigned int)v5;
              VmlDebugTraceWithError(16808, &off_14091DD38, 2147943862LL);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6A7A,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)0x800705B6LL,
              v89);
          }
          if ( v38 )
            break;
        }
LABEL_165:
        v66 = ((__int64 (*)(void))Vml::VmComMultiInstanceObject<Vml::VmComLocalMemStream>::CreateInstance<>)();
        Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
          &v98,
          v66);
        v67 = v98;
        v68 = (Vml::VmComMemStreamBase *)(v98 + 24);
        v137[0] = (struct Vml::VmGuid *)(v98 + 24);
        v69 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v122 + 248LL))(
                v122,
                (v98 + 24) & ((unsigned __int128)-(__int128)v98 >> 64),
                L"settings");
        if ( v69 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B2E,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v69,
            v89);
        v75 = Vml::VmComMemStreamBase::Seek(v68, v96, 0, 0);
        if ( v75 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B30,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v75,
            v89);
        v76 = Vml::VmComMultiInstanceObject<Vml::VmComLocalMemStream>::CreateInstance<>(retaddr);
        Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
          &v97,
          v76);
        v77 = v97;
        v78 = (Vml::VmComMemStreamBase *)(v97 + 24);
        *(_QWORD *)Status = v97 + 24;
        v79 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v122 + 248LL))(
                v122,
                (v97 + 24) & ((unsigned __int128)-(__int128)v97 >> 64),
                L"topology");
        if ( v79 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B39,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v79,
            v89);
        v80 = Vml::VmComMemStreamBase::Seek(v78, v96, 0, 0);
        if ( v80 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B3B,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v80,
            v89);
        v81 = (struct IGroupRepository *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 98) + 280LL))(*((_QWORD *)v3 + 98));
        Vml::VmReferencePtr<IGroupRepository,Vml::VmUserReferenceTraits>::Reset(&v99);
        v99 = v81;
        *(_OWORD *)v111 = 0;
        GroupRepositoryAutoLock::GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v111, v81, 1);
        if ( SLODWORD(v111[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B41,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)LODWORD(v111[1]),
            v89);
        v82 = (*(__int64 (__fastcall **)(struct IGroupRepository *, _BYTE *, __int64 *))(*(_QWORD *)v81 + 312LL))(
                v81,
                v144,
                &v131);
        if ( v82 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B46,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v82,
            v89);
        v83 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, const unsigned __int16 *))(*(_QWORD *)v131 + 256LL))(
                v131,
                (unsigned __int64)v137[0] & -(__int64)(v67 != 0),
                L"settings");
        if ( v83 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B4C,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v83,
            v89);
        v84 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v131 + 256LL))(
                v131,
                *(_QWORD *)Status & -(__int64)(v77 != 0),
                L"topology");
        if ( v84 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B52,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v84,
            v89);
        v85 = (*(__int64 (__fastcall **)(struct IGroupRepository *))(*(_QWORD *)v81 + 368LL))(v81);
        if ( v85 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B55,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v85,
            v89);
        GroupRepositoryAutoLock::~GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v111);
        GroupRepositoryAutoLock::~GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v110);
        v8 = 0;
        v103 = 0;
      }
      v142 = 0;
      v143 = 0;
      Src = 0;
      v129 = si128;
      LOWORD(Src) = 0;
      v135 = 0;
      Uuid2 = 0;
      for ( k = 0; k < v39; ++k )
      {
        *(_OWORD *)v124 = 0;
        v125 = si128;
        LOWORD(v124[0]) = 0;
        *(_OWORD *)v126 = 0;
        v127 = si128;
        LOWORD(v126[0]) = 0;
        *(_OWORD *)v137 = 0;
        Vml::FormatString(v124, (wchar_t *)L"topology/shared_vhd_vm/vm%llu/guid");
        v41 = v124;
        if ( v125.m128i_i64[1] > 7uLL )
          v41 = (unsigned __int16 **)v124[0];
        v42 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v122 + 152LL))(
                v122,
                v41,
                v126);
        if ( v42 < 0 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            v89 = (unsigned int)v5;
            VmlDebugTraceWithError(16808, &off_14091DD50, (unsigned int)v42);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6AA3,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v42,
            v89);
        }
        v43 = (const unsigned __int16 *)v126;
        if ( v127.m128i_i64[1] > 7uLL )
          v43 = v126[0];
        Vml::VmGuid::Assign((Vml::VmGuid *)v137, v43);
        VmGuidSet::insert(&v142, v118, *((_QWORD *)&v142 + 1), v137);
        std::wstring::_Tidy_deallocate(v126);
        std::wstring::_Tidy_deallocate(v124);
        v39 = v136;
      }
      v3 = this;
      for ( m = (__int128 *)*((_QWORD *)this + 63); m != *((__int128 **)this + 64); ++m )
      {
        v71 = (_QWORD *)VmGuidSet::find(&v142, v119, m);
        if ( *v71 == *((_QWORD *)&v142 + 1) )
        {
          v138 = *m;
          *(_OWORD *)v126 = 0;
          v127 = si128;
          LOWORD(v126[0]) = 0;
          p_Uuid2 = (UUID *)&v138;
          v94 = v126;
          v124[0] = (unsigned __int16 *)retaddr;
          v124[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
          v125.m128i_i64[0] = 0;
          v125.m128i_i16[4] = 27316;
          *(_QWORD *)&v130 = &wil::details::functor_wrapper_void<_lambda_055d1e89baa3e0cb09851fcc1b0218da_>::`vftable';
          *((_QWORD *)&v130 + 1) = &p_Uuid2;
          wil::details::ResultFromException(v124, v70, &v130);
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            v89 = (unsigned int)v5;
            VmlDebugTraceWithError(16808, &off_14091D970, 2147943568LL);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6ABD,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80070490LL,
            v89);
        }
      }
      v45 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *))(*(_QWORD *)v122 + 152LL))(
              v122,
              L"shared_vhd_vm/shared_tracker_owner_id",
              &Src);
      if ( v45 < 0 )
      {
        IsDebugTraceEnabled = VmlIsDebugTraceEnabled(16808);
        if ( v45 != -2147024894 )
        {
          if ( IsDebugTraceEnabled )
          {
            v89 = (unsigned int)v5;
            VmlDebugTraceWithError(16808, &off_14091D988, (unsigned int)v45);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6ACD,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v45,
            v89);
        }
        if ( IsDebugTraceEnabled )
        {
          v89 = (unsigned int)v5;
          VmlDebugTraceWithError(16808, &off_14091D9A0, 2147942402LL);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AD7,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x80070002LL,
          v89);
      }
      v47 = (const unsigned __int16 *)&Src;
      if ( v129.m128i_i64[1] > 7uLL )
        v47 = (const unsigned __int16 *)Src;
      Vml::VmGuid::Assign((Vml::VmGuid *)&Uuid2, v47);
      Status[0] = 0;
      if ( UuidCompare((UUID *)((char *)this + 568), &Uuid2, Status) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
        {
          v89 = (unsigned int)v5;
          VmlDebugTraceWithError(16808, &off_14091D9B8, 2147942413LL);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AE4,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x8007000DLL,
          v89);
      }
      std::wstring::_Eos(&Src, 0);
      v48 = (*(__int64 (__fastcall **)(__int64, const char *, __int128 *))(*(_QWORD *)v122 + 152LL))(
              v122,
              L"shared_vhd_vm/shared_tracker_id",
              &Src);
      if ( v48 < 0 )
      {
        v49 = VmlIsDebugTraceEnabled(16808);
        if ( v48 != -2147024894 )
        {
          if ( v49 )
          {
            v89 = (unsigned int)v5;
            VmlDebugTraceWithError(16808, &off_14091D9D0, (unsigned int)v48);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6AF5,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v48,
            v89);
        }
        if ( v49 )
        {
          v89 = (unsigned int)v5;
          VmlDebugTraceWithError(16808, &off_14091D9E8, 2147942402LL);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AFF,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x80070002LL,
          v89);
      }
      v50 = (const unsigned __int16 *)&Src;
      if ( v129.m128i_i64[1] > 7uLL )
        v50 = (const unsigned __int16 *)Src;
      Vml::VmGuid::Assign((Vml::VmGuid *)&v135, v50);
      v137[0] = (ReplicationCoordinator *)((char *)this + 552);
      Status[0] = 0;
      if ( !UuidCompare((UUID *)((char *)this + 552), &v135, Status) )
      {
LABEL_164:
        std::wstring::_Tidy_deallocate(&Src);
        std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v142);
        goto LABEL_165;
      }
      if ( a3 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
        {
          v89 = (unsigned int)v5;
          VmlDebugTraceWithError(16808, &off_14091DA00, 2147942413LL);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B20,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x8007000DLL,
          v89);
      }
      if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6B08,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          v51);
      v52 = (unsigned __int32 *)((char *)this + 1424);
      CurrentThreadId = GetCurrentThreadId();
      v55 = _InterlockedCompareExchange((volatile signed __int32 *)this + 356, 1, 0);
      if ( v55 )
      {
        if ( *((_DWORD *)this + 357) == CurrentThreadId )
        {
          _InterlockedAdd((volatile signed __int32 *)this + 358, 1u);
          goto LABEL_146;
        }
        do
        {
          while ( (v55 & 1) != 0 || v55 >= 4 )
          {
            LOBYTE(v54) = 1;
            if ( !(unsigned int)RrwpLockWait((char *)this + 1424, 0xFFFFFFFFLL, v54) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2FE,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v89);
            _m_prefetchw(v52);
            v55 = *v52;
          }
          v56 = v55;
          v55 = _InterlockedCompareExchange((volatile signed __int32 *)v52, v55 + 1, v55);
        }
        while ( v55 != v56 );
      }
      _InterlockedExchange((volatile __int32 *)this + 357, CurrentThreadId);
LABEL_146:
      p_Uuid2 = (UUID *)((char *)this + 1424);
      v57 = 1;
      LOBYTE(v94) = 1;
      while ( v57 )
      {
        v58 = 1;
        BYTE12(v138) = 1;
        v59 = ReplicationCoordinator::gm_RcTlsIndex;
        LODWORD(v138) = ReplicationCoordinator::gm_RcTlsIndex;
        v60 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
        DWORD1(v138) = v60;
        DWORD2(v138) = v60 | 0x10;
        TlsSetValue(v59, (LPVOID)(v60 | 0x10));
        while ( v58 )
        {
          v61 = ReplicationPhaseManager::ProcessSharedTrackerIdChange(
                  *((ReplicationPhaseManager **)this + 97),
                  v137[0],
                  (const struct Vml::VmGuid *)&v135);
          if ( v61 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6B0E,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v61,
              v89);
          v58 = 0;
          BYTE12(v138) = 0;
        }
        TlsSetValue(v59, (LPVOID)v60);
        v57 = 0;
        LOBYTE(v94) = 0;
      }
      RrwLockRelease(v52);
      if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6B11,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          v62);
      v3 = this;
      Vml::VmSlimReaderWriterLock::AcquireExclusive((ReplicationCoordinator *)((char *)this + 1408));
      v63 = ReplicationCoordinator::gm_RcTlsIndex;
      v64 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      TlsSetValue(v63, (LPVOID)(v64 | 4LL));
      *(UUID *)((char *)this + 552) = v135;
      TlsSetValue(v63, (LPVOID)v64);
      *((_DWORD *)this + 354) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 176);
      updated = ReplicationCoordinator::UpdateSharedTrackerInfoToConfig(this);
      if ( updated < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B16,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)(unsigned int)updated,
          v89);
      goto LABEL_164;
    }
    LeaveCriticalSection(lpCriticalSection);
    v87 = 0;
  }
  catch ( ... )
  {
    HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                           (Vml *)0x41A8,
                                           (unsigned __int16)&off_14091D8F0,
                                           v86);
    v87 = HResultFromThrownExceptionAndTrace;
    if ( HResultFromThrownExceptionAndTrace < 0 && (unsigned int)VmlIsDebugTraceEnabled(16808) )
      VmlDebugTraceWithError(16808, &off_1408B8E38, (unsigned int)HResultFromThrownExceptionAndTrace);
  }
  std::wstring::_Tidy_deallocate(v121);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v139);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v132);
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v97);
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v98);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v122);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v131);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v99);
  return v87;
}

```

## disassembly

```asm
0x14020d218  mov     r11, rsp
0x14020d21b  mov     [r11+18h], rbx
0x14020d21f  mov     [r11+20h], rsi
0x14020d223  push    rdi
0x14020d224  push    r12
0x14020d226  push    r13
0x14020d228  push    r14
0x14020d22a  push    r15
0x14020d22c  sub     rsp, 290h
0x14020d233  movaps  xmmword ptr [r11-38h], xmm6
0x14020d238  mov     rax, cs:__security_cookie
0x14020d23f  xor     rax, rsp
0x14020d242  mov     [rsp+2B8h+var_40], rax
0x14020d24a  mov     [rsp+2B8h+var_278], r8d
0x14020d24f  mov     [rsp+2B8h+var_1E8], rdx
0x14020d257  mov     r13, rcx
0x14020d25a  mov     [rsp+2B8h+var_280], rcx
0x14020d25f  xor     r14d, r14d
0x14020d262  mov     [rsp+2B8h+var_240], r14
0x14020d267  lea     rdx, ?GROUP_FAILOVER_REPLICATION_SETTINGS_ID@@3QBGB; "82CEFEFE-9D05-4D0E-A9FE-6C0A1D33299F"
0x14020d26e  lea     rcx, [r11-50h]; this
0x14020d272  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x14020d277  mov     [rsp+2B8h+var_100], r14
0x14020d27f  mov     [rsp+2B8h+var_180], r14
0x14020d287  mov     [rsp+2B8h+var_248], r14
0x14020d28c  mov     [rsp+2B8h+var_250], r14
0x14020d291  mov     qword ptr [rsp+2B8h+var_258], r14
0x14020d296  xorps   xmm0, xmm0
0x14020d299  xorps   xmm1, xmm1
0x14020d29c  movdqu  [rsp+2B8h+var_F8], xmm1
0x14020d2a5  mov     [rsp+2B8h+var_E8], r14
0x14020d2ad  movdqu  [rsp+2B8h+var_88], xmm1
0x14020d2b6  mov     [rsp+2B8h+var_78], r14
0x14020d2be  mov     [rsp+2B8h+var_70], r14
0x14020d2c6  movups  [rsp+2B8h+var_1A0], xmm0
0x14020d2ce  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14020d2d6  movdqu  [rsp+2B8h+var_190], xmm6
0x14020d2df  mov     word ptr [rsp+2B8h+var_1A0], r14w
0x14020d2e8  lea     r12, [r13+60h]
0x14020d2ec  mov     [rsp+2B8h+var_1D8], r12
0x14020d2f4  lea     rax, [r12+18h]
0x14020d2f9  mov     [rsp+2B8h+var_1D0], rax
0x14020d301  lea     r15d, [r14+7]
0x14020d305  cmp     [rax], r15
0x14020d308  jbe     short loc_14020D30E
0x14020d30a  mov     r12, [r12]
0x14020d30e  mov     [rsp+2B8h+var_1C8], r12
0x14020d316  lea     rdx, [rsp+2B8h+var_1A0]
0x14020d31e  mov     rcx, r13
0x14020d321  call    ?GetName@ReplicationCoordinator@@QEBAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReplicationCoordinator::GetName(std::wstring &)
0x14020d326  mov     [rsp+2B8h+var_288], r14d
0x14020d32b  mov     ecx, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; dwTlsIndex
0x14020d331  call    cs:__imp_TlsGetValue
0x14020d338  nop     dword ptr [rax+rax+00h]
0x14020d33d  and     eax, 1Eh
0x14020d340  mov     rcx, [rsp+2B8h]; this
0x14020d348  jz      short loc_14020D35C
0x14020d34a  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d351  mov     edx, 6995h; void *
0x14020d356  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14020d35c  lea     rbx, [r13+5C0h]
0x14020d363  mov     [rsp+2B8h+lpCriticalSection], rbx
0x14020d36b  mov     rcx, rbx; lpCriticalSection
0x14020d36e  call    cs:__imp_EnterCriticalSection
0x14020d375  nop     dword ptr [rax+rax+00h]
0x14020d37a  mov     esi, 1
0x14020d37f  mov     al, sil
0x14020d382  mov     [rsp+2B8h+var_210], al
0x14020d389  test    al, al
0x14020d38b  jz      loc_14020ECF3
0x14020d391  mov     bl, sil
0x14020d394  mov     [rsp+2B8h+var_22C], bl
0x14020d39b  mov     edi, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; ulong ReplicationCoordinator::gm_RcTlsIndex
0x14020d3a1  mov     [rsp+2B8h+dwTlsIndex], edi
0x14020d3a5  mov     [rsp+2B8h+var_238], edi
0x14020d3ac  mov     ecx, edi; dwTlsIndex
0x14020d3ae  call    cs:__imp_TlsGetValue
0x14020d3b5  nop     dword ptr [rax+rax+00h]
0x14020d3ba  mov     [rsp+2B8h+lpTlsValue], rax
0x14020d3c2  mov     [rsp+2B8h+var_234], eax
0x14020d3c9  mov     edx, eax
0x14020d3cb  mov     esi, 1
0x14020d3d0  or      edx, esi; lpTlsValue
0x14020d3d2  mov     [rsp+2B8h+var_230], edx
0x14020d3d9  mov     ecx, edi; dwTlsIndex
0x14020d3db  call    cs:__imp_TlsSetValue
0x14020d3e2  nop     dword ptr [rax+rax+00h]
0x14020d3e7  nop
0x14020d3e8  test    bl, bl
0x14020d3ea  jz      loc_14020ECCD
0x14020d3f0  mov     rdi, [rsp+2B8h]
0x14020d3f8  mov     ecx, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; dwTlsIndex
0x14020d3fe  call    cs:__imp_TlsGetValue
0x14020d405  nop     dword ptr [rax+rax+00h]
0x14020d40a  test    sil, al
0x14020d40d  jnz     short loc_14020D424
0x14020d40f  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d416  mov     edx, 6997h; void *
0x14020d41b  mov     rcx, rdi; this
0x14020d41e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14020d424  mov     edx, 40h ; '@'
0x14020d429  mov     rcx, r13
0x14020d42c  call    ?TestOperationalFlag@ReplicationCoordinator@@AEBAHW4RcOperationalFlags@1@@Z; ReplicationCoordinator::TestOperationalFlag(ReplicationCoordinator::RcOperationalFlags)
0x14020d431  test    eax, eax
0x14020d433  jz      short loc_14020D496
0x14020d435  mov     edi, 41A8h
0x14020d43a  mov     ecx, edi
0x14020d43c  call    VmlIsDebugTraceEnabled
0x14020d441  test    eax, eax
0x14020d443  jz      short loc_14020D477
0x14020d445  lea     r9, [rsp+2B8h+var_1A0]
0x14020d44d  cmp     qword ptr [rsp+2B8h+var_190+8], r15
0x14020d455  cmova   r9, qword ptr [rsp+2B8h+var_1A0]
0x14020d45e  mov     qword ptr [rsp+2B8h+var_298], r12; int
0x14020d463  mov     r8d, 80004004h
0x14020d469  lea     rdx, off_14091DD88; "%ws::%ws Coordinator has already stoppe"...
0x14020d470  mov     ecx, edi
0x14020d472  call    VmlDebugTraceWithError
0x14020d477  mov     rcx, [rsp+2B8h]; this
0x14020d47f  mov     r9d, 80004004h; char *
0x14020d485  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d48c  mov     edx, 6997h; void *
0x14020d491  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d496  xorps   xmm0, xmm0
0x14020d499  movups  xmmword ptr [rsp+2B8h+var_208], xmm0
0x14020d4a1  xor     r8d, r8d; int
0x14020d4a4  mov     rbx, [rsp+2B8h+var_1E8]
0x14020d4ac  mov     rdx, rbx; struct IGroupRepository *
0x14020d4af  lea     rcx, [rsp+2B8h+var_208]; this
0x14020d4b7  call    ??0GroupRepositoryAutoLock@@QEAA@PEAUIGroupRepository@@H@Z; GroupRepositoryAutoLock::GroupRepositoryAutoLock(IGroupRepository *,int)
0x14020d4bc  nop
0x14020d4bd  mov     r9d, dword ptr [rsp+2B8h+var_208+8]; char *
0x14020d4c5  mov     rcx, [rsp+2B8h]; this
0x14020d4cd  test    r9d, r9d
0x14020d4d0  jns     short loc_14020D4E3
0x14020d4d2  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d4d9  mov     edx, 69A0h; void *
0x14020d4de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d4e3  mov     rax, [rbx]
0x14020d4e6  lea     r8, [rsp+2B8h+var_180]
0x14020d4ee  lea     rdx, [rsp+2B8h+var_50]
0x14020d4f6  mov     rcx, rbx
0x14020d4f9  mov     rax, [rax+138h]
0x14020d500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14020d505  mov     rcx, [rsp+2B8h]; this
0x14020d50d  test    eax, eax
0x14020d50f  jns     short loc_14020D525
0x14020d511  mov     r9d, eax; char *
0x14020d514  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d51b  mov     edx, 69A5h; void *
0x14020d520  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d525  mov     rcx, [r13+310h]
0x14020d52c  mov     rax, [rcx]
0x14020d52f  xor     r8d, r8d
0x14020d532  lea     rdx, [rsp+2B8h+var_88]
0x14020d53a  mov     rax, [rax+58h]
0x14020d53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14020d543  mov     rax, qword ptr [rsp+2B8h+var_88+8]
0x14020d54b  cmp     rax, qword ptr [rsp+2B8h+var_88]
0x14020d553  jz      loc_14020E547
0x14020d559  mov     eax, [r13+318h]
0x14020d560  cmp     [rsp+2B8h+var_278], r14d
0x14020d565  jz      loc_14020D72A
0x14020d56b  cmp     eax, esi
0x14020d56d  jz      short loc_14020D5D0
0x14020d56f  mov     edi, 41A8h
0x14020d574  mov     ecx, edi
0x14020d576  call    VmlIsDebugTraceEnabled
0x14020d57b  test    eax, eax
0x14020d57d  jz      short loc_14020D5B1
0x14020d57f  lea     r9, [rsp+2B8h+var_1A0]
0x14020d587  cmp     qword ptr [rsp+2B8h+var_190+8], r15
0x14020d58f  cmova   r9, qword ptr [rsp+2B8h+var_1A0]
0x14020d598  mov     qword ptr [rsp+2B8h+var_298], r12; int
0x14020d59d  mov     r8d, 8007139Fh
0x14020d5a3  lea     rdx, off_14091DDA0; "%ws::%ws The group is not a primary gro"...
0x14020d5aa  mov     ecx, edi
0x14020d5ac  call    VmlDebugTraceWithError
0x14020d5b1  mov     rcx, [rsp+2B8h]; this
0x14020d5b9  mov     r9d, 8007139Fh; char *
0x14020d5bf  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d5c6  mov     edx, 69B7h; void *
0x14020d5cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d5d0  add     r13, 590h
0x14020d5d7  xor     eax, eax
0x14020d5d9  lea     ecx, [rax+4]
0x14020d5dc  lock cmpxchg [r13+0], ecx
0x14020d5e2  mov     ebx, eax
0x14020d5e4  jz      short loc_14020D60E
0x14020d5e6  test    sil, al
0x14020d5e9  jz      loc_14020D6D1
0x14020d5ef  call    cs:__imp_GetCurrentThreadId
0x14020d5f6  nop     dword ptr [rax+rax+00h]
0x14020d5fb  mov     ecx, eax
0x14020d5fd  mov     eax, [r13+4]
0x14020d601  cmp     eax, ecx
0x14020d603  jnz     loc_14020D6D1
0x14020d609  lock add [r13+8], esi
0x14020d60e  mov     esi, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; ulong ReplicationCoordinator::gm_RcTlsIndex
0x14020d614  mov     ecx, esi; dwTlsIndex
0x14020d616  call    cs:__imp_TlsGetValue
0x14020d61d  nop     dword ptr [rax+rax+00h]
0x14020d622  mov     rdi, rax
0x14020d625  mov     edx, eax
0x14020d627  or      rdx, 8; lpTlsValue
0x14020d62b  mov     ecx, esi; dwTlsIndex
0x14020d62d  call    cs:__imp_TlsSetValue
0x14020d634  nop     dword ptr [rax+rax+00h]
0x14020d639  mov     rcx, [rsp+2B8h+var_280]
0x14020d63e  mov     rcx, [rcx+308h]; this
0x14020d645  call    ?GetReplicationPhaseFlags@ReplicationPhaseManager@@QEAAKXZ; ReplicationPhaseManager::GetReplicationPhaseFlags(void)
0x14020d64a  mov     ebx, eax
0x14020d64c  mov     edx, edi; lpTlsValue
0x14020d64e  mov     ecx, esi; dwTlsIndex
0x14020d650  call    cs:__imp_TlsSetValue
0x14020d657  nop     dword ptr [rax+rax+00h]
0x14020d65c  mov     rcx, r13
0x14020d65f  call    RrwLockRelease
0x14020d664  cmp     ebx, 10000h
0x14020d66a  jz      loc_14020D941
0x14020d670  mov     edi, 41A8h
0x14020d675  mov     ecx, edi
0x14020d677  call    VmlIsDebugTraceEnabled
0x14020d67c  test    eax, eax
0x14020d67e  jz      short loc_14020D6B2
0x14020d680  lea     r9, [rsp+2B8h+var_1A0]
0x14020d688  cmp     qword ptr [rsp+2B8h+var_190+8], r15
0x14020d690  cmova   r9, qword ptr [rsp+2B8h+var_1A0]
0x14020d699  mov     qword ptr [rsp+2B8h+var_298], r12; int
0x14020d69e  mov     r8d, 8007139Fh
0x14020d6a4  lea     rdx, off_14091DDB8; "%ws::%ws All VMs in the group are not p"...
0x14020d6ab  mov     ecx, edi
0x14020d6ad  call    VmlDebugTraceWithError
0x14020d6b2  mov     rcx, [rsp+2B8h]; this
0x14020d6ba  mov     r9d, 8007139Fh; char *
0x14020d6c0  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d6c7  mov     edx, 69C8h; void *
0x14020d6cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d6d1  test    sil, bl
0x14020d6d4  jnz     short loc_14020D6EE
0x14020d6d6  mov     edx, ebx
0x14020d6d8  lea     ecx, [rbx+4]
0x14020d6db  mov     eax, ebx
0x14020d6dd  lock cmpxchg [r13+0], ecx
0x14020d6e3  mov     ebx, eax
0x14020d6e5  cmp     eax, edx
0x14020d6e7  jnz     short loc_14020D6D1
0x14020d6e9  jmp     loc_14020D60E
0x14020d6ee  xor     r8d, r8d
0x14020d6f1  or      edx, 0FFFFFFFFh
0x14020d6f4  mov     rcx, r13
0x14020d6f7  call    RrwpLockWait
0x14020d6fc  test    eax, eax
0x14020d6fe  jnz     short loc_14020D71F
0x14020d700  mov     rcx, [rsp+2B8h]; this
0x14020d708  mov     r9d, 102h; char *
0x14020d70e  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14020d715  mov     edx, 249h; void *
0x14020d71a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14020d71f  prefetchw byte ptr [r13+0]
0x14020d724  mov     ebx, [r13+0]
0x14020d728  jmp     short loc_14020D6D1
0x14020d72a  cmp     eax, 2
0x14020d72d  jz      short loc_14020D790
0x14020d72f  mov     edi, 41A8h
0x14020d734  mov     ecx, edi
0x14020d736  call    VmlIsDebugTraceEnabled
0x14020d73b  test    eax, eax
0x14020d73d  jz      short loc_14020D771
0x14020d73f  lea     r9, [rsp+2B8h+var_1A0]
0x14020d747  cmp     qword ptr [rsp+2B8h+var_190+8], r15
0x14020d74f  cmova   r9, qword ptr [rsp+2B8h+var_1A0]
0x14020d758  mov     qword ptr [rsp+2B8h+var_298], r12; int
0x14020d75d  mov     r8d, 8007139Fh
0x14020d763  lea     rdx, off_14091DDD0; "%ws::%ws The group is not a recovery gr"...
0x14020d76a  mov     ecx, edi
0x14020d76c  call    VmlDebugTraceWithError
0x14020d771  mov     rcx, [rsp+2B8h]; this
0x14020d779  mov     r9d, 8007139Fh; char *
0x14020d77f  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14020d786  mov     edx, 69D6h; void *
0x14020d78b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14020d790  lea     rdi, [r13+590h]
0x14020d797  xor     eax, eax
0x14020d799  lea     ecx, [rax+4]
0x14020d79c  lock cmpxchg [rdi], ecx
0x14020d7a0  mov     ebx, eax
0x14020d7a2  jz      short loc_14020D7CA
0x14020d7a4  test    sil, al
0x14020d7a7  jz      loc_14020D8B2
0x14020d7ad  call    cs:__imp_GetCurrentThreadId
0x14020d7b4  nop     dword ptr [rax+rax+00h]
0x14020d7b9  mov     ecx, eax
0x14020d7bb  mov     eax, [rdi+4]
0x14020d7be  cmp     eax, ecx
0x14020d7c0  jnz     loc_14020D8B2
0x14020d7c6  lock add [rdi+8], esi
0x14020d7ca  mov     qword ptr [rsp+2B8h+var_110], rdi
0x14020d7d2  mov     al, sil
0x14020d7d5  mov     byte ptr [rsp+2B8h+var_110+8], al
  ... truncated ...
```
