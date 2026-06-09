# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x18046f350`
- end: `0x18046f47f`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18046f110`

## callees

- `0x1800a14f8`
- `0x1800e2988`
- `0x1800e34bc`
- `0x18046f2fc`
- `0x18046f350`
- `0x18046f898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18046f439`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18046f439`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18046f416`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18046f416`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18046f3b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18046f3b9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18046f450`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18046f450`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18046f425`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18046f425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046f461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046f461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(
        SHELLEXECUTEINFOW *a1)
{
  int v2; // eax
  DWORD v3; // edi
  HANDLE Event; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  DWORD ProcessId; // eax
  BOOL bAlertable; // [rsp+20h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v13; // [rsp+58h] [rbp+10h] BYREF

  a1->fMask |= 0x540u;
  a1->nShow = 1;
  v2 = SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::Execute(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = -2147418113;
    if ( a1->hProcess )
    {
      Event = CreateEventExW(0, L"Local\\SystemSettings_DataModel_CloseAdminFlow", 1u, 0x100000u);
      v13 = Event;
      if ( !Event )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x32,
                      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingExternalFlowUtilities.h",
                      v5);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
        return LastError;
      }
      Handles[0] = a1->hProcess;
      Handles[1] = Event;
      if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) == 1 )
      {
        ProcessId = GetProcessId(a1->hProcess);
        SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ProcessId);
        WaitForSingleObject(a1->hProcess, 0xFFFFFFFF);
      }
      ExitCode = 0;
      if ( GetExitCodeProcess(a1->hProcess, &ExitCode) )
        v3 = ExitCode;
      CloseHandle(a1->hProcess);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)(unsigned int)v2,
      bAlertable);
  }
  return v3;
}

```

## disassembly

```asm
0x18046f350  mov     [rsp+arg_10], rbx
0x18046f355  push    rdi
0x18046f356  sub     rsp, 40h
0x18046f35a  mov     rbx, rcx
0x18046f35d  or      dword ptr [rcx+4], 540h
0x18046f364  mov     dword ptr [rcx+30h], 1
0x18046f36b  call    ?Execute@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::Execute(_SHELLEXECUTEINFOW *)
0x18046f370  mov     edi, eax
0x18046f372  test    eax, eax
0x18046f374  jns     short loc_18046F394
0x18046f376  mov     rcx, [rsp+48h]; this
0x18046f37b  mov     r9d, eax; char *
0x18046f37e  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18046f385  mov     edx, 2Ch ; ','; void *
0x18046f38a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18046f38f  jmp     loc_18046F472
0x18046f394  mov     edi, 8000FFFFh
0x18046f399  cmp     qword ptr [rbx+68h], 0
0x18046f39e  jz      loc_18046F472
0x18046f3a4  mov     r9d, 100000h; dwDesiredAccess
0x18046f3aa  mov     r8d, 1; dwFlags
0x18046f3b0  lea     rdx, aLocalSystemset; "Local\\SystemSettings_DataModel_CloseAd"...
0x18046f3b7  xor     ecx, ecx; lpEventAttributes
0x18046f3b9  call    cs:__imp_CreateEventExW
0x18046f3bf  mov     [rsp+48h+arg_8], rax
0x18046f3c4  test    rax, rax
0x18046f3c7  jnz     short loc_18046F3F0
0x18046f3c9  mov     rcx, [rsp+48h]; this
0x18046f3ce  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18046f3d5  lea     edx, [rax+32h]; void *
0x18046f3d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18046f3dd  mov     ebx, eax
0x18046f3df  lea     rcx, [rsp+48h+arg_8]
0x18046f3e4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18046f3e9  mov     eax, ebx
0x18046f3eb  jmp     loc_18046F474
0x18046f3f0  mov     rcx, [rbx+68h]
0x18046f3f4  mov     [rsp+48h+Handles], rcx
0x18046f3f9  mov     [rsp+48h+var_10], rax
0x18046f3fe  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18046f406  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18046f40a  xor     r8d, r8d; bWaitAll
0x18046f40d  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18046f412  lea     ecx, [r8+2]; nCount
0x18046f416  call    cs:__imp_WaitForMultipleObjectsEx
0x18046f41c  cmp     eax, 1
0x18046f41f  jnz     short loc_18046F43F
0x18046f421  mov     rcx, [rbx+68h]; Process
0x18046f425  call    cs:__imp_GetProcessId
0x18046f42b  mov     ecx, eax
0x18046f42d  call    ?GracefullyTerminateProcess@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAJK@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ulong)
0x18046f432  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18046f435  mov     rcx, [rbx+68h]; hHandle
0x18046f439  call    cs:__imp_WaitForSingleObject
0x18046f43f  mov     [rsp+48h+ExitCode], 0
0x18046f447  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x18046f44c  mov     rcx, [rbx+68h]; hProcess
0x18046f450  call    cs:__imp_GetExitCodeProcess
0x18046f456  test    eax, eax
0x18046f458  cmovnz  edi, [rsp+48h+ExitCode]
0x18046f45d  mov     rcx, [rbx+68h]; hObject
0x18046f461  call    cs:__imp_CloseHandle
0x18046f467  nop
0x18046f468  lea     rcx, [rsp+48h+arg_8]
0x18046f46d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18046f472  mov     eax, edi
0x18046f474  mov     rbx, [rsp+48h+arg_10]
0x18046f479  add     rsp, 40h
0x18046f47d  pop     rdi
0x18046f47e  retn
```
