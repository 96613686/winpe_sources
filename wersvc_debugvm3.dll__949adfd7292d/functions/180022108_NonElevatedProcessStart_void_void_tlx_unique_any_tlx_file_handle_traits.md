# NonElevatedProcessStart(void *,void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180022108`
- end: `0x180022d4c`
- name: `?NonElevatedProcessStart@@YAJPEAX0PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `3140`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019b34`

## callees

- `0x1800029d0`
- `0x180002a00`
- `0x180002ff0`
- `0x1800035e8`
- `0x180006134`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x180013f54`
- `0x180022108`
- `0x1800300c0`
- `0x180030590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022c41`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002296c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002296c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800228f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800228f2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800225d2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180022bc2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800225d2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180022bc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002233f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002233f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800226fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800226fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002245c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002250d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002245c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002250d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800224f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800224f7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022c36`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022c36`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022819`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180022819`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800223b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800223b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022452`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800224c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800224c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800224d5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800224d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002291d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002291d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002261a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002262b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002263a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002266b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002268d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022606`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002261a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002262b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002263a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002266b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002268d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ca3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022ae3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022b58`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022c68`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022ae3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022b58`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180022c68`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800225f2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800225f2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022a6f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022a6f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022a09`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022a09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022240`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022240`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225e2`
- `profapi!__imp_CreateEnvBlock` at `0x1800227cc`
- `profapi!__imp_CreateEnvBlock` at `0x1800227cc`
- `profapi!__imp_DestroyEnvBlock` at `0x18002227d`
- `profapi!__imp_DestroyEnvBlock` at `0x180022657`
- `profapi!__imp_DestroyEnvBlock` at `0x1800227bb`
- `profapi!__imp_DestroyEnvBlock` at `0x18002227d`
- `profapi!__imp_DestroyEnvBlock` at `0x180022657`
- `profapi!__imp_DestroyEnvBlock` at `0x1800227bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800222c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800222c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NonElevatedProcessStart(HANDLE ProcessHandle, void *a2, void **a3)
{
  int v6; // r14d
  PSID *v7; // r12
  PSECURITY_DESCRIPTOR *v9; // rax
  signed int LastError; // eax
  signed int UserToken; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  void **v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  PSID *v17; // rax
  signed int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  PUCHAR SidSubAuthorityCount; // rax
  signed int v22; // eax
  LPVOID v23; // rcx
  signed int v24; // eax
  BOOL v25; // r12d
  signed int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  DWORD ProcessId; // eax
  HANDLE v30; // rcx
  signed int v31; // eax
  _QWORD *v32; // r12
  signed int v33; // eax
  signed int v34; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v36; // rbx
  signed int v37; // eax
  signed int v38; // eax
  HANDLE v39; // rax
  signed int v40; // eax
  void *v41; // rcx
  signed int v42; // eax
  int v43; // [rsp+60h] [rbp-A0h]
  PSID *v44; // [rsp+68h] [rbp-98h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION hObject; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpEnvironment; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hToken; // [rsp+98h] [rbp-68h]
  HANDLE TokenHandle; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE EventW; // [rsp+B0h] [rbp-50h]
  HANDLE TargetHandle; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE v53; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v54; // [rsp+C8h] [rbp-38h] BYREF
  LPCVOID lpBaseAddress; // [rsp+D0h] [rbp-30h]
  HANDLE v56; // [rsp+D8h] [rbp-28h]
  HANDLE hSourceHandle; // [rsp+E0h] [rbp-20h]
  HANDLE Handles[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v60; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  PSID *v62; // [rsp+120h] [rbp+20h]
  HANDLE v63; // [rsp+128h] [rbp+28h]
  struct _STARTUPINFOW StartupInfo; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Buffer[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR ApplicationName[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  WCHAR CommandLine[264]; // [rsp+5C0h] [rbp+4C0h] BYREF
  WCHAR Name[264]; // [rsp+7D0h] [rbp+6D0h] BYREF

  hSourceHandle = a2;
  v6 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v7 = 0;
  hToken = 0;
  lpEnvironment = 0;
  memset(&hObject, 0, sizeof(hObject));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset_0(Buffer, 0, 0x208u);
  memset_0(ApplicationName, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  memset_0(Name, 0, 0x208u);
  EventW = 0;
  TargetHandle = 0;
  v53 = 0;
  v56 = 0;
  v60 = 0;
  v54 = 0;
  lpBaseAddress = 0;
  v61 = 0;
  *(_OWORD *)Handles = 0;
  hMem = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  if ( (__int64)a2 <= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    memset(&hObject, 0, sizeof(hObject));
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return 2147942487LL;
  }
  v43 = 0;
  v9 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GR;;;WD)(A;OICI;GA;;;SY)", 1u, v9, 0) )
  {
    LastError = GetLastError();
    UserToken = LastError;
    if ( LastError > 0 )
      UserToken = (unsigned __int16)LastError | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 35;
    goto LABEL_63;
  }
  v14 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(ProcessHandle, 8u, v14) )
  {
    v15 = GetLastError();
    UserToken = v15;
    if ( v15 > 0 )
      UserToken = (unsigned __int16)v15 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 36;
    goto LABEL_63;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v16 = GetLastError();
    UserToken = v16;
    if ( v16 > 0 )
      UserToken = (unsigned __int16)v16 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 37;
LABEL_63:
    WPP_SF_d(v12[2], v13, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)UserToken);
LABEL_64:
    v6 = v43;
    goto LABEL_65;
  }
  v17 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v17;
  v44 = v17;
  if ( !v17 )
  {
    v7 = 0;
    UserToken = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, 2147942414LL);
    goto LABEL_65;
  }
  v62 = v17;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v17, TokenInformationLength, &TokenInformationLength) )
  {
    v18 = GetLastError();
    UserToken = v18;
    if ( v18 > 0 )
      UserToken = (unsigned __int16)v18 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v20 = 39;
    goto LABEL_46;
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v7);
  if ( *GetSidSubAuthority(*v7, (unsigned __int8)(*SidSubAuthorityCount - 1)) < 0x2000 )
  {
    UserToken = -2147024891;
LABEL_65:
    if ( hObject.hThread && v6 && hObject.hProcess )
      ResumeThread(hObject.hThread);
    goto LABEL_69;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v63 = EventW;
  if ( (unsigned __int64)EventW + 1 <= 1 )
  {
    v22 = GetLastError();
    UserToken = v22;
    if ( v22 > 0 )
      UserToken = (unsigned __int16)v22 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v20 = 40;
    goto LABEL_46;
  }
  UserToken = UserTokenUtility::GetUserToken(ProcessHandle);
  if ( UserToken == -2147024846 )
  {
    UserToken = UserTokenUtility::GetProcessToken(ProcessHandle);
    if ( UserToken < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_64;
      v13 = 41;
      goto LABEL_63;
    }
  }
  else if ( UserToken < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 42;
    goto LABEL_63;
  }
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    v42 = GetLastError();
    UserToken = v42;
    if ( v42 > 0 )
      UserToken = (unsigned __int16)v42 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v20 = 43;
LABEL_46:
    WPP_SF_d(v19[2], v20, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)UserToken);
    goto LABEL_64;
  }
  UserToken = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\wermgr.exe", Buffer);
  if ( UserToken < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 44;
    goto LABEL_63;
  }
  UserToken = StringCchPrintfW(CommandLine, 0x104u, L"%s -nonelevated", ApplicationName);
  if ( UserToken < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 45;
    goto LABEL_63;
  }
  v23 = lpEnvironment;
  lpEnvironment = 0;
  if ( v23 )
    DestroyEnvBlock();
  UserToken = CreateEnvBlock(&lpEnvironment, hToken, 0);
  if ( UserToken < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v13 = 46;
    goto LABEL_63;
  }
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"winsta0\\default";
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v24 = GetLastError();
    UserToken = v24;
    if ( v24 > 0 )
      UserToken = (unsigned __int16)v24 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v20 = 47;
    goto LABEL_46;
  }
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  v25 = CreateProcessAsUserW(
          hToken,
          ApplicationName,
          CommandLine,
          0,
          0,
          0,
          0x404u,
          lpEnvironment,
          Buffer,
          &StartupInfo,
          &hObject);
  v26 = GetLastError();
  UserToken = v26;
  if ( v26 > 0 )
    UserToken = (unsigned __int16)v26 | 0x80070000;
  if ( UserToken >= 0 )
    UserToken = -2147467259;
  RevertToSelf();
  if ( !v25 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_130;
    v28 = 48;
    goto LABEL_129;
  }
  v43 = 1;
  ProcessId = GetProcessId(hObject.hProcess);
  UserToken = StringCchPrintfW(Name, 0x104u, L"WerSvc\\WerSvcNonElevationInfoSectionName%d", ProcessId);
  if ( UserToken < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
        (unsigned int)UserToken);
    goto LABEL_135;
  }
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.bInheritHandle = 0;
  FileMappingAttributes.lpSecurityDescriptor = hMem;
  v30 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x18u, Name);
  v56 = v30;
  if ( (unsigned __int64)v30 + 1 <= 1 )
  {
    v31 = GetLastError();
    UserToken = v31;
    if ( v31 > 0 )
      UserToken = (unsigned __int16)v31 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_130;
      v28 = 50;
LABEL_129:
      WPP_SF_d(v27[2], v28, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)UserToken);
