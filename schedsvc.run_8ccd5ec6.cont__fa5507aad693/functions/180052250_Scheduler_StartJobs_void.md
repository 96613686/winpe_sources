# Scheduler::StartJobs(void)

- ea: `0x180052250`
- end: `0x1800524ce`
- name: `?StartJobs@Scheduler@@QEAAJXZ`
- size: `638`
- prototype: `__int64 __fastcall(Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002e520`

## callees

- `0x18000ff10`
- `0x180013a90`
- `0x18001ea40`
- `0x18002db74`
- `0x180043478`
- `0x180051384`
- `0x180052250`
- `0x1800524d4`
- `0x1800525c0`
- `0x18005dcd4`
- `0x18006d680`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052304`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052304`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005228a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005228a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005233e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005233e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052497`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800522cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800522cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052430`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Scheduler::StartJobs(Scheduler *this)
{
  __int64 v2; // rax
  bool v3; // dl
  __int64 v4; // r14
  int v5; // ebx
  const unsigned __int16 *Path; // rax
  EventManager *v7; // rcx
  _QWORD *v8; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-29h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-21h] BYREF
  __int128 v12; // [rsp+40h] [rbp-19h] BYREF
  struct _GUID v13; // [rsp+50h] [rbp-9h] BYREF
  GUID iid; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+80h] [rbp+27h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *(_QWORD *)&SystemTimeAsFileTime + 5000000LL;
  SystemTimeAsFileTime.dwLowDateTime += 5000000;
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v2);
  while ( 1 )
  {
    JobMoniker::JobMoniker(&iid, 0, 0);
    FileTime1 = 0;
    TSTime::TSTime((TSTime *)&v12, v3);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v4 = *((_QWORD *)this + 10);
    if ( !*(_DWORD *)(v4 + 24) && !*(_DWORD *)(v4 + 28) )
      break;
    FileTime1 = *(FILETIME *)(v4 + 24);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) > 0 )
    {
      TraceTime("Scheduler::StartJobs: run time in the future", &FileTime1, (const struct JobMoniker *)(v4 + 40));
      goto LABEL_14;
    }
    JobMoniker::operator=(&iid, v4 + 40);
    v12 = *(_OWORD *)(v4 + 80);
    v5 = *(_DWORD *)(v4 + 36);
    SortedRunListItem::Delete((SortedRunListItem *)v4);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    TraceTime("Scheduler::StartJobs: starting", &FileTime1, (const struct JobMoniker *)&iid);
    if ( v5 == 2 )
    {
      *(_QWORD *)&v13.Data1 = 0;
      *(_QWORD *)v13.Data4 = 0;
      Path = JobMoniker::GetPath((JobMoniker *)&iid);
      EventManager::EvtReport(v7, &TIME_TRIGGER, Path, &v13);
      JobStore::DeleteExpiredTask(JobStore::m_pCommonStore, (const struct JobMoniker *)&iid);
      if ( (*(_DWORD *)(v15 + 16) & 0x2000000) != 0 )
        (*((void (__fastcall **)(void ***, GUID *))UbpmProxySingleton::s_singleton[0] + 1))(
          UbpmProxySingleton::s_singleton,
          &iid);
    }
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids);
  }
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v8 == (_QWORD *)((char *)this + 72) )
  {
    *((_QWORD *)this + 21) = -1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids);
    }
  }
  else
  {
    *((_QWORD *)this + 21) = v8[3];
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return 0;
}

