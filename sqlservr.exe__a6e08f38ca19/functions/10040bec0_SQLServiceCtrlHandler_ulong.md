# SQLServiceCtrlHandler(ulong)

- ea: `0x10040bec0`
- end: `0x10040c407`
- name: `?SQLServiceCtrlHandler@@YAXK@Z`
- size: `1351`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040a080`
- `0x10040bec0`
- `0x1004403d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040bfd9`
- `KERNEL32!EnterCriticalSection` at `0x10040c08d`
- `KERNEL32!EnterCriticalSection` at `0x10040c0f4`
- `KERNEL32!EnterCriticalSection` at `0x10040c193`
- `KERNEL32!EnterCriticalSection` at `0x10040c261`
- `KERNEL32!EnterCriticalSection` at `0x10040bfd9`
- `KERNEL32!EnterCriticalSection` at `0x10040c08d`
- `KERNEL32!EnterCriticalSection` at `0x10040c0f4`
- `KERNEL32!EnterCriticalSection` at `0x10040c193`
- `KERNEL32!EnterCriticalSection` at `0x10040c261`
- `KERNEL32!SetThreadPriority` at `0x10040c39d`
- `KERNEL32!SetThreadPriority` at `0x10040c39d`
- `KERNEL32!LeaveCriticalSection` at `0x10040c04f`
- `KERNEL32!LeaveCriticalSection` at `0x10040c0e2`
- `KERNEL32!LeaveCriticalSection` at `0x10040c237`
- `KERNEL32!LeaveCriticalSection` at `0x10040c2f0`
- `KERNEL32!LeaveCriticalSection` at `0x10040c04f`
- `KERNEL32!LeaveCriticalSection` at `0x10040c0e2`
- `KERNEL32!LeaveCriticalSection` at `0x10040c237`
- `KERNEL32!LeaveCriticalSection` at `0x10040c2f0`
- `KERNEL32!CreateEventA` at `0x10040c2dc`
- `KERNEL32!CreateEventA` at `0x10040c2dc`
- `KERNEL32!SetThreadAffinityMask` at `0x10040c3ab`
- `KERNEL32!SetThreadAffinityMask` at `0x10040c3ab`
- `KERNEL32!CloseHandle` at `0x10040c3b4`
- `KERNEL32!CloseHandle` at `0x10040c3b4`
- `KERNEL32!GetLastError` at `0x10040c01c`
- `KERNEL32!GetLastError` at `0x10040c0af`
- `KERNEL32!GetLastError` at `0x10040c131`
- `KERNEL32!GetLastError` at `0x10040c1d0`
- `KERNEL32!GetLastError` at `0x10040c2a4`
- `KERNEL32!GetLastError` at `0x10040c300`
- `KERNEL32!GetLastError` at `0x10040c01c`
- `KERNEL32!GetLastError` at `0x10040c0af`
- `KERNEL32!GetLastError` at `0x10040c131`
- `KERNEL32!GetLastError` at `0x10040c1d0`
- `KERNEL32!GetLastError` at `0x10040c2a4`
- `KERNEL32!GetLastError` at `0x10040c300`
- `ADVAPI32!SetServiceStatus` at `0x10040c012`
- `ADVAPI32!SetServiceStatus` at `0x10040c0a1`
- `ADVAPI32!SetServiceStatus` at `0x10040c127`
- `ADVAPI32!SetServiceStatus` at `0x10040c1c6`
- `ADVAPI32!SetServiceStatus` at `0x10040c29a`
- `ADVAPI32!SetServiceStatus` at `0x10040c012`
- `ADVAPI32!SetServiceStatus` at `0x10040c0a1`
- `ADVAPI32!SetServiceStatus` at `0x10040c127`
- `ADVAPI32!SetServiceStatus` at `0x10040c1c6`
- `ADVAPI32!SetServiceStatus` at `0x10040c29a`
- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040bf30`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040c33c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040c38f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040c33c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040c38f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10040bf2a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10040bf2a`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x10040c05a`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x10040c3bf`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x10040c05a`
- `sqldk!?SetShutdownOption@@YAXW4ShutdownOption@@K@Z` at `0x10040c3bf`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c02e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c0c1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c143`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c1e2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c2b6`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c312`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c02e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c0c1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c143`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c1e2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c2b6`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040c312`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040c3db`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040c3db`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040bf8f`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040bf8f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10040c254`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10040c254`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10040c360`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10040c360`

## string_xrefs

- `0x10040c31b`: `initsignal:CreateEvent`
- `0x10040c037`: `SQLServiceControlHandler`
- `0x10040c0ca`: `SQLServiceControlHandler`
- `0x10040c14c`: `SQLServiceControlHandler`
- `0x10040c1eb`: `SQLServiceControlHandler`
- `0x10040c2bf`: `SQLServiceControlHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SQLServiceCtrlHandler(DWORD dwControl)
{
  __int64 v2; // r8
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  void *v5; // rsp
  void *v6; // rsp
  unsigned int *p_ThrdAddr; // r9
  DWORD v8; // eax
  wchar_t *v9; // rax
  DWORD v10; // eax
  wchar_t *v11; // rax
  DWORD v12; // eax
  wchar_t *v13; // rax
  DWORD v14; // eax
  wchar_t *v15; // rax
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  DWORD v18; // eax
  wchar_t *v19; // rax
  void *v20; // rbx
  unsigned int ThrdAddr; // [rsp+40h] [rbp+0h] BYREF
  __int64 v22; // [rsp+48h] [rbp+8h]
  _BYTE v23[4096]; // [rsp+50h] [rbp+10h] BYREF
  _BYTE v24[6048]; // [rsp+1050h] [rbp+1010h] BYREF

  v22 = -2;
  if ( !*((_DWORD *)qword_10049F360 + 10544) )
    utassert_fail(1u, "GetSrvCtrMan()", "dbsignal.cpp", 1004, 0);
  v2 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
  if ( v2 )
  {
    v3 = 8 * v2 + 15;
    if ( v3 <= 8 * v2 )
      v3 = 0xFFFFFFFFFFFFFF0LL;
    v4 = v3 & 0xFFFFFFFFFFFFFFF0uLL;
    v5 = alloca(v4);
    v6 = alloca(v4);
    p_ThrdAddr = &ThrdAddr;
  }
  else
  {
    p_ThrdAddr = 0;
  }
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v24, 0, v2, (void **)p_ThrdAddr, 1, 0, 0);
  switch ( dwControl )
  {
    case 1u:
      if ( (*((_BYTE *)qword_10049F360 + 48) & 0x20) != 0 )
        SQLExit(248);
      EnterCriticalSection(&SCMCrtSec);
      SQLServiceStatus.dwCurrentState = 3;
      *(_QWORD *)&SQLServiceStatus.dwWin32ExitCode = 0;
      SQLServiceStatus.dwCheckPoint = 1;
      SQLServiceStatus.dwWaitHint = 60000;
      if ( !SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        LastError = GetLastError();
        OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"SQLServiceControlHandler", OSErrString);
      }
      qword_1004D28C0 = CreateEventA(0, 1, 0, 0);
      LeaveCriticalSection(&SCMCrtSec);
      if ( !qword_1004D28C0 )
      {
        v18 = GetLastError();
        v19 = GetOSErrString(v18, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"initsignal:CreateEvent", v19);
        SQLExit(249, 17143, 1066);
      }
      v20 = (void *)_beginthreadex(0, 0, incrementsignal, (void *)3, 0, &ThrdAddr);
      if ( !v20 )
      {
        scierrlog(0x42E0u, L"incrementsignal");
        SQLExit(250, 17120, 1066);
      }
      SetThreadPriority(v20, 2);
      SetThreadAffinityMask(v20, 1u);
      CloseHandle(v20);
      SetShutdownOption(2, 0);
      goto LABEL_43;
    case 2u:
      EnterCriticalSection(&SCMCrtSec);
      if ( (*((_BYTE *)qword_10049F360 + 48) & 0x40) != 0 )
        goto LABEL_33;
      SQLServiceStatus.dwCurrentState = 7;
      *((_DWORD *)qword_10049F360 + 12) |= 0x40u;
      if ( SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        scierrlog(0x42F8u);
      }
      else
      {
        v14 = GetLastError();
        v15 = GetOSErrString(v14, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"SQLServiceControlHandler", v15);
      }
      if ( *((_DWORD *)qword_10049F360 + 3648) )
        goto LABEL_33;
      *((_DWORD *)qword_10049F360 + 3648) = 1;
