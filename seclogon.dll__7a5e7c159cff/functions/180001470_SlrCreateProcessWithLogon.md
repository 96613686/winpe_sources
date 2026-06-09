# SlrCreateProcessWithLogon

- ea: `0x180001470`
- end: `0x180002107`
- name: `SlrCreateProcessWithLogon`
- size: `3223`
- prototype: `int __fastcall(RPC_BINDING_HANDLE BindingHandle, DWORD **, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001470`
- `0x180002110`
- `0x180002570`
- `0x1800028f0`
- `0x180003e58`
- `0x1800045ee`
- `0x180004720`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000184d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000184d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000170d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001d6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000170d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001d6c`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180001b6b`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180001b6b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001ab0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002092`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000480c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001ab0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002092`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000480c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001860`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001a7f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001860`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180001a7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004854`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004862`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000162d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000162d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800016d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001b2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800016d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001b2e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180001c62`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180001c62`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001a26`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001a26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000161f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000161f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800020fc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800048f5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800020fc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800048f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000202a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800048ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000493a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000202a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800048ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000493a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001a49`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001a49`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180001be2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180001be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001606`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001647`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000180f`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001cdb`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800020ab`
- `RPCRT4!RpcRevertToSelfEx` at `0x180004820`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001647`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000180f`
- `RPCRT4!RpcRevertToSelfEx` at `0x180001cdb`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800020ab`
- `RPCRT4!RpcRevertToSelfEx` at `0x180004820`
- `RPCRT4!RpcImpersonateClient` at `0x1800015ad`
- `RPCRT4!RpcImpersonateClient` at `0x180001782`
- `RPCRT4!RpcImpersonateClient` at `0x1800015ad`
- `RPCRT4!RpcImpersonateClient` at `0x180001782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000209d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000498d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000209d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000498d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180001cca`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002020`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002052`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000492d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004968`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180001cca`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002020`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002052`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000492d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004968`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800015d7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800015d7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18000197f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18000197f`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180001954`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180001954`
- `ntdll!RtlSetEnvironmentVar` at `0x1800019cd`
- `ntdll!RtlSetEnvironmentVar` at `0x1800019fc`
- `ntdll!RtlSetEnvironmentVar` at `0x1800019cd`
- `ntdll!RtlSetEnvironmentVar` at `0x1800019fc`
- `ntdll!RtlSidDominates` at `0x180001e16`
- `ntdll!RtlSidDominates` at `0x180001e16`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001df7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001df7`
- `ntdll!NtQueryInformationProcess` at `0x180001689`
- `ntdll!NtQueryInformationProcess` at `0x180001689`
- `ntdll!RtlNtStatusToDosError` at `0x180001e32`
- `ntdll!RtlNtStatusToDosError` at `0x180001e59`
- `ntdll!RtlNtStatusToDosError` at `0x180001e6c`
- `ntdll!RtlNtStatusToDosError` at `0x180001e32`
- `ntdll!RtlNtStatusToDosError` at `0x180001e59`
- `ntdll!RtlNtStatusToDosError` at `0x180001e6c`
- `ntdll!RtlFreeSid` at `0x180001e26`
- `ntdll!RtlFreeSid` at `0x180001e26`
- `SspiCli!GetUserNameExW` at `0x180001aa2`
- `SspiCli!GetUserNameExW` at `0x180001aa2`
- `USERENV!UnloadUserProfile` at `0x1800020f0`
- `USERENV!UnloadUserProfile` at `0x18000487f`
- `USERENV!UnloadUserProfile` at `0x1800020f0`
- `USERENV!UnloadUserProfile` at `0x18000487f`
- `USERENV!CreateEnvironmentBlock` at `0x1800018b2`
- `USERENV!CreateEnvironmentBlock` at `0x1800018b2`
- `USERENV!DestroyEnvironmentBlock` at `0x180002061`
- `USERENV!DestroyEnvironmentBlock` at `0x1800047fc`
- `USERENV!DestroyEnvironmentBlock` at `0x180002061`
- `USERENV!DestroyEnvironmentBlock` at `0x1800047fc`
- `USERENV!LoadUserProfileW` at `0x180001aee`
- `USERENV!LoadUserProfileW` at `0x180001aee`

## string_xrefs

- `0x1800018dc`: `HOMEPATH`

## pseudocode

