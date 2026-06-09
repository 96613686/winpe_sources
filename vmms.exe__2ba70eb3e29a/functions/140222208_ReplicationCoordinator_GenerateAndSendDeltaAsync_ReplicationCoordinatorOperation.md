# ReplicationCoordinator::GenerateAndSendDeltaAsync(ReplicationCoordinatorOperation *)

- ea: `0x140222208`
- end: `0x14022450a`
- name: `?GenerateAndSendDeltaAsync@ReplicationCoordinator@@AEAAXPEAVReplicationCoordinatorOperation@@@Z`
- size: `8962`
- prototype: `void __fastcall(ReplicationCoordinator *__hidden this, struct ReplicationCoordinatorOperation *)`
- caller_count: `2`
- callee_count: `73`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14040847c`
- `0x14061894c`

## callees

- `0x140022640`
- `0x1400249e4`
- `0x140041630`
- `0x14004f3c4`
- `0x14005c630`
- `0x140071534`
- `0x14007bb80`
- `0x1400916d8`
- `0x1400b4590`
- `0x1400bd87c`
- `0x1400c6d70`
- `0x1400da4f0`
- `0x1400f9400`
- `0x1400fd9a8`
- `0x140154408`
- `0x14017902c`
- `0x1401879a4`
- `0x140188e18`
- `0x1401cedfc`
- `0x1401d0c6c`
- `0x1401d0d6c`
- `0x1401d3f60`
- `0x140207c10`
- `0x14021f4f8`
- `0x140221390`
- `0x14022145c`
- `0x1402221d4`
- `0x140222208`
- `0x14022f914`
- `0x1402407a4`
- `0x14029583c`
- `0x140299634`
- `0x14029db54`
- `0x1402a27fc`
- `0x1402b62c4`
- `0x1402bc110`
- `0x1402be39c`
- `0x1402f5fac`
- `0x1402f83e8`
- `0x1402fad14`
- `0x1402fcfd8`
- `0x1402fd850`
- `0x14032dd6c`
- `0x140342730`
- `0x14037c7dc`
- `0x1403b5fa0`
- `0x1403b91c8`
- `0x140471354`
- `0x1404828e0`
- `0x140482b74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140223c43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140223f21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140224326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14022435e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140223c43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140223f21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140224326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14022435e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140222441`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140223c96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140224157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140222441`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140223c96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140224157`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402223ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140222484`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402224d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402225e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402228b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402233d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223c6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223ccb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223d12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14022412e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14022418e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402241d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402223ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140222484`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402224d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402225e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402228b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402233d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223c6d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223ccb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140223d12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14022412e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14022418e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1402241d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402224ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140222607`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402226be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402228dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140222994`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402233f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402234a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223c1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223cef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223efb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402241b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402242b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140224311`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402224ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140222607`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402226be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402228dd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140222994`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402233f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402234a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223c1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223cef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140223efb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402241b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1402242b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140224311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140222591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140222867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140223385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140222591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140222867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140223385`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140222bbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140222d3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140222bbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140222d3d`
- `vmprox!SetVmErrInfo` at `0x1402223c9`
- `vmprox!SetVmErrInfo` at `0x1402223c9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14022315d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1402232db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14022315d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1402232db`

## string_xrefs