LABEL_32:
      EventManualInternal<SuspendQueueSLock>::Signal(&off_1004A08D8, 0);
      goto LABEL_33;
    case 3u:
      EnterCriticalSection(&SCMCrtSec);
      if ( (*((_BYTE *)qword_10049F360 + 48) & 0x40) == 0 )
        goto LABEL_33;
      SQLServiceStatus.dwCurrentState = 4;
      *((_DWORD *)qword_10049F360 + 12) &= ~0x40u;
      if ( SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        scierrlog(0x42FAu);
      }
      else
      {
        v12 = GetLastError();
        v13 = GetOSErrString(v12, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"SQLServiceControlHandler", v13);
      }
      if ( *((_DWORD *)qword_10049F360 + 3648) )
        goto LABEL_33;
      *((_DWORD *)qword_10049F360 + 3648) = 2;
      goto LABEL_32;
    case 4u:
      EnterCriticalSection(&SCMCrtSec);
      if ( !SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        v10 = GetLastError();
        v11 = GetOSErrString(v10, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"SQLServiceControlHandler", v11);
        LeaveCriticalSection(&SCMCrtSec);
        goto LABEL_44;
      }
LABEL_33:
      LeaveCriticalSection(&SCMCrtSec);
      goto LABEL_44;
    case 5u:
      EnterCriticalSection(&SCMCrtSec);
      SQLServiceStatus.dwCurrentState = 3;
      *(_QWORD *)&SQLServiceStatus.dwWin32ExitCode = 0;
      SQLServiceStatus.dwCheckPoint = 1;
      SQLServiceStatus.dwWaitHint = 20000;
      if ( !SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
      {
        v8 = GetLastError();
        v9 = GetOSErrString(v8, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0x42F7u, L"SQLServiceControlHandler", v9);
      }
      LeaveCriticalSection(&SCMCrtSec);
      SetShutdownOption(2, 0);
      if ( !ShutdownMessageLogged )
      {
        ShutdownMessageLogged = 1;
        scierrlog(0x42FBu);
      }
LABEL_43:
      EventManualInternal<SuspendQueueSLock>::Signal(&off_1004A08D8, 0);
      goto LABEL_44;
  }
  scierrlog(0x42F9u, dwControl);