LABEL_130:
      v7 = v44;
      goto LABEL_64;
    }
LABEL_135:
    v7 = v44;
    v6 = 1;
    goto LABEL_65;
  }
  v32 = MapViewOfFile(v30, 6u, 0, 0, 0x18u);
  lpBaseAddress = v32;
  if ( !v32 )
  {
    v33 = GetLastError();
    UserToken = v33;
    if ( v33 > 0 )
      UserToken = (unsigned __int16)v33 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_130;
      v28 = 51;
      goto LABEL_129;
    }
    goto LABEL_135;
  }
  if ( !DuplicateHandle(ProcessHandle, hSourceHandle, hObject.hProcess, &TargetHandle, 0, 0, 2u) )
  {
    v34 = GetLastError();
    UserToken = v34;
    if ( v34 > 0 )
      UserToken = (unsigned __int16)v34 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_130;
      v28 = 52;
      goto LABEL_129;
    }
    goto LABEL_135;
  }
  CurrentProcess = GetCurrentProcess();
  v36 = EventW;
  if ( !DuplicateHandle(CurrentProcess, EventW, hObject.hProcess, &v53, 0x100000u, 0, 0) )
  {
    v37 = GetLastError();
    UserToken = v37;
    if ( v37 > 0 )
      UserToken = (unsigned __int16)v37 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_130;
      v28 = 53;
      goto LABEL_129;
    }
    goto LABEL_135;
  }
  *(_DWORD *)v32 = 24;
  v32[1] = TargetHandle;
  v32[2] = v53;
  if ( ResumeThread(hObject.hThread) == -1 )
  {
    v38 = GetLastError();
    UserToken = v38;
    if ( v38 > 0 )
      UserToken = (unsigned __int16)v38 | 0x80070000;
    if ( UserToken >= 0 )
      UserToken = -2147467259;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_130;
      v28 = 54;
      goto LABEL_129;
    }
    goto LABEL_135;
  }
  Handles[0] = v36;
  Handles[1] = hObject.hProcess;
  WaitForMultipleObjectsEx(2u, Handles, 0, 0x1388u, 0);
  if ( a3 )
  {
    v39 = GetCurrentProcess();
    if ( !DuplicateHandle(v39, hObject.hProcess, ProcessHandle, &v54, 0x100000u, 0, 0) )
    {
      v40 = GetLastError();
      UserToken = v40;
      if ( v40 > 0 )
        UserToken = (unsigned __int16)v40 | 0x80070000;
      if ( UserToken >= 0 )
        UserToken = -2147467259;
      goto LABEL_135;
    }
    v41 = *a3;
    *a3 = v54;
    if ( (unsigned __int64)v41 + 1 > 1 )
      CloseHandle(v41);
  }
  UserToken = 0;
  v7 = v44;