- `0x14022268f`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140222965`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x14022347c`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall ReplicationCoordinator::GenerateAndSendDeltaAsync(
        ReplicationCoordinator *this,
        struct ReplicationCoordinatorOperation *a2)
{
  struct ReplicationCoordinatorOperation *v2; // rsi
  ReplicationCoordinator *v3; // r15
  unsigned int v4; // r12d
  _QWORD *v5; // rax
  const char *v6; // r9
  char v7; // al
  char v8; // bl
  DWORD v9; // edi
  const char *v10; // r9
  signed __int32 *v11; // r12
  signed __int32 v12; // eax
  signed __int32 v13; // ebx
  char v14; // al
  char v15; // bl
  DWORD v16; // edi
  unsigned int Value; // esi
  int VmsForReplicationAction; // eax
  signed __int32 v19; // edx
  unsigned int v20; // r9d
  __int128 *i; // rbx
  __int128 *v22; // rdi
  __int128 *v23; // rbx
  __int128 *v24; // rdi
  signed __int32 v25; // eax
  signed __int32 v26; // ebx
  char v27; // al
  char v28; // bl
  DWORD v29; // edi
  unsigned int v30; // esi
  int v31; // eax
  signed __int32 v32; // edx
  __int128 *v33; // rdi
  __int128 *v34; // rbx
  __int128 v35; // xmm7
  __int128 *j; // rbx
  __int128 *v37; // rdi
  __int128 v38; // xmm6
  int v39; // eax
  unsigned int v40; // ebx
  Vml::VmSharableObject *v41; // rbx
  Vml::VmSharableObject *v42; // rcx
  __int64 v43; // rbx
  Vml::VmSharableObject *v44; // rdi
  Vml::VmSharableObject *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  __int128 *k; // rbx
  __int128 *v49; // rdi
  _QWORD *v50; // rax
  __int128 v51; // xmm6
  _QWORD *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rsi
  Vml::VmSharableObject *v55; // r12
  Vml::VmSharableObject *v56; // rcx
  int v57; // eax
  int v58; // eax
  int VmIdList; // eax
  int CurrentCycleListOfVms; // eax
  __int128 *m; // rbx
  __int128 *v62; // rdi
  _QWORD *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rsi
  Vml::VmSharableObject *v66; // r12
  Vml::VmSharableObject *v67; // rcx
  signed __int32 *v68; // rdi
  signed __int32 v69; // eax
  signed __int32 v70; // ebx
  char v71; // al
  char v72; // bl
  DWORD v73; // esi
  unsigned int v74; // r12d
  int v75; // eax
  signed __int32 v76; // edx
  __int128 n; // rdi
  _QWORD *v78; // rax
  __int64 v79; // rax
  FILETIME v80; // rbx
  int v81; // eax
  const void *v82; // rcx
  __int128 ii; // rdi
  __int128 v84; // xmm6
  _QWORD *v85; // rax
  __int64 v86; // rdx
  __int128 v87; // xmm6
  __int64 v88; // rbx
  int v89; // eax
  __int128 *v90; // rdx
  _QWORD *v91; // rax
  _QWORD *v92; // rax
  __int128 v93; // xmm6
  _QWORD *v94; // rax
  void **v95; // rax
  const char *v96; // r9
  char v97; // al
  char v98; // bl
  DWORD v99; // edi
  unsigned int v100; // esi
  const char *v101; // r9
  int v102; // eax
  int v103; // ebx
  int v104; // eax
  const struct std::nothrow_t *v105; // rdx
  __int64 v106; // rbx
  struct _RTL_CRITICAL_SECTION *v107; // rsi
  __int64 v108; // rdx
  const struct Vml::ExceptionTraceParameters *v109; // r8
  unsigned int v110; // r12d
  const struct _EVENT_DESCRIPTOR *RcEventDescriptorFromErrorCode; // rax
  __int64 *v112; // r8
  __int64 v113; // rdx
  const struct _EVENT_DESCRIPTOR *FrEventDescriptorFromErrorCode; // rax
  __int64 v115; // r10
  const char *v116; // r9
  char v117; // al
  char v118; // di
  DWORD v119; // esi
  unsigned int v120; // r12d
  const char *v121; // r9
  unsigned int TimeoutInterval; // edi
  __int64 v123; // [rsp+20h] [rbp-758h]
  unsigned int v124[2]; // [rsp+28h] [rbp-750h]
  unsigned int ConsistencyLevel; // [rsp+50h] [rbp-728h] BYREF
  unsigned int HResultFromThrownExceptionAndTrace; // [rsp+54h] [rbp-724h] BYREF
  int v127; // [rsp+58h] [rbp-720h]
  int v128[2]; // [rsp+60h] [rbp-718h]
  unsigned int v129; // [rsp+68h] [rbp-710h] BYREF
  unsigned int v130; // [rsp+6Ch] [rbp-70Ch]
  struct ReplicationCoordinatorOperation *v131; // [rsp+70h] [rbp-708h]
  __int128 v132; // [rsp+78h] [rbp-700h] BYREF
  DWORD v133; // [rsp+88h] [rbp-6F0h]
  unsigned int v134; // [rsp+8Ch] [rbp-6ECh]
  unsigned int v135; // [rsp+90h] [rbp-6E8h]
  char v136; // [rsp+94h] [rbp-6E4h]
  int v137; // [rsp+98h] [rbp-6E0h]
  DWORD dwTlsIndex; // [rsp+9Ch] [rbp-6DCh]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-6D8h]
  int v140; // [rsp+A8h] [rbp-6D0h]
  DWORD v141; // [rsp+B0h] [rbp-6C8h]
  unsigned int v142; // [rsp+B4h] [rbp-6C4h]
  int v143; // [rsp+B8h] [rbp-6C0h]
  char v144; // [rsp+BCh] [rbp-6BCh]
  DWORD v145; // [rsp+C0h] [rbp-6B8h]
  unsigned int v146; // [rsp+C4h] [rbp-6B4h]
  int v147; // [rsp+C8h] [rbp-6B0h]
  char v148; // [rsp+CCh] [rbp-6ACh]
  wil::details::in1diag3 *v149; // [rsp+D0h] [rbp-6A8h] BYREF
  const char *v150; // [rsp+D8h] [rbp-6A0h]
  __int64 v151; // [rsp+E0h] [rbp-698h]
  __int16 v152; // [rsp+E8h] [rbp-690h]
  DWORD v153; // [rsp+F0h] [rbp-688h]
  unsigned int v154; // [rsp+F4h] [rbp-684h]
  int v155; // [rsp+F8h] [rbp-680h]
  char v156; // [rsp+FCh] [rbp-67Ch]
  LPVOID lpTlsValue; // [rsp+100h] [rbp-678h]
  _QWORD *v158; // [rsp+108h] [rbp-670h]
  ReplicationCoordinator *v159; // [rsp+110h] [rbp-668h]
  struct ReplicationCoordinatorOperation *v160; // [rsp+118h] [rbp-660h]
  char *v161; // [rsp+120h] [rbp-658h]
  char v162; // [rsp+128h] [rbp-650h]
  char *v163; // [rsp+130h] [rbp-648h]
  char v164; // [rsp+138h] [rbp-640h]
  char *v165; // [rsp+140h] [rbp-638h]
  char v166; // [rsp+148h] [rbp-630h]
  _QWORD v167[3]; // [rsp+150h] [rbp-628h] BYREF
  _QWORD v168[3]; // [rsp+168h] [rbp-610h] BYREF
  __int16 v169; // [rsp+180h] [rbp-5F8h]
  _QWORD v170[3]; // [rsp+188h] [rbp-5F0h] BYREF
  __int16 v171; // [rsp+1A0h] [rbp-5D8h]
  _BYTE v172[8]; // [rsp+1B0h] [rbp-5C8h] BYREF
  _BYTE v173[8]; // [rsp+1B8h] [rbp-5C0h] BYREF
  _BYTE v174[8]; // [rsp+1C0h] [rbp-5B8h] BYREF
  _BYTE v175[8]; // [rsp+1C8h] [rbp-5B0h] BYREF
  _BYTE v176[8]; // [rsp+1D0h] [rbp-5A8h] BYREF
  _BYTE v177[8]; // [rsp+1D8h] [rbp-5A0h] BYREF
  _BYTE v178[8]; // [rsp+1E0h] [rbp-598h] BYREF
  _BYTE v179[8]; // [rsp+1E8h] [rbp-590h] BYREF
  _BYTE v180[8]; // [rsp+1F0h] [rbp-588h] BYREF
  _BYTE v181[8]; // [rsp+1F8h] [rbp-580h] BYREF
  _BYTE v182[8]; // [rsp+200h] [rbp-578h] BYREF
  _BYTE v183[8]; // [rsp+208h] [rbp-570h] BYREF
  _BYTE v184[8]; // [rsp+210h] [rbp-568h] BYREF
  _BYTE v185[8]; // [rsp+218h] [rbp-560h] BYREF
  _BYTE v186[8]; // [rsp+220h] [rbp-558h] BYREF
  _OWORD v187[2]; // [rsp+228h] [rbp-550h] BYREF
  _OWORD v188[2]; // [rsp+248h] [rbp-530h] BYREF
  _BYTE v189[16]; // [rsp+268h] [rbp-510h] BYREF
  _BYTE v190[16]; // [rsp+278h] [rbp-500h] BYREF
  _BYTE v191[16]; // [rsp+288h] [rbp-4F0h] BYREF
  _BYTE v192[16]; // [rsp+298h] [rbp-4E0h] BYREF
  _BYTE v193[16]; // [rsp+2A8h] [rbp-4D0h] BYREF
  _BYTE v194[16]; // [rsp+2B8h] [rbp-4C0h] BYREF
  _BYTE v195[16]; // [rsp+2C8h] [rbp-4B0h] BYREF
  _BYTE v196[16]; // [rsp+2D8h] [rbp-4A0h] BYREF
  _BYTE v197[16]; // [rsp+2E8h] [rbp-490h] BYREF
  _BYTE v198[16]; // [rsp+2F8h] [rbp-480h] BYREF
  struct _GUID v199; // [rsp+308h] [rbp-470h] BYREF
  _BYTE v200[16]; // [rsp+318h] [rbp-460h] BYREF
  _BYTE v201[16]; // [rsp+328h] [rbp-450h] BYREF
  _BYTE v202[16]; // [rsp+338h] [rbp-440h] BYREF
  _BYTE v203[16]; // [rsp+348h] [rbp-430h] BYREF
  _BYTE v204[16]; // [rsp+358h] [rbp-420h] BYREF
  _BYTE v205[16]; // [rsp+368h] [rbp-410h] BYREF
  _BYTE v206[16]; // [rsp+378h] [rbp-400h] BYREF
  _BYTE v207[16]; // [rsp+388h] [rbp-3F0h] BYREF
  struct _GUID v208; // [rsp+398h] [rbp-3E0h] BYREF
  _BYTE v209[16]; // [rsp+3A8h] [rbp-3D0h] BYREF
  _BYTE v210[16]; // [rsp+3B8h] [rbp-3C0h] BYREF
  _BYTE v211[16]; // [rsp+3C8h] [rbp-3B0h] BYREF
  _BYTE v212[16]; // [rsp+3D8h] [rbp-3A0h] BYREF
  _BYTE v213[16]; // [rsp+3E8h] [rbp-390h] BYREF
  _BYTE v214[16]; // [rsp+3F8h] [rbp-380h] BYREF
  _BYTE v215[16]; // [rsp+408h] [rbp-370h] BYREF
  _BYTE v216[16]; // [rsp+418h] [rbp-360h] BYREF
  _BYTE v217[16]; // [rsp+428h] [rbp-350h] BYREF
  _BYTE v218[16]; // [rsp+438h] [rbp-340h] BYREF
  _BYTE v219[16]; // [rsp+448h] [rbp-330h] BYREF
  _BYTE v220[24]; // [rsp+458h] [rbp-320h] BYREF
  __int128 v221; // [rsp+470h] [rbp-308h] BYREF
  FILETIME FileTime1; // [rsp+480h] [rbp-2F8h] BYREF
  Vml::VmSharableObject *v223; // [rsp+488h] [rbp-2F0h] BYREF
  __int128 v224; // [rsp+490h] [rbp-2E8h] BYREF
  __int64 v225; // [rsp+4A0h] [rbp-2D8h]
  __int128 Buf1; // [rsp+4B0h] [rbp-2C8h] BYREF
  __int128 v227; // [rsp+4C0h] [rbp-2B8h] BYREF
  __int64 v228; // [rsp+4D0h] [rbp-2A8h]
  __int128 v229; // [rsp+4D8h] [rbp-2A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+4E8h] [rbp-290h] BYREF
  __int128 v231; // [rsp+4F0h] [rbp-288h] BYREF
  _OWORD v232[2]; // [rsp+500h] [rbp-278h] BYREF
  __int128 v233; // [rsp+520h] [rbp-258h] BYREF
  __int64 v234; // [rsp+530h] [rbp-248h]
  __int128 v235; // [rsp+538h] [rbp-240h] BYREF
  __int64 v236; // [rsp+548h] [rbp-230h]
  FILETIME FileTime2; // [rsp+550h] [rbp-228h] BYREF
  __int128 v238; // [rsp+558h] [rbp-220h] BYREF
  __int128 v239; // [rsp+568h] [rbp-210h] BYREF
  __int128 Buf2; // [rsp+578h] [rbp-200h] BYREF
  __int128 *v241; // [rsp+588h] [rbp-1F0h]
  __int128 v242; // [rsp+590h] [rbp-1E8h] BYREF
  __int64 v243; // [rsp+5A0h] [rbp-1D8h]
  __int128 v244; // [rsp+5A8h] [rbp-1D0h] BYREF
  __m128i si128; // [rsp+5B8h] [rbp-1C0h]
  void **v246; // [rsp+5C8h] [rbp-1B0h] BYREF
  __int128 *p_Buf2; // [rsp+5D0h] [rbp-1A8h]
  __int128 v248; // [rsp+5E0h] [rbp-198h] BYREF
  __int128 v249; // [rsp+5F0h] [rbp-188h] BYREF
  __int128 v250; // [rsp+600h] [rbp-178h] BYREF
  __int128 v251; // [rsp+610h] [rbp-168h] BYREF
  __int128 v252; // [rsp+620h] [rbp-158h] BYREF
  _QWORD v253[2]; // [rsp+630h] [rbp-148h] BYREF
  _QWORD v254[2]; // [rsp+640h] [rbp-138h] BYREF
  unsigned __int8 v255[16]; // [rsp+650h] [rbp-128h] BYREF
  int v256; // [rsp+660h] [rbp-118h]
  GUID v257; // [rsp+664h] [rbp-114h]
  int v258; // [rsp+674h] [rbp-104h]
  _DWORD v259[3]; // [rsp+680h] [rbp-F8h] BYREF
  __int128 v260; // [rsp+68Ch] [rbp-ECh]
  __int128 v261; // [rsp+69Ch] [rbp-DCh]
  __int128 v262; // [rsp+6ACh] [rbp-CCh]
  __int128 v263; // [rsp+6BCh] [rbp-BCh]
  __int128 v264; // [rsp+6CCh] [rbp-ACh]
  __int128 v265; // [rsp+6DCh] [rbp-9Ch]
  __int128 v266; // [rsp+6ECh] [rbp-8Ch]
  __int128 v267; // [rsp+6FCh] [rbp-7Ch]
  __int128 v268; // [rsp+70Ch] [rbp-6Ch]
  int v269; // [rsp+71Ch] [rbp-5Ch]
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+0h]

  v2 = a2;
  v131 = a2;
  v3 = this;
  v159 = this;
  v160 = a2;
  v137 = 1;
  v4 = 0;
  SystemTimeAsFileTime = 0;
  v248 = 0;
  v129 = 0;
  v250 = 0;
  v223 = 0;
  v239 = 0;
  std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(&v239);
  v249 = 0;
  v242 = 0;
  v243 = 0;
  v227 = 0;
  v228 = 0;
  v238 = 0;
  std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(&v238);
  v224 = 0;
  v225 = 0;
  v229 = 0;
  std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(&v229);
  v231 = 0;
  std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>(&v231);
  v127 = 3;
  FileTime2 = 0;
  v233 = 0;
  v234 = 0;
  v235 = 0;
  v236 = 0;
  v232[0] = 0;
  v232[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v232[0]) = 0;
  v5 = (_QWORD *)((char *)v3 + 96);
  *(_QWORD *)v128 = (char *)v3 + 96;
  if ( *((_QWORD *)v3 + 15) > 7u )
  {
    v5 = (_QWORD *)*v5;
    *(_QWORD *)v128 = v5;
  }
  v158 = v5;
  ReplicationCoordinator::GetName(v3, v232);
  v130 = 0;
  SetVmErrInfo(0);
  v248 = *((_OWORD *)v2 + 5);
  v140 = *((_DWORD *)v2 + 40);
  HResultFromThrownExceptionAndTrace = *((_DWORD *)v2 + 38);
  if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 0x1E) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x282C,
      (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
      v6);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v3 + 1472);
  *(_QWORD *)&v132 = (char *)v3 + 1472;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 1472));
  v7 = 1;
  BYTE8(v132) = 1;
  try
  {
    while ( v7 )
    {
      v8 = 1;
      v136 = 1;
      v9 = ReplicationCoordinator::gm_RcTlsIndex;
      dwTlsIndex = ReplicationCoordinator::gm_RcTlsIndex;
      v133 = ReplicationCoordinator::gm_RcTlsIndex;
      lpTlsValue = TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      v134 = (unsigned int)lpTlsValue;
      v135 = (unsigned int)lpTlsValue | 1;
      TlsSetValue(v9, (LPVOID)((unsigned int)lpTlsValue | 1));
      while ( v8 )
      {
        if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x282E,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            v10);
        if ( (unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 64) )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            LODWORD(v123) = v128[0];
            VmlDebugTraceWithError(16808, &off_14091FF28, 2147500036LL);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x282E,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80004004LL,
            v123);
        }
        if ( v140 == 1 )
        {
          v11 = (signed __int32 *)((char *)v3 + 1424);
          v12 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 356, 4, 0);
          v13 = v12;
          if ( v12 )
          {
            if ( (v12 & 1) != 0 && *((_DWORD *)v3 + 357) == GetCurrentThreadId() )
            {
              _InterlockedIncrement((volatile signed __int32 *)v3 + 358);
            }
            else
            {
              do
              {
                while ( (v13 & 1) != 0 )
                {
                  if ( !(unsigned int)RrwpLockWait((char *)v3 + 1424, 0xFFFFFFFFLL, 0) )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x249,
                      (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                      (const char *)0x102,
                      v123);
                  _m_prefetchw(v11);
                  v13 = *v11;
                }
                v19 = v13;
                v13 = _InterlockedCompareExchange(v11, v13 + 4, v13);
              }
              while ( v13 != v19 );
            }
          }
          v161 = (char *)v3 + 1424;
          v14 = 1;
          v162 = 1;
          while ( v14 )
          {
            v15 = 1;
            v156 = 1;
            v16 = ReplicationCoordinator::gm_RcTlsIndex;
            v153 = ReplicationCoordinator::gm_RcTlsIndex;
            Value = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
            v154 = Value;
            v155 = Value | 8;
            TlsSetValue(v16, (LPVOID)(Value | 8));
            while ( v15 )
            {
              VmsForReplicationAction = ReplicationPhaseManager::GetVmsForReplicationAction(
                                          *((_QWORD *)v3 + 97),
                                          4,
                                          &v242);
              if ( VmsForReplicationAction < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2840,
                  (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                  (const char *)(unsigned int)VmsForReplicationAction,
                  v123);
              v15 = 0;
              v156 = 0;
            }
            TlsSetValue(v16, (LPVOID)Value);
            v14 = 0;
            v162 = 0;
          }
          RrwLockRelease((char *)v3 + 1424);
          v22 = (__int128 *)*((_QWORD *)&v242 + 1);
          for ( i = (__int128 *)v242; i != v22; ++i )
          {
            v221 = *i;
            Buf1 = 0;
            ReplicationCoordinator::FindVmOperation(
              v3,
              (const struct Vml::VmGuid *)&v221,
              (struct Vml::VmGuid *)&Buf1,
              v20);
            Buf2 = 0;
            if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
              VmGuidSet::insert(&v227, v197, &v221);
          }
          v24 = (__int128 *)*((_QWORD *)&v227 + 1);
          v23 = (__int128 *)v227;
          if ( (_QWORD)v227 == *((_QWORD *)&v227 + 1) )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
            {
              LODWORD(v123) = v128[0];
              VmlDebugTraceWithError(16808, &off_14091FF40, 2147947423LL);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x285F,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)0x8007139FLL,
              v123);
          }
          do
          {
            Buf1 = *v23;
            if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,0>>::find(
                              (char *)v3 + 5472,
                              v181,
                              &Buf1) == *((_QWORD *)v3 + 684) )
              VmGuidSet::insert(&v224, v198, &Buf1);
            ++v23;
          }
          while ( v23 != v24 );
          v25 = _InterlockedCompareExchange(v11, 4, 0);
          v26 = v25;
          if ( v25 )
          {
            if ( (v25 & 1) != 0 && *((_DWORD *)v3 + 357) == GetCurrentThreadId() )
            {
              _InterlockedIncrement((volatile signed __int32 *)v3 + 358);
            }
            else
            {
              do
              {
                while ( (v26 & 1) != 0 )
                {
                  if ( !(unsigned int)RrwpLockWait((char *)v3 + 1424, 0xFFFFFFFFLL, 0) )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x249,
                      (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                      (const char *)0x102,
                      v123);
                  _m_prefetchw(v11);
                  v26 = *v11;
                }
                v32 = v26;
                v26 = _InterlockedCompareExchange(v11, v26 + 4, v26);
              }
              while ( v26 != v32 );
            }
          }
          v163 = (char *)v3 + 1424;
          v27 = 1;
          v164 = 1;
          while ( v27 )
          {
            v28 = 1;
            v144 = 1;
            v29 = ReplicationCoordinator::gm_RcTlsIndex;
            v141 = ReplicationCoordinator::gm_RcTlsIndex;
            v30 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
            v142 = v30;
            v143 = v30 | 8;
            TlsSetValue(v29, (LPVOID)(v30 | 8));
            while ( v28 )
            {
              v31 = ReplicationPhaseManager::GetVmsForReplicationAction(*((_QWORD *)v3 + 97), 41, &v233);
              if ( v31 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2876,
                  (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                  (const char *)(unsigned int)v31,
                  v123);
              v28 = 0;
              v144 = 0;
            }
            TlsSetValue(v29, (LPVOID)v30);
            v27 = 0;
            v164 = 0;
          }
          RrwLockRelease((char *)v3 + 1424);
          v33 = (__int128 *)*((_QWORD *)&v233 + 1);
          v34 = (__int128 *)v233;
          if ( (_QWORD)v233 != *((_QWORD *)&v233 + 1) )
          {
            while ( v34 != v33 )
            {
              Buf1 = *v34;
              if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,0>>::find(
                                (char *)v3 + 616,
                                v173,
                                &Buf1) == *((_QWORD *)v3 + 77) )
              {
                v221 = 0;
                FileTime1 = 0;
                Vml::VmGuid::Create((Vml::VmGuid *)&v221);
                FileTime1 = (FILETIME)ReplicationCoordinator::CreateCDPReferencePoint(v3, &v221, 3);
                if ( !*(_QWORD *)&FileTime1 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x28A7,
                    (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                    (const char *)0x80004003LL,
                    v123);
                v35 = (__int128)*ReplicationCoordinator::CreateGroupRecoverySnapshot(v3, &v199, 0x280u);
                v37 = (__int128 *)*((_QWORD *)&v233 + 1);
                for ( j = (__int128 *)v233; j != v37; ++j )
                {
                  Buf2 = *j;
                  if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,0>>::find(
                                    (char *)v3 + 616,
                                    v185,
                                    &Buf2) == *((_QWORD *)v3 + 77) )
                  {
                    v38 = v221;
                    *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                             (char *)v3 + 616,
                                             v200,
                                             &Buf2)
                              + 44LL) = v38;
                    *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                             (char *)v3 + 632,
                                             v201,
                                             &Buf2)
                              + 44LL) = v35;
                  }
                }
                Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&FileTime1);
                break;
              }
              ++v34;
            }
          }
          if ( (unsigned int)ReplicationCoordinator::IsGroupVssSnapshotRequired(v3)
            && (Buf1 = 0,
                v39 = memcmp_0((char *)v3 + 552, &Buf1, 0x10u),
                (__int64)(*((_QWORD *)v3 + 17) - *((_QWORD *)v3 + 16)) >> 4 == ((__int64)(*((_QWORD *)&v224 + 1) - v224) >> 4)
                                                                             - (v39 != 0))
            && (_QWORD)v233 == *((_QWORD *)&v233 + 1) )
          {
            GetSystemTimeAsFileTime((LPFILETIME)v3 + 175);
            v40 = 1;
            v127 = 1;
          }
          else
          {
            v40 = v127;
          }
          if ( (_QWORD)v224 != *((_QWORD *)&v224 + 1) )
          {
            Vml::VmGuid::Create((Vml::VmGuid *)&v249);
            Vml::VmGuid::Create((Vml::VmGuid *)&v250);
            v41 = (Vml::VmSharableObject *)ReplicationCoordinator::CreateCDPReferencePoint(v3, &v250, v40);
            v42 = v223;
            v223 = 0;
            if ( v42 )
              Vml::VmSharableObject::DecrementUserCount(v42);
            v223 = v41;
            if ( !v41 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x28E5,
                (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                (const char *)0x80004003LL,
                v123);
            FileTime2 = *(FILETIME *)(*(__int64 (__fastcall **)(Vml::VmSharableObject *, _BYTE *))(*(_QWORD *)v41 + 120LL))(
                                       v41,
                                       v183);
            v43 = *(_QWORD *)std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePoint,Vml::VmUserReferenceTraits>>::_Try_emplace<Vml::VmGuid const &,>(
                               &v231,
                               v202,
                               &v250);
            v44 = v223;
            v223 = 0;
            v45 = *(Vml::VmSharableObject **)(v43 + 48);
            *(_QWORD *)(v43 + 48) = 0;
            if ( v45 )
              Vml::VmSharableObject::DecrementUserCount(v45);
            *(_QWORD *)(v43 + 48) = v44;
          }
          if ( (unsigned int)VmlIsDebugTraceEnabled(49576) )
          {
            *(_QWORD *)v124 = (__int64)(*((_QWORD *)&v224 + 1) - v224) >> 4;
            v123 = (__int64)(*((_QWORD *)&v227 + 1) - v227) >> 4;
            VmlDebugTraceEx(49576, &off_14091FE78);
          }
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          *((struct _FILETIME *)v3 + 192) = SystemTimeAsFileTime;
          if ( *((_QWORD *)&v224 + 1) - (_QWORD)v224 == *((_QWORD *)&v227 + 1) - (_QWORD)v227 )
          {
            v46 = std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePoint,Vml::VmUserReferenceTraits>>::_Try_emplace<Vml::VmGuid const &,>(
                    &v231,
                    v203,
                    &v250);
            ConsistencyLevel = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v46 + 48LL) + 112LL))(*(_QWORD *)(*(_QWORD *)v46 + 48LL));
          }
          else
          {
            ConsistencyLevel = 2;
          }
          v47 = ReplicationCoordinatorOperation::SetContext(v131, 4, &v227);
          if ( v47 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x290F,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v47,
              v123);
          v49 = (__int128 *)*((_QWORD *)&v227 + 1);
          for ( k = (__int128 *)v227; k != v49; ++k )
          {
            v221 = *k;
            v50 = (_QWORD *)VmGuidSet::find(&v224, v184, &v221);
            if ( *v50 == *((_QWORD *)&v224 + 1) )
            {
              v252 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                              (char *)v3 + 5472,
                                              v204,
                                              &v221)
                               + 44LL);
              *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                       &v229,
                                       v205,
                                       &v221)
                        + 44LL) = v252;
              v52 = (_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<IVmmsCDPReferencePoint,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsCDPReferencePoint,Vml::VmUserReferenceTraits>>>,0>>::find(
                                &v231,
                                v172,
                                &v252);
              if ( *v52 == (_QWORD)v231 )
              {
                v167[0] = &v223;
                v167[1] = v3;
                v167[2] = &v252;
                v170[0] = retaddr;
                v170[1] = "onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
                v170[2] = 0;
                v171 = 10534;
                v253[0] = &wil::details::functor_wrapper_void<_lambda_297657faf1b52f28c2911355fe512f30_>::`vftable';
                v253[1] = v167;
                wil::details::ResultFromException(v170, v53, v253);
                if ( v223 )
                {
                  v54 = *(_QWORD *)std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePoint,Vml::VmUserReferenceTraits>>::_Try_emplace<Vml::VmGuid const &,>(
                                     &v231,
                                     v206,
                                     &v252);
                  v55 = v223;
                  v223 = 0;
                  v56 = *(Vml::VmSharableObject **)(v54 + 48);
                  *(_QWORD *)(v54 + 48) = 0;
                  if ( v56 )
                    Vml::VmSharableObject::DecrementUserCount(v56);
                  *(_QWORD *)(v54 + 48) = v55;
                }
                else
                {
                  VmGuidSet::insert(&v235, v207, &v221);
                }
              }
            }
            else
            {
              v51 = v250;
              *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                       &v229,
                                       v196,
                                       &v221)
                        + 44LL) = v51;
            }
          }
          ReplicationCoordinatorOperation::SetTransferId(v131, (const struct Vml::VmGuid *)&v249);
          ReplicationCoordinatorOperation::SetReferencePointIdMap(v131, &v229);
          if ( (_QWORD)v224 != *((_QWORD *)&v224 + 1) )
            ReplicationCoordinatorOperation::SetCurrentCycleListOfVms(v131, (const struct VmGuidSet *)&v224);
          ReplicationCoordinatorOperation::SetDeltaCreationTime(v131, &SystemTimeAsFileTime);
          ReplicationCoordinatorOperation::SetConsistencyLevel(v131, ConsistencyLevel);
          v57 = ReplicationCoordinatorOperation::SaveConfiguration(v131);
          if ( v57 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2940,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v57,
              v123);
          v58 = ReplicationCoordinator::SaveOperation(v3, (const struct Vml::VmGuid *)&v248, v131);
          if ( v58 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2944,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v58,
              v123);
        }
        else
        {
          VmIdList = ReplicationCoordinatorOperation::GetVmIdList(v2, (struct VmGuidSet *)&v227);
          if ( VmIdList < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x294A,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)VmIdList,
              v123);
          v249 = (__int128)*ReplicationCoordinatorOperation::GetTransferId(v2, &v208);
          ReplicationCoordinatorOperation::GetReferencePointIdMap(v2, &v229);
          SystemTimeAsFileTime = **(struct _FILETIME **)&ReplicationCoordinatorOperation::GetDeltaCreationTime(v2);
          CurrentCycleListOfVms = ReplicationCoordinatorOperation::GetCurrentCycleListOfVms(
                                    v2,
                                    (struct VmGuidSet *)&v224);
          if ( CurrentCycleListOfVms < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2953,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)CurrentCycleListOfVms,
              v123);
          ConsistencyLevel = ReplicationCoordinatorOperation::GetConsistencyLevel(v2);
          if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)v3 + 192) > 0 )
            *((struct _FILETIME *)v3 + 192) = SystemTimeAsFileTime;
          v62 = (__int128 *)*((_QWORD *)&v227 + 1);
          for ( m = (__int128 *)v227; m != v62; ++m )
          {
            Buf1 = *m;
            v251 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                            &v229,
                                            v209,
                                            &Buf1)
                             + 44LL);
            v63 = (_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<IVmmsCDPReferencePoint,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsCDPReferencePoint,Vml::VmUserReferenceTraits>>>,0>>::find(
                              &v231,
                              v174,
                              &v251);
            if ( *v63 == (_QWORD)v231 )
            {
              *(_QWORD *)&v244 = &v223;
              *((_QWORD *)&v244 + 1) = v3;
              si128.m128i_i64[0] = (__int64)&v251;
              v168[0] = retaddr;
              v168[1] = "onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
              v168[2] = 0;
              v169 = 10599;
              v254[0] = &wil::details::functor_wrapper_void<_lambda_6598de56bac073dc2dd3c7528c924d4c_>::`vftable';
              v254[1] = &v244;
              wil::details::ResultFromException(v168, v64, v254);
              if ( v223 )
              {
                if ( (_QWORD)v224 != *((_QWORD *)&v224 + 1) )
                {
                  FileTime1 = 0;
                  FileTime1 = *(FILETIME *)(*(__int64 (__fastcall **)(Vml::VmSharableObject *, _BYTE *))(*(_QWORD *)v223 + 120LL))(
                                             v223,
                                             v175);
                  if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
                    FileTime2 = FileTime1;
                }
                v65 = *(_QWORD *)std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePoint,Vml::VmUserReferenceTraits>>::_Try_emplace<Vml::VmGuid const &,>(
                                   &v231,
                                   v210,
                                   &v251);
                v66 = v223;
                v223 = 0;
                v67 = *(Vml::VmSharableObject **)(v65 + 48);
                *(_QWORD *)(v65 + 48) = 0;
                if ( v67 )
                  Vml::VmSharableObject::DecrementUserCount(v67);
                *(_QWORD *)(v65 + 48) = v66;
              }
              else
              {
                VmGuidSet::insert(&v235, v211, &Buf1);
              }
            }
          }
          v68 = (signed __int32 *)((char *)v3 + 1424);
          v69 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 356, 4, 0);
          v70 = v69;
          if ( v69 )
          {
            if ( (v69 & 1) != 0 && *((_DWORD *)v3 + 357) == GetCurrentThreadId() )
            {
              _InterlockedIncrement((volatile signed __int32 *)v3 + 358);
            }
            else
            {
              do
              {
                while ( (v70 & 1) != 0 )
                {
                  if ( !(unsigned int)RrwpLockWait((char *)v3 + 1424, 0xFFFFFFFFLL, 0) )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x249,
                      (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                      (const char *)0x102,
                      v123);
                  _m_prefetchw(v68);
                  v70 = *v68;
                }
                v76 = v70;
                v70 = _InterlockedCompareExchange(v68, v70 + 4, v70);
              }
              while ( v70 != v76 );
            }
          }
          v165 = (char *)v3 + 1424;
          v71 = 1;
          v166 = 1;
          while ( v71 )
          {
            v72 = 1;
            v148 = 1;
            v73 = ReplicationCoordinator::gm_RcTlsIndex;
            v145 = ReplicationCoordinator::gm_RcTlsIndex;
            v74 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
            v146 = v74;
            v147 = v74 | 8;
            TlsSetValue(v73, (LPVOID)(v74 | 8));
            while ( v72 )
            {
              v75 = ReplicationPhaseManager::GetVmsForReplicationAction(*((_QWORD *)v3 + 97), 41, &v233);
              if ( v75 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2985,
                  (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
                  (const char *)(unsigned int)v75,
                  v123);
              v72 = 0;
              v148 = 0;
            }
            TlsSetValue(v73, (LPVOID)v74);
            v71 = 0;
            v166 = 0;
          }
          RrwLockRelease((char *)v3 + 1424);
        }
        for ( n = v227; (_QWORD)n != *((_QWORD *)&n + 1); *(_QWORD *)&n = n + 16 )
        {
          v221 = *(_OWORD *)n;
          Buf1 = 0;
          v78 = (_QWORD *)VmGuidSet::find(&v235, v176, &v221);
          if ( *v78 == *((_QWORD *)&v235 + 1) )
          {
            Buf1 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                            &v229,
                                            v212,
                                            &v221)
                             + 44LL);
            v79 = std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePoint,Vml::VmUserReferenceTraits>>::_Try_emplace<Vml::VmGuid const &,>(
                    &v231,
                    v213,
                    &Buf1);
            (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(*(_QWORD *)v79 + 48LL) + 160LL))(
              *(_QWORD *)(*(_QWORD *)v79 + 48LL),
              &v239);
            v80 = *(FILETIME *)v239;
            FileTime1 = *(FILETIME *)v239;
            while ( !*(_BYTE *)(*(_QWORD *)&v80 + 25LL) )
            {
              v81 = memcmp_0(&v221, (char *)v3 + 552, 0x10u);
              v82 = (const void *)(*(_QWORD *)&v80 + 44LL);
              if ( v81 )
              {
                if ( !memcmp_0(v82, &v221, 0x10u) )
                {
                  v187[0] = *(_OWORD *)(*(_QWORD *)&v80 + 44LL);
                  v187[1] = *(_OWORD *)(*(_QWORD *)&v80 + 28LL);
                  std::map<Vml::VmGuid,Vml::VmGuid>::insert<std::pair<Vml::VmGuid,Vml::VmGuid>,0>(&v238, v215, v187);
                  break;
                }
              }
              else if ( !memcmp_0(v82, (char *)v3 + 568, 0x10u) )
              {
                v188[0] = *(_OWORD *)((char *)v3 + 552);
                v188[1] = *(_OWORD *)(*(_QWORD *)&v80 + 28LL);
                std::map<Vml::VmGuid,Vml::VmGuid>::insert<std::pair<Vml::VmGuid,Vml::VmGuid>,0>(&v238, v214, v188);
                break;
              }
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>>>,std::_Iterator_base0>::operator++(&FileTime1);
              v80 = FileTime1;
            }
          }
        }
        ReplicationCoordinator::AddVmOperation(v3, (const struct VmGuidSet *)&v227, (const struct Vml::VmGuid *)&v248);
        v137 = 0;
        for ( ii = v227; (_QWORD)ii != *((_QWORD *)&ii + 1); *(_QWORD *)&ii = ii + 16 )
        {
          v84 = *(_OWORD *)ii;
          _SEND_DELTA_REPLICATION_ACTION_INPUT::_SEND_DELTA_REPLICATION_ACTION_INPUT((_SEND_DELTA_REPLICATION_ACTION_INPUT *)v259);
          *(GUID *)v255 = GUID_NULL;
          v256 = 0;
          v257 = GUID_NULL;
          v258 = 0;
          v221 = v84;
          Buf1 = 0;
          v259[2] = memcmp_0(&v221, (char *)v3 + 552, 0x10u) == 0 ? 2 : 0;
          v259[0] = 3;
          v259[1] = 3;
          v260 = *((_OWORD *)v3 + 5);
          v261 = v248;
          v262 = v84;
          v85 = (_QWORD *)VmGuidSet::find(&v233, v177, &v221);
          if ( *v85 != *((_QWORD *)&v233 + 1) )
          {
            FileTime1 = 0;
            v87 = 0;
            *(_QWORD *)&Buf2 = &FileTime1;
            *((_QWORD *)&Buf2 + 1) = v3;
            v241 = &v221;
            v149 = retaddr;
            v150 = "onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
            v151 = 0;
            v152 = 10710;
            v246 = &wil::details::functor_wrapper_void<_lambda_209705e279d523fa0b298e593564a588_>::`vftable';
            p_Buf2 = &Buf2;
            wil::details::ResultFromException(&v149, v86, &v246);
            if ( FileTime1 )
            {
              (*(void (__fastcall **)(FILETIME, __int128 *))(**(_QWORD **)&FileTime1 + 160LL))(FileTime1, &v239);
              v88 = *(_QWORD *)v239;
              *(_QWORD *)&Buf2 = *(_QWORD *)v239;
              while ( !*(_BYTE *)(v88 + 25) )
              {
                v89 = memcmp_0(&v221, (char *)v3 + 552, 0x10u);
                v90 = (__int128 *)((char *)v3 + 568);
                if ( v89 )
                  v90 = &v221;
                if ( !memcmp_0((const void *)(v88 + 44), v90, 0x10u) )
                {
                  v87 = *(_OWORD *)(v88 + 28);
                  break;
                }
                std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>>>,std::_Iterator_base0>::operator++(&Buf2);
                v88 = Buf2;
              }
              v267 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                              (char *)v3 + 616,
                                              v217,
                                              &v221)
                               + 44LL);
              v266 = v87;
              v268 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                              (char *)v3 + 632,
                                              v218,
                                              &v221)
                               + 44LL);
            }
            else
            {
              VmGuidSet::insert(&v235, v216, &v221);
            }
            Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&FileTime1);
          }
          v91 = (_QWORD *)VmGuidSet::find(&v235, v178, &v221);
          if ( *v91 == *((_QWORD *)&v235 + 1) )
          {
            if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,0>>::find(
                              (char *)v3 + 5472,
                              v179,
                              &v221) == *((_QWORD *)v3 + 684) )
            {
              Buf1 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                              &v229,
                                              v219,
                                              &v221)
                               + 44LL);
              *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                       (char *)v3 + 5472,
                                       v220,
                                       &v221)
                        + 44LL) = Buf1;
              v92 = (_QWORD *)std::map<Vml::VmGuid,VmGuidSet>::_Try_emplace<Vml::VmGuid const &,>(
                                (char *)v3 + 5504,
                                v189,
                                &Buf1);
              VmGuidSet::insert(*v92 + 48LL, v190, &v221);
            }
            else
            {
              Buf1 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                              &v229,
                                              v191,
                                              &v221)
                               + 44LL);
            }
            if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<Vml::VmGuid,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,0>>::find(
                              (char *)v3 + 5520,
                              v180,
                              &v221) == *((_QWORD *)v3 + 690) )
            {
              v93 = v249;
              *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                       (char *)v3 + 5520,
                                       v192,
                                       &v221)
                        + 44LL) = v93;
            }
            v263 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                            (char *)v3 + 5520,
                                            v193,
                                            &v221)
                             + 44LL);
            v264 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                            (char *)v3 + 5472,
                                            v194,
                                            &v221)
                             + 44LL);
            v265 = *(_OWORD *)(*(_QWORD *)std::map<Vml::VmGuid,Vml::VmGuid>::_Try_emplace<Vml::VmGuid const &,>(
                                            &v238,
                                            v195,
                                            &v221)
                             + 44LL);
          }
          else
          {
            v269 = 1;
            v94 = (_QWORD *)VmGuidSet::find(&v224, v186, &v221);
            if ( *v94 != *((_QWORD *)&v224 + 1) )
            {
              v95 = (void **)VmGuidSet::find(&v224, v182, &v221);
              memmove_0(*v95, (char *)*v95 + 16, *((_QWORD *)&v224 + 1) - ((_QWORD)*v95 + 16));
              *((_QWORD *)&v224 + 1) -= 16LL;
            }
          }
          ReplicationCoordinator::SendMessageToVirtualMachine(v3, (struct Vml::VmGuid *)&v221, v259, 0xA0u, v255, 0x28u);
          if ( v258 != 262151 )
            ReplicationCoordinatorOperation::UpdateProgress(v131, v255, 0x28u);
        }
        v8 = 0;
        v136 = 0;
        v2 = v131;
        v4 = ConsistencyLevel;
      }
      TlsSetValue(dwTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
      v7 = 0;
      BYTE8(v132) = 0;
    }
    LeaveCriticalSection(lpCriticalSection);
    HResultFromThrownExceptionAndTrace = ReplicationCoordinatorOperation::WaitForCompletion(
                                           v2,
                                           HResultFromThrownExceptionAndTrace);
    if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 0x1E) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2A42,
        (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
        v96);
    *(_QWORD *)&v132 = lpCriticalSection;
    EnterCriticalSection(lpCriticalSection);
    v97 = 1;
    BYTE8(v132) = 1;
    while ( v97 )
    {
      v98 = 1;
      v136 = 1;
      v99 = ReplicationCoordinator::gm_RcTlsIndex;
      v133 = ReplicationCoordinator::gm_RcTlsIndex;
      v100 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
      v134 = v100;
      v135 = v100 | 1;
      TlsSetValue(v99, (LPVOID)(v100 | 1));
      while ( v98 )
      {
        if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 1) == 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x2A44,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            v101);
        if ( (unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 64) )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
          {
            LODWORD(v123) = v128[0];
            VmlDebugTraceWithError(16808, &off_14091FE90, 2147500036LL);
          }
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2A44,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)0x80004004LL,
            v123);
        }
        *(_QWORD *)v124 = &v129;
        v123 = (__int64)&HResultFromThrownExceptionAndTrace;
        v102 = ReplicationCoordinator::ProcessOperation(v3, v131, 4, &v227);
        if ( v102 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2A4D,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v102,
            (int)&HResultFromThrownExceptionAndTrace);
        if ( (_QWORD)v224 == *((_QWORD *)&v224 + 1) )
        {
          v103 = v129;
        }
        else
        {
          ConsistencyLevel = 0;
          FileTime1 = 0;
          v103 = v129;
          ReplicationCoordinator::CreateDeltaReplicationStatusMessage(
            (_DWORD)v3,
            (unsigned int)&v249,
            (unsigned int)&FileTime2,
            v4,
            0,
            (__int64)&v224,
            v129,
            (__int64)&FileTime1,
            (__int64)&ConsistencyLevel);
          v104 = ReplicationCoordinator::SendMessageOverNetwork(v3, *(void **)&FileTime1, ConsistencyLevel, 0);
          if ( v104 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2A65,
              (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
              (const char *)(unsigned int)v104,
              v123);
          operator delete(*(void **)&FileTime1, v105);
        }
        if ( v103 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2A68,
            (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
            (const char *)(unsigned int)v103,
            v123);
        if ( !(unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 16) )
        {
          v106 = *((_QWORD *)v3 + 226);
          *(_DWORD *)(v106 + 112) = ReplicationCoordinator::CalculateNextTimeoutInterval(v3);
        }
        v98 = 0;
        v136 = 0;
      }
      TlsSetValue(v99, (LPVOID)v100);
      v97 = 0;
      BYTE8(v132) = 0;
    }
    v107 = lpCriticalSection;
    LeaveCriticalSection(lpCriticalSection);
    v110 = v130;
  }
  catch ( ... )
  {
    HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                           (Vml *)0x41A8,
                                           (unsigned __int16)&off_14091FEA8,
                                           v109);
    *(_QWORD *)v128 = v158;
    v110 = HResultFromThrownExceptionAndTrace;
    v130 = HResultFromThrownExceptionAndTrace;
    v3 = v159;
    v131 = v160;
    v107 = lpCriticalSection;
  }
  if ( (v110 & 0x80000000) == 0 )
    goto LABEL_247;
  v244 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v244) = 0;
  *(_QWORD *)&v132 = &v248;
  *((_QWORD *)&v132 + 1) = &v244;
  v149 = retaddr;
  v150 = "onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp";
  v151 = 0;
  v152 = 10872;
  v246 = &wil::details::functor_wrapper_void<_lambda_617b78bd8eb4ca4de4b851b18612fab5_>::`vftable';
  p_Buf2 = &v132;
  wil::details::ResultFromException(&v149, v108, &v246);
  v132 = 0;
  Vml::VmAutoLock::VmAutoLock((Vml::VmAutoLock *)&v132, (ReplicationCoordinator *)((char *)v3 + 800));
  ++*((_DWORD *)v3 + 258);
  Vml::VmAutoLock::~VmAutoLock((Vml::VmAutoLock *)&v132);
  RcEventDescriptorFromErrorCode = GetRcEventDescriptorFromErrorCode(v110);
  if ( RcEventDescriptorFromErrorCode )
  {
    v112 = (__int64 *)RcEventDescriptorFromErrorCode;
    v113 = *((_QWORD *)v3 + 98);
  }
  else
  {
    FrEventDescriptorFromErrorCode = GetFrEventDescriptorFromErrorCode(v110);
    v113 = v115;
    if ( !FrEventDescriptorFromErrorCode )
    {
      v124[0] = 1;
      ReplicationCoordinator::ReportAndLogError(
        v3,
        v115,
        MSVM_VMMS_FR_COLLECTION_GENERATE_AND_SEND_DELTA_FAILED_ERROR,
        v110,
        "ReplicationCoordinator::GenerateAndSendDeltaAsync",
        *(_QWORD *)v124);
      goto LABEL_224;
    }
    v112 = MSVM_VMMS_FR_COLLECTION_GENERATE_AND_SEND_DELTA_ERROR;
  }
  LODWORD(v123) = 1;
  ReplicationCoordinator::ReportAndLogError(v3, v113, v112, "ReplicationCoordinator::GenerateAndSendDeltaAsync", v123);
LABEL_224:
  if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
    VmlDebugTraceWithError(16808, &off_14091FEB8, v110);
  if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 0x1E) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2AA5,
      (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
      v116);
  *(_QWORD *)&v132 = v107;
  EnterCriticalSection(v107);
  v117 = 1;
  BYTE8(v132) = 1;
LABEL_229:
  if ( !v117 )
  {
    LeaveCriticalSection(lpCriticalSection);
    std::wstring::_Tidy_deallocate(&v244);
LABEL_247:
    std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::clear(&v238);
    if ( (_QWORD)v224 != *((_QWORD *)&v224 + 1) )
      *((_QWORD *)&v224 + 1) = v224;
    std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmGuid,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmGuid>>,0>>::clear(&v229);
    std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePointGroup,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsReferencePointGroup,Vml::VmUserReferenceTraits>>>,0>>::clear(&v231);
    if ( (_QWORD)v233 != *((_QWORD *)&v233 + 1) )
      *((_QWORD *)&v233 + 1) = v233;
    if ( (_QWORD)v242 != *((_QWORD *)&v242 + 1) )
      *((_QWORD *)&v242 + 1) = v242;
    if ( (_QWORD)v227 != *((_QWORD *)&v227 + 1) )
      *((_QWORD *)&v227 + 1) = v227;
    if ( (_QWORD)v235 != *((_QWORD *)&v235 + 1) )
      *((_QWORD *)&v235 + 1) = v235;
    goto LABEL_257;
  }
  v118 = 1;
  v136 = 1;
  v119 = ReplicationCoordinator::gm_RcTlsIndex;
  v133 = ReplicationCoordinator::gm_RcTlsIndex;
  v120 = (unsigned int)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex);
  v134 = v120;
  v135 = v120 | 1;
  TlsSetValue(v119, (LPVOID)(v120 | 1));
  while ( 1 )
  {
    if ( !v118 )
    {
      TlsSetValue(v119, (LPVOID)v120);
      v117 = 0;
      BYTE8(v132) = 0;
      goto LABEL_229;
    }
    if ( ((unsigned __int8)TlsGetValue(ReplicationCoordinator::gm_RcTlsIndex) & 3) == 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2AA7,
        (unsigned int)"onecore\\vm\\vmms\\rcmgr\\replicationcoordinator.cpp",
        v121);
    if ( (unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 64) )
      break;
    if ( v137 )
    {
      ReplicationCoordinatorOperation::Complete(v131, v130);
      TimeoutInterval = 1000 * ReplicationCoordinator::GetReplicationIntervalInternal(v3);
      if ( (unsigned int)VmlIsDebugTraceEnabled(49576) )
        VmlDebugTraceEx(49576, &off_140920010);
    }
    else
    {
      TimeoutInterval = ReplicationCoordinator::CalculateNextTimeoutInterval(v3);
    }
    if ( !(unsigned int)ReplicationCoordinator::TestOperationalFlag(v3, 16) )
      *(_DWORD *)(*((_QWORD *)v3 + 226) + 112LL) = TimeoutInterval;
    v118 = 0;
    v136 = 0;
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(16808) )
    VmlDebugTraceEx(16808, &off_14091FFF8);
  TlsSetValue(v119, (LPVOID)v120);
  LeaveCriticalSection(lpCriticalSection);
  std::wstring::_Tidy_deallocate(&v244);
