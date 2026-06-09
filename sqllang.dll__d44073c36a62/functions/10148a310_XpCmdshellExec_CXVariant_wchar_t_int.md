# XpCmdshellExec(CXVariant *,wchar_t *,int)

- ea: `0x10148a310`
- end: `0x10148b4e2`
- name: `?XpCmdshellExec@@YAKPEAVCXVariant@@PEA_WH@Z`
- size: `4562`
- prototype: `unsigned int __fastcall(struct CXVariant *, wchar_t *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10148d480`

## callees

- `0x100401070`
- `0x100401433`
- `0x1004076a0`
- `0x100430d60`
- `0x1005511a0`
- `0x1014894e0`
- `0x1014898e0`
- `0x101489bd0`
- `0x10148a310`

## import_xrefs

- `USERENV!DestroyEnvironmentBlock` at `0x10148ae60`
- `USERENV!DestroyEnvironmentBlock` at `0x10148ae60`
- `USERENV!CreateEnvironmentBlock` at `0x10148ad6b`
- `USERENV!CreateEnvironmentBlock` at `0x10148ad6b`
- `KERNEL32!GetCurrentProcess` at `0x10148a6b1`
- `KERNEL32!GetCurrentProcess` at `0x10148a6ba`
- `KERNEL32!GetCurrentProcess` at `0x10148a6b1`
- `KERNEL32!GetCurrentProcess` at `0x10148a6ba`
- `KERNEL32!GetLastError` at `0x10148a642`
- `KERNEL32!GetLastError` at `0x10148a6f8`
- `KERNEL32!GetLastError` at `0x10148a763`
- `KERNEL32!GetLastError` at `0x10148a7df`
- `KERNEL32!GetLastError` at `0x10148a83c`
- `KERNEL32!GetLastError` at `0x10148a923`
- `KERNEL32!GetLastError` at `0x10148a93d`
- `KERNEL32!GetLastError` at `0x10148a9e7`
- `KERNEL32!GetLastError` at `0x10148aa52`
- `KERNEL32!GetLastError` at `0x10148af24`
- `KERNEL32!GetLastError` at `0x10148b087`
- `KERNEL32!GetLastError` at `0x10148b0a6`
- `KERNEL32!GetLastError` at `0x10148b158`
- `KERNEL32!GetLastError` at `0x10148b392`
- `KERNEL32!GetLastError` at `0x10148a642`
- `KERNEL32!GetLastError` at `0x10148a6f8`
- `KERNEL32!GetLastError` at `0x10148a763`
- `KERNEL32!GetLastError` at `0x10148a7df`
- `KERNEL32!GetLastError` at `0x10148a83c`
- `KERNEL32!GetLastError` at `0x10148a923`
- `KERNEL32!GetLastError` at `0x10148a93d`
- `KERNEL32!GetLastError` at `0x10148a9e7`
- `KERNEL32!GetLastError` at `0x10148aa52`
- `KERNEL32!GetLastError` at `0x10148af24`
- `KERNEL32!GetLastError` at `0x10148b087`
- `KERNEL32!GetLastError` at `0x10148b0a6`
- `KERNEL32!GetLastError` at `0x10148b158`
- `KERNEL32!GetLastError` at `0x10148b392`
- `KERNEL32!CloseHandle` at `0x10148a751`
- `KERNEL32!CloseHandle` at `0x10148a82a`
- `KERNEL32!CloseHandle` at `0x10148ad21`
- `KERNEL32!CloseHandle` at `0x10148af12`
- `KERNEL32!CloseHandle` at `0x10148b3f7`
- `KERNEL32!CloseHandle` at `0x10148b40b`
- `KERNEL32!CloseHandle` at `0x10148b42f`
- `KERNEL32!CloseHandle` at `0x10148b444`
- `KERNEL32!CloseHandle` at `0x10148a751`
- `KERNEL32!CloseHandle` at `0x10148a82a`
- `KERNEL32!CloseHandle` at `0x10148ad21`
- `KERNEL32!CloseHandle` at `0x10148af12`
- `KERNEL32!CloseHandle` at `0x10148b3f7`
- `KERNEL32!CloseHandle` at `0x10148b40b`
- `KERNEL32!CloseHandle` at `0x10148b42f`
- `KERNEL32!CloseHandle` at `0x10148b444`
- `KERNEL32!MultiByteToWideChar` at `0x10148b13d`
- `KERNEL32!MultiByteToWideChar` at `0x10148b13d`
- `KERNEL32!ReadFile` at `0x10148b00c`
- `KERNEL32!ReadFile` at `0x10148b063`
- `KERNEL32!ReadFile` at `0x10148b00c`
- `KERNEL32!ReadFile` at `0x10148b063`
- `KERNEL32!CreateProcessW` at `0x10148ae22`
- `KERNEL32!CreateProcessW` at `0x10148ae22`
- `KERNEL32!GetExitCodeProcess` at `0x10148b380`
- `KERNEL32!GetExitCodeProcess` at `0x10148b380`
- `KERNEL32!DuplicateHandle` at `0x10148a6e6`
- `KERNEL32!DuplicateHandle` at `0x10148a6e6`
- `KERNEL32!CreatePipe` at `0x10148a630`
- `KERNEL32!CreatePipe` at `0x10148a7cd`
- `KERNEL32!CreatePipe` at `0x10148a630`
- `KERNEL32!CreatePipe` at `0x10148a7cd`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10148a919`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10148a9d5`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10148a919`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10148a9d5`
- `KERNEL32!UpdateProcThreadAttribute` at `0x10148aa40`
- `KERNEL32!UpdateProcThreadAttribute` at `0x10148aa40`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x10148aed1`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x10148aed1`
- `ADVAPI32!CreateProcessAsUserW` at `0x10148acde`
- `ADVAPI32!CreateProcessAsUserW` at `0x10148acde`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10148a358`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10148a389`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x10148a390`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x10148a390`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10148aec3`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10148aec3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a3df`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a44a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a66f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a725`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a790`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a805`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a862`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a96a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148aa0d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148aa78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148ac33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148af4a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b0d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b185`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b3bf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a3df`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a44a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a66f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a725`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a790`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a805`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a862`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148a96a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148aa0d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148aa78`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148ac33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148af4a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b0d2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b185`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148b3bf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10148a996`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10148af9c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10148a996`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10148af9c`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10148a53f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10148a53f`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10148a35f`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10148a35f`
- `sqldk!SystemThread_TlsIndex` at `0x10148a3fd`
- `sqldk!SystemThread_TlsIndex` at `0x10148a459`
- `sqldk!SystemThread_TlsIndex` at `0x10148a4fa`
- `sqldk!SystemThread_TlsIndex` at `0x10148a558`
- `sqldk!SystemThread_TlsIndex` at `0x10148aaa4`
- `sqldk!SystemThread_TlsIndex` at `0x10148ae8b`
- `sqldk!SystemThread_TlsIndex` at `0x10148b1b3`
- `sqldk!SystemThread_TlsIndex` at `0x10148b2ad`
- `sqldk!SystemThread_TlsOffset` at `0x10148a406`
- `sqldk!SystemThread_TlsOffset` at `0x10148a462`
- `sqldk!SystemThread_TlsOffset` at `0x10148a503`
- `sqldk!SystemThread_TlsOffset` at `0x10148a561`
- `sqldk!SystemThread_TlsOffset` at `0x10148aaad`
- `sqldk!SystemThread_TlsOffset` at `0x10148ae94`
- `sqldk!SystemThread_TlsOffset` at `0x10148b1bc`
- `sqldk!SystemThread_TlsOffset` at `0x10148b2b6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a47d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a51e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a57c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148aac8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148aead`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148b1d7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148b2d1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a47d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a51e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148a57c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148aac8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148aead`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148b1d7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10148b2d1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148a9ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148afb4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148b3e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148b41a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148a9ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148afb4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148b3e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10148b41a`
- `sqldk!?Unhook@SOS_AutoUnhookDebugBreak@@QEAA?AW4SOS_RESULT@@XZ` at `0x10148ac6d`
- `sqldk!?Unhook@SOS_AutoUnhookDebugBreak@@QEAA?AW4SOS_RESULT@@XZ` at `0x10148adb3`
- `sqldk!?Unhook@SOS_AutoUnhookDebugBreak@@QEAA?AW4SOS_RESULT@@XZ` at `0x10148ac6d`
- `sqldk!?Unhook@SOS_AutoUnhookDebugBreak@@QEAA?AW4SOS_RESULT@@XZ` at `0x10148adb3`
- `sqldk!??1SOS_AutoUnhookDebugBreak@@QEAA@XZ` at `0x10148ad09`
- `sqldk!??1SOS_AutoUnhookDebugBreak@@QEAA@XZ` at `0x10148ae4d`
- `sqldk!??1SOS_AutoUnhookDebugBreak@@QEAA@XZ` at `0x10148ad09`
- `sqldk!??1SOS_AutoUnhookDebugBreak@@QEAA@XZ` at `0x10148ae4d`
- `sqldk!??0SOS_AutoUnhookDebugBreak@@QEAA@W4HookPoint@SOS_DebugBreakHookMgr@@@Z` at `0x10148ac5e`
- `sqldk!??0SOS_AutoUnhookDebugBreak@@QEAA@W4HookPoint@SOS_DebugBreakHookMgr@@@Z` at `0x10148ada4`
- `sqldk!??0SOS_AutoUnhookDebugBreak@@QEAA@W4HookPoint@SOS_DebugBreakHookMgr@@@Z` at `0x10148ac5e`
- `sqldk!??0SOS_AutoUnhookDebugBreak@@QEAA@W4HookPoint@SOS_DebugBreakHookMgr@@@Z` at `0x10148ada4`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10148b105`
- `sqlmin!?AddNewColumn@BackupResultSet@@IEAAXPEB_WW4ColumnType@BackupColumn@@I@Z` at `0x10148b105`
- `sqlmin!??0BackupResultSet@@QEAA@PEAVBackupOperation@@KPEAVIMemObj@@@Z` at `0x10148afd3`
- `sqlmin!??0BackupResultSet@@QEAA@PEAVBackupOperation@@KPEAVIMemObj@@@Z` at `0x10148afd3`
- `sqlmin!??1BackupResultSet@@QEAA@XZ` at `0x10148b3d4`
- `sqlmin!??1BackupResultSet@@QEAA@XZ` at `0x10148b3d4`
- `sqlmin!?GetBlankRow@BackupResultSet@@UEAAPEAVBackupResultSetRow@@XZ` at `0x10148b113`
- `sqlmin!?GetBlankRow@BackupResultSet@@UEAAPEAVBackupResultSetRow@@XZ` at `0x10148b113`
- `sqlmin!?CompleteAndSendRow@BackupResultSet@@UEAAXPEAVBackupResultSetRow@@@Z` at `0x10148b244`
- `sqlmin!?CompleteAndSendRow@BackupResultSet@@UEAAXPEAVBackupResultSetRow@@@Z` at `0x10148b244`
- `sqlmin!?EndResultSet@BackupResultSet@@QEAAXH@Z` at `0x10148b338`
- `sqlmin!?EndResultSet@BackupResultSet@@QEAAXH@Z` at `0x10148b338`
- `sqlmin!?SetStringColumn@BackupResultSetRow@@QEAAXPEFB_WH@Z` at `0x10148b194`
- `sqlmin!?SetStringColumn@BackupResultSetRow@@QEAAXPEFB_WH@Z` at `0x10148b194`
- `sqlmin!?SetNullColumn@BackupResultSetRow@@QEAAXK@Z` at `0x10148b1a4`
- `sqlmin!?SetNullColumn@BackupResultSetRow@@QEAAXK@Z` at `0x10148b1a4`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10148ab2a`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10148ab2a`
- `sqlmin!GetXdbServerGlobals` at `0x10148a3e5`
- `sqlmin!GetXdbServerGlobals` at `0x10148a3e5`

## string_xrefs

- `0x10148a984`: `sql\ntdbms\msql\security\src\secsp.cpp`
- `0x10148af8d`: `sql\ntdbms\msql\security\src\secsp.cpp`
- `0x10148b0b0`: `ReadFile`
- `0x10148ae2c`: `CreateProcess`
- `0x10148a64c`: `CreatePipe`
- `0x10148a677`: `CreatePipe`
- `0x10148ad75`: `CreateEnvironmentBlock`
- `0x10148ace8`: `CreateProcessAsUser`
- `0x10148a947`: `InitializeProcThreadAttributeList`
- `0x10148a972`: `InitializeProcThreadAttributeList`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall XpCmdshellExec(struct CXVariant *a1, wchar_t *a2, int a3)
{
  struct CXVariant *v3; // r13
  __int64 v4; // rcx
  const wchar_t *OperatingSystemName; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  struct IMemObj *v9; // r12
  int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdx
  wchar_t *v16; // rbx
  void *v17; // r14
  wchar_t *v18; // r15
  HANDLE CurrentProcess; // rbx
  HANDLE v20; // rax
  wchar_t *v21; // rbx
  wchar_t *v22; // rbx
  wchar_t *v23; // rbx
  wchar_t *v24; // rbx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v25; // r14
  wchar_t *v26; // rbx
  wchar_t *v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // rbx
  unsigned int v30; // edi
  __int64 v31; // rcx
  int v32; // r14d
  unsigned __int16 MasterDbId; // ax
  int v34; // r12d
  __int64 *v35; // rcx
  __int64 v36; // rax
  HANDLE v37; // rdi
  const wchar_t *v38; // rbx
  BOOL v39; // eax
  const wchar_t *v40; // rbx
  BOOL v41; // eax
  const wchar_t *v42; // rbx
  BOOL v43; // eax
  const wchar_t *v44; // rbx
  BOOL v45; // eax
  struct IMemObj *v46; // rdi
  __int64 v47; // rbx
  struct Worker *v48; // rcx
  HANDLE v49; // rcx
  wchar_t *v50; // rbx
  struct IMemObj *v51; // r12
  int v52; // r15d
  int v53; // ebx
  __int64 v54; // rdi
  BOOL v55; // r14d
  wchar_t *v56; // rdi
  int v57; // eax
  BackupResultSetRow *BlankRow; // rax
  BackupResultSetRow *v59; // r15
  int v60; // ebx
  wchar_t *v61; // rdi
  __int64 v62; // rdi
  __int64 v63; // rbx
  unsigned int v64; // edi
  __int64 v65; // rcx
  int v66; // r12d
  __int64 *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdi
  __int64 v70; // rbx
  unsigned int v71; // edi
  __int64 v72; // rcx
  __int64 *v73; // rcx
  __int64 v74; // rax
  wchar_t *v75; // rbx
  DWORD v76; // ebx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-4C8h]
  DWORD dwOptions[2]; // [rsp+30h] [rbp-4B8h]
  DWORD dwOptionsa[2]; // [rsp+30h] [rbp-4B8h]
  DWORD dwOptionsb[2]; // [rsp+30h] [rbp-4B8h]
  DWORD dwOptionsc[2]; // [rsp+30h] [rbp-4B8h]
  int lpCommandLinea; // [rsp+C0h] [rbp-428h]
  DWORD NumberOfBytesRead; // [rsp+C8h] [rbp-420h] BYREF
  DWORD ExitCode; // [rsp+CCh] [rbp-41Ch] BYREF
  struct IMemObj *v87; // [rsp+D0h] [rbp-418h]
  LPVOID Environment; // [rsp+D8h] [rbp-410h] BYREF
  HANDLE TargetHandle; // [rsp+E0h] [rbp-408h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+E8h] [rbp-400h]
  struct CXVariant *v91; // [rsp+F0h] [rbp-3F8h]
  int v92; // [rsp+F8h] [rbp-3F0h]
  int v93; // [rsp+FCh] [rbp-3ECh]
  void *hReadPipe; // [rsp+100h] [rbp-3E8h] BYREF
  ULONG_PTR Size; // [rsp+108h] [rbp-3E0h] BYREF
  HANDLE hToken; // [rsp+110h] [rbp-3D8h] BYREF
  void *hWritePipe[2]; // [rsp+118h] [rbp-3D0h] BYREF
  HANDLE hObject; // [rsp+128h] [rbp-3C0h] BYREF
  char v99[8]; // [rsp+130h] [rbp-3B8h] BYREF
  char v100[8]; // [rsp+138h] [rbp-3B0h] BYREF
  HANDLE v101; // [rsp+140h] [rbp-3A8h]
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+148h] [rbp-3A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+160h] [rbp-388h] BYREF
  HANDLE hProcess; // [rsp+178h] [rbp-370h]
  HANDLE hThread; // [rsp+180h] [rbp-368h]
  HANDLE v106; // [rsp+188h] [rbp-360h]
  HANDLE v107; // [rsp+190h] [rbp-358h]
  int *v108; // [rsp+198h] [rbp-350h]
  __int64 v109; // [rsp+1A0h] [rbp-348h]
  int v110; // [rsp+1A8h] [rbp-340h]
  int v111; // [rsp+1ACh] [rbp-33Ch]
  __int64 v112; // [rsp+1B0h] [rbp-338h]
  int v113; // [rsp+1B8h] [rbp-330h]
  int v114; // [rsp+1BCh] [rbp-32Ch]
  __int64 v115; // [rsp+1C0h] [rbp-328h]
  int v116; // [rsp+1C8h] [rbp-320h]
  int v117; // [rsp+1CCh] [rbp-31Ch]
  __int64 v118; // [rsp+1D0h] [rbp-318h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v119; // [rsp+1D8h] [rbp-310h]
  HANDLE v120; // [rsp+1E0h] [rbp-308h]
  int v121; // [rsp+1F0h] [rbp-2F8h] BYREF
  __int64 v122; // [rsp+1F8h] [rbp-2F0h]
  int v123; // [rsp+200h] [rbp-2E8h] BYREF
  int v124; // [rsp+204h] [rbp-2E4h]
  __int64 v125; // [rsp+208h] [rbp-2E0h]
  int v126; // [rsp+210h] [rbp-2D8h] BYREF
  __int64 v127; // [rsp+218h] [rbp-2D0h]
  __int64 v128; // [rsp+220h] [rbp-2C8h]
  __int64 v129; // [rsp+228h] [rbp-2C0h]
  __int64 v130; // [rsp+230h] [rbp-2B8h]
  bool v131; // [rsp+240h] [rbp-2A8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+250h] [rbp-298h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v133; // [rsp+2B8h] [rbp-230h]
  __int64 v134; // [rsp+2C0h] [rbp-228h]
  _BYTE v135[16]; // [rsp+2C8h] [rbp-220h] BYREF
  _BYTE v136[24]; // [rsp+2D8h] [rbp-210h] BYREF
  _BYTE v137[144]; // [rsp+2F0h] [rbp-1F8h] BYREF
  __int128 v138; // [rsp+380h] [rbp-168h] BYREF
  __int64 v139; // [rsp+390h] [rbp-158h]
  CHAR Buffer[256]; // [rsp+3A0h] [rbp-148h] BYREF

  v134 = -2;
  v3 = a1;
  v91 = a1;
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
  {
    v138 = *(_OWORD *)L"xp_cmdshell";
    v139 = *(_QWORD *)L"ell";
    OperatingSystemName = OsInfo::GetOperatingSystemName(SOS_OS_OsInfo);
    v6 = -1;
    do
      ++v6;
    while ( OperatingSystemName[v6] );
    ex_raise(162, 2, 14, 200, 22, &v138, 2 * v6, OperatingSystemName);
  }
  if ( *(_DWORD *)(GetXdbServerGlobals(v4) + 11976)
    && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset)
                             + 72LL)
                 + 270LL)
      & 2) == 0
    && !byte_102EDCD4A )
  {
    ex_raise(405, 14, 16, 45, L"xp_cmdshell");
  }
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v9 = *(struct IMemObj **)(v8 + 1000);
  v87 = v9;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v121, 1);
  lpAttributeList = (LPPROC_THREAD_ATTRIBUTE_LIST)&v123;
  v126 = 536871517;
  v10 = 0;
  v127 = 0;
  v129 = 0;
  v128 = 0;
  v130 = 0;
  v131 = 0;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = *(_QWORD *)(v12 + 600);
  if ( v13 )
    v131 = (unsigned int)SOS_Task::PushWait(v13, &v126) == 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v125 = v15;
  v124 = (*(_DWORD *)(v15 + 800) >> 11) & 1;
  if ( v124 || (*(_BYTE *)(v15 + 800) & 4) == 0 )
  {
    v123 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 608) + 8LL))(*(_QWORD *)(v15 + 608));
  }
  else
  {
    v123 = 0;
  }
  *(_QWORD *)&PipeAttributes.nLength = 24;
  *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
  PipeAttributes.lpSecurityDescriptor = 0;
  *(__m128i *)hWritePipe = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  hReadPipe = (void *)-1LL;
  v16 = off_102ED13A0;
  if ( !CreatePipe(&hReadPipe, hWritePipe, &PipeAttributes, 0) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptions[0] = GetLastError();
    ex_raise(151, 21, 16, 1, v16, L"CreatePipe", *(_QWORD *)dwOptions);
  }
  v17 = hReadPipe;
  v109 = (__int64)hReadPipe;
  v101 = hWritePipe[0];
  TargetHandle = (HANDLE)-1LL;
  v18 = off_102ED13A0;
  CurrentProcess = GetCurrentProcess();
  v20 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, hReadPipe, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 2, v18, L"DuplicateHandle", *(_QWORD *)dwOptionsa);
  }
  v107 = TargetHandle;
  v109 = -1;
  v21 = off_102ED13A0;
  if ( !CloseHandle(v17) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 3, v21, L"CloseHandle", *(_QWORD *)dwOptionsa);
  }
  hObject = (HANDLE)-1LL;
  v22 = off_102ED13A0;
  if ( !CreatePipe(&hWritePipe[1], &hObject, &PipeAttributes, 0) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 4, v22, L"CreatePipe", *(_QWORD *)dwOptionsa);
  }
  v106 = hWritePipe[1];
  v23 = off_102ED13A0;
  if ( !CloseHandle(hObject) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 5, v23, L"CloseHandle", *(_QWORD *)dwOptionsa);
  }
  *(_OWORD *)&StartupInfo.cb = 0;
  memset(&StartupInfo.lpTitle, 0, 56);
  v133 = 0;
  StartupInfo.cb = 112;
  StartupInfo.dwFlags = 257;
  StartupInfo.wShowWindow = 0;
  StartupInfo.hStdOutput = hWritePipe[0];
  StartupInfo.hStdError = hWritePipe[0];
  StartupInfo.hStdInput = hWritePipe[1];
  StartupInfo.lpDesktop = (LPWSTR)&szPassword;
  v119 = 0;
  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
  {
    v24 = off_102ED13A0;
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 6, v24, L"InitializeProcThreadAttributeList", *(_QWORD *)dwOptionsa);
  }
  v25 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](
                                                Size,
                                                v9,
                                                "sql\\ntdbms\\msql\\security\\src\\secsp.cpp",
                                                653,
                                                3u);
  lpAttributeList = v25;
  if ( v25 )
    operator delete[](0);
  v119 = v25;
  v26 = off_102ED13A0;
  if ( !InitializeProcThreadAttributeList(v25, 1u, 0, &Size) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsa[0] = GetLastError();
    ex_raise(151, 21, 16, 7, v26, L"InitializeProcThreadAttributeList", *(_QWORD *)dwOptionsa);
  }
  v27 = off_102ED13A0;
  if ( !UpdateProcThreadAttribute(v25, 0, 0x20002u, hWritePipe, 0x10u, 0, 0) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsb[0] = GetLastError();
    ex_raise(151, 21, 16, 7, v27, L"InitializeProcThreadAttributeList", *(_QWORD *)dwOptionsb);
  }
  v133 = v25;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v29 = *(_QWORD *)(v28 + 256);
  if ( !v29 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v29 = *(_QWORD *)(v28 + 256);
  }
  v112 = v29;
  v30 = *(_DWORD *)(v29 + 800);
  v111 = (v30 >> 11) & 1;
  if ( (v30 & 4) != 0 && (v31 = *(_QWORD *)(v29 + 608)) != 0 )
  {
    v32 = 1;
    v110 = 1;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v31 + 16LL))(v31, v29, 1);
  }
  else
  {
    v32 = 0;
    v110 = 0;
  }
  MasterDbId = GetMasterDbId();
  v34 = (unsigned __int8)ISECManager::AccessCheckWithAuditState(0, MasterDbId, 0, 24, 51);
  if ( v32 )
  {
    v35 = *(__int64 **)(v29 + 608);
    v36 = *v35;
    if ( (v30 & 0x800) != 0 )
      (*(void (__fastcall **)(__int64 *, __int64))(v36 + 24))(v35, v29);
    else
      (*(void (__fastcall **)(__int64 *, __int64))(v36 + 8))(v35, v29);
  }
  try
  {
    if ( v34 )
    {
      Environment = 0;
      if ( (unsigned int)FIsRunningAsLocalSystem(v3) )
      {
        v42 = off_102ED13A0;
        v43 = CreateEnvironmentBlock(&Environment, 0, 1);
        CheckReturnValue(v42, v3, 20, L"CreateEnvironmentBlock", v43);
      }
      else
      {
        Environment = 0;
      }
      SOS_AutoUnhookDebugBreak::SOS_AutoUnhookDebugBreak(v100, 1);
      SOS_AutoUnhookDebugBreak::Unhook(v100);
      v93 = 525312;
      v44 = off_102ED13A0;
      v45 = CreateProcessW(0, a2, 0, 0, 1, 0x80400u, Environment, 0, &StartupInfo, &ProcessInformation);
      CheckReturnValue(v44, v3, 21, L"CreateProcess", v45);
      SOS_AutoUnhookDebugBreak::~SOS_AutoUnhookDebugBreak((SOS_AutoUnhookDebugBreak *)v100);
      if ( Environment )
        DestroyEnvironmentBlock(Environment);
    }
    else
    {
      hToken = 0;
      if ( !(unsigned int)LogonAsXpCmdshellCredential(v3, &hToken) )
      {
        *((_DWORD *)v3 + 2) = 15153;
        dwDesiredAccess[0] = 58;
        ex_raise(151, 53, 16, 1, *(_QWORD *)dwDesiredAccess, L"##xp_cmdshell_proxy_account##");
      }
      v37 = hToken;
      v108 = (int *)hToken;
      v120 = hToken;
      SOS_AutoUnhookDebugBreak::SOS_AutoUnhookDebugBreak(v99, 1);
      SOS_AutoUnhookDebugBreak::Unhook(v99);
      v92 = 524304;
      v38 = off_102ED13A0;
      v39 = CreateProcessAsUserW(hToken, 0, a2, 0, 0, 1, 0x80010u, 0, 0, &StartupInfo, &ProcessInformation);
      CheckReturnValue(v38, v3, 10, L"CreateProcessAsUser", v39);
      SOS_AutoUnhookDebugBreak::~SOS_AutoUnhookDebugBreak((SOS_AutoUnhookDebugBreak *)v99);
      v120 = 0;
      v40 = off_102ED13A0;
      v41 = CloseHandle(v37);
      CheckReturnValue(v40, v3, 11, L"CloseHandle", v41);
    }
  }
  catch ( SQLError v136 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v135, (const struct SQLError *)v136);
      DeleteProcThreadAttributeList(lpAttributeList);
      ExceptionPassOn((const struct SQLError *)v136);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v135);
    }
    catch ( ShortStackException )
    {
    }
    v10 = 0;
    v3 = v91;
  }
  v46 = v87;
  v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v48 = *(struct Worker **)(v47 + 256);
  if ( !v48 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v48 = *(struct Worker **)(v47 + 256);
  }
  if ( *((_DWORD *)v48 + 139) )
    ExceptionPostCatchActions(v48);
  DeleteProcThreadAttributeList(lpAttributeList);
  hThread = ProcessInformation.hThread;
  hProcess = ProcessInformation.hProcess;
  v49 = v101;
  v101 = (HANDLE)-1LL;
  v50 = off_102ED13A0;
  if ( !CloseHandle(v49) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsc[0] = GetLastError();
    ex_raise(151, 21, 16, 30, v50, L"CloseHandle", *(_QWORD *)dwOptionsc);
  }
  memset_0(Buffer, 0, 0xFFu);
  v91 = 0;
  v51 = 0;
  v87 = 0;
  if ( a3 )
  {
    v51 = (struct IMemObj *)operator new[](0x1FEu, v46, "sql\\ntdbms\\msql\\security\\src\\secsp.cpp", 849, 3u);
    v87 = v51;
    if ( v51 )
      operator delete[](0);
    v91 = v51;
  }
  BackupResultSet::BackupResultSet((BackupResultSet *)v137, 0, 1u, 0);
  v52 = 0;
  lpCommandLinea = 0;
  do
  {
    v53 = 0;
    v54 = 0;
    v55 = ReadFile(TargetHandle, Buffer, 1u, &NumberOfBytesRead, 0);
    if ( v55 )
    {
      while ( Buffer[v54] != 10 )
      {
        ++v53;
        ++v54;
        if ( v53 >= 255 )
          goto LABEL_80;
        _mm_lfence();
        v55 = ReadFile(TargetHandle, &Buffer[v53], 1u, &NumberOfBytesRead, 0);
        if ( !v55 )
          goto LABEL_78;
      }
      if ( v53 && Buffer[v54 - 1] == 13 )
        --v53;
    }
    else
    {
LABEL_78:
      if ( GetLastError() != 109 )
      {
        v56 = off_102ED13A0;
        *((_DWORD *)v3 + 2) = 15121;
        dwOptionsc[0] = GetLastError();
        ex_raise(151, 21, 16, 40, v56, L"ReadFile", *(_QWORD *)dwOptionsc);
      }
    }
LABEL_80:
    v57 = a3;
    if ( a3 )
    {
      if ( !v52 )
        BackupResultSet::AddNewColumn(v137, L"output", 13, 510);
      BlankRow = BackupResultSet::GetBlankRow((BackupResultSet *)v137);
      v59 = BlankRow;
      if ( v53 )
      {
        v60 = 2 * MultiByteToWideChar(1u, 0, Buffer, v53, (LPWSTR)v51, 255);
        v61 = off_102ED13A0;
        if ( !v60 )
        {
          *((_DWORD *)v3 + 2) = 15121;
          dwOptionsc[0] = GetLastError();
          ex_raise(151, 21, 16, 41, v61, L"MultiByteToWideChar", *(_QWORD *)dwOptionsc);
        }
        BackupResultSetRow::SetStringColumn(v59, (const wchar_t *)v51, v60);
      }
      else
      {
        BackupResultSetRow::SetNullColumn(BlankRow, 1u);
      }
      v62 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v63 = *(_QWORD *)(v62 + 256);
      if ( !v63 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v63 = *(_QWORD *)(v62 + 256);
      }
      v115 = v63;
      v64 = *(_DWORD *)(v63 + 800);
      v114 = (v64 >> 11) & 1;
      if ( (v64 & 4) != 0 && (v65 = *(_QWORD *)(v63 + 608)) != 0 )
      {
        v66 = 1;
        v113 = 1;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v65 + 16LL))(v65, v63, 1);
      }
      else
      {
        v66 = 0;
        v113 = 0;
      }
      BackupResultSet::CompleteAndSendRow((BackupResultSet *)v137, v59);
      if ( v66 )
      {
        v67 = *(__int64 **)(v63 + 608);
        v68 = *v67;
        if ( (v64 & 0x800) != 0 )
          (*(void (__fastcall **)(__int64 *, __int64))(v68 + 24))(v67, v63);
        else
          (*(void (__fastcall **)(__int64 *, __int64))(v68 + 8))(v67, v63);
      }
      v57 = a3;
    }
    ++lpCommandLinea;
    if ( !v55 )
      break;
    v52 = lpCommandLinea;
    v51 = v87;
  }
  while ( NumberOfBytesRead );
  if ( v57 )
  {
    v69 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v70 = *(_QWORD *)(v69 + 256);
    if ( !v70 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v70 = *(_QWORD *)(v69 + 256);
    }
    v118 = v70;
    v71 = *(_DWORD *)(v70 + 800);
    v117 = (v71 >> 11) & 1;
    if ( (v71 & 4) != 0 && (v72 = *(_QWORD *)(v70 + 608)) != 0 )
    {
      v10 = 1;
      v116 = 1;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v72 + 16LL))(v72, v70, 1);
    }
    else
    {
      v116 = 0;
    }
    BackupResultSet::EndResultSet((BackupResultSet *)v137, 0);
    if ( v10 )
    {
      v73 = *(__int64 **)(v70 + 608);
      v74 = *v73;
      if ( (v71 & 0x800) != 0 )
        (*(void (__fastcall **)(__int64 *, __int64))(v74 + 24))(v73, v70);
      else
        (*(void (__fastcall **)(__int64 *, __int64))(v74 + 8))(v73, v70);
    }
  }
  ExitCode = 1;
  v75 = off_102ED13A0;
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
    *((_DWORD *)v3 + 2) = 15121;
    dwOptionsc[0] = GetLastError();
    ex_raise(151, 21, 16, 50, v75, L"GetExitCodeProcess", *(_QWORD *)dwOptionsc);
  }
  v76 = ExitCode;
  BackupResultSet::~BackupResultSet((BackupResultSet *)v137);
  operator delete[](v91);
  if ( hProcess )
    CloseHandle(hProcess);
  if ( hThread )
    CloseHandle(hThread);
  operator delete[](lpAttributeList);
  if ( v106 != (HANDLE)-1LL )
    CloseHandle(v106);
  if ( v107 != (HANDLE)-1LL )
    CloseHandle(v107);
  v108 = &v123;
  if ( v123 )
  {
    if ( v124 )
      *(_DWORD *)(v125 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v125 + 608) + 16LL))(
        *(_QWORD *)(v125 + 608),
        v125,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v126);
  *(_DWORD *)(v122 + 616) &= ~v121;
  return v76;
}

```

