# IsRasInstalled(ulong *,ulong *)

- ea: `0x180001d70`
- end: `0x180002054`
- name: `?IsRasInstalled@@YAHPEAK0@Z`
- size: `740`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180001850`

## callees

- `0x180001d70`
- `0x180008300`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000201b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001de3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001eaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000201b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fcd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180001eeb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180001eeb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001f65`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001fee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002007`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001f65`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001fee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002007`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180001e50`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180001e50`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180001dd4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180001e9b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180001dd4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180001e9b`

## pseudocode

```c
__int64 __fastcall IsRasInstalled(unsigned int *a1, unsigned int *a2)
{
  int v2; // eax
  BOOL v5; // esi
  SC_HANDLE v7; // rax
  __int64 dwCurrentState; // r9
  DWORD LastError; // eax
  DWORD v10; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  v2 = gIsRasInstalled;
  *a2 = 0;
  *a1 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( v2 == 2 )
    return 0;
  v5 = 0;
  if ( v2 == 1 )
  {
    EnterCriticalSection(&gSensLock);
    if ( ghRasMan )
      v5 = QueryServiceStatus(ghRasMan, &ServiceStatus);
    LeaveCriticalSection(&gSensLock);
    if ( v5 )
    {
      *a1 = ServiceStatus.dwCurrentState;
      return 1;
    }
    *a2 = GetLastError();
    return 0;
  }
  EnterCriticalSection(&gSensLock);
  v7 = ghSCM;
  if ( !ghSCM )
  {
    v7 = OpenSCManagerW(0, 0, 0xF003Fu);
    ghSCM = v7;
    if ( !v7 )
    {
      LeaveCriticalSection(&gSensLock);
      LastError = GetLastError();
      *a2 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids, LastError);
      }
      return 0;
    }
  }
  if ( !ghRasMan )
  {
    ghRasMan = OpenServiceW(v7, L"RasMan", 4u);
    if ( !ghRasMan )
    {
      CloseServiceHandle(ghSCM);
      ghSCM = 0;
      LeaveCriticalSection(&gSensLock);
      v10 = GetLastError();
      *a2 = v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids, v10);
      }
      gIsRasInstalled = 2;
      return 0;
    }
  }
  LeaveCriticalSection(&gSensLock);
  gIsRasInstalled = 1;
  EnterCriticalSection(&gSensLock);
  if ( ghRasMan )
    v5 = QueryServiceStatus(ghRasMan, &ServiceStatus);
  LeaveCriticalSection(&gSensLock);
  if ( !v5 )
  {
    *a2 = GetLastError();
    EnterCriticalSection(&gSensLock);
    if ( ghSCM )
    {
      CloseServiceHandle(ghSCM);
      ghSCM = 0;
    }
    if ( ghRasMan )
    {
      CloseServiceHandle(ghRasMan);
      ghRasMan = 0;
    }
    LeaveCriticalSection(&gSensLock);
    return 0;
  }
  dwCurrentState = ServiceStatus.dwCurrentState;
  *a1 = ServiceStatus.dwCurrentState;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids, dwCurrentState);
  }
  return 1;
}

```

## disassembly

