# PnpInstallDevice

- ea: `0x1800056d0`
- end: `0x18000820d`
- name: `PnpInstallDevice`
- size: `11069`
- prototype: `__int64 __fastcall(DEVNODE, __int64, WCHAR *, __int64, void *, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009d70`

## callees

- `0x1800024d0`
- `0x180002750`
- `0x1800040f0`
- `0x180005540`
- `0x1800056d0`
- `0x180008220`
- `0x1800099d0`
- `0x180009ab0`
- `0x18000b360`
- `0x18000e810`
- `0x18000f5a0`
- `0x18000f650`
- `0x18000f82c`
- `0x18000f970`
- `0x18000fc1c`
- `0x18001002c`
- `0x1800101e8`
- `0x1800104d8`
- `0x1800117d4`
- `0x180011964`
- `0x1800132c0`
- `0x180013590`
- `0x180013bdc`
- `0x180013e94`
- `0x18001621c`
- `0x1800167b0`
- `0x180016818`
- `0x180016cac`
- `0x180016d84`
- `0x180017058`
- `0x1800171b8`
- `0x18001725c`
- `0x180017408`
- `0x1800177e0`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800058be`
- `msvcrt!wcsrchr` at `0x1800058be`
- `ntdll!RtlFreeHeap` at `0x1800080d8`
- `ntdll!RtlFreeHeap` at `0x1800080ef`
- `ntdll!RtlFreeHeap` at `0x180008106`
- `ntdll!RtlFreeHeap` at `0x18000811d`
- `ntdll!RtlFreeHeap` at `0x1800080d8`
- `ntdll!RtlFreeHeap` at `0x1800080ef`
- `ntdll!RtlFreeHeap` at `0x180008106`
- `ntdll!RtlFreeHeap` at `0x18000811d`
- `ntdll!RtlAllocateHeap` at `0x1800059db`
- `ntdll!RtlAllocateHeap` at `0x1800059db`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007313`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000753c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007546`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007639`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007313`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000753c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007546`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180007639`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f61`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006f52`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000751a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000757c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000807e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000751a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000757c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000807e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180006ea2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180006ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006eac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006eac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f67`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180006fa3`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180006fa3`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180007082`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180007082`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800070ab`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1800070ab`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005889`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007010`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005889`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000746b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000746b`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x180005873`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x180005873`
- `DEVRTL!DevRtlWriteTextLog` at `0x180005864`
- `DEVRTL!DevRtlWriteTextLog` at `0x180005c7e`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006833`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006e0c`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006ffa`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800074c8`
- `DEVRTL!DevRtlWriteTextLog` at `0x180005864`
- `DEVRTL!DevRtlWriteTextLog` at `0x180005c7e`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006833`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006e0c`
- `DEVRTL!DevRtlWriteTextLog` at `0x180006ffa`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800074c8`

## string_xrefs

- `0x18000584f`: `{Plug and Play Service: Device Install for %ws}`
- `0x18000681e`: `{Plug and Play Service: Device Install exit(%08x)}`
- `0x180005c66`: `Install needed due to device having problem code CM_PROB_NOT_CONFIGURED`
- `0x180006def`: `Creating Install Process: %ws`
- `0x180006fe5`: `Server install process exited with code 0x%08x`
- `0x1800073bd`: `Setup online Device Install (Software initiated)`
- `0x1800073b6`: `Device Install (Software initiated)`
- `0x180005bfc`: `Setup online Device Install (Hardware initiated)`
- `0x180005bf5`: `Device Install (Hardware initiated)`
- `0x1800074a7`: `Install needed due to device having problem code CM_PROB_REINSTALL`
- `0x18000749b`: `Install needed due to device being marked for re-install`
- `0x18000748f`: `Install needed due to device needing additional installation`
- `0x1800074b3`: `Timeout was detected during previous device installation, setting DI_DONOTCALLCONFIGMG`

## pseudocode

```c
__int64 __fastcall PnpInstallDevice(
        DEVNODE a1,
        __int64 a2,
        WCHAR *a3,
        __int64 a4,
        void *a5,
        __int64 a6,
        unsigned int a7,
        int a8)
{
  const wchar_t *v8; // rsi
  WCHAR *v9; // r15
  __int64 v10; // rax
  WCHAR *v11; // r14
  PVOID v12; // r12
  unsigned __int64 v13; // rdx
  int v14; // ecx
  unsigned int v15; // edi
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r15
  const wchar_t *v19; // r12
  unsigned int v20; // r13d
  wchar_t *v21; // rax
  wchar_t *v22; // rdi
  __int64 v23; // rcx
  _WORD *v24; // rax
  NTSTATUS v25; // edx
  __int64 v26; // rbx
  _WORD *v27; // rax
  __int64 v28; // rcx
  char *v29; // rbx
  __int64 v30; // rax
  char *v31; // rbx
  __int64 v32; // rax
  WCHAR *v33; // r12
  unsigned __int64 v34; // r12
  WCHAR *Heap; // r9
  __int64 v36; // rax
  WCHAR *v37; // rdx
  unsigned __int64 v38; // r8
  WCHAR *v39; // rcx
  NTSTATUS v40; // ecx
  LPWSTR v41; // r11
  unsigned __int64 v42; // rcx
  LPWSTR v43; // rax
  int v44; // ebx
  unsigned __int64 v45; // r10
  const wchar_t *v46; // r13
  __int64 v47; // rcx
  WCHAR *v48; // r9
  WCHAR *v49; // rcx
  int v50; // ebx
  unsigned __int64 v51; // rcx
  LPWSTR v52; // rax
  int v53; // ebx
  unsigned __int64 v54; // r10
  __int64 v55; // rcx
  WCHAR *v56; // r9
  WCHAR *v57; // rcx
  int v58; // ebx
  const WCHAR *v59; // rbx
  void *v60; // rdi
  void *v61; // rbx
  DWORD LastError; // esi
  const char *v63; // r9
  unsigned __int64 v64; // rcx
  LPWSTR v65; // rax
  int v66; // ebx
  unsigned __int64 v67; // r10
  const wchar_t *v68; // r15
  unsigned __int64 v69; // r11
  unsigned __int64 v70; // rcx
  LPWSTR v71; // rax
  int v72; // ebx
  unsigned __int64 v73; // r10
  __int64 v74; // rcx
  WCHAR *v75; // r9
  WCHAR *v76; // rcx
  int v77; // ebx
  LPWSTR v78; // r9
  unsigned __int64 v79; // rcx
  LPWSTR v80; // rax
  int v81; // ebx
  unsigned __int64 v82; // r10
  __int64 v83; // rcx
  WCHAR *v84; // r9
  WCHAR *v85; // rcx
  int v86; // ebx
  __int64 v87; // rcx
  WCHAR *v88; // r9
  WCHAR *v89; // rcx
  unsigned __int64 v90; // rcx
  LPWSTR v91; // rax
  int v92; // ebx
  unsigned __int64 v93; // r10
  __int64 v94; // rcx
  WCHAR *v95; // r9
  WCHAR *v96; // rcx
  int v97; // ebx
  unsigned __int64 v98; // rcx
  LPWSTR v99; // rax
  int v100; // ebx
  unsigned __int64 v101; // r10
  LPWSTR v102; // rdi
  __int64 v103; // r10
  int v104; // ebx
  __int64 *v105; // rdi
  __int64 *v106; // rax
  WCHAR *v107; // r9
  WCHAR *v108; // rcx
  int v109; // ebx
  __int64 v110; // rcx
  WCHAR *v111; // r9
  WCHAR *v112; // rcx
  unsigned __int64 v113; // rcx
  LPWSTR v114; // rax
  int v115; // ebx
  unsigned __int64 v116; // r10
  unsigned __int64 v117; // rdx
  unsigned __int64 v118; // rcx
  WCHAR *v119; // r9
  WCHAR *v120; // rcx
  int v121; // ebx
  unsigned __int64 v122; // rcx
  LPWSTR v123; // rax
  int v124; // ebx
  unsigned __int64 v125; // r10
  unsigned __int64 v126; // rcx
  WCHAR *v127; // r9
  WCHAR *v128; // rcx
  int v129; // ebx
  __int64 *v130; // r10
  bool v131; // cc
  LPWSTR v132; // r11
  int v133; // ebx
  unsigned __int64 v134; // rcx
  LPWSTR v135; // rax
  int v136; // ebx
  unsigned __int64 v137; // r10
  __int64 v138; // rcx
  WCHAR *v139; // r9
  WCHAR *v140; // rcx
  int v141; // ebx
  unsigned __int64 v142; // rcx
  LPWSTR v143; // rax
  int v144; // ebx
  unsigned __int64 v145; // r10
  __int64 v146; // rcx
  WCHAR *v147; // r9
  WCHAR *v148; // rcx
  int v149; // ebx
  __int64 *v150; // r10
  int v151; // ebx
  __int64 v152; // rdi
  unsigned __int64 v153; // rcx
  WCHAR *v154; // rax
  int v155; // ebx
  unsigned __int64 v156; // r10
  __int64 v157; // rcx
  WCHAR *v158; // r9
  WCHAR *v159; // rcx
  int v160; // ebx
  unsigned __int64 v161; // rcx
  WCHAR *v162; // rax
  int v163; // ebx
  unsigned __int64 v164; // r10
  __int64 v165; // rcx
  WCHAR *v166; // r9
  WCHAR *v167; // rcx
  int v168; // ebx
  __int64 *v169; // r10
  int v170; // ebx
  __int64 v171; // rcx
  WCHAR *v172; // r9
  WCHAR *v173; // rcx
  int v174; // ebx
  unsigned __int64 v175; // r10
  WCHAR *v176; // rbx
  HANDLE hProcess; // rdi
  DWORD v178; // edi
  DWORD v179; // r14d
  int v180; // esi
  int v181; // ecx
  int v182; // r8d
  __int64 v184; // rcx
  WCHAR *v185; // r9
  WCHAR *v186; // rcx
  int v187; // ebx
  int v188; // ebx
  __int64 v189; // rcx
  WCHAR *v190; // rax
  WCHAR *v191; // rcx
  int v192; // ebx
  __int64 *v193; // rax
  __int64 v194; // rsi
  WCHAR *v195; // r9
  WCHAR *v196; // rcx
  int v197; // ebx
  __int64 v198; // rcx
  WCHAR *v199; // rcx
  unsigned __int64 v200; // rcx
  WCHAR *v201; // rax
  int v202; // ebx
  unsigned __int64 v203; // r10
  __int64 v204; // rcx
  WCHAR *v205; // r9
  WCHAR *v206; // rcx
  int v207; // ebx
  unsigned __int64 v208; // rcx
  WCHAR *v209; // rax
  unsigned __int64 v210; // rcx
  WCHAR *v211; // rax
  int v212; // ebx
  __int64 v213; // rcx
  const wchar_t *v214; // r9
  WCHAR *v215; // rax
  WCHAR *v216; // rcx
  int v217; // ebx
  unsigned __int64 v218; // rcx
  WCHAR *v219; // rax
  int v220; // ebx
  __int64 v221; // rcx
  WCHAR *v222; // rax
  WCHAR *v223; // rcx
  int v224; // ebx
  int v225; // ebx
  __int64 v226; // rcx
  WCHAR *v227; // rax
  WCHAR *v228; // rcx
  int v229; // ebx
  unsigned __int64 v230; // rcx
  WCHAR *v231; // rax
  int v232; // ebx
  DWORD CurrentThreadId; // eax
  DWORD v234; // eax
  DWORD v235; // ebx
  DWORD v236; // eax
  unsigned __int64 v237; // rbx
  _QWORD *v238; // rcx
  char v239; // di
  DEVNODE v240; // esi
  __int16 v241; // cx
  DWORD v242; // eax
  __int64 v243; // rdx
  __int64 v244; // r8
  __int64 v245; // rdx
  __int64 v246; // r8
  __int64 v247; // rdx
  __int64 v248; // r8
  WCHAR *v249; // rax
  WCHAR *v250; // rcx
  __int64 *v251; // rbx
  int v252; // r8d
  DWORD v253; // eax
  NTSTATUS v254; // ecx
  const wchar_t *v255; // r8
  __int64 v256; // rax
  __int64 v257; // rdx
  DWORD v258; // eax
  void *v259; // rax
  int v260; // eax
  void *v261; // rax
  NTSTATUS v262; // eax
  int v263; // ebx
  DWORD v264; // eax
  _QWORD *v265; // rcx
  __int64 v266; // rdx
  int LogStatus; // edi
  __int64 dwCreationFlags; // [rsp+28h] [rbp-420h]
  DWORD ExitCode; // [rsp+50h] [rbp-3F8h] BYREF
  LPWSTR lpCommandLine; // [rsp+58h] [rbp-3F0h]
  __int64 *v271; // [rsp+60h] [rbp-3E8h] BYREF
  DEVINSTID_W pDeviceID; // [rsp+68h] [rbp-3E0h]
  PVOID P; // [rsp+70h] [rbp-3D8h]
  HANDLE v274; // [rsp+78h] [rbp-3D0h]
  BYTE PropertyBuffer[8]; // [rsp+80h] [rbp-3C8h] BYREF
  DEVNODE pdnDevInst; // [rsp+88h] [rbp-3C0h] BYREF
  __int64 v277; // [rsp+90h] [rbp-3B8h] BYREF
  int v278; // [rsp+98h] [rbp-3B0h]
  ULONG pulStatus; // [rsp+9Ch] [rbp-3ACh] BYREF
  const wchar_t *v280; // [rsp+A0h] [rbp-3A8h]
  ULONG pulProblemNumber; // [rsp+A8h] [rbp-3A0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+B0h] [rbp-398h] BYREF
  __int64 v283; // [rsp+B8h] [rbp-390h]
  HANDLE Handles; // [rsp+C0h] [rbp-388h] BYREF
  void *Src; // [rsp+C8h] [rbp-380h]
  HANDLE hObject; // [rsp+D0h] [rbp-378h]
  PVOID v287; // [rsp+D8h] [rbp-370h]
  PVOID v288; // [rsp+E0h] [rbp-368h]
  __int128 v289; // [rsp+E8h] [rbp-360h] BYREF
  __int128 v290; // [rsp+F8h] [rbp-350h]
  __int128 v291; // [rsp+108h] [rbp-340h]
  __int64 v292; // [rsp+118h] [rbp-330h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+120h] [rbp-328h] BYREF
  wchar_t *v294; // [rsp+138h] [rbp-310h]
  struct _STARTUPINFOW StartupInfo; // [rsp+140h] [rbp-308h] BYREF
  __int128 v296; // [rsp+1B0h] [rbp-298h] BYREF
  int v297; // [rsp+1C0h] [rbp-288h]
  _WORD v298[20]; // [rsp+1C8h] [rbp-280h] BYREF
  wchar_t Str[264]; // [rsp+1F0h] [rbp-258h] BYREF

  v8 = (const wchar_t *)a4;
  v280 = (const wchar_t *)a4;
  v9 = a3;
  pDeviceID = a3;
  v10 = a2;
  v283 = a2;
  pdnDevInst = a1;
  Src = a5;
  ExitCode = 0;
  v11 = 0;
  lpCommandLine = 0;
  v12 = 0;
  v287 = 0;
  v288 = 0;
  v274 = 0;
  hObject = 0;
  memset(&StartupInfo, 0, 100);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  pulStatus = 0;
  pulProblemNumber = 0;
  v278 = 0;
  Handles = 0;
  PropertyBuffer[0] = 0;
  v13 = (unsigned __int64)&WPP_GLOBAL_Control;
  v14 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
    v10 = v283;
  }
  if ( (Microsoft_Windows_UserPnpEnableBits & 0x10) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)ENTER_PNP_INSTALL_DEVICE, (_DWORD)a3, 1, (__int64)&v296);
    v10 = v283;
  }
  v15 = a7;
  v16 = a7 & 1;
  if ( (a7 & 1) != 0 && !v10 )
  {
    ExitCode = 13;
    v20 = 4;
    v18 = a6;
    v176 = pDeviceID;
    hProcess = 0;
    goto LABEL_368;
  }
  PropertyBuffer[0] = -1;
  PnpSetObjectProp(
    v9,
    v13,
    (__int64)a3,
    (const DEVPROPKEY *)DEVPKEY_Device_InstallInProgress,
    0x11u,
    PropertyBuffer,
    1u);
  v18 = a6;
  if ( a6 )
  {
    v19 = pDeviceID;
    DevRtlWriteTextLog(a6, 0x2000000, 131076, "{Plug and Play Service: Device Install for %ws}", pDeviceID);
    v20 = 4;
    goto LABEL_7;
  }
  if ( !v16 )
  {
    v59 = L"Setup online Device Install (Hardware initiated)";
    if ( (v15 & 0x20) == 0 )
      v59 = L"Device Install (Hardware initiated)";
    v278 = 0;
    v60 = 0;
    v19 = pDeviceID;
    if ( !pDeviceID || (v60 = (void *)pSetupUnicodeToMultiByte(pDeviceID)) != 0 )
    {
      v256 = pSetupUnicodeToMultiByte(v59);
      v61 = (void *)v256;
      if ( v256 )
      {
        LastError = 0;
        v278 = pSetupCreateTextLogSectionA(v60, v257, v256, &a6);
        if ( !v278 )
          LastError = GetLastError();
        v18 = a6;
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      v61 = 0;
      LastError = 8;
    }
    if ( v60 )
      HeapFree(hHeap, 0, v60);
    if ( v61 )
      HeapFree(hHeap, 0, v61);
    SetLastError(LastError);
    switch ( a8 )
    {
      case 2:
        v63 = "Install needed due to device having problem code CM_PROB_NOT_CONFIGURED";
        break;
      case 1:
        v63 = "Install needed due to device having problem code CM_PROB_REINSTALL";
        break;
      case 3:
        v63 = "Install needed due to device being marked for re-install";
        break;
      default:
        v20 = 4;
        if ( a8 == 4 )
          DevRtlWriteTextLog(v18, 0x2000000, 4, "Install needed due to device needing additional installation");
        goto LABEL_94;
    }
    v20 = 4;
    DevRtlWriteTextLog(v18, 0x2000000, 4, v63);
LABEL_94:
    v15 = a7;
    v8 = v280;
    goto LABEL_7;
  }
  v255 = L"Setup online Device Install (Software initiated)";
  if ( (v15 & 0x20) == 0 )
    v255 = L"Device Install (Software initiated)";
  v19 = pDeviceID;
  v278 = pSetupCreateTextLogSectionW(pDeviceID, v17, v255, &a6);
  v20 = 4;
  v18 = a6;
LABEL_7:
  DevRtlSetThreadLogToken(v18);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( ServerInstallBatchTimeoutDetected )
  {
    DevRtlWriteTextLog(
      v18,
      0x2000000,
      65542,
      "Timeout was detected during previous device installation, setting DI_DONOTCALLCONFIGMG");
    a7 = v15 | 0x100;
  }
  if ( GetDeviceInstallerFilename(Str) )
  {
    v21 = wcsrchr(Str, 0x5Cu);
    if ( v21 )
    {
      v22 = v21 + 1;
      v294 = v21 + 1;
      if ( v21 == (wchar_t *)-2LL )
      {
        v25 = -1073741811;
      }
      else
      {
        v23 = 0x7FFF;
        v24 = v21 + 1;
        v25 = 0;
        do
        {
          if ( !*v24 )
            break;
          ++v24;
          --v23;
        }
        while ( v23 );
        if ( !v23 )
          v25 = -1073741811;
        v26 = 0x7FFF - v23;
        if ( v25 >= 0 )
        {
          v27 = StringSearchAndReplace(v19);
          P = v27;
          if ( !v27 )
          {
            ExitCode = GetLastError();
            if ( ExitCode )
            {
LABEL_609:
              v176 = pDeviceID;
              hProcess = v11;
              goto LABEL_367;
            }
            v27 = v19;
          }
          v271 = (__int64 *)v27;
          if ( v27 )
          {
            v28 = 200;
            v13 = 0;
            do
            {
              if ( !*v27 )
                break;
              ++v27;
              --v28;
            }
            while ( v28 );
            if ( !v28 )
              v13 = 3221225485LL;
            a3 = (WCHAR *)(200 - v28);
            if ( (v13 & 0x80000000) == 0LL )
            {
              v29 = (char *)a3 + v26 + 22;
              v30 = 0;
              v277 = 0;
              if ( !v8 )
              {
LABEL_27:
                v31 = &v29[v30 + 3];
                v32 = 0;
                v277 = 0;
                v33 = (WCHAR *)Src;
                if ( !Src )
                  goto LABEL_28;
                v261 = StringSearchAndReplace((const wchar_t *)Src);
                v288 = v261;
                if ( v261 )
                {
                  v11 = (WCHAR *)v261;
                }
                else
                {
                  ExitCode = GetLastError();
                  if ( ExitCode )
                    goto LABEL_609;
                  v11 = v33;
                }
                v262 = RtlUnalignedStringCchLengthW(v11, 0x7FFF, &v277);
                if ( v262 >= 0 )
                {
                  v32 = v277;
LABEL_28:
                  v34 = (unsigned __int64)&v31[v32 + 57];
                  if ( 2 * v34 > 0xF42400 )
                    Heap = 0;
                  else
                    Heap = (WCHAR *)RtlAllocateHeap(PnpHeapHandle, 8u, 2 * v34);
                  lpCommandLine = Heap;
                  if ( !Heap )
                  {
                    ExitCode = 8;
                    v11 = 0;
                    goto LABEL_365;
                  }
                  if ( v34 - 1 > 0x7FFFFFFE )
                  {
                    v40 = -1073741811;
                    if ( v34 )
                      *Heap = 0;
                  }
                  else
                  {
                    v36 = 2147483646;
                    v37 = v22;
                    v38 = v34;
                    do
                    {
                      if ( !v36 )
                        break;
                      if ( !*v37 )
                        break;
                      *Heap++ = *v37++;
                      --v36;
                      --v38;
                    }
                    while ( v38 );
                    v39 = Heap - 1;
                    if ( v38 )
                      v39 = Heap;
                    *v39 = 0;
                    v40 = -2147483643;
                    if ( v38 )
                      v40 = 0;
                  }
                  if ( v40 < 0 )
                  {
                    ExitCode = RtlNtStatusToDosErrorNoTeb(v40);
                    v11 = lpCommandLine;
                    v18 = a6;
                    goto LABEL_365;
                  }
                  if ( (int)RtlStringCchPrintfW(v298, 17, L"%lx", pdnDevInst) < 0 )
                    goto LABEL_357;
                  v41 = lpCommandLine;
                  if ( v34 - 1 > 0x7FFFFFFE )
                  {
                    v44 = -1073741811;
                  }
                  else
                  {
                    v42 = v34;
                    v43 = lpCommandLine;
                    v44 = 0;
                    do
                    {
                      if ( !*v43 )
                        break;
                      ++v43;
                      --v42;
                    }
                    while ( v42 );
                    if ( !v42 )
                      v44 = -1073741811;
                    if ( v44 >= 0 )
                    {
                      v45 = v34 - v42;
                      goto LABEL_50;
                    }
                  }
                  v45 = 0;
LABEL_50:
                  v46 = L" \"";
                  if ( v44 < 0 )
                    goto LABEL_357;
                  v13 = v34 - v45;
                  if ( v34 - v45 <= 1 )
                  {
                    v50 = -2147483643;
                  }
                  else
                  {
                    v47 = 2147483646;
                    a3 = L" \"";
                    v48 = &lpCommandLine[v45];
                    do
                    {
                      if ( !v47 )
                        break;
                      if ( !*a3 )
                        break;
                      *v48++ = *a3++;
                      --v47;
                      --v13;
                    }
                    while ( v13 );
                    v49 = v48 - 1;
                    if ( v13 )
                      v49 = v48;
                    *v49 = 0;
                    v50 = -2147483643;
                    if ( v13 )
                    {
                      v50 = 0;
                      goto LABEL_60;
                    }
                  }
                  if ( v34 )
                  {
                    RtlStringExHandleOtherFlagsW(v41, 2 * v34, v45, &v296, &v277, 2048);
                    v41 = lpCommandLine;
                  }
LABEL_60:
                  if ( v50 < 0 )
                    goto LABEL_357;
                  if ( v34 - 1 > 0x7FFFFFFE )
                  {
                    v53 = -1073741811;
                  }
                  else
                  {
                    v51 = v34;
                    v52 = v41;
                    v53 = 0;
                    do
                    {
                      if ( !*v52 )
                        break;
                      ++v52;
                      --v51;
                    }
                    while ( v51 );
                    if ( !v51 )
                      v53 = -1073741811;
                    if ( v53 >= 0 )
                    {
                      v54 = v34 - v51;
                      goto LABEL_69;
                    }
                  }
                  v54 = 0;
LABEL_69:
                  if ( v53 < 0 )
                    goto LABEL_357;
                  v13 = v34 - v54;
                  if ( v34 - v54 <= 1 )
                  {
                    v58 = 0;
                    if ( v298[0] )
                      goto LABEL_633;
                  }
                  else
                  {
                    v55 = 2147483646;
                    a3 = v298;
                    v56 = &v41[v54];
                    do
                    {
                      if ( !v55 )
                        break;
                      if ( !*a3 )
                        break;
                      *v56++ = *a3++;
                      --v55;
                      --v13;
                    }
                    while ( v13 );
                    v57 = v56 - 1;
                    if ( v13 )
                      v57 = v56;
                    *v57 = 0;
                    v58 = -2147483643;
                    if ( v13 )
                      v58 = 0;
                  }
                  if ( v58 >= 0 )
                  {
                    if ( v34 - 1 > 0x7FFFFFFE )
                    {
                      v66 = -1073741811;
                    }
                    else
                    {
                      v64 = v34;
                      v65 = v41;
                      v66 = 0;
                      do
                      {
                        if ( !*v65 )
                          break;
                        ++v65;
                        --v64;
                      }
                      while ( v64 );
                      if ( !v64 )
                        v66 = -1073741811;
                      if ( v66 >= 0 )
                      {
                        v67 = v34 - v64;
                        goto LABEL_104;
                      }
                    }
                    v67 = 0;
LABEL_104:
                    if ( v66 >= 0 )
                    {
                      v13 = v34 - v67;
                      if ( v34 - v67 <= 1 )
                      {
                        v66 = -2147483643;
                        v68 = L"\"";
                      }
                      else
                      {
                        v87 = 2147483646;
                        v68 = L"\"";
                        a3 = (WCHAR *)L"\"";
                        v88 = &v41[v67];
                        do
                        {
                          if ( !v87 )
                            break;
                          if ( !*a3 )
                            break;
                          *v88++ = *a3++;
                          --v87;
                          --v13;
                        }
                        while ( v13 );
                        v89 = v88 - 1;
                        if ( v13 )
                          v89 = v88;
                        *v89 = 0;
                        v66 = -2147483643;
                        if ( v13 )
                        {
                          v66 = 0;
                          goto LABEL_106;
                        }
                      }
                      if ( v34 )
                        RtlStringExHandleOtherFlagsW(v41, 2 * v34, v67, &v277, &v296, 2048);
                    }
                    else
                    {
                      v68 = L"\"";
                    }
LABEL_106:
                    if ( v66 < 0 || (int)RtlStringCchPrintfW(v298, 17, L"%lx", a7) < 0 )
                      goto LABEL_357;
                    v69 = 2147483646;
                    if ( v34 - 1 > 0x7FFFFFFE )
                    {
                      v72 = -1073741811;
                    }
                    else
                    {
                      v70 = v34;
                      v71 = lpCommandLine;
                      v72 = 0;
                      do
                      {
                        if ( !*v71 )
                          break;
                        ++v71;
                        --v70;
                      }
                      while ( v70 );
                      if ( !v70 )
                        v72 = -1073741811;
                      if ( v72 >= 0 )
                      {
                        v73 = v34 - v70;
                        goto LABEL_116;
                      }
                    }
                    v73 = 0;
LABEL_116:
                    if ( v72 < 0 )
                      goto LABEL_357;
                    v13 = v34 - v73;
                    if ( v34 - v73 <= 1 )
                    {
                      v77 = -2147483643;
                    }
                    else
                    {
                      v74 = 2147483646;
                      a3 = L" \"";
                      v75 = &lpCommandLine[v73];
                      do
                      {
                        if ( !v74 )
                          break;
                        if ( !*a3 )
                          break;
                        *v75++ = *a3++;
                        --v74;
                        --v13;
                      }
                      while ( v13 );
                      v76 = v75 - 1;
                      if ( v13 )
                        v76 = v75;
                      *v76 = 0;
                      v77 = -2147483643;
                      if ( v13 )
                      {
                        v77 = 0;
                        goto LABEL_126;
                      }
                    }
                    if ( v34 )
                    {
                      RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v73, &v277, &v296, 2048);
                      v69 = 2147483646;
                    }
LABEL_126:
                    if ( v77 < 0 )
                      goto LABEL_357;
                    v78 = lpCommandLine;
                    if ( v34 - 1 > 0x7FFFFFFE )
                    {
                      v81 = -1073741811;
                    }
                    else
                    {
                      v79 = v34;
                      v80 = lpCommandLine;
                      v81 = 0;
                      do
                      {
                        if ( !*v80 )
                          break;
                        ++v80;
                        --v79;
                      }
                      while ( v79 );
                      if ( !v79 )
                        v81 = -1073741811;
                      if ( v81 >= 0 )
                      {
                        v82 = v34 - v79;
                        goto LABEL_135;
                      }
                    }
                    v82 = 0;
LABEL_135:
                    if ( v81 < 0 )
                      goto LABEL_357;
                    v13 = v34 - v82;
                    if ( v34 - v82 <= 1 )
                    {
                      v86 = 0;
                      if ( v298[0] )
                        goto LABEL_648;
                    }
                    else
                    {
                      v83 = 2147483646;
                      a3 = v298;
                      v84 = &lpCommandLine[v82];
                      do
                      {
                        if ( !v83 )
                          break;
                        if ( !*a3 )
                          break;
                        *v84++ = *a3++;
                        --v83;
                        --v13;
                      }
                      while ( v13 );
                      v85 = v84 - 1;
                      if ( v13 )
                        v85 = v84;
                      *v85 = 0;
                      v86 = -2147483643;
                      if ( v13 )
                        v86 = 0;
                      v78 = lpCommandLine;
                    }
                    if ( v86 >= 0 )
                    {
                      if ( v34 - 1 > 0x7FFFFFFE )
                      {
                        v92 = -1073741811;
                      }
                      else
                      {
                        v90 = v34;
                        v91 = v78;
                        v92 = 0;
                        do
                        {
                          if ( !*v91 )
                            break;
                          ++v91;
                          --v90;
                        }
                        while ( v90 );
                        if ( !v90 )
                          v92 = -1073741811;
                        if ( v92 >= 0 )
                        {
                          v93 = v34 - v90;
                          goto LABEL_166;
                        }
                      }
                      v93 = 0;
LABEL_166:
                      if ( v92 < 0 )
                        goto LABEL_357;
                      v13 = v34 - v93;
                      if ( v34 - v93 <= 1 )
                      {
                        v97 = -2147483643;
                      }
                      else
                      {
                        v94 = 2147483646;
                        a3 = (WCHAR *)L"\"";
                        v95 = &v78[v93];
                        do
                        {
                          if ( !v94 )
                            break;
                          if ( !*a3 )
                            break;
                          *v95++ = *a3++;
                          --v94;
                          --v13;
                        }
                        while ( v13 );
                        v96 = v95 - 1;
                        if ( v13 )
                          v96 = v95;
                        *v96 = 0;
                        v97 = -2147483643;
                        if ( v13 )
                        {
                          v97 = 0;
                          goto LABEL_176;
                        }
                      }
                      if ( v34 )
                      {
                        RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v93, &v277, &v296, 2048);
                        v69 = 2147483646;
                      }
LABEL_176:
                      if ( v97 < 0 )
                        goto LABEL_357;
                      if ( v34 - 1 > 0x7FFFFFFE )
                      {
                        v100 = -1073741811;
                      }
                      else
                      {
                        v98 = v34;
                        v99 = lpCommandLine;
                        v100 = 0;
                        do
                        {
                          if ( !*v99 )
                            break;
                          ++v99;
                          --v98;
                        }
                        while ( v98 );
                        if ( !v98 )
                          v100 = -1073741811;
                        if ( v100 >= 0 )
                        {
                          v101 = v34 - v98;
                          goto LABEL_185;
                        }
                      }
                      v101 = 0;
LABEL_185:
                      if ( v100 < 0 )
                      {
LABEL_186:
                        v102 = lpCommandLine;
                        goto LABEL_187;
                      }
                      v13 = v34 - v101;
                      if ( v34 - v101 <= 1 )
                      {
                        v100 = -2147483643;
                      }
                      else
                      {
                        v110 = 2147483646;
                        a3 = L" \"";
                        v111 = &lpCommandLine[v101];
                        do
                        {
                          if ( !v110 )
                            break;
                          if ( !*a3 )
                            break;
                          *v111++ = *a3++;
                          --v110;
                          --v13;
                        }
                        while ( v13 );
                        v112 = v111 - 1;
                        if ( v13 )
                          v112 = v111;
                        *v112 = 0;
                        v100 = -2147483643;
                        if ( v13 )
                        {
                          v100 = 0;
                          goto LABEL_186;
                        }
                      }
                      v102 = lpCommandLine;
                      if ( v34 )
                      {
                        RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v101, &v277, &v296, 2048);
                        v69 = 2147483646;
                      }
LABEL_187:
                      if ( v100 < 0 )
                        goto LABEL_357;
                      v103 = 0;
                      v277 = 0;
                      if ( v34 - 1 <= 0x7FFFFFFE )
                      {
                        v104 = RtlStringLengthWorkerW(v102, v34, &v277);
                        v103 = v277;
                      }
                      else
                      {
                        v104 = -1073741811;
                        if ( v34 <= 0x7FFFFFFF )
                          v104 = 0;
                      }
                      v105 = &qword_18001C3B0;
                      if ( v104 < 0 )
                        goto LABEL_357;
                      v13 = v34 - v103;
                      v106 = &qword_18001C3B0;
                      if ( v271 )
                        v106 = v271;
                      if ( v13 <= 1 )
                      {
                        v109 = 0;
                        if ( *(_WORD *)v106 )
                          goto LABEL_662;
                      }
                      else
                      {
                        a3 = (WCHAR *)v69;
                        v107 = &lpCommandLine[v103];
                        do
                        {
                          if ( !a3 )
                            break;
                          if ( !*(_WORD *)v106 )
                            break;
                          *v107++ = *(_WORD *)v106;
                          v106 = (__int64 *)((char *)v106 + 2);
                          a3 = (WCHAR *)((char *)a3 - 1);
                          --v13;
                        }
                        while ( v13 );
                        v108 = v107 - 1;
                        if ( v13 )
                          v108 = v107;
                        *v108 = 0;
                        v109 = -2147483643;
                        if ( v13 )
                          v109 = 0;
                      }
                      if ( v109 >= 0 )
                      {
                        v13 = (unsigned __int64)lpCommandLine;
                        if ( v34 - 1 > v69 )
                        {
                          v115 = -1073741811;
                        }
                        else
                        {
                          v113 = v34;
                          v114 = lpCommandLine;
                          v115 = 0;
                          do
                          {
                            if ( !*v114 )
                              break;
                            ++v114;
                            --v113;
                          }
                          while ( v113 );
                          if ( !v113 )
                            v115 = -1073741811;
                          if ( v115 >= 0 )
                          {
                            v116 = v34 - v113;
                            goto LABEL_223;
                          }
                        }
                        v116 = 0;
LABEL_223:
                        if ( v115 < 0 )
                          goto LABEL_357;
                        v117 = v34 - v116;
                        if ( v34 - v116 <= 1 )
                        {
                          v121 = -2147483643;
                        }
                        else
                        {
                          v118 = v69;
                          a3 = (WCHAR *)L"\"";
                          v119 = &lpCommandLine[v116];
                          do
                          {
                            if ( !v118 )
                              break;
                            if ( !*a3 )
                              break;
                            *v119++ = *a3++;
                            --v118;
                            --v117;
                          }
                          while ( v117 );
                          v120 = v119 - 1;
                          if ( v117 )
                            v120 = v119;
                          *v120 = 0;
                          v121 = -2147483643;
                          if ( v117 )
                          {
                            v121 = 0;
                            goto LABEL_233;
                          }
                        }
                        if ( v34 )
                        {
                          RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v116, &v271, &v296, 2048);
                          v69 = 2147483646;
                        }
LABEL_233:
                        v13 = (unsigned __int64)lpCommandLine;
                        if ( v121 < 0 )
                          goto LABEL_357;
                        if ( v34 - 1 > v69 )
                        {
                          v124 = -1073741811;
                        }
                        else
                        {
                          v122 = v34;
                          v123 = lpCommandLine;
                          v124 = 0;
                          do
                          {
                            if ( !*v123 )
                              break;
                            ++v123;
                            --v122;
                          }
                          while ( v122 );
                          if ( !v122 )
                            v124 = -1073741811;
                          if ( v124 >= 0 )
                          {
                            v125 = v34 - v122;
                            goto LABEL_242;
                          }
                        }
                        v125 = 0;
LABEL_242:
                        if ( v124 < 0 )
                          goto LABEL_357;
                        v13 = v34 - v125;
                        if ( v34 - v125 <= 1 )
                        {
                          v129 = -2147483643;
                        }
                        else
                        {
                          v126 = v69;
                          a3 = L" \"";
                          v127 = &lpCommandLine[v125];
                          do
                          {
                            if ( !v126 )
                              break;
                            if ( !*a3 )
                              break;
                            *v127++ = *a3++;
                            --v126;
                            --v13;
                          }
                          while ( v13 );
                          v128 = v127 - 1;
                          if ( v13 )
                            v128 = v127;
                          *v128 = 0;
                          v129 = -2147483643;
                          if ( v13 )
                          {
                            v129 = 0;
                            goto LABEL_252;
                          }
                        }
                        if ( v34 )
                        {
                          RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v125, &v271, &v296, 2048);
                          v69 = 2147483646;
                        }
LABEL_252:
                        if ( v129 < 0 )
                          goto LABEL_357;
                        v130 = 0;
                        v271 = 0;
                        v131 = v34 - 1 <= v69;
                        v132 = lpCommandLine;
                        if ( v131 )
                        {
                          v133 = RtlStringLengthWorkerW(lpCommandLine, v34, &v271);
                          v130 = v271;
                        }
                        else
                        {
                          v133 = -1073741811;
                          if ( v34 <= 0x7FFFFFFF )
                            v133 = 0;
                        }
                        if ( v133 < 0 )
                          goto LABEL_357;
                        v13 = v34 - (_QWORD)v130;
                        v193 = &qword_18001C3B0;
                        if ( v8 )
                          v193 = (__int64 *)v8;
                        v194 = 2147483646;
                        if ( v13 <= 1 )
                        {
                          v197 = 0;
                          if ( *(_WORD *)v193 )
                            goto LABEL_676;
                        }
                        else
                        {
                          a3 = (WCHAR *)2147483646;
                          v195 = &v132[(_QWORD)v130];
                          do
                          {
                            if ( !a3 )
                              break;
                            if ( !*(_WORD *)v193 )
                              break;
                            *v195++ = *(_WORD *)v193;
                            v193 = (__int64 *)((char *)v193 + 2);
                            a3 = (WCHAR *)((char *)a3 - 1);
                            --v13;
                          }
                          while ( v13 );
                          v196 = v195 - 1;
                          if ( v13 )
                            v196 = v195;
                          *v196 = 0;
                          v197 = -2147483643;
                          if ( v13 )
                            v197 = 0;
                        }
                        if ( v197 < 0 )
                        {
LABEL_676:
                          if ( v34 )
                            RtlStringExHandleOtherFlagsW(v132, 2 * v34, v130, &v271, &v296, 2304);
                          goto LABEL_357;
                        }
                        if ( v34 - 1 > 0x7FFFFFFE )
                        {
                          v136 = -1073741811;
                        }
                        else
                        {
                          v134 = v34;
                          v135 = v132;
                          v136 = 0;
                          do
                          {
                            if ( !*v135 )
                              break;
                            ++v135;
                            --v134;
                          }
                          while ( v134 );
                          if ( !v134 )
                            v136 = -1073741811;
                          if ( v136 >= 0 )
                          {
                            v137 = v34 - v134;
                            goto LABEL_266;
                          }
                        }
                        v137 = 0;
LABEL_266:
                        if ( v136 < 0 )
                          goto LABEL_357;
                        v13 = v34 - v137;
                        if ( v34 - v137 <= 1 )
                        {
                          v141 = -2147483643;
                        }
                        else
                        {
                          v138 = 2147483646;
                          a3 = (WCHAR *)L"\"";
                          v139 = &v132[v137];
                          do
                          {
                            if ( !v138 )
                              break;
                            if ( !*a3 )
                              break;
                            *v139++ = *a3++;
                            --v138;
                            --v13;
                          }
                          while ( v13 );
                          v140 = v139 - 1;
                          if ( v13 )
                            v140 = v139;
                          *v140 = 0;
                          v141 = -2147483643;
                          if ( v13 )
                          {
                            v141 = 0;
                            goto LABEL_276;
                          }
                        }
                        if ( v34 )
                        {
                          RtlStringExHandleOtherFlagsW(v132, 2 * v34, v137, &v271, &v296, 2048);
                          v132 = lpCommandLine;
                        }
LABEL_276:
                        if ( v141 < 0 )
                          goto LABEL_357;
                        if ( v34 - 1 > 0x7FFFFFFE )
                        {
                          v144 = -1073741811;
                        }
                        else
                        {
                          v142 = v34;
                          v143 = v132;
                          v144 = 0;
                          do
                          {
                            if ( !*v143 )
                              break;
                            ++v143;
                            --v142;
                          }
                          while ( v142 );
                          if ( !v142 )
                            v144 = -1073741811;
                          if ( v144 >= 0 )
                          {
                            v145 = v34 - v142;
                            goto LABEL_285;
                          }
                        }
                        v145 = 0;
LABEL_285:
                        if ( v144 < 0 )
                          goto LABEL_357;
                        v13 = v34 - v145;
                        if ( v34 - v145 <= 1 )
                        {
                          v149 = -2147483643;
                        }
                        else
                        {
                          v146 = 2147483646;
                          a3 = L" \"";
                          v147 = &v132[v145];
                          do
                          {
                            if ( !v146 )
                              break;
                            if ( !*a3 )
                              break;
                            *v147++ = *a3++;
                            --v146;
                            --v13;
                          }
                          while ( v13 );
                          v148 = v147 - 1;
                          if ( v13 )
                            v148 = v147;
                          *v148 = 0;
                          v149 = -2147483643;
                          if ( v13 )
                          {
                            v149 = 0;
                            goto LABEL_295;
                          }
                        }
                        if ( v34 )
                        {
                          RtlStringExHandleOtherFlagsW(v132, 2 * v34, v145, &v271, &v296, 2048);
                          v132 = lpCommandLine;
                        }
LABEL_295:
                        if ( v149 < 0 )
                          goto LABEL_357;
                        v150 = 0;
                        v271 = 0;
                        if ( v34 - 1 <= 0x7FFFFFFE )
                        {
                          v151 = RtlStringLengthWorkerW(v132, v34, &v271);
                          v150 = v271;
                        }
                        else
                        {
                          v151 = -1073741811;
                          if ( v34 <= 0x7FFFFFFF )
                            v151 = 0;
                        }
                        if ( v151 < 0 )
                        {
                          v11 = lpCommandLine;
LABEL_301:
                          v152 = 2 * v34;
                          goto LABEL_302;
                        }
                        v13 = v34 - (_QWORD)v150;
                        if ( v11 )
                          v105 = (__int64 *)v11;
                        v11 = lpCommandLine;
                        if ( v13 <= 1 )
                        {
                          v151 = 0;
                          if ( *(_WORD *)v105 )
                          {
                            v151 = -2147483643;
                            goto LABEL_691;
                          }
                        }
                        else
                        {
                          v198 = 2147483646;
                          a3 = &lpCommandLine[(_QWORD)v150];
                          do
                          {
                            if ( !v198 )
                              break;
                            if ( !*(_WORD *)v105 )
                              break;
                            *a3++ = *(_WORD *)v105;
                            v105 = (__int64 *)((char *)v105 + 2);
                            --v198;
                            --v13;
                          }
                          while ( v13 );
                          v199 = a3 - 1;
                          if ( v13 )
                            v199 = a3;
                          *v199 = 0;
                          v151 = -2147483643;
                          if ( v13 )
                            v151 = 0;
                        }
                        if ( v151 >= 0 )
                          goto LABEL_301;
LABEL_691:
                        v152 = 2 * v34;
                        if ( v34 )
                          RtlStringExHandleOtherFlagsW(v11, 2 * v34, v150, &v271, &v296, 2304);
LABEL_302:
                        if ( v151 < 0 )
                          goto LABEL_357;
                        if ( v34 - 1 > 0x7FFFFFFE )
                        {
                          v155 = -1073741811;
                        }
                        else
                        {
                          v153 = v34;
                          v154 = v11;
                          v155 = 0;
                          do
                          {
                            if ( !*v154 )
                              break;
                            ++v154;
                            --v153;
                          }
                          while ( v153 );
                          if ( !v153 )
                            v155 = -1073741811;
                          if ( v155 >= 0 )
                          {
                            v156 = v34 - v153;
                            goto LABEL_311;
                          }
                        }
                        v156 = 0;
LABEL_311:
                        if ( v155 < 0 )
                          goto LABEL_357;
                        v13 = v34 - v156;
                        if ( v34 - v156 <= 1 )
                        {
                          v160 = -2147483643;
                        }
                        else
                        {
                          v157 = 2147483646;
                          a3 = (WCHAR *)L"\"";
                          v158 = &v11[v156];
                          do
                          {
                            if ( !v157 )
                              break;
                            if ( !*a3 )
                              break;
                            *v158++ = *a3++;
                            --v157;
                            --v13;
                          }
                          while ( v13 );
                          v159 = v158 - 1;
                          if ( v13 )
                            v159 = v158;
                          *v159 = 0;
                          v160 = -2147483643;
                          if ( v13 )
                          {
                            v160 = 0;
                            goto LABEL_321;
                          }
                        }
                        if ( v34 )
                          RtlStringExHandleOtherFlagsW(v11, v152, v156, &v271, &v296, 2048);
LABEL_321:
                        if ( v160 >= 0 )
                        {
                          if ( (int)RtlStringCchPrintfW(v298, 17, L"%I64x", a6) < 0 )
                            goto LABEL_363;
                          if ( v34 - 1 > 0x7FFFFFFE )
                          {
                            v163 = -1073741811;
                          }
                          else
                          {
                            v161 = v34;
                            v162 = v11;
                            v163 = 0;
                            do
                            {
                              if ( !*v162 )
                                break;
                              ++v162;
                              --v161;
                            }
                            while ( v161 );
                            if ( !v161 )
                              v163 = -1073741811;
                            if ( v163 >= 0 )
                            {
                              v164 = v34 - v161;
                              goto LABEL_331;
                            }
                          }
                          v164 = 0;
LABEL_331:
                          if ( v163 >= 0 )
                          {
                            v13 = v34 - v164;
                            if ( v34 - v164 <= 1 )
                            {
                              v168 = -2147483643;
                            }
                            else
                            {
                              v165 = 2147483646;
                              a3 = L" \"";
                              v166 = &v11[v164];
                              do
                              {
                                if ( !v165 )
                                  break;
                                if ( !*a3 )
                                  break;
                                *v166++ = *a3++;
                                --v165;
                                --v13;
                              }
                              while ( v13 );
                              v167 = v166 - 1;
                              if ( v13 )
                                v167 = v166;
                              *v167 = 0;
                              v168 = -2147483643;
                              if ( v13 )
                              {
                                v168 = 0;
                                goto LABEL_341;
                              }
                            }
                            if ( v34 )
                              RtlStringExHandleOtherFlagsW(v11, v152, v164, &v271, &v296, 2048);
LABEL_341:
                            if ( v168 < 0 )
                              goto LABEL_363;
                            v169 = 0;
                            v271 = 0;
                            if ( v34 - 1 <= 0x7FFFFFFE )
                            {
                              v170 = RtlStringLengthWorkerW(v11, v34, &v271);
                              v169 = v271;
                            }
                            else
                            {
                              v170 = -1073741811;
                              if ( v34 <= 0x7FFFFFFF )
                                v170 = 0;
                            }
                            if ( v170 < 0 )
                              goto LABEL_363;
                            v13 = v34 - (_QWORD)v169;
                            if ( v34 - (unsigned __int64)v169 <= 1 )
                            {
                              v174 = 0;
                              if ( v298[0] )
                                goto LABEL_705;
                            }
                            else
                            {
                              v171 = 2147483646;
                              a3 = v298;
                              v172 = &v11[(_QWORD)v169];
                              do
                              {
                                if ( !v171 )
                                  break;
                                if ( !*a3 )
                                  break;
                                *v172++ = *a3++;
                                --v171;
                                --v13;
                              }
                              while ( v13 );
                              v173 = v172 - 1;
                              if ( v13 )
                                v173 = v172;
                              *v173 = 0;
                              v174 = -2147483643;
                              if ( v13 )
                                v174 = 0;
                            }
                            if ( v174 >= 0 )
                            {
                              if ( v34 - 1 > 0x7FFFFFFE )
                              {
                                v202 = -1073741811;
                              }
                              else
                              {
                                v200 = v34;
                                v201 = v11;
                                v202 = 0;
                                do
                                {
                                  if ( !*v201 )
                                    break;
                                  ++v201;
                                  --v200;
                                }
                                while ( v200 );
                                if ( !v200 )
                                  v202 = -1073741811;
                                if ( v202 >= 0 )
                                {
                                  v203 = v34 - v200;
                                  goto LABEL_452;
                                }
                              }
                              v203 = 0;
LABEL_452:
                              if ( v202 < 0 )
                                goto LABEL_363;
                              v13 = v34 - v203;
                              if ( v34 - v203 <= 1 )
                              {
                                v207 = -2147483643;
                              }
                              else
                              {
                                v204 = 2147483646;
                                a3 = (WCHAR *)L"\"";
                                v205 = &v11[v203];
                                do
                                {
                                  if ( !v204 )
                                    break;
                                  if ( !*a3 )
                                    break;
                                  *v205++ = *a3++;
                                  --v204;
                                  --v13;
                                }
                                while ( v13 );
                                v206 = v205 - 1;
                                if ( v13 )
                                  v206 = v205;
                                *v206 = 0;
                                v207 = -2147483643;
                                if ( v13 )
                                {
                                  v207 = 0;
                                  goto LABEL_462;
                                }
                              }
                              if ( v34 )
                                RtlStringExHandleOtherFlagsW(v11, v152, v203, &v271, &v296, 2048);
LABEL_462:
                              if ( v207 < 0 || (int)RtlStringCchPrintfW(v298, 17, L"%p", v283) < 0 )
                                goto LABEL_363;
                              if ( v34 - 1 > 0x7FFFFFFE )
                              {
                                v263 = -1073741811;
                              }
                              else
                              {
                                v208 = v34;
                                v209 = v11;
                                v263 = 0;
                                do
                                {
                                  if ( !*v209 )
                                    break;
                                  ++v209;
                                  --v208;
                                }
                                while ( v208 );
                                if ( !v208 )
                                  v263 = -1073741811;
                                if ( v263 >= 0 )
                                {
                                  v175 = v34 - v208;
                                  goto LABEL_362;
                                }
                              }
                              v175 = 0;
LABEL_362:
                              if ( v263 < 0 )
                                goto LABEL_363;
                              v13 = v34 - v175;
                              if ( v34 - v175 <= 1 )
                              {
                                v187 = -2147483643;
                              }
                              else
                              {
                                v184 = 2147483646;
                                a3 = L" \"";
                                v185 = &v11[v175];
                                do
                                {
                                  if ( !v184 )
                                    break;
                                  if ( !*a3 )
                                    break;
                                  *v185++ = *a3++;
                                  --v184;
                                  --v13;
                                }
                                while ( v13 );
                                v186 = v185 - 1;
                                if ( v13 )
                                  v186 = v185;
                                *v186 = 0;
                                v187 = -2147483643;
                                if ( v13 )
                                {
                                  v187 = 0;
                                  goto LABEL_401;
                                }
                              }
                              if ( v34 )
                                RtlStringExHandleOtherFlagsW(v11, v152, v175, &v271, &v296, 2048);
LABEL_401:
                              if ( v187 < 0 )
                                goto LABEL_363;
                              v169 = 0;
                              v271 = 0;
                              if ( v34 - 1 <= 0x7FFFFFFE )
                              {
                                v188 = RtlStringLengthWorkerW(v11, v34, &v271);
                                v169 = v271;
                              }
                              else
                              {
                                v188 = -1073741811;
                                if ( v34 <= 0x7FFFFFFF )
                                  v188 = 0;
                              }
                              if ( v188 < 0 )
                                goto LABEL_363;
                              v13 = v34 - (_QWORD)v169;
                              if ( v34 - (unsigned __int64)v169 <= 1 )
                              {
                                v192 = 0;
                                if ( v298[0] )
                                  goto LABEL_719;
                              }
                              else
                              {
                                v189 = 2147483646;
                                a3 = v298;
                                v190 = &v11[(_QWORD)v169];
                                do
                                {
                                  if ( !v189 )
                                    break;
                                  if ( !*a3 )
                                    break;
                                  *v190++ = *a3++;
                                  --v189;
                                  --v13;
                                }
                                while ( v13 );
                                v191 = v190 - 1;
                                if ( v13 )
                                  v191 = v190;
                                *v191 = 0;
                                v192 = -2147483643;
                                if ( v13 )
                                  v192 = 0;
                              }
                              if ( v192 >= 0 )
                              {
                                if ( v34 - 1 > 0x7FFFFFFE )
                                {
                                  v212 = -1073741811;
                                }
                                else
                                {
                                  v210 = v34;
                                  v211 = v11;
                                  v212 = 0;
                                  do
                                  {
                                    if ( !*v211 )
                                      break;
                                    ++v211;
                                    --v210;
                                  }
                                  while ( v210 );
                                  if ( !v210 )
                                    v212 = -1073741811;
                                  if ( v212 >= 0 )
                                  {
                                    a3 = (WCHAR *)(v34 - v210);
                                    goto LABEL_481;
                                  }
                                }
                                a3 = 0;
LABEL_481:
                                if ( v212 < 0 )
                                  goto LABEL_363;
                                v13 = v34 - (_QWORD)a3;
                                if ( v34 - (unsigned __int64)a3 <= 1 )
                                {
                                  v217 = -2147483643;
                                }
                                else
                                {
                                  v213 = 2147483646;
                                  v214 = L"\"";
                                  v215 = &v11[(_QWORD)a3];
                                  do
                                  {
                                    if ( !v213 )
                                      break;
                                    if ( !*v214 )
                                      break;
                                    *v215++ = *v214++;
                                    --v213;
                                    --v13;
                                  }
                                  while ( v13 );
                                  v216 = v215 - 1;
                                  if ( v13 )
                                    v216 = v215;
                                  *v216 = 0;
                                  v217 = -2147483643;
                                  if ( v13 )
                                  {
                                    v217 = 0;
                                    goto LABEL_491;
                                  }
                                }
                                if ( v34 )
                                  RtlStringExHandleOtherFlagsW(v11, v152, a3, &v271, &v296, 2048);
LABEL_491:
                                if ( v217 < 0 )
                                  goto LABEL_363;
                                if ( v34 - 1 > 0x7FFFFFFE )
                                {
                                  v220 = -1073741811;
                                }
                                else
                                {
                                  v218 = v34;
                                  v219 = v11;
                                  v220 = 0;
                                  do
                                  {
                                    if ( !*v219 )
                                      break;
                                    ++v219;
                                    --v218;
                                  }
                                  while ( v218 );
                                  if ( !v218 )
                                    v220 = -1073741811;
                                  if ( v220 >= 0 )
                                  {
                                    a3 = (WCHAR *)(v34 - v218);
                                    goto LABEL_500;
                                  }
                                }
                                a3 = 0;
LABEL_500:
                                if ( v220 < 0 )
                                  goto LABEL_363;
                                v13 = v34 - (_QWORD)a3;
                                if ( v34 - (unsigned __int64)a3 <= 1 )
                                {
                                  v224 = -2147483643;
                                }
                                else
                                {
                                  v221 = 2147483646;
                                  v222 = &v11[(_QWORD)a3];
                                  do
                                  {
                                    if ( !v221 )
                                      break;
                                    if ( !*v46 )
                                      break;
                                    *v222++ = *v46++;
                                    --v221;
                                    --v13;
                                  }
                                  while ( v13 );
                                  v223 = v222 - 1;
                                  if ( v13 )
                                    v223 = v222;
                                  *v223 = 0;
                                  v224 = -2147483643;
                                  if ( v13 )
                                  {
                                    v224 = 0;
                                    goto LABEL_510;
                                  }
                                }
                                if ( v34 )
                                  RtlStringExHandleOtherFlagsW(v11, v152, a3, &v271, &v296, 2048);
LABEL_510:
                                if ( v224 < 0 )
                                  goto LABEL_363;
                                v169 = 0;
                                v271 = 0;
                                if ( v34 - 1 <= 0x7FFFFFFE )
                                {
                                  v225 = RtlStringLengthWorkerW(v11, v34, &v271);
                                  v169 = v271;
                                }
                                else
                                {
                                  v225 = -1073741811;
                                  if ( v34 <= 0x7FFFFFFF )
                                    v225 = 0;
                                }
                                if ( v225 < 0 )
                                  goto LABEL_363;
                                v13 = v34 - (_QWORD)v169;
                                if ( v34 - (unsigned __int64)v169 <= 1 )
                                {
                                  v229 = 0;
                                  if ( PnpServiceEventIdentifier )
                                  {
LABEL_733:
                                    if ( !v34 )
                                      goto LABEL_363;
LABEL_734:
                                    RtlStringExHandleOtherFlagsW(v11, v152, v169, &v271, &v296, 2304);
                                    goto LABEL_363;
                                  }
                                }
                                else
                                {
                                  v226 = 2147483646;
                                  a3 = &PnpServiceEventIdentifier;
                                  v227 = &v11[(_QWORD)v169];
                                  do
                                  {
                                    if ( !v226 )
                                      break;
                                    if ( !*a3 )
                                      break;
                                    *v227++ = *a3++;
                                    --v226;
                                    --v13;
                                  }
                                  while ( v13 );
                                  v228 = v227 - 1;
                                  if ( v13 )
                                    v228 = v227;
                                  *v228 = 0;
                                  v229 = -2147483643;
                                  if ( v13 )
                                    v229 = 0;
                                }
                                if ( v229 >= 0 )
                                {
                                  if ( v34 - 1 > 0x7FFFFFFE )
                                  {
                                    v13 = 3221225485LL;
                                  }
                                  else
                                  {
                                    v230 = v34;
                                    v231 = v11;
                                    v13 = 0;
                                    do
                                    {
                                      if ( !*v231 )
                                        break;
                                      ++v231;
                                      --v230;
                                    }
                                    while ( v230 );
                                    if ( !v230 )
                                      v13 = 3221225485LL;
                                    if ( (v13 & 0x80000000) == 0LL )
                                    {
                                      a3 = (WCHAR *)(v34 - v230);
                                      goto LABEL_535;
                                    }
                                  }
                                  a3 = 0;
LABEL_535:
                                  if ( (v13 & 0x80000000) != 0LL )
                                  {
                                    v232 = v13;
                                    goto LABEL_537;
                                  }
                                  v13 = v34 - (_QWORD)a3;
                                  if ( v34 - (unsigned __int64)a3 <= 1 )
                                  {
                                    v232 = -2147483643;
                                  }
                                  else
                                  {
                                    v249 = &v11[(_QWORD)a3];
                                    do
                                    {
                                      if ( !v194 )
                                        break;
                                      if ( !*v68 )
                                        break;
                                      *v249++ = *v68++;
                                      --v194;
                                      --v13;
                                    }
                                    while ( v13 );
                                    v250 = v249 - 1;
                                    if ( v13 )
                                      v250 = v249;
                                    *v250 = 0;
                                    v232 = -2147483643;
                                    if ( v13 )
                                    {
                                      v232 = 0;
                                      goto LABEL_537;
                                    }
                                  }
                                  if ( v34 )
                                    RtlStringExHandleOtherFlagsW(v11, v152, a3, &v271, &v296, 2048);
LABEL_537:
                                  if ( v232 < 0 )
                                    goto LABEL_363;
                                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
                                  {
                                    WPP_SF_S(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      21,
                                      WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                                      v11);
                                  }
                                  v18 = a6;
                                  DevRtlWriteTextLog(a6, 0x2000000, 65542, "Creating Install Process: %ws", v294);
                                  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                                  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
                                  StartupInfo.cb = 104;
                                  StartupInfo.lpDesktop = 0;
                                  EnterCriticalSection(&PnpInstallProcessLock);
                                  if ( CreateProcessW(Str, v11, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                                  {
                                    CurrentThreadId = GetCurrentThreadId();
                                    SetProcessId(CurrentThreadId, ProcessInformation.dwProcessId);
                                  }
                                  else
                                  {
                                    v234 = GetLastError();
                                    ExitCode = v234;
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                    {
                                      WPP_SF_d(
                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                        22,
                                        WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                                        v234);
                                    }
                                  }
                                  LeaveCriticalSection(&PnpInstallProcessLock);
                                  if ( ExitCode )
                                    goto LABEL_364;
                                  hProcess = ProcessInformation.hProcess;
                                  v274 = ProcessInformation.hProcess;
                                  hObject = ProcessInformation.hThread;
                                  Handles = ProcessInformation.hProcess;
                                  v235 = WaitForMultipleObjectsEx(1u, &Handles, 0, 0xFFFFFFFF, 0);
                                  EnterCriticalSection(&PnpInstallProcessLock);
                                  v236 = GetCurrentThreadId();
                                  SetProcessId(v236, 0);
                                  LeaveCriticalSection(&PnpInstallProcessLock);
                                  if ( v235 )
                                  {
                                    if ( v235 != -1 )
                                    {
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                      {
                                        WPP_SF_d(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          27,
                                          WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                                          v235);
                                      }
                                      ExitCode = 13;
                                      goto LABEL_749;
                                    }
                                    v264 = GetLastError();
                                    ExitCode = v264;
                                    v265 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                    {
                                      v266 = 26;
                                      goto LABEL_747;
                                    }
                                  }
                                  else
                                  {
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                    {
                                      WPP_SF_(
                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                        23,
                                        WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
                                    }
                                    if ( GetExitCodeProcess(hProcess, &ExitCode) )
                                    {
                                      v237 = UnbiasedTime / 0x2710;
                                      v238 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                                      {
                                        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                        {
                                          WPP_SF_d(
                                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                                            25,
                                            WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                                            ExitCode);
                                          v238 = WPP_GLOBAL_Control;
                                        }
                                        if ( v238 != &WPP_GLOBAL_Control && (*((_DWORD *)v238 + 7) & 0x40000) != 0 )
                                          WPP_SF_d(
                                            v238[2],
                                            28,
                                            WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                                            ExitCode);
                                      }
                                      DevRtlWriteTextLog(
                                        v18,
                                        0x2000000,
                                        65542,
                                        "Server install process exited with code 0x%08x",
                                        ExitCode);
                                      UnbiasedTime = 0;
                                      QueryUnbiasedInterruptTime(&UnbiasedTime);
                                      dwCreationFlags = UnbiasedTime / 0x2710 - v237;
                                      v176 = pDeviceID;
                                      v239 = a7;
                                      v240 = pdnDevInst;
                                      LogInstallDevice(
                                        pdnDevInst,
                                        a7,
                                        (__int64 *)pDeviceID,
                                        (__int64)v280,
                                        (__int64)Src,
                                        dwCreationFlags,
                                        ExitCode);
                                      pdnDevInst = 0;
                                      if ( CM_Locate_DevNodeW(&pdnDevInst, v176, 5u)
                                        || CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, pdnDevInst, 0) )
                                      {
                                        pulProblemNumber = 0;
                                        v241 = 0;
                                        pulStatus = 0;
                                      }
                                      else
                                      {
                                        v241 = pulStatus;
                                      }
                                      v242 = ExitCode;
                                      if ( ExitCode )
                                      {
                                        v20 = 4;
                                        if ( (v241 & 0x400) != 0 && v240 != 3 )
                                        {
                                          PnpSetObjectProp(
                                            v176,
                                            v13,
                                            (__int64)a3,
                                            (const DEVPROPKEY *)DEVPKEY_Device_InstallError,
                                            0x17u,
                                            (PBYTE)&ExitCode,
                                            4u);
                                          SetDeviceInstallDate(v176);
                                          v242 = ExitCode;
                                        }
                                      }
                                      else
                                      {
                                        if ( (v241 & 0x400) == 0 )
                                        {
                                          PnpSetObjectProp(
                                            v176,
                                            v13,
                                            (__int64)a3,
                                            (const DEVPROPKEY *)DEVPKEY_Device_InstallError,
                                            0,
                                            0,
                                            0);
                                          SetDeviceInstallDate(v176);
                                          PnpSetObjectProp(
                                            v176,
                                            v243,
                                            v244,
                                            (const DEVPROPKEY *)DEVPKEY_Device_InstallInf,
                                            0,
                                            0,
                                            0);
                                          PnpSetObjectProp(
                                            v176,
                                            v245,
                                            v246,
                                            (const DEVPROPKEY *)DEVPKEY_Device_InstallStrongName,
                                            0,
                                            0,
                                            0);
                                          v242 = ExitCode;
                                        }
                                        v20 = 4;
                                      }
                                      if ( v242 == -536870328 && (v239 & 1) == 0 )
                                      {
                                        pdnDevInst = GetDeviceConfigFlags(v176) | 0x40;
                                        PnpSetDeviceRegProp(v176, v247, v248, &pdnDevInst);
                                        SetDeviceProblem(v176);
                                      }
                                      goto LABEL_366;
                                    }
                                    v264 = GetLastError();
                                    ExitCode = v264;
                                    v265 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
                                    {
                                      v266 = 24;
LABEL_747:
                                      WPP_SF_d(v265[2], v266, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v264);
                                    }
                                  }
LABEL_749:
                                  v176 = pDeviceID;
                                  v20 = 4;
                                  goto LABEL_367;
                                }
                                goto LABEL_733;
                              }
LABEL_719:
                              if ( !v34 )
                                goto LABEL_363;
                              goto LABEL_734;
                            }
LABEL_705:
                            if ( !v34 )
                              goto LABEL_363;
                            goto LABEL_734;
                          }
LABEL_363:
                          v18 = a6;
                          ExitCode = 13;
LABEL_364:
                          v20 = 4;
LABEL_365:
                          v176 = pDeviceID;
LABEL_366:
                          hProcess = v274;
LABEL_367:
                          v12 = P;
                          goto LABEL_368;
                        }
LABEL_357:
                        v11 = lpCommandLine;
                        goto LABEL_363;
                      }
LABEL_662:
                      if ( v34 )
                        RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v103, &v271, &v296, 2304);
                      goto LABEL_357;
                    }
LABEL_648:
                    if ( v34 )
                      RtlStringExHandleOtherFlagsW(lpCommandLine, 2 * v34, v82, &v277, &v296, 2048);
                    goto LABEL_357;
                  }
LABEL_633:
                  if ( v34 )
                    RtlStringExHandleOtherFlagsW(v41, 2 * v34, v54, &v277, &v296, 2048);
                  goto LABEL_357;
                }
                v258 = RtlNtStatusToDosErrorNoTeb(v262);
                v11 = lpCommandLine;
                goto LABEL_608;
              }
              v259 = StringSearchAndReplace(v8);
              v287 = v259;
              if ( v259 )
              {
                v8 = (const wchar_t *)v259;
              }
              else
              {
                ExitCode = GetLastError();
                if ( ExitCode )
                  goto LABEL_609;
              }
              v260 = RtlUnalignedStringCchLengthW(v8, 260, &v277);
              if ( v260 >= 0 )
              {
                v30 = v277;
                goto LABEL_27;
              }
              v254 = v260;
LABEL_606:
              v258 = RtlNtStatusToDosErrorNoTeb(v254);
LABEL_608:
              ExitCode = v258;
              goto LABEL_609;
            }
          }
          else
          {
            LODWORD(v13) = -1073741811;
          }
          v254 = v13;
          goto LABEL_606;
        }
      }
      ExitCode = RtlNtStatusToDosErrorNoTeb(v25);
      v176 = pDeviceID;
      v12 = 0;
      hProcess = 0;
    }
    else
    {
      ExitCode = 13;
      v176 = pDeviceID;
      v12 = 0;
      hProcess = 0;
    }
  }
  else
  {
    ExitCode = GetLastError();
    v176 = pDeviceID;
    v12 = 0;
    hProcess = 0;
  }
