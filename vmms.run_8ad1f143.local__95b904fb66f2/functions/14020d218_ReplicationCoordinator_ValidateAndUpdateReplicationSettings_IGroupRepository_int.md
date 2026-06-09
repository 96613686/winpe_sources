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
  __int128 *v11; // r9
  struct IGroupRepository *v12; // rbx
  int v13; // eax
  int v14; // eax
  __int128 *v15; // r9
  volatile signed __int32 *v16; // r13
  signed __int32 v17; // eax
  signed __int32 v18; // ebx
  DWORD v19; // esi
  unsigned int Value; // edi
  unsigned int ReplicationPhaseFlags; // ebx
  __int128 *v22; // r9
  signed __int32 v23; // edx
  __int128 *v24; // r9
  signed __int32 *v25; // rdi
  signed __int32 v26; // eax
  signed __int32 v27; // ebx
  char v28; // al
  char v29; // bl
  DWORD v30; // esi
  unsigned int v31; // r13d
  __int128 *v32; // r9
  signed __int32 v33; // edx
  unsigned int v34; // esi
  __int128 *v35; // r9
  unsigned __int64 i; // rbx
  __int128 *p_Src; // rdx
  __int128 *v38; // r9
  const unsigned __int16 *v39; // rdx
  __int128 *v40; // rbx
  __int64 v41; // rcx
  UUID *j; // rbx
  int v43; // eax
  unsigned int v44; // ebx
  __int128 *v45; // r9
  __int128 *v46; // r9
  __int64 v47; // rax
  unsigned __int64 v48; // rcx
  __int128 *v49; // r9
  unsigned __int64 k; // rdi
  unsigned __int16 **v51; // rdx
  int v52; // ebx
  __int128 *v53; // r9
  const unsigned __int16 *v54; // rdx
  __int128 *m; // rbx
  int v56; // ebx
  int IsDebugTraceEnabled; // eax
  __int128 *v58; // r9
  __int128 *v59; // r9
  const unsigned __int16 *v60; // rdx
  __int128 *v61; // r9
  int v62; // ebx
  int v63; // eax
  __int128 *v64; // r9
  __int128 *v65; // r9
  const unsigned __int16 *v66; // rdx
  const char *v67; // r9
  unsigned __int32 *v68; // rbx
  DWORD CurrentThreadId; // edi
  __int64 v70; // r8
  unsigned __int32 v71; // eax
  unsigned __int32 v72; // edx
  char v73; // al
  char v74; // di
  DWORD v75; // esi
  unsigned int v76; // r13d
  int v77; // eax
  const char *v78; // r9
  DWORD v79; // edi
  unsigned int v80; // ebx
  int updated; // eax
  __int128 *v82; // r9
  __int64 v83; // rax
  unsigned __int64 v84; // rsi
  Vml::VmComMemStreamBase *v85; // rbx
  int v86; // eax
  __int64 v87; // rdx
  _QWORD *v88; // rcx
  __int128 *v89; // r9
  __int128 *v90; // r9
  __int64 v91; // rdx
  __int128 *v92; // r9
  _QWORD *v93; // rax
  __int64 v94; // rdx
  __int128 *v95; // r9
  int v96; // eax
  __int64 v97; // rax
  unsigned __int64 v98; // rdi
  Vml::VmComMemStreamBase *v99; // rbx
  int v100; // eax
  int v101; // eax
  struct IGroupRepository *v102; // rbx
  int v103; // eax
  int v104; // eax
  int v105; // eax
  int v106; // eax
  const struct Vml::ExceptionTraceParameters *v107; // r8
  unsigned int v108; // r12d
  __int128 *v109; // r9
  unsigned int v111; // [rsp+20h] [rbp-298h]
  int HResultFromThrownExceptionAndTrace; // [rsp+30h] [rbp-288h]
  UUID *p_Uuid2; // [rsp+48h] [rbp-270h] BYREF
  unsigned __int16 **v116; // [rsp+50h] [rbp-268h]
  DWORD dwTlsIndex; // [rsp+58h] [rbp-260h]
  union _LARGE_INTEGER v118; // [rsp+60h] [rbp-258h]
  unsigned __int64 v119; // [rsp+68h] [rbp-250h] BYREF
  unsigned __int64 v120; // [rsp+70h] [rbp-248h] BYREF
  struct IGroupRepository *v121; // [rsp+78h] [rbp-240h] BYREF
  DWORD v122; // [rsp+80h] [rbp-238h]
  int v123; // [rsp+84h] [rbp-234h]
  unsigned int v124; // [rsp+88h] [rbp-230h]
  char v125; // [rsp+8Ch] [rbp-22Ch]
  DWORD v126; // [rsp+90h] [rbp-228h]
  unsigned int v127; // [rsp+94h] [rbp-224h]
  int v128; // [rsp+98h] [rbp-220h]
  char v129; // [rsp+9Ch] [rbp-21Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-218h]
  char v131; // [rsp+A8h] [rbp-210h]
  char *v132[2]; // [rsp+B0h] [rbp-208h] BYREF
  char *v133[2]; // [rsp+C0h] [rbp-1F8h] BYREF
  struct IGroupRepository *v134; // [rsp+D0h] [rbp-1E8h]
  LPVOID lpTlsValue; // [rsp+D8h] [rbp-1E0h]
  char *v136; // [rsp+E0h] [rbp-1D8h]
  char *v137; // [rsp+E8h] [rbp-1D0h]
  _QWORD *v138; // [rsp+F0h] [rbp-1C8h]
  char v139[8]; // [rsp+F8h] [rbp-1C0h] BYREF
  char v140[8]; // [rsp+100h] [rbp-1B8h] BYREF
  char v141[8]; // [rsp+108h] [rbp-1B0h] BYREF
  char v142[8]; // [rsp+110h] [rbp-1A8h] BYREF
  __int128 v143; // [rsp+118h] [rbp-1A0h] BYREF
  __m128i v144; // [rsp+128h] [rbp-190h]
  __int64 v145; // [rsp+138h] [rbp-180h] BYREF
  RPC_STATUS Status[2]; // [rsp+140h] [rbp-178h] BYREF
  unsigned __int16 *v147[2]; // [rsp+148h] [rbp-170h] BYREF
  __m128i v148; // [rsp+158h] [rbp-160h]
  unsigned __int16 *v149[2]; // [rsp+168h] [rbp-150h] BYREF
  __m128i v150; // [rsp+178h] [rbp-140h]
  __int128 Src; // [rsp+188h] [rbp-130h] BYREF
  __m128i v152; // [rsp+198h] [rbp-120h]
  __int128 v153; // [rsp+1A8h] [rbp-110h] BYREF
  __int64 v154; // [rsp+1B8h] [rbp-100h] BYREF
  __int128 v155; // [rsp+1C0h] [rbp-F8h] BYREF
  __int64 v156; // [rsp+1D0h] [rbp-E8h]
  UUID Uuid2; // [rsp+1E0h] [rbp-D8h] BYREF
  UUID v158; // [rsp+1F0h] [rbp-C8h] BYREF
  unsigned __int64 v159; // [rsp+200h] [rbp-B8h] BYREF
  struct Vml::VmGuid *v160[2]; // [rsp+210h] [rbp-A8h] BYREF
  __int128 v161; // [rsp+220h] [rbp-98h] BYREF
  __int128 v162; // [rsp+230h] [rbp-88h] BYREF
  __int64 v163; // [rsp+240h] [rbp-78h]
  unsigned __int64 v164; // [rsp+248h] [rbp-70h] BYREF
  __int128 v165; // [rsp+250h] [rbp-68h] BYREF
  __int64 v166; // [rsp+260h] [rbp-58h]
  _BYTE v167[16]; // [rsp+268h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v134 = a2;
  v3 = this;
  v121 = 0;
  Vml::VmGuid::Assign((Vml::VmGuid *)v167, L"82CEFEFE-9D05-4D0E-A9FE-6C0A1D33299F");
  v154 = 0;
  v145 = 0;
  v120 = 0;
  v119 = 0;
  v118.QuadPart = 0;
  v155 = 0;
  v156 = 0;
  v162 = 0;
  v163 = 0;
  v164 = 0;
  v143 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v144 = si128;
  LOWORD(v143) = 0;
  v5 = (_QWORD *)((char *)v3 + 96);
  v136 = (char *)v3 + 96;
  v137 = (char *)v3 + 120;
  if ( *((_QWORD *)v3 + 15) > 7u )
    v5 = (_QWORD *)*v5;
  v138 = v5;
  ReplicationCoordinator::GetName(v3, &v143);
  if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 0x1E) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6995,
      (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
      v6);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v3 + 1472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 1472));
  v7 = 1;
  v131 = 1;
  try
  {
LABEL_6:
    if ( v7 )
    {
      v8 = 1;
      v125 = 1;
      v9 = ReplicationCoordinator::gm_RcTlsIndex;
      dwTlsIndex = ReplicationCoordinator::gm_RcTlsIndex;
      v122 = ReplicationCoordinator::gm_RcTlsIndex;
      lpTlsValue = TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      v123 = (int)lpTlsValue;
      v124 = (unsigned int)lpTlsValue | 1;
      TlsSetValue(v9, (LPVOID)((unsigned int)lpTlsValue | 1));
      while ( 1 )
      {
        if ( !v8 )
        {
          TlsSetValue(dwTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
          v7 = 0;
          v131 = 0;
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
            v11 = &v143;
            if ( v144.m128i_i64[1] > 7uLL )
              v11 = (__int128 *)v143;
            VmlDebugTraceWithError(16808, &off_14091DD88, 2147500036LL, v11, v5);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6997,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80004004LL,
            v111);
        }
        *(_OWORD *)v132 = 0;
        v12 = v134;
        GroupRepositoryAutoLock::GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v132, v134, 0);
        if ( SLODWORD(v132[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69A0,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)LODWORD(v132[1]),
            v111);
        v13 = (*(__int64 (__fastcall **)(struct IGroupRepository *, _BYTE *, __int64 *))(*(_QWORD *)v12 + 312LL))(
                v12,
                v167,
                &v145);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69A5,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v13,
            v111);
        (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)v3 + 98) + 88LL))(
          *((_QWORD *)v3 + 98),
          &v162,
          0);
        if ( *((_QWORD *)&v162 + 1) != (_QWORD)v162 )
        {
          v14 = *((_DWORD *)v3 + 198);
          if ( a3 )
          {
            if ( v14 != 1 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v15 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v15 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DDA0, 2147947423LL, v15, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69B7,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v111);
            }
            v16 = (volatile signed __int32 *)((char *)v3 + 1424);
            v17 = _InterlockedCompareExchange(v16, 4, 0);
            v18 = v17;
            if ( v17 )
            {
              if ( (v17 & 1) != 0 && *((_DWORD *)v16 + 1) == GetCurrentThreadId() )
              {
                _InterlockedAdd(v16 + 2, 1u);
              }
              else
              {
                do
                {
                  while ( (v18 & 1) != 0 )
                  {
                    if ( !(unsigned int)RrwpLockWait(v16, 0xFFFFFFFFLL, 0) )
                      wil::details::in1diag3::Throw_Win32(
                        retaddr,
                        (void *)0x249,
                        (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                        (const char *)0x102,
                        v111);
                    _m_prefetchw((const void *)v16);
                    v18 = *v16;
                  }
                  v23 = v18;
                  v18 = _InterlockedCompareExchange(v16, v18 + 4, v18);
                }
                while ( v18 != v23 );
              }
            }
            v19 = ReplicationCoordinator::gm_RcTlsIndex;
            Value = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
            TlsSetValue(v19, (LPVOID)(Value | 8LL));
            ReplicationPhaseFlags = ReplicationPhaseManager::GetReplicationPhaseFlags(*((ReplicationPhaseManager **)this
                                                                                      + 97));
            TlsSetValue(v19, (LPVOID)Value);
            RrwLockRelease(v16);
            if ( ReplicationPhaseFlags != 0x10000 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v22 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v22 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DDB8, 2147947423LL, v22, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69C8,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v111);
            }
          }
          else
          {
            if ( v14 != 2 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v24 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v24 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DDD0, 2147947423LL, v24, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x69D6,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x8007139FLL,
                v111);
            }
            v25 = (signed __int32 *)((char *)v3 + 1424);
            v26 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 356, 4, 0);
            v27 = v26;
            if ( v26 )
            {
              if ( (v26 & 1) != 0 && *((_DWORD *)v3 + 357) == GetCurrentThreadId() )
              {
                _InterlockedAdd((volatile signed __int32 *)v3 + 358, 1u);
              }
              else
              {
                do
                {
                  while ( (v27 & 1) != 0 )
                  {
                    if ( !(unsigned int)RrwpLockWait((char *)v3 + 1424, 0xFFFFFFFFLL, 0) )
                      wil::details::in1diag3::Throw_Win32(
                        retaddr,
                        (void *)0x249,
                        (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                        (const char *)0x102,
                        v111);
                    _m_prefetchw(v25);
                    v27 = *v25;
                  }
                  v33 = v27;
                  v27 = _InterlockedCompareExchange(v25, v27 + 4, v27);
                }
                while ( v27 != v33 );
              }
            }
            *(_QWORD *)&v153 = (char *)v3 + 1424;
            v28 = 1;
            BYTE8(v153) = 1;
            while ( v28 )
            {
              v29 = 1;
              v129 = 1;
              v30 = ReplicationCoordinator::gm_RcTlsIndex;
              v126 = ReplicationCoordinator::gm_RcTlsIndex;
              v31 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
              v127 = v31;
              v128 = v31 | 8;
              TlsSetValue(v30, (LPVOID)(v31 | 8));
              while ( v29 )
              {
                if ( !(unsigned int)ReplicationPhaseManager::IsWaitingForIr(*((ReplicationPhaseManager **)this + 97)) )
                {
                  if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
                  {
                    v32 = &v143;
                    if ( v144.m128i_i64[1] > 7uLL )
                      v32 = (__int128 *)v143;
                    VmlDebugTraceWithError(16808, &off_14091DDE8, 2147947423LL, v32, v5);
                  }
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x69E4,
                    (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                    (const char *)0x8007139FLL,
                    v111);
                }
                v29 = 0;
                v129 = 0;
              }
              TlsSetValue(v30, (LPVOID)v31);
              v28 = 0;
              BYTE8(v153) = 0;
            }
            RrwLockRelease(v25);
          }
          v34 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v145
                                                                                                 + 168LL))(
                  v145,
                  L"topology/vm/count",
                  &v164);
          if ( (v34 & 0x80000000) != 0 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v35 = &v143;
              if ( v144.m128i_i64[1] > 7uLL )
                v35 = (__int128 *)v143;
              VmlDebugTraceWithError(16808, &off_14091DE00, v34, v35, v5);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x69F6,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)v34,
              v111);
          }
          for ( i = 0; i < v164; ++i )
          {
            Src = 0;
            v152 = si128;
            LOWORD(Src) = 0;
            *(_OWORD *)v147 = 0;
            v148 = si128;
            LOWORD(v147[0]) = 0;
            v158 = 0;
            Vml::FormatString(&Src, (wchar_t *)L"topology/vm/vm%llu/guid");
            p_Src = &Src;
            if ( v152.m128i_i64[1] > 7uLL )
              p_Src = (__int128 *)Src;
            v34 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int16 **))(*(_QWORD *)v145 + 152LL))(
                    v145,
                    p_Src,
                    v147);
            if ( (v34 & 0x80000000) != 0 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v38 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v38 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DCA8, v34, v38, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A10,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v34,
                v111);
            }
            v39 = (const unsigned __int16 *)v147;
            if ( v148.m128i_i64[1] > 7uLL )
              v39 = v147[0];
            Vml::VmGuid::Assign((Vml::VmGuid *)&v158, v39);
            VmGuidSet::insert(&v155, v139, *((_QWORD *)&v155 + 1), &v158);
            std::wstring::_Tidy_deallocate(v147);
            std::wstring::_Tidy_deallocate(&Src);
          }
          v40 = (__int128 *)v162;
          v41 = *((_QWORD *)&v155 + 1);
          while ( v40 != *((__int128 **)&v162 + 1) )
          {
            v93 = (_QWORD *)VmGuidSet::find(&v155, v142, v40);
            v41 = *((_QWORD *)&v155 + 1);
            if ( *v93 == *((_QWORD *)&v155 + 1) )
            {
              v153 = *v40;
              *(_OWORD *)v149 = 0;
              v150 = si128;
              LOWORD(v149[0]) = 0;
              p_Uuid2 = (UUID *)&v153;
              v116 = v149;
              v147[0] = (unsigned __int16 *)retaddr;
              v147[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
              v148.m128i_i64[0] = 0;
              v148.m128i_i16[4] = 27169;
              *(_QWORD *)&Uuid2.Data1 = &wil::details::functor_wrapper_void<_lambda_5c4d8d808dfae828cbf8d5e573fbfa90_>::`vftable';
              *(_QWORD *)Uuid2.Data4 = &p_Uuid2;
              wil::details::ResultFromException(v147, v94, &Uuid2);
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v95 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v95 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DCC0, 2147943568LL, v95, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A2A,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x80070490LL,
                v111);
            }
            ++v40;
          }
          v3 = this;
          for ( j = (UUID *)*((_QWORD *)this + 16); j != *((UUID **)this + 17); ++j )
          {
            Uuid2 = *j;
            *(_QWORD *)Status = 0;
            VmGuidSet::find(&v155, Status, &Uuid2);
            if ( *(_QWORD *)Status == *((_QWORD *)&v155 + 1) )
            {
              *(_OWORD *)v149 = 0;
              v150 = si128;
              LOWORD(v149[0]) = 0;
              p_Uuid2 = &Uuid2;
              v116 = v149;
              v147[0] = (unsigned __int16 *)retaddr;
              v147[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
              v148.m128i_i64[0] = 0;
              v148.m128i_i16[4] = 27194;
              *(_QWORD *)&v153 = &wil::details::functor_wrapper_void<_lambda_8133ae184a6f14abd9aed618c3ff868c_>::`vftable';
              *((_QWORD *)&v153 + 1) = &p_Uuid2;
              wil::details::ResultFromException(v147, v91, &v153);
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v92 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v92 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DCD8, 2147943568LL, v92, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A43,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x80070490LL,
                v111);
            }
            memmove_0(
              *(void **)Status,
              (const void *)(*(_QWORD *)Status + 16LL),
              *((_QWORD *)&v155 + 1) - (*(_QWORD *)Status + 16LL));
            v41 = *((_QWORD *)&v155 + 1) - 16LL;
            *((_QWORD *)&v155 + 1) -= 16LL;
          }
          if ( (_QWORD)v155 != v41 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v90 = &v143;
              if ( v144.m128i_i64[1] > 7uLL )
                v90 = (__int128 *)v143;
              VmlDebugTraceWithError(16808, &off_14091DCF0, v34, v90, v5);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6A52,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)v34,
              v111);
          }
          v159 = 0;
          v43 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v145
                                                                                                 + 168LL))(
                  v145,
                  L"topology/shared_vhd_vm/count",
                  &v159);
          v44 = v43;
          if ( v43 < 0 )
          {
            if ( v43 != -2147024894 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v45 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v45 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DD08, v44, v45, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A64,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v44,
                v111);
            }
            if ( (__int64)(*((_QWORD *)this + 64) - *((_QWORD *)this + 63)) >> 4 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
              {
                v46 = &v143;
                if ( v144.m128i_i64[1] > 7uLL )
                  v46 = (__int128 *)v143;
                VmlDebugTraceWithError(16808, &off_14091DD20, v44, v46, v5);
              }
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A6F,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)v44,
                v111);
            }
          }
          v47 = (__int64)(*((_QWORD *)this + 64) - *((_QWORD *)this + 63)) >> 4;
          v48 = v159;
          if ( v47 != v159 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              v49 = &v143;
              if ( v144.m128i_i64[1] > 7uLL )
                v49 = (__int128 *)v143;
              VmlDebugTraceWithError(16808, &off_14091DD38, 2147943862LL, v49, v5);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6A7A,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)0x800705B6LL,
              v111);
          }
          if ( v47 )
            break;
        }
