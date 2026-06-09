# Scheduler::EvaluateScheduledJob(Scheduling::JobSchedule &,JobMoniker const &,TSTime,TSTime)

- ea: `0x1800514b0`
- end: `0x180051721`
- name: `?EvaluateScheduledJob@Scheduler@@AEAAJAEAVJobSchedule@Scheduling@@AEBVJobMoniker@@VTSTime@@2@Z`
- size: `625`
- prototype: `int __high(struct Scheduling::JobSchedule *, const struct JobMoniker *, struct TSTime, struct TSTime)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800513b8`
- `0x18006c210`
- `0x18006c7e4`

## callees

- `0x18002db74`
- `0x180037b40`
- `0x1800422f0`
- `0x1800514b0`
- `0x18005176c`
- `0x180054eb8`
- `0x180067290`
- `0x18006ce60`
- `0x18006d498`
- `0x18006d680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516df`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005160f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005160f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005162d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005162d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800515d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800515d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800516cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800516cf`

## string_xrefs

- `0x180051676`: `Scheduler::EvaluateScheduledJob: nextRun=`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Scheduler::EvaluateScheduledJob(__int64 a1, __int64 a2, JobMoniker *a3, __int128 *a4, __int128 *a5)
{
  signed int RunTimes; // edi
  char v8; // bl
  unsigned int Path; // eax
  int v10; // edx
  int v11; // r8d
  struct RunListItem *v12; // rbx
  char v13; // r14
  const struct TSTime *Stop; // rax
  const unsigned __int16 *v15; // rax
  signed int LastError; // eax
  __int128 v18; // [rsp+30h] [rbp-41h] BYREF
  __int128 v19; // [rsp+40h] [rbp-31h] BYREF
  void **v20; // [rsp+50h] [rbp-21h] BYREF
  struct RunListItem *v21; // [rsp+58h] [rbp-19h]
  void ***v22; // [rsp+60h] [rbp-11h]
  __int64 v23; // [rsp+68h] [rbp-9h]
  __int64 v24; // [rsp+70h] [rbp-1h]
  int v25; // [rsp+78h] [rbp+7h]
  int v26; // [rsp+7Ch] [rbp+Bh]
  int v27; // [rsp+80h] [rbp+Fh]
  FILETIME FileTime1; // [rsp+E8h] [rbp+77h] BYREF

  v20 = &RunListItem::`vftable';
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = -1;
  v27 = 0;
  v21 = (struct RunListItem *)&v20;
  v22 = &v20;
  v18 = *a5;
  v19 = *a4;
  RunTimes = Scheduling::JobSchedule::GetRunTimes(a2, &v19, &v18, &v20, -1);
  LODWORD(a5) = RunTimes;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((RunTimes >> 31) & 0xFFFFFFFE) + 4 )
  {
    v8 = v25;
    Path = (unsigned int)JobMoniker::GetPath(a3);
    WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, Path, RunTimes, v8);
  }
  if ( RunTimes >= 0 )
  {
    FileTime1 = 0;
    v12 = v21;
    v13 = 0;
    while ( *((_DWORD *)v12 + 6) || *((_DWORD *)v12 + 7) )
    {
      FileTime1 = (FILETIME)*((_QWORD *)v12 + 3);
      *(_QWORD *)&v18 = a1 + 32;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
      Stop = (const struct TSTime *)Scheduling::JobSchedule::GetStop(a2, &v19);
      SortedRunList::AddSorted((SortedRunList *)(a1 + 72), v12, a3, Stop);
      if ( CompareFileTime(&FileTime1, (const FILETIME *)(a1 + 168)) < 0 )
      {
        *(FILETIME *)(a1 + 168) = FileTime1;
        v13 = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
      v12 = (struct RunListItem *)*((_QWORD *)v12 + 1);
    }
    RunTimes = (int)a5;
    if ( v13 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( JobStore::GetTracingLevel(JobStore::m_pCommonStore) > 9 )
          TraceTime("Scheduler::EvaluateScheduledJob: nextRun=", (struct _FILETIME *)(a1 + 168), a3);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v15 = JobMoniker::GetPath(a3);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids, v15);
        }
        if ( !SetEvent(*(HANDLE *)(a1 + 24)) )
        {
          LastError = GetLastError();
          RunTimes = LastError;
          if ( LastError > 0 )
            RunTimes = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  RunList::~RunList((RunList *)&v20);
  return (unsigned int)RunTimes;
}

```

## disassembly

```asm
0x1800514b0  mov     [rsp-8+arg_0], rbx
0x1800514b5  mov     [rsp-8+arg_8], rdx
0x1800514ba  push    rbp
0x1800514bb  push    rsi
0x1800514bc  push    rdi
0x1800514bd  push    r12
0x1800514bf  push    r13
0x1800514c1  push    r14
0x1800514c3  push    r15
0x1800514c5  lea     rbp, [rsp-1Fh]
0x1800514ca  sub     rsp, 90h
0x1800514d1  mov     r15, r8
0x1800514d4  mov     r10, rdx
0x1800514d7  mov     rsi, rcx
0x1800514da  lea     rax, ??_7RunListItem@@6B@; const RunListItem::`vftable'
0x1800514e1  mov     [rbp+4Fh+var_70], rax
0x1800514e5  mov     rax, cs:qword_1800A8788
0x1800514ec  mov     [rbp+4Fh+var_58], rax
0x1800514f0  xor     r12d, r12d
0x1800514f3  mov     [rbp+4Fh+var_50], r12
0x1800514f7  mov     [rbp+4Fh+var_48], r12d
0x1800514fb  or      ecx, 0FFFFFFFFh
0x1800514fe  mov     [rbp+4Fh+var_44], ecx
0x180051501  mov     [rbp+4Fh+var_40], r12d
0x180051505  lea     rax, [rbp+4Fh+var_70]
0x180051509  mov     [rbp+4Fh+var_68], rax
0x18005150d  lea     rax, [rbp+4Fh+var_70]
0x180051511  mov     [rbp+4Fh+var_60], rax
0x180051515  mov     rax, [rbp+4Fh+arg_20]
0x180051519  movaps  xmm0, xmmword ptr [rax]
0x18005151c  movdqa  [rbp+4Fh+var_90], xmm0
0x180051521  movaps  xmm1, xmmword ptr [r9]
0x180051525  movdqa  [rbp+4Fh+var_80], xmm1
0x18005152a  mov     [rsp+0C0h+var_A0], ecx
0x18005152e  lea     r9, [rbp+4Fh+var_70]
0x180051532  lea     r8, [rbp+4Fh+var_90]
0x180051536  lea     rdx, [rbp+4Fh+var_80]
0x18005153a  mov     rcx, r10
0x18005153d  call    ?GetRunTimes@JobSchedule@Scheduling@@QEAAJVTSTime@@0PEAVRunList@@K@Z; Scheduling::JobSchedule::GetRunTimes(TSTime,TSTime,RunList *,ulong)
0x180051542  mov     edi, eax
0x180051544  mov     dword ptr [rbp+4Fh+arg_20], eax
0x180051547  lea     r13, WPP_GLOBAL_Control
0x18005154e  mov     rax, cs:WPP_GLOBAL_Control
0x180051555  cmp     rax, r13
0x180051558  jz      short loc_18005159C
0x18005155a  test    dword ptr [rax+1Ch], 2000h
0x180051561  jz      short loc_18005159C
0x180051563  mov     ecx, edi
0x180051565  sar     ecx, 1Fh
0x180051568  and     ecx, 0FFFFFFFEh
0x18005156b  add     ecx, 4
0x18005156e  movzx   eax, byte ptr [rax+19h]
0x180051572  cmp     eax, ecx
0x180051574  jb      short loc_18005159C
0x180051576  mov     ebx, [rbp+4Fh+var_48]
0x180051579  mov     rcx, r15; this
0x18005157c  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180051581  mov     [rsp+0C0h+var_98], ebx
0x180051585  mov     [rsp+0C0h+var_A0], edi
0x180051589  mov     r9, rax
0x18005158c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051593  mov     rcx, [rcx+10h]
0x180051597  call    WPP_SF_SDd
0x18005159c  test    edi, edi
0x18005159e  js      loc_1800516FA
0x1800515a4  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], r12
0x1800515a8  mov     rbx, [rbp+4Fh+var_68]
0x1800515ac  mov     r14b, r12b
0x1800515af  mov     rdi, [rbp+4Fh+arg_8]
0x1800515b3  cmp     [rbx+18h], r12d
0x1800515b7  jnz     short loc_1800515C3
0x1800515b9  cmp     [rbx+1Ch], r12d
0x1800515bd  jz      loc_180051645
0x1800515c3  mov     rax, [rbx+18h]
0x1800515c7  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], rax
0x1800515cb  lea     r12, [rsi+20h]
0x1800515cf  mov     qword ptr [rbp+4Fh+var_90], r12
0x1800515d3  mov     rcx, r12; lpCriticalSection
0x1800515d6  call    cs:__imp_EnterCriticalSection
0x1800515dd  nop     dword ptr [rax+rax+00h]
0x1800515e2  nop
0x1800515e3  lea     rdx, [rbp+4Fh+var_80]
0x1800515e7  mov     rcx, rdi
0x1800515ea  call    ?GetStop@JobSchedule@Scheduling@@QEBA?AVTSTime@@XZ; Scheduling::JobSchedule::GetStop(void)
0x1800515ef  mov     r9, rax; struct TSTime *
0x1800515f2  lea     rcx, [rsi+48h]; this
0x1800515f6  mov     r8, r15; struct JobMoniker *
0x1800515f9  mov     rdx, rbx; struct RunListItem *
0x1800515fc  call    ?AddSorted@SortedRunList@@QEAAJPEBVRunListItem@@AEBVJobMoniker@@AEBVTSTime@@@Z; SortedRunList::AddSorted(RunListItem const *,JobMoniker const &,TSTime const &)
0x180051601  lea     r13, [rsi+0A8h]
0x180051608  mov     rdx, r13; lpFileTime2
0x18005160b  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x18005160f  call    cs:__imp_CompareFileTime
0x180051616  nop     dword ptr [rax+rax+00h]
0x18005161b  test    eax, eax
0x18005161d  jns     short loc_18005162A
0x18005161f  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x180051623  mov     [r13+0], rax
0x180051627  mov     r14b, 1
0x18005162a  mov     rcx, r12; lpCriticalSection
0x18005162d  call    cs:__imp_LeaveCriticalSection
0x180051634  nop     dword ptr [rax+rax+00h]
0x180051639  mov     rbx, [rbx+8]
0x18005163d  xor     r12d, r12d
0x180051640  jmp     loc_1800515B3
0x180051645  test    r14b, r14b
0x180051648  mov     edi, dword ptr [rbp+4Fh+arg_20]
0x18005164b  jz      loc_1800516FA
0x180051651  cmp     [rsi+18h], r12
0x180051655  jz      loc_1800516FA
0x18005165b  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x180051662  call    ?GetTracingLevel@JobStore@@QEBAKXZ; JobStore::GetTracingLevel(void)
0x180051667  cmp     eax, 9
0x18005166a  jbe     short loc_180051682
0x18005166c  lea     rdx, [rsi+0A8h]; struct _FILETIME *
0x180051673  mov     r8, r15; struct JobMoniker *
0x180051676  lea     rcx, aSchedulerEvalu; "Scheduler::EvaluateScheduledJob: nextRu"...
0x18005167d  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x180051682  mov     rax, cs:WPP_GLOBAL_Control
0x180051689  lea     rcx, WPP_GLOBAL_Control
0x180051690  cmp     rax, rcx
0x180051693  jz      short loc_1800516CB
0x180051695  test    dword ptr [rax+1Ch], 2000h
0x18005169c  jz      short loc_1800516CB
0x18005169e  cmp     byte ptr [rax+19h], 4
0x1800516a2  jb      short loc_1800516CB
0x1800516a4  mov     rcx, r15; this
0x1800516a7  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x1800516ac  mov     edx, 0Dh
0x1800516b1  mov     r9, rax
0x1800516b4  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x1800516bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516c2  mov     rcx, [rcx+10h]
0x1800516c6  call    WPP_SF_S
0x1800516cb  mov     rcx, [rsi+18h]; hEvent
0x1800516cf  call    cs:__imp_SetEvent
0x1800516d6  nop     dword ptr [rax+rax+00h]
0x1800516db  test    eax, eax
0x1800516dd  jnz     short loc_1800516FA
0x1800516df  call    cs:__imp_GetLastError
0x1800516e6  nop     dword ptr [rax+rax+00h]
0x1800516eb  mov     edi, eax
0x1800516ed  test    eax, eax
0x1800516ef  jle     short loc_1800516FA
0x1800516f1  movzx   edi, ax
0x1800516f4  or      edi, 80070000h
0x1800516fa  lea     rcx, [rbp+4Fh+var_70]; this
0x1800516fe  call    ??1RunList@@QEAA@XZ; RunList::~RunList(void)
0x180051703  mov     eax, edi
0x180051705  mov     rbx, [rsp+0C0h+arg_0]
0x18005170d  add     rsp, 90h
0x180051714  pop     r15
0x180051716  pop     r14
0x180051718  pop     r13
0x18005171a  pop     r12
0x18005171c  pop     rdi
0x18005171d  pop     rsi
0x18005171e  pop     rbp
0x18005171f  retn
```