LABEL_368:
  PnpSetObjectProp(v176, v13, (__int64)a3, (const DEVPROPKEY *)DEVPKEY_Device_InstallInProgress, 0, 0, 0);
  if ( hObject )
    CloseHandle(hObject);
  if ( hProcess )
    CloseHandle(hProcess);
  if ( v11 )
    RtlFreeHeap(PnpHeapHandle, 0, v11);
  if ( v12 )
    RtlFreeHeap(PnpHeapHandle, 0, v12);
  if ( v287 )
    RtlFreeHeap(PnpHeapHandle, 0, v287);
  if ( v288 )
    RtlFreeHeap(PnpHeapHandle, 0, v288);
  if ( v278 )
  {
    v178 = ExitCode;
    v179 = GetLastError();
    v289 = 0;
    v290 = 0;
    v291 = 0;
    v292 = 0;
    v180 = 0;
    v296 = 0;
    v297 = 0;
    pdnDevInst = 0;
    if ( g_sputils_LogInitialized || (unsigned int)pSpUtilsLogInitialize() )
    {
      v251 = &GlobalDevLogData;
      if ( (v18 & 3) != 3 )
        v251 = (__int64 *)&GlobalAppLogData;
      if ( !(unsigned int)TextLogMapFile(v251, &v289, 512, 2) )
      {
        v180 = 1;
        if ( (unsigned int)TextLogFindSection(&v289, (unsigned int)v18, &v296, &pdnDevInst) )
        {
          if ( (TextLogWriteSectionFooter((unsigned int)&v289, (unsigned int)&v296, v252, 1, v178),
                TextLogDeleteCtlTag(&v289, pdnDevInst),
                (_DWORD)v292)
            && (unsigned int)(DWORD2(v290) - v290) >= *((_DWORD *)v251 + 2)
            || (unsigned int)TextLogContainsPendingRenameTag(&v289) )
          {
            if ( (unsigned int)TextLogRequestLogFileRename(&v289) )
            {
              if ( (unsigned int)TextLogRenameLogFile(&v289) )
              {
                if ( (_DWORD)v292 )
                  TextLogDecayLogFileBackups(*(STRSAFE_LPCWSTR *)(v291 + 16));
                *((_DWORD *)v251 + 6) = 0;
              }
              else
              {
                v253 = GetLastError() - 1;
                if ( !v253 || v253 == 49 )
                  *((_DWORD *)v251 + 6) = 4;
                else
                  v20 = ++*((_DWORD *)v251 + 6);
                if ( (_DWORD)v292 && v20 >= 4 && (*((_DWORD *)v251 + 3) & 0x2000) == 0 )
                {
                  LogStatus = TextLogGetLogStatus(v251);
                  if ( (LogStatus & 0x2000) == 0 )
                  {
                    TextLogQueueLogFileBackup(*(LPCWSTR *)(v291 + 16));
                    TextLogSetLogStatus(v251, LogStatus | 0x2000u);
                  }
                  *((_DWORD *)v251 + 3) |= 0x2000u;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      GetLastError();
    }
    if ( v180 )
      TextLogUnmapFile(&v289);
    SetLastError(v179);
  }
  else
  {
    DevRtlWriteTextLog(v18, 0x2000000, 262148, "{Plug and Play Service: Device Install exit(%08x)}", ExitCode);
  }
  if ( (Microsoft_Windows_UserPnpEnableBits & 0x10) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v181, (unsigned int)EXIT_PNP_INSTALL_DEVICE, v182, 1, (__int64)&v296);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  return ExitCode;
}

```

## disassembly

```asm
0x1800056d0  push    rbx
0x1800056d2  push    rsi
0x1800056d3  push    rdi
0x1800056d4  push    r12
0x1800056d6  push    r13
0x1800056d8  push    r14
0x1800056da  push    r15
0x1800056dc  sub     rsp, 410h
0x1800056e3  mov     rax, cs:__security_cookie
0x1800056ea  xor     rax, rsp
0x1800056ed  mov     [rsp+448h+var_48], rax
0x1800056f5  mov     rsi, r9
0x1800056f8  mov     [rsp+448h+var_3A8], r9
0x180005700  mov     r15, r8
0x180005703  mov     [rsp+448h+pDeviceID], r8
0x180005708  mov     rax, rdx
0x18000570b  mov     [rsp+448h+var_390], rdx
0x180005713  mov     [rsp+448h+pdnDevInst], ecx
0x18000571a  mov     rdx, [rsp+448h+arg_20]
0x180005722  mov     [rsp+448h+Src], rdx
0x18000572a  mov     [rsp+448h+ExitCode], 0
0x180005732  xor     r14d, r14d
0x180005735  mov     [rsp+448h+lpCommandLine], r14
0x18000573a  xor     r12d, r12d
0x18000573d  mov     [rsp+448h+var_370], r12
0x180005745  mov     [rsp+448h+var_368], r12
0x18000574d  mov     [rsp+448h+var_3D0], r12
0x180005752  xor     ecx, ecx
0x180005754  mov     [rsp+448h+hObject], rcx
0x18000575c  xorps   xmm0, xmm0
0x18000575f  movups  xmmword ptr [rsp+448h+StartupInfo.cb], xmm0
0x180005767  movups  xmmword ptr [rsp+448h+StartupInfo.lpDesktop], xmm0
0x18000576f  movups  xmmword ptr [rsp+448h+StartupInfo.dwX], xmm0
0x180005777  movups  xmmword ptr [rsp+448h+StartupInfo.dwXCountChars], xmm0
0x18000577f  movups  xmmword ptr [rsp+448h+StartupInfo.wShowWindow], xmm0
0x180005787  movups  xmmword ptr [rsp+448h+StartupInfo.hStdInput], xmm0
0x18000578f  mov     dword ptr [rsp+448h+StartupInfo.hStdError], ecx
0x180005796  movups  xmmword ptr [rsp+448h+ProcessInformation.hProcess], xmm0
0x18000579e  mov     qword ptr [rsp+448h+ProcessInformation.dwProcessId], rcx
0x1800057a6  mov     [rsp+448h+pulStatus], ecx
0x1800057ad  mov     [rsp+448h+pulProblemNumber], ecx
0x1800057b4  mov     [rsp+448h+var_3B0], ecx
0x1800057bb  mov     [rsp+448h+Handles], rcx
0x1800057c3  mov     [rsp+448h+PropertyBuffer], cl
0x1800057ca  lea     rdx, WPP_GLOBAL_Control
0x1800057d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057d8  cmp     rcx, rdx
0x1800057db  jnz     loc_18000735B
0x1800057e1  test    cs:Microsoft_Windows_UserPnpEnableBits, 10h
0x1800057e8  jnz     loc_18000738A
0x1800057ee  mov     edi, [rsp+448h+arg_30]
0x1800057f5  mov     ebx, edi
0x1800057f7  and     ebx, 1
0x1800057fa  jnz     loc_180006B28
0x180005800  mov     [rsp+448h+PropertyBuffer], 0FFh
0x180005808  mov     dword ptr [rsp+448h+lpEnvironment], 1; ULONG
0x180005810  lea     rax, [rsp+448h+PropertyBuffer]
0x180005818  mov     qword ptr [rsp+448h+dwCreationFlags], rax; PropertyBuffer
0x18000581d  mov     [rsp+448h+bInheritHandles], 11h; PropertyType
0x180005825  lea     r9, DEVPKEY_Device_InstallInProgress
0x18000582c  mov     rcx, r15; pDeviceID
0x18000582f  call    PnpSetObjectProp
0x180005834  mov     r15, [rsp+448h+arg_28]
0x18000583c  test    r15, r15
0x18000583f  jz      loc_180005BE8
0x180005845  mov     r12, [rsp+448h+pDeviceID]
0x18000584a  mov     qword ptr [rsp+448h+bInheritHandles], r12
0x18000584f  lea     r9, aPlugAndPlaySer_4; "{Plug and Play Service: Device Install "...
0x180005856  mov     edx, 2000000h
0x18000585b  mov     r8d, 20004h
0x180005861  mov     rcx, r15
0x180005864  call    cs:__imp_DevRtlWriteTextLog
0x18000586a  mov     r13d, 4
0x180005870  mov     rcx, r15
0x180005873  call    cs:__imp_DevRtlSetThreadLogToken
0x180005879  mov     [rsp+448h+UnbiasedTime], r14
0x180005881  lea     rcx, [rsp+448h+UnbiasedTime]; UnbiasedTime
0x180005889  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000588f  cmp     cs:ServerInstallBatchTimeoutDetected, r14d
0x180005896  jnz     loc_1800074B3
0x18000589c  lea     rcx, [rsp+448h+Str]
0x1800058a4  call    GetDeviceInstallerFilename
0x1800058a9  test    eax, eax
0x1800058ab  jz      loc_1800074DE
0x1800058b1  mov     edx, 5Ch ; '\'; Ch
0x1800058b6  lea     rcx, [rsp+448h+Str]; Str
0x1800058be  call    cs:__imp_wcsrchr
0x1800058c4  test    rax, rax
0x1800058c7  jz      loc_1800074F8
0x1800058cd  lea     rdi, [rax+2]
0x1800058d1  mov     [rsp+448h+var_310], rdi
0x1800058d9  test    rdi, rdi
0x1800058dc  jz      loc_180007302
0x1800058e2  mov     ecx, 7FFFh
0x1800058e7  mov     rax, rdi
0x1800058ea  xor     edx, edx
0x1800058ec  nop     dword ptr [rax+00h]
0x1800058f0  cmp     [rax], dx
0x1800058f3  jz      short loc_1800058FF
0x1800058f5  add     rax, 2
0x1800058f9  sub     rcx, 1
0x1800058fd  jnz     short loc_1800058F0
0x1800058ff  test    rcx, rcx
0x180005902  jz      loc_180007510
0x180005908  mov     ebx, 7FFFh
0x18000590d  sub     rbx, rcx
0x180005910  xor     eax, eax
0x180005912  test    edx, edx
0x180005914  cmovs   rbx, rax
0x180005918  js      loc_180007307
0x18000591e  mov     rcx, r12; Src
0x180005921  call    StringSearchAndReplace
0x180005926  mov     [rsp+448h+P], rax
0x18000592b  test    rax, rax
0x18000592e  jz      loc_18000751A
0x180005934  mov     [rsp+448h+var_3E8], rax
0x180005939  test    rax, rax
0x18000593c  jz      loc_18000732D
0x180005942  mov     r8d, 0C8h
0x180005948  mov     ecx, r8d
0x18000594b  xor     edx, edx
0x18000594d  nop     dword ptr [rax]
0x180005950  cmp     [rax], dx
0x180005953  jz      short loc_18000595F
0x180005955  add     rax, 2
0x180005959  sub     rcx, 1
0x18000595d  jnz     short loc_180005950
0x18000595f  test    rcx, rcx
0x180005962  jz      loc_180007530
0x180005968  sub     r8, rcx
0x18000596b  xor     eax, eax
0x18000596d  test    edx, edx
0x18000596f  cmovs   r8, rax
0x180005973  js      loc_180007332
0x180005979  add     rbx, 16h
0x18000597d  add     rbx, r8
0x180005980  xor     eax, eax
0x180005982  mov     [rsp+448h+var_3B8], rax
0x18000598a  test    rsi, rsi
0x18000598d  jnz     loc_180007562
0x180005993  add     rax, 3
0x180005997  add     rbx, rax
0x18000599a  xor     eax, eax
0x18000599c  mov     [rsp+448h+var_3B8], rax
0x1800059a4  mov     r12, [rsp+448h+Src]
0x1800059ac  test    r12, r12
0x1800059af  jnz     loc_1800075B0
0x1800059b5  lea     r12, [rax+39h]
0x1800059b9  add     r12, rbx
0x1800059bc  lea     rax, [r12+r12]
0x1800059c0  cmp     rax, 0F42400h
0x1800059c6  ja      loc_180006B54
0x1800059cc  mov     r8, rax; Size
0x1800059cf  mov     edx, 8; Flags
0x1800059d4  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800059db  call    cs:__imp_RtlAllocateHeap
0x1800059e1  mov     r9, rax
0x1800059e4  mov     [rsp+448h+lpCommandLine], r9
0x1800059e9  test    r9, r9
0x1800059ec  jz      loc_180007609
0x1800059f2  lea     rax, [r12-1]
0x1800059f7  mov     r15d, 7FFFFFFEh
0x1800059fd  cmp     rax, r15
0x180005a00  ja      loc_18000761B
0x180005a06  mov     eax, r15d
0x180005a09  mov     rdx, rdi
0x180005a0c  mov     r8, r12
0x180005a0f  nop
0x180005a10  test    rax, rax
0x180005a13  jz      short loc_180005A32
0x180005a15  movzx   ecx, word ptr [rdx]
0x180005a18  test    cx, cx
0x180005a1b  jz      short loc_180005A32
0x180005a1d  mov     [r9], cx
0x180005a21  add     r9, 2
0x180005a25  add     rdx, 2
0x180005a29  dec     rax
0x180005a2c  sub     r8, 1
0x180005a30  jnz     short loc_180005A10
0x180005a32  lea     rcx, [r9-2]
0x180005a36  test    r8, r8
0x180005a39  cmovnz  rcx, r9
0x180005a3d  xor     eax, eax
0x180005a3f  mov     [rcx], ax
0x180005a42  mov     edi, 80000005h
0x180005a47  mov     ecx, edi
0x180005a49  test    r8, r8
0x180005a4c  cmovnz  ecx, eax; Status
0x180005a4f  test    ecx, ecx
0x180005a51  js      loc_180007639
0x180005a57  mov     r9d, [rsp+448h+pdnDevInst]
0x180005a5f  lea     r8, aLx; "%lx"
0x180005a66  mov     edx, 11h
0x180005a6b  lea     rcx, [rsp+448h+var_280]
0x180005a73  call    RtlStringCchPrintfW
0x180005a78  test    eax, eax
0x180005a7a  js      loc_18000667D
0x180005a80  lea     rax, [r12-1]
0x180005a85  mov     r11, [rsp+448h+lpCommandLine]
0x180005a8a  cmp     rax, r15
0x180005a8d  ja      loc_18000765F
0x180005a93  mov     rcx, r12
0x180005a96  mov     rax, r11
0x180005a99  xor     ebx, ebx
0x180005a9b  nop     dword ptr [rax+rax+00h]
0x180005aa0  cmp     [rax], bx
0x180005aa3  jz      short loc_180005AAF
0x180005aa5  add     rax, 2
0x180005aa9  sub     rcx, 1
0x180005aad  jnz     short loc_180005AA0
0x180005aaf  test    rcx, rcx
0x180005ab2  jz      loc_180007655
0x180005ab8  test    ebx, ebx
0x180005aba  js      loc_180007664
0x180005ac0  mov     r10, r12
0x180005ac3  sub     r10, rcx
0x180005ac6  lea     r13, asc_18001C3A8; " \""
0x180005acd  test    ebx, ebx
0x180005acf  js      loc_18000667D
0x180005ad5  mov     rdx, r12
0x180005ad8  sub     rdx, r10
0x180005adb  cmp     rdx, 1
0x180005adf  jbe     loc_18000766C
0x180005ae5  mov     rcx, r15
0x180005ae8  mov     r8, r13
0x180005aeb  lea     r9, [r11+r10*2]
0x180005aef  nop
0x180005af0  test    rcx, rcx
0x180005af3  jz      short loc_180005B13
0x180005af5  movzx   eax, word ptr [r8]
0x180005af9  test    ax, ax
0x180005afc  jz      short loc_180005B13
0x180005afe  mov     [r9], ax
0x180005b02  add     r9, 2
0x180005b06  add     r8, 2
0x180005b0a  dec     rcx
0x180005b0d  sub     rdx, 1
0x180005b11  jnz     short loc_180005AF0
0x180005b13  lea     rcx, [r9-2]
0x180005b17  test    rdx, rdx
0x180005b1a  cmovnz  rcx, r9
0x180005b1e  xor     eax, eax
0x180005b20  mov     [rcx], ax
0x180005b23  mov     ebx, edi
0x180005b25  test    rdx, rdx
0x180005b28  cmovnz  ebx, eax
0x180005b2b  jz      loc_18000766E
0x180005b31  test    ebx, ebx
0x180005b33  js      loc_18000667D
0x180005b39  lea     rax, [r12-1]
0x180005b3e  cmp     rax, r15
0x180005b41  ja      loc_1800076B7
0x180005b47  mov     rcx, r12
0x180005b4a  mov     rax, r11
0x180005b4d  xor     ebx, ebx
0x180005b4f  nop
0x180005b50  cmp     [rax], bx
0x180005b53  jz      short loc_180005B5F
0x180005b55  add     rax, 2
0x180005b59  sub     rcx, 1
0x180005b5d  jnz     short loc_180005B50
0x180005b5f  test    rcx, rcx
0x180005b62  jz      loc_1800076AD
0x180005b68  test    ebx, ebx
0x180005b6a  js      loc_1800076BC
0x180005b70  mov     r10, r12
0x180005b73  sub     r10, rcx
0x180005b76  test    ebx, ebx
0x180005b78  js      loc_18000667D
0x180005b7e  mov     rdx, r12
0x180005b81  sub     rdx, r10
0x180005b84  cmp     rdx, 1
0x180005b88  jbe     loc_1800076C4
0x180005b8e  mov     rcx, r15
0x180005b91  lea     r8, [rsp+448h+var_280]
0x180005b99  lea     r9, [r11+r10*2]
0x180005b9d  nop     dword ptr [rax]
0x180005ba0  test    rcx, rcx
0x180005ba3  jz      short loc_180005BC3
0x180005ba5  movzx   eax, word ptr [r8]
0x180005ba9  test    ax, ax
0x180005bac  jz      short loc_180005BC3
0x180005bae  mov     [r9], ax
0x180005bb2  add     r9, 2
0x180005bb6  add     r8, 2
0x180005bba  dec     rcx
0x180005bbd  sub     rdx, 1
0x180005bc1  jnz     short loc_180005BA0
0x180005bc3  lea     rcx, [r9-2]
0x180005bc7  test    rdx, rdx
0x180005bca  cmovnz  rcx, r9
0x180005bce  xor     eax, eax
0x180005bd0  mov     [rcx], ax
0x180005bd3  mov     ebx, edi
0x180005bd5  test    rdx, rdx
0x180005bd8  cmovnz  ebx, eax
0x180005bdb  test    ebx, ebx
0x180005bdd  js      loc_1800076D6
0x180005be3  jmp     loc_180005CA0
0x180005be8  mov     eax, edi
  ... truncated ...
```
