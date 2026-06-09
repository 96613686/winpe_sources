# Scheduler::EvaluateScheduledJob(Scheduling::JobSchedule &,JobMoniker const &,TSTime,TSTime)

- ea: `0x18005013c`
- end: `0x180050387`
- name: `?EvaluateScheduledJob@Scheduler@@AEAAJAEAVJobSchedule@Scheduling@@AEBVJobMoniker@@VTSTime@@2@Z`
- size: `587`
- prototype: `int __high(struct Scheduling::JobSchedule *, const struct JobMoniker *, struct TSTime, struct TSTime)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050058`
- `0x180068e3c`
- `0x1800693fc`

## callees

- `0x18002132c`
- `0x180035570`
- `0x180040630`
- `0x18005013c`
- `0x1800503d0`
- `0x18005276c`
- `0x18006420c`
- `0x180069a40`
- `0x18006a038`
- `0x18006a218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005034c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005034c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180050291`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180050291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005025e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005025e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050342`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050342`

## string_xrefs

- `0x1800502e9`: `Scheduler::EvaluateScheduledJob: nextRun=`

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
0x18005013c  mov     [rsp-8+arg_0], rbx
0x180050141  mov     [rsp-8+arg_8], rdx
0x180050146  push    rbp
0x180050147  push    rsi
0x180050148  push    rdi
0x180050149  push    r12
0x18005014b  push    r13
0x18005014d  push    r14
0x18005014f  push    r15
0x180050151  lea     rbp, [rsp-1Fh]
0x180050156  sub     rsp, 90h
0x18005015d  mov     r15, r8
0x180050160  mov     r10, rdx
0x180050163  mov     rsi, rcx
0x180050166  lea     rax, ??_7RunListItem@@6B@; const RunListItem::`vftable'
0x18005016d  mov     [rbp+4Fh+var_70], rax
0x180050171  mov     rax, cs:qword_1800A4780
0x180050178  mov     [rbp+4Fh+var_58], rax
0x18005017c  xor     r12d, r12d
0x18005017f  mov     [rbp+4Fh+var_50], r12
0x180050183  mov     [rbp+4Fh+var_48], r12d
0x180050187  or      ecx, 0FFFFFFFFh
0x18005018a  mov     [rbp+4Fh+var_44], ecx
0x18005018d  mov     [rbp+4Fh+var_40], r12d
0x180050191  lea     rax, [rbp+4Fh+var_70]
0x180050195  mov     [rbp+4Fh+var_68], rax
0x180050199  lea     rax, [rbp+4Fh+var_70]
0x18005019d  mov     [rbp+4Fh+var_60], rax
0x1800501a1  mov     rax, [rbp+4Fh+arg_20]
0x1800501a5  movaps  xmm0, xmmword ptr [rax]
0x1800501a8  movdqa  [rbp+4Fh+var_90], xmm0
0x1800501ad  movaps  xmm1, xmmword ptr [r9]
0x1800501b1  movdqa  [rbp+4Fh+var_80], xmm1
0x1800501b6  mov     [rsp+0C0h+var_A0], ecx
0x1800501ba  lea     r9, [rbp+4Fh+var_70]
0x1800501be  lea     r8, [rbp+4Fh+var_90]
0x1800501c2  lea     rdx, [rbp+4Fh+var_80]
0x1800501c6  mov     rcx, r10
0x1800501c9  call    ?GetRunTimes@JobSchedule@Scheduling@@QEAAJVTSTime@@0PEAVRunList@@K@Z; Scheduling::JobSchedule::GetRunTimes(TSTime,TSTime,RunList *,ulong)
0x1800501ce  mov     edi, eax
0x1800501d0  mov     dword ptr [rbp+4Fh+arg_20], eax
0x1800501d3  lea     r13, WPP_GLOBAL_Control
0x1800501da  mov     rax, cs:WPP_GLOBAL_Control
0x1800501e1  cmp     rax, r13
0x1800501e4  jz      short loc_180050228
0x1800501e6  test    dword ptr [rax+1Ch], 2000h
0x1800501ed  jz      short loc_180050228
0x1800501ef  mov     ecx, edi
0x1800501f1  sar     ecx, 1Fh
0x1800501f4  and     ecx, 0FFFFFFFEh
0x1800501f7  add     ecx, 4
0x1800501fa  movzx   eax, byte ptr [rax+19h]
0x1800501fe  cmp     eax, ecx
0x180050200  jb      short loc_180050228
0x180050202  mov     ebx, [rbp+4Fh+var_48]
0x180050205  mov     rcx, r15; this
0x180050208  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18005020d  mov     [rsp+0C0h+var_98], ebx
0x180050211  mov     [rsp+0C0h+var_A0], edi
0x180050215  mov     r9, rax
0x180050218  mov     rcx, cs:WPP_GLOBAL_Control
0x18005021f  mov     rcx, [rcx+10h]
0x180050223  call    WPP_SF_SDd
0x180050228  test    edi, edi
0x18005022a  js      loc_180050361
0x180050230  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], r12
0x180050234  mov     rbx, [rbp+4Fh+var_68]
0x180050238  mov     r14b, r12b
0x18005023b  mov     rdi, [rbp+4Fh+arg_8]
0x18005023f  cmp     [rbx+18h], r12d
0x180050243  jnz     short loc_18005024B
0x180050245  cmp     [rbx+1Ch], r12d
0x180050249  jz      short loc_1800502B8
0x18005024b  mov     rax, [rbx+18h]
0x18005024f  mov     qword ptr [rbp+4Fh+FileTime1.dwLowDateTime], rax
0x180050253  lea     r12, [rsi+20h]
0x180050257  mov     qword ptr [rbp+4Fh+var_90], r12
0x18005025b  mov     rcx, r12; lpCriticalSection
0x18005025e  call    cs:__imp_EnterCriticalSection
0x180050264  nop
0x180050265  lea     rdx, [rbp+4Fh+var_80]
0x180050269  mov     rcx, rdi
0x18005026c  call    ?GetStop@JobSchedule@Scheduling@@QEBA?AVTSTime@@XZ; Scheduling::JobSchedule::GetStop(void)
0x180050271  mov     r9, rax; struct TSTime *
0x180050274  lea     rcx, [rsi+48h]; this
0x180050278  mov     r8, r15; struct JobMoniker *
0x18005027b  mov     rdx, rbx; struct RunListItem *
0x18005027e  call    ?AddSorted@SortedRunList@@QEAAJPEBVRunListItem@@AEBVJobMoniker@@AEBVTSTime@@@Z; SortedRunList::AddSorted(RunListItem const *,JobMoniker const &,TSTime const &)
0x180050283  lea     r13, [rsi+0A8h]
0x18005028a  mov     rdx, r13; lpFileTime2
0x18005028d  lea     rcx, [rbp+4Fh+FileTime1]; lpFileTime1
0x180050291  call    cs:__imp_CompareFileTime
0x180050297  test    eax, eax
0x180050299  jns     short loc_1800502A6
0x18005029b  mov     rax, qword ptr [rbp+4Fh+FileTime1.dwLowDateTime]
0x18005029f  mov     [r13+0], rax
0x1800502a3  mov     r14b, 1
0x1800502a6  mov     rcx, r12; lpCriticalSection
0x1800502a9  call    cs:__imp_LeaveCriticalSection
0x1800502af  mov     rbx, [rbx+8]
0x1800502b3  xor     r12d, r12d
0x1800502b6  jmp     short loc_18005023F
0x1800502b8  test    r14b, r14b
0x1800502bb  mov     edi, dword ptr [rbp+4Fh+arg_20]
0x1800502be  jz      loc_180050361
0x1800502c4  cmp     [rsi+18h], r12
0x1800502c8  jz      loc_180050361
0x1800502ce  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x1800502d5  call    ?GetTracingLevel@JobStore@@QEBAKXZ; JobStore::GetTracingLevel(void)
0x1800502da  cmp     eax, 9
0x1800502dd  jbe     short loc_1800502F5
0x1800502df  lea     rdx, [rsi+0A8h]; struct _FILETIME *
0x1800502e6  mov     r8, r15; struct JobMoniker *
0x1800502e9  lea     rcx, aSchedulerEvalu; "Scheduler::EvaluateScheduledJob: nextRu"...
0x1800502f0  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x1800502f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800502fc  lea     rcx, WPP_GLOBAL_Control
0x180050303  cmp     rax, rcx
0x180050306  jz      short loc_18005033E
0x180050308  test    dword ptr [rax+1Ch], 2000h
0x18005030f  jz      short loc_18005033E
0x180050311  cmp     byte ptr [rax+19h], 4
0x180050315  jb      short loc_18005033E
0x180050317  mov     rcx, r15; this
0x18005031a  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18005031f  mov     edx, 0Dh
0x180050324  mov     r9, rax
0x180050327  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18005032e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050335  mov     rcx, [rcx+10h]
0x180050339  call    WPP_SF_S
0x18005033e  mov     rcx, [rsi+18h]; hEvent
0x180050342  call    cs:__imp_SetEvent
0x180050348  test    eax, eax
0x18005034a  jnz     short loc_180050361
0x18005034c  call    cs:__imp_GetLastError
0x180050352  mov     edi, eax
0x180050354  test    eax, eax
0x180050356  jle     short loc_180050361
0x180050358  movzx   edi, ax
0x18005035b  or      edi, 80070000h
0x180050361  lea     rcx, [rbp+4Fh+var_70]; this
0x180050365  call    ??1RunList@@QEAA@XZ; RunList::~RunList(void)
0x18005036a  mov     eax, edi
0x18005036c  mov     rbx, [rsp+0C0h+arg_0]
0x180050374  add     rsp, 90h
0x18005037b  pop     r15
0x18005037d  pop     r14
0x18005037f  pop     r13
0x180050381  pop     r12
0x180050383  pop     rdi
0x180050384  pop     rsi
0x180050385  pop     rbp
0x180050386  retn
```
