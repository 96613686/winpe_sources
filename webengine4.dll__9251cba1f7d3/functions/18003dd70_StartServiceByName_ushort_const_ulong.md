# StartServiceByName(ushort const *,ulong)

- ea: `0x18003dd70`
- end: `0x18003dfc0`
- name: `?StartServiceByName@@YAJPEBGK@Z`
- size: `592`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18003c1e8`
- `0x18003ccd4`
- `0x18003ef38`

## callees

- `0x18003abe4`
- `0x18003dd70`
- `0x18003ff7c`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18003df83`
- `ADVAPI32!CloseServiceHandle` at `0x18003df91`
- `ADVAPI32!CloseServiceHandle` at `0x18003df83`
- `ADVAPI32!CloseServiceHandle` at `0x18003df91`
- `ADVAPI32!ControlService` at `0x18003df2f`
- `ADVAPI32!ControlService` at `0x18003df2f`
- `ADVAPI32!OpenSCManagerW` at `0x18003ddf6`
- `ADVAPI32!OpenSCManagerW` at `0x18003ddf6`
- `ADVAPI32!OpenServiceW` at `0x18003de5a`
- `ADVAPI32!OpenServiceW` at `0x18003de5a`
- `ADVAPI32!StartServiceW` at `0x18003debc`
- `ADVAPI32!StartServiceW` at `0x18003debc`

## string_xrefs

- `0x18003df15`: `ControlService`
- `0x18003df50`: `ControlService`
- `0x18003ddd6`: `Connecting to Service Manager`
- `0x18003de10`: `Connecting to Service Manager`
- `0x18003dde0`: `OpenSCManager`
- `0x18003de1a`: `OpenSCManager`
- `0x18003de35`: `Opening Service handle`
- `0x18003de75`: `Opening Service handle`
- `0x18003de3f`: `OpenService`
- `0x18003de7f`: `OpenService`
- `0x18003dda0`: `Starting service: `
- `0x18003df5e`: `Starting service: `
- `0x18003dda9`: `StartServiceByName`
- `0x18003df6d`: `StartServiceByName`
- `0x18003de9b`: `Starting service`
- `0x18003ded3`: `Starting service`
- `0x18003dea5`: `StartService`
- `0x18003dedd`: `StartService`
- `0x18003df0b`: `Pausing service`
- `0x18003df46`: `Pausing service`

## pseudocode