LABEL_257:
  std::wstring::_Tidy_deallocate(v232);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v235);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v233);
  std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<ReplicationCoordinator,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<ReplicationCoordinator,Vml::VmUserReferenceTraits>>>,0>>::~_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<ReplicationCoordinator,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<ReplicationCoordinator,Vml::VmUserReferenceTraits>>>,0>>(&v231);
  std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmGuid>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>(
    &v229,
    &v229);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v224);
  std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmGuid>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>(
    &v238,
    &v238);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v227);
  std::vector<Schema::Responses::System::GuestPhysicalAddressRange>::_Tidy(&v242);
  std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmGuid>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Vml::VmGuid const,Vml::VmGuid>,void *>>>(
    &v239,
    &v239);
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v223);
}

```

## disassembly

```asm
0x140222208  mov     r11, rsp
0x14022220b  mov     [r11+18h], rbx
0x14022220f  mov     [r11+20h], rsi
0x140222213  push    rdi
0x140222214  push    r12
0x140222216  push    r13
0x140222218  push    r14
0x14022221a  push    r15
0x14022221c  sub     rsp, 750h
0x140222223  movaps  xmmword ptr [r11-38h], xmm6
0x140222228  movaps  xmmword ptr [r11-48h], xmm7
0x14022222d  mov     rax, cs:__security_cookie
0x140222234  xor     rax, rsp
0x140222237  mov     [rsp+778h+var_58], rax
0x14022223f  mov     rsi, rdx
0x140222242  mov     [rsp+778h+var_708], rdx
0x140222247  mov     r15, rcx
0x14022224a  mov     [rsp+778h+var_668], rcx
0x140222252  mov     [rsp+778h+var_660], rdx
0x14022225a  mov     [rsp+778h+var_6E0], 1
0x140222265  xor     r14d, r14d
0x140222268  mov     r12d, r14d
0x14022226b  mov     [r11-290h], r14
0x140222272  xorps   xmm0, xmm0
0x140222275  movdqa  [rsp+778h+var_198], xmm0
0x14022227e  mov     dword ptr [rsp+778h+var_710], r14d
0x140222283  xorps   xmm1, xmm1
0x140222286  movdqa  [rsp+778h+var_178], xmm1
0x14022228f  mov     [r11-2F0h], r14
0x140222296  movups  [rsp+778h+var_210], xmm0
0x14022229e  lea     rcx, [r11-210h]; void *
0x1402222a5  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveLess@Vml@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBUCaseInsensitiveLess@Vml@@@Z; std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(Vml::CaseInsensitiveLess const &)
0x1402222aa  nop
0x1402222ab  xorps   xmm0, xmm0
0x1402222ae  movdqa  [rsp+778h+var_188], xmm0
0x1402222b7  xorps   xmm1, xmm1
0x1402222ba  movdqu  [rsp+778h+var_1E8], xmm1
0x1402222c3  mov     [rsp+778h+var_1D8], r14
0x1402222cb  movdqu  [rsp+778h+var_2B8], xmm1
0x1402222d4  mov     [rsp+778h+var_2A8], r14
0x1402222dc  movups  [rsp+778h+var_220], xmm0
0x1402222e4  lea     rcx, [rsp+778h+var_220]; void *
0x1402222ec  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveLess@Vml@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBUCaseInsensitiveLess@Vml@@@Z; std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(Vml::CaseInsensitiveLess const &)
0x1402222f1  nop
0x1402222f2  xorps   xmm0, xmm0
0x1402222f5  xorps   xmm1, xmm1
0x1402222f8  movdqu  [rsp+778h+var_2E8], xmm1
0x140222301  mov     [rsp+778h+var_2D8], r14
0x140222309  movups  [rsp+778h+var_2A0], xmm0
0x140222311  lea     rcx, [rsp+778h+var_2A0]; void *
0x140222319  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveLess@Vml@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBUCaseInsensitiveLess@Vml@@@Z; std::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>,0>>(Vml::CaseInsensitiveLess const &)
0x14022231e  nop
0x14022231f  xorps   xmm0, xmm0
0x140222322  movups  [rsp+778h+var_288], xmm0
0x14022232a  lea     rcx, [rsp+778h+var_288]
0x140222332  call    ??0?$map@VVmGuid@Vml@@V?$VmReferencePtr@UIVmmsVirtualMachineObject@@VVmUserReferenceTraits@Vml@@@2@U?$less@VVmGuid@Vml@@@std@@V?$allocator@U?$pair@$$CBVVmGuid@Vml@@V?$VmReferencePtr@UIVmmsVirtualMachineObject@@VVmUserReferenceTraits@Vml@@@2@@std@@@5@@std@@QEAA@XZ; std::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>::map<Vml::VmGuid,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>(void)
0x140222337  nop
0x140222338  mov     [rsp+778h+var_720], 3
0x140222340  mov     qword ptr [rsp+778h+FileTime2.dwLowDateTime], r14
0x140222348  xorps   xmm0, xmm0
0x14022234b  xorps   xmm1, xmm1
0x14022234e  movdqu  [rsp+778h+var_258], xmm1
0x140222357  mov     [rsp+778h+var_248], r14
0x14022235f  movdqu  [rsp+778h+var_240], xmm1
0x140222368  mov     [rsp+778h+var_230], r14
0x140222370  movups  [rsp+778h+var_278], xmm0
0x140222378  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140222380  movdqu  [rsp+778h+var_268], xmm1
0x140222389  mov     word ptr [rsp+778h+var_278], r14w
0x140222392  lea     rax, [r15+60h]
0x140222396  mov     qword ptr [rsp+778h+var_718], rax
0x14022239b  cmp     qword ptr [rax+18h], 7
0x1402223a0  jbe     short loc_1402223AA
0x1402223a2  mov     rax, [rax]
0x1402223a5  mov     qword ptr [rsp+778h+var_718], rax
0x1402223aa  mov     [rsp+778h+var_670], rax
0x1402223b2  lea     rdx, [rsp+778h+var_278]
0x1402223ba  mov     rcx, r15
0x1402223bd  call    ?GetName@ReplicationCoordinator@@QEBAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReplicationCoordinator::GetName(std::wstring &)
0x1402223c2  mov     dword ptr [rsp+778h+var_710+4], r14d
0x1402223c7  xor     ecx, ecx
0x1402223c9  call    cs:__imp_SetVmErrInfo
0x1402223d0  nop     dword ptr [rax+rax+00h]
0x1402223d5  movups  xmm0, xmmword ptr [rsi+50h]
0x1402223d9  movdqu  [rsp+778h+var_198], xmm0
0x1402223e2  mov     eax, [rsi+0A0h]
0x1402223e8  mov     [rsp+778h+var_6D0], eax
0x1402223ef  mov     ebx, [rsi+98h]
0x1402223f5  mov     [rsp+778h+var_724], ebx
0x1402223f9  mov     ecx, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; dwTlsIndex
0x1402223ff  call    cs:__imp_TlsGetValue
0x140222406  nop     dword ptr [rax+rax+00h]
0x14022240b  and     eax, 1Eh
0x14022240e  mov     rcx, [rsp+778h]; this
0x140222416  jz      short loc_14022242A
0x140222418  lea     r8, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14022241f  mov     edx, 282Ch; void *
0x140222424  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14022242a  lea     rdi, [r15+5C0h]
0x140222431  mov     [rsp+778h+lpCriticalSection], rdi
0x140222439  mov     qword ptr [rsp+778h+var_700], rdi
0x14022243e  mov     rcx, rdi; lpCriticalSection
0x140222441  call    cs:__imp_EnterCriticalSection
0x140222448  nop     dword ptr [rax+rax+00h]
0x14022244d  mov     al, 1
0x14022244f  mov     byte ptr [rsp+778h+var_700+8], al
0x140222456  lea     r13, aOnecoreVmVmmsR_11; "onecore\\vm\\vmms\\rcmgr\\replicationco"...
0x14022245d  test    al, al
0x14022245f  jz      loc_140223C38
0x140222465  mov     bl, 1
0x140222467  mov     [rsp+778h+var_6E4], bl
0x14022246e  mov     edi, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; ulong ReplicationCoordinator::gm_RcTlsIndex
0x140222474  mov     [rsp+778h+dwTlsIndex], edi
0x14022247b  mov     [rsp+778h+var_6F0], edi
0x140222482  mov     ecx, edi; dwTlsIndex
0x140222484  call    cs:__imp_TlsGetValue
0x14022248b  nop     dword ptr [rax+rax+00h]
0x140222490  mov     [rsp+778h+lpTlsValue], rax
0x140222498  mov     [rsp+778h+var_6EC], eax
0x14022249f  or      eax, 1
0x1402224a2  mov     edx, eax; lpTlsValue
0x1402224a4  mov     [rsp+778h+var_6E8], edx
0x1402224ab  mov     ecx, edi; dwTlsIndex
0x1402224ad  call    cs:__imp_TlsSetValue
0x1402224b4  nop     dword ptr [rax+rax+00h]
0x1402224b9  nop
0x1402224ba  test    bl, bl
0x1402224bc  jz      loc_140223C0F
0x1402224c2  mov     rbx, [rsp+778h]
0x1402224ca  mov     ecx, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; dwTlsIndex
0x1402224d0  call    cs:__imp_TlsGetValue
0x1402224d7  nop     dword ptr [rax+rax+00h]
0x1402224dc  test    al, 1
0x1402224de  jnz     short loc_1402224F1
0x1402224e0  mov     r8, r13; unsigned int
0x1402224e3  mov     edx, 282Eh; void *
0x1402224e8  mov     rcx, rbx; this
0x1402224eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1402224f1  mov     edx, 40h ; '@'
0x1402224f6  mov     rcx, r15
0x1402224f9  call    ?TestOperationalFlag@ReplicationCoordinator@@AEBAHW4RcOperationalFlags@1@@Z; ReplicationCoordinator::TestOperationalFlag(ReplicationCoordinator::RcOperationalFlags)
0x1402224fe  test    eax, eax
0x140222500  jz      short loc_140222565
0x140222502  mov     ebx, 41A8h
0x140222507  mov     ecx, ebx
0x140222509  call    VmlIsDebugTraceEnabled
0x14022250e  test    eax, eax
0x140222510  jz      short loc_14022254A
0x140222512  lea     r9, [rsp+778h+var_278]
0x14022251a  cmp     qword ptr [rsp+778h+var_268+8], 7
0x140222523  cmova   r9, qword ptr [rsp+778h+var_278]
0x14022252c  mov     rax, qword ptr [rsp+778h+var_718]
0x140222531  mov     [rsp+778h+var_758], rax; int
0x140222536  mov     r8d, 80004004h
0x14022253c  lea     rdx, off_14091FF28; "%ws::%ws Coordinator has already stoppe"...
0x140222543  mov     ecx, ebx
0x140222545  call    VmlDebugTraceWithError
0x14022254a  mov     rcx, [rsp+778h]; this
0x140222552  mov     r9d, 80004004h; char *
0x140222558  mov     r8, r13; unsigned int
0x14022255b  mov     edx, 282Eh; void *
0x140222560  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140222565  cmp     [rsp+778h+var_6D0], 1
0x14022256d  jnz     loc_1402230A0
0x140222573  lea     r12, [r15+590h]
0x14022257a  xor     eax, eax
0x14022257c  lea     esi, [rax+4]
0x14022257f  lock cmpxchg [r12], esi
0x140222585  mov     ebx, eax
0x140222587  jz      short loc_1402225B2
0x140222589  test    al, 1
0x14022258b  jz      loc_140222652
0x140222591  call    cs:__imp_GetCurrentThreadId
0x140222598  nop     dword ptr [rax+rax+00h]
0x14022259d  mov     ecx, eax
0x14022259f  mov     eax, [r12+4]
0x1402225a4  cmp     eax, ecx
0x1402225a6  jnz     loc_140222652
0x1402225ac  lock inc dword ptr [r12+8]
0x1402225b2  mov     [rsp+778h+var_658], r12
0x1402225ba  mov     al, 1
0x1402225bc  mov     [rsp+778h+var_650], al
0x1402225c3  test    al, al
0x1402225c5  jz      loc_1402226D9
0x1402225cb  mov     bl, 1
0x1402225cd  mov     [rsp+778h+var_67C], bl
0x1402225d4  mov     edi, cs:?gm_RcTlsIndex@ReplicationCoordinator@@0KA; ulong ReplicationCoordinator::gm_RcTlsIndex
0x1402225da  mov     [rsp+778h+var_688], edi
0x1402225e1  mov     ecx, edi; dwTlsIndex
0x1402225e3  call    cs:__imp_TlsGetValue
0x1402225ea  nop     dword ptr [rax+rax+00h]
0x1402225ef  mov     rsi, rax
0x1402225f2  mov     [rsp+778h+var_684], esi
0x1402225f9  mov     edx, eax
0x1402225fb  or      edx, 8; lpTlsValue
0x1402225fe  mov     [rsp+778h+var_680], edx
0x140222605  mov     ecx, edi; dwTlsIndex
0x140222607  call    cs:__imp_TlsSetValue
0x14022260e  nop     dword ptr [rax+rax+00h]
0x140222613  nop
0x140222614  test    bl, bl
0x140222616  jz      loc_1402226BA
0x14022261c  lea     r8, [rsp+778h+var_1E8]
0x140222624  mov     edx, 4
0x140222629  mov     rcx, [r15+308h]
0x140222630  call    ?GetVmsForReplicationAction@ReplicationPhaseManager@@QEAAJW4_REPLICATION_COORDINATOR_ACTION@@AEAVVmGuidSet@@@Z; ReplicationPhaseManager::GetVmsForReplicationAction(_REPLICATION_COORDINATOR_ACTION,VmGuidSet &)
0x140222635  mov     rcx, [rsp+778h]; this
0x14022263d  test    eax, eax
0x14022263f  jns     short loc_1402226AB
0x140222641  mov     r9d, eax; char *
0x140222644  mov     r8, r13; unsigned int
0x140222647  mov     edx, 2840h; void *
0x14022264c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140222652  test    bl, 1
0x140222655  jnz     short loc_14022266F
0x140222657  mov     edx, ebx
0x140222659  lea     ecx, [rbx+4]
0x14022265c  mov     eax, ebx
0x14022265e  lock cmpxchg [r12], ecx
0x140222664  mov     ebx, eax
0x140222666  cmp     eax, edx
0x140222668  jnz     short loc_140222652
0x14022266a  jmp     loc_1402225B2
0x14022266f  xor     r8d, r8d
0x140222672  or      edx, 0FFFFFFFFh
0x140222675  mov     rcx, r12
0x140222678  call    RrwpLockWait
0x14022267d  test    eax, eax
0x14022267f  jnz     short loc_1402226A0
0x140222681  mov     rcx, [rsp+778h]; this
0x140222689  mov     r9d, 102h; char *
0x14022268f  lea     r8, aOnecoreVmCommo_25; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140222696  mov     edx, 249h; void *
0x14022269b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1402226a0  prefetchw byte ptr [r12]
0x1402226a5  mov     ebx, [r12]
0x1402226a9  jmp     short loc_140222652
0x1402226ab  mov     bl, r14b
0x1402226ae  mov     [rsp+778h+var_67C], bl
0x1402226b5  jmp     loc_140222614
0x1402226ba  mov     edx, esi; lpTlsValue
0x1402226bc  mov     ecx, edi; dwTlsIndex
0x1402226be  call    cs:__imp_TlsSetValue
0x1402226c5  nop     dword ptr [rax+rax+00h]
0x1402226ca  mov     al, r14b
0x1402226cd  mov     [rsp+778h+var_650], al
0x1402226d4  jmp     loc_1402225C3
0x1402226d9  mov     rcx, r12
0x1402226dc  call    RrwLockRelease
0x1402226e1  mov     rbx, qword ptr [rsp+778h+var_1E8]
0x1402226e9  mov     rdi, qword ptr [rsp+778h+var_1E8+8]
0x1402226f1  cmp     rbx, rdi
0x1402226f4  jz      loc_14022277A
0x1402226fa  movups  xmm0, xmmword ptr [rbx]
0x1402226fd  movdqu  [rsp+778h+var_308], xmm0
0x140222706  xorps   xmm1, xmm1
0x140222709  movdqa  [rsp+778h+Buf1], xmm1
0x140222712  lea     r8, [rsp+778h+Buf1]; struct Vml::VmGuid *
0x14022271a  lea     rdx, [rsp+778h+var_308]; struct Vml::VmGuid *
0x140222722  mov     rcx, r15; this
0x140222725  call    ?FindVmOperation@ReplicationCoordinator@@QEAAXAEBVVmGuid@Vml@@AEAV23@K@Z; ReplicationCoordinator::FindVmOperation(Vml::VmGuid const &,Vml::VmGuid &,ulong)
0x14022272a  xorps   xmm0, xmm0
0x14022272d  movups  [rsp+778h+Buf2], xmm0
0x140222735  mov     r8d, 10h; Size
0x14022273b  lea     rdx, [rsp+778h+Buf2]; Buf2
0x140222743  lea     rcx, [rsp+778h+Buf1]; Buf1
0x14022274b  call    memcmp_0
0x140222750  test    eax, eax
0x140222752  jnz     short loc_140222771
0x140222754  lea     r8, [rsp+778h+var_308]
0x14022275c  lea     rdx, [rsp+778h+var_490]
0x140222764  lea     rcx, [rsp+778h+var_2B8]
0x14022276c  call    ?insert@VmGuidSet@@QEAA?AU?$pair@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VVmGuid@Vml@@@std@@@std@@@std@@_N@std@@AEBVVmGuid@Vml@@@Z; VmGuidSet::insert(Vml::VmGuid const &)
0x140222771  add     rbx, 10h
0x140222775  jmp     loc_1402226F1
0x14022277a  mov     rbx, qword ptr [rsp+778h+var_2B8]
0x140222782  mov     rdi, qword ptr [rsp+778h+var_2B8+8]
0x14022278a  cmp     rbx, rdi
0x14022278d  jnz     short loc_1402227F7
0x14022278f  mov     ebx, 41A8h
0x140222794  mov     ecx, ebx
0x140222796  call    VmlIsDebugTraceEnabled
0x14022279b  test    eax, eax
0x14022279d  jz      short loc_1402227D7
0x14022279f  lea     r9, [rsp+778h+var_278]
0x1402227a7  cmp     qword ptr [rsp+778h+var_268+8], 7
0x1402227b0  cmova   r9, qword ptr [rsp+778h+var_278]
0x1402227b9  mov     rax, qword ptr [rsp+778h+var_718]
0x1402227be  mov     [rsp+778h+var_758], rax; int
0x1402227c3  mov     r8d, 8007139Fh
0x1402227c9  lea     rdx, off_14091FF40; "%ws::%ws No VMs found for current delta"...
0x1402227d0  mov     ecx, ebx
0x1402227d2  call    VmlDebugTraceWithError
0x1402227d7  mov     rcx, [rsp+778h]; this
0x1402227df  mov     r9d, 8007139Fh; char *
0x1402227e5  mov     r8, r13; unsigned int
0x1402227e8  mov     edx, 285Fh; void *
0x1402227ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402227f2  cmp     rbx, rdi
0x1402227f5  jz      short loc_140222850
  ... truncated ...
```
