# CClassData::PrivilegedLaunchActivatorServer(CToken *,ushort *,ulong,int,ulong,int,ushort *,ulong,unsigned __int64,tagBLOB *,void * *,void * *,ulong *,int *)

- ea: `0x1800507c0`
- end: `0x18005209e`
- name: `?PrivilegedLaunchActivatorServer@CClassData@@QEAAJPEAVCToken@@PEAGKHKH1K_KPEAUtagBLOB@@PEAPEAX4PEAKPEAH@Z`
- size: `6366`
- prototype: `__int64 __fastcall(CClassData *this, struct CToken *, unsigned __int16 *, unsigned int, int, char, int, unsigned __int16 *, unsigned int, unsigned __int64, struct tagBLOB *, void **, void **, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `69`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009aec4`
- `0x1800edd30`

## callees

- `0x180005c40`
- `0x1800081c0`
- `0x180008264`
- `0x180008648`
- `0x180009b30`
- `0x18000a1ac`
- `0x18000a480`
- `0x18000b428`
- `0x18001f828`
- `0x1800247a8`
- `0x1800250b0`
- `0x180025730`
- `0x180026a90`
- `0x18002834c`
- `0x180029a54`
- `0x18002ba28`
- `0x18002d6cc`
- `0x18002e210`
- `0x18002ed28`
- `0x18002f058`
- `0x18002fa6c`
- `0x1800320b0`
- `0x1800320d4`
- `0x18004778c`
- `0x18004c5bc`
- `0x18004c760`
- `0x18004c774`
- `0x18004ca7c`
- `0x18004cb84`
- `0x18004fee4`
- `0x180050178`
- `0x1800507c0`
- `0x1800520a4`
- `0x180052184`
- `0x1800521a8`
- `0x180052210`
- `0x18005248c`
- `0x1800524c4`
- `0x1800684b4`
- `0x18006ad0c`
- `0x18006b5a4`
- `0x18006bbe4`
- `0x180078e8c`
- `0x1800805d4`
- `0x180081d3c`
- `0x18008cc30`
- `0x18008cd90`
- `0x18008e98c`
- `0x180098b54`
- `0x18009d044`

## import_xrefs

- `ntdll!NtResumeThread` at `0x180051d3d`
- `ntdll!NtResumeThread` at `0x180051d3d`
- `ntdll!NtTerminateProcess` at `0x180050a95`
- `ntdll!NtTerminateProcess` at `0x180051084`
- `ntdll!NtTerminateProcess` at `0x1800511e9`
- `ntdll!NtTerminateProcess` at `0x1800513cf`
- `ntdll!NtTerminateProcess` at `0x180050a95`
- `ntdll!NtTerminateProcess` at `0x180051084`
- `ntdll!NtTerminateProcess` at `0x1800511e9`
- `ntdll!NtTerminateProcess` at `0x1800513cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005126b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800518f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051afb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005126b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800518f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051afb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051fa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050c8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051971`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800519a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800519cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050c8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051971`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800519a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800519cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051c30`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180051c30`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005133b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005140d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005145b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180051497`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005133b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005140d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005145b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180051497`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180051bb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180051bb2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800519f6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800519f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180051c11`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180051c11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051bf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051fcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051bf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051fcb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050b06`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051612`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051640`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051901`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051910`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005191f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005192e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005193d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051986`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050b06`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051612`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051640`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051901`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051910`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005191f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005192e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005193d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180051986`
- `profapi!__imp_CreateEnvBlock` at `0x1800514f7`
- `profapi!__imp_CreateEnvBlock` at `0x1800514f7`
- `profapi!__imp_DestroyEnvBlock` at `0x1800518a3`
- `profapi!__imp_DestroyEnvBlock` at `0x1800518a3`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18005172a`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18005172a`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180051d21`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x180051d21`

## string_xrefs

