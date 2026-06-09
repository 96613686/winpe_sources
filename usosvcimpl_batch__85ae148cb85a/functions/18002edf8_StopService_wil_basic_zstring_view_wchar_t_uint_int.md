# StopService(wil::basic_zstring_view<wchar_t>,uint,int)

- ea: `0x18002edf8`
- end: `0x18002effa`
- name: `?StopService@@YAXV?$basic_zstring_view@_W@wil@@IH@Z`
- size: `514`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18002faa0`

## callees

- `0x180010f24`
- `0x18002edf8`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002ee5f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002ee5f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ee34`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002ee34`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x18002eeef`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x18002eeef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef47`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef6b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef75`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef47`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef6b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ef75`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002eea4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ef2f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002eea4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ef2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ef5e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ef5e`

## string_xrefs

- `0x18002ee2b`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
BOOL __fastcall StopService(LPCWSTR *a1)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rbx
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  int i; // esi
  const char *v10; // r9
  __int128 pControlParams; // [rsp+30h] [rbp-68h] BYREF
  __int128 v13; // [rsp+40h] [rbp-58h]
  __int128 v14; // [rsp+50h] [rbp-48h]
  __int64 v15; // [rsp+60h] [rbp-38h]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Sysprep.cpp",
      v3);
  v5 = OpenServiceW(v2, *a1, 0x24u);
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Sysprep.cpp",
      v6);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !QueryServiceStatus(v5, &ServiceStatus) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Sysprep.cpp",
      v7);
  if ( ServiceStatus.dwCurrentState != 3 && ServiceStatus.dwCurrentState != 1 )
  {
    pControlParams = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    LODWORD(pControlParams) = 1074135063;
    if ( !ControlServiceExW(v5, 1u, 1u, &pControlParams) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x28,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Sysprep.cpp",
        v8);
  }
  for ( i = 0; i < 30; ++i )
  {
    pControlParams = 0;
    *(_QWORD *)&v13 = 0;
    DWORD2(v13) = 0;
    if ( !QueryServiceStatus(v5, (LPSERVICE_STATUS)&pControlParams) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Sysprep.cpp",
        v10);
    if ( DWORD1(pControlParams) == 1 )
      break;
    Sleep(0x3E8u);
  }
  CloseServiceHandle(v5);
  return CloseServiceHandle(v4);
}

```

## disassembly

