# Vml::VmServiceModule<GuestComputeServiceModule>::UnregisterServer(void)

- ea: `0x14003cd60`
- end: `0x14003ce44`
- name: `?UnregisterServer@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003d6c0`

## callees

- `0x14000ddac`
- `0x1400341ac`
- `0x14003c5c8`
- `0x14003cd60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003cdf2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003cd77`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14003cd77`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003cdd7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003cde0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003cdd7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003cde0`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14003cdc5`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14003cdc5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14003cdaf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14003cdaf`

## string_xrefs

- `0x14003ce08`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ce1f`: `onecore\vm\common\vml\VmModules.h`
- `0x14003ce31`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
BOOL Vml::VmServiceModule<GuestComputeServiceModule>::UnregisterServer()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rbx
  const WCHAR *ServiceName; // rax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  const char *v6; // r9
  BOOL result; // eax
  DWORD LastError; // eax
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  SC_HANDLE v11; // [rsp+30h] [rbp+8h]
  SC_HANDLE v12; // [rsp+38h] [rbp+10h]

  v0 = OpenSCManagerW(0, 0, 4u);
  v2 = v0;
  v12 = v0;
  if ( !v0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBCB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
      v1);
  try
  {
    ServiceName = (const WCHAR *)Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(&g_Module);
    v4 = OpenServiceW(v2, ServiceName, 0x10000u);
    v5 = v4;
    v11 = v4;
    if ( v4 )
    {
      if ( !DeleteService(v4) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xBD4,
          (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
          v6);
      CloseServiceHandle(v5);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1060 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xBDD,
          (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
          (const char *)LastError,
          v9);
    }
    result = CloseServiceHandle(v2);
  }
  catch ( ... )
  {
    if ( v11 )
      CloseServiceHandle(v11);
    CloseServiceHandle(v12);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x14003cd60  mov     [rsp+arg_10], rbx
0x14003cd65  mov     [rsp+arg_0], rcx
0x14003cd6a  push    rdi; unsigned int
0x14003cd6b  sub     rsp, 20h
0x14003cd6f  xor     edx, edx; lpDatabaseName
0x14003cd71  xor     ecx, ecx; lpMachineName
0x14003cd73  lea     r8d, [rdx+4]; dwDesiredAccess
0x14003cd77  call    cs:__imp_OpenSCManagerW
0x14003cd7d  mov     rbx, rax
0x14003cd80  mov     [rsp+28h+arg_8], rax
0x14003cd85  mov     [rsp+28h+arg_0], 0
0x14003cd8e  test    rax, rax
0x14003cd91  jz      loc_14003CE1A
0x14003cd97  lea     rcx, ?g_Module@@3VGuestComputeServiceModule@@A; GuestComputeServiceModule g_Module
0x14003cd9e  call    ?GetServiceName@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<GuestComputeServiceModule>::GetServiceName(void)
0x14003cda3  mov     r8d, 10000h; dwDesiredAccess
0x14003cda9  mov     rdx, rax; lpServiceName
0x14003cdac  mov     rcx, rbx; hSCManager
0x14003cdaf  call    cs:__imp_OpenServiceW
0x14003cdb5  mov     rdi, rax
0x14003cdb8  mov     [rsp+28h+arg_0], rax
0x14003cdbd  test    rax, rax
0x14003cdc0  jz      short loc_14003CDF2
0x14003cdc2  mov     rcx, rax; hService
0x14003cdc5  call    cs:__imp_DeleteService
0x14003cdcb  mov     rcx, [rsp+28h]; this
0x14003cdd0  test    eax, eax
0x14003cdd2  jz      short loc_14003CE31
0x14003cdd4  mov     rcx, rdi; hSCObject
0x14003cdd7  call    cs:__imp_CloseServiceHandle
0x14003cddd  mov     rcx, rbx; hSCObject
0x14003cde0  call    cs:__imp_CloseServiceHandle
0x14003cde6  nop
0x14003cde7  mov     rbx, [rsp+28h+arg_10]
0x14003cdec  add     rsp, 20h
0x14003cdf0  pop     rdi
0x14003cdf1  retn
0x14003cdf2  call    cs:__imp_GetLastError
0x14003cdf8  nop
0x14003cdf9  cmp     eax, 424h
0x14003cdfe  jz      short loc_14003CDDD
0x14003ce00  mov     rcx, [rsp+28h]; this
0x14003ce05  mov     r9d, eax; char *
0x14003ce08  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ce0f  mov     edx, 0BDDh; void *
0x14003ce14  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14003ce1a  mov     rcx, [rsp+28h]; this
0x14003ce1f  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ce26  mov     edx, 0BCBh; void *
0x14003ce2b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003ce31  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003ce38  mov     edx, 0BD4h; void *
0x14003ce3d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