```c
int __fastcall SlrCreateProcessWithLogon(RPC_BINDING_HANDLE BindingHandle, DWORD **a2, __int64 a3)
{
  int v5; // r12d
  DWORD *v6; // rsi
  UINT LastError; // edi
  HANDLE CurrentThread; // rax
  int v9; // eax
  __int64 v10; // rbx
  WCHAR *v11; // rdi
  WCHAR *v12; // rcx
  DWORD CurrentDirectoryW; // eax
  int v14; // ebx
  void *v15; // r15
  int v16; // ecx
  void *v17; // rdi
  HANDLE CurrentProcess; // rax
  int v19; // eax
  NTSTATUS v20; // ebx
  void *v21; // rbx
  int result; // eax
  void *v23; // rbx
  HANDLE v24; // rax
  void *v25; // rdi
  HANDLE v26; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v28; // rax
  int ReturnLength; // [rsp+88h] [rbp-6D8h]
  int v30; // [rsp+CCh] [rbp-694h]
  _BYTE v31[8]; // [rsp+D0h] [rbp-690h] BYREF
  HANDLE hToken; // [rsp+D8h] [rbp-688h] BYREF
  int v33; // [rsp+E0h] [rbp-680h]
  HANDLE ProcessHandle; // [rsp+E8h] [rbp-678h] BYREF
  LPVOID v35; // [rsp+F0h] [rbp-670h] BYREF
  WINBOOL pfResult; // [rsp+F8h] [rbp-668h] BYREF
  int v37; // [rsp+FCh] [rbp-664h]
  DWORD TokenInformationLength; // [rsp+100h] [rbp-660h] BYREF
  int ProcessInformation; // [rsp+104h] [rbp-65Ch] BYREF
  int v40; // [rsp+108h] [rbp-658h] BYREF
  int v41; // [rsp+10Ch] [rbp-654h]
  HANDLE hProfile; // [rsp+110h] [rbp-650h]
  LPVOID lpMem; // [rsp+118h] [rbp-648h] BYREF
  DWORD v44; // [rsp+120h] [rbp-640h] BYREF
  ULONG nSize; // [rsp+124h] [rbp-63Ch] BYREF
  HANDLE ClientToken; // [rsp+128h] [rbp-638h] BYREF
  PSID Sid; // [rsp+130h] [rbp-630h] BYREF
  void *TokenHandle; // [rsp+138h] [rbp-628h] BYREF
  HANDLE hObject; // [rsp+140h] [rbp-620h] BYREF
  WCHAR *v50; // [rsp+148h] [rbp-618h]
  ULONG_PTR Size[2]; // [rsp+150h] [rbp-610h] BYREF
  __int128 v52; // [rsp+160h] [rbp-600h] BYREF
  __int128 v53; // [rsp+170h] [rbp-5F0h]
  __int128 TokenInformation; // [rsp+180h] [rbp-5E0h] BYREF
  _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+190h] [rbp-5D0h] BYREF
  __int64 v56; // [rsp+1A8h] [rbp-5B8h] BYREF
  DWORD **v57; // [rsp+1B0h] [rbp-5B0h]
  __int64 v58; // [rsp+1B8h] [rbp-5A8h]
  RPC_BINDING_HANDLE v59; // [rsp+1C0h] [rbp-5A0h]
  DWORD **v60; // [rsp+1C8h] [rbp-598h]
  _PROFILEINFOW ProfileInfo; // [rsp+1D0h] [rbp-590h] BYREF
  __int128 v62; // [rsp+208h] [rbp-558h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+218h] [rbp-548h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+220h] [rbp-540h] BYREF
  _OWORD v65[3]; // [rsp+238h] [rbp-528h] BYREF
  _QWORD v66[12]; // [rsp+268h] [rbp-4F8h] BYREF
  __int128 v67; // [rsp+2C8h] [rbp-498h] BYREF
  int v68; // [rsp+2D8h] [rbp-488h]
  __int128 v69; // [rsp+2E0h] [rbp-480h] BYREF
  wchar_t v70; // [rsp+2F0h] [rbp-470h]
  WCHAR Buffer[264]; // [rsp+2F8h] [rbp-468h] BYREF
  WCHAR NameBuffer[248]; // [rsp+508h] [rbp-258h] BYREF

  v57 = a2;
  v59 = BindingHandle;
  v60 = a2;
  v58 = a3;
  hToken = 0;
  hProfile = 0;
  ProcessHandle = 0;
  v30 = 0;
  v5 = 0;
  v33 = 0;
  v37 = 0;
  v41 = 0;
  memset(&ProcessAttributes, 0, 20);
  v6 = *a2;
  Size[1] = (ULONG_PTR)*a2;
  v52 = 0;
  v53 = 0;
  TokenInformation = 0;
  v40 = 0;
  lpMem = 0;
  v35 = 0;
  ClientToken = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  pfResult = 0;
  memset(v65, 0, sizeof(v65));
  Size[0] = 0;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  LODWORD(TokenInformation) = -1;
  LastError = RpcImpersonateClient(BindingHandle);
  if ( LastError )
    goto LABEL_54;
  v5 = 1;
  v33 = 1;
  ProcessHandle = OpenProcess(0x4C0u, 0, v6[18]);
  if ( !ProcessHandle )
    goto LABEL_88;
  TokenInformationLength = 88;
  TokenHandle = 0;
  v31[0] = LastError;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v66, TokenInformationLength, &TokenInformationLength) )
    {
      *(_DWORD *)IdentifierAuthority.Value = 0;
      *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
      Sid = 0;
      v19 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x2000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
      if ( v19 < 0 )
      {
        LastError = RtlNtStatusToDosError(v19);
      }
      else
      {
        v20 = RtlSidDominates(v66[0], Sid, v31);
        RtlFreeSid(Sid);
        if ( v20 >= 0 )
        {
          if ( !v31[0] )
            LastError = 5;
        }
        else
        {
          LastError = RtlNtStatusToDosError(v20);
        }
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !v31[0] )
    goto LABEL_54;
  LastError = RpcRevertToSelfEx(BindingHandle);
  if ( LastError )
    goto LABEL_54;
  v5 = 0;
  v33 = 0;
  ProcessInformation = 0;
  v9 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v9 < 0 )
  {
    LastError = RtlNtStatusToDosError(v9);
  }
  else
  {
    LastError = 0;
    v40 = ProcessInformation;
  }
  if ( LastError )
    goto LABEL_54;
  v44 = 0;
  hObject = 0;
  if ( OpenProcessToken(ProcessHandle, 8u, &hObject)
    && GetTokenInformation(hObject, TokenSessionId, &TokenInformation, 4u, &v44) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( LastError )
    goto LABEL_54;
  v10 = -1;
  if ( (*(_DWORD *)(*(_QWORD *)v6 + 60LL) & 0x100) != 0 )
  {
    v41 = 1;
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)v6 + 80LL) = -1;
    *(_QWORD *)(*(_QWORD *)v6 + 88LL) = -1;
    *(_QWORD *)(*(_QWORD *)v6 + 96LL) = -1;
  }
  if ( RpcImpersonateClient(BindingHandle) )
    goto LABEL_88;
  v5 = 1;
  v33 = 1;
  if ( *((_QWORD *)v6 + 11) )
  {
    if ( OpenProcessToken(ProcessHandle, 0xCu, &ClientToken) )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Privilege[0].Luid = (LUID)29LL;
      if ( !PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
        pfResult = 0;
      CloseHandle(ClientToken);
      if ( !pfResult )
      {
        LastError = 1314;
        goto LABEL_54;
      }
      v17 = (void *)*((_QWORD *)v6 + 11);
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(ProcessHandle, v17, CurrentProcess, &hToken, 0, 0, 2u) )
      {
        LastError = RpcRevertToSelfEx(BindingHandle);
        if ( !LastError )
        {
          v5 = 0;
          v33 = 0;
          LastError = 0;
          goto LABEL_25;
        }
LABEL_54:
        v15 = v35;
        goto LABEL_55;
      }
    }
LABEL_89:
    LastError = GetLastError();
    goto LABEL_54;
  }
  if ( (v6[21] & 1) == 0 && (v6[19] & 2) == 0 )
  {
    LastError = GetLogonSid(&lpMem);
    if ( LastError )
      goto LABEL_54;
  }
  v62 = *(_OWORD *)(v6 + 14);
  LastError = LogonUserWrap(*((wchar_t **)v6 + 1), ReturnLength, (__int64)lpMem, (__int64)&hToken, (__int64)&v35);
  if ( LastError )
    goto LABEL_54;
  LastError = RpcRevertToSelfEx(BindingHandle);
  if ( LastError )
    goto LABEL_54;
  v5 = 0;
  v33 = 0;
LABEL_25:
  if ( (v6[19] & 1) != 0 )
  {
    nSize = 257;
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize) )
        LastError = GetLastError();
      RevertToSelf();
      ProfileInfo.dwSize = 56;
      ProfileInfo.lpUserName = NameBuffer;
      v15 = v35;
      ProfileInfo.lpProfilePath = (LPWSTR)v35;
      if ( !LoadUserProfileW(hToken, &ProfileInfo) )
        goto LABEL_88;
      hProfile = ProfileInfo.hProfile;
      if ( !LastError )
        goto LABEL_26;
LABEL_55:
      v14 = 0;
      goto LABEL_90;
    }
    goto LABEL_89;
  }
LABEL_26:
  if ( SetTokenInformation(hToken, TokenSessionId, &v40, 4u) && ImpersonateLoggedOnUser(hToken) )
  {
    v37 = 1;
    ProcessAttributes.nLength = 24;
    ProcessAttributes.bInheritHandle = 0;
    ProcessAttributes.lpSecurityDescriptor = 0;
    if ( !*((_QWORD *)v6 + 5) )
    {
      if ( CreateEnvironmentBlock((LPVOID *)v6 + 5, hToken, 0) )
      {
        v67 = *(_OWORD *)L"HOMEDRIVE";
        v68 = *(_DWORD *)L"E";
        v69 = *(_OWORD *)L"HOMEPATH";
        v70 = aHomepath[8];
        v56 = 0;
        memset_0(Buffer, 0, 0x208u);
        v11 = 0;
        v50 = 0;
        v30 = 1;
        if ( (unsigned int)RtlQueryEnvironmentVariable(*((_QWORD *)v6 + 5), &v67, 9, 0, 0, &v56) == -1073741568 )
        {
          v12 = (WCHAR *)*((_QWORD *)v6 + 6);
          if ( v12 )
          {
            if ( !*v12 || !v12[1] )
            {
LABEL_35:
              if ( v11 && v11[1] == 58 )
              {
                RtlSetEnvironmentVar(v6 + 10, &v67, 9, v11, 2);
                do
                  ++v10;
                while ( v11[v10] );
                RtlSetEnvironmentVar(v6 + 10, &v69, 8, v11 + 2, v10 - 2);
              }
              goto LABEL_40;
            }
          }
          else
          {
            CurrentDirectoryW = GetCurrentDirectoryW(0x104u, Buffer);
            v12 = Buffer;
            if ( CurrentDirectoryW < 2 )
              v12 = 0;
          }
          v50 = v12;
          v11 = v12;
          goto LABEL_35;
        }
      }
      else
      {
        *((_QWORD *)v6 + 5) = 0;
      }
    }
LABEL_40:
    Size[0] = 48;
    if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v65, 1u, 0, Size)
      || !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v65, 0, 0x20000u, &ProcessHandle, 8u, 0, 0) )
    {
      v14 = v30;
LABEL_42:
      LastError = GetLastError();
      TerminateProcess(*(HANDLE *)a3, LastError);
      CloseHandle(*(HANDLE *)(a3 + 8));
      CloseHandle(*(HANDLE *)a3);
      v15 = v35;
      goto LABEL_90;
    }
    *(_QWORD *)(*(_QWORD *)v6 + 104LL) = v65;
    v16 = 524292;
    v14 = v30;
    if ( v30 )
      v16 = 525316;
    if ( CreateProcessAsUserW(
           hToken,
           *((LPCWSTR *)v6 + 3),
           *((LPWSTR *)v6 + 4),
           &ProcessAttributes,
           &ProcessAttributes,
           0,
           v6[20] | v16,
           *((LPVOID *)v6 + 5),
           *((LPCWSTR *)v6 + 6),
           *(LPSTARTUPINFOW *)v6,
           (LPPROCESS_INFORMATION)a3) )
    {
      if ( v41 && !(unsigned int)SlpSetStdHandles(*(HANDLE *)a3, ProcessHandle, *(_QWORD *)(*(_QWORD *)v6 + 96LL)) )
        goto LABEL_42;
      SetLastError(0);
    }
    goto LABEL_62;
  }
LABEL_88:
  v14 = 0;
LABEL_62:
  LastError = GetLastError();
  v15 = v35;
LABEL_90:
  *(_DWORD *)(a3 + 24) = LastError;
  if ( v14 )
    DestroyEnvironmentBlock(*((LPVOID *)v6 + 5));
  if ( v37 )
    RevertToSelf();
  if ( v5 )
    RpcRevertToSelfEx(BindingHandle);
  v21 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  if ( v15 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v15);
  }
  if ( *(_DWORD *)(a3 + 24) )
  {
    result = (int)hProfile;
    if ( hProfile )
      result = UnloadUserProfile(hToken, hProfile);
    if ( hToken )
      result = CloseHandle(hToken);
  }
  else
  {
    *(_QWORD *)&v52 = *(_QWORD *)a3;
    *((_QWORD *)&v52 + 1) = hToken;
    *(_QWORD *)&v53 = hProfile;
    *((_QWORD *)&TokenInformation + 1) = v6;
    if ( (_DWORD)TokenInformation != -1 )
      LastError = SecondaryLogonProcessWatchdogNewProcess((__int64)&v52);
    if ( LastError )
    {
      *(_DWORD *)(a3 + 24) = LastError;
    }
    else
    {
      if ( (v6[20] & 4) == 0 )
        ResumeThread(*(HANDLE *)(a3 + 8));
      v23 = *(void **)a3;
      v24 = GetCurrentProcess();
      DuplicateHandle(v24, v23, ProcessHandle, (LPHANDLE)a3, 0, 0, 2u);
      v25 = *(void **)(a3 + 8);
      v26 = GetCurrentProcess();
      DuplicateHandle(v26, v25, ProcessHandle, (LPHANDLE)(a3 + 8), 0, 0, 3u);
    }
    result = (int)v57;
    *v57 = 0;
  }
  if ( ProcessHandle )
    return CloseHandle(ProcessHandle);
  return result;
}

```

