# Scheduler::StartJobs(void)

- ea: `0x18004f984`
- end: `0x18004fbd7`
- name: `?StartJobs@Scheduler@@QEAAJXZ`
- size: `595`
- prototype: `__int64 __fastcall(Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180038890`

## callees

- `0x18001a430`
- `0x18002132c`
- `0x180022600`
- `0x18003fff0`
- `0x180040b70`
- `0x18004f984`
- `0x18004fbe0`
- `0x18004fccc`
- `0x180050028`
- `0x18005b124`
- `0x18006a218`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004fa2c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004fa2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f9be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f9be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fa60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fa60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fba7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f9fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f9fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb46`

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
0x18004f984  mov     [rsp-8+arg_8], rbx
0x18004f989  mov     [rsp-8+arg_10], rsi
0x18004f98e  push    rbp
0x18004f98f  push    rdi
0x18004f990  push    r13
0x18004f992  push    r14
0x18004f994  push    r15
0x18004f996  lea     rbp, [rsp-37h]
0x18004f99b  sub     rsp, 90h
0x18004f9a2  mov     rax, cs:__security_cookie
0x18004f9a9  xor     rax, rsp
0x18004f9ac  mov     [rbp+57h+var_28], rax
0x18004f9b0  mov     rsi, rcx
0x18004f9b3  xor     r15d, r15d
0x18004f9b6  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18004f9ba  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004f9be  call    cs:__imp_GetSystemTimeAsFileTime
0x18004f9c4  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18004f9c8  add     rax, 4C4B40h
0x18004f9ce  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18004f9d1  shr     rax, 20h
0x18004f9d5  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], eax
0x18004f9d8  lea     rdi, [rsi+20h]
0x18004f9dc  xor     r8d, r8d; unsigned __int16 *
0x18004f9df  xor     edx, edx; psz
0x18004f9e1  lea     rcx, [rbp+57h+iid]; lpiid
0x18004f9e5  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18004f9ea  nop
0x18004f9eb  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r15
0x18004f9ef  lea     rcx, [rbp+57h+var_70]; this
0x18004f9f3  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18004f9f8  mov     rcx, rdi; lpCriticalSection
0x18004f9fb  call    cs:__imp_EnterCriticalSection
0x18004fa01  mov     r14, [rsi+50h]
0x18004fa05  lea     r13, WPP_GLOBAL_Control
0x18004fa0c  cmp     [r14+18h], r15d
0x18004fa10  jnz     short loc_18004FA1C
0x18004fa12  cmp     [r14+1Ch], r15d
0x18004fa16  jz      loc_18004FAEA
0x18004fa1c  mov     rax, [r14+18h]
0x18004fa20  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x18004fa24  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x18004fa28  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18004fa2c  call    cs:__imp_CompareFileTime
0x18004fa32  test    eax, eax
0x18004fa34  jg      loc_18004FB1C
0x18004fa3a  lea     rdx, [r14+28h]
0x18004fa3e  lea     rcx, [rbp+57h+iid]
0x18004fa42  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x18004fa47  movups  xmm0, xmmword ptr [r14+50h]
0x18004fa4c  movdqu  [rbp+57h+var_70], xmm0
0x18004fa51  mov     ebx, [r14+24h]
0x18004fa55  mov     rcx, r14; this
0x18004fa58  call    ?Delete@SortedRunListItem@@QEAAXXZ; SortedRunListItem::Delete(void)
0x18004fa5d  mov     rcx, rdi; lpCriticalSection
0x18004fa60  call    cs:__imp_LeaveCriticalSection
0x18004fa66  lea     r8, [rbp+57h+iid]; struct JobMoniker *
0x18004fa6a  lea     rdx, [rbp+57h+FileTime1]; struct _FILETIME *
0x18004fa6e  lea     rcx, aSchedulerStart_0; "Scheduler::StartJobs: starting"
0x18004fa75  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x18004fa7a  cmp     ebx, 2
0x18004fa7d  jnz     short loc_18004FADC
0x18004fa7f  mov     qword ptr [rbp+57h+var_60.Data1], r15
0x18004fa83  mov     qword ptr [rbp+57h+var_60.Data4], r15
0x18004fa87  lea     rcx, [rbp+57h+iid]; this
0x18004fa8b  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004fa90  lea     r9, [rbp+57h+var_60]; struct _GUID *
0x18004fa94  mov     r8, rax; unsigned __int16 *
0x18004fa97  lea     rdx, TIME_TRIGGER; struct _EVENT_DESCRIPTOR *
0x18004fa9e  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@PEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,void *,_GUID const *)
0x18004faa3  lea     rdx, [rbp+57h+iid]; struct JobMoniker *
0x18004faa7  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x18004faae  call    ?DeleteExpiredTask@JobStore@@QEAAJAEBVJobMoniker@@@Z; JobStore::DeleteExpiredTask(JobMoniker const &)
0x18004fab3  mov     rax, [rbp+57h+var_30]
0x18004fab7  test    dword ptr [rax+10h], 2000000h
0x18004fabe  jz      short loc_18004FADC
0x18004fac0  mov     rax, cs:?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x18004fac7  lea     rdx, [rbp+57h+iid]
0x18004facb  lea     rcx, ?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x18004fad2  mov     rax, [rax+8]
0x18004fad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fadb  nop
0x18004fadc  lea     rcx, [rbp+57h+iid]; this
0x18004fae0  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18004fae5  jmp     loc_18004F9DC
0x18004faea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004faf1  cmp     rcx, r13
0x18004faf4  jz      short loc_18004FB30
0x18004faf6  test    dword ptr [rcx+1Ch], 2000h
0x18004fafd  jz      short loc_18004FB30
0x18004faff  cmp     byte ptr [rcx+19h], 4
0x18004fb03  jb      short loc_18004FB30
0x18004fb05  mov     edx, 16h
0x18004fb0a  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18004fb11  mov     rcx, [rcx+10h]
0x18004fb15  call    WPP_SF_
0x18004fb1a  jmp     short loc_18004FB30
0x18004fb1c  lea     r8, [r14+28h]; struct JobMoniker *
0x18004fb20  lea     rdx, [rbp+57h+FileTime1]; struct _FILETIME *
0x18004fb24  lea     rcx, aSchedulerStart; "Scheduler::StartJobs: run time in the f"...
0x18004fb2b  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x18004fb30  mov     rcx, rdi; lpCriticalSection
0x18004fb33  call    cs:__imp_LeaveCriticalSection
0x18004fb39  nop
0x18004fb3a  lea     rcx, [rbp+57h+iid]; this
0x18004fb3e  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18004fb43  mov     rcx, rdi; lpCriticalSection
0x18004fb46  call    cs:__imp_EnterCriticalSection
0x18004fb4c  lea     rax, [rsi+48h]
0x18004fb50  mov     rcx, [rax+8]
0x18004fb54  cmp     rcx, rax
0x18004fb57  jnz     short loc_18004FB99
0x18004fb59  mov     rax, qword ptr cs:FileTime2.dwLowDateTime
0x18004fb60  mov     [rsi+0A8h], rax
0x18004fb67  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb6e  cmp     rcx, r13
0x18004fb71  jz      short loc_18004FBA4
0x18004fb73  test    dword ptr [rcx+1Ch], 2000h
0x18004fb7a  jz      short loc_18004FBA4
0x18004fb7c  cmp     byte ptr [rcx+19h], 4
0x18004fb80  jb      short loc_18004FBA4
0x18004fb82  mov     edx, 17h
0x18004fb87  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18004fb8e  mov     rcx, [rcx+10h]
0x18004fb92  call    WPP_SF_
0x18004fb97  jmp     short loc_18004FBA4
0x18004fb99  mov     rax, [rcx+18h]
0x18004fb9d  mov     [rsi+0A8h], rax
0x18004fba4  mov     rcx, rdi; lpCriticalSection
0x18004fba7  call    cs:__imp_LeaveCriticalSection
0x18004fbad  xor     eax, eax
0x18004fbaf  mov     rcx, [rbp+57h+var_28]
0x18004fbb3  xor     rcx, rsp; StackCookie
0x18004fbb6  call    __security_check_cookie
0x18004fbbb  lea     r11, [rsp+0B0h+var_20]
0x18004fbc3  mov     rbx, [r11+38h]
0x18004fbc7  mov     rsi, [r11+40h]
0x18004fbcb  mov     rsp, r11
0x18004fbce  pop     r15
0x18004fbd0  pop     r14
0x18004fbd2  pop     r13
0x18004fbd4  pop     rdi
0x18004fbd5  pop     rbp
0x18004fbd6  retn
```
