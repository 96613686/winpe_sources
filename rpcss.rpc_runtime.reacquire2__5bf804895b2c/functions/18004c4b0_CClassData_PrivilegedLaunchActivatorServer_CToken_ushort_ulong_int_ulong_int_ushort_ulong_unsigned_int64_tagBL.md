# CClassData::PrivilegedLaunchActivatorServer(CToken *,ushort *,ulong,int,ulong,int,ushort *,ulong,unsigned __int64,tagBLOB *,void * *,void * *,ulong *,int *)

- ea: `0x18004c4b0`
- end: `0x18004daee`
- name: `?PrivilegedLaunchActivatorServer@CClassData@@QEAAJPEAVCToken@@PEAGKHKH1K_KPEAUtagBLOB@@PEAPEAX4PEAKPEAH@Z`
- size: `5694`
- prototype: `__int64 __usercall@<rax>(CClassData *__hidden this@<rcx>, struct CToken *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, int, unsigned int, int, unsigned __int16 *, unsigned int, unsigned __int64, struct tagBLOB *, void **, void **, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `68`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a0540`
- `0x1800f58e0`

## callees

- `0x1800065a4`
- `0x180008b74`
- `0x180008c20`
- `0x18000902c`
- `0x18000a5bc`
- `0x18000b9e0`
- `0x18000c3f8`
- `0x18000c6fc`
- `0x18000ce7c`
- `0x18000fb8c`
- `0x180010b00`
- `0x180010e04`
- `0x18001efe0`
- `0x1800210f8`
- `0x180022ddc`
- `0x180023da8`
- `0x180023dc4`
- `0x180024590`
- `0x180025088`
- `0x180025b54`
- `0x18002ea40`
- `0x18002f3e0`
- `0x18002faa8`
- `0x1800375e0`
- `0x180039a7c`
- `0x18004c144`
- `0x18004c160`
- `0x18004c1ac`
- `0x18004c440`
- `0x18004c4b0`
- `0x18004daf4`
- `0x18004dbf4`
- `0x18004dd1c`
- `0x18004e554`
- `0x18005112c`
- `0x1800516c0`
- `0x180051cac`
- `0x18006d3ec`
- `0x18006fcf4`
- `0x180073ab8`
- `0x18007b088`
- `0x180084fcc`
- `0x1800861e8`
- `0x18009007c`
- `0x180093da8`
- `0x180093f20`
- `0x180095c0c`
- `0x18009e160`
- `0x1800a276c`
- `0x1800a3e30`

## import_xrefs

- `ntdll!NtResumeThread` at `0x18004d789`
- `ntdll!NtResumeThread` at `0x18004d789`
- `ntdll!NtTerminateProcess` at `0x18004c76e`
- `ntdll!NtTerminateProcess` at `0x18004c76e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d68d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ccf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d9ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ccf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d37c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d37c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d660`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d660`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cdc8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ce2d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cec9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cf07`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cdc8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004ce2d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cec9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18004cf07`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18004d5d0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18004d5d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004d40e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004d40e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004d63b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004d63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da14`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d2ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d303`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d318`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d32d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d342`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d395`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d2ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d303`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d318`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d32d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d342`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004d395`
- `profapi!__imp_CreateEnvBlock` at `0x18004cf68`
- `profapi!__imp_CreateEnvBlock` at `0x18004cf68`
- `profapi!__imp_DestroyEnvBlock` at `0x18004d283`
- `profapi!__imp_DestroyEnvBlock` at `0x18004d283`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18004d123`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18004d123`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18004d767`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18004d767`

## string_xrefs

