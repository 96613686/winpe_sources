# RpcServer::FlushTriggers(JobMoniker const &)

- ea: `0x18003c8f8`
- end: `0x18003cbc3`
- name: `?FlushTriggers@RpcServer@@CAJAEBVJobMoniker@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(const struct JobMoniker *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047ee0`
- `0x18004f9b8`
- `0x18004fc18`

## callees

- `0x18002db74`
- `0x18003c8f8`
- `0x18003cbd0`
- `0x18003cc8c`
- `0x18003cde0`
- `0x18003cf28`
- `0x180045e54`
- `0x180051384`
- `0x180054eb8`
- `0x180067290`
- `0x18006c1e4`
- `0x18006d1c4`
- `0x18006d680`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb3d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003ca9f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003ca9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c920`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003cb2d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003cb2d`

## string_xrefs

- `0x18003cad0`: `DeleteJobSchedule, nextRun:`

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
0x18003c8f8  push    rbx
0x18003c8fa  push    rbp
0x18003c8fb  push    rsi
0x18003c8fc  push    rdi
0x18003c8fd  push    r12
0x18003c8ff  push    r13
0x18003c901  push    r14
0x18003c903  push    r15
0x18003c905  sub     rsp, 38h
0x18003c909  mov     rbp, cs:?g_pScheduler@@3PEAVScheduler@@EA; Scheduler * g_pScheduler
0x18003c910  mov     r14, rcx
0x18003c913  xor     r13d, r13d
0x18003c916  mov     esi, r13d
0x18003c919  lea     rbx, [rbp+20h]
0x18003c91d  mov     rcx, rbx; lpCriticalSection
0x18003c920  call    cs:__imp_EnterCriticalSection
0x18003c927  nop     dword ptr [rax+rax+00h]
0x18003c92c  lea     r15, [rbp+140h]
0x18003c933  mov     rdi, [r15+8]
0x18003c937  lea     r12, WPP_GLOBAL_Control
0x18003c93e  cmp     rdi, r15
0x18003c941  jnz     short loc_18003C995
0x18003c943  mov     rax, cs:WPP_GLOBAL_Control
0x18003c94a  cmp     rax, r12
0x18003c94d  jz      loc_18003CA30
0x18003c953  test    dword ptr [rax+1Ch], 2000h
0x18003c95a  jz      loc_18003CA30
0x18003c960  cmp     byte ptr [rax+19h], 4
0x18003c964  jb      loc_18003CA30
0x18003c96a  mov     rcx, r14; this
0x18003c96d  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003c972  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c979  lea     edx, [r13+13h]
0x18003c97d  mov     r9, rax
0x18003c980  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003c987  mov     rcx, [rcx+10h]
0x18003c98b  call    WPP_SF_S
0x18003c990  jmp     loc_18003CA30
0x18003c995  test    rdi, rdi
0x18003c998  jz      loc_18003CA30
0x18003c99e  lea     rbx, WPP_GLOBAL_Control
0x18003c9a5  cmp     rdi, r15
0x18003c9a8  jz      short loc_18003CA25
0x18003c9aa  mov     rdx, [r14+10h]; struct _bstr_t::Data_t *
0x18003c9ae  mov     rcx, [rdi+28h]; this
0x18003c9b2  mov     r12, [rdi+8]
0x18003c9b6  cmp     rcx, rdx
0x18003c9b9  jz      short loc_18003C9CE
0x18003c9bb  test    rcx, rcx
0x18003c9be  jz      short loc_18003CA1D
0x18003c9c0  test    rdx, rdx
0x18003c9c3  jz      short loc_18003CA1D
0x18003c9c5  call    ?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z; _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)
0x18003c9ca  test    eax, eax
0x18003c9cc  jnz     short loc_18003CA1D
0x18003c9ce  mov     rax, cs:WPP_GLOBAL_Control
0x18003c9d5  cmp     rax, rbx
0x18003c9d8  jz      short loc_18003CA15
0x18003c9da  test    dword ptr [rax+1Ch], 2000h
0x18003c9e1  jz      short loc_18003CA15
0x18003c9e3  cmp     byte ptr [rax+19h], 5
0x18003c9e7  jb      short loc_18003CA15
0x18003c9e9  mov     rcx, r14; this
0x18003c9ec  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003c9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9f8  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003c9ff  mov     edx, 14h
0x18003ca04  mov     [rsp+78h+var_58], rdi
0x18003ca09  mov     r9, rax
0x18003ca0c  mov     rcx, [rcx+10h]
0x18003ca10  call    WPP_SF_Sq
0x18003ca15  mov     rcx, rdi; this
0x18003ca18  call    ?Delete@ScheduleListItem@@QEAAXXZ; ScheduleListItem::Delete(void)
0x18003ca1d  mov     rdi, r12
0x18003ca20  test    r12, r12
0x18003ca23  jnz     short loc_18003C9A5
0x18003ca25  lea     rbx, [rbp+20h]
0x18003ca29  lea     r12, WPP_GLOBAL_Control
0x18003ca30  mov     rdi, [rbp+50h]
0x18003ca34  cmp     [rdi+18h], r13d
0x18003ca38  jnz     short loc_18003CA40
0x18003ca3a  cmp     [rdi+1Ch], r13d
0x18003ca3e  jz      short loc_18003CA62
0x18003ca40  mov     r15, [rdi+8]
0x18003ca44  lea     rdx, [r14+10h]
0x18003ca48  lea     rcx, [rdi+38h]
0x18003ca4c  call    ??8_bstr_t@@QEBA_NAEBV0@@Z; _bstr_t::operator==(_bstr_t const &)
0x18003ca51  test    al, al
0x18003ca53  jz      short loc_18003CA5D
0x18003ca55  mov     rcx, rdi; this
0x18003ca58  call    ?Delete@SortedRunListItem@@QEAAXXZ; SortedRunListItem::Delete(void)
0x18003ca5d  mov     rdi, r15
0x18003ca60  jmp     short loc_18003CA34
0x18003ca62  mov     rdi, [rbp+50h]
0x18003ca66  mov     rax, qword ptr cs:FileTime2.dwLowDateTime
0x18003ca6d  mov     qword ptr [rsp+78h+FileTime1.dwLowDateTime], rax
0x18003ca75  cmp     [rdi+18h], r13d
0x18003ca79  jnz     short loc_18003CA81
0x18003ca7b  cmp     [rdi+1Ch], r13d
0x18003ca7f  jz      short loc_18003CA8D
0x18003ca81  mov     rax, [rdi+18h]
0x18003ca85  mov     qword ptr [rsp+78h+FileTime1.dwLowDateTime], rax
0x18003ca8d  lea     r15, [rbp+0A8h]
0x18003ca94  mov     rdx, r15; lpFileTime2
0x18003ca97  lea     rcx, [rsp+78h+FileTime1]; lpFileTime1
0x18003ca9f  call    cs:__imp_CompareFileTime
0x18003caa6  nop     dword ptr [rax+rax+00h]
0x18003caab  test    eax, eax
0x18003caad  jle     loc_18003CB58
0x18003cab3  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x18003caba  call    ?GetTracingLevel@JobStore@@QEBAKXZ; JobStore::GetTracingLevel(void)
0x18003cabf  cmp     eax, 9
0x18003cac2  jbe     short loc_18003CADC
0x18003cac4  lea     r8, [rdi+28h]; struct JobMoniker *
0x18003cac8  lea     rdx, [rsp+78h+FileTime1]; struct _FILETIME *
0x18003cad0  lea     rcx, aDeletejobsched; "DeleteJobSchedule, nextRun:"
0x18003cad7  call    ?TraceTime@@YAXPEBDAEAU_FILETIME@@AEBVJobMoniker@@@Z; TraceTime(char const *,_FILETIME &,JobMoniker const &)
0x18003cadc  mov     rax, qword ptr [rsp+78h+FileTime1.dwLowDateTime]
0x18003cae4  mov     [r15], rax
0x18003cae7  mov     rax, cs:WPP_GLOBAL_Control
0x18003caee  cmp     rax, r12
0x18003caf1  jz      short loc_18003CB29
0x18003caf3  test    dword ptr [rax+1Ch], 2000h
0x18003cafa  jz      short loc_18003CB29
0x18003cafc  cmp     byte ptr [rax+19h], 4
0x18003cb00  jb      short loc_18003CB29
0x18003cb02  mov     rcx, r14; this
0x18003cb05  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18003cb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb11  lea     r8, WPP_5435fee58aaf3c352ed5cdc6abf88a31_Traceguids
0x18003cb18  mov     edx, 15h
0x18003cb1d  mov     r9, rax
0x18003cb20  mov     rcx, [rcx+10h]
0x18003cb24  call    WPP_SF_S
0x18003cb29  mov     rcx, [rbp+18h]; hEvent
0x18003cb2d  call    cs:__imp_SetEvent
0x18003cb34  nop     dword ptr [rax+rax+00h]
0x18003cb39  test    eax, eax
0x18003cb3b  jnz     short loc_18003CB58
0x18003cb3d  call    cs:__imp_GetLastError
0x18003cb44  nop     dword ptr [rax+rax+00h]
0x18003cb49  mov     esi, eax
0x18003cb4b  test    eax, eax
0x18003cb4d  jle     short loc_18003CB58
0x18003cb4f  movzx   esi, ax
0x18003cb52  or      esi, 80070000h
0x18003cb58  mov     rcx, rbx; lpCriticalSection
0x18003cb5b  call    cs:__imp_LeaveCriticalSection
0x18003cb62  nop     dword ptr [rax+rax+00h]
0x18003cb67  test    esi, esi
0x18003cb69  mov     rdx, r14; struct JobMoniker *
0x18003cb6c  cmovns  esi, r13d
0x18003cb70  call    ?UnregisterIdleJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterIdleJob(JobMoniker const &)
0x18003cb75  test    eax, eax
0x18003cb77  mov     rdx, r14; struct JobMoniker *
0x18003cb7a  cmovs   esi, eax
0x18003cb7d  call    ?UnregisterLogonJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterLogonJob(JobMoniker const &)
0x18003cb82  test    eax, eax
0x18003cb84  mov     rdx, r14; struct JobMoniker *
0x18003cb87  cmovs   esi, eax
0x18003cb8a  call    ?UnregisterSessionChangeJob@PseudoEventTrap@@QEAAJAEBVJobMoniker@@@Z; PseudoEventTrap::UnregisterSessionChangeJob(JobMoniker const &)
0x18003cb8f  mov     rcx, cs:?g_pEventTrapMap@@3PEAVEventTrapMap@@EA; EventTrapMap * g_pEventTrapMap
0x18003cb96  test    eax, eax
0x18003cb98  cmovs   esi, eax
0x18003cb9b  mov     rdx, [rcx]
0x18003cb9e  mov     rax, [rdx+8]
0x18003cba2  mov     rdx, r14
0x18003cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbaa  test    eax, eax
0x18003cbac  cmovs   esi, eax
0x18003cbaf  mov     eax, esi
0x18003cbb1  add     rsp, 38h
0x18003cbb5  pop     r15
0x18003cbb7  pop     r14
0x18003cbb9  pop     r13
0x18003cbbb  pop     r12
0x18003cbbd  pop     rdi
0x18003cbbe  pop     rsi
0x18003cbbf  pop     rbp
0x18003cbc0  pop     rbx
0x18003cbc1  retn
```
