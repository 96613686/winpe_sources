# Vml::VmServiceModule<ComputeServiceModule>::UnregisterServer(void)

- ea: `0x14013c6d0`
- end: `0x14013c7d4`
- name: `?UnregisterServer@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEAAXXZ`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140113430`

## callees

- `0x140080180`
- `0x1400c4154`
- `0x140139790`
- `0x14013c6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013c7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013c7a5`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14013c754`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14013c754`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013c77d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013c78c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013c77d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14013c78c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14013c6e7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14013c6e7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14013c738`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14013c738`

## string_xrefs

- `0x14013c70e`: `onecore\vm\common\vml\VmModules.h`
- `0x14013c769`: `onecore\vm\common\vml\VmModules.h`
- `0x14013c7c1`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
BOOL Vml::VmServiceModule<ComputeServiceModule>::UnregisterServer()
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
    ServiceName = (const WCHAR *)Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(&g_Module);
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
0x14013c6d0  mov     [rsp+arg_10], rbx
0x14013c6d5  mov     [rsp+arg_0], rcx
0x14013c6da  push    rdi; unsigned int
0x14013c6db  sub     rsp, 20h
0x14013c6df  xor     edx, edx; lpDatabaseName
0x14013c6e1  xor     ecx, ecx; lpMachineName
0x14013c6e3  lea     r8d, [rdx+4]; dwDesiredAccess
0x14013c6e7  call    cs:__imp_OpenSCManagerW
0x14013c6ee  nop     dword ptr [rax+rax+00h]
0x14013c6f3  mov     rbx, rax
0x14013c6f6  mov     [rsp+28h+arg_8], rax
0x14013c6fb  mov     [rsp+28h+arg_0], 0
0x14013c704  test    rax, rax
0x14013c707  jnz     short loc_14013C720
0x14013c709  mov     rcx, [rsp+28h]; this
0x14013c70e  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013c715  mov     edx, 0BCBh; void *
0x14013c71a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013c720  lea     rcx, ?g_Module@@3VComputeServiceModule@@A; ComputeServiceModule g_Module
0x14013c727  call    ?GetServiceName@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(void)
0x14013c72c  mov     r8d, 10000h; dwDesiredAccess
0x14013c732  mov     rdx, rax; lpServiceName
0x14013c735  mov     rcx, rbx; hSCManager
0x14013c738  call    cs:__imp_OpenServiceW
0x14013c73f  nop     dword ptr [rax+rax+00h]
0x14013c744  mov     rdi, rax
0x14013c747  mov     [rsp+28h+arg_0], rax
0x14013c74c  test    rax, rax
0x14013c74f  jz      short loc_14013C7A5
0x14013c751  mov     rcx, rax; hService
0x14013c754  call    cs:__imp_DeleteService
0x14013c75b  nop     dword ptr [rax+rax+00h]
0x14013c760  mov     rcx, [rsp+28h]; this
0x14013c765  test    eax, eax
0x14013c767  jnz     short loc_14013C77A
0x14013c769  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013c770  mov     edx, 0BD4h; void *
0x14013c775  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013c77a  mov     rcx, rdi; hSCObject
0x14013c77d  call    cs:__imp_CloseServiceHandle
0x14013c784  nop     dword ptr [rax+rax+00h]
0x14013c789  mov     rcx, rbx; hSCObject
0x14013c78c  call    cs:__imp_CloseServiceHandle
0x14013c793  nop     dword ptr [rax+rax+00h]
0x14013c798  nop
0x14013c799  mov     rbx, [rsp+28h+arg_10]
0x14013c79e  add     rsp, 20h
0x14013c7a2  pop     rdi
0x14013c7a3  retn
0x14013c7a5  call    cs:__imp_GetLastError
0x14013c7ac  nop     dword ptr [rax+rax+00h]
0x14013c7b1  nop
0x14013c7b2  cmp     eax, 424h
0x14013c7b7  jz      short loc_14013C789
0x14013c7b9  mov     rcx, [rsp+28h]; this
0x14013c7be  mov     r9d, eax; char *
0x14013c7c1  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x14013c7c8  mov     edx, 0BDDh; void *
0x14013c7cd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
