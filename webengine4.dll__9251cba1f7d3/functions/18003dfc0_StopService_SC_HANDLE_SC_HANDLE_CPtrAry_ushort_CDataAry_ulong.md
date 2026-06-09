# StopService(SC_HANDLE__ *,SC_HANDLE__ *,CPtrAry<ushort *> *,CDataAry<ulong> *)

- ea: `0x18003dfc0`
- end: `0x18003e2e6`
- name: `?StopService@@YAJPEAUSC_HANDLE__@@0PEAV?$CPtrAry@PEAG@@PEAV?$CDataAry@K@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, struct SC_HANDLE__ *, CImplPtrAry *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18003ccd4`

## callees

- `0x18003abe4`
- `0x18003dfc0`
- `0x18003e494`
- `0x18003ff7c`
- `0x18004d030`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x18004e168`
- `0x18004e650`
- `0x18004e670`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003e129`
- `KERNEL32!GetLastError` at `0x18003e129`
- `ADVAPI32!CloseServiceHandle` at `0x18003e101`
- `ADVAPI32!CloseServiceHandle` at `0x18003e101`
- `ADVAPI32!EnumDependentServicesW` at `0x18003e0b9`
- `ADVAPI32!EnumDependentServicesW` at `0x18003e1ae`
- `ADVAPI32!EnumDependentServicesW` at `0x18003e0b9`
- `ADVAPI32!EnumDependentServicesW` at `0x18003e1ae`
- `ADVAPI32!OpenServiceW` at `0x18003e239`
- `ADVAPI32!OpenServiceW` at `0x18003e239`
- `ADVAPI32!QueryServiceStatus` at `0x18003e022`
- `ADVAPI32!QueryServiceStatus` at `0x18003e022`

## string_xrefs

- `0x18003dff2`: `Finding out service state`
- `0x18003e038`: `Finding out service state`
- `0x18003e002`: `QueryServiceStatus`
- `0x18003e042`: `QueryServiceStatus`
- `0x18003e1f8`: `Opening Service handle`
- `0x18003e254`: `Opening Service handle`
- `0x18003e202`: `OpenService`
- `0x18003e25e`: `OpenService`
- `0x18003e07d`: `Enumerating dependent services`
- `0x18003e087`: `EnumDependentServices`
- `0x18003e0c8`: `EnumDependentServices`
- `0x18003e140`: `EnumDependentServices`
- `0x18003e16f`: `EnumDependentServices`
- `0x18003e1c4`: `EnumDependentServices`

## pseudocode