```asm
0x18002edf8  mov     [rsp+arg_8], rbx
0x18002edfd  mov     [rsp+arg_10], rsi
0x18002ee02  mov     [rsp+arg_18], rdi
0x18002ee07  push    r14
0x18002ee09  sub     rsp, 90h
0x18002ee10  mov     rax, cs:__security_cookie
0x18002ee17  xor     rax, rsp
0x18002ee1a  mov     [rsp+98h+var_10], rax
0x18002ee22  mov     rbx, rcx
0x18002ee25  mov     r8d, 1; dwDesiredAccess
0x18002ee2b  lea     rdx, DatabaseName; "ServicesActive"
0x18002ee32  xor     ecx, ecx; lpMachineName
0x18002ee34  call    cs:__imp_OpenSCManagerW
0x18002ee3a  mov     rdi, rax
0x18002ee3d  mov     [rsp+98h+var_78], rax
0x18002ee42  mov     rcx, [rsp+98h]; this
0x18002ee4a  test    rax, rax
0x18002ee4d  jz      loc_18002EFA6
0x18002ee53  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18002ee59  mov     rdx, [rbx]; lpServiceName
0x18002ee5c  mov     rcx, rdi; hSCManager
0x18002ee5f  call    cs:__imp_OpenServiceW
0x18002ee65  mov     rbx, rax
0x18002ee68  mov     [rsp+98h+var_70], rax
0x18002ee6d  mov     rcx, [rsp+98h]; this
0x18002ee75  test    rax, rax
0x18002ee78  jz      loc_18002EFB6
0x18002ee7e  xorps   xmm0, xmm0
0x18002ee81  xor     eax, eax
0x18002ee83  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18002ee88  mov     qword ptr [rsp+98h+ServiceStatus.dwServiceSpecificExitCode], rax
0x18002ee8d  mov     [rsp+98h+ServiceStatus.dwWaitHint], eax
0x18002ee94  mov     rsi, [rsp+98h]
0x18002ee9c  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18002eea1  mov     rcx, rbx; hService
0x18002eea4  call    cs:__imp_QueryServiceStatus
0x18002eeaa  test    eax, eax
0x18002eeac  jz      loc_18002EFC5
0x18002eeb2  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 3
0x18002eeb7  jz      short loc_18002EF05
0x18002eeb9  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 1
0x18002eebe  jz      short loc_18002EF05
0x18002eec0  xorps   xmm0, xmm0
0x18002eec3  xor     eax, eax
0x18002eec5  movups  [rsp+98h+pControlParams], xmm0
0x18002eeca  movups  [rsp+98h+var_58], xmm0
0x18002eecf  movups  [rsp+98h+var_48], xmm0
0x18002eed4  mov     [rsp+98h+var_38], rax
0x18002eed9  mov     dword ptr [rsp+98h+pControlParams], 40060017h
0x18002eee1  lea     r9, [rsp+98h+pControlParams]; pControlParams
0x18002eee6  lea     edx, [rax+1]; dwControl
0x18002eee9  mov     r8d, edx; dwInfoLevel
0x18002eeec  mov     rcx, rbx; hService
0x18002eeef  call    cs:__imp_ControlServiceExW
0x18002eef5  mov     rcx, [rsp+98h]; this
0x18002eefd  test    eax, eax
0x18002eeff  jz      loc_18002EFD7
0x18002ef05  xor     esi, esi
0x18002ef07  cmp     esi, 1Eh
0x18002ef0a  jge     short loc_18002EF68
0x18002ef0c  xorps   xmm0, xmm0
0x18002ef0f  xor     eax, eax
0x18002ef11  movups  [rsp+98h+pControlParams], xmm0
0x18002ef16  mov     qword ptr [rsp+98h+var_58], rax
0x18002ef1b  mov     dword ptr [rsp+98h+var_58+8], eax
0x18002ef1f  mov     r14, [rsp+98h]
0x18002ef27  lea     rdx, [rsp+98h+pControlParams]; lpServiceStatus
0x18002ef2c  mov     rcx, rbx; hService
0x18002ef2f  call    cs:__imp_QueryServiceStatus
0x18002ef35  test    eax, eax
0x18002ef37  jz      loc_18002EFE6
0x18002ef3d  cmp     dword ptr [rsp+98h+pControlParams+4], 1
0x18002ef42  jnz     short loc_18002EF59
0x18002ef44  mov     rcx, rbx; hSCObject
0x18002ef47  call    cs:__imp_CloseServiceHandle
0x18002ef4d  nop
0x18002ef4e  mov     rcx, rdi; hSCObject
0x18002ef51  call    cs:__imp_CloseServiceHandle
0x18002ef57  jmp     short loc_18002EF7C
0x18002ef59  mov     ecx, 3E8h; dwMilliseconds
0x18002ef5e  call    cs:__imp_Sleep
0x18002ef64  inc     esi
0x18002ef66  jmp     short loc_18002EF07
0x18002ef68  mov     rcx, rbx; hSCObject
0x18002ef6b  call    cs:__imp_CloseServiceHandle
0x18002ef71  nop
0x18002ef72  mov     rcx, rdi; hSCObject
0x18002ef75  call    cs:__imp_CloseServiceHandle
0x18002ef7b  nop
0x18002ef7c  mov     rcx, [rsp+98h+var_10]
0x18002ef84  xor     rcx, rsp; StackCookie
0x18002ef87  call    __security_check_cookie
0x18002ef8c  lea     r11, [rsp+98h+var_8]
0x18002ef94  mov     rbx, [r11+18h]
0x18002ef98  mov     rsi, [r11+20h]
0x18002ef9c  mov     rdi, [r11+28h]
0x18002efa0  mov     rsp, r11
0x18002efa3  pop     r14
0x18002efa5  retn
0x18002efa6  lea     r8, aCW1SSrcOrchest_35; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18002efad  lea     edx, [rax+1Ah]; void *
0x18002efb0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002efb6  lea     r8, aCW1SSrcOrchest_35; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18002efbd  lea     edx, [rax+1Dh]; void *
0x18002efc0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002efc5  lea     r8, aCW1SSrcOrchest_35; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18002efcc  lea     edx, [rax+20h]; void *
0x18002efcf  mov     rcx, rsi; this
0x18002efd2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002efd7  lea     r8, aCW1SSrcOrchest_35; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18002efde  lea     edx, [rax+28h]; void *
0x18002efe1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002efe6  lea     r8, aCW1SSrcOrchest_35; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18002efed  lea     edx, [rax+2Eh]; void *
0x18002eff0  mov     rcx, r14; this
0x18002eff3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