- `0x180050a30`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180050bcb`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051011`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051176`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005135c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051512`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800516a6`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800517ba`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005188b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051bca`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051c5e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051ca3`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051d52`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051e17`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051ed3`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180051bc3`: `Failed CreateProcessAsUser`
- `0x18005134e`: `Failed to add attribute (DCOMLaunch)`
- `0x1800514a1`: `Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)`
- `0x180051e08`: `Failed PostCreateProcessUWPActivation`
- `0x180051c43`: `rpcss.dll`

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
  unsigned __int8 v15; // r12
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
  struct _PROCESS_INFORMATION *v29; // rdx
  HLOCAL v30; // rcx
  int LaunchCommandLine; // eax
  __int64 v32; // rdx
  WCHAR *v34; // rax
  void *v35; // rdi
  DWORD LastError; // ebx
  DWORD v37; // r15d
  char v38; // r13
  int ProcessExtensions; // edi
  unsigned int SessionId; // eax
  unsigned int v41; // eax
  const unsigned __int16 *v42; // rdx
  unsigned int v43; // eax
  const unsigned __int16 *v44; // rdx
  __int64 v45; // r14
  __int64 v46; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v47; // rdx
  __int64 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // rax
  int TokenILValue; // eax
  __int64 v55; // rax
  int MediumRaisedCredUIToken; // eax
  unsigned __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // rax
  struct _PROCESS_INFORMATION *v60; // rdx
  void *v61; // rbx
  int v62; // eax
  int v63; // ecx
  CSCMProfileCache *v64; // rcx
  __int64 v65; // rdx
  const char *v66; // r9
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // r9
  unsigned __int16 *v71; // r14
  unsigned __int16 *v72; // r12
  HLOCAL v73; // rbx
  HLOCAL v74; // rbx
  const unsigned __int16 *v75; // r8
  int DebuggerInfo; // eax
  bool v77; // r12
  unsigned __int64 v78; // rcx
  int *v79; // r13
  __int64 v80; // rdx
  void *v81; // rdx
  HLOCAL v82; // rcx
  unsigned __int16 *v83; // rax
  void *v84; // r14
  __int64 v85; // r8
  __int64 v86; // r9
  void (__fastcall *v87)(CClassData *, HSTRING *); // rbx
  void **v88; // rax
  void **v89; // rax
  DWORD v90; // eax
  DWORD v91; // eax
  int ActivationActivityIfNeeded; // eax
  int v93; // edi
  int v94; // eax
  __int64 v95; // rdx
  NTSTATUS v96; // eax
  HSTRING v97; // r13
  int v98; // r12d
  CClassData *v99; // rcx
  const unsigned __int16 *v100; // r15
  const unsigned __int16 *v101; // rax
  __int64 v102; // rdi
  const unsigned __int16 *v103; // rbx
  HLOCAL v104; // rsi
  unsigned int v105; // r14d
  unsigned int v106; // eax
  CClassData *v107; // rcx
  int v108; // esi
  unsigned int v109; // r14d
  unsigned int v110; // eax
  CSCMProfileCache *v111; // rcx
  CSCMProfileCache *v112; // rcx
  HANDLE hProcess; // rax
  DWORD dwProcessId; // edx
  HANDLE hThread; // rcx
  HANDLE v116; // rax
  struct _PROCESS_INFORMATION *v117; // rdx
  const char *cbSize; // [rsp+20h] [rbp-E0h]
  const char *lpPreviousValue; // [rsp+28h] [rbp-D8h]
  bool v121; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  PVOID lpValue; // [rsp+80h] [rbp-80h] BYREF
  bool v124; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v125; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v126; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v127; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v128; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v129; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL v130; // [rsp+B8h] [rbp-48h] BYREF
  CSCMProfileCache *p_Buf2; // [rsp+C0h] [rbp-40h] BYREF
  struct _PROCESS_INFORMATION *p_ProcessInformation; // [rsp+C8h] [rbp-38h]
  NTSTATUS *v133; // [rsp+D0h] [rbp-30h]
  char v134; // [rsp+D8h] [rbp-28h]
  char v135; // [rsp+E0h] [rbp-20h]
  char v136; // [rsp+E1h] [rbp-1Fh] BYREF
  bool v137; // [rsp+E2h] [rbp-1Eh] BYREF
  struct _GUID v138; // [rsp+F0h] [rbp-10h] BYREF
  bool v139; // [rsp+100h] [rbp+0h]
  CToken *v140; // [rsp+108h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+110h] [rbp+10h] BYREF
  HSTRING string; // [rsp+118h] [rbp+18h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v144; // [rsp+138h] [rbp+38h] BYREF
  void *v145; // [rsp+140h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+148h] [rbp+48h] BYREF
  HANDLE v147[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v148[8]; // [rsp+160h] [rbp+60h] BYREF
  char v149; // [rsp+1A0h] [rbp+A0h]
  __int64 v150; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v151; // [rsp+1B8h] [rbp+B8h]
  int v152; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned __int16 *lpEnvironment; // [rsp+1C0h] [rbp+C0h] BYREF
  int v154; // [rsp+1C8h] [rbp+C8h]
  __int64 v155; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 *v156; // [rsp+1D8h] [rbp+D8h] BYREF
  int v157; // [rsp+1E0h] [rbp+E0h] BYREF
  int v158[3]; // [rsp+1E4h] [rbp+E4h] BYREF
  __int64 (__fastcall **v159)(); // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v160[48]; // [rsp+1F8h] [rbp+F8h] BYREF
  int *v161; // [rsp+228h] [rbp+128h]
  int *v162; // [rsp+230h] [rbp+130h]
  int Value; // [rsp+238h] [rbp+138h] BYREF
  int v164; // [rsp+23Ch] [rbp+13Ch]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v165; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 *v166; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int16 *v167; // [rsp+250h] [rbp+150h]
  unsigned __int16 *v168; // [rsp+258h] [rbp+158h] BYREF
  HLOCAL *p_hMem; // [rsp+260h] [rbp+160h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v170; // [rsp+268h] [rbp+168h] BYREF
  char v171; // [rsp+270h] [rbp+170h]
  struct tagBLOB *v172; // [rsp+278h] [rbp+178h]
  CClassData *v173; // [rsp+280h] [rbp+180h]
  void **v174; // [rsp+288h] [rbp+188h]
  void **v175; // [rsp+290h] [rbp+190h]
  unsigned int *v176; // [rsp+298h] [rbp+198h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD v178[4]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v179; // [rsp+2D8h] [rbp+1D8h]
  HSTRING *p_string; // [rsp+2E0h] [rbp+1E0h]
  unsigned int *v181; // [rsp+2E8h] [rbp+1E8h]
  CToken **v182; // [rsp+2F0h] [rbp+1F0h]
  LPVOID *p_lpMem; // [rsp+2F8h] [rbp+1F8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+300h] [rbp+200h] BYREF
  HLOCAL v185; // [rsp+368h] [rbp+268h]
  _BYTE v186[8]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v187[88]; // [rsp+378h] [rbp+278h] BYREF
  GUID Buf2; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v189[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v190; // [rsp+3F0h] [rbp+2F0h]
  __int128 v191; // [rsp+400h] [rbp+300h]
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v15 = 0;
  v16 = a12;
  v18 = a13;
  v19 = a14;
  v20 = a15;
  v167 = a3;
  v173 = this;
  v140 = a2;
  v151 = a4;
  v172 = a11;
  v174 = a12;
  v175 = a13;
  v176 = a14;
  v162 = a15;
  lpMem = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  hMem = 0;
  v156 = 0;
  v168 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  lpValue = 0;
  v148[0] = &v136;
  v148[1] = &lpEnvironment;
  v148[2] = &hObject;
  v148[3] = &v121;
  v148[4] = &v155;
  v148[5] = &v152;
  lpEnvironment = 0;
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  hObject = 0;
  v121 = 0;
  Buf2 = GUID_NULL;
  v136 = 0;
  v130 = 0;
  v125 = 0;
  v126 = 0;
  v129 = 0;
  v128 = 0;
  v155 = 0;
  v137 = 0;
  v127 = 0;
  *v16 = 0;
  *v18 = 0;
  *v19 = 0;
  *v20 = 0;
  v148[7] = &v137;
  p_Buf2 = (CSCMProfileCache *)&Buf2;
  p_ProcessInformation = &ProcessInformation;
  v133 = &v152;
  v159 = &off_18010ECB0;
  v157 = 0;
  v139 = 0;
  v152 = 0;
  v148[6] = this;
  v134 = 1;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v160,
    (struct wil::details::IFailureCallback *)&v159,
    v21,
    v22);
  v161 = &v152;
  if ( ((*((_QWORD *)this + 11) + 80LL) & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64)) != 0 )
    v139 = *(_QWORD *)(((*((_QWORD *)this + 11) + 80LL)
                      & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 11) >> 64))
                     + 8) != 0;
  if ( !v140 )
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
    goto LABEL_11;
  }
  v164 = a6 & 4;
  if ( (a6 & 4) != 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      IsActivateAsIUAllowed = CClassData::PrivilegedLaunchIsActivateAsIUAllowed(v26, v140);
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
      IsActivateAsIUAllowed = CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(this, v140, 0);
      LastErrorMsg = IsActivateAsIUAllowed;
      if ( IsActivateAsIUAllowed < 0 )
      {
        v24 = 1566;
        goto LABEL_9;
      }
    }
  }
  v154 = 0;
  if ( (CClassData::AppIDFlags(this) & 2) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v130,
      0);
    IsActivateAsIUAllowed = CToken::GetLogonIDSid(*((HANDLE *)v140 + 9), &v130);
    LastErrorMsg = IsActivateAsIUAllowed;
    if ( IsActivateAsIUAllowed < 0 )
    {
      v24 = 1572;
      goto LABEL_9;
    }
    v154 = 1;
  }
  v190 = 0;
  v191 = 0;
  v189[0] = (char *)v140 + 156;
  v189[1] = v130;
  LaunchCommandLine = IsTokenBoolPresent(*((void **)v140 + 9), TokenIsAppContainer, &v157);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v32 = 1578;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)LaunchCommandLine,
      (int)cbSize);
    CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
LABEL_11:
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
    if ( v134 )
    {
      v134 = 0;
      v28 = *(_QWORD *)p_Buf2 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)p_Buf2 == *(_QWORD *)&GUID_NULL.Data1 )
        v28 = *((_QWORD *)p_Buf2 + 1) - *(_QWORD *)GUID_NULL.Data4;
      if ( v28 )
      {
        v138 = *(struct _GUID *)p_Buf2;
        CSCMProfileCache::ReleaseProfile(p_Buf2, &v138);
      }
      if ( p_ProcessInformation->hProcess )
        NtTerminateProcess(p_ProcessInformation->hProcess, *v133);
    }
