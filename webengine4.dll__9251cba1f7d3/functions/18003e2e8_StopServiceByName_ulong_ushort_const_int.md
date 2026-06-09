# StopServiceByName(ulong *,ushort const *,int *)

- ea: `0x18003e2e8`
- end: `0x18003e492`
- name: `?StopServiceByName@@YAJPEAKPEBGPEAH@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18003c1e8`
- `0x18003ef38`

## callees

- `0x18003abe4`
- `0x18003e2e8`
- `0x18003e494`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18003e465`
- `ADVAPI32!CloseServiceHandle` at `0x18003e473`
- `ADVAPI32!CloseServiceHandle` at `0x18003e465`
- `ADVAPI32!CloseServiceHandle` at `0x18003e473`
- `ADVAPI32!OpenSCManagerW` at `0x18003e369`
- `ADVAPI32!OpenSCManagerW` at `0x18003e369`
- `ADVAPI32!OpenServiceW` at `0x18003e3cd`
- `ADVAPI32!OpenServiceW` at `0x18003e3cd`

## string_xrefs

- `0x18003e33d`: `Connecting to Service Manager`
- `0x18003e383`: `Connecting to Service Manager`
- `0x18003e34b`: `OpenSCManager`
- `0x18003e38d`: `OpenSCManager`
- `0x18003e3a8`: `Opening Service handle`
- `0x18003e3f8`: `Opening Service handle`
- `0x18003e418`: `Opening Service handle`
- `0x18003e3b2`: `OpenService`
- `0x18003e402`: `OpenService`
- `0x18003e422`: `OpenService`
- `0x18003e317`: `Stopping service: `
- `0x18003e440`: `Stopping service: `
- `0x18003e326`: `StopServiceByName`
- `0x18003e44f`: `StopServiceByName`

## pseudocode

```c
__int64 __fastcall StopServiceByName(unsigned int *a1, const unsigned __int16 *a2, int *a3)
{
  unsigned int LastWin32Error; // ebx
  SC_HANDLE v4; // rsi
  unsigned int *v8; // r15
  SC_HANDLE v9; // rbp
  char v11; // [rsp+60h] [rbp+8h] BYREF

  LastWin32Error = 0;
  v4 = 0;
  if ( a3 )
    *a3 = 1;
  CSetupLogging::Log(1, "StopServiceByName", 0, "Stopping service: ", a2);
  v8 = (unsigned int *)&v11;
  if ( a1 )
    v8 = a1;
  *v8 = 1;
  CSetupLogging::Log(1, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  v9 = OpenSCManagerW(0, 0, 1u);
  if ( !v9 )
    LastWin32Error = GetLastWin32Error();
  CSetupLogging::Log(LastWin32Error, "OpenSCManager", 0, "Connecting to Service Manager", 0);
  if ( !LastWin32Error )
  {
    CSetupLogging::Log(1, "OpenService", 0, "Opening Service handle", 0);
    v4 = OpenServiceW(v9, a2, 0xA4u);
    if ( v4 )
    {
      CSetupLogging::Log(0, "OpenService", 0, "Opening Service handle", 0);
      LastWin32Error = StopSingleService(v9, v4, v8);
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
      if ( LastWin32Error == -2147023836 )
      {
        if ( a3 )
          *a3 = 0;
        LastWin32Error = 0;
      }
      CSetupLogging::Log(LastWin32Error, "OpenService", 0, "Opening Service handle", 0);
    }
  }
  CSetupLogging::Log(LastWin32Error, "StopServiceByName", 0, "Stopping service: ", a2);
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v9 )
    CloseServiceHandle(v9);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003e2e8  mov     [rsp+arg_8], rbx
0x18003e2ed  mov     [rsp+arg_10], rbp
0x18003e2f2  push    rsi
0x18003e2f3  push    rdi
0x18003e2f4  push    r13
0x18003e2f6  push    r14
0x18003e2f8  push    r15
0x18003e2fa  sub     rsp, 30h
0x18003e2fe  xor     ebx, ebx
0x18003e300  xor     esi, esi
0x18003e302  mov     rdi, r8
0x18003e305  mov     r14, rdx
0x18003e308  mov     rbp, rcx
0x18003e30b  lea     r13d, [rbx+1]
0x18003e30f  test    r8, r8
0x18003e312  jz      short loc_18003E317
0x18003e314  mov     [r8], r13d
0x18003e317  lea     r9, aStoppingServic; "Stopping service: "
0x18003e31e  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x18003e323  xor     r8d, r8d; unsigned int
0x18003e326  lea     rdx, aStopservicebyn; "StopServiceByName"
0x18003e32d  mov     ecx, r13d; int
0x18003e330  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e335  test    rbp, rbp
0x18003e338  lea     r15, [rsp+58h+arg_0]
0x18003e33d  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003e344  mov     ecx, r13d; int
0x18003e347  cmovnz  r15, rbp
0x18003e34b  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003e352  and     [rsp+58h+var_38], rbx
0x18003e357  xor     r8d, r8d; unsigned int
0x18003e35a  mov     [r15], r13d
0x18003e35d  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e362  mov     r8d, r13d; dwDesiredAccess
0x18003e365  xor     edx, edx; lpDatabaseName
0x18003e367  xor     ecx, ecx; lpMachineName
0x18003e369  call    cs:__imp_OpenSCManagerW
0x18003e36f  mov     rbp, rax
0x18003e372  test    rax, rax
0x18003e375  jnz     short loc_18003E37E
0x18003e377  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e37c  mov     ebx, eax
0x18003e37e  and     [rsp+58h+var_38], rsi
0x18003e383  lea     r9, aConnectingToSe; "Connecting to Service Manager"
0x18003e38a  xor     r8d, r8d; unsigned int
0x18003e38d  lea     rdx, aOpenscmanager; "OpenSCManager"
0x18003e394  mov     ecx, ebx; int
0x18003e396  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e39b  test    ebx, ebx
0x18003e39d  jnz     loc_18003E440
0x18003e3a3  and     [rsp+58h+var_38], rsi
0x18003e3a8  lea     r9, aOpeningService; "Opening Service handle"
0x18003e3af  xor     r8d, r8d; unsigned int
0x18003e3b2  lea     rdx, aOpenservice; "OpenService"
0x18003e3b9  mov     ecx, r13d; int
0x18003e3bc  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e3c1  mov     r8d, 0A4h; dwDesiredAccess
0x18003e3c7  mov     rdx, r14; lpServiceName
0x18003e3ca  mov     rcx, rbp; hSCManager
0x18003e3cd  call    cs:__imp_OpenServiceW
0x18003e3d3  mov     rsi, rax
0x18003e3d6  test    rax, rax
0x18003e3d9  jnz     short loc_18003E412
0x18003e3db  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e3e0  mov     ebx, eax
0x18003e3e2  cmp     eax, 80070424h
0x18003e3e7  jnz     short loc_18003E3F2
0x18003e3e9  test    rdi, rdi
0x18003e3ec  jz      short loc_18003E3F0
0x18003e3ee  and     [rdi], esi
0x18003e3f0  xor     ebx, ebx
0x18003e3f2  and     [rsp+58h+var_38], 0
0x18003e3f8  lea     r9, aOpeningService; "Opening Service handle"
0x18003e3ff  xor     r8d, r8d; unsigned int
0x18003e402  lea     rdx, aOpenservice; "OpenService"
0x18003e409  mov     ecx, ebx; int
0x18003e40b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e410  jmp     short loc_18003E440
0x18003e412  and     [rsp+58h+var_38], 0
0x18003e418  lea     r9, aOpeningService; "Opening Service handle"
0x18003e41f  xor     r8d, r8d; unsigned int
0x18003e422  lea     rdx, aOpenservice; "OpenService"
0x18003e429  xor     ecx, ecx; int
0x18003e42b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e430  mov     r8, r15; unsigned int *
0x18003e433  mov     rdx, rsi; struct SC_HANDLE__ *
0x18003e436  mov     rcx, rbp; struct SC_HANDLE__ *
0x18003e439  call    ?StopSingleService@@YAJPEAUSC_HANDLE__@@0PEAK@Z; StopSingleService(SC_HANDLE__ *,SC_HANDLE__ *,ulong *)
0x18003e43e  mov     ebx, eax
0x18003e440  lea     r9, aStoppingServic; "Stopping service: "
0x18003e447  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x18003e44c  xor     r8d, r8d; unsigned int
0x18003e44f  lea     rdx, aStopservicebyn; "StopServiceByName"
0x18003e456  mov     ecx, ebx; int
0x18003e458  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e45d  test    rsi, rsi
0x18003e460  jz      short loc_18003E46B
0x18003e462  mov     rcx, rsi; hSCObject
0x18003e465  call    cs:__imp_CloseServiceHandle
0x18003e46b  test    rbp, rbp
0x18003e46e  jz      short loc_18003E479
0x18003e470  mov     rcx, rbp; hSCObject
0x18003e473  call    cs:__imp_CloseServiceHandle
0x18003e479  mov     rbp, [rsp+58h+arg_10]
0x18003e47e  mov     eax, ebx
0x18003e480  mov     rbx, [rsp+58h+arg_8]
0x18003e485  add     rsp, 30h
0x18003e489  pop     r15
0x18003e48b  pop     r14
0x18003e48d  pop     r13
0x18003e48f  pop     rdi
0x18003e490  pop     rsi
0x18003e491  retn
```
