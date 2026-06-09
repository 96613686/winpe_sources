# SQLStartupShutdownControl::NotifySQLServerStarted(void)

- ea: `0x10041a620`
- end: `0x10041a7e7`
- name: `?NotifySQLServerStarted@SQLStartupShutdownControl@@EEAAXXZ`
- size: `455`
- prototype: `void __fastcall(SQLStartupShutdownControl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10041a620`
- `0x10041eac0`
- `0x100423970`
- `0x1004403d0`
- `0x100440a70`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10041a749`
- `KERNEL32!EnterCriticalSection` at `0x10041a749`
- `KERNEL32!LeaveCriticalSection` at `0x10041a7c9`
- `KERNEL32!LeaveCriticalSection` at `0x10041a7c9`
- `KERNEL32!SetEvent` at `0x10041a764`
- `KERNEL32!SetEvent` at `0x10041a764`
- `KERNEL32!GetLastError` at `0x10041a795`
- `KERNEL32!GetLastError` at `0x10041a795`
- `ADVAPI32!SetServiceStatus` at `0x10041a78b`
- `ADVAPI32!SetServiceStatus` at `0x10041a78b`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a679`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a679`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a67f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a67f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10041a7a8`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10041a7a8`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041a71c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041a71c`
- `hostregdll!HostReg_BootedInstanceService` at `0x10041a657`
- `hostregdll!HostReg_BootedInstanceService` at `0x10041a657`
- `sqlfederation!ShouldBootFederation` at `0x10041a6e6`
- `sqlfederation!ShouldBootFederation` at `0x10041a6e6`
- `sqlfederation!BootFederation` at `0x10041a6fc`
- `sqlfederation!BootFederation` at `0x10041a6fc`

## string_xrefs

- `0x10041a722`: `Federation Boot Completed Successfully \n`
- `0x10041a7ae`: `completesignal`
- `0x10041a668`: `Error: [NotifyFabricReadyForConnections] Failed while marking the instance service as booted. ErrorCode: 0x%08lx.\n`

## pseudocode

```c
void __fastcall SQLStartupShutdownControl::NotifySQLServerStarted(SQLStartupShutdownControl *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v4; // eax
  char *v5; // rcx
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  _BYTE v8[4096]; // [rsp+30h] [rbp-1218h] BYREF
  char Buffer[512]; // [rsp+1030h] [rbp-218h] BYREF

  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    v1 = HostReg_BootedInstanceService(this);
    v2 = v1;
    if ( v1 < 0 )
    {
      _mm_lfence();
      TraceInitFabric(
        L"Error: [NotifyFabricReadyForConnections] Failed while marking the instance service as booted. ErrorCode: 0x%08lx.\r\n",
        (unsigned int)v1);
      _mm_lfence();
      SetWin32ExitCode(v2);
      DefaultLocale = GetDefaultLocale();
      v4 = StringCchPrintf_lA(
             Buffer,
             0x200u,
             "%hs (HRESULT 0x%x)",
             DefaultLocale,
             "Server boot notification failure.",
             v2);
      v5 = "Server boot notification failure.";
      if ( v4 >= 0 )
        v5 = Buffer;
      FailAndExit(v5);
    }
  }
  if ( (*(_BYTE *)(qword_10049F340 + 1487) & 0x10) != 0
    && (*(_BYTE *)(qword_10049F340 + 1488) & 4) != 0
    && (unsigned __int8)ShouldBootFederation(this) )
  {
    traceprint(L"Booting Federation.\n");
    if ( (int)BootFederation() < 0 )
    {
      scierrlog(0x42F2u, L"SQL federation");
      SQLExit(251);
    }
    traceprint(L"Federation Boot Completed Successfully \n");
  }
  if ( *((_DWORD *)qword_10049F360 + 10544) )
  {
    EnterCriticalSection(&SCMCrtSec);
    if ( SQLServiceStatus.dwCurrentState == 2 )
    {
      if ( hEvent )
        SetEvent(hEvent);
      SQLServiceStatus.dwCurrentState = 4;
      *(_QWORD *)&SQLServiceStatus.dwCheckPoint = 0;
      if ( !SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        LastError = GetLastError();
        OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v8, 0, 0);
        scierrlog(0x42F7u, L"completesignal", OSErrString);
      }
    }
    LeaveCriticalSection(&SCMCrtSec);
  }
}

```

## disassembly