```

## disassembly

```asm
0x180052250  mov     [rsp-8+arg_8], rbx
0x180052255  mov     [rsp-8+arg_10], rsi
0x18005225a  push    rbp
0x18005225b  push    rdi
0x18005225c  push    r13
0x18005225e  push    r14
0x180052260  push    r15
0x180052262  lea     rbp, [rsp-37h]
0x180052267  sub     rsp, 90h
0x18005226e  mov     rax, cs:__security_cookie
0x180052275  xor     rax, rsp
0x180052278  mov     [rbp+57h+var_28], rax
0x18005227c  mov     rsi, rcx
0x18005227f  xor     r15d, r15d
0x180052282  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180052286  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005228a  call    cs:__imp_GetSystemTimeAsFileTime
0x180052291  nop     dword ptr [rax+rax+00h]
0x180052296  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18005229a  add     rax, 4C4B40h
0x1800522a0  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1800522a3  shr     rax, 20h
0x1800522a7  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], eax
0x1800522aa  lea     rdi, [rsi+20h]
0x1800522ae  xor     r8d, r8d; unsigned __int16 *
0x1800522b1  xor     edx, edx; psz
0x1800522b3  lea     rcx, [rbp+57h+iid]; lpiid
0x1800522b7  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x1800522bc  nop
0x1800522bd  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r15
0x1800522c1  lea     rcx, [rbp+57h+var_70]; this
0x1800522c5  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x1800522ca  mov     rcx, rdi; lpCriticalSection
0x1800522cd  call    cs:__imp_EnterCriticalSection
0x1800522d4  nop     dword ptr [rax+rax+00h]
0x1800522d9  mov     r14, [rsi+50h]
0x1800522dd  lea     r13, WPP_GLOBAL_Control
0x1800522e4  cmp     [r14+18h], r15d
0x1800522e8  jnz     short loc_1800522F4
0x1800522ea  cmp     [r14+1Ch], r15d
0x1800522ee  jz      loc_1800523CE
0x1800522f4  mov     rax, [r14+18h]
0x1800522f8  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x1800522fc  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180052300  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180052304  call    cs:__imp_CompareFileTime
0x18005230b  nop     dword ptr [rax+rax+00h]
0x180052310  test    eax, eax
0x180052312  jg      loc_180052400
0x180052318  lea     rdx, [r14+28h]
0x18005231c  lea     rcx, [rbp+57h+iid]
0x180052320  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x180052325  movups  xmm0, xmmword ptr [r14+50h]
0x18005232a  movdqu  [rbp+57h+var_70], xmm0
0x18005232f  mov     ebx, [r14+24h]
0x180052333  mov     rcx, r14; this
0x180052336  call    ?Delete@SortedRunListItem@@QEAAXXZ; SortedRunListItem::Delete(void)
0x18005233b  mov     rcx, rdi; lpCriticalSection
0x18005233e  call    cs:__imp_LeaveCriticalSection
0x180052345  nop     dword ptr [rax+rax+00h]
0x18005234a  lea     r8, [rbp+57h+iid]; struct JobMoniker *
0x18005234e  lea     rdx, [rbp+57h+FileTime1]; struct _FILETIME *
0x180052352  lea     rcx, aSchedulerStart_0; "Scheduler::StartJobs: starting"
0x180052359  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x18005235e  cmp     ebx, 2
0x180052361  jnz     short loc_1800523C0
0x180052363  mov     qword ptr [rbp+57h+var_60.Data1], r15
0x180052367  mov     qword ptr [rbp+57h+var_60.Data4], r15
0x18005236b  lea     rcx, [rbp+57h+iid]; this
0x18005236f  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180052374  lea     r9, [rbp+57h+var_60]; struct _GUID *
0x180052378  mov     r8, rax; unsigned __int16 *
0x18005237b  lea     rdx, TIME_TRIGGER; struct _EVENT_DESCRIPTOR *
0x180052382  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@PEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,void *,_GUID const *)
0x180052387  lea     rdx, [rbp+57h+iid]; struct JobMoniker *
0x18005238b  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x180052392  call    ?DeleteExpiredTask@JobStore@@QEAAJAEBVJobMoniker@@@Z; JobStore::DeleteExpiredTask(JobMoniker const &)
0x180052397  mov     rax, [rbp+57h+var_30]
0x18005239b  test    dword ptr [rax+10h], 2000000h
0x1800523a2  jz      short loc_1800523C0
0x1800523a4  mov     rax, cs:?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x1800523ab  lea     rdx, [rbp+57h+iid]
0x1800523af  lea     rcx, ?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x1800523b6  mov     rax, [rax+8]
0x1800523ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523bf  nop
0x1800523c0  lea     rcx, [rbp+57h+iid]; this
0x1800523c4  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x1800523c9  jmp     loc_1800522AE
0x1800523ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523d5  cmp     rcx, r13
0x1800523d8  jz      short loc_180052414
0x1800523da  test    dword ptr [rcx+1Ch], 2000h
0x1800523e1  jz      short loc_180052414
0x1800523e3  cmp     byte ptr [rcx+19h], 4
0x1800523e7  jb      short loc_180052414
0x1800523e9  mov     edx, 16h
0x1800523ee  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x1800523f5  mov     rcx, [rcx+10h]
0x1800523f9  call    WPP_SF_
0x1800523fe  jmp     short loc_180052414
0x180052400  lea     r8, [r14+28h]; struct JobMoniker *
0x180052404  lea     rdx, [rbp+57h+FileTime1]; struct _FILETIME *
0x180052408  lea     rcx, aSchedulerStart; "Scheduler::StartJobs: run time in the f"...
0x18005240f  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x180052414  mov     rcx, rdi; lpCriticalSection
0x180052417  call    cs:__imp_LeaveCriticalSection
0x18005241e  nop     dword ptr [rax+rax+00h]
0x180052423  nop
0x180052424  lea     rcx, [rbp+57h+iid]; this
0x180052428  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18005242d  mov     rcx, rdi; lpCriticalSection
0x180052430  call    cs:__imp_EnterCriticalSection
0x180052437  nop     dword ptr [rax+rax+00h]
0x18005243c  lea     rax, [rsi+48h]
0x180052440  mov     rcx, [rax+8]
0x180052444  cmp     rcx, rax
0x180052447  jnz     short loc_180052489
0x180052449  mov     rax, qword ptr cs:FileTime2.dwLowDateTime
0x180052450  mov     [rsi+0A8h], rax
0x180052457  mov     rcx, cs:WPP_GLOBAL_Control
0x18005245e  cmp     rcx, r13
0x180052461  jz      short loc_180052494
0x180052463  test    dword ptr [rcx+1Ch], 2000h
0x18005246a  jz      short loc_180052494
0x18005246c  cmp     byte ptr [rcx+19h], 4
0x180052470  jb      short loc_180052494
0x180052472  mov     edx, 17h
0x180052477  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18005247e  mov     rcx, [rcx+10h]
0x180052482  call    WPP_SF_
0x180052487  jmp     short loc_180052494
0x180052489  mov     rax, [rcx+18h]
0x18005248d  mov     [rsi+0A8h], rax
0x180052494  mov     rcx, rdi; lpCriticalSection
0x180052497  call    cs:__imp_LeaveCriticalSection
0x18005249e  nop     dword ptr [rax+rax+00h]
0x1800524a3  xor     eax, eax
0x1800524a5  mov     rcx, [rbp+57h+var_28]
0x1800524a9  xor     rcx, rsp; StackCookie
0x1800524ac  call    __security_check_cookie
0x1800524b1  lea     r11, [rsp+0B0h+var_20]
0x1800524b9  mov     rbx, [r11+38h]
0x1800524bd  mov     rsi, [r11+40h]
0x1800524c1  mov     rsp, r11
0x1800524c4  pop     r15
0x1800524c6  pop     r14
0x1800524c8  pop     r13
0x1800524ca  pop     rdi
0x1800524cb  pop     rbp
0x1800524cc  retn
```