- `0x18004c703`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004c830`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004cae7`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004cde6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004ce50`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004cf89`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d0a2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d1b6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d26b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d5ee`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d6a0`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d6df`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d7a4`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d869`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004d91f`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18004cddf`: `Failed to add attribute (DCOMLaunch)`
- `0x18004ce42`: `Failed to add attribute (DCOMLaunch)`
- `0x18004d5e7`: `Failed CreateProcessAsUser`
- `0x18004cf17`: `Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)`
- `0x18004d85a`: `Failed PostCreateProcessUWPActivation`
- `0x18004d67f`: `rpcss.dll`

## pseudocode

```c
__int64 __fastcall CClassData::PrivilegedLaunchActivatorServer(
        CClassData *this,
        struct CToken *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        int a5,
        char a6,
        int a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned __int64 a10,
        struct tagBLOB *a11,
        void **a12,
        void **a13,
        unsigned int *a14,
        int *a15)
{
  char v15; // r13
  void **v16; // rdi
  void **v18; // r14
  unsigned int *v19; // r15
  int *v20; // rbx
  struct wil::CallContextInfo *v21; // r8
  bool v22; // r9
  int LastErrorMsg; // ebx
  __int64 v24; // rdx
  __int64 v25; // r9
  CClassData *v26; // rcx
  int IsActivateAsIUAllowed; // eax
  __int64 v28; // rax
  int LaunchCommandLine; // eax
  __int64 v30; // rdx
  WCHAR *v32; // rax
  unsigned __int8 v33; // r12
  DWORD v34; // r15d
  int ProcessExtensions; // edi
  unsigned int SessionId; // eax
  unsigned int v37; // eax
  const unsigned __int16 *v38; // rdx
  unsigned int v39; // eax
  const unsigned __int16 *v40; // rdx
  int PackageNameFromToken; // eax
  __int64 v42; // rdx
  __int64 v43; // r9
  __int64 v44; // r14
  __int64 v45; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v46; // rdx
  __int64 *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  void *v50; // rbx
  int v51; // eax
  int v52; // ecx
  CSCMProfileCache *v53; // rcx
  __int64 v54; // rdx
  const char *v55; // r9
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r9
  unsigned __int16 *v59; // r14
  unsigned __int16 *v60; // r12
  const unsigned __int16 *v61; // r8
  int DebuggerInfo; // eax
  bool v63; // r12
  unsigned __int64 v64; // rcx
  int *v65; // r13
  __int64 v66; // rdx
  void *v67; // rdx
  LPPROC_THREAD_ATTRIBUTE_LIST v68; // rcx
  unsigned __int16 *v69; // rax
  void *v70; // r14
  __int64 v71; // r8
  __int64 v72; // r9
  void (__fastcall *v73)(CClassData *, HSTRING *); // rbx
  void **v74; // rax
  void **v75; // rax
  DWORD LastError; // eax
  DWORD v77; // eax
  int ActivationActivityIfNeeded; // eax
  struct ActivationActivity *v79; // rcx
  int v80; // edi
  int v81; // eax
  __int64 v82; // rdx
  NTSTATUS v83; // eax
  HSTRING v84; // r13
  int v85; // r12d
  CClassData *v86; // rcx
  const unsigned __int16 *v87; // r15
  const unsigned __int16 *v88; // rax
  __int64 v89; // rdi
  const unsigned __int16 *v90; // rbx
  HLOCAL v91; // rsi
  unsigned int v92; // r14d
  unsigned int v93; // eax
  CClassData *v94; // rcx
  int v95; // esi
  unsigned int v96; // r14d
  unsigned int v97; // eax
  CSCMProfileCache *v98; // rcx
  CSCMProfileCache *v99; // rcx
  HANDLE hProcess; // rax
  DWORD dwProcessId; // edx
  HANDLE hThread; // rcx
  HANDLE v103; // rax
  struct _PROCESS_INFORMATION *v104; // rdx
  const char *cbSize; // [rsp+20h] [rbp-E0h]
  const char *lpPreviousValue; // [rsp+28h] [rbp-D8h]
  bool v108; // [rsp+70h] [rbp-90h] BYREF
  bool v109[7]; // [rsp+71h] [rbp-8Fh] BYREF
  CSCMProfileCache *p_Buf2; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION *p_ProcessInformation; // [rsp+80h] [rbp-80h]
  NTSTATUS *v112; // [rsp+88h] [rbp-78h]
  char v113; // [rsp+90h] [rbp-70h]
  char v114; // [rsp+98h] [rbp-68h]
  char v115; // [rsp+99h] [rbp-67h] BYREF
  bool v116; // [rsp+9Ah] [rbp-66h] BYREF
  bool v117; // [rsp+9Bh] [rbp-65h]
  struct _GUID v118; // [rsp+A0h] [rbp-60h] BYREF
  CToken *v119; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v122; // [rsp+C8h] [rbp-38h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+D0h] [rbp-30h] BYREF
  PVOID lpValue; // [rsp+D8h] [rbp-28h] BYREF
  void *v125; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v126; // [rsp+E8h] [rbp-18h] BYREF
  HLOCAL v127; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+F8h] [rbp-8h] BYREF
  struct ActivationActivity *v129; // [rsp+100h] [rbp+0h] BYREF
  HLOCAL v130; // [rsp+108h] [rbp+8h] BYREF
  HANDLE v131; // [rsp+110h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+118h] [rbp+18h] BYREF
  HLOCAL v133; // [rsp+120h] [rbp+20h] BYREF
  int v134; // [rsp+128h] [rbp+28h]
  unsigned __int16 *lpEnvironment; // [rsp+130h] [rbp+30h] BYREF
  HLOCAL v136; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v137; // [rsp+140h] [rbp+40h]
  int v138; // [rsp+144h] [rbp+44h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+148h] [rbp+48h] BYREF
  int v140; // [rsp+160h] [rbp+60h] BYREF
  int v141; // [rsp+164h] [rbp+64h] BYREF
  __int64 v142; // [rsp+168h] [rbp+68h] BYREF
  __int64 (__fastcall **v143)(); // [rsp+170h] [rbp+70h] BYREF
  _BYTE v144[48]; // [rsp+178h] [rbp+78h] BYREF
  int *v145; // [rsp+1A8h] [rbp+A8h]
  int *v146; // [rsp+1B0h] [rbp+B0h]
  int v147; // [rsp+1B8h] [rbp+B8h]
  int Value; // [rsp+1BCh] [rbp+BCh] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v149; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 *v150; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int16 *v151; // [rsp+1D0h] [rbp+D0h]
  unsigned __int16 *v152; // [rsp+1D8h] [rbp+D8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST *p_lpAttributeList; // [rsp+1E0h] [rbp+E0h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v154; // [rsp+1E8h] [rbp+E8h] BYREF
  char v155; // [rsp+1F0h] [rbp+F0h]
  struct tagBLOB *v156; // [rsp+1F8h] [rbp+F8h]
  unsigned __int16 *v157; // [rsp+200h] [rbp+100h]
  CClassData *v158; // [rsp+208h] [rbp+108h]
  void **v159; // [rsp+210h] [rbp+110h]
  void **v160; // [rsp+218h] [rbp+118h]
  unsigned int *v161; // [rsp+220h] [rbp+120h]
  _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v163[8]; // [rsp+240h] [rbp+140h] BYREF
  char v164; // [rsp+280h] [rbp+180h]
  _QWORD v165[4]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v166; // [rsp+2B0h] [rbp+1B0h]
  HSTRING *p_string; // [rsp+2B8h] [rbp+1B8h]
  unsigned int *v168; // [rsp+2C0h] [rbp+1C0h]
  CToken **v169; // [rsp+2C8h] [rbp+1C8h]
  LPVOID *p_lpMem; // [rsp+2D0h] [rbp+1D0h]
  struct _STARTUPINFOW StartupInfo; // [rsp+2E0h] [rbp+1E0h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v172; // [rsp+348h] [rbp+248h]
  _BYTE v173[8]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v174[88]; // [rsp+358h] [rbp+258h] BYREF
  GUID Buf2; // [rsp+3B0h] [rbp+2B0h] BYREF
  _QWORD v176[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v177; // [rsp+3D0h] [rbp+2D0h]
  __int128 v178; // [rsp+3E0h] [rbp+2E0h]
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v15 = 0;
  v16 = a12;
  v18 = a13;
  v19 = a14;
  v20 = a15;
  v151 = a3;
  v158 = this;
  v119 = a2;
  v137 = a4;
  v156 = a11;
  v159 = a12;
  v160 = a13;
  v161 = a14;
  v146 = a15;
  lpMem = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  lpAttributeList = 0;
  v157 = 0;
  v152 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  lpValue = 0;
  v163[0] = &v115;
  v163[1] = &lpEnvironment;
  v163[2] = &hObject;
  v163[3] = &v108;
  v163[4] = &v142;
  v163[5] = &v138;
  lpEnvironment = 0;
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  hObject = 0;
  v108 = 0;
  Buf2 = GUID_NULL;
  v115 = 0;
  v136 = 0;
  v127 = 0;
  v130 = 0;
  v133 = 0;
  hMem = 0;
  v142 = 0;
  v116 = 0;
  v131 = 0;
  *v16 = 0;
  *v18 = 0;
  *v19 = 0;
  *v20 = 0;
  v163[7] = &v116;
  p_Buf2 = (CSCMProfileCache *)&Buf2;
  p_ProcessInformation = &ProcessInformation;
  v112 = &v138;
  v143 = off_180117CA8;
  v141 = 0;
  v117 = 0;
  v138 = 0;
  v163[6] = this;
  v113 = 1;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v144,
    (struct wil::details::IFailureCallback *)&v143,
    v21,
    v22);
  v145 = &v138;
  if ( ((*((_QWORD *)this + 11) + 80LL) & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64)) != 0 )
    v117 = *(_QWORD *)(((*((_QWORD *)this + 11) + 80LL)
                      & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64))
                     + 8) != 0;
  if ( !v119 )
  {
    LastErrorMsg = -2147024891;
    v24 = 1556;
    v25 = 2147942405LL;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)v25,
      (int)cbSize);