```asm
0x10041a620  mov     eax, 1248h
0x10041a625  call    _alloca_probe
0x10041a62a  sub     rsp, rax
0x10041a62d  mov     rax, cs:__security_cookie
0x10041a634  xor     rax, rsp
0x10041a637  mov     [rsp+1248h+var_18], rax
0x10041a63f  mov     rax, cs:qword_10049F360
0x10041a646  cmp     dword ptr [rax+38A8h], 0
0x10041a64d  jz      short loc_10041A6CD
0x10041a64f  mov     [rsp+1248h+var_8], rbx
0x10041a657  call    cs:__imp_HostReg_BootedInstanceService
0x10041a65d  mov     ebx, eax
0x10041a65f  test    eax, eax
0x10041a661  jns     short loc_10041A6C5
0x10041a663  lfence
0x10041a666  mov     edx, eax
0x10041a668  lea     rcx, aErrorNotifyfab; "Error: [NotifyFabricReadyForConnections"...
0x10041a66f  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x10041a674  lfence
0x10041a677  mov     ecx, ebx
0x10041a679  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041a67f  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a685  mov     [rsp+1248h+var_1220], ebx
0x10041a689  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041a690  lea     rbx, aServerBootNoti; "Server boot notification failure."
0x10041a697  mov     r9, rax; struct __crt_locale_pointers *
0x10041a69a  mov     edx, 200h; unsigned __int64
0x10041a69f  mov     [rsp+1248h+var_1228], rbx
0x10041a6a4  lea     rcx, [rsp+1248h+Buffer]; Buffer
0x10041a6ac  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041a6b1  mov     rcx, rbx
0x10041a6b4  test    eax, eax
0x10041a6b6  js      short loc_10041A6C0
0x10041a6b8  lea     rcx, [rsp+1248h+Buffer]; char *
0x10041a6c0  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041a6c5  mov     rbx, [rsp+1248h+var_8]
0x10041a6cd  mov     rax, cs:qword_10049F340
0x10041a6d4  test    byte ptr [rax+5CFh], 10h
0x10041a6db  jz      short loc_10041A72E
0x10041a6dd  test    byte ptr [rax+5D0h], 4
0x10041a6e4  jz      short loc_10041A72E
0x10041a6e6  call    cs:__imp_ShouldBootFederation
0x10041a6ec  test    al, al
0x10041a6ee  jz      short loc_10041A72E
0x10041a6f0  lea     rcx, aBootingFederat; "Booting Federation.\n"
0x10041a6f7  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x10041a6fc  call    cs:__imp_BootFederation
0x10041a702  test    eax, eax
0x10041a704  jns     short loc_10041A722
0x10041a706  lea     rdx, aSqlFederation; "SQL federation"
0x10041a70d  mov     ecx, 42F2h; unsigned int
0x10041a712  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10041a717  mov     ecx, 0FBh
0x10041a71c  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x10041a722  lea     rcx, aFederationBoot; "Federation Boot Completed Successfully "...
0x10041a729  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x10041a72e  mov     rax, cs:qword_10049F360
0x10041a735  cmp     dword ptr [rax+0A4C0h], 0
0x10041a73c  jz      loc_10041A7CF
0x10041a742  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10041a749  call    cs:__imp_EnterCriticalSection
0x10041a74f  cmp     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS SQLServiceStatus ...
0x10041a756  jnz     short loc_10041A7C2
0x10041a758  mov     rcx, cs:hEvent; hEvent
0x10041a75f  test    rcx, rcx
0x10041a762  jz      short loc_10041A76A
0x10041a764  call    cs:__imp_SetEvent
0x10041a76a  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10041a771  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10041a778  xor     eax, eax
0x10041a77a  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS SQLServiceStatus ...
0x10041a784  mov     qword ptr cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rax; _SERVICE_STATUS SQLServiceStatus ...
0x10041a78b  call    cs:__imp_SetServiceStatus
0x10041a791  test    eax, eax
0x10041a793  jnz     short loc_10041A7C2
0x10041a795  call    cs:__imp_GetLastError
0x10041a79b  xor     r9d, r9d
0x10041a79e  lea     rdx, [rsp+1248h+var_1218]
0x10041a7a3  mov     ecx, eax
0x10041a7a5  xor     r8d, r8d
0x10041a7a8  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10041a7ae  lea     rdx, aCompletesignal; "completesignal"
0x10041a7b5  mov     ecx, 42F7h; unsigned int
0x10041a7ba  mov     r8, rax
0x10041a7bd  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10041a7c2  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10041a7c9  call    cs:__imp_LeaveCriticalSection
0x10041a7cf  mov     rcx, [rsp+1248h+var_18]
0x10041a7d7  xor     rcx, rsp; StackCookie
0x10041a7da  call    __security_check_cookie
0x10041a7df  add     rsp, 1248h
0x10041a7e6  retn
```