LABEL_18:
    v149 = 0;
    lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v148);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v128);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v129);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v126);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v125);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v130);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v29);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpValue);
    v30 = hMem;
    hMem = 0;
    if ( v30 )
      LocalFree(v30);
    goto LABEL_285;
  }
  lpEnvironment = 0;
  v166 = 0;
  StartupInfo.cb = 112;
  if ( a5 || a7 )
    a8 = (unsigned __int16 *)&Class;
  StartupInfo.lpDesktop = a8;
  v34 = 0;
  if ( *((_BYTE *)this + 80) != 3 )
    v34 = (WCHAR *)*((_QWORD *)this + 2);
  StartupInfo.wShowWindow = 1;
  v35 = lpMem;
  StartupInfo.lpTitle = v34;
  StartupInfo.dwX = 40;
  StartupInfo.dwY = 40;
  StartupInfo.dwXSize = 80;
  StartupInfo.dwYSize = 40;
  StartupInfo.dwFlags = 128;
  if ( lpMem )
  {
    LastError = GetLastError();
    HeapFree(g_hHeap, 0, v35);
    SetLastError(LastError);
  }
  lpMem = 0;
  LaunchCommandLine = CClassData::GetLaunchCommandLine(this, (unsigned __int16 **)&lpMem);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v32 = 1616;
    goto LABEL_28;
  }
  v135 = 0;
  v37 = 16;
  v38 = 0;
  ProcessExtensions = 0;
  if ( (a6 & 4) == 0 )
  {
    v124 = 0;
    LaunchCommandLine = CToken::HasInheritableSysAppId(v140, &v124);
    LastErrorMsg = LaunchCommandLine;
    if ( LaunchCommandLine < 0 )
    {
      v32 = 1680;
      goto LABEL_28;
    }
    if ( v124 )
    {
      LODWORD(v145) = 0;
      LaunchCommandLine = AppModelPolicy_GetPolicy(*((_QWORD *)v140 + 9), 17, &v145);
      LastErrorMsg = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v32 = 1684;
        goto LABEL_28;
      }
      ProcessExtensions = AppModelPolicyValueToWhichCreateProcessExtensions((unsigned int)v145);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      goto LABEL_71;
    if ( ProcessExtensions == 1 )
    {
      v38 = 1;
    }
    else
    {
      if ( (unsigned int)(ProcessExtensions - 2) <= 1 )
      {
        v38 = 1;
        v135 = 1;
      }
      if ( !ProcessExtensions )
      {
LABEL_71:
        if ( gbSAFERAAAChecksEnabled && *((_QWORD *)this + 7) )
        {
          LaunchCommandLine = CClassData::GetAAASaferToken(this, v140, &hObject);
          LastErrorMsg = LaunchCommandLine;
          if ( LaunchCommandLine < 0 )
          {
            v32 = 1730;
            goto LABEL_28;
          }
          v121 = LaunchCommandLine != 1;
        }
        goto LABEL_76;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpValue,
      0);
    LaunchCommandLine = GetPackageNameFromToken(*((void **)v140 + 9), (unsigned __int16 **)&lpValue);
    LastErrorMsg = LaunchCommandLine;
    if ( LaunchCommandLine < 0 )
    {
      v32 = 1713;
      goto LABEL_28;
    }
    if ( (unsigned int)(ProcessExtensions - 1) <= 2 )
      v37 = 20;
    goto LABEL_71;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    if ( *((_BYTE *)this + 172) )
    {
      SessionId = CToken::GetSessionId(v140);
      LaunchCommandLine = GetAaaAsUserTokenForPackagedRegistration(v140, SessionId, &hObject);
      LastErrorMsg = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v32 = 1634;
        goto LABEL_28;
      }
      v124 = 0;
      LaunchCommandLine = GetTokenHasInheritableSysAppId(hObject, &v124);
      LastErrorMsg = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v32 = 1642;
        goto LABEL_28;
      }
      if ( v124 )
      {
        LODWORD(v145) = 0;
        LaunchCommandLine = AppModelPolicy_GetPolicy(hObject, 17, &v145);
        LastErrorMsg = LaunchCommandLine;
        if ( LaunchCommandLine < 0 )
        {
          v32 = 1647;
          goto LABEL_28;
        }
        ProcessExtensions = AppModelPolicyValueToWhichCreateProcessExtensions((unsigned int)v145);
      }
    }
    else
    {
      v41 = CToken::GetSessionId(v140);
      LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v140, v42, 0, v41, 1, &hObject);
      LastErrorMsg = LaunchCommandLine;
      if ( LaunchCommandLine < 0 )
      {
        v32 = 1659;
        goto LABEL_28;
      }
    }
  }
  else
  {
    v43 = CToken::GetSessionId(v140);
    LaunchCommandLine = GetInteractiveUserTokenForCallerRequest(v140, v44, 0, v43, 1, &hObject);
    LastErrorMsg = LaunchCommandLine;
    if ( LaunchCommandLine < 0 )
    {
      v32 = 1670;
      goto LABEL_28;
    }
  }
  v121 = 1;
LABEL_76:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    goto LABEL_87;
  if ( ProcessExtensions == 1 )
  {
    v38 = 1;
  }
  else
  {
    if ( (unsigned int)(ProcessExtensions - 2) <= 1 )
    {
      v38 = 1;
      v135 = 1;
    }
    if ( !ProcessExtensions )
      goto LABEL_87;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpValue,
    0);
  LaunchCommandLine = GetPackageNameFromToken(*((void **)v140 + 9), (unsigned __int16 **)&lpValue);
  LastErrorMsg = LaunchCommandLine;
  if ( LaunchCommandLine < 0 )
  {
    v32 = 1767;
    goto LABEL_28;
  }
  if ( (unsigned int)(ProcessExtensions - 1) <= 2 )
    v37 |= 4u;