LABEL_11:
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
    goto LABEL_12;
  }
  v147 = a6 & 4;
  if ( (a6 & 4) != 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      IsActivateAsIUAllowed = CClassData::PrivilegedLaunchIsActivateAsIUAllowed(v26, v119);
      LastErrorMsg = IsActivateAsIUAllowed;
      if ( IsActivateAsIUAllowed < 0 )
      {
        v24 = 1562;
LABEL_9:
        v25 = (unsigned int)IsActivateAsIUAllowed;
        goto LABEL_10;
      }
    }
    else
    {
      IsActivateAsIUAllowed = CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(this, v119, 0);
      LastErrorMsg = IsActivateAsIUAllowed;
      if ( IsActivateAsIUAllowed < 0 )
      {
        v24 = 1566;
        goto LABEL_9;
      }
    }
  }
  v134 = 0;
  if ( (CClassData::AppIDFlags(this) & 2) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v136,
      0);
    IsActivateAsIUAllowed = CToken::GetLogonIDSid(*((HANDLE *)v119 + 9), &v136);
    LastErrorMsg = IsActivateAsIUAllowed;
    if ( IsActivateAsIUAllowed < 0 )
    {
      v24 = 1572;
      goto LABEL_9;
    }
    v134 = 1;
  }
  v177 = 0;
  v178 = 0;
  v176[0] = (char *)v119 + 156;
  v176[1] = v136;
  LaunchCommandLine = IsTokenBoolPresent(*((void **)v119 + 9), TokenIsAppContainer, &v141);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v30 = 1578;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)LaunchCommandLine,
      (int)cbSize);
LABEL_28:
    CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
    goto LABEL_11;
  }
  lpEnvironment = 0;
  v150 = 0;
  StartupInfo.cb = 112;
  if ( a5 || a7 )
    a8 = (unsigned __int16 *)&Class;
  StartupInfo.lpDesktop = a8;
  v32 = 0;
  if ( *((_BYTE *)this + 80) != 3 )
    v32 = (WCHAR *)*((_QWORD *)this + 2);
  StartupInfo.lpTitle = v32;
  StartupInfo.dwXSize = 80;
  StartupInfo.dwX = 40;
  StartupInfo.dwY = 40;
  StartupInfo.dwYSize = 40;
  StartupInfo.wShowWindow = 1;
  StartupInfo.dwFlags = 128;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpMem,
    0);
  LaunchCommandLine = CClassData::GetLaunchCommandLine(this, (unsigned __int16 **)&lpMem);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v30 = 1616;
    goto LABEL_27;
  }
  v33 = 0;
  v34 = 16;
  v114 = 0;
  ProcessExtensions = 0;
  if ( (a6 & 4) != 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( *((_BYTE *)this + 172) )
      {
        SessionId = CToken::GetSessionId(v119);
        LaunchCommandLine = GetAaaAsUserTokenForPackagedRegistration(v119, SessionId, &hObject);
        LastErrorMsg = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v30 = 1634;
          goto LABEL_27;
        }
        v109[0] = 0;
        LaunchCommandLine = GetTokenHasInheritableSysAppId(hObject, v109);
        LastErrorMsg = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v30 = 1642;
          goto LABEL_27;
        }
        if ( v109[0] )
        {
          LODWORD(v125) = 0;
          LaunchCommandLine = AppModelPolicy_GetPolicy(hObject, 17, &v125);
          LastErrorMsg = LaunchCommandLine;
          if ( LaunchCommandLine < 0 )
          {
            v30 = 1647;
            goto LABEL_27;
          }
          ProcessExtensions = AppModelPolicyValueToWhichCreateProcessExtensions((unsigned int)v125);
        }
      }
      else
      {
        v37 = CToken::GetSessionId(v119);
        LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v119, v38, 0, v37, 1, &hObject);
        LastErrorMsg = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v30 = 1659;
          goto LABEL_27;
        }
      }
    }
    else
    {
      v39 = CToken::GetSessionId(v119);
      LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v119, v40, 0, v39, 1, &hObject);
      LastErrorMsg = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v30 = 1670;
        goto LABEL_27;
      }
    }
    v108 = 1;
    goto LABEL_76;
  }
  v109[0] = 0;
  LaunchCommandLine = CToken::HasInheritableSysAppId(v119, v109);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v30 = 1680;
    goto LABEL_27;
  }
  if ( v109[0] )
  {
    LODWORD(v125) = 0;
    LaunchCommandLine = AppModelPolicy_GetPolicy(*((_QWORD *)v119 + 9), 17, &v125);
    LastErrorMsg = LaunchCommandLine;
    if ( LaunchCommandLine < 0 )
    {
      v30 = 1684;
      goto LABEL_27;
    }
    ProcessExtensions = AppModelPolicyValueToWhichCreateProcessExtensions((unsigned int)v125);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    if ( ProcessExtensions == 1 )
    {
      v15 = 1;
    }
    else
    {
      if ( (unsigned int)(ProcessExtensions - 2) <= 1 )
      {
        v15 = 1;
        v114 = 1;
      }
      if ( !ProcessExtensions )
        goto LABEL_71;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpValue,
      0);
    PackageNameFromToken = GetPackageNameFromToken(*((void **)v119 + 9), (unsigned __int16 **)&lpValue);
    LastErrorMsg = PackageNameFromToken;
    if ( PackageNameFromToken < 0 )
    {
      v42 = 1713;
      goto LABEL_67;
    }
    if ( (unsigned int)(ProcessExtensions - 1) <= 2 )
      v34 = 20;
  }
LABEL_71:
  if ( gbSAFERAAAChecksEnabled && *((_QWORD *)this + 7) )
  {
    PackageNameFromToken = CClassData::GetAAASaferToken(this, v119, &hObject);
    LastErrorMsg = PackageNameFromToken;
    if ( PackageNameFromToken < 0 )
    {
      v42 = 1730;
      goto LABEL_67;
    }
    v108 = PackageNameFromToken != 1;
  }
LABEL_76:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    goto LABEL_87;
  if ( ProcessExtensions == 1 )
  {
    v15 = 1;
LABEL_83:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpValue,
      0);
    PackageNameFromToken = GetPackageNameFromToken(*((void **)v119 + 9), (unsigned __int16 **)&lpValue);
    LastErrorMsg = PackageNameFromToken;
    if ( PackageNameFromToken >= 0 )
    {
      if ( (unsigned int)(ProcessExtensions - 1) <= 2 )
        v34 |= 4u;
      goto LABEL_87;
    }
    v42 = 1767;
LABEL_67:
    v43 = (unsigned int)PackageNameFromToken;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)v43,
      (int)cbSize);
    CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
LABEL_12:
    if ( v113 )
    {
      v113 = 0;
      v28 = *(_QWORD *)p_Buf2 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)p_Buf2 == *(_QWORD *)&GUID_NULL.Data1 )
        v28 = *((_QWORD *)p_Buf2 + 1) - *(_QWORD *)GUID_NULL.Data4;
      if ( v28 )
      {
        v118 = *(struct _GUID *)p_Buf2;
        CSCMProfileCache::ReleaseProfile(p_Buf2, &v118);
      }
      if ( p_ProcessInformation->hProcess )
        NtTerminateProcess(p_ProcessInformation->hProcess, *v112);
    }
LABEL_260:
    v164 = 0;
    lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v163);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v131);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v133);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v130);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v127);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v136);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v104);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpValue);
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &lpAttributeList,
      0);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
    return (unsigned int)LastErrorMsg;
  }
  if ( (unsigned int)(ProcessExtensions - 2) <= 1 )
  {
    v15 = 1;
    v114 = 1;
  }
  if ( ProcessExtensions )
    goto LABEL_83;