## disassembly

```asm
0x180001470  mov     r11, rsp
0x180001473  push    rbx
0x180001474  push    rsi
0x180001475  push    rdi
0x180001476  push    r12
0x180001478  push    r13
0x18000147a  push    r14
0x18000147c  push    r15
0x18000147e  sub     rsp, 6C0h
0x180001485  mov     rax, cs:__security_cookie
0x18000148c  xor     rax, rsp
0x18000148f  mov     [rsp+6F8h+var_48], rax
0x180001497  mov     r14, r8
0x18000149a  mov     [rsp+6F8h+var_5B0], rdx
0x1800014a2  mov     r13, rcx
0x1800014a5  mov     [rsp+6F8h+var_5A0], rcx
0x1800014ad  mov     [rsp+6F8h+var_598], rdx
0x1800014b5  mov     [rsp+6F8h+var_5A8], r8
0x1800014bd  xor     ebx, ebx
0x1800014bf  mov     [rsp+6F8h+hToken], rbx
0x1800014c4  mov     [r11-650h], rbx
0x1800014cb  mov     [r11-678h], rbx
0x1800014d2  mov     [rsp+6F8h+var_694], ebx
0x1800014d6  mov     r12d, ebx
0x1800014d9  mov     [rsp+6F8h+var_680], ebx
0x1800014dd  mov     [rsp+6F8h+var_664], ebx
0x1800014e4  mov     [rsp+6F8h+var_654], ebx
0x1800014eb  xor     ecx, ecx
0x1800014ed  xorps   xmm0, xmm0
0x1800014f0  movups  xmmword ptr [rsp+6F8h+ProcessAttributes.nLength], xmm0
0x1800014f8  mov     [rsp+6F8h+ProcessAttributes.bInheritHandle], ecx
0x1800014ff  mov     rsi, [rdx]
0x180001502  mov     [rsp+6F8h+var_608], rsi
0x18000150a  movups  [rsp+6F8h+var_600], xmm0
0x180001512  movups  [rsp+6F8h+var_5F0], xmm0
0x18000151a  movups  [rsp+6F8h+TokenInformation], xmm0
0x180001522  mov     [rsp+6F8h+var_698], 57h ; 'W'
0x18000152a  mov     [rsp+6F8h+var_658], ebx
0x180001531  mov     [r11-648h], rbx
0x180001538  mov     [r11-670h], rbx
0x18000153f  mov     [r11-638h], rbx
0x180001546  xor     eax, eax
0x180001548  movups  xmmword ptr [rsp+6F8h+RequiredPrivileges.PrivilegeCount], xmm0
0x180001550  mov     [rsp+6F8h+RequiredPrivileges.Privilege.Attributes], eax
0x180001557  mov     [rsp+6F8h+pfResult], ebx
0x18000155e  movups  [rsp+6F8h+var_528], xmm0
0x180001566  movups  [rsp+6F8h+var_518], xmm0
0x18000156e  movups  [rsp+6F8h+var_508], xmm0
0x180001576  mov     [r11-610h], rbx
0x18000157d  xorps   xmm1, xmm1
0x180001580  movups  xmmword ptr [rsp+6F8h+ProfileInfo.dwSize], xmm1
0x180001588  movups  xmmword ptr [rsp+6F8h+ProfileInfo.lpProfilePath], xmm1
0x180001590  movups  xmmword ptr [rsp+6F8h+ProfileInfo.lpServerName], xmm1
0x180001598  mov     [r11-560h], rax
0x18000159f  mov     dword ptr [rsp+6F8h+TokenInformation], 0FFFFFFFFh
0x1800015aa  mov     rcx, r13; BindingHandle
0x1800015ad  call    cs:__imp_RpcImpersonateClient
0x1800015b3  mov     edi, eax
0x1800015b5  mov     [rsp+6F8h+var_698], eax
0x1800015b9  test    eax, eax
0x1800015bb  jnz     loc_180001B9E
0x1800015c1  mov     r12d, 1
0x1800015c7  mov     [rsp+6F8h+var_680], r12d
0x1800015cc  mov     r8d, [rsi+48h]; dwProcessId
0x1800015d0  xor     edx, edx; bInheritHandle
0x1800015d2  mov     ecx, 4C0h; dwDesiredAccess
0x1800015d7  call    cs:__imp_OpenProcess
0x1800015dd  mov     [rsp+6F8h+ProcessHandle], rax
0x1800015e5  test    rax, rax
0x1800015e8  jz      loc_180001EF5
0x1800015ee  mov     [rsp+6F8h+TokenInformationLength], 58h ; 'X'
0x1800015f9  mov     [rsp+6F8h+TokenHandle], rbx
0x180001601  mov     [rsp+6F8h+var_690], dil
0x180001606  call    cs:__imp_GetCurrentThread
0x18000160c  mov     rcx, rax; ThreadHandle
0x18000160f  lea     r9, [rsp+6F8h+TokenHandle]; TokenHandle
0x180001617  mov     edx, 8; DesiredAccess
0x18000161c  mov     r8d, r12d; OpenAsSelf
0x18000161f  call    cs:__imp_OpenThreadToken
0x180001625  test    eax, eax
0x180001627  jnz     loc_180001D42
0x18000162d  call    cs:__imp_GetLastError
0x180001633  mov     edi, eax
0x180001635  mov     [rsp+6F8h+var_698], eax
0x180001639  cmp     [rsp+6F8h+var_690], 0
0x18000163e  jz      loc_180001B9E
0x180001644  mov     rcx, r13; BindingHandle
0x180001647  call    cs:__imp_RpcRevertToSelfEx
0x18000164d  mov     edi, eax
0x18000164f  mov     [rsp+6F8h+var_698], eax
0x180001653  test    eax, eax
0x180001655  jnz     loc_180001B9E
0x18000165b  mov     r12d, ebx
0x18000165e  mov     [rsp+6F8h+var_680], ebx
0x180001662  mov     [rsp+6F8h+ProcessInformation], ebx
0x180001669  mov     [rsp+6F8h+ReturnLength], rbx; ReturnLength
0x18000166e  mov     r9d, 4; ProcessInformationLength
0x180001674  lea     r8, [rsp+6F8h+ProcessInformation]; ProcessInformation
0x18000167c  mov     edx, 18h; ProcessInformationClass
0x180001681  mov     rcx, [rsp+6F8h+ProcessHandle]; ProcessHandle
0x180001689  call    cs:__imp_NtQueryInformationProcess
0x18000168f  test    eax, eax
0x180001691  js      loc_180001E6A
0x180001697  mov     edi, ebx
0x180001699  mov     eax, [rsp+6F8h+ProcessInformation]
0x1800016a0  mov     [rsp+6F8h+var_658], eax
0x1800016a7  mov     [rsp+6F8h+var_698], edi
0x1800016ab  test    edi, edi
0x1800016ad  jnz     loc_180001B9E
0x1800016b3  mov     [rsp+6F8h+var_640], ebx
0x1800016ba  mov     [rsp+6F8h+hObject], rbx
0x1800016c2  lea     r8, [rsp+6F8h+hObject]; TokenHandle
0x1800016ca  mov     edx, 8; DesiredAccess
0x1800016cf  mov     rcx, [rsp+6F8h+ProcessHandle]; ProcessHandle
0x1800016d7  call    cs:__imp_OpenProcessToken
0x1800016dd  test    eax, eax
0x1800016df  jz      loc_180001D35
0x1800016e5  lea     rax, [rsp+6F8h+var_640]
0x1800016ed  mov     [rsp+6F8h+ReturnLength], rax; int
0x1800016f2  mov     r9d, 4; TokenInformationLength
0x1800016f8  lea     r8, [rsp+6F8h+TokenInformation]; TokenInformation
0x180001700  mov     edx, 0Ch; TokenInformationClass
0x180001705  mov     rcx, [rsp+6F8h+hObject]; TokenHandle
0x18000170d  call    cs:__imp_GetTokenInformation
0x180001713  test    eax, eax
0x180001715  jz      loc_180001E79
0x18000171b  mov     edi, ebx
0x18000171d  mov     rcx, [rsp+6F8h+hObject]; hObject
0x180001725  test    rcx, rcx
0x180001728  jnz     loc_180001D95
0x18000172e  mov     [rsp+6F8h+var_698], edi
0x180001732  test    edi, edi
0x180001734  jnz     loc_180001B9E
0x18000173a  mov     rax, [rsi]
0x18000173d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001744  test    dword ptr [rax+3Ch], 100h
0x18000174b  jnz     short loc_180001761
0x18000174d  mov     [rax+50h], rbx
0x180001751  mov     rax, [rsi]
0x180001754  mov     [rax+58h], rbx
0x180001758  mov     rax, [rsi]
0x18000175b  mov     [rax+60h], rbx
0x18000175f  jmp     short loc_18000176C
0x180001761  mov     [rsp+6F8h+var_654], 1
0x18000176c  test    byte ptr [rsi+4Ch], 2
0x180001770  mov     eax, 2
0x180001775  mov     r15d, 9
0x18000177b  cmovz   r15d, eax
0x18000177f  mov     rcx, r13; BindingHandle
0x180001782  call    cs:__imp_RpcImpersonateClient
0x180001788  mov     [rsp+6F8h+var_698], eax
0x18000178c  test    eax, eax
0x18000178e  jnz     loc_180001EF5
0x180001794  mov     r12d, 1
0x18000179a  mov     [rsp+6F8h+var_680], r12d
0x18000179f  cmp     qword ptr [rsi+58h], 0
0x1800017a4  jnz     loc_180001B19
0x1800017aa  mov     eax, [rsi+54h]
0x1800017ad  test    r12b, al
0x1800017b0  jz      loc_180001E93
0x1800017b6  movups  xmm0, xmmword ptr [rsi+38h]
0x1800017ba  movaps  [rsp+6F8h+var_558], xmm0
0x1800017c2  lea     rax, [rsp+6F8h+var_670]
0x1800017ca  mov     [rsp+6F8h+lpEnvironment], rax; __int64
0x1800017cf  lea     rax, [rsp+6F8h+hToken]
0x1800017d4  mov     [rsp+6F8h+lpReturnSize], rax; __int64
0x1800017d9  mov     rax, [rsp+6F8h+lpMem]
0x1800017e1  mov     [rsp+6F8h+lpPreviousValue], rax; __int64
0x1800017e6  mov     r9d, r15d
0x1800017e9  lea     r8, [rsp+6F8h+var_558]
0x1800017f1  mov     rdx, [rsi+10h]
0x1800017f5  mov     rcx, [rsi+8]; Str
0x1800017f9  call    LogonUserWrap
0x1800017fe  mov     edi, eax
0x180001800  mov     [rsp+6F8h+var_698], eax
0x180001804  test    eax, eax
0x180001806  jnz     loc_180001B9E
0x18000180c  mov     rcx, r13; BindingHandle
0x18000180f  call    cs:__imp_RpcRevertToSelfEx
0x180001815  mov     edi, eax
0x180001817  mov     [rsp+6F8h+var_698], eax
0x18000181b  test    eax, eax
0x18000181d  jnz     loc_180001B9E
0x180001823  xor     r12d, r12d
0x180001826  mov     [rsp+6F8h+var_680], r12d
0x18000182b  test    byte ptr [rsi+4Ch], 1
0x18000182f  jnz     loc_180001A6F
0x180001835  mov     r9d, 4; TokenInformationLength
0x18000183b  lea     r8, [rsp+6F8h+var_658]; TokenInformation
0x180001843  mov     edx, 0Ch; TokenInformationClass
0x180001848  mov     rcx, [rsp+6F8h+hToken]; TokenHandle
0x18000184d  call    cs:__imp_SetTokenInformation
0x180001853  test    eax, eax
0x180001855  jz      loc_180001EF5
0x18000185b  mov     rcx, [rsp+6F8h+hToken]; hToken
0x180001860  call    cs:__imp_ImpersonateLoggedOnUser
0x180001866  test    eax, eax
0x180001868  jz      loc_180001EF5
0x18000186e  mov     [rsp+6F8h+var_664], 1
0x180001879  mov     [rsp+6F8h+ProcessAttributes.nLength], 18h
0x180001884  mov     [rsp+6F8h+ProcessAttributes.bInheritHandle], 0
0x18000188f  mov     [rsp+6F8h+ProcessAttributes.lpSecurityDescriptor], 0
0x18000189b  cmp     qword ptr [rsi+28h], 0
0x1800018a0  jnz     loc_180001A02
0x1800018a6  xor     r8d, r8d; bInherit
0x1800018a9  mov     rdx, [rsp+6F8h+hToken]; hToken
0x1800018ae  lea     rcx, [rsi+28h]; lpEnvironment
0x1800018b2  call    cs:__imp_CreateEnvironmentBlock
0x1800018b8  test    eax, eax
0x1800018ba  jz      loc_180001ECE
0x1800018c0  movups  xmm0, xmmword ptr cs:aHomedrive; "HOMEDRIVE"
0x1800018c7  movups  [rsp+6F8h+var_498], xmm0
0x1800018cf  mov     eax, dword ptr cs:aHomedrive+10h; "E"
0x1800018d5  mov     [rsp+6F8h+var_488], eax
0x1800018dc  movups  xmm0, xmmword ptr cs:aHomepath; "HOMEPATH"
0x1800018e3  movups  [rsp+6F8h+var_480], xmm0
0x1800018eb  movzx   eax, word ptr cs:aHomepath+10h; ""
0x1800018f2  mov     [rsp+6F8h+var_470], ax
0x1800018fa  mov     [rsp+6F8h+var_5B8], 0
0x180001906  xor     edx, edx; Val
0x180001908  mov     r8d, 208h; Size
0x18000190e  lea     rcx, [rsp+6F8h+Buffer]; void *
0x180001916  call    memset_0
0x18000191b  xor     edi, edi
0x18000191d  mov     [rsp+6F8h+var_618], rdi
0x180001925  mov     [rsp+6F8h+var_694], 1
0x18000192d  lea     rax, [rsp+6F8h+var_5B8]
0x180001935  mov     [rsp+6F8h+lpPreviousValue], rax
0x18000193a  mov     [rsp+6F8h+ReturnLength], rdi
0x18000193f  xor     r9d, r9d
0x180001942  mov     r8d, 9
0x180001948  lea     rdx, [rsp+6F8h+var_498]
0x180001950  mov     rcx, [rsi+28h]
0x180001954  call    cs:__imp_RtlQueryEnvironmentVariable
0x18000195a  cmp     eax, 0C0000100h
0x18000195f  jnz     loc_180001A02
0x180001965  mov     rcx, [rsi+30h]
0x180001969  test    rcx, rcx
0x18000196c  jnz     loc_180001EDB
0x180001972  lea     rdx, [rsp+6F8h+Buffer]; lpBuffer
0x18000197a  mov     ecx, 104h; nBufferLength
0x18000197f  call    cs:__imp_GetCurrentDirectoryW
0x180001985  lea     rcx, [rsp+6F8h+Buffer]
0x18000198d  cmp     eax, 2
0x180001990  cmovb   rcx, rdi
0x180001994  mov     [rsp+6F8h+var_618], rcx
0x18000199c  mov     rdi, rcx
0x18000199f  test    rdi, rdi
0x1800019a2  jz      short loc_180001A02
0x1800019a4  mov     eax, 3Ah ; ':'
0x1800019a9  cmp     ax, [rdi+2]
0x1800019ad  jnz     short loc_180001A02
0x1800019af  mov     [rsp+6F8h+ReturnLength], 2
0x1800019b8  mov     r9, rdi
0x1800019bb  mov     r8d, 9
0x1800019c1  lea     rdx, [rsp+6F8h+var_498]
0x1800019c9  lea     rcx, [rsi+28h]
0x1800019cd  call    cs:__imp_RtlSetEnvironmentVar
0x1800019d3  inc     rbx
0x1800019d6  cmp     word ptr [rdi+rbx*2], 0
0x1800019db  jnz     short loc_1800019D3
0x1800019dd  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800019e1  lea     r9, [rdi+4]
0x1800019e5  mov     [rsp+6F8h+ReturnLength], rbx
0x1800019ea  mov     r8d, 8
0x1800019f0  lea     rdx, [rsp+6F8h+var_480]
0x1800019f8  lea     rcx, [rsi+28h]
0x1800019fc  call    cs:__imp_RtlSetEnvironmentVar
0x180001a02  mov     [rsp+6F8h+Size], 30h ; '0'
0x180001a0e  lea     r9, [rsp+6F8h+Size]; lpSize
0x180001a16  xor     r8d, r8d; dwFlags
0x180001a19  mov     edx, 1; dwAttributeCount
0x180001a1e  lea     rcx, [rsp+6F8h+var_528]; lpAttributeList
0x180001a26  call    cs:__imp_InitializeProcThreadAttributeList
0x180001a2c  test    eax, eax
0x180001a2e  jnz     loc_180001BAF
0x180001a34  mov     ebx, [rsp+6F8h+var_694]
0x180001a38  call    cs:__imp_GetLastError
0x180001a3e  mov     edi, eax
0x180001a40  mov     [rsp+6F8h+var_698], eax
0x180001a44  mov     edx, eax; uExitCode
0x180001a46  mov     rcx, [r14]; hProcess
0x180001a49  call    cs:__imp_TerminateProcess
0x180001a4f  mov     rcx, [r14+8]; hObject
0x180001a53  call    cs:__imp_CloseHandle
0x180001a59  mov     rcx, [r14]; hObject
0x180001a5c  call    cs:__imp_CloseHandle
0x180001a62  mov     r15, [rsp+6F8h+var_670]
0x180001a6a  jmp     loc_180001F0F
0x180001a6f  mov     [rsp+6F8h+nSize], 101h
0x180001a7a  mov     rcx, [rsp+6F8h+hToken]; hToken
0x180001a7f  call    cs:__imp_ImpersonateLoggedOnUser
0x180001a85  test    eax, eax
0x180001a87  jz      loc_180001EFE
0x180001a8d  lea     r8, [rsp+6F8h+nSize]; nSize
0x180001a95  lea     rdx, [rsp+6F8h+NameBuffer]; lpNameBuffer
0x180001a9d  mov     ecx, 10002h; NameFormat
0x180001aa2  call    cs:__imp_GetUserNameExW
0x180001aa8  test    al, al
0x180001aaa  jz      loc_180001EBD
  ... truncated ...
```
