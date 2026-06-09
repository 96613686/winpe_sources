# CExec::ExecuteProcess(Schema::Process::ProcessParameters const &,void *,void *,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x1400e0b10`
- end: `0x1400e1b10`
- name: `?ExecuteProcess@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@PEAX11AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `4096`
- prototype: `LPHANDLE __fastcall(HANDLE *, __int64, void *, void *, HANDLE hSourceHandle, ConsoleToPipeRedirector *, __int64)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400aa790`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x140006098`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x14001e4f4`
- `0x14002dd18`
- `0x14003f1c4`
- `0x140040048`
- `0x1400aebe4`
- `0x1400df8a8`
- `0x1400dfbe0`
- `0x1400dfff4`
- `0x1400e0244`
- `0x1400e02ac`
- `0x1400e0538`
- `0x1400e072c`
- `0x1400e099c`
- `0x1400e0b10`
- `0x1400e1be8`
- `0x1400e21dc`
- `0x1400e2dd8`
- `0x1400e2efc`
- `0x1400e3020`
- `0x1400e3144`
- `0x1400e3b1c`
- `0x1400e3d58`
- `0x1400e4970`
- `0x1400e4cd4`
- `0x1400e5fa8`
- `0x1400e6104`
- `0x1400e8cec`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e0dde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e11f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1220`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e0dde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e11f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e0dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e11e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e120d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e0dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e11e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e120d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400e0fa8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400e0fa8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400e1984`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400e1984`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400e0d08`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400e0d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400e190d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400e190d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e17cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e17d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e17cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e17d4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e13ab`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e13fb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e1431`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e156b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e13ab`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e13fb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e1431`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1400e156b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400e1750`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400e1750`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400e17f9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400e17f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e0dd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e0f9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e11ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e0dd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e0f9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e11ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e19f5`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x1400e1920`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x1400e1920`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x1400e11c3`
- `api-ms-win-core-console-internal-l1-1-0!CreatePseudoConsoleAsUser` at `0x1400e11c3`
- `profapi!__imp_CreateEnvBlock` at `0x1400e0fd5`
- `profapi!__imp_CreateEnvBlock` at `0x1400e0fd5`
- `profapi!__imp_DestroyEnvBlock` at `0x1400e197d`
- `profapi!__imp_DestroyEnvBlock` at `0x1400e197d`
- `profapi!__imp_LoadProfileBasic` at `0x1400e0f2f`
- `profapi!__imp_LoadProfileBasic` at `0x1400e0f2f`

## string_xrefs

- `0x1400e1a49`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1a5b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1a70`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1a82`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1a97`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1aac`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1ac5`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1ad7`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1aec`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e1afe`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e147f`: `CreateProcessAsUserW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPHANDLE __fastcall CExec::ExecuteProcess(
        HANDLE *a1,
        __int64 a2,
        void *a3,
        void *a4,
        HANDLE hSourceHandle,
        ConsoleToPipeRedirector *a6,
        __int64 a7)
{
  const unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r14
  const unsigned __int16 *v13; // rbx
  ConsoleToPipeRedirector *v14; // r14
  char v15; // bl
  __int64 v16; // r15
  __int64 v17; // r13
  HANDLE v18; // rdi
  DWORD LastError; // ebx
  __int16 v20; // r12
  int ProfileBasic; // eax
  HANDLE v22; // rdi
  const char *v23; // r9
  int v24; // eax
  __int64 v25; // rdx
  ConsoleToPipeRedirector *v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // rax
  __int64 **v29; // rdx
  __int64 *i; // rcx
  __int64 j; // rcx
  __int64 v32; // rax
  bool v33; // di
  int PseudoConsoleAsUser; // eax
  DWORD v35; // ebx
  DWORD v36; // ebx
  __int64 v37; // r13
  HANDLE *Console; // rcx
  HANDLE *v39; // rcx
  void *v40; // rbx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v41; // rcx
  const char *v42; // r9
  char *v43; // r12
  const char *v44; // r9
  const char *v45; // r9
  const unsigned __int16 *v46; // rdx
  const WCHAR *lpCurrentDirectory; // rdi
  const WCHAR *v48; // rcx
  const char *v49; // r9
  const WCHAR *p_UserData; // rdx
  WCHAR *Ptr; // rcx
  __int64 ApplicationName; // rbx
  __int128 *lpEnvironment; // rax
  HANDLE v54; // rsi
  const char *v55; // r9
  HANDLE hProcess; // rbx
  HANDLE CurrentProcess; // rdi
  HANDLE v58; // rax
  const char *v59; // r9
  _DWORD *v60; // rax
  DWORD dwProcessId; // ecx
  volatile signed __int32 *v62; // rbx
  struct _PROCESS_INFORMATION *v63; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v64; // rcx
  int cbSize; // [rsp+20h] [rbp-E0h]
  char v67; // [rsp+60h] [rbp-A0h]
  ConsoleToPipeRedirector *v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h]
  __int16 v70[4]; // [rsp+78h] [rbp-88h]
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v72; // [rsp+88h] [rbp-78h]
  HANDLE v73; // [rsp+90h] [rbp-70h]
  __int64 v74; // [rsp+98h] [rbp-68h]
  char v75; // [rsp+A1h] [rbp-5Fh]
  WCHAR *v76; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v77; // [rsp+B0h] [rbp-50h]
  HANDLE v78; // [rsp+B8h] [rbp-48h]
  LPHANDLE lpTargetHandle; // [rsp+C0h] [rbp-40h]
  HANDLE v80[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v81[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v82; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v83; // [rsp+E4h] [rbp-1Ch] BYREF
  HANDLE *v84; // [rsp+E8h] [rbp-18h]
  __int64 v85; // [rsp+F0h] [rbp-10h]
  __int64 v86; // [rsp+F8h] [rbp-8h]
  _BYTE Src[32]; // [rsp+100h] [rbp+0h] BYREF
  char v88[32]; // [rsp+120h] [rbp+20h] BYREF
  HANDLE v89; // [rsp+140h] [rbp+40h] BYREF
  __int64 v90; // [rsp+148h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+150h] [rbp+50h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v93; // [rsp+1D8h] [rbp+D8h]
  PVOID lpValue; // [rsp+1E0h] [rbp+E0h]
  HANDLE hObject; // [rsp+1E8h] [rbp+E8h] BYREF
  HANDLE v96; // [rsp+1F0h] [rbp+F0h] BYREF
  HANDLE TargetHandle; // [rsp+1F8h] [rbp+F8h] BYREF
  HANDLE hToken[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v99; // [rsp+210h] [rbp+110h]
  __int64 v100; // [rsp+218h] [rbp+118h]
  LPVOID v101; // [rsp+220h] [rbp+120h] BYREF
  __int128 v102; // [rsp+228h] [rbp+128h] BYREF
  __int128 v103; // [rsp+238h] [rbp+138h] BYREF
  __int64 v104; // [rsp+248h] [rbp+148h]
  unsigned __int64 v105; // [rsp+250h] [rbp+150h]
  void **v106; // [rsp+260h] [rbp+160h] BYREF
  int v107; // [rsp+268h] [rbp+168h] BYREF
  char v108; // [rsp+26Ch] [rbp+16Ch]
  int v109; // [rsp+290h] [rbp+190h] BYREF
  const char *v110; // [rsp+298h] [rbp+198h]
  __int64 v111; // [rsp+2A0h] [rbp+1A0h]
  char v112; // [rsp+2A8h] [rbp+1A8h]
  int v113; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v114[152]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v115; // [rsp+350h] [rbp+250h]
  __int64 v116; // [rsp+358h] [rbp+258h]
  int v117; // [rsp+360h] [rbp+260h]
  __int64 v118; // [rsp+368h] [rbp+268h]
  int *v119; // [rsp+370h] [rbp+270h]
  __int64 v120; // [rsp+378h] [rbp+278h]
  __int64 v121; // [rsp+380h] [rbp+280h]
  void ***v122; // [rsp+388h] [rbp+288h]
  __int64 v123; // [rsp+390h] [rbp+290h]
  int v124; // [rsp+398h] [rbp+298h]
  int *v125; // [rsp+3A0h] [rbp+2A0h]
  char v126; // [rsp+3A8h] [rbp+2A8h]
  void **v127; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v128; // [rsp+3B8h] [rbp+2B8h] BYREF
  char v129; // [rsp+3BCh] [rbp+2BCh]
  int v130; // [rsp+3E0h] [rbp+2E0h] BYREF
  const char *v131; // [rsp+3E8h] [rbp+2E8h]
  __int64 v132; // [rsp+3F0h] [rbp+2F0h]
  char v133; // [rsp+3F8h] [rbp+2F8h]
  int v134; // [rsp+400h] [rbp+300h]
  char v135[152]; // [rsp+408h] [rbp+308h] BYREF
  __int64 v136; // [rsp+4A0h] [rbp+3A0h]
  __int64 v137; // [rsp+4A8h] [rbp+3A8h]
  int v138; // [rsp+4B0h] [rbp+3B0h]
  __int64 v139; // [rsp+4B8h] [rbp+3B8h]
  int *v140; // [rsp+4C0h] [rbp+3C0h]
  __int64 v141; // [rsp+4C8h] [rbp+3C8h]
  __int64 v142; // [rsp+4D0h] [rbp+3D0h]
  void ***v143; // [rsp+4D8h] [rbp+3D8h]
  __int64 v144; // [rsp+4E0h] [rbp+3E0h]
  int v145; // [rsp+4E8h] [rbp+3E8h]
  int *v146; // [rsp+4F0h] [rbp+3F0h]
  char v147; // [rsp+4F8h] [rbp+3F8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+500h] [rbp+400h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v149; // [rsp+510h] [rbp+410h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v150; // [rsp+520h] [rbp+420h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v151; // [rsp+530h] [rbp+430h] BYREF
  _QWORD Value[3]; // [rsp+540h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  lpTargetHandle = a1;
  v84 = a1;
  v68 = a6;
  v90 = a7;
  memset_0(&v127, 0, 0x150u);
  v128 = 0;
  v129 = 0;
  v133 = 0;
  v130 = 0;
  v131 = "ExecuteProcess";
  v132 = 0;
  v134 = 0;
  v136 = 0;
  v137 = 0;
  memset_0(v135, 0, sizeof(v135));
  v138 = 1;
  v139 = 0;
  v140 = &v128;
  v141 = 0;
  v142 = 0;
  v143 = &v127;
  v144 = 0;
  v145 = 0;
  v146 = &v130;
  v147 = 0;
  v127 = &CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess *)&v127);
  v10 = L"pipe";
  v11 = L"pipe";
  if ( !hSourceHandle )
    v11 = L"<n/a>";
  v12 = L"pipe";
  if ( !a4 )
    v12 = L"<n/a>";
  if ( !a3 )
    v10 = L"<n/a>";
  v13 = (const unsigned __int16 *)(a2 + 32);
  v76 = (WCHAR *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) > 7u )
    v13 = *(const unsigned __int16 **)v13;
  if ( g_VmlEtwTrace )
  {
    VmCreateDataDescriptor(&v151, &v83, v11);
    VmCreateDataDescriptor(&v150, &v82, v12);
    VmCreateDataDescriptor(&v149, &v81[1], v10);
    VmCreateDataDescriptor(&UserData, v81, v13);
    v14 = 0;
    if ( g_VmlEtwTrace )
      EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_CREATE_PROCESS, 4u, &UserData);
  }
  else
  {
    v14 = 0;
  }
  v15 = *(_BYTE *)(a2 + 169);
  v67 = v15;
  TargetHandle = 0;
  CExec::ConnectStdDevicePipe(&TargetHandle, a3);
  v96 = 0;
  CExec::ConnectStdDevicePipe(&v96, a4);
  hObject = 0;
  CExec::ConnectStdDevicePipe(&hObject, hSourceHandle);
  v85 = -1;
  v86 = -1;
  *(_QWORD *)v81 = -1;
  v16 = -1;
  v72 = (HANDLE)-1LL;
  v17 = -1;
  v74 = -1;
  if ( v15 )
  {
    v16 = (__int64)TargetHandle;
    v72 = TargetHandle;
    TargetHandle = (HANDLE)-1LL;
    v17 = (__int64)v96;
    v74 = (__int64)v96;
    v96 = (HANDLE)-1LL;
    v18 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v18);
      SetLastError(LastError);
      v15 = v67;
    }
    hObject = (HANDLE)-1LL;
  }
  if ( *(_WORD *)(a2 + 174) )
    v70[0] = *(_WORD *)(a2 + 174);
  else
    *(_DWORD *)v70 = 25;
  if ( *(_WORD *)(a2 + 176) )
    v20 = *(_WORD *)(a2 + 176);
  else
    v20 = 80;
  v78 = 0;
  hToken[0] = 0;
  CExec::GetProcessToken(hToken, a2);
  memset_0(&v106, 0, 0x150u);
  v107 = 0;
  v108 = 0;
  v112 = 0;
  v109 = 0;
  v110 = "ExecuteProcess_LoadProfile";
  v111 = 0;
  v113 = 0;
  v115 = 0;
  v116 = 0;
  memset_0(v114, 0, sizeof(v114));
  v117 = 1;
  v118 = 0;
  v119 = &v107;
  v120 = 0;
  v121 = 0;
  v122 = &v106;
  v123 = 0;
  v124 = 0;
  v125 = &v109;
  v126 = 0;
  v106 = &CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable';
  CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity((CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *)&v106);
  ProfileBasic = LoadProfileBasic(hToken[0], 0);
  if ( ProfileBasic < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)ProfileBasic,
      cbSize);
  v22 = hToken[0];
  v73 = hToken[0];
  hToken[0] = 0;
  v78 = v73;
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v106);
  v106 = &CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v106);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v106);
  if ( (unsigned __int64)hToken[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hToken[0]);
  if ( !ImpersonateLoggedOnUser(v22) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v23);
  v75 = 1;
  v101 = 0;
  v24 = CreateEnvBlock(&v101, v22, 0);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)v24,
      cbSize);
  v103 = 0;
  v104 = 0;
  v105 = 7;
  LOWORD(v103) = 0;
  v102 = 0;
  CExec::EnvironmentBlockToMap(&v102, v101);
  v26 = v68;
  if ( *(_QWORD *)(a2 + 160) || *((_QWORD *)v68 + 2) )
  {
    CExec::UpdateEnvironmentMap(&v102, a2 + 152, v68);
    v68 = 0;
    v69 = 0;
    hToken[0] = &v68;
    hToken[1] = &v68;
    v27 = operator new(0x60u);
    *v27 = v27;
    v27[1] = v27;
    v27[2] = v27;
    *((_WORD *)v27 + 12) = 257;
    v68 = (ConsoleToPipeRedirector *)v27;
    v28 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(
            &v68,
            *(_QWORD *)(v102 + 8),
            v27);
    *((_QWORD *)v68 + 1) = v28;
    v69 = *((_QWORD *)&v102 + 1);
    v29 = (__int64 **)*((_QWORD *)v68 + 1);
    if ( *((_BYTE *)v29 + 25) )
    {
      *(_QWORD *)v68 = v68;
      *((_QWORD *)v68 + 2) = v68;
    }
    else
    {
      for ( i = *v29; !*((_BYTE *)i + 25); i = (__int64 *)*i )
        v29 = (__int64 **)i;
      *(_QWORD *)v68 = v29;
      for ( j = *((_QWORD *)v68 + 1); !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
        ;
      *((_QWORD *)v68 + 2) = j;
    }
    v32 = CExec::EnvironmentMapToBlock(&UserData);
    std::wstring::operator=(&v103, v32);
    std::wstring::~wstring(&UserData);
  }
  v33 = v15 && (!*(_BYTE *)(a2 + 181) || !*(_BYTE *)(a2 + 180));
  *(__m128i *)v80 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v68 = 0;
  lpValue = 0;
  if ( v33 )
  {
    LOWORD(hToken[0]) = v20;
    WORD1(hToken[0]) = v70[0];
    lpValue = 0;
    PseudoConsoleAsUser = CreatePseudoConsoleAsUser(v73, LODWORD(hToken[0]), v16, v17);
    if ( PseudoConsoleAsUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)(unsigned int)PseudoConsoleAsUser,
        0);
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v35 = GetLastError();
      CloseHandle((HANDLE)v16);
      SetLastError(v35);
    }
    v72 = (HANDLE)-1LL;
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v36 = GetLastError();
      CloseHandle((HANDLE)v17);
      SetLastError(v36);
    }
    v37 = -1;
    v74 = -1;
  }
  else
  {
    Console = (HANDLE *)CreateConsole(hToken, v25, v26);
    if ( v80 != Console )
    {
      v80[0] = *Console;
      *Console = (HANDLE)-1LL;
    }
    v39 = Console + 1;
    if ( &v80[1] != v39 )
    {
      v80[1] = *v39;
      *v39 = (HANDLE)-1LL;
    }
    if ( (unsigned __int64)hToken[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hToken[1]);
    if ( (unsigned __int64)hToken[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hToken[0]);
    v40 = operator new(0x180u);
    hToken[0] = v40;
    memset_0(v40, 0, 0x180u);
    v14 = (ConsoleToPipeRedirector *)ConsoleToPipeRedirector::ConsoleToPipeRedirector(v40, v70[0], v20, v70[0], v20);
    v68 = v14;
    v37 = v74;
  }
  *(_QWORD *)&StartupInfo.cb = 112;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  v93 = 0;
  CExec::MakeAttributeList(&lpAttributeList);
  v41 = lpAttributeList;
  v93 = lpAttributeList;
  Value[0] = TargetHandle;
  Value[1] = v96;
  Value[2] = hObject;
  StartupInfo.dwFlags |= 0x100u;
  if ( !v67 )
  {
    StartupInfo.hStdInput = TargetHandle;
    StartupInfo.hStdOutput = v96;
    StartupInfo.hStdError = hObject;
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 0x18u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v42);
    v41 = lpAttributeList;
  }
  v43 = (char *)v80[1];
  if ( v33 )
  {
    v89 = 0;
    if ( !UpdateProcThreadAttribute(v41, 0, 0x20016u, lpValue, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v44);
  }
  else
  {
    v89 = v80[1];
    if ( !UpdateProcThreadAttribute(v41, 0, 0x2000Au, &v89, 8u, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v49);
  }
  if ( v90 != -1 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Du, &v90, 8u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v45);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&v106, 0, 0x150u);
  v107 = 0;
  v108 = 0;
  v112 = 0;
  v109 = 0;
  v110 = "CreateProcessAsUserW";
  v111 = 0;
  v113 = 0;
  v115 = 0;
  v116 = 0;
  memset_0(v114, 0, sizeof(v114));
  v117 = 1;
  v118 = 0;
  v119 = &v107;
  v120 = 0;
  v121 = 0;
  v122 = &v106;
  v123 = 0;
  v124 = 0;
  v125 = &v109;
  v126 = 0;
  v106 = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StartActivity((CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *)&v106);
  lpCurrentDirectory = (const WCHAR *)(a2 + 120);
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *(_QWORD *)(a2 + 144) <= 7u )
      v48 = (const WCHAR *)(a2 + 120);
    else
      v48 = *(const WCHAR **)lpCurrentDirectory;
    Vml::CreateDirectoryW(v48, v46);
  }
  UserData = 0;
  v149.Ptr = 0;
  *(_QWORD *)&v149.Size = 7;
  LOWORD(UserData.Ptr) = 0;
  v150 = 0;
  v151.Ptr = 0;
  *(_QWORD *)&v151.Size = 7;
  LOWORD(v150.Ptr) = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    p_UserData = (const WCHAR *)a2;
  else
    p_UserData = *(const WCHAR **)a2;
  Ptr = (WCHAR *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) > 7u )
  {
    Ptr = *(WCHAR **)Ptr;
    v76 = Ptr;
  }
  if ( !*p_UserData )
  {
    *(_OWORD *)hToken = 0;
    v99 = 0;
    v100 = 0;
    std::wstring::_Construct<1,unsigned short const *>(hToken, L"PATH", 4);
    lpCurrentDirectory = (const WCHAR *)(a2 + 120);
    std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
      &v102,
      hToken);
    ApplicationName = GetApplicationName(Src);
    std::wstring::operator=(&UserData, ApplicationName);
    std::wstring::operator=(&v150, ApplicationName + 32);
    std::wstring::~wstring(v88);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(hToken);
    p_UserData = (const WCHAR *)&UserData;
    if ( *(_QWORD *)&v149.Size > 7u )
      p_UserData = (const WCHAR *)UserData.Ptr;
    if ( v151.Ptr )
    {
      Ptr = (WCHAR *)&v150;
      if ( *(_QWORD *)&v151.Size > 7u )
        Ptr = (WCHAR *)v150.Ptr;
    }
    else
    {
      Ptr = v76;
    }
  }
  if ( *(_QWORD *)(a2 + 136) )
  {
    if ( *((_QWORD *)lpCurrentDirectory + 3) > 7u )
      lpCurrentDirectory = *(const WCHAR **)lpCurrentDirectory;
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( v104 )
  {
    lpEnvironment = &v103;
    if ( v105 > 7 )
      lpEnvironment = (__int128 *)v103;
  }
  else
  {
    lpEnvironment = (__int128 *)v101;
  }
  v54 = v73;
  if ( !CreateProcessAsUserW(
          v73,
          p_UserData,
          Ptr,
          0,
          0,
          1,
          0x80400u,
          lpEnvironment,
          lpCurrentDirectory,
          &StartupInfo,
          &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F7,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v55);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v106);
  std::wstring::~wstring(&v150);
  std::wstring::~wstring(&UserData);
  v106 = &CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v106);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v106);
  hProcess = ProcessInformation.hProcess;
  v73 = ProcessInformation.hProcess;
  ProcessInformation.hProcess = 0;
  *lpTargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v58 = GetCurrentProcess();
  if ( !DuplicateHandle(v58, hProcess, CurrentProcess, lpTargetHandle, 0x101041u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v59);
  if ( v14 )
  {
    CspReadNextConsoleIo(*(_QWORD *)v14);
    ConsoleToPipeRedirector::StartRead(v14);
  }
  v60 = operator new(0x40u);
  *(_OWORD *)v60 = 0;
  v60[2] = 1;
  v60[3] = 1;
  *(_QWORD *)v60 = &std::_Ref_count_obj2<CExec::ProcessTracker>::`vftable';
  dwProcessId = ProcessInformation.dwProcessId;
  *((_QWORD *)v60 + 2) = hProcess;
  v73 = 0;
  v68 = 0;
  *((_QWORD *)v60 + 3) = v14;
  *((_QWORD *)v60 + 4) = lpValue;
  lpValue = 0;
  *((_QWORD *)v60 + 5) = v54;
  v78 = 0;
  v60[12] = dwProcessId;
  *((_QWORD *)v60 + 7) = 0;
  v76 = (WCHAR *)(v60 + 4);
  v77 = v60;
  CExec::TrackProcess(ProcessInformation.dwProcessId, &v76);
  v62 = v77;
  if ( v77 )
  {
    if ( _InterlockedExchangeAdd(v77 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
      if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
    }
  }
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v127);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v63);
  v64 = lpAttributeList;
  lpAttributeList = 0;
  if ( v64 )
    LocalFree(v64);
  if ( lpValue )
    ClosePseudoConsole();
  if ( (unsigned __int64)(v43 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v43);
  if ( (unsigned __int64)v80[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v80[0]);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    &v102,
    &v102);
  std::wstring::~wstring(&v103);
  if ( v101 )
    DestroyEnvBlock();
  RevertToSelf();
  if ( (unsigned __int64)(v37 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v37);
  if ( (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v72);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)v96 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v96);
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TargetHandle);
  v127 = &CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable';
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v127);
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(&v127);
  return lpTargetHandle;
}