LABEL_44:
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v24);
}

```

## disassembly

```asm
0x10040bec0  push    rbp
0x10040bec2  mov     eax, 2800h
0x10040bec7  call    _alloca_probe
0x10040becc  sub     rsp, rax
0x10040becf  lea     rbp, [rsp+40h]
0x10040bed4  mov     [rbp+27C0h+var_27B8], 0FFFFFFFFFFFFFFFEh
0x10040bedc  mov     [rbp+27C0h+arg_8], rbx
0x10040bee3  mov     [rbp+27C0h+arg_10], rdi
0x10040beea  mov     rax, cs:__security_cookie
0x10040bef1  xor     rax, rbp
0x10040bef4  mov     [rbp+27C0h+var_10], rax
0x10040befb  mov     ebx, ecx
0x10040befd  mov     rax, cs:qword_10049F360
0x10040bf04  xor     edi, edi
0x10040bf06  cmp     [rax+0A4C0h], edi
0x10040bf0c  jnz     short loc_10040BF30
0x10040bf0e  mov     qword ptr [rsp+2800h+InitFlag], rdi
0x10040bf13  mov     r9d, 3ECh
0x10040bf19  lea     r8, aDbsignalCpp; "dbsignal.cpp"
0x10040bf20  lea     rdx, aGetsrvctrman; "GetSrvCtrMan()"
0x10040bf27  lea     ecx, [rdi+1]
0x10040bf2a  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10040bf30  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040bf37  mov     r8, [rax+8]
0x10040bf3b  test    r8, r8
0x10040bf3e  jz      short loc_10040BF71
0x10040bf40  lea     rax, ds:0[r8*8]
0x10040bf48  lea     rcx, [rax+0Fh]
0x10040bf4c  cmp     rcx, rax
0x10040bf4f  ja      short loc_10040BF5B
0x10040bf51  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10040bf5b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10040bf5f  mov     rax, rcx
0x10040bf62  call    _alloca_probe
0x10040bf67  sub     rsp, rcx
0x10040bf6a  lea     r9, [rsp+2800h+var_27C0]
0x10040bf6f  jmp     short loc_10040BF74
0x10040bf71  mov     r9, rdi
0x10040bf74  mov     [rsp+2800h+var_27D0], rdi
0x10040bf79  mov     [rsp+2800h+ThrdAddr], rdi
0x10040bf7e  mov     [rsp+2800h+InitFlag], 1
0x10040bf86  xor     edx, edx
0x10040bf88  lea     rcx, [rbp+27C0h+var_17B0]
0x10040bf8f  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040bf95  nop
0x10040bf96  mov     eax, ebx
0x10040bf98  sub     eax, 1
0x10040bf9b  jz      loc_10040C242
0x10040bfa1  sub     eax, 1
0x10040bfa4  jz      loc_10040C18C
0x10040bfaa  sub     eax, 1
0x10040bfad  jz      loc_10040C0ED
0x10040bfb3  sub     eax, 1
0x10040bfb6  jz      loc_10040C086
0x10040bfbc  cmp     eax, 1
0x10040bfbf  jz      short loc_10040BFD2
0x10040bfc1  mov     edx, ebx
0x10040bfc3  mov     ecx, 42F9h; unsigned int
0x10040bfc8  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040bfcd  jmp     loc_10040C3D4
0x10040bfd2  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040bfd9  call    cs:__imp_EnterCriticalSection
0x10040bfdf  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS SQLServiceStatus ...
0x10040bfe9  mov     qword ptr cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rdi; _SERVICE_STATUS SQLServiceStatus ...
0x10040bff0  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS SQLServiceStatus ...
0x10040bffa  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 4E20h; _SERVICE_STATUS SQLServiceStatus ...
0x10040c004  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c00b  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c012  call    cs:__imp_SetServiceStatus
0x10040c018  test    eax, eax
0x10040c01a  jnz     short loc_10040C048
0x10040c01c  call    cs:__imp_GetLastError
0x10040c022  mov     ecx, eax
0x10040c024  xor     r9d, r9d
0x10040c027  xor     r8d, r8d
0x10040c02a  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c02e  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c034  mov     r8, rax
0x10040c037  lea     rdx, aSqlservicecont; "SQLServiceControlHandler"
0x10040c03e  mov     ecx, 42F7h; unsigned int
0x10040c043  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c048  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c04f  call    cs:__imp_LeaveCriticalSection
0x10040c055  xor     edx, edx
0x10040c057  lea     ecx, [rdx+2]
0x10040c05a  call    cs:__imp_?SetShutdownOption@@YAXW4ShutdownOption@@K@Z; SetShutdownOption(ShutdownOption,ulong)
0x10040c060  cmp     cs:?ShutdownMessageLogged@@3HA, 0; int ShutdownMessageLogged
0x10040c067  jnz     loc_10040C3C5
0x10040c06d  mov     cs:?ShutdownMessageLogged@@3HA, 1; int ShutdownMessageLogged
0x10040c077  mov     ecx, 42FBh; unsigned int
0x10040c07c  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c081  jmp     loc_10040C3C5
0x10040c086  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c08d  call    cs:__imp_EnterCriticalSection
0x10040c093  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c09a  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c0a1  call    cs:__imp_SetServiceStatus
0x10040c0a7  test    eax, eax
0x10040c0a9  jnz     loc_10040C230
0x10040c0af  call    cs:__imp_GetLastError
0x10040c0b5  mov     ecx, eax
0x10040c0b7  xor     r9d, r9d
0x10040c0ba  xor     r8d, r8d
0x10040c0bd  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c0c1  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c0c7  mov     r8, rax
0x10040c0ca  lea     rdx, aSqlservicecont; "SQLServiceControlHandler"
0x10040c0d1  mov     ecx, 42F7h; unsigned int
0x10040c0d6  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c0db  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c0e2  call    cs:__imp_LeaveCriticalSection
0x10040c0e8  jmp     loc_10040C3D4
0x10040c0ed  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c0f4  call    cs:__imp_EnterCriticalSection
0x10040c0fa  mov     rax, cs:qword_10049F360
0x10040c101  test    byte ptr [rax+30h], 40h
0x10040c105  jz      loc_10040C230
0x10040c10b  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS SQLServiceStatus ...
0x10040c115  and     dword ptr [rax+30h], 0FFFFFFBFh
0x10040c119  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c120  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c127  call    cs:__imp_SetServiceStatus
0x10040c12d  test    eax, eax
0x10040c12f  jnz     short loc_10040C15F
0x10040c131  call    cs:__imp_GetLastError
0x10040c137  mov     ecx, eax
0x10040c139  xor     r9d, r9d
0x10040c13c  xor     r8d, r8d
0x10040c13f  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c143  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c149  mov     r8, rax
0x10040c14c  lea     rdx, aSqlservicecont; "SQLServiceControlHandler"
0x10040c153  mov     ecx, 42F7h; unsigned int
0x10040c158  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c15d  jmp     short loc_10040C169
0x10040c15f  mov     ecx, 42FAh; unsigned int
0x10040c164  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c169  mov     rax, cs:qword_10049F360
0x10040c170  cmp     dword ptr [rax+3900h], 0
0x10040c177  jnz     loc_10040C230
0x10040c17d  mov     dword ptr [rax+3900h], 2
0x10040c187  jmp     loc_10040C222
0x10040c18c  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c193  call    cs:__imp_EnterCriticalSection
0x10040c199  mov     rax, cs:qword_10049F360
0x10040c1a0  test    byte ptr [rax+30h], 40h
0x10040c1a4  jnz     loc_10040C230
0x10040c1aa  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 7; _SERVICE_STATUS SQLServiceStatus ...
0x10040c1b4  or      dword ptr [rax+30h], 40h
0x10040c1b8  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c1bf  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c1c6  call    cs:__imp_SetServiceStatus
0x10040c1cc  test    eax, eax
0x10040c1ce  jnz     short loc_10040C1FE
0x10040c1d0  call    cs:__imp_GetLastError
0x10040c1d6  mov     ecx, eax
0x10040c1d8  xor     r9d, r9d
0x10040c1db  xor     r8d, r8d
0x10040c1de  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c1e2  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c1e8  mov     r8, rax
0x10040c1eb  lea     rdx, aSqlservicecont; "SQLServiceControlHandler"
0x10040c1f2  mov     ecx, 42F7h; unsigned int
0x10040c1f7  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c1fc  jmp     short loc_10040C208
0x10040c1fe  mov     ecx, 42F8h; unsigned int
0x10040c203  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c208  mov     rax, cs:qword_10049F360
0x10040c20f  cmp     dword ptr [rax+3900h], 0
0x10040c216  jnz     short loc_10040C230
0x10040c218  mov     dword ptr [rax+3900h], 1
0x10040c222  xor     edx, edx
0x10040c224  lea     rcx, off_1004A08D8
0x10040c22b  call    ?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x10040c230  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c237  call    cs:__imp_LeaveCriticalSection
0x10040c23d  jmp     loc_10040C3D4
0x10040c242  mov     rax, cs:qword_10049F360
0x10040c249  test    byte ptr [rax+30h], 20h
0x10040c24d  jz      short loc_10040C25A
0x10040c24f  mov     ecx, 0F8h
0x10040c254  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x10040c25a  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c261  call    cs:__imp_EnterCriticalSection
0x10040c267  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS SQLServiceStatus ...
0x10040c271  mov     qword ptr cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rdi; _SERVICE_STATUS SQLServiceStatus ...
0x10040c278  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS SQLServiceStatus ...
0x10040c282  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS SQLServiceStatus ...
0x10040c28c  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c293  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c29a  call    cs:__imp_SetServiceStatus
0x10040c2a0  test    eax, eax
0x10040c2a2  jnz     short loc_10040C2D0
0x10040c2a4  call    cs:__imp_GetLastError
0x10040c2aa  mov     ecx, eax
0x10040c2ac  xor     r9d, r9d
0x10040c2af  xor     r8d, r8d
0x10040c2b2  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c2b6  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c2bc  mov     r8, rax
0x10040c2bf  lea     rdx, aSqlservicecont; "SQLServiceControlHandler"
0x10040c2c6  mov     ecx, 42F7h; unsigned int
0x10040c2cb  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c2d0  xor     r9d, r9d; lpName
0x10040c2d3  xor     r8d, r8d; bInitialState
0x10040c2d6  lea     edx, [r9+1]; bManualReset
0x10040c2da  xor     ecx, ecx; lpEventAttributes
0x10040c2dc  call    cs:__imp_CreateEventA
0x10040c2e2  mov     cs:qword_1004D28C0, rax
0x10040c2e9  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c2f0  call    cs:__imp_LeaveCriticalSection
0x10040c2f6  cmp     cs:qword_1004D28C0, 0
0x10040c2fe  jnz     short loc_10040C342
0x10040c300  call    cs:__imp_GetLastError
0x10040c306  mov     ecx, eax
0x10040c308  xor     r9d, r9d
0x10040c30b  xor     r8d, r8d
0x10040c30e  lea     rdx, [rbp+27C0h+var_27B0]
0x10040c312  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040c318  mov     r8, rax
0x10040c31b  lea     rdx, aInitsignalCrea; "initsignal:CreateEvent"
0x10040c322  mov     ecx, 42F7h; unsigned int
0x10040c327  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c32c  mov     edx, 42F7h
0x10040c331  mov     ecx, 0F9h
0x10040c336  mov     r8d, 42Ah
0x10040c33c  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040c342  lea     rax, [rbp+27C0h+var_27C0]
0x10040c346  mov     [rsp+2800h+ThrdAddr], rax; ThrdAddr
0x10040c34b  mov     [rsp+2800h+InitFlag], edi; InitFlag
0x10040c34f  mov     r9d, 3; ArgList
0x10040c355  lea     r8, ?incrementsignal@@YAIPEAX@Z; StartAddress
0x10040c35c  xor     edx, edx; StackSize
0x10040c35e  xor     ecx, ecx; Security
0x10040c360  call    cs:__imp__beginthreadex
0x10040c366  mov     rbx, rax
0x10040c369  test    rax, rax
0x10040c36c  jnz     short loc_10040C395
0x10040c36e  lea     rdx, aIncrementsigna; "incrementsignal"
0x10040c375  mov     ecx, 42E0h; unsigned int
0x10040c37a  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040c37f  mov     edx, 42E0h
0x10040c384  mov     ecx, 0FAh
0x10040c389  mov     r8d, 42Ah
0x10040c38f  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040c395  mov     edx, 2; nPriority
0x10040c39a  mov     rcx, rbx; hThread
0x10040c39d  call    cs:__imp_SetThreadPriority
0x10040c3a3  mov     edx, 1; dwThreadAffinityMask
0x10040c3a8  mov     rcx, rbx; hThread
0x10040c3ab  call    cs:__imp_SetThreadAffinityMask
0x10040c3b1  mov     rcx, rbx; hObject
0x10040c3b4  call    cs:__imp_CloseHandle
0x10040c3ba  xor     edx, edx
0x10040c3bc  lea     ecx, [rdx+2]
0x10040c3bf  call    cs:__imp_?SetShutdownOption@@YAXW4ShutdownOption@@K@Z; SetShutdownOption(ShutdownOption,ulong)
0x10040c3c5  xor     edx, edx
0x10040c3c7  lea     rcx, off_1004A08D8
0x10040c3ce  call    ?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x10040c3d3  nop
0x10040c3d4  lea     rcx, [rbp+27C0h+var_17B0]
0x10040c3db  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040c3e1  mov     rcx, [rbp+27C0h+var_10]
0x10040c3e8  xor     rcx, rbp; StackCookie
0x10040c3eb  call    __security_check_cookie
0x10040c3f0  mov     rbx, [rbp+27C0h+arg_8]
0x10040c3f7  mov     rdi, [rbp+27C0h+arg_10]
0x10040c3fe  lea     rsp, [rbp+27C0h]
0x10040c405  pop     rbp
0x10040c406  retn
```
