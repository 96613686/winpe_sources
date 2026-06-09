# StopSingleService(SC_HANDLE__ *,SC_HANDLE__ *,ulong *)

- ea: `0x18003e494`
- end: `0x18003e648`
- name: `?StopSingleService@@YAJPEAUSC_HANDLE__@@0PEAK@Z`
- size: `436`
- prototype: `int(struct SC_HANDLE__ *, struct SC_HANDLE__ *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18003dfc0`
- `0x18003e2e8`

## callees

- `0x18003abe4`
- `0x18003e494`
- `0x18003ff7c`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!ControlService` at `0x18003e583`
- `ADVAPI32!ControlService` at `0x18003e583`
- `ADVAPI32!QueryServiceStatus` at `0x18003e515`
- `ADVAPI32!QueryServiceStatus` at `0x18003e5a6`
- `ADVAPI32!QueryServiceStatus` at `0x18003e515`
- `ADVAPI32!QueryServiceStatus` at `0x18003e5a6`

## string_xrefs

- `0x18003e4b8`: `Stopping service`
- `0x18003e60b`: `Stopping service`
- `0x18003e4cd`: `StopSingleService`
- `0x18003e615`: `StopSingleService`
- `0x18003e4e8`: `Finding out service state`
- `0x18003e52c`: `Finding out service state`
- `0x18003e4f6`: `QueryServiceStatus`
- `0x18003e536`: `QueryServiceStatus`
- `0x18003e559`: `Shutting down service`
- `0x18003e560`: `ControlService`

## pseudocode

```c
__int64 __fastcall StopSingleService(struct SC_HANDLE__ *a1, SC_HANDLE a2, unsigned int *a3)
{
  unsigned int LastWin32Error; // edi
  unsigned int *v6; // r14
  char v8; // [rsp+30h] [rbp-48h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-40h] BYREF

  LastWin32Error = 0;
  CSetupLogging::Log(1, "StopSingleService", 0, "Stopping service", 0);
  v6 = (unsigned int *)&v8;
  if ( a3 )
    v6 = a3;
  *v6 = 1;
  CSetupLogging::Log(1, "QueryServiceStatus", 0, "Finding out service state", 0);
  if ( !QueryServiceStatus(a2, &ServiceStatus) )
    LastWin32Error = GetLastWin32Error();
  CSetupLogging::Log(LastWin32Error, "QueryServiceStatus", 0, "Finding out service state", 0);
  if ( LastWin32Error )
    LastWin32Error = 0;
  else
    *v6 = ServiceStatus.dwCurrentState;
  CSetupLogging::Log(1, "ControlService", 0, "Shutting down service", 0);
  if ( ControlService(a2, 1u, &ServiceStatus) )
    goto LABEL_16;
  LastWin32Error = GetLastWin32Error();
  if ( LastWin32Error + 2147023835 <= 1 )
  {
    if ( QueryServiceStatus(a2, &ServiceStatus) )
    {
      if ( ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
      {
        LastWin32Error = 0;
        goto LABEL_16;
      }
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
    }
  }
  if ( !LastWin32Error )
  {
LABEL_16:
    CSetupLogging::Log(LastWin32Error, "ControlService", 0, "Shutting down service", 0);
    LastWin32Error = WaitForServiceState(a2, 1u);
    goto LABEL_17;
  }
  CSetupLogging::Log(LastWin32Error, "ControlService", 0, "Shutting down service", 0);
LABEL_17:
  CSetupLogging::Log(LastWin32Error, "StopSingleService", 0, "Stopping service", 0);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003e494  mov     [rsp+arg_0], rbx
0x18003e499  mov     [rsp+arg_18], rsi
0x18003e49e  push    rdi
0x18003e49f  push    r14
0x18003e4a1  push    r15
0x18003e4a3  sub     rsp, 60h
0x18003e4a7  mov     rax, cs:__security_cookie
0x18003e4ae  xor     rax, rsp
0x18003e4b1  mov     [rsp+78h+var_20], rax
0x18003e4b6  xor     edi, edi
0x18003e4b8  lea     r9, aStoppingServic_0; "Stopping service"
0x18003e4bf  and     [rsp+78h+var_58], rdi
0x18003e4c4  mov     rbx, r8
0x18003e4c7  mov     rsi, rdx
0x18003e4ca  xor     r8d, r8d; unsigned int
0x18003e4cd  lea     rdx, aStopsingleserv; "StopSingleService"
0x18003e4d4  lea     r15d, [rdi+1]
0x18003e4d8  mov     ecx, r15d; int
0x18003e4db  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e4e0  test    rbx, rbx
0x18003e4e3  lea     r14, [rsp+78h+var_48]
0x18003e4e8  lea     r9, aFindingOutServ; "Finding out service state"
0x18003e4ef  mov     ecx, r15d; int
0x18003e4f2  cmovnz  r14, rbx
0x18003e4f6  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x18003e4fd  and     [rsp+78h+var_58], rdi
0x18003e502  xor     r8d, r8d; unsigned int
0x18003e505  mov     [r14], r15d
0x18003e508  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e50d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003e512  mov     rcx, rsi; hService
0x18003e515  call    cs:__imp_QueryServiceStatus
0x18003e51b  test    eax, eax
0x18003e51d  jnz     short loc_18003E526
0x18003e51f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e524  mov     edi, eax
0x18003e526  and     [rsp+78h+var_58], 0
0x18003e52c  lea     r9, aFindingOutServ; "Finding out service state"
0x18003e533  xor     r8d, r8d; unsigned int
0x18003e536  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x18003e53d  mov     ecx, edi; int
0x18003e53f  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e544  test    edi, edi
0x18003e546  jnz     short loc_18003E551
0x18003e548  mov     ecx, [rsp+78h+ServiceStatus.dwCurrentState]
0x18003e54c  mov     [r14], ecx
0x18003e54f  jmp     short loc_18003E553
0x18003e551  xor     edi, edi
0x18003e553  and     [rsp+78h+var_58], 0
0x18003e559  lea     rbx, aShuttingDownSe; "Shutting down service"
0x18003e560  lea     r14, aControlservice_0; "ControlService"
0x18003e567  mov     r9, rbx; char *
0x18003e56a  mov     rdx, r14; char *
0x18003e56d  xor     r8d, r8d; unsigned int
0x18003e570  mov     ecx, r15d; int
0x18003e573  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e578  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003e57d  mov     edx, r15d; dwControl
0x18003e580  mov     rcx, rsi; hService
0x18003e583  call    cs:__imp_ControlService
0x18003e589  test    eax, eax
0x18003e58b  jnz     short loc_18003E5E2
0x18003e58d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e592  mov     edi, eax
0x18003e594  add     eax, 7FF8FBDBh
0x18003e599  cmp     eax, r15d
0x18003e59c  ja      short loc_18003E5B7
0x18003e59e  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003e5a3  mov     rcx, rsi; hService
0x18003e5a6  call    cs:__imp_QueryServiceStatus
0x18003e5ac  test    eax, eax
0x18003e5ae  jnz     short loc_18003E5D3
0x18003e5b0  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e5b5  mov     edi, eax
0x18003e5b7  test    edi, edi
0x18003e5b9  jz      short loc_18003E5E2
0x18003e5bb  and     [rsp+78h+var_58], 0
0x18003e5c1  mov     r9, rbx; char *
0x18003e5c4  xor     r8d, r8d; unsigned int
0x18003e5c7  mov     rdx, r14; char *
0x18003e5ca  mov     ecx, edi; int
0x18003e5cc  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e5d1  jmp     short loc_18003E605
0x18003e5d3  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18003e5d7  dec     eax
0x18003e5d9  test    eax, 0FFFFFFFDh
0x18003e5de  jnz     short loc_18003E5B7
0x18003e5e0  xor     edi, edi
0x18003e5e2  and     [rsp+78h+var_58], 0
0x18003e5e8  mov     r9, rbx; char *
0x18003e5eb  xor     r8d, r8d; unsigned int
0x18003e5ee  mov     rdx, r14; char *
0x18003e5f1  mov     ecx, edi; int
0x18003e5f3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e5f8  mov     edx, r15d; dwControl
0x18003e5fb  mov     rcx, rsi; hService
0x18003e5fe  call    ?WaitForServiceState@@YAJPEAUSC_HANDLE__@@K@Z; WaitForServiceState(SC_HANDLE__ *,ulong)
0x18003e603  mov     edi, eax
0x18003e605  and     [rsp+78h+var_58], 0
0x18003e60b  lea     r9, aStoppingServic_0; "Stopping service"
0x18003e612  xor     r8d, r8d; unsigned int
0x18003e615  lea     rdx, aStopsingleserv; "StopSingleService"
0x18003e61c  mov     ecx, edi; int
0x18003e61e  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e623  mov     eax, edi
0x18003e625  mov     rcx, [rsp+78h+var_20]
0x18003e62a  xor     rcx, rsp; StackCookie
0x18003e62d  call    __security_check_cookie
0x18003e632  lea     r11, [rsp+78h+var_18]
0x18003e637  mov     rbx, [r11+20h]
0x18003e63b  mov     rsi, [r11+38h]
0x18003e63f  mov     rsp, r11
0x18003e642  pop     r15
0x18003e644  pop     r14
0x18003e646  pop     rdi
0x18003e647  retn
```