```

## disassembly

```asm
0x1400e0b10  push    rbp
0x1400e0b12  push    rbx
0x1400e0b13  push    rsi
0x1400e0b14  push    rdi
0x1400e0b15  push    r12
0x1400e0b17  push    r13
0x1400e0b19  push    r14
0x1400e0b1b  push    r15
0x1400e0b1d  lea     rbp, [rsp-468h]
0x1400e0b25  sub     rsp, 568h
0x1400e0b2c  mov     rax, cs:__security_cookie
0x1400e0b33  xor     rax, rsp
0x1400e0b36  mov     [rbp+4A0h+var_48], rax
0x1400e0b3d  mov     r12, r9
0x1400e0b40  mov     r15, r8
0x1400e0b43  mov     rsi, rdx
0x1400e0b46  mov     [rbp+4A0h+lpTargetHandle], rcx
0x1400e0b4a  mov     [rbp+4A0h+var_4B8], rcx
0x1400e0b4e  mov     r13, [rbp+4A0h+hSourceHandle]
0x1400e0b55  mov     rax, [rbp+4A0h+arg_28]
0x1400e0b5c  mov     [rsp+5A0h+var_538], rax
0x1400e0b61  mov     rax, [rbp+4A0h+arg_30]
0x1400e0b68  mov     [rbp+4A0h+var_458], rax
0x1400e0b6c  xor     ebx, ebx
0x1400e0b6e  mov     [rsp+5A0h+var_53C], ebx
0x1400e0b72  xor     edx, edx; Val
0x1400e0b74  mov     r8d, 150h; Size
0x1400e0b7a  lea     rcx, [rbp+4A0h+var_1F0]; void *
0x1400e0b81  call    memset_0
0x1400e0b86  mov     [rbp+4A0h+var_1E8], ebx
0x1400e0b8c  mov     [rbp+4A0h+var_1E4], bl
0x1400e0b92  mov     [rbp+4A0h+var_1A8], bl
0x1400e0b98  mov     [rbp+4A0h+var_1C0], ebx
0x1400e0b9e  lea     rax, aExecuteprocess_0; "ExecuteProcess"
0x1400e0ba5  mov     [rbp+4A0h+var_1B8], rax
0x1400e0bac  mov     [rbp+4A0h+var_1B0], rbx
0x1400e0bb3  mov     [rbp+4A0h+var_1A0], ebx
0x1400e0bb9  mov     [rbp+4A0h+var_100], rbx
0x1400e0bc0  mov     [rbp+4A0h+var_F8], rbx
0x1400e0bc7  xor     edx, edx; Val
0x1400e0bc9  mov     r8d, 98h; Size
0x1400e0bcf  lea     rcx, [rbp+4A0h+var_198]; void *
0x1400e0bd6  call    memset_0
0x1400e0bdb  mov     [rbp+4A0h+var_F0], 1
0x1400e0be5  xor     eax, eax
0x1400e0be7  mov     [rbp+4A0h+var_E8], rax
0x1400e0bee  lea     rax, [rbp+4A0h+var_1E8]
0x1400e0bf5  mov     [rbp+4A0h+var_E0], rax
0x1400e0bfc  mov     [rbp+4A0h+var_D8], rbx
0x1400e0c03  mov     [rbp+4A0h+var_D0], rbx
0x1400e0c0a  lea     rax, [rbp+4A0h+var_1F0]
0x1400e0c11  mov     [rbp+4A0h+var_C8], rax
0x1400e0c18  mov     [rbp+4A0h+var_C0], rbx
0x1400e0c1f  mov     [rbp+4A0h+var_B8], ebx
0x1400e0c25  lea     rax, [rbp+4A0h+var_1C0]
0x1400e0c2c  mov     [rbp+4A0h+var_B0], rax
0x1400e0c33  mov     [rbp+4A0h+var_A8], bl
0x1400e0c39  lea     rax, ??_7ExecuteProcess@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess::`vftable'
0x1400e0c40  mov     [rbp+4A0h+var_1F0], rax
0x1400e0c47  lea     rcx, [rbp+4A0h+var_1F0]; this
0x1400e0c4e  call    ?StartActivity@ExecuteProcess@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity(void)
0x1400e0c53  nop
0x1400e0c54  lea     rax, aNA; "<n/a>"
0x1400e0c5b  lea     rdi, aPipe_0; "pipe"
0x1400e0c62  mov     r8, rdi
0x1400e0c65  test    r13, r13
0x1400e0c68  cmovz   r8, rax; unsigned __int16 *
0x1400e0c6c  mov     r14, rdi
0x1400e0c6f  test    r12, r12
0x1400e0c72  cmovz   r14, rax
0x1400e0c76  test    r15, r15
0x1400e0c79  cmovz   rdi, rax
0x1400e0c7d  lea     rbx, [rsi+20h]
0x1400e0c81  mov     qword ptr [rbp+4A0h+var_4F8], rbx
0x1400e0c85  cmp     qword ptr [rbx+18h], 7
0x1400e0c8a  jbe     short loc_1400E0C8F
0x1400e0c8c  mov     rbx, [rbx]
0x1400e0c8f  xor     edx, edx
0x1400e0c91  cmp     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, rdx; _VML_ETW_TRACE * g_VmlEtwTrace
0x1400e0c98  jz      short loc_1400E0D10
0x1400e0c9a  lea     rdx, [rbp+4A0h+var_4BC]; unsigned int *
0x1400e0c9e  lea     rcx, [rbp+4A0h+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x1400e0ca5  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400e0caa  mov     r8, r14; unsigned __int16 *
0x1400e0cad  lea     rdx, [rbp+4A0h+var_4C0]; unsigned int *
0x1400e0cb1  lea     rcx, [rbp+4A0h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x1400e0cb8  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400e0cbd  mov     r8, rdi; unsigned __int16 *
0x1400e0cc0  lea     rdx, [rbp+4A0h+var_4C8+4]; unsigned int *
0x1400e0cc4  lea     rcx, [rbp+4A0h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x1400e0ccb  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400e0cd0  mov     r8, rbx; unsigned __int16 *
0x1400e0cd3  lea     rdx, [rbp+4A0h+var_4C8]; unsigned int *
0x1400e0cd7  lea     rcx, [rbp+4A0h+UserData]; struct _EVENT_DATA_DESCRIPTOR *
0x1400e0cde  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400e0ce3  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x1400e0cea  xor     r14d, r14d
0x1400e0ced  test    rcx, rcx
0x1400e0cf0  jz      short loc_1400E0D13
0x1400e0cf2  lea     r9, [rbp+4A0h+UserData]; UserData
0x1400e0cf9  lea     r8d, [r14+4]; UserDataCount
0x1400e0cfd  lea     rdx, MSCEXEC_CREATE_PROCESS; EventDescriptor
0x1400e0d04  mov     rcx, [rcx+10h]; RegHandle
0x1400e0d08  call    cs:__imp_EventWrite
0x1400e0d0e  jmp     short loc_1400E0D13
0x1400e0d10  xor     r14d, r14d
0x1400e0d13  mov     bl, [rsi+0A9h]
0x1400e0d19  mov     [rsp+5A0h+var_540], bl
0x1400e0d1d  mov     [rbp+4A0h+TargetHandle], r14
0x1400e0d24  mov     r9b, bl
0x1400e0d27  mov     r8b, 1
0x1400e0d2a  mov     rdx, r15; hSourceHandle
0x1400e0d2d  lea     rcx, [rbp+4A0h+TargetHandle]; lpTargetHandle
0x1400e0d34  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x1400e0d39  nop
0x1400e0d3a  mov     [rbp+4A0h+var_3B0], r14
0x1400e0d41  mov     r9b, bl
0x1400e0d44  xor     r8d, r8d
0x1400e0d47  mov     rdx, r12; hSourceHandle
0x1400e0d4a  lea     rcx, [rbp+4A0h+var_3B0]; lpTargetHandle
0x1400e0d51  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x1400e0d56  nop
0x1400e0d57  mov     [rbp+4A0h+hObject], r14
0x1400e0d5e  mov     r9b, bl
0x1400e0d61  xor     r8d, r8d
0x1400e0d64  mov     rdx, r13; hSourceHandle
0x1400e0d67  lea     rcx, [rbp+4A0h+hObject]; lpTargetHandle
0x1400e0d6e  call    ?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z; CExec::ConnectStdDevicePipe(void *,bool,bool)
0x1400e0d73  nop
0x1400e0d74  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400e0d78  mov     [rbp+4A0h+var_4B0], r12
0x1400e0d7c  mov     [rbp+4A0h+var_4A8], r12
0x1400e0d80  mov     qword ptr [rbp+4A0h+var_4C8], r12
0x1400e0d84  mov     r15, r12
0x1400e0d87  mov     [rbp+4A0h+var_518], r12
0x1400e0d8b  mov     r13, r12
0x1400e0d8e  mov     [rbp+4A0h+var_508], r12
0x1400e0d92  test    bl, bl
0x1400e0d94  jz      short loc_1400E0DEF
0x1400e0d96  mov     r15, [rbp+4A0h+TargetHandle]
0x1400e0d9d  mov     [rbp+4A0h+var_518], r15
0x1400e0da1  mov     [rbp+4A0h+TargetHandle], r12
0x1400e0da8  mov     r13, [rbp+4A0h+var_3B0]
0x1400e0daf  mov     [rbp+4A0h+var_508], r13
0x1400e0db3  mov     [rbp+4A0h+var_3B0], r12
0x1400e0dba  mov     rdi, [rbp+4A0h+hObject]
0x1400e0dc1  lea     rax, [rdi-1]
0x1400e0dc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e0dc9  ja      short loc_1400E0DE8
0x1400e0dcb  call    cs:__imp_GetLastError
0x1400e0dd1  mov     ebx, eax
0x1400e0dd3  mov     rcx, rdi; hObject
0x1400e0dd6  call    cs:__imp_CloseHandle
0x1400e0ddc  mov     ecx, ebx; dwErrCode
0x1400e0dde  call    cs:__imp_SetLastError
0x1400e0de4  mov     bl, [rsp+5A0h+var_540]
0x1400e0de8  mov     [rbp+4A0h+hObject], r12
0x1400e0def  movzx   eax, word ptr [rsi+0AEh]
0x1400e0df6  test    ax, ax
0x1400e0df9  jnz     short loc_1400E0E05
0x1400e0dfb  mov     dword ptr [rsp+5A0h+var_528], 19h
0x1400e0e03  jmp     short loc_1400E0E0A
0x1400e0e05  mov     [rsp+5A0h+var_528], ax
0x1400e0e0a  movzx   eax, word ptr [rsi+0B0h]
0x1400e0e11  test    ax, ax
0x1400e0e14  jnz     short loc_1400E0E1E
0x1400e0e16  mov     r12d, 50h ; 'P'
0x1400e0e1c  jmp     short loc_1400E0E22
0x1400e0e1e  movzx   r12d, ax
0x1400e0e22  mov     [rbp+4A0h+var_4E8], r14
0x1400e0e26  mov     [rbp+4A0h+hToken], r14
0x1400e0e2d  mov     rdx, rsi
0x1400e0e30  lea     rcx, [rbp+4A0h+hToken]
0x1400e0e37  call    ?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z; CExec::GetProcessToken(Schema::Process::ProcessParameters const &)
0x1400e0e3c  nop
0x1400e0e3d  xor     edx, edx; Val
0x1400e0e3f  mov     r8d, 150h; Size
0x1400e0e45  lea     rcx, [rbp+4A0h+var_340]; void *
0x1400e0e4c  call    memset_0
0x1400e0e51  mov     [rbp+4A0h+var_338], r14d
0x1400e0e58  mov     [rbp+4A0h+var_334], r14b
0x1400e0e5f  mov     [rbp+4A0h+var_2F8], r14b
0x1400e0e66  mov     [rbp+4A0h+var_310], r14d
0x1400e0e6d  lea     rax, aExecuteprocess; "ExecuteProcess_LoadProfile"
0x1400e0e74  mov     [rbp+4A0h+var_308], rax
0x1400e0e7b  mov     [rbp+4A0h+var_300], r14
0x1400e0e82  mov     [rbp+4A0h+var_2F0], r14d
0x1400e0e89  mov     [rbp+4A0h+var_250], r14
0x1400e0e90  mov     [rbp+4A0h+var_248], r14
0x1400e0e97  xor     edx, edx; Val
0x1400e0e99  mov     r8d, 98h; Size
0x1400e0e9f  lea     rcx, [rbp+4A0h+var_2E8]; void *
0x1400e0ea6  call    memset_0
0x1400e0eab  mov     [rbp+4A0h+var_240], 1
0x1400e0eb5  xor     eax, eax
0x1400e0eb7  mov     [rbp+4A0h+var_238], rax
0x1400e0ebe  lea     rax, [rbp+4A0h+var_338]
0x1400e0ec5  mov     [rbp+4A0h+var_230], rax
0x1400e0ecc  mov     [rbp+4A0h+var_228], r14
0x1400e0ed3  mov     [rbp+4A0h+var_220], r14
0x1400e0eda  lea     rax, [rbp+4A0h+var_340]
0x1400e0ee1  mov     [rbp+4A0h+var_218], rax
0x1400e0ee8  mov     [rbp+4A0h+var_210], r14
0x1400e0eef  mov     [rbp+4A0h+var_208], r14d
0x1400e0ef6  lea     rax, [rbp+4A0h+var_310]
0x1400e0efd  mov     [rbp+4A0h+var_200], rax
0x1400e0f04  mov     [rbp+4A0h+var_1F8], r14b
0x1400e0f0b  lea     rax, ??_7ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable'
0x1400e0f12  mov     [rbp+4A0h+var_340], rax
0x1400e0f19  lea     rcx, [rbp+4A0h+var_340]; this
0x1400e0f20  call    ?StartActivity@ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@QEAAXXZ; CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity(void)
0x1400e0f25  nop
0x1400e0f26  xor     edx, edx
0x1400e0f28  mov     rcx, [rbp+4A0h+hToken]
0x1400e0f2f  call    cs:__imp_LoadProfileBasic
0x1400e0f35  mov     rcx, [rbp+4A8h]; this
0x1400e0f3c  test    eax, eax
0x1400e0f3e  js      loc_1400E1A6D
0x1400e0f44  mov     rdi, [rbp+4A0h+hToken]
0x1400e0f4b  mov     [rbp+4A0h+var_510], rdi
0x1400e0f4f  mov     [rbp+4A0h+hToken], r14
0x1400e0f56  mov     [rbp+4A0h+var_4E8], rdi
0x1400e0f5a  lea     rcx, [rbp+4A0h+var_340]
0x1400e0f61  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400e0f66  nop
0x1400e0f67  lea     rax, ??_7ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::`vftable'
0x1400e0f6e  mov     [rbp+4A0h+var_340], rax
0x1400e0f75  lea     rcx, [rbp+4A0h+var_340]
0x1400e0f7c  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400e0f81  lea     rcx, [rbp+4A0h+var_340]
0x1400e0f88  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400e0f8d  nop
0x1400e0f8e  mov     rcx, [rbp+4A0h+hToken]; hObject
0x1400e0f95  lea     rax, [rcx-1]
0x1400e0f99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e0f9d  ja      short loc_1400E0FA5
0x1400e0f9f  call    cs:__imp_CloseHandle
0x1400e0fa5  mov     rcx, rdi; hToken
0x1400e0fa8  call    cs:__imp_ImpersonateLoggedOnUser
0x1400e0fae  mov     rcx, [rbp+4A8h]; this
0x1400e0fb5  test    eax, eax
0x1400e0fb7  jz      loc_1400E1A82
0x1400e0fbd  mov     [rbp+4A0h+var_4FF], 1
0x1400e0fc1  mov     [rbp+4A0h+var_380], r14
0x1400e0fc8  xor     r8d, r8d
0x1400e0fcb  mov     rdx, rdi
0x1400e0fce  lea     rcx, [rbp+4A0h+var_380]
0x1400e0fd5  call    cs:__imp_CreateEnvBlock
0x1400e0fdb  mov     rcx, [rbp+4A8h]; this
0x1400e0fe2  test    eax, eax
0x1400e0fe4  js      loc_1400E1A94
0x1400e0fea  xorps   xmm0, xmm0
0x1400e0fed  movups  [rbp+4A0h+var_368], xmm0
0x1400e0ff4  mov     [rbp+4A0h+var_358], r14
0x1400e0ffb  mov     [rbp+4A0h+var_350], 7
0x1400e1006  mov     word ptr [rbp+4A0h+var_368], r14w
0x1400e100e  movups  [rbp+4A0h+var_378], xmm0
0x1400e1015  mov     rdx, [rbp+4A0h+var_380]
0x1400e101c  lea     rcx, [rbp+4A0h+var_378]
0x1400e1023  call    ?EnvironmentBlockToMap@CExec@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBG@Z; CExec::EnvironmentBlockToMap(ushort const *)
0x1400e1028  nop
0x1400e1029  mov     r8, [rsp+5A0h+var_538]
0x1400e102e  cmp     [rsi+0A0h], r14
0x1400e1035  jnz     short loc_1400E1041
0x1400e1037  cmp     [r8+10h], r14
0x1400e103b  jz      loc_1400E1147
0x1400e1041  lea     rdx, [rsi+98h]
0x1400e1048  lea     rcx, [rbp+4A0h+var_378]
0x1400e104f  call    ?UpdateEnvironmentMap@CExec@@YAXAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CExec::UpdateEnvironmentMap(std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>> &,std::map<std::wstring,std::wstring> const &,std::wstring const &)
0x1400e1054  mov     [rsp+5A0h+var_538], r14
0x1400e1059  mov     [rsp+5A0h+var_530], r14
0x1400e105e  lea     rax, [rsp+5A0h+var_538]
0x1400e1063  mov     [rbp+4A0h+hToken], rax
0x1400e106a  lea     rax, [rsp+5A0h+var_538]
0x1400e106f  mov     [rbp+4A0h+hToken+8], rax
0x1400e1076  mov     ecx, 60h ; '`'; Size
0x1400e107b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400e1080  mov     [rax], rax
0x1400e1083  mov     [rax+8], rax
0x1400e1087  mov     [rax+10h], rax
0x1400e108b  mov     word ptr [rax+18h], 101h
0x1400e1091  mov     [rsp+5A0h+var_538], rax
0x1400e1096  mov     r8, rax
0x1400e1099  mov     rdx, qword ptr [rbp+4A0h+var_378]
0x1400e10a0  mov     rdx, [rdx+8]
0x1400e10a4  lea     rcx, [rsp+5A0h+var_538]
0x1400e10a9  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1400e10ae  mov     rcx, rax
0x1400e10b1  mov     rax, [rsp+5A0h+var_538]
0x1400e10b6  mov     [rax+8], rcx
0x1400e10ba  mov     rax, qword ptr [rbp+4A0h+var_378+8]
0x1400e10c1  mov     [rsp+5A0h+var_530], rax
0x1400e10c6  mov     r8, [rsp+5A0h+var_538]
0x1400e10cb  mov     rdx, [r8+8]
0x1400e10cf  cmp     [rdx+19h], r14b
0x1400e10d3  jnz     short loc_1400E110F
0x1400e10d5  mov     rcx, [rdx]
0x1400e10d8  cmp     [rcx+19h], r14b
0x1400e10dc  jnz     short loc_1400E10ED
0x1400e10de  mov     rdx, rcx
  ... truncated ...
```
