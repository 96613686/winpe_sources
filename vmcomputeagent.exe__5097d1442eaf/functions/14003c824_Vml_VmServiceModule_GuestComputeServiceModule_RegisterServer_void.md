# Vml::VmServiceModule<GuestComputeServiceModule>::RegisterServer(void)

- ea: `0x14003c824`
- end: `0x14003ca8c`
- name: `?RegisterServer@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ`
- size: `616`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003d6c0`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x14003c164`
- `0x14003c5c8`
- `0x14003c824`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003c89e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003c992`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003c89e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003c992`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003c851`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003c851`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003c9d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003c9da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003c9d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003c9da`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14003c922`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14003c922`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14003c954`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14003c9b8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14003c954`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14003c9b8`

## string_xrefs

- `0x14003ca0f`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ca40`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ca51`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ca79`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ca29`: `onecore\vm\compute\service\guest\exe\GuestComputeServiceModule.h`
- `0x14003ca6a`: `onecore\vm\compute\service\guest\exe\GuestComputeServiceModule.h`

## pseudocode

```c
BOOL Vml::VmServiceModule<GuestComputeServiceModule>::RegisterServer()
{
  SC_HANDLE v0; // rax
  Vml::Details *v1; // rcx
  const char *v2; // r9
  SC_HANDLE v3; // rdi
  const WCHAR *v4; // rbx
  const char *v5; // r9
  const WCHAR *ServiceName; // rax
  SC_HANDLE ServiceW; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rbx
  const char *v10; // r9
  const char *v11; // r9
  const char *v12; // r9
  BOOL result; // eax
  SC_HANDLE v14; // [rsp+70h] [rbp-38h]
  SC_HANDLE v15; // [rsp+78h] [rbp-30h]
  WCHAR *v16; // [rsp+80h] [rbp-28h] BYREF
  int Info; // [rsp+88h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 2u);
  v3 = v0;
  v15 = v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB73,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
      v2);
  try
  {
    Vml::Details::CacheModulePath(v1);
    v4 = lpDisplayName;
    if ( !lpDisplayName )
    {
      v4 = &`GuestComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName;
      if ( !LoadStringW(&_ImageBase, 0x64u, &`GuestComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName, 260) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecore\\vm\\compute\\service\\guest\\exe\\GuestComputeServiceModule.h",
          v5);
      lpDisplayName = &`GuestComputeServiceModule::_GetDisplayName'::`2'::g_DisplayName;
    }
    ServiceName = (const WCHAR *)Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(&g_Module);
    ServiceW = CreateServiceW(
                 v3,
                 ServiceName,
                 v4,
                 0x10000000u,
                 0x20u,
                 3u,
                 1u,
                 &Vml::Details::g_ModulePath,
                 0,
                 0,
                 &Dependencies,
                 0,
                 0);
    v9 = ServiceW;
    v14 = ServiceW;
    if ( !ServiceW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB89,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v8);
    Info = 1;
    if ( !ChangeServiceConfig2W(ServiceW, 5u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB94,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v10);
    v16 = 0;
    if ( !LoadStringW(
            &_ImageBase,
            0x65u,
            &`GuestComputeServiceModule::_GetServiceDescription'::`2'::g_ServiceDescription,
            2048) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\vm\\compute\\service\\guest\\exe\\GuestComputeServiceModule.h",
        v11);
    v16 = &`GuestComputeServiceModule::_GetServiceDescription'::`2'::g_ServiceDescription;
    if ( !ChangeServiceConfig2W(v9, 1u, &v16) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB9D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v12);
    CloseServiceHandle(v9);
    result = CloseServiceHandle(v3);
  }
  catch ( ... )
  {
    if ( v14 )
    {
      DeleteService(v14);
      CloseServiceHandle(v14);
    }
    CloseServiceHandle(v15);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x14003c824  mov     [rsp+arg_0], rbx
0x14003c829  mov     [rsp+arg_8], rdi
0x14003c82e  push    r15
0x14003c830  sub     rsp, 0A0h
0x14003c837  mov     rax, cs:__security_cookie
0x14003c83e  xor     rax, rsp
0x14003c841  mov     [rsp+0A8h+var_18], rax
0x14003c849  xor     edx, edx; lpDatabaseName
0x14003c84b  xor     ecx, ecx; lpMachineName
0x14003c84d  lea     r8d, [rdx+2]; dwDesiredAccess
0x14003c851  call    cs:__imp_OpenSCManagerW
0x14003c857  mov     rdi, rax
0x14003c85a  mov     [rsp+0A8h+var_30], rax
0x14003c85f  mov     [rsp+0A8h+var_38], 0
0x14003c868  test    rax, rax
0x14003c86b  jz      loc_14003CA07
0x14003c871  call    ?CacheModulePath@Details@Vml@@YAXXZ; Vml::Details::CacheModulePath(void)
0x14003c876  mov     rbx, cs:lpDisplayName
0x14003c87d  test    rbx, rbx
0x14003c880  jnz     short loc_14003C8B3
0x14003c882  mov     r9d, 104h; cchBufferMax
0x14003c888  lea     rbx, ?g_DisplayName@?1??_GetDisplayName@GuestComputeServiceModule@@QEBAPEBGXZ@4PAGA; ushort near * `GuestComputeServiceModule::_GetDisplayName(void)'::`2'::g_DisplayName
0x14003c88f  mov     r8, rbx; lpBuffer
0x14003c892  mov     edx, 64h ; 'd'; uID
0x14003c897  lea     rcx, __ImageBase; hInstance
0x14003c89e  call    cs:__imp_LoadStringW
0x14003c8a4  test    eax, eax
0x14003c8a6  jz      loc_14003CA21
0x14003c8ac  mov     cs:lpDisplayName, rbx
0x14003c8b3  lea     rcx, ?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003c8ba  call    ?GetServiceName@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(void)
0x14003c8bf  mov     [rsp+0A8h+lpPassword], 0; lpPassword
0x14003c8c8  mov     [rsp+0A8h+lpServiceStartName], 0; lpServiceStartName
0x14003c8d1  lea     rcx, Dependencies
0x14003c8d8  mov     [rsp+0A8h+lpDependencies], rcx; lpDependencies
0x14003c8dd  mov     [rsp+0A8h+lpdwTagId], 0; lpdwTagId
0x14003c8e6  mov     [rsp+0A8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14003c8ef  lea     rcx, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x14003c8f6  mov     [rsp+0A8h+lpBinaryPathName], rcx; lpBinaryPathName
0x14003c8fb  mov     [rsp+0A8h+dwErrorControl], 1; dwErrorControl
0x14003c903  mov     [rsp+0A8h+dwStartType], 3; dwStartType
0x14003c90b  mov     [rsp+0A8h+dwServiceType], 20h ; ' '; dwServiceType
0x14003c913  mov     r9d, 10000000h; dwDesiredAccess
0x14003c919  mov     r8, rbx; lpDisplayName
0x14003c91c  mov     rdx, rax; lpServiceName
0x14003c91f  mov     rcx, rdi; hSCManager
0x14003c922  call    cs:__imp_CreateServiceW
0x14003c928  mov     rbx, rax
0x14003c92b  mov     [rsp+0A8h+var_38], rax
0x14003c930  test    rax, rax
0x14003c933  jz      loc_14003CA38
0x14003c939  mov     [rsp+0A8h+Info], 1
0x14003c944  lea     r8, [rsp+0A8h+Info]; lpInfo
0x14003c94c  mov     edx, 5; dwInfoLevel
0x14003c951  mov     rcx, rbx; hService
0x14003c954  call    cs:__imp_ChangeServiceConfig2W
0x14003c95a  mov     rcx, [rsp+0A8h]; this
0x14003c962  test    eax, eax
0x14003c964  jz      loc_14003CA51
0x14003c96a  mov     [rsp+0A8h+var_28], 0
0x14003c976  mov     r9d, 800h; cchBufferMax
0x14003c97c  lea     r15, ?g_ServiceDescription@?1??_GetServiceDescription@GuestComputeServiceModule@@QEBAPEAGXZ@4PAGA; ushort near * `GuestComputeServiceModule::_GetServiceDescription(void)'::`2'::g_ServiceDescription
0x14003c983  mov     r8, r15; lpBuffer
0x14003c986  mov     edx, 65h ; 'e'; uID
0x14003c98b  lea     rcx, __ImageBase; hInstance
0x14003c992  call    cs:__imp_LoadStringW
0x14003c998  test    eax, eax
0x14003c99a  jz      loc_14003CA62
0x14003c9a0  mov     [rsp+0A8h+var_28], r15
0x14003c9a8  lea     r8, [rsp+0A8h+var_28]; lpInfo
0x14003c9b0  mov     edx, 1; dwInfoLevel
0x14003c9b5  mov     rcx, rbx; hService
0x14003c9b8  call    cs:__imp_ChangeServiceConfig2W
0x14003c9be  mov     rcx, [rsp+0A8h]; this
0x14003c9c6  test    eax, eax
0x14003c9c8  jz      loc_14003CA79
0x14003c9ce  mov     rcx, rbx; hSCObject
0x14003c9d1  call    cs:__imp_CloseServiceHandle
0x14003c9d7  mov     rcx, rdi; hSCObject
0x14003c9da  call    cs:__imp_CloseServiceHandle
0x14003c9e0  nop
0x14003c9e1  mov     rcx, [rsp+0A8h+var_18]
0x14003c9e9  xor     rcx, rsp; StackCookie
0x14003c9ec  call    __security_check_cookie
0x14003c9f1  lea     r11, [rsp+0A8h+var_8]
0x14003c9f9  mov     rbx, [r11+10h]
0x14003c9fd  mov     rdi, [r11+18h]
0x14003ca01  mov     rsp, r11
0x14003ca04  pop     r15
0x14003ca06  retn
0x14003ca07  mov     rcx, [rsp+0A8h]; this
0x14003ca0f  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ca16  mov     edx, 0B73h; void *
0x14003ca1b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ca21  mov     rcx, [rsp+0A8h]; this
0x14003ca29  lea     r8, aOnecoreVmCompu_45; "onecore\\vm\\compute\\service\\guest\\e"...
0x14003ca30  lea     edx, [rax+47h]; void *
0x14003ca33  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ca38  mov     rcx, [rsp+0A8h]; this
0x14003ca40  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ca47  mov     edx, 0B89h; void *
0x14003ca4c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ca51  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ca58  mov     edx, 0B94h; void *
0x14003ca5d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ca62  mov     rcx, [rsp+0A8h]; this
0x14003ca6a  lea     r8, aOnecoreVmCompu_45; "onecore\\vm\\compute\\service\\guest\\e"...
0x14003ca71  lea     edx, [rax+4Ah]; void *
0x14003ca74  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ca79  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ca80  mov     edx, 0B9Dh; void *
0x14003ca85  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