## disassembly

```asm
0x10148a310  mov     [rsp+arg_10], r8d
0x10148a315  push    rbx
0x10148a316  push    rsi
0x10148a317  push    rdi
0x10148a318  push    r12
0x10148a31a  push    r13
0x10148a31c  push    r14
0x10148a31e  push    r15
0x10148a320  sub     rsp, 4B0h
0x10148a327  mov     [rsp+4E8h+var_228], 0FFFFFFFFFFFFFFFEh
0x10148a333  mov     rax, cs:__security_cookie
0x10148a33a  xor     rax, rsp
0x10148a33d  mov     [rsp+4E8h+var_48], rax
0x10148a345  mov     [rsp+4E8h+lpCommandLine], rdx
0x10148a34d  mov     r13, rcx
0x10148a350  mov     [rsp+4E8h+var_3F8], rcx
0x10148a358  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10148a35f  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x10148a365  test    al, al
0x10148a367  jz      short loc_10148A3E5
0x10148a369  movups  xmm0, xmmword ptr cs:aXpCmdshell; "xp_cmdshell"
0x10148a370  movups  [rsp+4E8h+var_168], xmm0
0x10148a378  movsd   xmm1, qword ptr cs:aXpCmdshell+10h; "ell"
0x10148a380  movsd   [rsp+4E8h+var_158], xmm1
0x10148a389  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10148a390  call    cs:__imp_?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ; OsInfo::GetOperatingSystemName(void)
0x10148a396  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10148a39d  nop     dword ptr [rax]
0x10148a3a0  inc     rcx
0x10148a3a3  cmp     word ptr [rax+rcx*2], 0
0x10148a3a8  jnz     short loc_10148A3A0
0x10148a3aa  add     rcx, rcx
0x10148a3ad  mov     [rsp+4E8h+lpEnvironment], rax
0x10148a3b2  mov     qword ptr [rsp+4E8h+dwOptions], rcx
0x10148a3b7  lea     rax, [rsp+4E8h+var_168]
0x10148a3bf  mov     qword ptr [rsp+4E8h+bInheritHandle], rax
0x10148a3c4  mov     qword ptr [rsp+4E8h+dwDesiredAccess], 16h
0x10148a3cd  mov     edx, 2
0x10148a3d2  mov     ecx, 0A2h
0x10148a3d7  lea     r9d, [rcx+26h]
0x10148a3db  lea     r8d, [rdx+0Ch]
0x10148a3df  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a3e5  call    cs:__imp_GetXdbServerGlobals
0x10148a3eb  cmp     dword ptr [rax+2EC8h], 0
0x10148a3f2  jz      short loc_10148A450
0x10148a3f4  mov     rdx, gs:58h
0x10148a3fd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10148a404  mov     ecx, [rax]
0x10148a406  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10148a40d  mov     eax, [rax]
0x10148a40f  add     rax, [rdx+rcx*8]
0x10148a413  mov     rax, [rax]
0x10148a416  mov     rcx, [rax+48h]
0x10148a41a  test    byte ptr [rcx+10Eh], 2
0x10148a421  jnz     short loc_10148A450
0x10148a423  cmp     cs:byte_102EDCD4A, 0
0x10148a42a  jnz     short loc_10148A450
0x10148a42c  lea     rax, aXpCmdshell; "xp_cmdshell"
0x10148a433  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rax
0x10148a438  mov     edx, 0Eh
0x10148a43d  mov     ecx, 195h
0x10148a442  lea     r9d, [rdx+1Fh]
0x10148a446  lea     r8d, [rdx+2]
0x10148a44a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a450  mov     rdx, gs:58h
0x10148a459  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10148a460  mov     ecx, [rax]
0x10148a462  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10148a469  mov     ebx, [rax]
0x10148a46b  add     rbx, [rdx+rcx*8]
0x10148a46f  mov     rax, [rbx+100h]
0x10148a476  test    rax, rax
0x10148a479  jnz     short loc_10148A48A
0x10148a47b  xor     ecx, ecx
0x10148a47d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10148a483  mov     rax, [rbx+100h]
0x10148a48a  mov     r12, [rax+3E8h]
0x10148a491  mov     [rsp+4E8h+var_418], r12
0x10148a499  mov     edx, 1
0x10148a49e  lea     rcx, [rsp+4E8h+var_2F8]
0x10148a4a6  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10148a4ab  nop
0x10148a4ac  lea     rax, [rsp+4E8h+var_2E8]
0x10148a4b4  mov     [rsp+4E8h+lpAttributeList], rax
0x10148a4bc  mov     [rsp+4E8h+var_2D8], 2000025Dh
0x10148a4c7  xor     esi, esi
0x10148a4c9  mov     [rsp+4E8h+var_2D0], rsi
0x10148a4d1  mov     [rsp+4E8h+var_2C0], rsi
0x10148a4d9  mov     [rsp+4E8h+var_2C8], rsi
0x10148a4e1  mov     [rsp+4E8h+var_2B8], rsi
0x10148a4e9  mov     [rsp+4E8h+var_2A8], sil
0x10148a4f1  mov     rdx, gs:58h
0x10148a4fa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10148a501  mov     ecx, [rax]
0x10148a503  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10148a50a  mov     ebx, [rax]
0x10148a50c  add     rbx, [rdx+rcx*8]
0x10148a510  mov     rax, [rbx+100h]
0x10148a517  test    rax, rax
0x10148a51a  jnz     short loc_10148A52B
0x10148a51c  xor     ecx, ecx
0x10148a51e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10148a524  mov     rax, [rbx+100h]
0x10148a52b  mov     rcx, [rax+258h]
0x10148a532  test    rcx, rcx
0x10148a535  jz      short loc_10148A54F
0x10148a537  lea     rdx, [rsp+4E8h+var_2D8]
0x10148a53f  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10148a545  test    eax, eax
0x10148a547  setz    [rsp+4E8h+var_2A8]
0x10148a54f  mov     rdx, gs:58h
0x10148a558  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10148a55f  mov     ecx, [rax]
0x10148a561  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10148a568  mov     ebx, [rax]
0x10148a56a  add     rbx, [rdx+rcx*8]
0x10148a56e  mov     rdx, [rbx+100h]
0x10148a575  test    rdx, rdx
0x10148a578  jnz     short loc_10148A589
0x10148a57a  xor     ecx, ecx
0x10148a57c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10148a582  mov     rdx, [rbx+100h]
0x10148a589  mov     [rsp+4E8h+var_2E0], rdx
0x10148a591  mov     eax, [rdx+320h]
0x10148a597  shr     eax, 0Bh
0x10148a59a  and     eax, 1
0x10148a59d  mov     [rsp+4E8h+var_2E4], eax
0x10148a5a4  jnz     short loc_10148A5B8
0x10148a5a6  test    byte ptr [rdx+320h], 4
0x10148a5ad  jz      short loc_10148A5B8
0x10148a5af  mov     [rsp+4E8h+var_2E8], esi
0x10148a5b6  jmp     short loc_10148A5D1
0x10148a5b8  mov     [rsp+4E8h+var_2E8], 1
0x10148a5c3  mov     rcx, [rdx+260h]
0x10148a5ca  mov     rax, [rcx]
0x10148a5cd  call    qword ptr [rax+8]
0x10148a5d0  nop
0x10148a5d1  mov     qword ptr [rsp+4E8h+PipeAttributes.nLength], 18h
0x10148a5dd  mov     qword ptr [rsp+4E8h+PipeAttributes.bInheritHandle], 1
0x10148a5e9  mov     [rsp+4E8h+PipeAttributes.lpSecurityDescriptor], rsi
0x10148a5f1  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x10148a5f9  movdqu  xmmword ptr [rsp+4E8h+hWritePipe], xmm0
0x10148a602  mov     [rsp+4E8h+hReadPipe], 0FFFFFFFFFFFFFFFFh
0x10148a60e  mov     rbx, cs:off_102ED13A0; "xp_cmdshell"
0x10148a615  xor     r9d, r9d; nSize
0x10148a618  lea     r8, [rsp+4E8h+PipeAttributes]; lpPipeAttributes
0x10148a620  lea     rdx, [rsp+4E8h+hWritePipe]; hWritePipe
0x10148a628  lea     rcx, [rsp+4E8h+hReadPipe]; hReadPipe
0x10148a630  call    cs:__imp_CreatePipe
0x10148a636  test    eax, eax
0x10148a638  jnz     short loc_10148A677
0x10148a63a  mov     dword ptr [r13+8], 3B11h
0x10148a642  call    cs:__imp_GetLastError
0x10148a648  mov     [rsp+4E8h+dwOptions], eax
0x10148a64c  lea     rdi, aCreatepipe; "CreatePipe"
0x10148a653  mov     qword ptr [rsp+4E8h+bInheritHandle], rdi
0x10148a658  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rbx
0x10148a65d  mov     edx, 15h
0x10148a662  mov     ecx, 97h
0x10148a667  lea     r9d, [rdx-14h]
0x10148a66b  lea     r8d, [rdx-5]
0x10148a66f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a675  jmp     short loc_10148A67E
0x10148a677  lea     rdi, aCreatepipe; "CreatePipe"
0x10148a67e  mov     r14, [rsp+4E8h+hReadPipe]
0x10148a686  mov     [rsp+4E8h+var_348], r14
0x10148a68e  mov     rax, [rsp+4E8h+hWritePipe]
0x10148a696  mov     [rsp+4E8h+var_3A8], rax
0x10148a69e  mov     [rsp+4E8h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x10148a6aa  mov     r15, cs:off_102ED13A0; "xp_cmdshell"
0x10148a6b1  call    cs:__imp_GetCurrentProcess
0x10148a6b7  mov     rbx, rax
0x10148a6ba  call    cs:__imp_GetCurrentProcess
0x10148a6c0  mov     rcx, rax; hSourceProcessHandle
0x10148a6c3  mov     [rsp+4E8h+dwOptions], 2; dwOptions
0x10148a6cb  mov     [rsp+4E8h+bInheritHandle], esi; bInheritHandle
0x10148a6cf  mov     [rsp+4E8h+dwDesiredAccess], esi; dwDesiredAccess
0x10148a6d3  lea     r9, [rsp+4E8h+TargetHandle]; lpTargetHandle
0x10148a6db  mov     r8, rbx; hTargetProcessHandle
0x10148a6de  mov     rdx, [rsp+4E8h+hReadPipe]; hSourceHandle
0x10148a6e6  call    cs:__imp_DuplicateHandle
0x10148a6ec  test    eax, eax
0x10148a6ee  jnz     short loc_10148A72B
0x10148a6f0  mov     dword ptr [r13+8], 3B11h
0x10148a6f8  call    cs:__imp_GetLastError
0x10148a6fe  mov     [rsp+4E8h+dwOptions], eax
0x10148a702  lea     rax, aDuplicatehandl; "DuplicateHandle"
0x10148a709  mov     qword ptr [rsp+4E8h+bInheritHandle], rax
0x10148a70e  mov     qword ptr [rsp+4E8h+dwDesiredAccess], r15
0x10148a713  mov     edx, 15h
0x10148a718  mov     ecx, 97h
0x10148a71d  lea     r9d, [rdx-13h]
0x10148a721  lea     r8d, [rdx-5]
0x10148a725  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a72b  mov     rax, [rsp+4E8h+TargetHandle]
0x10148a733  mov     [rsp+4E8h+var_358], rax
0x10148a73b  mov     [rsp+4E8h+var_348], 0FFFFFFFFFFFFFFFFh
0x10148a747  mov     rbx, cs:off_102ED13A0; "xp_cmdshell"
0x10148a74e  mov     rcx, r14; hObject
0x10148a751  call    cs:__imp_CloseHandle
0x10148a757  test    eax, eax
0x10148a759  jnz     short loc_10148A798
0x10148a75b  mov     dword ptr [r13+8], 3B11h
0x10148a763  call    cs:__imp_GetLastError
0x10148a769  mov     [rsp+4E8h+dwOptions], eax
0x10148a76d  lea     r15, aClosehandle; "CloseHandle"
0x10148a774  mov     qword ptr [rsp+4E8h+bInheritHandle], r15
0x10148a779  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rbx
0x10148a77e  mov     edx, 15h
0x10148a783  mov     ecx, 97h
0x10148a788  lea     r9d, [rdx-12h]
0x10148a78c  lea     r8d, [rdx-5]
0x10148a790  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a796  jmp     short loc_10148A79F
0x10148a798  lea     r15, aClosehandle; "CloseHandle"
0x10148a79f  mov     [rsp+4E8h+hObject], 0FFFFFFFFFFFFFFFFh
0x10148a7ab  mov     rbx, cs:off_102ED13A0; "xp_cmdshell"
0x10148a7b2  xor     r9d, r9d; nSize
0x10148a7b5  lea     r8, [rsp+4E8h+PipeAttributes]; lpPipeAttributes
0x10148a7bd  lea     rdx, [rsp+4E8h+hObject]; hWritePipe
0x10148a7c5  lea     rcx, [rsp+4E8h+hWritePipe+8]; hReadPipe
0x10148a7cd  call    cs:__imp_CreatePipe
0x10148a7d3  test    eax, eax
0x10148a7d5  jnz     short loc_10148A80B
0x10148a7d7  mov     dword ptr [r13+8], 3B11h
0x10148a7df  call    cs:__imp_GetLastError
0x10148a7e5  mov     [rsp+4E8h+dwOptions], eax
0x10148a7e9  mov     qword ptr [rsp+4E8h+bInheritHandle], rdi
0x10148a7ee  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rbx
0x10148a7f3  mov     edx, 15h
0x10148a7f8  mov     ecx, 97h
0x10148a7fd  lea     r9d, [rdx-11h]
0x10148a801  lea     r8d, [rdx-5]
0x10148a805  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a80b  mov     rax, [rsp+4E8h+hWritePipe+8]
0x10148a813  mov     [rsp+4E8h+var_360], rax
0x10148a81b  mov     rbx, cs:off_102ED13A0; "xp_cmdshell"
0x10148a822  mov     rcx, [rsp+4E8h+hObject]; hObject
0x10148a82a  call    cs:__imp_CloseHandle
0x10148a830  test    eax, eax
0x10148a832  jnz     short loc_10148A868
0x10148a834  mov     dword ptr [r13+8], 3B11h
0x10148a83c  call    cs:__imp_GetLastError
0x10148a842  mov     [rsp+4E8h+dwOptions], eax
0x10148a846  mov     qword ptr [rsp+4E8h+bInheritHandle], r15
0x10148a84b  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rbx
0x10148a850  mov     edx, 15h
0x10148a855  mov     ecx, 97h
0x10148a85a  lea     r9d, [rdx-10h]
0x10148a85e  lea     r8d, [rdx-5]
0x10148a862  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a868  xorps   xmm0, xmm0
0x10148a86b  movups  xmmword ptr [rsp+4E8h+StartupInfo.cb], xmm0
0x10148a873  movups  xmmword ptr [rsp+4E8h+StartupInfo.lpDesktop], xmm0
0x10148a87b  movups  xmmword ptr [rsp+4E8h+StartupInfo.dwX], xmm0
0x10148a883  movups  xmmword ptr [rsp+4E8h+StartupInfo.dwXCountChars], xmm0
0x10148a88b  movups  xmmword ptr [rsp+4E8h+StartupInfo.wShowWindow], xmm0
0x10148a893  movups  xmmword ptr [rsp+4E8h+StartupInfo.hStdInput], xmm0
0x10148a89b  movups  xmmword ptr [rsp+4E8h+StartupInfo.hStdError], xmm0
0x10148a8a3  mov     [rsp+4E8h+StartupInfo.cb], 70h ; 'p'
0x10148a8ae  mov     [rsp+4E8h+StartupInfo.dwFlags], 101h
0x10148a8b9  mov     [rsp+4E8h+StartupInfo.wShowWindow], si
0x10148a8c1  mov     rax, [rsp+4E8h+hWritePipe]
0x10148a8c9  mov     [rsp+4E8h+StartupInfo.hStdOutput], rax
0x10148a8d1  mov     [rsp+4E8h+StartupInfo.hStdError], rax
0x10148a8d9  mov     rax, [rsp+4E8h+hWritePipe+8]
0x10148a8e1  mov     [rsp+4E8h+StartupInfo.hStdInput], rax
0x10148a8e9  lea     rax, szPassword
0x10148a8f0  mov     [rsp+4E8h+StartupInfo.lpDesktop], rax
0x10148a8f8  mov     [rsp+4E8h+var_310], rsi
0x10148a900  mov     [rsp+4E8h+Size], rsi
0x10148a908  lea     r9, [rsp+4E8h+Size]; lpSize
0x10148a910  xor     r8d, r8d; dwFlags
0x10148a913  lea     edx, [r8+1]; dwAttributeCount
0x10148a917  xor     ecx, ecx; lpAttributeList
0x10148a919  call    cs:__imp_InitializeProcThreadAttributeList
0x10148a91f  test    eax, eax
0x10148a921  jnz     short loc_10148A972
0x10148a923  call    cs:__imp_GetLastError
0x10148a929  cmp     eax, 7Ah ; 'z'
0x10148a92c  jz      short loc_10148A972
0x10148a92e  mov     rbx, cs:off_102ED13A0; "xp_cmdshell"
0x10148a935  mov     dword ptr [r13+8], 3B11h
0x10148a93d  call    cs:__imp_GetLastError
0x10148a943  mov     [rsp+4E8h+dwOptions], eax
0x10148a947  lea     rdi, aInitializeproc; "InitializeProcThreadAttributeList"
0x10148a94e  mov     qword ptr [rsp+4E8h+bInheritHandle], rdi
0x10148a953  mov     qword ptr [rsp+4E8h+dwDesiredAccess], rbx
0x10148a958  mov     edx, 15h
0x10148a95d  mov     ecx, 97h
0x10148a962  lea     r9d, [rdx-0Fh]
0x10148a966  lea     r8d, [rdx-5]
0x10148a96a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10148a970  jmp     short loc_10148A979
0x10148a972  lea     rdi, aInitializeproc; "InitializeProcThreadAttributeList"
0x10148a979  mov     byte ptr [rsp+4E8h+dwDesiredAccess], 3
0x10148a97e  mov     r9d, 28Dh
0x10148a984  lea     r8, aSqlNtdbmsMsqlS_1; "sql\\ntdbms\\msql\\security\\src\\secsp"...
0x10148a98b  mov     rdx, r12
0x10148a98e  mov     rcx, [rsp+4E8h+Size]
  ... truncated ...
```