```c
__int64 __fastcall StopService(struct SC_HANDLE__ *a1, SC_HANDLE a2, CImplPtrAry *this, CImplAry *a4)
{
  unsigned int LastWin32Error; // ebx
  struct _ENUM_SERVICE_STATUSW *v8; // rdi
  SC_HANDLE v9; // r14
  struct _ENUM_SERVICE_STATUSW *v11; // rax
  __int64 v12; // rsi
  unsigned __int16 *v13; // rax
  DWORD cbBufSize; // [rsp+30h] [rbp-59h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-55h] BYREF
  CImplAry *v16; // [rsp+38h] [rbp-51h]
  LPCWSTR lpServiceName[2]; // [rsp+40h] [rbp-49h]
  _OWORD v18[2]; // [rsp+50h] [rbp-39h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-19h] BYREF

  LastWin32Error = 0;
  v16 = a4;
  v8 = 0;
  v9 = 0;
  CSetupLogging::Log(1, "QueryServiceStatus", 0, "Finding out service state", 0);
  if ( !QueryServiceStatus(a2, &ServiceStatus) )
    LastWin32Error = GetLastWin32Error();
  CSetupLogging::Log(LastWin32Error, "QueryServiceStatus", 0, "Finding out service state", 0);
  if ( !LastWin32Error && ServiceStatus.dwCurrentState != 1 )
  {
    if ( ServiceStatus.dwCurrentState == 3 )
      return (unsigned int)WaitForServiceState(a2, 1u);
    CSetupLogging::Log(1, "EnumDependentServices", 0, "Enumerating dependent services", 0);
    if ( EnumDependentServicesW(a2, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
    {
      CSetupLogging::Log(0, "EnumDependentServices", 0, "Enumerating dependent services", 0);
      goto LABEL_9;
    }
    if ( GetLastError() != 234 )
    {
      LastWin32Error = GetLastWin32Error();
      CSetupLogging::Log(LastWin32Error, "EnumDependentServices", 0, "Enumerating dependent services", 0);
      if ( LastWin32Error )
        return LastWin32Error;
    }
    v11 = (struct _ENUM_SERVICE_STATUSW *)MemAllocClear(cbBufSize);
    v8 = v11;
    if ( !v11 )
    {
      LastWin32Error = -2147024882;
      CSetupLogging::Log(-2147024882, "EnumDependentServices", 0, "Enumerating dependent services", 0);
      return LastWin32Error;
    }
    if ( !EnumDependentServicesW(a2, 1u, v11, cbBufSize, &cbBufSize, &ServicesReturned) )
      LastWin32Error = GetLastWin32Error();
    CSetupLogging::Log(LastWin32Error, "EnumDependentServices", 0, "Enumerating dependent services", 0);
    if ( !LastWin32Error )
    {
      v12 = 0;
      if ( !ServicesReturned )
      {
LABEL_9:
        LastWin32Error = StopSingleService(a1, a2, 0);
        if ( !v8 )
          goto LABEL_11;
        goto LABEL_10;
      }
      while ( 1 )
      {
        *(_OWORD *)lpServiceName = *(_OWORD *)&v8[v12].lpServiceName;
        v18[0] = *(_OWORD *)&v8[v12].ServiceStatus.dwServiceType;
        v18[1] = *(_OWORD *)&v8[v12].ServiceStatus.dwServiceSpecificExitCode;
        CSetupLogging::Log(1, "OpenService", 0, "Opening Service handle", 0);
        v9 = OpenServiceW(a1, lpServiceName[0], 0x24u);
        if ( !v9 )
          LastWin32Error = GetLastWin32Error();
        CSetupLogging::Log(LastWin32Error, "OpenService", 0, "Opening Service handle", 0);
        if ( LastWin32Error )
          break;
        v13 = DupStr(lpServiceName[0]);
        if ( !v13 )
        {
          LastWin32Error = -2147024882;
          break;
        }
        LastWin32Error = CImplPtrAry::Append(this, v13);
        if ( LastWin32Error )
          break;
        LastWin32Error = CImplAry::AppendIndirect(v16, 4u, (char *)v18 + 4, 0);
        if ( LastWin32Error )
          break;
        LastWin32Error = StopSingleService(a1, v9, 0);
        if ( LastWin32Error )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= ServicesReturned )
          goto LABEL_9;
      }
    }
LABEL_10:
    MemFree(v8);
LABEL_11:
    if ( v9 )
      CloseServiceHandle(v9);
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003dfc0  push    rbp
0x18003dfc2  push    rbx
0x18003dfc3  push    rsi
0x18003dfc4  push    rdi
0x18003dfc5  push    r12
0x18003dfc7  push    r13
0x18003dfc9  push    r14
0x18003dfcb  push    r15
0x18003dfcd  lea     rbp, [rsp-1Fh]
0x18003dfd2  sub     rsp, 0A8h
0x18003dfd9  mov     rax, cs:__security_cookie
0x18003dfe0  xor     rax, rsp
0x18003dfe3  mov     [rbp+57h+var_50], rax
0x18003dfe7  xor     ebx, ebx
0x18003dfe9  mov     [rbp+57h+var_A8], r9
0x18003dfed  and     [rsp+0E0h+pcbBytesNeeded], rbx
0x18003dff2  lea     r9, aFindingOutServ; "Finding out service state"
0x18003dff9  mov     r13, r8
0x18003dffc  mov     r15, rdx
0x18003dfff  mov     r12, rcx
0x18003e002  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x18003e009  lea     esi, [rbx+1]
0x18003e00c  xor     r8d, r8d; unsigned int
0x18003e00f  mov     ecx, esi; int
0x18003e011  xor     edi, edi
0x18003e013  xor     r14d, r14d
0x18003e016  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e01b  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003e01f  mov     rcx, r15; hService
0x18003e022  call    cs:__imp_QueryServiceStatus
0x18003e028  test    eax, eax
0x18003e02a  jnz     short loc_18003E033
0x18003e02c  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e031  mov     ebx, eax
0x18003e033  and     [rsp+0E0h+pcbBytesNeeded], rdi
0x18003e038  lea     r9, aFindingOutServ; "Finding out service state"
0x18003e03f  xor     r8d, r8d; unsigned int
0x18003e042  lea     rdx, aQueryservicest_0; "QueryServiceStatus"
0x18003e049  mov     ecx, ebx; int
0x18003e04b  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e050  test    ebx, ebx
0x18003e052  jnz     loc_18003E107
0x18003e058  cmp     [rbp+57h+ServiceStatus.dwCurrentState], esi
0x18003e05b  jz      loc_18003E107
0x18003e061  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 3
0x18003e065  jnz     short loc_18003E078
0x18003e067  mov     edx, esi; dwControl
0x18003e069  mov     rcx, r15; hService
0x18003e06c  call    ?WaitForServiceState@@YAJPEAUSC_HANDLE__@@K@Z; WaitForServiceState(SC_HANDLE__ *,ulong)
0x18003e071  mov     ebx, eax
0x18003e073  jmp     loc_18003E107
0x18003e078  and     [rsp+0E0h+pcbBytesNeeded], rdi
0x18003e07d  lea     rsi, aEnumeratingDep; "Enumerating dependent services"
0x18003e084  xor     r8d, r8d; unsigned int
0x18003e087  lea     rdx, aEnumdependents_0; "EnumDependentServices"
0x18003e08e  mov     r9, rsi; char *
0x18003e091  lea     ecx, [r8+1]; int
0x18003e095  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e09a  xor     r9d, r9d; cbBufSize
0x18003e09d  lea     rax, [rbp+57h+ServicesReturned]
0x18003e0a1  mov     [rsp+0E0h+lpServicesReturned], rax; lpServicesReturned
0x18003e0a6  xor     r8d, r8d; lpServices
0x18003e0a9  lea     rax, [rbp+57h+cbBufSize]
0x18003e0ad  mov     rcx, r15; hService
0x18003e0b0  mov     [rsp+0E0h+pcbBytesNeeded], rax; unsigned __int16 *
0x18003e0b5  lea     edx, [r9+1]; dwServiceState
0x18003e0b9  call    cs:__imp_EnumDependentServicesW
0x18003e0bf  test    eax, eax
0x18003e0c1  jz      short loc_18003E129
0x18003e0c3  and     [rsp+0E0h+pcbBytesNeeded], rdi
0x18003e0c8  lea     rdx, aEnumdependents_0; "EnumDependentServices"
0x18003e0cf  mov     r9, rsi; char *
0x18003e0d2  xor     r8d, r8d; unsigned int
0x18003e0d5  xor     ecx, ecx; int
0x18003e0d7  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e0dc  xor     r8d, r8d; unsigned int *
0x18003e0df  mov     rdx, r15; struct SC_HANDLE__ *
0x18003e0e2  mov     rcx, r12; struct SC_HANDLE__ *
0x18003e0e5  call    ?StopSingleService@@YAJPEAUSC_HANDLE__@@0PEAK@Z; StopSingleService(SC_HANDLE__ *,SC_HANDLE__ *,ulong *)
0x18003e0ea  mov     ebx, eax
0x18003e0ec  test    rdi, rdi
0x18003e0ef  jz      short loc_18003E0F9
0x18003e0f1  mov     rcx, rdi; lpMem
0x18003e0f4  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003e0f9  test    r14, r14
0x18003e0fc  jz      short loc_18003E107
0x18003e0fe  mov     rcx, r14; hSCObject
0x18003e101  call    cs:__imp_CloseServiceHandle
0x18003e107  mov     eax, ebx
0x18003e109  mov     rcx, [rbp+57h+var_50]
0x18003e10d  xor     rcx, rsp; StackCookie
0x18003e110  call    __security_check_cookie
0x18003e115  add     rsp, 0A8h
0x18003e11c  pop     r15
0x18003e11e  pop     r14
0x18003e120  pop     r13
0x18003e122  pop     r12
0x18003e124  pop     rdi
0x18003e125  pop     rsi
0x18003e126  pop     rbx
0x18003e127  pop     rbp
0x18003e128  retn
0x18003e129  call    cs:__imp_GetLastError
0x18003e12f  cmp     eax, 0EAh
0x18003e134  jz      short loc_18003E15A
0x18003e136  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e13b  and     [rsp+0E0h+pcbBytesNeeded], rdi
0x18003e140  lea     rdx, aEnumdependents_0; "EnumDependentServices"
0x18003e147  mov     r9, rsi; char *
0x18003e14a  xor     r8d, r8d; unsigned int
0x18003e14d  mov     ecx, eax; int
0x18003e14f  mov     ebx, eax
0x18003e151  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e156  test    ebx, ebx
0x18003e158  jnz     short loc_18003E107
0x18003e15a  mov     ecx, [rbp+57h+cbBufSize]; unsigned __int64
0x18003e15d  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18003e162  mov     rdi, rax
0x18003e165  test    rax, rax
0x18003e168  jnz     short loc_18003E18D
0x18003e16a  and     [rsp+0E0h+pcbBytesNeeded], r14
0x18003e16f  lea     rdx, aEnumdependents_0; "EnumDependentServices"
0x18003e176  mov     ebx, 8007000Eh
0x18003e17b  mov     r9, rsi; char *
0x18003e17e  mov     ecx, ebx; int
0x18003e180  xor     r8d, r8d; unsigned int
0x18003e183  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e188  jmp     loc_18003E107
0x18003e18d  mov     r9d, [rbp+57h+cbBufSize]; cbBufSize
0x18003e191  lea     rax, [rbp+57h+ServicesReturned]
0x18003e195  mov     [rsp+0E0h+lpServicesReturned], rax; lpServicesReturned
0x18003e19a  mov     r8, rdi; lpServices
0x18003e19d  lea     rax, [rbp+57h+cbBufSize]
0x18003e1a1  mov     edx, 1; dwServiceState
0x18003e1a6  mov     rcx, r15; hService
0x18003e1a9  mov     [rsp+0E0h+pcbBytesNeeded], rax; unsigned __int16 *
0x18003e1ae  call    cs:__imp_EnumDependentServicesW
0x18003e1b4  test    eax, eax
0x18003e1b6  jnz     short loc_18003E1BF
0x18003e1b8  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e1bd  mov     ebx, eax
0x18003e1bf  and     [rsp+0E0h+pcbBytesNeeded], r14
0x18003e1c4  lea     rdx, aEnumdependents_0; "EnumDependentServices"
0x18003e1cb  mov     r9, rsi; char *
0x18003e1ce  xor     r8d, r8d; unsigned int
0x18003e1d1  mov     ecx, ebx; int
0x18003e1d3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e1d8  test    ebx, ebx
0x18003e1da  jnz     loc_18003E0F1
0x18003e1e0  xor     esi, esi
0x18003e1e2  cmp     [rbp+57h+ServicesReturned], esi
0x18003e1e5  jbe     loc_18003E0DC
0x18003e1eb  and     [rsp+0E0h+pcbBytesNeeded], 0
0x18003e1f1  lea     rcx, [rsi+rsi*2]
0x18003e1f5  add     rcx, rcx
0x18003e1f8  lea     r9, aOpeningService; "Opening Service handle"
0x18003e1ff  xor     r8d, r8d; unsigned int
0x18003e202  lea     rdx, aOpenservice; "OpenService"
0x18003e209  movups  xmm0, xmmword ptr [rdi+rcx*8]
0x18003e20d  movups  xmmword ptr [rbp+57h+lpServiceName], xmm0
0x18003e211  movups  xmm1, xmmword ptr [rdi+rcx*8+10h]
0x18003e216  movups  [rbp+57h+var_90], xmm1
0x18003e21a  movups  xmm0, xmmword ptr [rdi+rcx*8+20h]
0x18003e21f  lea     ecx, [r8+1]; int
0x18003e223  movups  [rbp+57h+var_80], xmm0
0x18003e227  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e22c  mov     rdx, [rbp+57h+lpServiceName]; lpServiceName
0x18003e230  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18003e236  mov     rcx, r12; hSCManager
0x18003e239  call    cs:__imp_OpenServiceW
0x18003e23f  mov     r14, rax
0x18003e242  test    rax, rax
0x18003e245  jnz     short loc_18003E24E
0x18003e247  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003e24c  mov     ebx, eax
0x18003e24e  and     [rsp+0E0h+pcbBytesNeeded], 0
0x18003e254  lea     r9, aOpeningService; "Opening Service handle"
0x18003e25b  xor     r8d, r8d; unsigned int
0x18003e25e  lea     rdx, aOpenservice; "OpenService"
0x18003e265  mov     ecx, ebx; int
0x18003e267  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003e26c  test    ebx, ebx
0x18003e26e  jnz     loc_18003E0F1
0x18003e274  mov     rcx, [rbp+57h+lpServiceName]; Src
0x18003e278  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x18003e27d  test    rax, rax
0x18003e280  jz      short loc_18003E2DC
0x18003e282  mov     rdx, rax; void *
0x18003e285  mov     rcx, r13; this
0x18003e288  call    ?Append@CImplPtrAry@@IEAAJPEAX@Z; CImplPtrAry::Append(void *)
0x18003e28d  mov     ebx, eax
0x18003e28f  test    eax, eax
0x18003e291  jnz     loc_18003E0F1
0x18003e297  mov     rcx, [rbp+57h+var_A8]; this
0x18003e29b  lea     r8, [rbp+57h+var_90+4]; void *
0x18003e29f  xor     r9d, r9d; void **
0x18003e2a2  lea     edx, [rax+4]; unsigned __int64
0x18003e2a5  call    ?AppendIndirect@CImplAry@@IEAAJ_KPEAXPEAPEAX@Z; CImplAry::AppendIndirect(unsigned __int64,void *,void * *)
0x18003e2aa  mov     ebx, eax
0x18003e2ac  test    eax, eax
0x18003e2ae  jnz     loc_18003E0F1
0x18003e2b4  xor     r8d, r8d; unsigned int *
0x18003e2b7  mov     rdx, r14; struct SC_HANDLE__ *
0x18003e2ba  mov     rcx, r12; struct SC_HANDLE__ *
0x18003e2bd  call    ?StopSingleService@@YAJPEAUSC_HANDLE__@@0PEAK@Z; StopSingleService(SC_HANDLE__ *,SC_HANDLE__ *,ulong *)
0x18003e2c2  mov     ebx, eax
0x18003e2c4  test    eax, eax
0x18003e2c6  jnz     loc_18003E0F1
0x18003e2cc  inc     esi
0x18003e2ce  cmp     esi, [rbp+57h+ServicesReturned]
0x18003e2d1  jb      loc_18003E1EB
0x18003e2d7  jmp     loc_18003E0DC
0x18003e2dc  mov     ebx, 8007000Eh
0x18003e2e1  jmp     loc_18003E0F1
```