LABEL_87:
  v45 = -1;
  v158[0] = 0;
  v46 = *((_QWORD *)this + 11);
  if ( v46 && *(_DWORD *)(v46 + 76) != -1 )
  {
    if ( *(_DWORD *)(v46 + 76) != 2 )
    {
      LastErrorMsg = -2147024809;
      v52 = 1790;
      v51 = 2147942487LL;
      goto LABEL_98;
    }
    v15 = 1;
    v158[0] = 2;
  }
  if ( !hObject )
  {
    hObject = (HANDLE)*((_QWORD *)v140 + 9);
    v121 = 0;
  }
  if ( (CClassData::AppIDFlags(this) & 0x8000) != 0 )
  {
    v165 = v47;
    v48 = (__int64 *)*((_QWORD *)this + 8);
    v138.Data1 = -463841586;
    *(_DWORD *)&v138.Data2 = 1173371292;
    *(_DWORD *)v138.Data4 = -1430294626;
    *(_DWORD *)&v138.Data4[4] = 527514829;
    if ( v48 )
    {
      v49 = *v48;
      LODWORD(v145) = (_DWORD)v47;
      v50 = (*(__int64 (__fastcall **)(__int64 *, struct _PROC_THREAD_ATTRIBUTE_LIST **))(v49 + 40))(v48, &v165);
      LastErrorMsg = v50;
      if ( v50 < 0 )
      {
        v51 = (unsigned int)v50;
        v52 = 1815;
        goto LABEL_98;
      }
      TokenILValue = CToken::GetTokenILValue(v140, (unsigned int *)&v145);
      v47 = 0;
      LastErrorMsg = TokenILValue;
      if ( TokenILValue < 0 )
      {
        v51 = (unsigned int)TokenILValue;
        v52 = 1816;
LABEL_98:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v52,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)v51,
          (int)cbSize);
        CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
        if ( v134 )
        {
          v134 = 0;
          v53 = *(_QWORD *)p_Buf2 - *(_QWORD *)&GUID_NULL.Data1;
          if ( *(_QWORD *)p_Buf2 == *(_QWORD *)&GUID_NULL.Data1 )
            v53 = *((_QWORD *)p_Buf2 + 1) - *(_QWORD *)GUID_NULL.Data4;
          if ( v53 )
          {
            v138 = *(struct _GUID *)p_Buf2;
            CSCMProfileCache::ReleaseProfile(p_Buf2, &v138);
          }
          if ( p_ProcessInformation->hProcess )
            NtTerminateProcess(p_ProcessInformation->hProcess, *v133);
        }
        goto LABEL_18;
      }
      if ( v165 )
      {
        v55 = *(_QWORD *)v165 - *(_QWORD *)&v138.Data1;
        if ( *(_QWORD *)v165 == *(_QWORD *)&v138.Data1 )
          v55 = *((_QWORD *)v165 + 1) - *(_QWORD *)v138.Data4;
        if ( !v55 && (_DWORD)v145 == 0x2000 )
        {
          v145 = 0;
          MediumRaisedCredUIToken = GetMediumRaisedCredUIToken(hObject, &v145);
          v47 = 0;
          LastErrorMsg = MediumRaisedCredUIToken;
          if ( MediumRaisedCredUIToken < 0 )
          {
            v57 = (unsigned int)MediumRaisedCredUIToken;
            v58 = 1821;
            goto LABEL_115;
          }
          v61 = v145;
          if ( v145 )
          {
            if ( v121 )
            {
              CloseHandle(hObject);
              v47 = 0;
            }
            hObject = v61;
            v121 = 1;
          }
        }
      }
    }
  }
  p_hMem = &hMem;
  v62 = (int)v47;
  v170 = v47;
  v63 = (int)v47;
  v171 = 1;
  LOBYTE(v63) = v135 != (char)v47;
  LOBYTE(v62) = v38 != 0;
  LastErrorMsg = InitializeAttributeList(v139 + (unsigned int)v15 + v62 + v63, v172, &v170);
  if ( v171 )
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      p_hMem,
      v170);
  if ( LastErrorMsg < 0 )
  {
    v57 = (unsigned int)LastErrorMsg;
    v58 = 1868;
LABEL_115:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)v57,
      (int)cbSize);
    CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
    if ( v134 )
    {
      v134 = 0;
      v59 = *(_QWORD *)p_Buf2 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)p_Buf2 == *(_QWORD *)&GUID_NULL.Data1 )
        v59 = *((_QWORD *)p_Buf2 + 1) - *(_QWORD *)GUID_NULL.Data4;
      if ( v59 )
      {
        v138 = *(struct _GUID *)p_Buf2;
        CSCMProfileCache::ReleaseProfile(p_Buf2, &v138);
      }
      if ( p_ProcessInformation->hProcess )
        NtTerminateProcess(p_ProcessInformation->hProcess, *v133);
    }
LABEL_122:
    v149 = 0;
LABEL_123:
    lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v148);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v128);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v129);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v126);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v125);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v130);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v60);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpValue);
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &hMem,
      0);
LABEL_285:
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpMem);
    return (unsigned int)LastErrorMsg;
  }
  Value = 4;
  if ( v38 )
  {
    do
      ++v45;
    while ( *((_WORD *)lpValue + v45) );
    if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20008u, lpValue, 2 * v45, 0, 0) )
    {
      v65 = 1877;
LABEL_136:
      v66 = "Failed to add attribute (DCOMLaunch)";
      goto LABEL_137;
    }
  }
  if ( v135 && !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x20012u, &Value, 4u, 0, 0) )
  {
    v65 = 1883;
    goto LABEL_136;
  }
  if ( v139
    && !UpdateProcThreadAttribute(
          (LPPROC_THREAD_ATTRIBUTE_LIST)hMem,
          0,
          0x20007u,
          *(PVOID *)(((*((_QWORD *)this + 11) + 80LL) & -(__int64)(*((_QWORD *)this + 11) != 0)) + 8),
          *(unsigned int *)((*((_QWORD *)this + 11) + 80LL) & -(__int64)(*((_QWORD *)this + 11) != 0)),
          0,
          0) )
  {
    v65 = 1890;
    goto LABEL_136;
  }
  if ( v15 )
  {
    if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)hMem, 0, 0x2000Bu, v158, 4u, 0, 0) )
    {
      v66 = "Failed to add attribute (PROC_THREAD_ATTRIBUTE_PROTECTION_LEVEL)";
      v65 = 1896;
LABEL_137:
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)v65,
                       (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                       v66,
                       cbSize);
      CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
      if ( v134 )
      {
        v134 = 0;
        v67 = *(_QWORD *)p_Buf2 - *(_QWORD *)&GUID_NULL.Data1;
        if ( *(_QWORD *)p_Buf2 == *(_QWORD *)&GUID_NULL.Data1 )
          v67 = *((_QWORD *)p_Buf2 + 1) - *(_QWORD *)GUID_NULL.Data4;
        if ( v67 )
        {
          v138 = *(struct _GUID *)p_Buf2;
          CSCMProfileCache::ReleaseProfile(p_Buf2, &v138);
        }
        if ( p_ProcessInformation->hProcess )
          NtTerminateProcess(p_ProcessInformation->hProcess, *v133);
      }
