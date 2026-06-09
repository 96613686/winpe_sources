# Vml::VmServiceModule<ComputeServiceModule>::RegisterServer(void)

- ea: `0x14013b328`
- end: `0x14013b5a9`
- name: `?RegisterServer@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEAAXXZ`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140113430`

## callees

- `0x140080180`
- `0x1401332f0`
- `0x14013749c`
- `0x140139790`
- `0x14013b328`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013b3c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013b4fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013b3c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013b4fb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013b566`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013b575`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013b566`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013b575`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14013b45d`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14013b45d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14013b355`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14013b355`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14013b4aa`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14013b53a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14013b4aa`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14013b53a`

## string_xrefs

- `0x14013b37f`: `onecore\vm\common\vml\VmModules.h`
- `0x14013b47e`: `onecore\vm\common\vml\VmModules.h`
- `0x14013b4c2`: `onecore\vm\common\vml\VmModules.h`
- `0x14013b552`: `onecore\vm\common\vml\VmModules.h`
- `0x14013b3d8`: `onecore\vm\compute\service\host\main\ComputeServiceModule.h`
- `0x14013b513`: `onecore\vm\compute\service\host\main\ComputeServiceModule.h`

## pseudocode

```c
BOOL Vml::VmServiceModule<ComputeServiceModule>::RegisterServer()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rdi
  const WCHAR *v3; // rbx
  const char *v4; // r9
  const WCHAR *ServiceName; // rax
  SC_HANDLE ServiceW; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rbx
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  BOOL result; // eax
  SC_HANDLE v13; // [rsp+70h] [rbp-38h]
  SC_HANDLE v14; // [rsp+78h] [rbp-30h]
  WCHAR *v15; // [rsp+80h] [rbp-28h] BYREF
  int Info; // [rsp+88h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 2u);
  v2 = v0;
  v14 = v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB73,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
      v1);
  try
  {
    wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>();
    v3 = (const WCHAR *)*((_QWORD *)&xmmword_1403D36E0 + 1);
    if ( !*((_QWORD *)&xmmword_1403D36E0 + 1) )
    {
      v3 = &`ComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName;
      if ( !LoadStringW(&_ImageBase, 0x64u, &`ComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName, 260) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\ComputeServiceModule.h",
          v4);
      *((_QWORD *)&xmmword_1403D36E0 + 1) = &`ComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName;
    }
    ServiceName = (const WCHAR *)Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(&g_Module);
    ServiceW = CreateServiceW(
                 v2,
                 ServiceName,
                 v3,
                 0x10000000u,
                 0x10u,
                 3u,
                 1u,
                 &Vml::Details::g_ModulePath,
                 0,
                 0,
                 L"rpcss",
                 0,
                 0);
    v8 = ServiceW;
    v13 = ServiceW;
    if ( !ServiceW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB89,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v7);
    Info = 1;
    if ( !ChangeServiceConfig2W(ServiceW, 5u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB94,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v9);
    v15 = 0;
    if ( !LoadStringW(
            &_ImageBase,
            0x65u,
            &`ComputeServiceModule::_GetServiceDescription'::`2'::g_ServiceDescription,
            2048) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\ComputeServiceModule.h",
        v10);
    v15 = &`ComputeServiceModule::_GetServiceDescription'::`2'::g_ServiceDescription;
    if ( !ChangeServiceConfig2W(v8, 1u, &v15) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB9D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v11);
    CloseServiceHandle(v8);
    result = CloseServiceHandle(v2);
  }
  catch ( ... )
  {
    if ( v13 )
    {
      DeleteService(v13);
      CloseServiceHandle(v13);
    }
    CloseServiceHandle(v14);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x14013b328  mov     [rsp+arg_0], rbx
0x14013b32d  mov     [rsp+arg_8], rdi
0x14013b332  push    r15
0x14013b334  sub     rsp, 0A0h
0x14013b33b  mov     rax, cs:__security_cookie
0x14013b342  xor     rax, rsp
0x14013b345  mov     [rsp+0A8h+var_18], rax
0x14013b34d  xor     edx, edx; lpDatabaseName
0x14013b34f  xor     ecx, ecx; lpMachineName
0x14013b351  lea     r8d, [rdx+2]; dwDesiredAccess
0x14013b355  call    cs:__imp_OpenSCManagerW
0x14013b35c  nop     dword ptr [rax+rax+00h]
0x14013b361  mov     rdi, rax
0x14013b364  mov     [rsp+0A8h+var_30], rax
0x14013b369  mov     [rsp+0A8h+var_38], 0
0x14013b372  test    rax, rax
0x14013b375  jnz     short loc_14013B391
0x14013b377  mov     rcx, [rsp+0A8h]; this
0x14013b37f  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013b386  mov     edx, 0B73h; void *
0x14013b38b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b391  xor     dl, dl
0x14013b393  call    ??$init_once@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@Z; wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>(_RTL_RUN_ONCE &,_lambda_4285b01c8e2dee337a7854b7e6bdc04c_)
0x14013b398  mov     rbx, qword ptr cs:xmmword_1403D36E0+8
0x14013b39f  test    rbx, rbx
0x14013b3a2  jnz     short loc_14013B3EE
0x14013b3a4  mov     r9d, 104h; cchBufferMax
0x14013b3aa  lea     rbx, ?g_DisplayName@?1??_GetDisplayName@ComputeServiceModule@@QEBAPEBGXZ@4PAGA; ushort near * `ComputeServiceModule::_GetDisplayName(void)'::`2'::g_DisplayName
0x14013b3b1  mov     r8, rbx; lpBuffer
0x14013b3b4  mov     edx, 64h ; 'd'; uID
0x14013b3b9  lea     rcx, __ImageBase; hInstance
0x14013b3c0  call    cs:__imp_LoadStringW
0x14013b3c7  nop     dword ptr [rax+rax+00h]
0x14013b3cc  test    eax, eax
0x14013b3ce  jnz     short loc_14013B3E7
0x14013b3d0  mov     rcx, [rsp+0A8h]; this
0x14013b3d8  lea     r8, aOnecoreVmCompu_29; "onecore\\vm\\compute\\service\\host\\ma"...
0x14013b3df  lea     edx, [rax+2Bh]; void *
0x14013b3e2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b3e7  mov     qword ptr cs:xmmword_1403D36E0+8, rbx
0x14013b3ee  lea     rcx, ?g_Module@@3VComputeServiceModule@@A; ComputeServiceModule g_Module
0x14013b3f5  call    ?GetServiceName@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(void)
0x14013b3fa  mov     [rsp+0A8h+lpPassword], 0; lpPassword
0x14013b403  mov     [rsp+0A8h+lpServiceStartName], 0; lpServiceStartName
0x14013b40c  lea     rcx, ?g_ServiceDependencies@?1??_GetServiceDependencies@ComputeServiceModule@@QEBAPEBGXZ@4QBGB; "rpcss"
0x14013b413  mov     [rsp+0A8h+lpDependencies], rcx; lpDependencies
0x14013b418  mov     [rsp+0A8h+lpdwTagId], 0; lpdwTagId
0x14013b421  mov     [rsp+0A8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14013b42a  lea     rcx, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x14013b431  mov     [rsp+0A8h+lpBinaryPathName], rcx; lpBinaryPathName
0x14013b436  mov     [rsp+0A8h+dwErrorControl], 1; dwErrorControl
0x14013b43e  mov     [rsp+0A8h+dwStartType], 3; dwStartType
0x14013b446  mov     [rsp+0A8h+dwServiceType], 10h; dwServiceType
0x14013b44e  mov     r9d, 10000000h; dwDesiredAccess
0x14013b454  mov     r8, rbx; lpDisplayName
0x14013b457  mov     rdx, rax; lpServiceName
0x14013b45a  mov     rcx, rdi; hSCManager
0x14013b45d  call    cs:__imp_CreateServiceW
0x14013b464  nop     dword ptr [rax+rax+00h]
0x14013b469  mov     rbx, rax
0x14013b46c  mov     [rsp+0A8h+var_38], rax
0x14013b471  test    rax, rax
0x14013b474  jnz     short loc_14013B48F
0x14013b476  mov     rcx, [rsp+0A8h]; this
0x14013b47e  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013b485  mov     edx, 0B89h; void *
0x14013b48a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b48f  mov     [rsp+0A8h+Info], 1
0x14013b49a  lea     r8, [rsp+0A8h+Info]; lpInfo
0x14013b4a2  mov     edx, 5; dwInfoLevel
0x14013b4a7  mov     rcx, rbx; hService
0x14013b4aa  call    cs:__imp_ChangeServiceConfig2W
0x14013b4b1  nop     dword ptr [rax+rax+00h]
0x14013b4b6  mov     rcx, [rsp+0A8h]; this
0x14013b4be  test    eax, eax
0x14013b4c0  jnz     short loc_14013B4D3
0x14013b4c2  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013b4c9  mov     edx, 0B94h; void *
0x14013b4ce  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b4d3  mov     [rsp+0A8h+var_28], 0
0x14013b4df  mov     r9d, 800h; cchBufferMax
0x14013b4e5  lea     r15, ?g_ServiceDescription@?1??_GetServiceDescription@ComputeServiceModule@@QEBAPEAGXZ@4PAGA; ushort near * `ComputeServiceModule::_GetServiceDescription(void)'::`2'::g_ServiceDescription
0x14013b4ec  mov     r8, r15; lpBuffer
0x14013b4ef  mov     edx, 65h ; 'e'; uID
0x14013b4f4  lea     rcx, __ImageBase; hInstance
0x14013b4fb  call    cs:__imp_LoadStringW
0x14013b502  nop     dword ptr [rax+rax+00h]
0x14013b507  test    eax, eax
0x14013b509  jnz     short loc_14013B522
0x14013b50b  mov     rcx, [rsp+0A8h]; this
0x14013b513  lea     r8, aOnecoreVmCompu_29; "onecore\\vm\\compute\\service\\host\\ma"...
0x14013b51a  lea     edx, [rax+2Ch]; void *
0x14013b51d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b522  mov     [rsp+0A8h+var_28], r15
0x14013b52a  lea     r8, [rsp+0A8h+var_28]; lpInfo
0x14013b532  mov     edx, 1; dwInfoLevel
0x14013b537  mov     rcx, rbx; hService
0x14013b53a  call    cs:__imp_ChangeServiceConfig2W
0x14013b541  nop     dword ptr [rax+rax+00h]
0x14013b546  mov     rcx, [rsp+0A8h]; this
0x14013b54e  test    eax, eax
0x14013b550  jnz     short loc_14013B563
0x14013b552  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013b559  mov     edx, 0B9Dh; void *
0x14013b55e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013b563  mov     rcx, rbx; hSCObject
0x14013b566  call    cs:__imp_CloseServiceHandle
0x14013b56d  nop     dword ptr [rax+rax+00h]
0x14013b572  mov     rcx, rdi; hSCObject
0x14013b575  call    cs:__imp_CloseServiceHandle
0x14013b57c  nop     dword ptr [rax+rax+00h]
0x14013b581  nop
0x14013b582  mov     rcx, [rsp+0A8h+var_18]
0x14013b58a  xor     rcx, rsp; StackCookie
0x14013b58d  call    __security_check_cookie
0x14013b592  lea     r11, [rsp+0A8h+var_8]
0x14013b59a  mov     rbx, [r11+10h]
0x14013b59e  mov     rdi, [r11+18h]
0x14013b5a2  mov     rsp, r11
0x14013b5a5  pop     r15
0x14013b5a7  retn
```