LABEL_199:
        v83 = ((__int64 (*)(void))Vml::VmComMultiInstanceObject<Vml::VmComLocalMemStream>::CreateInstance<>)();
        Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
          &v120,
          v83);
        v84 = v120;
        v85 = (Vml::VmComMemStreamBase *)(v120 + 24);
        v160[0] = (struct Vml::VmGuid *)(v120 + 24);
        v86 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v145 + 248LL))(
                v145,
                (v120 + 24) & ((unsigned __int128)-(__int128)v120 >> 64),
                L"settings");
        if ( v86 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B2E,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v86,
            v111);
        v96 = Vml::VmComMemStreamBase::Seek(v85, v118, 0, 0);
        if ( v96 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B30,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v96,
            v111);
        v97 = Vml::VmComMultiInstanceObject<Vml::VmComLocalMemStream>::CreateInstance<>(retaddr);
        Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
          &v119,
          v97);
        v98 = v119;
        v99 = (Vml::VmComMemStreamBase *)(v119 + 24);
        *(_QWORD *)Status = v119 + 24;
        v100 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v145 + 248LL))(
                 v145,
                 (v119 + 24) & ((unsigned __int128)-(__int128)v119 >> 64),
                 L"topology");
        if ( v100 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B39,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v100,
            v111);
        v101 = Vml::VmComMemStreamBase::Seek(v99, v118, 0, 0);
        if ( v101 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B3B,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v101,
            v111);
        v102 = (struct IGroupRepository *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 98) + 280LL))(*((_QWORD *)v3 + 98));
        Vml::VmReferencePtr<IGroupRepository,Vml::VmUserReferenceTraits>::Reset(&v121);
        v121 = v102;
        *(_OWORD *)v133 = 0;
        GroupRepositoryAutoLock::GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v133, v102, 1);
        if ( SLODWORD(v133[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B41,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)LODWORD(v133[1]),
            v111);
        v103 = (*(__int64 (__fastcall **)(struct IGroupRepository *, _BYTE *, __int64 *))(*(_QWORD *)v102 + 312LL))(
                 v102,
                 v167,
                 &v154);
        if ( v103 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B46,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v103,
            v111);
        v104 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, const unsigned __int16 *))(*(_QWORD *)v154 + 256LL))(
                 v154,
                 (unsigned __int64)v160[0] & -(__int64)(v84 != 0),
                 L"settings");
        if ( v104 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B4C,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v104,
            v111);
        v105 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v154 + 256LL))(
                 v154,
                 *(_QWORD *)Status & -(__int64)(v98 != 0),
                 L"topology");
        if ( v105 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B52,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v105,
            v111);
        v106 = (*(__int64 (__fastcall **)(struct IGroupRepository *))(*(_QWORD *)v102 + 368LL))(v102);
        if ( v106 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B55,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v106,
            v111);
        GroupRepositoryAutoLock::~GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v133);
        GroupRepositoryAutoLock::~GroupRepositoryAutoLock((GroupRepositoryAutoLock *)v132);
        v8 = 0;
        v125 = 0;
      }
      v165 = 0;
      v166 = 0;
      Src = 0;
      v152 = si128;
      LOWORD(Src) = 0;
      v158 = 0;
      Uuid2 = 0;
      for ( k = 0; k < v48; ++k )
      {
        *(_OWORD *)v147 = 0;
        v148 = si128;
        LOWORD(v147[0]) = 0;
        *(_OWORD *)v149 = 0;
        v150 = si128;
        LOWORD(v149[0]) = 0;
        *(_OWORD *)v160 = 0;
        Vml::FormatString(v147, (wchar_t *)L"topology/shared_vhd_vm/vm%llu/guid");
        v51 = v147;
        if ( v148.m128i_i64[1] > 7uLL )
          v51 = (unsigned __int16 **)v147[0];
        v52 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v145 + 152LL))(
                v145,
                v51,
                v149);
        if ( v52 < 0 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            v53 = &v143;
            if ( v144.m128i_i64[1] > 7uLL )
              v53 = (__int128 *)v143;
            VmlDebugTraceWithError(16808, &off_14091DD50, (unsigned int)v52, v53, v5);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6AA3,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v52,
            v111);
        }
        v54 = (const unsigned __int16 *)v149;
        if ( v150.m128i_i64[1] > 7uLL )
          v54 = v149[0];
        Vml::VmGuid::Assign((Vml::VmGuid *)v160, v54);
        VmGuidSet::insert(&v165, v140, *((_QWORD *)&v165 + 1), v160);
        std::wstring::_Tidy_deallocate(v149);
        std::wstring::_Tidy_deallocate(v147);
        v48 = v159;
      }
      v3 = this;
      for ( m = (__int128 *)*((_QWORD *)this + 63); m != *((__int128 **)this + 64); ++m )
      {
        v88 = (_QWORD *)VmGuidSet::find(&v165, v141, m);
        if ( *v88 == *((_QWORD *)&v165 + 1) )
        {
          v161 = *m;
          *(_OWORD *)v149 = 0;
          v150 = si128;
          LOWORD(v149[0]) = 0;
          p_Uuid2 = (UUID *)&v161;
          v116 = v149;
          v147[0] = (unsigned __int16 *)retaddr;
          v147[1] = (unsigned __int16 *)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
          v148.m128i_i64[0] = 0;
          v148.m128i_i16[4] = 27316;
          *(_QWORD *)&v153 = &wil::details::functor_wrapper_void<_lambda_055d1e89baa3e0cb09851fcc1b0218da_>::`vftable';
          *((_QWORD *)&v153 + 1) = &p_Uuid2;
          wil::details::ResultFromException(v147, v87, &v153);
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            v89 = &v143;
            if ( v144.m128i_i64[1] > 7uLL )
              v89 = (__int128 *)v143;
            VmlDebugTraceWithError(16808, &off_14091D970, 2147943568LL, v89, v5);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6ABD,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80070490LL,
            v111);
        }
      }
      v56 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *))(*(_QWORD *)v145 + 152LL))(
              v145,
              L"shared_vhd_vm/shared_tracker_owner_id",
              &Src);
      if ( v56 < 0 )
      {
        IsDebugTraceEnabled = VmlIsDebugTraceEnabled(16808);
        if ( v56 != -2147024894 )
        {
          if ( IsDebugTraceEnabled )
          {
            v58 = &v143;
            if ( v144.m128i_i64[1] > 7uLL )
              v58 = (__int128 *)v143;
            VmlDebugTraceWithError(16808, &off_14091D988, (unsigned int)v56, v58, v5);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6ACD,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v56,
            v111);
        }
        if ( IsDebugTraceEnabled )
        {
          v59 = &v143;
          if ( v144.m128i_i64[1] > 7uLL )
            v59 = (__int128 *)v143;
          VmlDebugTraceWithError(16808, &off_14091D9A0, 2147942402LL, v59, v5);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AD7,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x80070002LL,
          v111);
      }
      v60 = (const unsigned __int16 *)&Src;
      if ( v152.m128i_i64[1] > 7uLL )
        v60 = (const unsigned __int16 *)Src;
      Vml::VmGuid::Assign((Vml::VmGuid *)&Uuid2, v60);
      Status[0] = 0;
      if ( UuidCompare((UUID *)((char *)this + 568), &Uuid2, Status) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
        {
          v61 = &v143;
          if ( v144.m128i_i64[1] > 7uLL )
            v61 = (__int128 *)v143;
          VmlDebugTraceWithError(16808, &off_14091D9B8, 2147942413LL, v61, v5);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AE4,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x8007000DLL,
          v111);
      }
      std::wstring::_Eos(&Src, 0);
      v62 = (*(__int64 (__fastcall **)(__int64, const char *, __int128 *))(*(_QWORD *)v145 + 152LL))(
              v145,
              L"shared_vhd_vm/shared_tracker_id",
              &Src);
      if ( v62 < 0 )
      {
        v63 = VmlIsDebugTraceEnabled(16808);
        if ( v62 != -2147024894 )
        {
          if ( v63 )
          {
            v64 = &v143;
            if ( v144.m128i_i64[1] > 7uLL )
              v64 = (__int128 *)v143;
            VmlDebugTraceWithError(16808, &off_14091D9D0, (unsigned int)v62, v64, v5);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6AF5,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v62,
            v111);
        }
        if ( v63 )
        {
          v65 = &v143;
          if ( v144.m128i_i64[1] > 7uLL )
            v65 = (__int128 *)v143;
          VmlDebugTraceWithError(16808, &off_14091D9E8, 2147942402LL, v65, v5);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AFF,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x80070002LL,
          v111);
      }
      v66 = (const unsigned __int16 *)&Src;
      if ( v152.m128i_i64[1] > 7uLL )
        v66 = (const unsigned __int16 *)Src;
      Vml::VmGuid::Assign((Vml::VmGuid *)&v158, v66);
      v160[0] = (ReplicationCoordinator *)((char *)this + 552);
      Status[0] = 0;
      if ( !UuidCompare((UUID *)((char *)this + 552), &v158, Status) )
      {
LABEL_198:
        std::wstring::_Tidy_deallocate(&Src);
        std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v165);
        goto LABEL_199;
      }
      if ( a3 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
        {
          v82 = &v143;
          if ( v144.m128i_i64[1] > 7uLL )
            v82 = (__int128 *)v143;
          VmlDebugTraceWithError(16808, &off_14091DA00, 2147942413LL, v82, v5);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B20,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)0x8007000DLL,
          v111);
      }
      if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6B08,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          v67);
      v68 = (unsigned __int32 *)((char *)this + 1424);
      CurrentThreadId = GetCurrentThreadId();
      v71 = _InterlockedCompareExchange((volatile signed __int32 *)this + 356, 1, 0);
      if ( v71 )
      {
        if ( *((_DWORD *)this + 357) == CurrentThreadId )
        {
          _InterlockedAdd((volatile signed __int32 *)this + 358, 1u);
          goto LABEL_178;
        }
        do
        {
          while ( (v71 & 1) != 0 || v71 >= 4 )
          {
            LOBYTE(v70) = 1;
            if ( !(unsigned int)RrwpLockWait((char *)this + 1424, 0xFFFFFFFFLL, v70) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2FE,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v111);
            _m_prefetchw(v68);
            v71 = *v68;
          }
          v72 = v71;
          v71 = _InterlockedCompareExchange((volatile signed __int32 *)v68, v71 + 1, v71);
        }
        while ( v71 != v72 );
      }
      _InterlockedExchange((volatile __int32 *)this + 357, CurrentThreadId);
LABEL_178:
      p_Uuid2 = (UUID *)((char *)this + 1424);
      v73 = 1;
      LOBYTE(v116) = 1;
      while ( v73 )
      {
        v74 = 1;
        BYTE12(v161) = 1;
        v75 = ReplicationCoordinator::gm_RcTlsIndex;
        LODWORD(v161) = ReplicationCoordinator::gm_RcTlsIndex;
        v76 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
        DWORD1(v161) = v76;
        DWORD2(v161) = v76 | 0x10;
        TlsSetValue(v75, (LPVOID)(v76 | 0x10));
        while ( v74 )
        {
          v77 = ReplicationPhaseManager::ProcessSharedTrackerIdChange(
                  *((ReplicationPhaseManager **)this + 97),
                  v160[0],
                  (const struct Vml::VmGuid *)&v158);
          if ( v77 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6B0E,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v77,
              v111);
          v74 = 0;
          BYTE12(v161) = 0;
        }
        TlsSetValue(v75, (LPVOID)v76);
        v73 = 0;
        LOBYTE(v116) = 0;
      }
      RrwLockRelease(v68);
      if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6B11,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          v78);
      v3 = this;
      Vml::VmSlimReaderWriterLock::AcquireExclusive((ReplicationCoordinator *)((char *)this + 1408));
      v79 = ReplicationCoordinator::gm_RcTlsIndex;
      v80 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      TlsSetValue(v79, (LPVOID)(v80 | 4LL));
      *(UUID *)((char *)this + 552) = v158;
      TlsSetValue(v79, (LPVOID)v80);
      *((_DWORD *)this + 354) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 176);
      updated = ReplicationCoordinator::UpdateSharedTrackerInfoToConfig(this);
      if ( updated < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B16,
          (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
          (const char *)(unsigned int)updated,
          v111);
      goto LABEL_198;
    }
    LeaveCriticalSection(lpCriticalSection);
    v108 = 0;
  }
  catch ( ... )
  {
    HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                           (Vml *)0x41A8,
                                           (unsigned __int16)&off_14091D8F0,
                                           v107);
    v108 = HResultFromThrownExceptionAndTrace;
    if ( HResultFromThrownExceptionAndTrace < 0 && (unsigned int)VmlIsDebugTraceEnabled(16808) )
    {
      v109 = &v143;
      if ( v144.m128i_i64[1] > 7uLL )
        v109 = (__int128 *)v143;
      VmlDebugTraceWithError(16808, &off_1408B8E38, (unsigned int)HResultFromThrownExceptionAndTrace, v109, v138);
    }
  }
  std::wstring::_Tidy_deallocate(&v143);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v162);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v155);
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v119);
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v120);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v145);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v154);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v121);
  return v108;
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