LABEL_87:
  v44 = -1;
  v140 = 0;
  v45 = *((_QWORD *)this + 11);
  if ( v45 && *(_DWORD *)(v45 + 76) != -1 )
  {
    if ( *(_DWORD *)(v45 + 76) != 2 )
    {
      LastErrorMsg = -2147024809;
      v42 = 1790;
      v43 = 2147942487LL;
      goto LABEL_68;
    }
    v33 = 1;
    v140 = 2;
  }
  if ( !hObject )
  {
    hObject = (HANDLE)*((_QWORD *)v119 + 9);
    v108 = 0;
  }
  if ( (CClassData::AppIDFlags(this) & 0x8000) != 0 )
  {
    v149 = v46;
    v47 = (__int64 *)*((_QWORD *)this + 8);
    v118.Data1 = -463841586;
    *(_DWORD *)&v118.Data2 = 1173371292;
    *(_DWORD *)v118.Data4 = -1430294626;
    *(_DWORD *)&v118.Data4[4] = 527514829;
    if ( v47 )
    {
      v48 = *v47;
      LODWORD(v125) = (_DWORD)v46;
      PackageNameFromToken = (*(__int64 (__fastcall **)(__int64 *, struct _PROC_THREAD_ATTRIBUTE_LIST **))(v48 + 40))(
                               v47,
                               &v149);
      LastErrorMsg = PackageNameFromToken;
      if ( PackageNameFromToken < 0 )
      {
        v42 = 1815;
        goto LABEL_67;
      }
      PackageNameFromToken = CToken::GetTokenILValue(v119, (unsigned int *)&v125);
      v46 = 0;
      LastErrorMsg = PackageNameFromToken;
      if ( PackageNameFromToken < 0 )
      {
        v42 = 1816;
        goto LABEL_67;
      }
      if ( v149 )
      {
        v49 = *(_QWORD *)v149 - *(_QWORD *)&v118.Data1;
        if ( *(_QWORD *)v149 == *(_QWORD *)&v118.Data1 )
          v49 = *((_QWORD *)v149 + 1) - *(_QWORD *)v118.Data4;
        if ( !v49 && (_DWORD)v125 == 0x2000 )
        {
          v125 = 0;
          PackageNameFromToken = GetMediumRaisedCredUIToken(hObject, &v125);
          v46 = 0;
          LastErrorMsg = PackageNameFromToken;
          if ( PackageNameFromToken < 0 )
          {
            v42 = 1821;
            goto LABEL_67;
          }
          v50 = v125;
          if ( v125 )
          {
            if ( v108 )
            {
              CloseHandle(hObject);
              v46 = 0;
            }
            hObject = v50;
            v108 = 1;
          }
        }
      }
    }
  }
  p_lpAttributeList = &lpAttributeList;
  v51 = (int)v46;
  v154 = v46;
  v52 = (int)v46;
  v155 = 1;
  LOBYTE(v52) = v114 != (char)v46;
  LOBYTE(v51) = v15 != 0;
  LastErrorMsg = InitializeAttributeList(v117 + (unsigned int)v33 + v51 + v52, v156, &v154);
  if ( v155 )
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      p_lpAttributeList,
      v154);
  if ( LastErrorMsg < 0 )
  {
    v43 = (unsigned int)LastErrorMsg;
    v42 = 1868;
    goto LABEL_68;
  }
  Value = 4;
  if ( v15 )
  {
    do
      ++v44;
    while ( *((_WORD *)lpValue + v44) );
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20008u, lpValue, 2 * v44, 0, 0) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x755,
                       (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                       "Failed to add attribute (DCOMLaunch)",
                       cbSize);
      goto LABEL_28;
    }
  }
  if ( v114 && !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20012u, &Value, 4u, 0, 0) )
  {
    v54 = 1883;
LABEL_122:
    v55 = "Failed to add attribute (DCOMLaunch)";
LABEL_123:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v54,
                     (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                     v55,
                     cbSize);
LABEL_124:
    CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
    goto LABEL_125;
  }
  if ( v117
    && !UpdateProcThreadAttribute(
          lpAttributeList,
          0,
          0x20007u,
          *(PVOID *)(((*((_QWORD *)this + 11) + 80LL) & -(__int64)(*((_QWORD *)this + 11) != 0)) + 8),
          *(unsigned int *)((*((_QWORD *)this + 11) + 80LL) & -(__int64)(*((_QWORD *)this + 11) != 0)),
          0,
          0) )
  {
    v54 = 1890;
    goto LABEL_122;
  }
  if ( v33 )
  {
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Bu, &v140, 4u, 0, 0) )
    {
      v55 = "Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)";
      v54 = 1896;
      goto LABEL_123;
    }
    v34 |= 0x40000u;
  }
  if ( lpAttributeList )
  {
    v34 |= 0x80000u;
    v172 = lpAttributeList;
  }
  v122 = 0;
  if ( (a6 & 0x20) != 0 )
  {
    if ( v151 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v56 = CreateEnvBlock(&v122, hObject, 0);
    LastErrorMsg = v56;
    if ( v56 < 0 )
    {
      v57 = 1918;
LABEL_141:
      v58 = (unsigned int)v56;
LABEL_142:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v57,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v58,
        (int)cbSize);
LABEL_143:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
      goto LABEL_124;
    }
    v59 = v122;
  }
  else if ( (*((_DWORD *)this + 12) || (a6 & 1) != 0) && !v147 )
  {
    v56 = CSCMProfileCache::GetOrLoadProfile(v53, hObject, &Buf2, &v150);
    LastErrorMsg = v56;
    if ( v56 < 0 )
    {
      v57 = 1930;
      goto LABEL_141;
    }
    v59 = v150;
  }
  else
  {
    v60 = v151;
    if ( v151 )
    {
      v56 = CClassData::AddAppPathsToEnv(this, v151, v137, &v152);
      LastErrorMsg = v56;
      if ( v56 < 0 )
      {
        v57 = 1941;
        goto LABEL_141;
      }
      v59 = v152;
      if ( v60 != v152 )
        v115 = 1;
    }
    else
    {
      v59 = v157;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v130,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v127,
    0);
  v61 = (const unsigned __int16 *)lpMem;
  if ( *((_QWORD *)this + 5) )
    v61 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  DebuggerInfo = GetDebuggerInfo(
                   *((HANDLE *)v119 + 9),
                   (char *)v119 + 156,
                   0,
                   0,
                   v116,
                   v61,
                   (unsigned __int16 **)&v127,
                   (unsigned __int16 **)&v130);
  if ( DebuggerInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79F,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)DebuggerInfo,
      (int)cbSize);
  v63 = v127 != 0;
  v64 = (unsigned int)(ProcessExtensions - 1);
  if ( ProcessExtensions == 1 )
  {
    if ( v127 || !lpValue )
    {
      *v146 = v63;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hMem,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v133,
        0);
      v65 = v146;
      LastErrorMsg = PrepareUWPActivation(
                       (unsigned __int16 *)lpValue,
                       (char *)v119 + 156,
                       (unsigned __int16 **)&v133,
                       (unsigned __int16 **)&hMem,
                       v146);
      if ( LastErrorMsg < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7AE,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)LastErrorMsg,
          (int)cbSize);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
        CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