LABEL_69:
  if ( hMem )
    LocalFree(hMem);
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( (unsigned __int64)v56 + 1 > 1 )
    CloseHandle(v56);
  if ( (unsigned __int64)EventW + 1 > 1 )
    CloseHandle(EventW);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( (unsigned __int64)hToken + 1 > 1 )
    CloseHandle(hToken);
  if ( v7 )
    operator delete(v7);
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x180022108  mov     [rsp-8+arg_18], rbx
0x18002210d  push    rbp
0x18002210e  push    rsi
0x18002210f  push    rdi
0x180022110  push    r12
0x180022112  push    r13
0x180022114  push    r14
0x180022116  push    r15
0x180022118  lea     rbp, [rsp-8F0h]
0x180022120  sub     rsp, 9F0h
0x180022127  mov     rax, cs:__security_cookie
0x18002212e  xor     rax, rsp
0x180022131  mov     [rbp+920h+var_40], rax
0x180022138  mov     r13, r8
0x18002213b  mov     rbx, rdx
0x18002213e  mov     [rbp+920h+hSourceHandle], rdx
0x180022142  mov     r15, rcx
0x180022145  xor     r14d, r14d
0x180022148  mov     [rbp+920h+TokenHandle], r14
0x18002214c  mov     [rsp+0A20h+TokenInformationLength], r14d
0x180022151  mov     r12d, r14d
0x180022154  mov     [rbp+920h+hToken], r14
0x180022158  mov     [rbp+920h+var_990], r14
0x18002215c  xorps   xmm0, xmm0
0x18002215f  xor     eax, eax
0x180022161  movups  xmmword ptr [rsp+0A20h+hObject], xmm0
0x180022166  mov     [rbp+920h+var_998], rax
0x18002216a  xor     edx, edx; Val
0x18002216c  lea     r8d, [r14+68h]; Size
0x180022170  lea     rcx, [rbp+920h+StartupInfo]; void *
0x180022174  call    memset_0
0x180022179  mov     edi, 208h
0x18002217e  mov     r8d, edi; Size
0x180022181  xor     edx, edx; Val
0x180022183  lea     rcx, [rbp+920h+Buffer]; void *
0x18002218a  call    memset_0
0x18002218f  mov     r8d, edi; Size
0x180022192  xor     edx, edx; Val
0x180022194  lea     rcx, [rbp+920h+ApplicationName]; void *
0x18002219b  call    memset_0
0x1800221a0  mov     r8d, edi; Size
0x1800221a3  xor     edx, edx; Val
0x1800221a5  lea     rcx, [rbp+920h+CommandLine]; void *
0x1800221ac  call    memset_0
0x1800221b1  mov     r8d, edi; Size
0x1800221b4  xor     edx, edx; Val
0x1800221b6  lea     rcx, [rbp+920h+Name]; void *
0x1800221bd  call    memset_0
0x1800221c2  mov     [rbp+920h+var_970], r14
0x1800221c6  mov     [rbp+920h+TargetHandle], r14
0x1800221ca  mov     [rbp+920h+var_960], r14
0x1800221ce  mov     eax, r14d
0x1800221d1  mov     [rbp+920h+var_948], rax
0x1800221d5  mov     [rbp+920h+var_910], rax
0x1800221d9  mov     [rbp+920h+var_958], r14
0x1800221dd  mov     [rbp+920h+lpBaseAddress], rax
0x1800221e1  mov     [rbp+920h+var_908], rax
0x1800221e5  xorps   xmm0, xmm0
0x1800221e8  movups  xmmword ptr [rbp+920h+Handles], xmm0
0x1800221ec  mov     edx, r14d
0x1800221ef  mov     [rbp+920h+hMem], rdx
0x1800221f3  movups  xmmword ptr [rbp+920h+FileMappingAttributes.nLength], xmm0
0x1800221f7  mov     qword ptr [rbp+920h+FileMappingAttributes.bInheritHandle], rax
0x1800221fb  test    rbx, rbx
0x1800221fe  jg      loc_1800222A1
0x180022204  lea     rax, WPP_GLOBAL_Control
0x18002220b  lea     edi, [r14+1]
0x18002220f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022216  cmp     rcx, rax
0x180022219  jz      short loc_180022238
0x18002221b  test    [rcx+1Ch], dil
0x18002221f  jz      short loc_180022238
0x180022221  lea     edx, [rdi+21h]
0x180022224  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002222b  mov     rcx, [rcx+10h]
0x18002222f  call    WPP_SF_
0x180022234  mov     rdx, [rbp+920h+hMem]
0x180022238  test    rdx, rdx
0x18002223b  jz      short loc_180022247
0x18002223d  mov     rcx, rdx; hMem
0x180022240  call    cs:__imp_LocalFree
0x180022246  nop
0x180022247  mov     rcx, [rsp+0A20h+hObject]; hObject
0x18002224c  test    rcx, rcx
0x18002224f  jz      short loc_180022257
0x180022251  call    cs:__imp_CloseHandle
0x180022257  mov     rcx, [rbp+920h+hObject+8]; hObject
0x18002225b  test    rcx, rcx
0x18002225e  jz      short loc_180022266
0x180022260  call    cs:__imp_CloseHandle
0x180022266  xorps   xmm0, xmm0
0x180022269  xor     eax, eax
0x18002226b  movups  xmmword ptr [rsp+0A20h+hObject], xmm0
0x180022270  mov     [rbp+920h+var_998], rax
0x180022274  mov     rcx, [rbp+920h+var_990]
0x180022278  test    rcx, rcx
0x18002227b  jz      short loc_180022284
0x18002227d  call    cs:__imp_DestroyEnvBlock
0x180022283  nop
0x180022284  mov     rcx, [rbp+920h+TokenHandle]; hObject
0x180022288  lea     rax, [rcx+1]
0x18002228c  cmp     rax, rdi
0x18002228f  jbe     short loc_180022297
0x180022291  call    cs:__imp_CloseHandle
0x180022297  mov     eax, 80070057h
0x18002229c  jmp     loc_180022695
0x1800222a1  mov     [rsp+0A20h+var_9C0], r14d
0x1800222a6  lea     rcx, [rbp+920h+hMem]
0x1800222aa  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1800222af  mov     r8, rax; SecurityDescriptor
0x1800222b2  xor     r9d, r9d; SecurityDescriptorSize
0x1800222b5  lea     edi, [r9+1]
0x1800222b9  mov     edx, edi; StringSDRevision
0x1800222bb  lea     rcx, aDPAOiciGrWdAOi; "D:P(A;OICI;GR;;;WD)(A;OICI;GA;;;SY)"
0x1800222c2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800222c8  test    eax, eax
0x1800222ca  jnz     short loc_18002232B
0x1800222cc  call    cs:__imp_GetLastError
0x1800222d2  mov     ebx, eax
0x1800222d4  test    eax, eax
0x1800222d6  jle     short loc_1800222E1
0x1800222d8  movzx   ebx, ax
0x1800222db  or      ebx, 80070000h
0x1800222e1  mov     r14d, 80004005h
0x1800222e7  test    ebx, ebx
0x1800222e9  cmovns  ebx, r14d
0x1800222ed  lea     rax, WPP_GLOBAL_Control
0x1800222f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222fb  cmp     rcx, rax
0x1800222fe  jz      loc_1800225B7
0x180022304  test    [rcx+1Ch], dil
0x180022308  jz      loc_1800224B2
0x18002230e  mov     edx, 23h ; '#'
0x180022313  mov     r9d, ebx
0x180022316  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002231d  mov     rcx, [rcx+10h]
0x180022321  call    WPP_SF_d
0x180022326  jmp     loc_1800224B2
0x18002232b  lea     rcx, [rbp+920h+TokenHandle]
0x18002232f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180022334  mov     r8, rax; TokenHandle
0x180022337  mov     edx, 8; DesiredAccess
0x18002233c  mov     rcx, r15; ProcessHandle
0x18002233f  call    cs:__imp_OpenProcessToken
0x180022345  test    eax, eax
0x180022347  jnz     short loc_180022392
0x180022349  call    cs:__imp_GetLastError
0x18002234f  mov     ebx, eax
0x180022351  test    eax, eax
0x180022353  jle     short loc_18002235E
0x180022355  movzx   ebx, ax
0x180022358  or      ebx, 80070000h
0x18002235e  mov     r14d, 80004005h
0x180022364  test    ebx, ebx
0x180022366  cmovns  ebx, r14d
0x18002236a  lea     rax, WPP_GLOBAL_Control
0x180022371  mov     rcx, cs:WPP_GLOBAL_Control
0x180022378  cmp     rcx, rax
0x18002237b  jz      loc_1800225B7
0x180022381  test    [rcx+1Ch], dil
0x180022385  jz      loc_1800224B2
0x18002238b  mov     edx, 24h ; '$'
0x180022390  jmp     short loc_180022313
0x180022392  mov     [rsp+0A20h+TokenInformationLength], 0
0x18002239a  lea     rax, [rsp+0A20h+TokenInformationLength]
0x18002239f  mov     [rsp+0A20h+ReturnLength], rax; ReturnLength
0x1800223a4  xor     r9d, r9d; TokenInformationLength
0x1800223a7  xor     r8d, r8d; TokenInformation
0x1800223aa  lea     ebx, [r9+19h]
0x1800223ae  mov     edx, ebx; TokenInformationClass
0x1800223b0  mov     rcx, [rbp+920h+TokenHandle]; TokenHandle
0x1800223b4  call    cs:__imp_GetTokenInformation
0x1800223ba  test    eax, eax
0x1800223bc  jnz     short loc_180022415
0x1800223be  call    cs:__imp_GetLastError
0x1800223c4  cmp     eax, 7Ah ; 'z'
0x1800223c7  jz      short loc_180022415
0x1800223c9  call    cs:__imp_GetLastError
0x1800223cf  mov     ebx, eax
0x1800223d1  test    eax, eax
0x1800223d3  jle     short loc_1800223DE
0x1800223d5  movzx   ebx, ax
0x1800223d8  or      ebx, 80070000h
0x1800223de  mov     r14d, 80004005h
0x1800223e4  test    ebx, ebx
0x1800223e6  cmovns  ebx, r14d
0x1800223ea  lea     rax, WPP_GLOBAL_Control
0x1800223f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f8  cmp     rcx, rax
0x1800223fb  jz      loc_1800225B7
0x180022401  test    [rcx+1Ch], dil
0x180022405  jz      loc_1800224B2
0x18002240b  mov     edx, 25h ; '%'
0x180022410  jmp     loc_180022313
0x180022415  mov     ecx, [rsp+0A20h+TokenInformationLength]; unsigned __int64
0x180022419  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022420  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022425  mov     r12, rax
0x180022428  mov     [rsp+0A20h+var_9B8], rax
0x18002242d  test    rax, rax
0x180022430  jz      loc_180022D02
0x180022436  mov     [rbp+920h+var_900], rax
0x18002243a  lea     rax, [rsp+0A20h+TokenInformationLength]
0x18002243f  mov     [rsp+0A20h+ReturnLength], rax; ReturnLength
0x180022444  mov     r9d, [rsp+0A20h+TokenInformationLength]; TokenInformationLength
0x180022449  mov     r8, r12; TokenInformation
0x18002244c  mov     edx, ebx; TokenInformationClass
0x18002244e  mov     rcx, [rbp+920h+TokenHandle]; TokenHandle
0x180022452  call    cs:__imp_GetTokenInformation
0x180022458  test    eax, eax
0x18002245a  jnz     short loc_1800224BF
0x18002245c  call    cs:__imp_GetLastError
0x180022462  mov     ebx, eax
0x180022464  test    eax, eax
0x180022466  jle     short loc_180022471
0x180022468  movzx   ebx, ax
0x18002246b  or      ebx, 80070000h
0x180022471  mov     r14d, 80004005h
0x180022477  test    ebx, ebx
0x180022479  cmovns  ebx, r14d
0x18002247d  lea     rax, WPP_GLOBAL_Control
0x180022484  mov     rcx, cs:WPP_GLOBAL_Control
0x18002248b  cmp     rcx, rax
0x18002248e  jz      loc_1800225B7
0x180022494  test    [rcx+1Ch], dil
0x180022498  jz      short loc_1800224B2
0x18002249a  mov     edx, 27h ; '''
0x18002249f  mov     r9d, ebx
0x1800224a2  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x1800224a9  mov     rcx, [rcx+10h]
0x1800224ad  call    WPP_SF_d
0x1800224b2  test    ebx, ebx
0x1800224b4  js      loc_1800225B7
0x1800224ba  jmp     loc_1800225D9
0x1800224bf  mov     rcx, [r12]; pSid
0x1800224c3  call    cs:__imp_GetSidSubAuthorityCount
0x1800224c9  mov     cl, [rax]
0x1800224cb  sub     cl, dil
0x1800224ce  movzx   edx, cl; nSubAuthority
0x1800224d1  mov     rcx, [r12]; pSid
0x1800224d5  call    cs:__imp_GetSidSubAuthority
0x1800224db  cmp     dword ptr [rax], 2000h
0x1800224e1  jnb     short loc_1800224ED
0x1800224e3  mov     ebx, 80070005h
0x1800224e8  jmp     loc_1800225BC
0x1800224ed  xor     r9d, r9d; lpName
0x1800224f0  xor     r8d, r8d; bInitialState
0x1800224f3  xor     edx, edx; bManualReset
0x1800224f5  xor     ecx, ecx; lpEventAttributes
0x1800224f7  call    cs:__imp_CreateEventW
0x1800224fd  mov     [rbp+920h+var_970], rax
0x180022501  mov     [rbp+920h+var_8F8], rax
0x180022505  inc     rax
0x180022508  cmp     rax, rdi
0x18002250b  ja      short loc_180022555
0x18002250d  call    cs:__imp_GetLastError
0x180022513  mov     ebx, eax
0x180022515  test    eax, eax
0x180022517  jle     short loc_180022522
0x180022519  movzx   ebx, ax
0x18002251c  or      ebx, 80070000h
0x180022522  mov     r14d, 80004005h
0x180022528  test    ebx, ebx
0x18002252a  cmovns  ebx, r14d
0x18002252e  lea     rax, WPP_GLOBAL_Control
0x180022535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002253c  cmp     rcx, rax
0x18002253f  jz      short loc_1800225B7
0x180022541  test    [rcx+1Ch], dil
0x180022545  jz      loc_1800224B2
0x18002254b  mov     edx, 28h ; '('
0x180022550  jmp     loc_18002249F
0x180022555  lea     r8, [rbp+920h+hToken]
0x180022559  mov     rcx, r15; ProcessHandle
0x18002255c  call    ?GetUserToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetUserToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x180022561  mov     ebx, eax
0x180022563  cmp     eax, 80070032h
0x180022568  jnz     loc_1800226BF
0x18002256e  lea     r8, [rbp+920h+hToken]
0x180022572  xor     edx, edx
0x180022574  mov     rcx, r15; ProcessHandle
0x180022577  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18002257c  mov     ebx, eax
0x18002257e  test    eax, eax
0x180022580  jns     loc_1800226EE
0x180022586  lea     rax, WPP_GLOBAL_Control
0x18002258d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022594  cmp     rcx, rax
0x180022597  jz      short loc_1800225B7
0x180022599  test    [rcx+1Ch], dil
0x18002259d  jz      short loc_1800225B7
0x18002259f  mov     edx, 29h ; ')'
0x1800225a4  mov     r9d, ebx
0x1800225a7  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x1800225ae  mov     rcx, [rcx+10h]
0x1800225b2  call    WPP_SF_d
0x1800225b7  mov     r14d, [rsp+0A20h+var_9C0]
0x1800225bc  mov     rcx, [rbp+920h+hObject+8]; hThread
0x1800225c0  test    rcx, rcx
0x1800225c3  jz      short loc_1800225D9
  ... truncated ...
```