```c
__int64 __fastcall StartServiceByName(const unsigned __int16 *a1, int a2)
{
  unsigned int LastWin32Error; // ebx
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-48h] BYREF

  LastWin32Error = 0;
  v5 = 0;
  v6 = 0;
  CSetupLogging::Log(1, "StartServiceByName", 0, "Starting service: ", a1);
  if ( a2 == 4 || a2 == 7 )
  {
    CSetupLogging::Log(1, "OpenSCManager", 0, "Connecting to Service Manager", 0);
    v5 = OpenSCManagerW(0, 0, 1u);
    if ( !v5 )
      LastWin32Error = GetLastWin32Error();
    CSetupLogging::Log(LastWin32Error, "OpenSCManager", 0, "Connecting to Service Manager", 0);
    if ( !LastWin32Error )
    {
      CSetupLogging::Log(1, "OpenService", 0, "Opening Service handle", 0);
      v6 = OpenServiceW(v5, a1, 0xD4u);
      if ( !v6 )
        LastWin32Error = GetLastWin32Error();
      CSetupLogging::Log(LastWin32Error, "OpenService", 0, "Opening Service handle", 0);
      if ( !LastWin32Error )
      {
        CSetupLogging::Log(1, "StartService", 0, "Starting service", 0);
        if ( !StartServiceW(v6, 0, 0) )
          LastWin32Error = GetLastWin32Error();
        CSetupLogging::Log(LastWin32Error, "StartService", 0, "Starting service", 0);
        if ( !LastWin32Error )
        {
          LastWin32Error = WaitForServiceState(v6, 4u);
          if ( !LastWin32Error && a2 == 7 )
          {
            CSetupLogging::Log(1, "ControlService", 0, "Pausing service", 0);
            if ( !ControlService(v6, 2u, &ServiceStatus) )
              LastWin32Error = GetLastWin32Error();
            CSetupLogging::Log(LastWin32Error, "ControlService", 0, "Pausing service", 0);
          }
        }
      }
    }
  }
  CSetupLogging::Log(LastWin32Error, "StartServiceByName", 0, "Starting service: ", a1);
  if ( v6 )
    CloseServiceHandle(v6);
  if ( v5 )
    CloseServiceHandle(v5);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003dd70  mov     r11, rsp
0x18003dd73  mov     [r11+10h], rbx
0x18003dd77  mov     [r11+18h], rbp
0x18003dd7b  mov     [r11+20h], rsi
0x18003dd7f  push    rdi
0x18003dd80  push    r12
0x18003dd82  push    r14
0x18003dd84  sub     rsp, 60h
0x18003dd88  mov     rax, cs:__security_cookie
0x18003dd8f  xor     rax, rsp
0x18003dd92  mov     [rsp+78h+var_28], rax
0x18003dd97  mov     ebp, edx
0x18003dd99  mov     [r11-58h], rcx
0x18003dd9d  mov     r14, rcx
0x18003dda0  lea     r9, aStartingServic_0; "Starting service: "
0x18003dda7  xor     ebx, ebx
0x18003dda9  lea     rdx, aStartserviceby; "StartServiceByName"
0x18003ddb0  xor     r8d, r8d; unsigned int
0x18003ddb3  xor     esi, esi
0x18003ddb5  xor     edi, edi
0x18003ddb7  lea     r12d, [rbx+1]
0x18003ddbb  mov     ecx, r12d; int
0x18003ddbe  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ddc3  cmp     ebp, 4
0x18003ddc6  jz      short loc_18003DDD1
0x18003ddc8  cmp     ebp, 7
0x18003ddcb  jnz     loc_18003DF5E
0x18003ddd1  and     [rsp+78h+var_58], rbx
0x18003ddd6  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003dddd  xor     r8d, r8d; unsigned int
0x18003dde0  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003dde7  mov     ecx, r12d; int
0x18003ddea  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ddef  mov     r8d, r12d; dwDesiredAccess
0x18003ddf2  xor     edx, edx; lpDatabaseName
0x18003ddf4  xor     ecx, ecx; lpMachineName
0x18003ddf6  call    cs:__imp_OpenSCManagerW
0x18003ddfc  mov     rsi, rax
0x18003ddff  test    rax, rax
0x18003de02  jnz     short loc_18003DE0B
0x18003de04  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003de09  mov     ebx, eax
0x18003de0b  and     [rsp+78h+var_58], rdi
0x18003de10  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003de17  xor     r8d, r8d; unsigned int
0x18003de1a  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003de21  mov     ecx, ebx; int
0x18003de23  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003de28  test    ebx, ebx
0x18003de2a  jnz     loc_18003DF5E
0x18003de30  and     [rsp+78h+var_58], rdi
0x18003de35  lea     r9, aOpeningService; "Opening Service handle"
0x18003de3c  xor     r8d, r8d; unsigned int
0x18003de3f  lea     rdx, aOpenservice; "OpenService"
0x18003de46  mov     ecx, r12d; int
0x18003de49  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003de4e  mov     r8d, 0D4h; dwDesiredAccess
0x18003de54  mov     rdx, r14; lpServiceName
0x18003de57  mov     rcx, rsi; hSCManager
0x18003de5a  call    cs:__imp_OpenServiceW
0x18003de60  mov     rdi, rax
0x18003de63  test    rax, rax
0x18003de66  jnz     short loc_18003DE6F
0x18003de68  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003de6d  mov     ebx, eax
0x18003de6f  and     [rsp+78h+var_58], 0
0x18003de75  lea     r9, aOpeningService; "Opening Service handle"
0x18003de7c  xor     r8d, r8d; unsigned int
0x18003de7f  lea     rdx, aOpenservice; "OpenService"
0x18003de86  mov     ecx, ebx; int
0x18003de88  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003de8d  test    ebx, ebx
0x18003de8f  jnz     loc_18003DF5E
0x18003de95  and     [rsp+78h+var_58], 0
0x18003de9b  lea     r9, aStartingServic; "Starting service"
0x18003dea2  xor     r8d, r8d; unsigned int
0x18003dea5  lea     rdx, aStartservice; "StartService"
0x18003deac  mov     ecx, r12d; int
0x18003deaf  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003deb4  xor     r8d, r8d; lpServiceArgVectors
0x18003deb7  xor     edx, edx; dwNumServiceArgs
0x18003deb9  mov     rcx, rdi; hService
0x18003debc  call    cs:__imp_StartServiceW
0x18003dec2  test    eax, eax
0x18003dec4  jnz     short loc_18003DECD
0x18003dec6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003decb  mov     ebx, eax
0x18003decd  and     [rsp+78h+var_58], 0
0x18003ded3  lea     r9, aStartingServic; "Starting service"
0x18003deda  xor     r8d, r8d; unsigned int
0x18003dedd  lea     rdx, aStartservice; "StartService"
0x18003dee4  mov     ecx, ebx; int
0x18003dee6  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003deeb  test    ebx, ebx
0x18003deed  jnz     short loc_18003DF5E
0x18003deef  lea     edx, [rbx+4]; dwControl
0x18003def2  mov     rcx, rdi; hService
0x18003def5  call    ?WaitForServiceState@@YAJPEAUSC_HANDLE__@@K@Z; WaitForServiceState(SC_HANDLE__ *,ulong)
0x18003defa  mov     ebx, eax
0x18003defc  test    eax, eax
0x18003defe  jnz     short loc_18003DF5E
0x18003df00  cmp     ebp, 7
0x18003df03  jnz     short loc_18003DF5E
0x18003df05  and     [rsp+78h+var_58], 0
0x18003df0b  lea     r9, aPausingService; "Pausing service"
0x18003df12  xor     r8d, r8d; unsigned int
0x18003df15  lea     rdx, aControlservice_0; "ControlService"
0x18003df1c  mov     ecx, r12d; int
0x18003df1f  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003df24  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003df29  mov     rcx, rdi; hService
0x18003df2c  lea     edx, [rbx+2]; dwControl
0x18003df2f  call    cs:__imp_ControlService
0x18003df35  test    eax, eax
0x18003df37  jnz     short loc_18003DF40
0x18003df39  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003df3e  mov     ebx, eax
0x18003df40  and     [rsp+78h+var_58], 0
0x18003df46  lea     r9, aPausingService; "Pausing service"
0x18003df4d  xor     r8d, r8d; unsigned int
0x18003df50  lea     rdx, aControlservice_0; "ControlService"
0x18003df57  mov     ecx, ebx; int
0x18003df59  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003df5e  lea     r9, aStartingServic_0; "Starting service: "
0x18003df65  mov     [rsp+78h+var_58], r14; unsigned __int16 *
0x18003df6a  xor     r8d, r8d; unsigned int
0x18003df6d  lea     rdx, aStartserviceby; "StartServiceByName"
0x18003df74  mov     ecx, ebx; int
0x18003df76  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003df7b  test    rdi, rdi
0x18003df7e  jz      short loc_18003DF89
0x18003df80  mov     rcx, rdi; hSCObject
0x18003df83  call    cs:__imp_CloseServiceHandle
0x18003df89  test    rsi, rsi
0x18003df8c  jz      short loc_18003DF97
0x18003df8e  mov     rcx, rsi; hSCObject
0x18003df91  call    cs:__imp_CloseServiceHandle
0x18003df97  mov     eax, ebx
0x18003df99  mov     rcx, [rsp+78h+var_28]
0x18003df9e  xor     rcx, rsp; StackCookie
0x18003dfa1  call    __security_check_cookie
0x18003dfa6  lea     r11, [rsp+78h+var_18]
0x18003dfab  mov     rbx, [r11+28h]
0x18003dfaf  mov     rbp, [r11+30h]
0x18003dfb3  mov     rsi, [r11+38h]
0x18003dfb7  mov     rsp, r11
0x18003dfba  pop     r14
0x18003dfbc  pop     r12
0x18003dfbe  pop     rdi
0x18003dfbf  retn
```