LABEL_144:
      v149 = 0;
      goto LABEL_123;
    }
    v37 |= 0x40000u;
  }
  if ( hMem )
  {
    v37 |= 0x80000u;
    v185 = hMem;
  }
  v144 = 0;
  if ( (a6 & 0x20) != 0 )
  {
    if ( v167 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v68 = CreateEnvBlock(&v144, hObject, 0);
    LastErrorMsg = v68;
    if ( v68 < 0 )
    {
      v69 = 1918;
LABEL_162:
      v70 = (unsigned int)v68;
LABEL_163:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v69,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v70,
        (int)cbSize);
      goto LABEL_164;
    }
    v71 = v144;
  }
  else if ( (*((_DWORD *)this + 12) || (a6 & 1) != 0) && !v164 )
  {
    v68 = CSCMProfileCache::GetOrLoadProfile(v64, hObject, &Buf2, &v166);
    LastErrorMsg = v68;
    if ( v68 < 0 )
    {
      v69 = 1930;
      goto LABEL_162;
    }
    v71 = v166;
  }
  else
  {
    v72 = v167;
    if ( v167 )
    {
      v68 = CClassData::AddAppPathsToEnv(this, v167, v151, &v168);
      LastErrorMsg = v68;
      if ( v68 < 0 )
      {
        v69 = 1941;
        goto LABEL_162;
      }
      v71 = v168;
      if ( v72 != v168 )
        v136 = 1;
    }
    else
    {
      v71 = v156;
    }
  }
  v73 = v126;
  if ( v126 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v156);
    LocalFree(v73);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v156);
  }
  v74 = v125;
  v126 = 0;
  if ( v125 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v156);
    LocalFree(v74);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v156);
  }
  v75 = (const unsigned __int16 *)lpMem;
  v125 = 0;
  if ( *((_QWORD *)this + 5) )
    v75 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  DebuggerInfo = GetDebuggerInfo(
                   *((HANDLE *)v140 + 9),
                   (char *)v140 + 156,
                   0,
                   0,
                   v137,
                   v75,
                   (unsigned __int16 **)&v125,
                   (unsigned __int16 **)&v126);
  if ( DebuggerInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79F,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)DebuggerInfo,
      (int)cbSize);
  v77 = v125 != 0;
  v78 = (unsigned int)(ProcessExtensions - 1);
  if ( ProcessExtensions == 1 )
  {
    if ( v125 || !lpValue )
    {
      *v162 = v77;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v128,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v129,
        0);
      v79 = v162;
      LastErrorMsg = PrepareUWPActivation(
                       (unsigned __int16 *)lpValue,
                       (char *)v140 + 156,
                       (unsigned __int16 **)&v129,
                       (unsigned __int16 **)&v128,
                       v162);
      if ( LastErrorMsg < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7AE,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)LastErrorMsg,
          (int)cbSize);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v144);
        CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
        if ( v134 )
        {
          v134 = 0;
          lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
        }
        goto LABEL_122;
      }
      if ( *v79 )
      {
        if ( v129 )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v125,
            &v129);
        if ( v128 )
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v126,
            &v128);
      }
    }
  }
  else
  {
    v78 = (unsigned int)(ProcessExtensions - 2);
    if ( (unsigned int)v78 <= 1 )
    {
      v178[0] = hObject;
      v178[2] = lpValue;
      v178[1] = 0;
      v178[3] = *((_QWORD *)this + 5);
      v179 = 3;
      if ( ProcessExtensions == 3 )
        LODWORD(v179) = 11;
      v68 = PrepareDesktopAppXActivation(v178, &v155);
      LastErrorMsg = v68;
      if ( v68 < 0 )
      {
        v69 = 2002;
        goto LABEL_162;
      }
      v78 = *(unsigned int *)(v155 + 16);
      *v162 = v78;
    }
  }
  if ( !v126 || !v71 )
  {
    v83 = v71;
    lpEnvironment = v71;
    goto LABEL_241;
  }
  LastErrorMsg = CClassData::AddDebugEnvironmentBlock((CClassData *)v78, v71, (unsigned __int16 *)v126, &lpEnvironment);
  if ( LastErrorMsg >= 0 )
  {
    v83 = lpEnvironment;
    if ( v71 != lpEnvironment )
    {
      if ( v136 )
      {
        HeapFree(g_hHeap, 0, v71);
        v83 = lpEnvironment;
      }
      v136 = 1;
    }
LABEL_241:
    if ( v83 )
      v37 |= 0x400u;
    if ( !ImpersonateLoggedOnUser(hObject) )
    {
      LastErrorMsg = -2147024891;
      v80 = 2041;
      goto LABEL_209;
    }
    v84 = 0;
    v137 = 1;
    if ( !v157 )
    {
      if ( v154 )
      {
        v85 = 0x1FFFFF;
        v86 = 0;
      }
      else
      {
        v85 = 0;
        v86 = 0x1FFFFF;
      }
      LODWORD(cbSize) = 0;
      v84 = (void *)CAccessInfo::IdentifyAccess(v189, v154 != 0 ? 3 : 0, v85, v86);
      if ( !v84 )
      {
        LastErrorMsg = -2147024882;
        v69 = 2050;
        v70 = 2147942414LL;
        goto LABEL_163;
      }
    }
    string = 0;
    v87 = *(void (__fastcall **)(CClassData *, HSTRING *))(*(_QWORD *)this + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v87(this, &string);
    ProcessAttributes.nLength = 24;
    ProcessAttributes.lpSecurityDescriptor = v84;
    ProcessAttributes.bInheritHandle = 0;
    v147[0] = 0;
    v88 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v147);
    if ( (unsigned int)DuplicateTokenAsPrimary(hObject, (char *)v140 + 156, v154, v88) )
    {
      if ( v121 )
        CloseHandle(hObject);
      hObject = v147[0];
      v147[0] = 0;
      p_string = &string;
      v181 = &a9;
      v182 = &v140;
      p_lpMem = &lpMem;
      v121 = 1;
      wil::ThreadFailureCallback__lambda_c01fa74e41f372f7dee1c77ec2d22326___((struct wil::details::IFailureCallback *)v186);
      CClassData::FireAAMCreateProcessEvent(this, a10, hObject, 0);
      if ( !CreateProcessAsUserW(
              hObject,
              *((LPCWSTR *)this + 5),
              (LPWSTR)lpMem,
              &ProcessAttributes,
              0,
              0,
              v37,
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
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v187);
LABEL_256:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v147);
        WindowsDeleteString(string);
        string = 0;
LABEL_164:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v144);
        CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
        if ( v134 )
        {
          v134 = 0;
          lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
        }
        goto LABEL_144;
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v187);
    }
    RevertToSelf();
    v137 = 0;
    v89 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v127);
    if ( !OpenProcessToken(ProcessInformation.hProcess, 8u, v89) )
    {
      v90 = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs("rpcss.dll", v90, 0);
      v91 = GetLastError();
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x82F,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v91,
        (unsigned int)cbSize);
    }
    v150 = 0;
    if ( (char *)v127 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded((__int64 *)this, v127, (__int64)&v150);
      LastErrorMsg = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x837,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)ActivationActivityIfNeeded,
          (int)cbSize);
        wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
          &v150,
          0);
        if ( (unsigned __int64)v147[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v147[0]);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_210;
      }
    }
    if ( ProcessExtensions )
    {
      v93 = ProcessExtensions - 1;
      if ( v93 )
      {
        if ( (unsigned int)(v93 - 1) <= 1 )
        {
          *(_DWORD *)(v155 + 40) = v37;
          v94 = PostCreateProcessDesktopAppXActivation(hObject, v155, &ProcessInformation);
          LastErrorMsg = v94;
          if ( v94 < 0 )
          {
            v95 = 2131;
LABEL_277:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v95,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
              (const char *)(unsigned int)v94,
              (int)cbSize);
            goto LABEL_278;
          }
          v96 = NtResumeThread(ProcessInformation.hThread, 0);
          if ( v96 < 0 )
          {
            LastErrorMsg = wil::details::in1diag3::Return_NtStatus(
                             retaddr,
                             (void *)0x854,
                             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                             (const char *)(unsigned int)v96,
                             (int)cbSize);
LABEL_278:
            wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
              &v150,
              0);
            goto LABEL_256;
          }
        }
      }
      else
      {
        v97 = string;
        v98 = CClassData::IdentityType(this);
        v100 = CClassData::AppUserModelID(v99);
        v101 = CClassData::ExecutionPackageName(this);
        v102 = *((_QWORD *)this + 7);
        v103 = v101;
        v104 = v125;
        v105 = a9;
        v106 = CToken::GetSessionId(v140);
        LastErrorMsg = PostCreateProcessUWPActivation(
                         v140,
                         *((unsigned int *)v173 + 33),
                         0,
                         v106,
                         v105,
                         0,
                         v104,
                         v102,
                         v103,
                         v100,
                         v98,
                         v97,
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
          goto LABEL_278;
        }
      }
    }
    else if ( v77 )
    {
      v151 = *((_DWORD *)this + 33);
      CClassData::IdentityType(this);
      CClassData::AppUserModelID(v107);
      CClassData::ExecutionPackageName(this);
      v108 = (int)v125;
      v109 = a9;
      v110 = CToken::GetSessionId(v140);
      LODWORD(cbSize) = v108;
      v94 = LaunchDebugger(v140, v110, v109, 0);
      LastErrorMsg = v94;
      if ( v94 < 0 )
      {
        v95 = 2118;
        goto LABEL_277;
      }
    }
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v150,
      0);
    if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v138 = Buf2;
      if ( CSCMProfileCache::ReleaseProfileOnProcessExit(v111, ProcessInformation.hProcess, &v138) )
      {
        v138 = Buf2;
        CSCMProfileCache::ReleaseProfile(v112, &v138);
        _InterlockedIncrement((volatile signed __int32 *)&gdwRudeProfileUnloads);
        Buf2 = GUID_NULL;
      }
    }
    hProcess = ProcessInformation.hProcess;
    dwProcessId = ProcessInformation.dwProcessId;
    hThread = ProcessInformation.hThread;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    *v174 = hProcess;
    v116 = v127;
    v127 = 0;
    *v175 = v116;
    *v176 = dwProcessId;
    CloseHandle(hThread);
    v134 = 0;
    wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
      &v150,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v147);
    WindowsDeleteString(string);
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v144);
    CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
    if ( v134 )
    {
      v134 = 0;
      lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
    }
    v149 = 0;
    lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v148);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v128);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v129);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v126);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v125);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v130);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v117);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&lpValue);
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &hMem,
      0);
    LastErrorMsg = 0;
    goto LABEL_285;
  }
  v80 = 2014;
