# RpcServer::FlushTriggers(JobMoniker const &)

- ea: `0x18003b2c0`
- end: `0x18003b56c`
- name: `?FlushTriggers@RpcServer@@CAJAEBVJobMoniker@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(const struct JobMoniker *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180045df0`
- `0x18004d620`
- `0x18004d868`

## callees

- `0x18002132c`
- `0x18003b2c0`
- `0x18003b580`
- `0x18003b62c`
- `0x18003b770`
- `0x18003b8ac`
- `0x180043db0`
- `0x180050028`
- `0x18005276c`
- `0x18006420c`
- `0x180068e10`
- `0x180069d84`
- `0x18006a218`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4f3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b461`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b50b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b50b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b4e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b4e9`

## string_xrefs

- `0x18003b48c`: `DeleteJobSchedule, nextRun:`

## pseudocode

```c
__int64 __fastcall RpcServer::FlushTriggers(const struct _bstr_t::Data_t **a1)
{
  Scheduler *v1; // rbp
  signed int v3; // esi
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  ScheduleListItem *v5; // rdi
  const unsigned __int16 *Path; // rax
  const struct _bstr_t::Data_t *v7; // rdx
  _bstr_t::Data_t *v8; // rcx
  ScheduleListItem *v9; // r12
  unsigned int v10; // eax
  __int64 i; // rdi
  __int64 v12; // r15
  FILETIME *v13; // rdi
  const unsigned __int16 *v14; // rax
  signed int LastError; // eax
  PseudoEventTrap *v16; // rcx
  int v17; // eax
  PseudoEventTrap *v18; // rcx
  int v19; // eax
  PseudoEventTrap *v20; // rcx
  int v21; // eax
  int v22; // eax
  FILETIME FileTime1; // [rsp+88h] [rbp+10h] BYREF

  v1 = g_pScheduler;
  v3 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pScheduler + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScheduler + 32));
  v5 = (ScheduleListItem *)*((_QWORD *)v1 + 41);
  if ( v5 == (Scheduler *)((char *)v1 + 320) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      Path = JobMoniker::GetPath((JobMoniker *)a1);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids, Path);
    }
  }
  else if ( v5 )
  {
    do
    {
      if ( v5 == (Scheduler *)((char *)v1 + 320) )
        break;
      v7 = a1[2];
      v8 = (_bstr_t::Data_t *)*((_QWORD *)v5 + 5);
      v9 = (ScheduleListItem *)*((_QWORD *)v5 + 1);
      if ( v8 == v7 || v8 && v7 && !(unsigned int)_bstr_t::Data_t::Compare(v8, v7) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v10 = (unsigned int)JobMoniker::GetPath((JobMoniker *)a1);
          WPP_SF_Sq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids,
            v10,
            (char)v5);
        }
        ScheduleListItem::Delete(v5);
      }
      v5 = v9;
    }
    while ( v9 );
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 32);
  }
  for ( i = *((_QWORD *)v1 + 10); *(_DWORD *)(i + 24) || *(_DWORD *)(i + 28); i = v12 )
  {
    v12 = *(_QWORD *)(i + 8);
    if ( (unsigned __int8)_bstr_t::operator==(i + 56, a1 + 2) )
      SortedRunListItem::Delete((SortedRunListItem *)i);
  }
  v13 = (FILETIME *)*((_QWORD *)v1 + 10);
  FileTime1 = (FILETIME)-1LL;
  if ( v13[3].dwLowDateTime || v13[3].dwHighDateTime )
    FileTime1 = v13[3];
  if ( CompareFileTime(&FileTime1, (const FILETIME *)v1 + 21) > 0 )
  {
    if ( JobStore::GetTracingLevel(JobStore::m_pCommonStore) > 9 )
      TraceTime("DeleteJobSchedule, nextRun:", &FileTime1, (const struct JobMoniker *)&v13[5]);
    *((FILETIME *)v1 + 21) = FileTime1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = JobMoniker::GetPath((JobMoniker *)a1);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids, v14);
    }
    if ( !SetEvent(*((HANDLE *)v1 + 3)) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LeaveCriticalSection(v4);
  if ( v3 >= 0 )
    v3 = 0;
  v17 = PseudoEventTrap::UnregisterIdleJob(v16, (const struct JobMoniker *)a1);
  if ( v17 < 0 )
    v3 = v17;
  v19 = PseudoEventTrap::UnregisterLogonJob(v18, (const struct JobMoniker *)a1);
  if ( v19 < 0 )
    v3 = v19;
  v21 = PseudoEventTrap::UnregisterSessionChangeJob(v20, (const struct JobMoniker *)a1);
  if ( v21 < 0 )
    v3 = v21;
  v22 = (*(__int64 (__fastcall **)(EventTrapMap *, const struct _bstr_t::Data_t **))(*(_QWORD *)g_pEventTrapMap + 8LL))(
          g_pEventTrapMap,
          a1);
  if ( v22 < 0 )
    return (unsigned int)v22;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003b2c0  push    rbx
0x18003b2c2  push    rbp
0x18003b2c3  push    rsi
0x18003b2c4  push    rdi
0x18003b2c5  push    r12
0x18003b2c7  push    r13
0x18003b2c9  push    r14
0x18003b2cb  push    r15
0x18003b2cd  sub     rsp, 38h
0x18003b2d1  mov     rbp, cs:?g_pScheduler@@3PEAVScheduler@@EA; Scheduler * g_pScheduler
0x18003b2d8  mov     r14, rcx
0x18003b2db  xor     r13d, r13d
0x18003b2de  mov     esi, r13d
0x18003b2e1  lea     rbx, [rbp+20h]
0x18003b2e5  mov     rcx, rbx; lpCriticalSection
0x18003b2e8  call    cs:__imp_EnterCriticalSection
0x18003b2ee  lea     r15, [rbp+140h]
0x18003b2f5  mov     rdi, [r15+8]
0x18003b2f9  lea     r12, WPP_GLOBAL_Control
0x18003b300  cmp     rdi, r15
0x18003b303  jnz     short loc_18003B357
0x18003b305  mov     rax, cs:WPP_GLOBAL_Control
0x18003b30c  cmp     rax, r12
0x18003b30f  jz      loc_18003B3F2
0x18003b315  test    dword ptr [rax+1Ch], 2000h
0x18003b31c  jz      loc_18003B3F2
0x18003b322  cmp     byte ptr [rax+19h], 4
0x18003b326  jb      loc_18003B3F2
0x18003b32c  mov     rcx, r14; this
0x18003b32f  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003b334  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b33b  lea     edx, [r13+13h]
0x18003b33f  mov     r9, rax
0x18003b342  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003b349  mov     rcx, [rcx+10h]
0x18003b34d  call    WPP_SF_S
0x18003b352  jmp     loc_18003B3F2
0x18003b357  test    rdi, rdi
0x18003b35a  jz      loc_18003B3F2
0x18003b360  lea     rbx, WPP_GLOBAL_Control
0x18003b367  cmp     rdi, r15
0x18003b36a  jz      short loc_18003B3E7
0x18003b36c  mov     rdx, [r14+10h]; struct _bstr_t::Data_t *
0x18003b370  mov     rcx, [rdi+28h]; this
0x18003b374  mov     r12, [rdi+8]
0x18003b378  cmp     rcx, rdx
0x18003b37b  jz      short loc_18003B390
0x18003b37d  test    rcx, rcx
0x18003b380  jz      short loc_18003B3DF
0x18003b382  test    rdx, rdx
0x18003b385  jz      short loc_18003B3DF
0x18003b387  call    ?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z; _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)
0x18003b38c  test    eax, eax
0x18003b38e  jnz     short loc_18003B3DF
0x18003b390  mov     rax, cs:WPP_GLOBAL_Control
0x18003b397  cmp     rax, rbx
0x18003b39a  jz      short loc_18003B3D7
0x18003b39c  test    dword ptr [rax+1Ch], 2000h
0x18003b3a3  jz      short loc_18003B3D7
0x18003b3a5  cmp     byte ptr [rax+19h], 5
0x18003b3a9  jb      short loc_18003B3D7
0x18003b3ab  mov     rcx, r14; this
0x18003b3ae  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003b3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3ba  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003b3c1  mov     edx, 14h
0x18003b3c6  mov     [rsp+78h+var_58], rdi
0x18003b3cb  mov     r9, rax
0x18003b3ce  mov     rcx, [rcx+10h]
0x18003b3d2  call    WPP_SF_Sq
0x18003b3d7  mov     rcx, rdi; this
0x18003b3da  call    ?Delete@ScheduleListItem@@QEAAXXZ; ScheduleListItem::Delete(void)
0x18003b3df  mov     rdi, r12
0x18003b3e2  test    r12, r12
0x18003b3e5  jnz     short loc_18003B367
0x18003b3e7  lea     rbx, [rbp+20h]
0x18003b3eb  lea     r12, WPP_GLOBAL_Control
0x18003b3f2  mov     rdi, [rbp+50h]
0x18003b3f6  cmp     [rdi+18h], r13d
0x18003b3fa  jnz     short loc_18003B402
0x18003b3fc  cmp     [rdi+1Ch], r13d
0x18003b400  jz      short loc_18003B424
0x18003b402  mov     r15, [rdi+8]
0x18003b406  lea     rdx, [r14+10h]
0x18003b40a  lea     rcx, [rdi+38h]
0x18003b40e  call    ??8_bstr_t@@QEBA_NAEBV0@@Z; _bstr_t::operator==(_bstr_t const &)
0x18003b413  test    al, al
0x18003b415  jz      short loc_18003B41F
0x18003b417  mov     rcx, rdi; this
0x18003b41a  call    ?Delete@SortedRunListItem@@QEAAXXZ; SortedRunListItem::Delete(void)
0x18003b41f  mov     rdi, r15
0x18003b422  jmp     short loc_18003B3F6
0x18003b424  mov     rdi, [rbp+50h]
0x18003b428  mov     rax, qword ptr cs:FileTime2.dwLowDateTime
0x18003b42f  mov     qword ptr [rsp+78h+FileTime1.dwLowDateTime], rax
0x18003b437  cmp     [rdi+18h], r13d
0x18003b43b  jnz     short loc_18003B443
0x18003b43d  cmp     [rdi+1Ch], r13d
0x18003b441  jz      short loc_18003B44F
0x18003b443  mov     rax, [rdi+18h]
0x18003b447  mov     qword ptr [rsp+78h+FileTime1.dwLowDateTime], rax
0x18003b44f  lea     r15, [rbp+0A8h]
0x18003b456  mov     rdx, r15; lpFileTime2
0x18003b459  lea     rcx, [rsp+78h+FileTime1]; lpFileTime1
0x18003b461  call    cs:__imp_CompareFileTime
0x18003b467  test    eax, eax
0x18003b469  jle     loc_18003B508
0x18003b46f  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x18003b476  call    ?GetTracingLevel@JobStore@@QEBAKXZ; JobStore::GetTracingLevel(void)
0x18003b47b  cmp     eax, 9
0x18003b47e  jbe     short loc_18003B498
0x18003b480  lea     r8, [rdi+28h]; struct JobMoniker *
0x18003b484  lea     rdx, [rsp+78h+FileTime1]; struct _FILETIME *
0x18003b48c  lea     rcx, aDeletejobsched; "DeleteJobSchedule, nextRun:"
0x18003b493  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x18003b498  mov     rax, qword ptr [rsp+78h+FileTime1.dwLowDateTime]
0x18003b4a0  mov     [r15], rax
0x18003b4a3  mov     rax, cs:WPP_GLOBAL_Control
0x18003b4aa  cmp     rax, r12
0x18003b4ad  jz      short loc_18003B4E5
0x18003b4af  test    dword ptr [rax+1Ch], 2000h
0x18003b4b6  jz      short loc_18003B4E5
0x18003b4b8  cmp     byte ptr [rax+19h], 4
0x18003b4bc  jb      short loc_18003B4E5
0x18003b4be  mov     rcx, r14; this
0x18003b4c1  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003b4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4cd  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003b4d4  mov     edx, 15h
0x18003b4d9  mov     r9, rax
0x18003b4dc  mov     rcx, [rcx+10h]
0x18003b4e0  call    WPP_SF_S
0x18003b4e5  mov     rcx, [rbp+18h]; hEvent
0x18003b4e9  call    cs:__imp_SetEvent
0x18003b4ef  test    eax, eax
0x18003b4f1  jnz     short loc_18003B508
0x18003b4f3  call    cs:__imp_GetLastError
0x18003b4f9  mov     esi, eax
0x18003b4fb  test    eax, eax
0x18003b4fd  jle     short loc_18003B508
0x18003b4ff  movzx   esi, ax
0x18003b502  or      esi, 80070000h
0x18003b508  mov     rcx, rbx; lpCriticalSection
0x18003b50b  call    cs:__imp_LeaveCriticalSection
0x18003b511  test    esi, esi
0x18003b513  mov     rdx, r14; struct JobMoniker *
0x18003b516  cmovns  esi, r13d
0x18003b51a  call    ?UnregisterIdleJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterIdleJob(JobMoniker const &)
0x18003b51f  test    eax, eax
0x18003b521  mov     rdx, r14; struct JobMoniker *
0x18003b524  cmovs   esi, eax
0x18003b527  call    ?UnregisterLogonJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterLogonJob(JobMoniker const &)
0x18003b52c  test    eax, eax
0x18003b52e  mov     rdx, r14; struct JobMoniker *
0x18003b531  cmovs   esi, eax
0x18003b534  call    ?UnregisterSessionChangeJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterSessionChangeJob(JobMoniker const &)
0x18003b539  mov     rcx, cs:?g_pEventTrapMap@@3PEAVEventTrapMap@@EA; EventTrapMap * g_pEventTrapMap
0x18003b540  test    eax, eax
0x18003b542  cmovs   esi, eax
0x18003b545  mov     rdx, [rcx]
0x18003b548  mov     rax, [rdx+8]
0x18003b54c  mov     rdx, r14
0x18003b54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b554  test    eax, eax
0x18003b556  cmovs   esi, eax
0x18003b559  mov     eax, esi
0x18003b55b  add     rsp, 38h
0x18003b55f  pop     r15
0x18003b561  pop     r14
0x18003b563  pop     r13
0x18003b565  pop     r12
0x18003b567  pop     rdi
0x18003b568  pop     rsi
0x18003b569  pop     rbp
0x18003b56a  pop     rbx
0x18003b56b  retn
```