LABEL_125:
        if ( v113 )
        {
          v113 = 0;
          lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
        }
        goto LABEL_260;
      }
      if ( *v65 )
      {
        if ( v133 )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v127,
            &v133);
        if ( hMem )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v130,
            &hMem);
      }
    }
  }
  else
  {
    v64 = (unsigned int)(ProcessExtensions - 2);
    if ( (unsigned int)v64 <= 1 )
    {
      v165[0] = hObject;
      v165[2] = lpValue;
      v165[1] = 0;
      v165[3] = *((_QWORD *)this + 5);
      v166 = 3;
      if ( ProcessExtensions == 3 )
        LODWORD(v166) = 11;
      v56 = PrepareDesktopAppXActivation(v165, &v142);
      LastErrorMsg = v56;
      if ( v56 < 0 )
      {
        v57 = 2002;
        goto LABEL_141;
      }
      v64 = *(unsigned int *)(v142 + 16);
      *v146 = v64;
    }
  }
  if ( !v130 || !v59 )
  {
    v69 = v59;
    lpEnvironment = v59;
    goto LABEL_214;
  }
  LastErrorMsg = CClassData::AddDebugEnvironmentBlock((CClassData *)v64, v59, (unsigned __int16 *)v130, &lpEnvironment);
  if ( LastErrorMsg >= 0 )
  {
    v69 = lpEnvironment;
    if ( v59 != lpEnvironment )
    {
      if ( v115 )
      {
        HeapFree(g_hHeap, 0, v59);
        v69 = lpEnvironment;
      }
      v115 = 1;
    }
LABEL_214:
    if ( v69 )
      v34 |= 0x400u;
    if ( !ImpersonateLoggedOnUser(hObject) )
    {
      LastErrorMsg = -2147024891;
      v66 = 2041;
      goto LABEL_182;
    }
    v70 = 0;
    v116 = 1;
    if ( !v141 )
    {
      if ( v134 )
      {
        v71 = 0x1FFFFF;
        v72 = 0;
      }
      else
      {
        v71 = 0;
        v72 = 0x1FFFFF;
      }
      LODWORD(cbSize) = 0;
      v70 = (void *)CAccessInfo::IdentifyAccess(v176, v134 != 0 ? 3 : 0, v71, v72);
      if ( !v70 )
      {
        LastErrorMsg = -2147024882;
        v57 = 2050;
        v58 = 2147942414LL;
        goto LABEL_142;
      }
    }
    string = 0;
    v73 = *(void (__fastcall **)(CClassData *, HSTRING *))(*(_QWORD *)this + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v73(this, &string);
    ProcessAttributes.nLength = 24;
    ProcessAttributes.lpSecurityDescriptor = v70;
    ProcessAttributes.bInheritHandle = 0;
    v126 = 0;
    v74 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v126);
    if ( (unsigned int)DuplicateTokenAsPrimary(hObject, (char *)v119 + 156, v134, v74) )
    {
      if ( v108 )
        CloseHandle(hObject);
      hObject = v126;
      v126 = 0;
      p_string = &string;
      v168 = &a9;
      v169 = &v119;
      p_lpMem = &lpMem;
      v108 = 1;
      wil::ThreadFailureCallback__lambda_c01fa74e41f372f7dee1c77ec2d22326___((struct wil::details::IFailureCallback *)v173);
      CClassData::FireAAMCreateProcessEvent(this, a10, hObject, 0);
      if ( !CreateProcessAsUserW(
              hObject,
              *((LPCWSTR *)this + 5),
              (LPWSTR)lpMem,
              &ProcessAttributes,
              0,
              0,
              v34,
              lpEnvironment,
              0,
              &StartupInfo,
              &ProcessInformation) )
      {
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x824,
                         (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                         "Failed CreateProcessAsUser",
                         cbSize);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v174);
LABEL_229:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v126);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_143;
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v174);
    }
    RevertToSelf();
    v116 = 0;
    v75 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v131);
    if ( !OpenProcessToken(ProcessInformation.hProcess, 8u, v75) )
    {
      LastError = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs("rpcss.dll", LastError, 0);
      v77 = GetLastError();
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x82F,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v77,
        (unsigned int)cbSize);
    }
    v129 = 0;
    if ( (char *)v131 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded(this, v131, &v129);
      LastErrorMsg = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x837,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)ActivationActivityIfNeeded,
          (int)cbSize);
        v79 = v129;
        v129 = 0;
        if ( v79 )
          ActivationActivity::DestroyActivationActivity(v79);
        if ( (char *)v126 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v126);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_183;
      }
    }
    if ( ProcessExtensions )
    {
      v80 = ProcessExtensions - 1;
      if ( v80 )
      {
        if ( (unsigned int)(v80 - 1) <= 1 )
        {
          *(_DWORD *)(v142 + 40) = v34;
          v81 = PostCreateProcessDesktopAppXActivation(hObject, v142, &ProcessInformation);
          LastErrorMsg = v81;
          if ( v81 < 0 )
          {
            v82 = 2131;
LABEL_252:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v82,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)(unsigned int)v81,
              (int)cbSize);
            goto LABEL_253;
          }
          v83 = NtResumeThread(ProcessInformation.hThread, 0);
          if ( v83 < 0 )
          {
            LastErrorMsg = wil::details::in1diag3::Return_NtStatus(
                             retaddr,
                             (void *)0x854,
                             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                             (const char *)(unsigned int)v83,
                             (int)cbSize);
LABEL_253:
            wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
              &v129,
              0);
            goto LABEL_229;
          }
        }
      }
      else
      {
        v84 = string;
        v85 = CClassData::IdentityType(this);
        v87 = CClassData::AppUserModelID(v86);
        v88 = CClassData::ExecutionPackageName(this);
        v89 = *((_QWORD *)this + 7);
        v90 = v88;
        v91 = v127;
        v92 = a9;
        v93 = CToken::GetSessionId(v119);
        LastErrorMsg = PostCreateProcessUWPActivation(
                         v119,
                         *((unsigned int *)v158 + 33),
                         0,
                         v93,
                         v92,
                         0,
                         v91,
                         v89,
                         v90,
                         v87,
                         v85,
                         v84,
                         &ProcessInformation);
        if ( LastErrorMsg < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x84D,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (const char *)(unsigned int)LastErrorMsg,
            (int)"Failed PostCreateProcessUWPActivation",
            lpPreviousValue);
          goto LABEL_253;
        }
      }
    }
    else if ( v63 )
    {
      v137 = *((_DWORD *)this + 33);
      CClassData::IdentityType(this);
      CClassData::AppUserModelID(v94);
      CClassData::ExecutionPackageName(this);
      v95 = (int)v127;
      v96 = a9;
      v97 = CToken::GetSessionId(v119);
      LODWORD(cbSize) = v95;
      v81 = LaunchDebugger(v119, v97, v96, 0);
      LastErrorMsg = v81;
      if ( v81 < 0 )
      {
        v82 = 2118;
        goto LABEL_252;
      }
    }
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v129,
      0);
    if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v118 = Buf2;
      if ( CSCMProfileCache::ReleaseProfileOnProcessExit(v98, ProcessInformation.hProcess, &v118) )
      {
        v118 = Buf2;
        CSCMProfileCache::ReleaseProfile(v99, &v118);
        _InterlockedIncrement((volatile signed __int32 *)&gdwRudeProfileUnloads);
        Buf2 = GUID_NULL;
      }
    }
    hProcess = ProcessInformation.hProcess;
    dwProcessId = ProcessInformation.dwProcessId;
    hThread = ProcessInformation.hThread;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    *v159 = hProcess;
    v103 = v131;
    v131 = 0;
    *v160 = v103;
    *v161 = dwProcessId;
    CloseHandle(hThread);
    v113 = 0;
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v129,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v126);
    WindowsDeleteString(string);
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
    CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
    if ( v113 )
    {
      v113 = 0;
      lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
    }
    LastErrorMsg = 0;
    goto LABEL_260;
  }
  v66 = 2014;