```asm
0x180001d70  mov     [rsp+arg_10], rbx
0x180001d75  push    rbp
0x180001d76  push    rsi
0x180001d77  push    rdi
0x180001d78  sub     rsp, 50h
0x180001d7c  mov     rax, cs:__security_cookie
0x180001d83  xor     rax, rsp
0x180001d86  mov     [rsp+68h+var_28], rax
0x180001d8b  mov     eax, cs:?gIsRasInstalled@@3W4SERVICE_INSTALL_STATE@@A; SERVICE_INSTALL_STATE gIsRasInstalled
0x180001d91  xor     ebp, ebp
0x180001d93  mov     [rdx], ebp
0x180001d95  xorps   xmm0, xmm0
0x180001d98  mov     [rcx], ebp
0x180001d9a  mov     rdi, rdx
0x180001d9d  mov     rbx, rcx
0x180001da0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180001da5  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180001daa  cmp     eax, 2
0x180001dad  jz      short loc_180001E1D
0x180001daf  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001db6  mov     esi, ebp
0x180001db8  cmp     eax, 1
0x180001dbb  jnz     short loc_180001E21
0x180001dbd  call    cs:__imp_EnterCriticalSection
0x180001dc3  mov     rcx, cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA; hService
0x180001dca  test    rcx, rcx
0x180001dcd  jz      short loc_180001DDC
0x180001dcf  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180001dd4  call    cs:__imp_QueryServiceStatus
0x180001dda  mov     esi, eax
0x180001ddc  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001de3  call    cs:__imp_LeaveCriticalSection
0x180001de9  test    esi, esi
0x180001deb  jz      short loc_180001E15
0x180001ded  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x180001df1  mov     [rbx], eax
0x180001df3  mov     eax, 1
0x180001df8  mov     rcx, [rsp+68h+var_28]
0x180001dfd  xor     rcx, rsp; StackCookie
0x180001e00  call    __security_check_cookie
0x180001e05  mov     rbx, [rsp+68h+arg_10]
0x180001e0d  add     rsp, 50h
0x180001e11  pop     rdi
0x180001e12  pop     rsi
0x180001e13  pop     rbp
0x180001e14  retn
0x180001e15  call    cs:__imp_GetLastError
0x180001e1b  mov     [rdi], eax
0x180001e1d  xor     eax, eax
0x180001e1f  jmp     short loc_180001DF8
0x180001e21  call    cs:__imp_EnterCriticalSection
0x180001e27  mov     rax, cs:?ghSCM@@3PEAUSC_HANDLE__@@EA; SC_HANDLE__ * ghSCM
0x180001e2e  test    rax, rax
0x180001e31  jz      loc_180001EE1
0x180001e37  cmp     cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA, rsi; SC_HANDLE__ * ghRasMan
0x180001e3e  jnz     short loc_180001E66
0x180001e40  mov     r8d, 4; dwDesiredAccess
0x180001e46  lea     rdx, ServiceName; "RasMan"
0x180001e4d  mov     rcx, rax; hSCManager
0x180001e50  call    cs:__imp_OpenServiceW
0x180001e56  mov     cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA, rax; SC_HANDLE__ * ghRasMan
0x180001e5d  test    rax, rax
0x180001e60  jz      loc_180001F5E
0x180001e66  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001e6d  call    cs:__imp_LeaveCriticalSection
0x180001e73  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001e7a  mov     cs:?gIsRasInstalled@@3W4SERVICE_INSTALL_STATE@@A, 1; SERVICE_INSTALL_STATE gIsRasInstalled
0x180001e84  call    cs:__imp_EnterCriticalSection
0x180001e8a  mov     rcx, cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA; hService
0x180001e91  test    rcx, rcx
0x180001e94  jz      short loc_180001EA3
0x180001e96  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180001e9b  call    cs:__imp_QueryServiceStatus
0x180001ea1  mov     esi, eax
0x180001ea3  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001eaa  call    cs:__imp_LeaveCriticalSection
0x180001eb0  test    esi, esi
0x180001eb2  jz      loc_180001FCD
0x180001eb8  mov     r9d, [rsp+68h+ServiceStatus.dwCurrentState]
0x180001ebd  mov     [rbx], r9d
0x180001ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ec7  lea     rdx, WPP_GLOBAL_Control
0x180001ece  cmp     rcx, rdx
0x180001ed1  jnz     loc_180002026
0x180001ed7  mov     eax, 1
0x180001edc  jmp     loc_180001DF8
0x180001ee1  xor     edx, edx; lpDatabaseName
0x180001ee3  xor     ecx, ecx; lpMachineName
0x180001ee5  mov     r8d, 0F003Fh; dwDesiredAccess
0x180001eeb  call    cs:__imp_OpenSCManagerW
0x180001ef1  mov     cs:?ghSCM@@3PEAUSC_HANDLE__@@EA, rax; SC_HANDLE__ * ghSCM
0x180001ef8  test    rax, rax
0x180001efb  jnz     loc_180001E37
0x180001f01  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001f08  call    cs:__imp_LeaveCriticalSection
0x180001f0e  call    cs:__imp_GetLastError
0x180001f14  mov     [rdi], eax
0x180001f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f1d  lea     rdx, WPP_GLOBAL_Control
0x180001f24  cmp     rcx, rdx
0x180001f27  jz      loc_180001E1D
0x180001f2d  test    byte ptr [rcx+1Ch], 1
0x180001f31  jz      loc_180001E1D
0x180001f37  cmp     byte ptr [rcx+19h], 2
0x180001f3b  jb      loc_180001E1D
0x180001f41  mov     rcx, [rcx+10h]
0x180001f45  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001f4c  mov     edx, 0Bh
0x180001f51  mov     r9d, eax
0x180001f54  call    WPP_SF_d
0x180001f59  jmp     loc_180001E1D
0x180001f5e  mov     rcx, cs:?ghSCM@@3PEAUSC_HANDLE__@@EA; hSCObject
0x180001f65  call    cs:__imp_CloseServiceHandle
0x180001f6b  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001f72  mov     cs:?ghSCM@@3PEAUSC_HANDLE__@@EA, rbp; SC_HANDLE__ * ghSCM
0x180001f79  call    cs:__imp_LeaveCriticalSection
0x180001f7f  call    cs:__imp_GetLastError
0x180001f85  mov     [rdi], eax
0x180001f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f8e  lea     rdx, WPP_GLOBAL_Control
0x180001f95  cmp     rcx, rdx
0x180001f98  jz      short loc_180001FBE
0x180001f9a  test    byte ptr [rcx+1Ch], 1
0x180001f9e  jz      short loc_180001FBE
0x180001fa0  cmp     byte ptr [rcx+19h], 2
0x180001fa4  jb      short loc_180001FBE
0x180001fa6  mov     rcx, [rcx+10h]
0x180001faa  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001fb1  mov     edx, 0Ch
0x180001fb6  mov     r9d, eax
0x180001fb9  call    WPP_SF_d
0x180001fbe  mov     cs:?gIsRasInstalled@@3W4SERVICE_INSTALL_STATE@@A, 2; SERVICE_INSTALL_STATE gIsRasInstalled
0x180001fc8  jmp     loc_180001E1D
0x180001fcd  call    cs:__imp_GetLastError
0x180001fd3  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001fda  mov     [rdi], eax
0x180001fdc  call    cs:__imp_EnterCriticalSection
0x180001fe2  mov     rcx, cs:?ghSCM@@3PEAUSC_HANDLE__@@EA; hSCObject
0x180001fe9  test    rcx, rcx
0x180001fec  jz      short loc_180001FFB
0x180001fee  call    cs:__imp_CloseServiceHandle
0x180001ff4  mov     cs:?ghSCM@@3PEAUSC_HANDLE__@@EA, rbp; SC_HANDLE__ * ghSCM
0x180001ffb  mov     rcx, cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA; hSCObject
0x180002002  test    rcx, rcx
0x180002005  jz      short loc_180002014
0x180002007  call    cs:__imp_CloseServiceHandle
0x18000200d  mov     cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA, rbp; SC_HANDLE__ * ghRasMan
0x180002014  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000201b  call    cs:__imp_LeaveCriticalSection
0x180002021  jmp     loc_180001E1D
0x180002026  test    byte ptr [rcx+1Ch], 1
0x18000202a  jz      loc_180001ED7
0x180002030  cmp     byte ptr [rcx+19h], 5
0x180002034  jb      loc_180001ED7
0x18000203a  mov     rcx, [rcx+10h]
0x18000203e  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180002045  mov     edx, 0Dh
0x18000204a  call    WPP_SF_d
0x18000204f  jmp     loc_180001ED7
```