LABEL_209:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v80,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)(unsigned int)LastErrorMsg,
    (int)cbSize);
LABEL_210:
  if ( v144 )
    DestroyEnvBlock();
  CAccessInfo::~CAccessInfo((CAccessInfo *)v189);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v160);
  if ( v134 )
  {
    v134 = 0;
    lambda_b479cf06d19fcf8f6338c277465ad4ea_::operator()(&p_Buf2);
  }
  v149 = 0;
  lambda_69eaeb91df0df7ca551aab9922b40790_::operator()(v148);
  if ( (char *)v127 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v127);
  if ( v128 )
    LocalFree(v128);
  if ( v129 )
    LocalFree(v129);
  if ( v126 )
    LocalFree(v126);
  if ( v125 )
    LocalFree(v125);
  if ( v130 )
    LocalFree(v130);
  if ( ProcessInformation.hProcess )
    wil::details::CloseHandle((wil::details *)ProcessInformation.hProcess, v81);
  if ( ProcessInformation.hThread )
    wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v81);
  if ( lpValue )
    HeapFree(g_hHeap, 0, lpValue);
  v82 = hMem;
  hMem = 0;
  if ( v82 )
    LocalFree(v82);
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x1800507c0  push    rbp
0x1800507c2  push    rbx
0x1800507c3  push    rsi
0x1800507c4  push    rdi
0x1800507c5  push    r12
0x1800507c7  push    r13
0x1800507c9  push    r14
0x1800507cb  push    r15
0x1800507cd  lea     rbp, [rsp-398h]
0x1800507d5  sub     rsp, 498h
0x1800507dc  mov     rax, cs:__security_cookie
0x1800507e3  xor     rax, rsp
0x1800507e6  mov     [rbp+3D0h+var_50], rax
0x1800507ed  mov     rax, [rbp+3D0h+arg_50]
0x1800507f4  xor     r12d, r12d
0x1800507f7  mov     rdi, [rbp+3D0h+arg_58]
0x1800507fe  mov     rsi, rcx
0x180050801  mov     r14, [rbp+3D0h+arg_60]
0x180050808  mov     r15, [rbp+3D0h+arg_68]
0x18005080f  mov     rbx, [rbp+3D0h+arg_70]
0x180050816  mov     [rbp+3D0h+var_280], r8
0x18005081d  lea     r8d, [r12+68h]; Size
0x180050822  mov     [rbp+3D0h+var_250], rcx
0x180050829  lea     rcx, [rbp+3D0h+StartupInfo.lpReserved]; void *
0x180050830  mov     [rbp+3D0h+var_3C8], rdx
0x180050834  xor     edx, edx; Val
0x180050836  mov     [rbp+3D0h+var_318], r9d
0x18005083d  mov     [rbp+3D0h+var_258], rax
0x180050844  mov     [rbp+3D0h+var_248], rdi
0x18005084b  mov     [rbp+3D0h+var_240], r14
0x180050852  mov     [rbp+3D0h+var_238], r15
0x180050859  mov     [rbp+3D0h+var_2A0], rbx
0x180050860  mov     [rbp+3D0h+lpMem], r12
0x180050864  mov     qword ptr [rbp+3D0h+StartupInfo.cb], r12
0x18005086b  call    memset_0
0x180050870  mov     eax, r12d
0x180050873  mov     [rsp+4D0h+hMem], r12
0x180050878  mov     qword ptr [rbp+3D0h+ProcessInformation.dwProcessId], rax
0x18005087c  lea     rdx, [rbp+3D0h+var_2E0]; struct wil::details::IFailureCallback *
0x180050883  mov     qword ptr [rbp+3D0h+ProcessAttributes.bInheritHandle], rax
0x18005088a  lea     rcx, [rbp+3D0h+var_2D8]; this
0x180050891  mov     [rbp+3D0h+var_2F8], rax
0x180050898  xorps   xmm0, xmm0
0x18005089b  mov     [rbp+3D0h+var_278], rax
0x1800508a2  xorps   xmm1, xmm1
0x1800508a5  movups  xmmword ptr [rbp+3D0h+ProcessInformation.hProcess], xmm0
0x1800508a9  mov     [rbp+3D0h+lpValue], r12
0x1800508ad  lea     rax, [rbp+3D0h+var_3EF]
0x1800508b1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800508b8  mov     [rbp+3D0h+var_370], rax
0x1800508bc  lea     rax, [rbp+3D0h+var_310]
0x1800508c3  mov     [rbp+3D0h+var_368], rax
0x1800508c7  lea     rax, [rbp+3D0h+hObject]
0x1800508cb  mov     [rbp+3D0h+var_360], rax
0x1800508cf  lea     rax, [rsp+4D0h+var_460]
0x1800508d4  mov     [rbp+3D0h+var_358], rax
0x1800508d8  lea     rax, [rbp+3D0h+var_300]
0x1800508df  mov     [rbp+3D0h+var_350], rax
0x1800508e6  lea     rax, [rbp+3D0h+var_314]
0x1800508ed  mov     [rbp+3D0h+var_348], rax
0x1800508f4  lea     rax, [rbp+3D0h+var_3EE]
0x1800508f8  mov     [rbp+3D0h+var_310], r12
0x1800508ff  movups  xmmword ptr [rbp+3D0h+ProcessAttributes.nLength], xmm1
0x180050906  mov     [rbp+3D0h+hObject], r12
0x18005090a  mov     [rsp+4D0h+var_460], r12b
0x18005090f  movdqu  [rbp+3D0h+Buf2], xmm0
0x180050917  mov     [rbp+3D0h+var_3EF], r12b
0x18005091b  mov     [rbp+3D0h+var_418], r12
0x18005091f  mov     [rbp+3D0h+var_440], r12
0x180050923  mov     [rbp+3D0h+var_438], r12
0x180050927  mov     [rbp+3D0h+var_420], r12
0x18005092b  mov     [rbp+3D0h+var_428], r12
0x18005092f  mov     [rbp+3D0h+var_300], r12
0x180050936  mov     [rbp+3D0h+var_3EE], r12b
0x18005093a  mov     [rbp+3D0h+var_430], r12
0x18005093e  mov     [rdi], r12
0x180050941  lea     edi, [r12+1]
0x180050946  mov     [r14], r12
0x180050949  mov     [r15], r12d
0x18005094c  mov     [rbx], r12d
0x18005094f  mov     [rbp+3D0h+var_338], rax
0x180050956  lea     rax, [rbp+3D0h+Buf2]
0x18005095d  mov     [rbp+3D0h+var_410], rax
0x180050961  lea     rax, [rbp+3D0h+ProcessInformation]
0x180050965  mov     [rbp+3D0h+var_408], rax
0x180050969  lea     rax, [rbp+3D0h+var_314]
0x180050970  mov     [rbp+3D0h+var_400], rax
0x180050974  lea     rax, off_18010ECB0
0x18005097b  mov     [rbp+3D0h+var_2E0], rax
0x180050982  mov     [rbp+3D0h+var_2F0], r12d
0x180050989  mov     [rbp+3D0h+var_3D0], r12b
0x18005098d  mov     [rbp+3D0h+var_314], r12d
0x180050994  mov     [rbp+3D0h+var_340], rsi
0x18005099b  mov     [rbp+3D0h+var_3F8], dil
0x18005099f  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800509a4  lea     rax, [rbp+3D0h+var_314]
0x1800509ab  mov     [rbp+3D0h+var_2A8], rax
0x1800509b2  mov     rax, [rsi+58h]
0x1800509b6  lea     rcx, [rax+50h]
0x1800509ba  neg     rax
0x1800509bd  sbb     rdx, rdx
0x1800509c0  and     rdx, rcx
0x1800509c3  jz      short loc_1800509CD
0x1800509c5  cmp     [rdx+8], r12
0x1800509c9  setnz   [rbp+3D0h+var_3D0]
0x1800509cd  cmp     [rbp+3D0h+var_3C8], r12
0x1800509d1  jnz     short loc_1800509E2
0x1800509d3  mov     ebx, 80070005h
0x1800509d8  mov     edx, 614h
0x1800509dd  mov     r9d, ebx
0x1800509e0  jmp     short loc_180050A29
0x1800509e2  mov     r14d, dword ptr [rbp+3D0h+arg_28]
0x1800509e9  and     r14d, 4
0x1800509ed  mov     [rbp+3D0h+var_294], r14d
0x1800509f4  jz      loc_180050B2C
0x1800509fa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180050a01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180050a06  mov     rdx, [rbp+3D0h+var_3C8]; struct CToken *
0x180050a0a  test    al, al
0x180050a0c  jz      loc_180050B11
0x180050a12  call    ?PrivilegedLaunchIsActivateAsIUAllowed@CClassData@@QEAAJPEAVCToken@@@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowed(CToken *)
0x180050a17  mov     ebx, eax
0x180050a19  test    eax, eax
0x180050a1b  jns     loc_180050B2C
0x180050a21  mov     edx, 61Ah; void *
0x180050a26  mov     r9d, eax; char *
0x180050a29  mov     rcx, [rbp+3D8h]; this
0x180050a30  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180050a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050a3c  lea     rcx, [rbp+3D0h+var_2D8]; this
0x180050a43  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180050a48  cmp     [rbp+3D0h+var_3F8], r12b
0x180050a4c  jz      short loc_180050A9B
0x180050a4e  mov     rcx, [rbp+3D0h+var_410]; this
0x180050a52  mov     [rbp+3D0h+var_3F8], r12b
0x180050a56  mov     rax, [rcx]
0x180050a59  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180050a60  jnz     short loc_180050A6D
0x180050a62  mov     rax, [rcx+8]
0x180050a66  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180050a6d  test    rax, rax
0x180050a70  jz      short loc_180050A83
0x180050a72  movups  xmm0, xmmword ptr [rcx]
0x180050a75  lea     rdx, [rbp+3D0h+var_3E0]; struct _GUID
0x180050a79  movdqu  xmmword ptr [rbp+3D0h+var_3E0.Data1], xmm0
0x180050a7e  call    ?ReleaseProfile@CSCMProfileCache@@QEAAJU_GUID@@@Z; CSCMProfileCache::ReleaseProfile(_GUID)
0x180050a83  mov     rax, [rbp+3D0h+var_408]
0x180050a87  mov     rcx, [rax]; ProcessHandle
0x180050a8a  test    rcx, rcx
0x180050a8d  jz      short loc_180050A9B
0x180050a8f  mov     rdx, [rbp+3D0h+var_400]
0x180050a93  mov     edx, [rdx]; ExitStatus
0x180050a95  call    cs:__imp_NtTerminateProcess
0x180050a9b  lea     rcx, [rbp+3D0h+var_370]
0x180050a9f  mov     [rbp+3D0h+var_330], r12b
0x180050aa6  call    _lambda_69eaeb91df0df7ca551aab9922b40790___operator__
0x180050aab  lea     rcx, [rbp+3D0h+var_430]
0x180050aaf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050ab4  lea     rcx, [rbp+3D0h+var_428]
0x180050ab8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050abd  lea     rcx, [rbp+3D0h+var_420]
0x180050ac1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050ac6  lea     rcx, [rbp+3D0h+var_438]
0x180050aca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050acf  lea     rcx, [rbp+3D0h+var_440]
0x180050ad3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050ad8  lea     rcx, [rbp+3D0h+var_418]
0x180050adc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050ae1  lea     rcx, [rbp+3D0h+ProcessInformation]; this
0x180050ae5  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180050aea  lea     rcx, [rbp+3D0h+lpValue]
0x180050aee  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@PEAVCClientOxid@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(void)
0x180050af3  mov     rcx, [rsp+4D0h+hMem]; hMem
0x180050af8  mov     [rsp+4D0h+hMem], r12
0x180050afd  test    rcx, rcx
0x180050b00  jz      loc_180052070
0x180050b06  call    cs:__imp_LocalFree
0x180050b0c  jmp     loc_180052070
0x180050b11  xor     r8d, r8d; int
0x180050b14  mov     rcx, rsi; this
0x180050b17  call    ?PrivilegedLaunchIsActivateAsIUAllowedOld@CClassData@@QEAAJPEAVCToken@@H@Z; CClassData::PrivilegedLaunchIsActivateAsIUAllowedOld(CToken *,int)
0x180050b1c  mov     ebx, eax
0x180050b1e  test    eax, eax
0x180050b20  jns     short loc_180050B2C
0x180050b22  mov     edx, 61Eh
0x180050b27  jmp     loc_180050A26
0x180050b2c  mov     rcx, rsi; this
0x180050b2f  mov     [rbp+3D0h+var_308], r12d
0x180050b36  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x180050b3b  test    al, 2
0x180050b3d  jz      short loc_180050B71
0x180050b3f  xor     edx, edx
0x180050b41  lea     rcx, [rbp+3D0h+var_418]
0x180050b45  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180050b4a  mov     rcx, [rbp+3D0h+var_3C8]
0x180050b4e  lea     rdx, [rbp+3D0h+var_418]; void **
0x180050b52  mov     rcx, [rcx+48h]; TokenHandle
0x180050b56  call    ?GetLogonIDSid@CToken@@SAJPEAXPEAPEAX@Z; CToken::GetLogonIDSid(void *,void * *)
0x180050b5b  mov     ebx, eax
0x180050b5d  test    eax, eax
0x180050b5f  jns     short loc_180050B6B
0x180050b61  mov     edx, 624h
0x180050b66  jmp     loc_180050A26
0x180050b6b  mov     [rbp+3D0h+var_308], edi
0x180050b71  mov     rcx, [rbp+3D0h+var_3C8]
0x180050b75  lea     r8, [rbp+3D0h+var_2F0]; int *
0x180050b7c  xorps   xmm0, xmm0
0x180050b7f  xorps   xmm1, xmm1
0x180050b82  movdqa  [rbp+3D0h+var_E0], xmm0
0x180050b8a  mov     edx, 1Dh; enum _TOKEN_INFORMATION_CLASS
0x180050b8f  movdqa  [rbp+3D0h+var_D0], xmm1
0x180050b97  lea     rax, [rcx+9Ch]
0x180050b9e  mov     [rbp+3D0h+var_F0], rax
0x180050ba5  mov     rax, [rbp+3D0h+var_418]
0x180050ba9  mov     [rbp+3D0h+var_E8], rax
0x180050bb0  mov     rcx, [rcx+48h]; void *
0x180050bb4  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180050bb9  mov     ebx, eax
0x180050bbb  test    eax, eax
0x180050bbd  jns     short loc_180050BEB
0x180050bbf  mov     edx, 62Ah; void *
0x180050bc4  mov     rcx, [rbp+3D8h]; this
0x180050bcb  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180050bd2  mov     r9d, eax; char *
0x180050bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050bda  lea     rcx, [rbp+3D0h+var_F0]; this
0x180050be1  call    ??1CAccessInfo@@QEAA@XZ; CAccessInfo::~CAccessInfo(void)
0x180050be6  jmp     loc_180050A3C
0x180050beb  mov     [rbp+3D0h+var_310], r12
0x180050bf2  mov     [rbp+3D0h+var_288], r12
0x180050bf9  mov     [rbp+3D0h+StartupInfo.cb], 70h ; 'p'
0x180050c03  cmp     [rbp+3D0h+arg_20], r12d
0x180050c0a  jnz     short loc_180050C1C
0x180050c0c  mov     rax, [rbp+3D0h+arg_38]
0x180050c13  cmp     [rbp+3D0h+arg_30], r12d
0x180050c1a  jz      short loc_180050C23
0x180050c1c  lea     rax, Class
0x180050c23  mov     [rbp+3D0h+StartupInfo.lpDesktop], rax
0x180050c2a  mov     rax, r12
0x180050c2d  cmp     byte ptr [rsi+50h], 3
0x180050c31  jz      short loc_180050C37
0x180050c33  mov     rax, [rsi+10h]
0x180050c37  mov     [rbp+3D0h+StartupInfo.wShowWindow], di
0x180050c3e  mov     rdi, [rbp+3D0h+lpMem]
0x180050c42  mov     [rbp+3D0h+StartupInfo.lpTitle], rax
0x180050c49  mov     eax, 28h ; '('
0x180050c4e  mov     [rbp+3D0h+StartupInfo.dwX], eax
0x180050c54  mov     [rbp+3D0h+StartupInfo.dwY], eax
0x180050c5a  mov     [rbp+3D0h+StartupInfo.dwXSize], 50h ; 'P'
0x180050c64  mov     [rbp+3D0h+StartupInfo.dwYSize], eax
0x180050c6a  mov     [rbp+3D0h+StartupInfo.dwFlags], 80h
0x180050c74  test    rdi, rdi
0x180050c77  jz      short loc_180050C9B
0x180050c79  call    cs:__imp_GetLastError
0x180050c7f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180050c86  mov     r8, rdi; lpMem
0x180050c89  xor     edx, edx; dwFlags
0x180050c8b  mov     ebx, eax
0x180050c8d  call    cs:__imp_HeapFree
0x180050c93  mov     ecx, ebx; dwErrCode
0x180050c95  call    cs:__imp_SetLastError
0x180050c9b  lea     rdx, [rbp+3D0h+lpMem]; unsigned __int16 **
0x180050c9f  mov     [rbp+3D0h+lpMem], r12
0x180050ca3  mov     rcx, rsi; this
0x180050ca6  call    ?GetLaunchCommandLine@CClassData@@AEAAJPEAPEAG@Z; CClassData::GetLaunchCommandLine(ushort * *)
0x180050cab  mov     ebx, eax
0x180050cad  test    eax, eax
0x180050caf  jns     short loc_180050CBB
0x180050cb1  mov     edx, 650h
0x180050cb6  jmp     loc_180050BC4
0x180050cbb  mov     [rbp+3D0h+var_3F0], r12b
0x180050cbf  mov     r15d, 10h
0x180050cc5  mov     r13b, r12b
0x180050cc8  mov     edi, r12d
0x180050ccb  test    r14d, r14d
0x180050cce  jz      loc_180050DE2
0x180050cd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180050cdb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180050ce0  mov     rcx, [rbp+3D0h+var_3C8]; this
0x180050ce4  test    al, al
0x180050ce6  jz      loc_180050DB0
0x180050cec  cmp     [rsi+0ACh], r12b
0x180050cf3  jz      loc_180050D7E
0x180050cf9  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x180050cfe  mov     rcx, [rbp+3D0h+var_3C8]; this
0x180050d02  lea     r8, [rbp+3D0h+hObject]; void **
0x180050d06  mov     edx, eax; unsigned int
0x180050d08  call    ?GetAaaAsUserTokenForPackagedRegistration@@YAJPEAVCToken@@KPEAPEAX@Z; GetAaaAsUserTokenForPackagedRegistration(CToken *,ulong,void * *)
0x180050d0d  mov     ebx, eax
0x180050d0f  test    eax, eax
0x180050d11  jns     short loc_180050D1D
0x180050d13  mov     edx, 662h
0x180050d18  jmp     loc_180050BC4
0x180050d1d  mov     rcx, [rbp+3D0h+hObject]; void *
0x180050d21  lea     rdx, [rbp+3D0h+var_448]; bool *
0x180050d25  mov     [rbp+3D0h+var_448], r12b
0x180050d29  call    ?GetTokenHasInheritableSysAppId@@YAJPEAXPEA_N@Z; GetTokenHasInheritableSysAppId(void *,bool *)
0x180050d2e  mov     ebx, eax
0x180050d30  test    eax, eax
0x180050d32  jns     short loc_180050D3E
  ... truncated ...
```