LABEL_182:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v66,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)(unsigned int)LastErrorMsg,
    (int)cbSize);
LABEL_183:
  if ( v122 )
    DestroyEnvBlock();
  CAccessInfo::~CAccessInfo((CAccessInfo *)v176);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v144);
  if ( v113 )
  {
    v113 = 0;
    lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
  }
  v164 = 0;
  lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v163);
  if ( (char *)v131 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v131);
  if ( hMem )
    LocalFree(hMem);
  if ( v133 )
    LocalFree(v133);
  if ( v130 )
    LocalFree(v130);
  if ( v127 )
    LocalFree(v127);
  if ( v136 )
    LocalFree(v136);
  if ( ProcessInformation.hProcess )
    wil::details::CloseHandle((wil::details *)ProcessInformation.hProcess, v67);
  if ( ProcessInformation.hThread )
    wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v67);
  if ( lpValue )
    HeapFree(g_hHeap, 0, lpValue);
  v68 = lpAttributeList;
  lpAttributeList = 0;
  if ( v68 )
    LocalFree(v68);
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x18004c4b0  push    rbp
0x18004c4b2  push    rbx
0x18004c4b3  push    rsi
0x18004c4b4  push    rdi
0x18004c4b5  push    r12
0x18004c4b7  push    r13
0x18004c4b9  push    r14
0x18004c4bb  push    r15
0x18004c4bd  lea     rbp, [rsp-378h]
0x18004c4c5  sub     rsp, 478h
0x18004c4cc  mov     rax, cs:__security_cookie
0x18004c4d3  xor     rax, rsp
0x18004c4d6  mov     [rbp+3B0h+var_50], rax
0x18004c4dd  mov     rax, [rbp+3B0h+arg_50]
0x18004c4e4  xor     r13d, r13d
0x18004c4e7  mov     rdi, [rbp+3B0h+arg_58]
0x18004c4ee  mov     rsi, rcx
0x18004c4f1  mov     r14, [rbp+3B0h+arg_60]
0x18004c4f8  mov     r15, [rbp+3B0h+arg_68]
0x18004c4ff  mov     rbx, [rbp+3B0h+arg_70]
0x18004c506  mov     [rbp+3B0h+var_2E0], r8
0x18004c50d  lea     r8d, [r13+68h]; Size
0x18004c511  mov     [rbp+3B0h+var_2A8], rcx
0x18004c518  lea     rcx, [rbp+3B0h+StartupInfo.lpReserved]; void *
0x18004c51f  mov     [rbp+3B0h+var_400], rdx
0x18004c523  xor     edx, edx; Val
0x18004c525  mov     [rbp+3B0h+var_370], r9d
0x18004c529  mov     [rbp+3B0h+var_2B8], rax
0x18004c530  mov     [rbp+3B0h+var_2A0], rdi
0x18004c537  mov     [rbp+3B0h+var_298], r14
0x18004c53e  mov     [rbp+3B0h+var_290], r15
0x18004c545  mov     [rbp+3B0h+var_300], rbx
0x18004c54c  mov     [rbp+3B0h+lpMem], r13
0x18004c550  mov     qword ptr [rbp+3B0h+StartupInfo.cb], r13
0x18004c557  call    memset_0
0x18004c55c  mov     eax, r13d
0x18004c55f  mov     [rbp+3B0h+lpAttributeList], r13
0x18004c563  mov     qword ptr [rbp+3B0h+ProcessInformation.dwProcessId], rax
0x18004c567  lea     rdx, [rbp+3B0h+var_340]; struct wil::details::IFailureCallback *
0x18004c56b  mov     qword ptr [rbp+3B0h+ProcessAttributes.bInheritHandle], rax
0x18004c572  lea     rcx, [rbp+3B0h+var_338]; this
0x18004c576  mov     [rbp+3B0h+var_2B0], rax
0x18004c57d  xorps   xmm0, xmm0
0x18004c580  mov     [rbp+3B0h+var_2D8], rax
0x18004c587  xorps   xmm1, xmm1
0x18004c58a  movups  xmmword ptr [rbp+3B0h+ProcessInformation.hProcess], xmm0
0x18004c58e  mov     [rbp+3B0h+lpValue], r13
0x18004c592  lea     rax, [rbp+3B0h+var_417]
0x18004c596  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c59d  mov     [rbp+3B0h+var_270], rax
0x18004c5a4  lea     rax, [rbp+3B0h+var_380]
0x18004c5a8  mov     [rbp+3B0h+var_268], rax
0x18004c5af  lea     rax, [rbp+3B0h+hObject]
0x18004c5b3  mov     [rbp+3B0h+var_260], rax
0x18004c5ba  lea     rax, [rsp+4B0h+var_440]
0x18004c5bf  mov     [rbp+3B0h+var_258], rax
0x18004c5c6  lea     rax, [rbp+3B0h+var_348]
0x18004c5ca  mov     [rbp+3B0h+var_250], rax
0x18004c5d1  lea     rax, [rbp+3B0h+var_36C]
0x18004c5d5  mov     [rbp+3B0h+var_248], rax
0x18004c5dc  lea     rax, [rbp+3B0h+var_416]
0x18004c5e0  mov     [rbp+3B0h+var_380], r13
0x18004c5e4  movups  xmmword ptr [rbp+3B0h+ProcessAttributes.nLength], xmm1
0x18004c5eb  mov     [rbp+3B0h+hObject], r13
0x18004c5ef  mov     [rsp+4B0h+var_440], r13b
0x18004c5f4  movdqu  [rbp+3B0h+Buf2], xmm0
0x18004c5fc  mov     [rbp+3B0h+var_417], r13b
0x18004c600  mov     [rbp+3B0h+var_378], r13
0x18004c604  mov     [rbp+3B0h+var_3C0], r13
0x18004c608  mov     [rbp+3B0h+var_3A8], r13
0x18004c60c  mov     [rbp+3B0h+var_390], r13
0x18004c610  mov     [rbp+3B0h+hMem], r13
0x18004c614  mov     [rbp+3B0h+var_348], r13
0x18004c618  mov     [rbp+3B0h+var_416], r13b
0x18004c61c  mov     [rbp+3B0h+var_3A0], r13
0x18004c620  mov     [rdi], r13
0x18004c623  lea     edi, [r13+1]
0x18004c627  mov     [r14], r13
0x18004c62a  mov     [r15], r13d
0x18004c62d  mov     [rbx], r13d
0x18004c630  mov     [rbp+3B0h+var_238], rax
0x18004c637  lea     rax, [rbp+3B0h+Buf2]
0x18004c63e  mov     [rsp+4B0h+var_438], rax
0x18004c643  lea     rax, [rbp+3B0h+ProcessInformation]
0x18004c647  mov     [rbp+3B0h+var_430], rax
0x18004c64b  lea     rax, [rbp+3B0h+var_36C]
0x18004c64f  mov     [rbp+3B0h+var_428], rax
0x18004c653  lea     rax, off_180117CA8
0x18004c65a  mov     [rbp+3B0h+var_340], rax
0x18004c65e  mov     [rbp+3B0h+var_34C], r13d
0x18004c662  mov     [rbp+3B0h+var_415], r13b
0x18004c666  mov     [rbp+3B0h+var_36C], r13d
0x18004c66a  mov     [rbp+3B0h+var_240], rsi
0x18004c671  mov     [rbp+3B0h+var_420], dil
0x18004c675  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18004c67a  lea     rax, [rbp+3B0h+var_36C]
0x18004c67e  mov     [rbp+3B0h+var_308], rax
0x18004c685  mov     rax, [rsi+58h]
0x18004c689  lea     rcx, [rax+50h]
0x18004c68d  neg     rax
0x18004c690  sbb     rdx, rdx
0x18004c693  and     rdx, rcx
0x18004c696  jz      short loc_18004C6A0
0x18004c698  cmp     [rdx+8], r13
0x18004c69c  setnz   [rbp+3B0h+var_415]
0x18004c6a0  cmp     [rbp+3B0h+var_400], r13
0x18004c6a4  jnz     short loc_18004C6B5
0x18004c6a6  mov     ebx, 80070005h
0x18004c6ab  mov     edx, 614h
0x18004c6b0  mov     r9d, ebx
0x18004c6b3  jmp     short loc_18004C6FC
0x18004c6b5  mov     r14d, dword ptr [rbp+3B0h+arg_28]
0x18004c6bc  and     r14d, 4
0x18004c6c0  mov     [rbp+3B0h+var_2F8], r14d
0x18004c6c7  jz      loc_18004C79A
0x18004c6cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18004c6d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18004c6d9  mov     rdx, [rbp+3B0h+var_400]; struct CToken *
0x18004c6dd  test    al, al
0x18004c6df  jz      loc_18004C77F
0x18004c6e5  call    ?PrivilegedLaunchIsActivateAsIUAllowed@CClassData@@QEAAJPEAVCToken@@@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowed(CToken *)
0x18004c6ea  mov     ebx, eax
0x18004c6ec  test    eax, eax
0x18004c6ee  jns     loc_18004C79A
0x18004c6f4  mov     edx, 61Ah; void *
0x18004c6f9  mov     r9d, eax; char *
0x18004c6fc  mov     rcx, [rbp+3B8h]; this
0x18004c703  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004c70a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c70f  lea     rcx, [rbp+3B0h+var_338]; this
0x18004c713  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18004c718  cmp     [rbp+3B0h+var_420], r13b
0x18004c71c  jz      loc_18004DA59
0x18004c722  mov     rcx, [rsp+4B0h+var_438]; this
0x18004c727  mov     [rbp+3B0h+var_420], r13b
0x18004c72b  mov     rax, [rcx]
0x18004c72e  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18004c735  jnz     short loc_18004C742
0x18004c737  mov     rax, [rcx+8]
0x18004c73b  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18004c742  test    rax, rax
0x18004c745  jz      short loc_18004C758
0x18004c747  movups  xmm0, xmmword ptr [rcx]
0x18004c74a  lea     rdx, [rbp+3B0h+var_410]; struct _GUID
0x18004c74e  movdqu  xmmword ptr [rbp+3B0h+var_410.Data1], xmm0
0x18004c753  call    ?ReleaseProfile@CSCMProfileCache@@QEAAJU_GUID@@@Z; CSCMProfileCache::ReleaseProfile(_GUID)
0x18004c758  mov     rax, [rbp+3B0h+var_430]
0x18004c75c  mov     rcx, [rax]; ProcessHandle
0x18004c75f  test    rcx, rcx
0x18004c762  jz      loc_18004DA59
0x18004c768  mov     rdx, [rbp+3B0h+var_428]
0x18004c76c  mov     edx, [rdx]; ExitStatus
0x18004c76e  call    cs:__imp_NtTerminateProcess
0x18004c775  nop     dword ptr [rax+rax+00h]
0x18004c77a  jmp     loc_18004DA59
0x18004c77f  xor     r8d, r8d; int
0x18004c782  mov     rcx, rsi; this
0x18004c785  call    ?PrivilegedLaunchIsActivateAsIUAllowedOld@CClassData@@QEAAJPEAVCToken@@H@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(CToken *,int)
0x18004c78a  mov     ebx, eax
0x18004c78c  test    eax, eax
0x18004c78e  jns     short loc_18004C79A
0x18004c790  mov     edx, 61Eh
0x18004c795  jmp     loc_18004C6F9
0x18004c79a  mov     rcx, rsi; this
0x18004c79d  mov     [rbp+3B0h+var_388], r13d
0x18004c7a1  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x18004c7a6  test    al, 2
0x18004c7a8  jz      short loc_18004C7D9
0x18004c7aa  xor     edx, edx
0x18004c7ac  lea     rcx, [rbp+3B0h+var_378]
0x18004c7b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004c7b5  mov     rcx, [rbp+3B0h+var_400]
0x18004c7b9  lea     rdx, [rbp+3B0h+var_378]; void **
0x18004c7bd  mov     rcx, [rcx+48h]; TokenHandle
0x18004c7c1  call    ?GetLogonIDSid@CToken@@SAJPEAXPEAPEAX@Z; CToken::GetLogonIDSid(void *,void * *)
0x18004c7c6  mov     ebx, eax
0x18004c7c8  test    eax, eax
0x18004c7ca  jns     short loc_18004C7D6
0x18004c7cc  mov     edx, 624h
0x18004c7d1  jmp     loc_18004C6F9
0x18004c7d6  mov     [rbp+3B0h+var_388], edi
0x18004c7d9  mov     rcx, [rbp+3B0h+var_400]
0x18004c7dd  lea     r8, [rbp+3B0h+var_34C]; int *
0x18004c7e1  xorps   xmm0, xmm0
0x18004c7e4  xorps   xmm1, xmm1
0x18004c7e7  movdqa  [rbp+3B0h+var_E0], xmm0
0x18004c7ef  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x18004c7f4  movdqa  [rbp+3B0h+var_D0], xmm1
0x18004c7fc  lea     rax, [rcx+9Ch]
0x18004c803  mov     [rbp+3B0h+var_F0], rax
0x18004c80a  mov     rax, [rbp+3B0h+var_378]
0x18004c80e  mov     [rbp+3B0h+var_E8], rax
0x18004c815  mov     rcx, [rcx+48h]; void *
0x18004c819  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18004c81e  mov     ebx, eax
0x18004c820  test    eax, eax
0x18004c822  jns     short loc_18004C850
0x18004c824  mov     edx, 62Ah; void *
0x18004c829  mov     rcx, [rbp+3B8h]; this
0x18004c830  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18004c837  mov     r9d, eax; char *
0x18004c83a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c83f  lea     rcx, [rbp+3B0h+var_F0]; this
0x18004c846  call    ??1CAccessInfo@@QEAA@XZ; CAccessInfo::~CAccessInfo(void)
0x18004c84b  jmp     loc_18004C70F
0x18004c850  mov     [rbp+3B0h+var_380], r13
0x18004c854  mov     [rbp+3B0h+var_2E8], r13
0x18004c85b  mov     [rbp+3B0h+StartupInfo.cb], 70h ; 'p'
0x18004c865  cmp     [rbp+3B0h+arg_20], r13d
0x18004c86c  jnz     short loc_18004C87E
0x18004c86e  mov     rax, [rbp+3B0h+arg_38]
0x18004c875  cmp     [rbp+3B0h+arg_30], r13d
0x18004c87c  jz      short loc_18004C885
0x18004c87e  lea     rax, Class
0x18004c885  mov     [rbp+3B0h+StartupInfo.lpDesktop], rax
0x18004c88c  mov     rax, r13
0x18004c88f  cmp     byte ptr [rsi+50h], 3
0x18004c893  jz      short loc_18004C899
0x18004c895  mov     rax, [rsi+10h]
0x18004c899  mov     [rbp+3B0h+StartupInfo.lpTitle], rax
0x18004c8a0  lea     rcx, [rbp+3B0h+lpMem]
0x18004c8a4  mov     eax, 28h ; '('
0x18004c8a9  mov     [rbp+3B0h+StartupInfo.dwXSize], 50h ; 'P'
0x18004c8b3  xor     edx, edx
0x18004c8b5  mov     [rbp+3B0h+StartupInfo.dwX], eax
0x18004c8bb  mov     [rbp+3B0h+StartupInfo.dwY], eax
0x18004c8c1  mov     [rbp+3B0h+StartupInfo.dwYSize], eax
0x18004c8c7  mov     [rbp+3B0h+StartupInfo.wShowWindow], di
0x18004c8ce  mov     [rbp+3B0h+StartupInfo.dwFlags], 80h
0x18004c8d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004c8dd  lea     rdx, [rbp+3B0h+lpMem]; unsigned __int16 **
0x18004c8e1  mov     rcx, rsi; this
0x18004c8e4  call    ?GetLaunchCommandLine@CClassData@@AEAAJPEAPEAG@Z; CClassData::GetLaunchCommandLine(ushort * *)
0x18004c8e9  mov     ebx, eax
0x18004c8eb  test    eax, eax
0x18004c8ed  jns     short loc_18004C8F9
0x18004c8ef  mov     edx, 650h
0x18004c8f4  jmp     loc_18004C829
0x18004c8f9  xor     r12d, r12d
0x18004c8fc  mov     r15d, 10h
0x18004c902  mov     [rbp+3B0h+var_418], r12b
0x18004c906  mov     edi, r12d
0x18004c909  test    r14d, r14d
0x18004c90c  jz      loc_18004CA23
0x18004c912  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18004c919  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18004c91e  mov     rcx, [rbp+3B0h+var_400]; this
0x18004c922  test    al, al
0x18004c924  jz      loc_18004C9F1
0x18004c92a  cmp     [rsi+0ACh], r12b
0x18004c931  jz      loc_18004C9BF
0x18004c937  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18004c93c  mov     rcx, [rbp+3B0h+var_400]; this
0x18004c940  lea     r8, [rbp+3B0h+hObject]; void **
0x18004c944  mov     edx, eax; unsigned int
0x18004c946  call    ?GetAaaAsUserTokenForPackagedRegistration@@YAJPEAVCToken@@KPEAPEAX@Z; GetAaaAsUserTokenForPackagedRegistration(CToken *,ulong,void * *)
0x18004c94b  mov     ebx, eax
0x18004c94d  test    eax, eax
0x18004c94f  jns     short loc_18004C95B
0x18004c951  mov     edx, 662h
0x18004c956  jmp     loc_18004C829
0x18004c95b  mov     rcx, [rbp+3B0h+hObject]; void *
0x18004c95f  lea     rdx, [rsp+4B0h+var_43F]; bool *
0x18004c964  mov     [rsp+4B0h+var_43F], r12b
0x18004c969  call    ?GetTokenHasInheritableSysAppId@@YAJPEAXPEA_N@Z; GetTokenHasInheritableSysAppId(void *,bool *)
0x18004c96e  mov     ebx, eax
0x18004c970  test    eax, eax
0x18004c972  jns     short loc_18004C97E
0x18004c974  mov     edx, 66Ah
0x18004c979  jmp     loc_18004C829
0x18004c97e  cmp     [rsp+4B0h+var_43F], r12b
0x18004c983  jz      short loc_18004C9B5
0x18004c985  mov     rcx, [rbp+3B0h+hObject]
0x18004c989  lea     r8, [rbp+3B0h+var_3D0]
0x18004c98d  mov     edx, 11h
0x18004c992  mov     dword ptr [rbp+3B0h+var_3D0], r12d
0x18004c996  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18004c99b  mov     ebx, eax
0x18004c99d  test    eax, eax
0x18004c99f  jns     short loc_18004C9AB
0x18004c9a1  mov     edx, 66Fh
0x18004c9a6  jmp     loc_18004C829
0x18004c9ab  mov     ecx, dword ptr [rbp+3B0h+var_3D0]
0x18004c9ae  call    ?AppModelPolicyValueToWhichCreateProcessExtensions@@YA?AW4WhichCreateProcessExtensions@@W4AppModelPolicy_PolicyValue@@@Z; AppModelPolicyValueToWhichCreateProcessExtensions(AppModelPolicy_PolicyValue)
0x18004c9b3  mov     edi, eax
0x18004c9b5  mov     [rsp+4B0h+var_440], 1
0x18004c9ba  jmp     loc_18004CB53
0x18004c9bf  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18004c9c4  lea     rcx, [rbp+3B0h+hObject]
0x18004c9c8  mov     r9d, eax; unsigned int
0x18004c9cb  mov     [rsp+4B0h+lpPreviousValue], rcx; void **
0x18004c9d0  xor     r8d, r8d; unsigned __int64
0x18004c9d3  mov     rcx, [rbp+3B0h+var_400]; this
0x18004c9d7  mov     byte ptr [rsp+4B0h+cbSize], 1; bool
0x18004c9dc  call    ?GetInteractiveUserTokenForCallerRequest@@YAJPEAVCToken@@PEBG_KK_NPEAPEAX@Z; GetInteractiveUserTokenForCallerRequest(CToken *,ushort const *,unsigned __int64,ulong,bool,void * *)
0x18004c9e1  mov     ebx, eax
0x18004c9e3  test    eax, eax
0x18004c9e5  jns     short loc_18004C9B5
0x18004c9e7  mov     edx, 67Bh
0x18004c9ec  jmp     loc_18004C829
  ... truncated ...
```
