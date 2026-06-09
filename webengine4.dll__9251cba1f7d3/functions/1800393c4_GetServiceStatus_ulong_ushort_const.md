# GetServiceStatus(ulong *,ushort const *)

- ea: `0x1800393c4`
- end: `0x1800395b4`
- name: `?GetServiceStatus@@YAJPEAKPEBG@Z`
- size: `496`
- prototype: `int(unsigned int *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800293d0`
- `0x18003c1e8`
- `0x18003ef38`

## callees

- `0x1800393c4`
- `0x18003abe4`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18003957d`
- `ADVAPI32!CloseServiceHandle` at `0x18003958b`
- `ADVAPI32!CloseServiceHandle` at `0x18003957d`
- `ADVAPI32!CloseServiceHandle` at `0x18003958b`
- `ADVAPI32!OpenSCManagerW` at `0x18003943a`
- `ADVAPI32!OpenSCManagerW` at `0x18003943a`
- `ADVAPI32!OpenServiceW` at `0x18003949e`
- `ADVAPI32!OpenServiceW` at `0x18003949e`
- `ADVAPI32!QueryServiceStatus` at `0x18003951f`
- `ADVAPI32!QueryServiceStatus` at `0x18003951f`

## string_xrefs

- `0x180039500`: `Finding out service state`
- `0x180039530`: `Finding out service state`
- `0x180039507`: `QueryServiceStatus`
- `0x18003953f`: `QueryServiceStatus`
- `0x1800393ee`: `Querying status of a service: `
- `0x180039558`: `Querying status of a service: `
- `0x1800393f8`: `GetServiceStatus`
- `0x180039567`: `GetServiceStatus`
- `0x180039413`: `Connecting to Service Manager`
- `0x18003944f`: `Connecting to Service Manager`
- `0x180039425`: `OpenSCManager`
- `0x18003945e`: `OpenSCManager`
- `0x180039474`: `Opening Service handle`
- `0x1800394bd`: `Opening Service handle`
- `0x1800394db`: `Opening Service handle`
- `0x180039483`: `OpenService`
- `0x1800394c8`: `OpenService`
- `0x1800394ea`: `OpenService`

## pseudocode

```c
__int64 __fastcall GetServiceStatus(unsigned int *a1, const unsigned __int16 *a2)
{
  unsigned int LastWin32Error; // ebx
  SC_HANDLE v5; // rdi
  SC_HANDLE v6; // rsi
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  LastWin32Error = 0;
  v5 = 0;
  CSetupLogging::Log(1, "GetServiceStatus", 0, "Querying status of a service: ", a2);
  *a1 = 1;
  CSetupLogging::Log(1, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  v6 = OpenSCManagerW(0, 0, 1u);
  if ( !v6 )
    LastWin32Error = GetLastWin32Error();
  CSetupLogging::Log(LastWin32Error, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  if ( !LastWin32Error )
  {
    CSetupLogging::Log(1, "OpenService", 0, "Opening Service handle", 0);
    v5 = OpenServiceW(v6, a2, 0xA4u);
    if ( v5 )
    {
      CSetupLogging::Log(0, "OpenService", 0, "Opening Service handle", 0);
      CSetupLogging::Log(1, "QueryServiceStatus", 0, "Finding out service state", 0);
      if ( !QueryServiceStatus(v5, &ServiceStatus) )
        LastWin32Error = GetLastWin32Error();
      CSetupLogging::Log(LastWin32Error, "QueryServiceStatus", 0, "Finding out service state", 0);
      if ( !LastWin32Error )
        *a1 = ServiceStatus.dwCurrentState;
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
      if ( LastWin32Error == -2147023836 )
        LastWin32Error = 0;
      CSetupLogging::Log(LastWin32Error, "OpenService", 0, "Opening Service handle", 0);
    }
  }
  CSetupLogging::Log(LastWin32Error, "GetServiceStatus", 0, "Querying status of a service: ", a2);
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v6 )
    CloseServiceHandle(v6);
  return LastWin32Error;
}

```

## disassembly

```asm
0x1800393c4  mov     [rsp+arg_10], rbx
0x1800393c9  push    rbp
0x1800393ca  push    rsi
0x1800393cb  push    rdi
0x1800393cc  push    r14
0x1800393ce  push    r15
0x1800393d0  sub     rsp, 60h
0x1800393d4  mov     rax, cs:__security_cookie
0x1800393db  xor     rax, rsp
0x1800393de  mov     [rsp+88h+var_38], rax
0x1800393e3  xor     r15d, r15d
0x1800393e6  mov     [rsp+88h+var_68], rdx; unsigned __int16 *
0x1800393eb  mov     rbp, rdx
0x1800393ee  lea     r9, aQueryingStatus; "Querying status of a service: "
0x1800393f5  mov     r14, rcx
0x1800393f8  lea     rdx, aGetservicestat; "GetServiceStatus"
0x1800393ff  xor     r8d, r8d; unsigned int
0x180039402  mov     ebx, r15d
0x180039405  lea     esi, [r15+1]
0x180039409  mov     edi, r15d
0x18003940c  mov     ecx, esi; int
0x18003940e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039413  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003941a  mov     [r14], esi
0x18003941d  xor     r8d, r8d; unsigned int
0x180039420  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x180039425  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003942c  mov     ecx, esi; int
0x18003942e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039433  mov     r8d, esi; dwDesiredAccess
0x180039436  xor     edx, edx; lpDatabaseName
0x180039438  xor     ecx, ecx; lpMachineName
0x18003943a  call    cs:__imp_OpenSCManagerW
0x180039440  mov     rsi, rax
0x180039443  test    rax, rax
0x180039446  jnz     short loc_18003944F
0x180039448  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003944d  mov     ebx, eax
0x18003944f  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x180039456  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x18003945b  xor     r8d, r8d; unsigned int
0x18003945e  lea     rdx, aOpenscmanager; "OpenSCManager"
0x180039465  mov     ecx, ebx; int
0x180039467  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003946c  test    ebx, ebx
0x18003946e  jnz     loc_180039558
0x180039474  lea     r9, aOpeningService; "Opening Service handle"
0x18003947b  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x180039480  xor     r8d, r8d; unsigned int
0x180039483  lea     rdx, aOpenservice; "OpenService"
0x18003948a  lea     ecx, [rbx+1]; int
0x18003948d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039492  mov     r8d, 0A4h; dwDesiredAccess
0x180039498  mov     rdx, rbp; lpServiceName
0x18003949b  mov     rcx, rsi; hSCManager
0x18003949e  call    cs:__imp_OpenServiceW
0x1800394a4  mov     rdi, rax
0x1800394a7  test    rax, rax
0x1800394aa  jnz     short loc_1800394DB
0x1800394ac  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800394b1  cmp     eax, 80070424h
0x1800394b6  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x1800394bb  mov     ebx, eax
0x1800394bd  lea     r9, aOpeningService; "Opening Service handle"
0x1800394c4  cmovz   ebx, r15d
0x1800394c8  lea     rdx, aOpenservice; "OpenService"
0x1800394cf  mov     ecx, ebx; int
0x1800394d1  xor     r8d, r8d; unsigned int
0x1800394d4  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800394d9  jmp     short loc_180039558
0x1800394db  lea     r9, aOpeningService; "Opening Service handle"
0x1800394e2  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x1800394e7  xor     r8d, r8d; unsigned int
0x1800394ea  lea     rdx, aOpenservice; "OpenService"
0x1800394f1  xor     ecx, ecx; int
0x1800394f3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x1800394f8  xor     r8d, r8d; unsigned int
0x1800394fb  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x180039500  lea     r9, aFindingOutServ; "Finding out service state"
0x180039507  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x18003950e  lea     ecx, [r8+1]; int
0x180039512  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039517  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18003951c  mov     rcx, rdi; hService
0x18003951f  call    cs:__imp_QueryServiceStatus
0x180039525  test    eax, eax
0x180039527  jnz     short loc_180039530
0x180039529  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003952e  mov     ebx, eax
0x180039530  lea     r9, aFindingOutServ; "Finding out service state"
0x180039537  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x18003953c  xor     r8d, r8d; unsigned int
0x18003953f  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x180039546  mov     ecx, ebx; int
0x180039548  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003954d  test    ebx, ebx
0x18003954f  jnz     short loc_180039558
0x180039551  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x180039555  mov     [r14], eax
0x180039558  lea     r9, aQueryingStatus; "Querying status of a service: "
0x18003955f  mov     [rsp+88h+var_68], rbp; unsigned __int16 *
0x180039564  xor     r8d, r8d; unsigned int
0x180039567  lea     rdx, aGetservicestat; "GetServiceStatus"
0x18003956e  mov     ecx, ebx; int
0x180039570  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180039575  test    rdi, rdi
0x180039578  jz      short loc_180039583
0x18003957a  mov     rcx, rdi; hSCObject
0x18003957d  call    cs:__imp_CloseServiceHandle
0x180039583  test    rsi, rsi
0x180039586  jz      short loc_180039591
0x180039588  mov     rcx, rsi; hSCObject
0x18003958b  call    cs:__imp_CloseServiceHandle
0x180039591  mov     eax, ebx
0x180039593  mov     rcx, [rsp+88h+var_38]
0x180039598  xor     rcx, rsp; StackCookie
0x18003959b  call    __security_check_cookie
0x1800395a0  mov     rbx, [rsp+88h+arg_10]
0x1800395a8  add     rsp, 60h
0x1800395ac  pop     r15
0x1800395ae  pop     r14
0x1800395b0  pop     rdi
0x1800395b1  pop     rsi
0x1800395b2  pop     rbp
0x1800395b3  retn
```
