# UbpmTerminateActionsForConsumer

- ea: `0x180003050`
- end: `0x18000367b`
- name: `UbpmTerminateActionsForConsumer`
- size: `1579`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180002dc0`
- `0x180003684`
- `0x180016eb0`
- `0x180035c50`

## callees

- `0x180002fcc`
- `0x180003050`
- `0x180004240`
- `0x1800049b4`
- `0x180004e10`
- `0x180005ed0`
- `0x180007460`
- `0x180009750`
- `0x18000a03c`
- `0x180015e10`
- `0x180019d90`
- `0x18001e9f4`
- `0x180024df0`
- `0x18002eb98`
- `0x180036d30`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800030e3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800031c3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800035c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800030e3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800031c3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800035c2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000311d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800031fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003602`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000311d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800031fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035c8`
- `RPCRT4!UuidEqual` at `0x1800033d4`
- `RPCRT4!UuidEqual` at `0x1800033ff`
- `RPCRT4!UuidEqual` at `0x180003520`
- `RPCRT4!UuidEqual` at `0x180003631`
- `RPCRT4!UuidEqual` at `0x1800033d4`
- `RPCRT4!UuidEqual` at `0x1800033ff`
- `RPCRT4!UuidEqual` at `0x180003520`
- `RPCRT4!UuidEqual` at `0x180003631`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000327c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000327c`

## string_xrefs

- `0x180003255`: `NT TASK`
- `0x180003597`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180003234`: `Removed`
- `0x18000322d`: `Not removed`

## pseudocode

```c
__int64 __fastcall UbpmTerminateActionsForConsumer(
        __int64 a1,
        UUID *a2,
        int a3,
        __int64 a4,
        unsigned __int8 a5,
        __int64 a6)
{
  __int64 v6; // rax
  unsigned int v10; // ebx
  const WCHAR *v11; // rdi
  __int64 v12; // rax
  char v13; // bp
  __int64 *v14; // r15
  char v15; // r15
  DWORD v16; // eax
  UUID *v17; // r14
  _QWORD *v18; // rcx
  __int64 *v19; // r15
  int v20; // edi
  UUID **v22; // rax
  char v23; // r12
  UUID *v24; // r15
  DWORD v25; // eax
  struct _GUID *v26; // r14
  bool v27; // zf
  __int64 v28; // rcx
  const wchar_t *v29; // r9
  __int64 v30; // r8
  __int64 *v31; // rcx
  __int64 **v32; // rax
  struct _GUID *v33; // rbx
  __int64 *v34; // r12
  __int64 *v35; // rax
  __int64 **v36; // rcx
  UUID *v37; // rax
  UUID **v38; // rcx
  struct _GUID *v39; // rax
  struct _GUID **v40; // rcx
  struct _GUID *v41; // rax
  const struct _EVENT_DESCRIPTOR *v42; // rdx
  const unsigned __int16 *v43; // rbx
  const unsigned __int16 *v44; // rax
  int v45; // eax
  __int64 v46; // r8
  DWORD CurrentThreadId; // eax
  __int64 v48; // r8
  UUID *v49; // r12
  void *cchCount2; // [rsp+28h] [rbp-70h]
  const struct _GUID *v51; // [rsp+30h] [rbp-68h]
  RPC_STATUS Status[2]; // [rsp+40h] [rbp-58h] BYREF
  struct _GUID *v53; // [rsp+48h] [rbp-50h] BYREF
  __int64 *v54; // [rsp+50h] [rbp-48h]
  RPC_STATUS v55; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v56; // [rsp+B8h] [rbp+20h]

  v56 = a4;
  v6 = *(_QWORD *)(a1 + 24);
  v55 = 0;
  v10 = 1168;
  v11 = *(const WCHAR **)(v6 + 8);
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( (unsigned int)v12 > 8 && CompareStringW(0x7Fu, 1u, v11, 7, L"NT TASK", 7) == 2 )
      v11 += 7;
  }
  v13 = 0;
  v14 = *(__int64 **)(a1 + 224);
  if ( v14 != (__int64 *)(a1 + 224) )
  {
    while ( 1 )
    {
      v54 = (__int64 *)*v14;
      v53 = (struct _GUID *)((char *)v14 + 52);
      if ( !a2 )
        break;
      if ( UuidEqual(a2, (UUID *)((char *)v14 + 52), &v55) )
        goto LABEL_31;
LABEL_38:
      v14 = v54;
      if ( v54 == (__int64 *)(a1 + 224) )
        goto LABEL_6;
    }
    v53 = (struct _GUID *)((char *)v14 + 52);
LABEL_31:
    if ( !v56 || v56 == v14[10] )
    {
      if ( a6 )
      {
        *(_QWORD *)Status = 0;
        UbpmUtilsGetAccountNamesFromSid(a6, 1, 0, 0, (__int64)Status);
        v43 = *(const unsigned __int16 **)Status;
        v44 = L"(NONE)";
        if ( *(_QWORD *)Status )
          v44 = *(const unsigned __int16 **)Status;
        v45 = EventManager::EvtReport(g_hTaskEventManager, v42, v11, v53, v44, cchCount2, v51);
        v46 = (unsigned __int16)v45;
        if ( v45 >= 0 )
          v46 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", STOPPING_ON_REQUEST, v46);
        UBPM_MIDL_user_free(v43);
      }
      v30 = v14[3];
      if ( *(_DWORD *)(v30 + 16) == 1 )
      {
        v33 = (struct _GUID *)v14[4];
        UbpmpHostTerminateTask(v33, v14 + 5, v30, a5);
        v53 = v33;
        if ( v33 )
          UbpmpDecrementRefAndDelete(&v53, 1);
      }
      ReportTaskEvent((void *)a1, &JOB_TERMINATION, v11, (const struct _GUID *)((char *)v14 + 52));
      *(_OWORD *)(a1 + 272) = 0;
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) )
      {
        RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
        CurrentThreadId = GetCurrentThreadId();
        v48 = 6;
        dword_18004CEE8 = CurrentThreadId;
        if ( !a5 )
          v48 = 1;
        UbpmpMaintenanceTaskStoppedCallout(a1, v14, v48);
        dword_18004CEE8 = 0;
        RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
      }
      UbpmQueueConsumerClose((void *)v14[13]);
      v31 = (__int64 *)*v14;
      if ( *(__int64 **)(*v14 + 8) != v14 || (v32 = (__int64 **)v14[1], *v32 != v14) )
LABEL_50:
        __fastfail(3u);
      *v32 = v31;
      v13 = 1;
      v31[1] = (__int64)v32;
      v14[1] = (__int64)v14;
      *v14 = (__int64)v14;
      UBPM_MIDL_user_free(v14);
      v10 = 0;
    }
    goto LABEL_38;
  }
LABEL_6:
  if ( a3 )
    UbpmStatsOperation(a1, 2, 0);
  if ( a2 )
  {
    Status[0] = 0;
    v15 = 0;
    RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
    v16 = GetCurrentThreadId();
    v17 = (UUID *)g_leQueuedSerialActionsListHead;
    dword_18004CEA0 = v16;
    while ( v17 != (UUID *)&g_leQueuedSerialActionsListHead )
    {
      v49 = *(UUID **)&v17->Data1;
      if ( UuidEqual(a2, v17 + 1, Status) )
      {
        v37 = *(UUID **)&v17->Data1;
        if ( *(UUID **)(*(_QWORD *)&v17->Data1 + 8LL) != v17 )
          goto LABEL_50;
        v38 = *(UUID ***)v17->Data4;
        if ( *v38 != v17 )
          goto LABEL_50;
        *v38 = v37;
        *(_QWORD *)v37->Data4 = v38;
        *(_QWORD *)v17->Data4 = v17;
        *(_QWORD *)&v17->Data1 = v17;
        UBPM_MIDL_user_free(v17);
        v15 = 1;
      }
      v17 = v49;
    }
    dword_18004CEA0 = 0;
    RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_13;
    v27 = v15 == 0;
LABEL_24:
    v28 = v18[2];
    v29 = L"Removed";
    if ( v27 )
      v29 = L"Not removed";
    WPP_SF_Sd(v28, 95, (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, (_DWORD)v29, 0);
    goto LABEL_13;
  }
  if ( v56 )
  {
    UbpmpRemoveQueuedSerialActions(0, 0, 0, 0);
    goto LABEL_13;
  }
  v22 = *(UUID ***)(a1 + 24);
  Status[0] = 0;
  v23 = 0;
  v24 = *v22;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  v25 = GetCurrentThreadId();
  v26 = (struct _GUID *)g_leQueuedSerialActionsListHead;
  dword_18004CEA0 = v25;
  if ( g_leQueuedSerialActionsListHead != (_UNKNOWN *)&g_leQueuedSerialActionsListHead )
  {
    do
    {
      v41 = *(struct _GUID **)&v26->Data1;
      v53 = *(struct _GUID **)&v26->Data1;
      if ( v24 )
      {
        if ( UuidEqual(v24, v26 + 2, Status) )
        {
          v39 = *(struct _GUID **)&v26->Data1;
          if ( *(struct _GUID **)(*(_QWORD *)&v26->Data1 + 8LL) != v26 )
            goto LABEL_50;
          v40 = *(struct _GUID ***)v26->Data4;
          if ( *v40 != v26 )
            goto LABEL_50;
          *v40 = v39;
          *(_QWORD *)v39->Data4 = v40;
          *(_QWORD *)v26->Data4 = v26;
          *(_QWORD *)&v26->Data1 = v26;
          UBPM_MIDL_user_free(v26);
          v23 = 1;
        }
        v41 = v53;
      }
      v26 = v41;
    }
    while ( v41 != (struct _GUID *)&g_leQueuedSerialActionsListHead );
  }
  dword_18004CEA0 = 0;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v27 = v23 == 0;
    goto LABEL_24;
  }
LABEL_13:
  *(_BYTE *)(a1 + 304) = 0;
  v19 = *(__int64 **)(a1 + 256);
  Status[0] = 0;
  v20 = 1168;
  if ( v19 != (__int64 *)(a1 + 256) )
  {
    do
    {
      v34 = (__int64 *)*v19;
      if ( (!a2 || UuidEqual(a2, (UUID *)((char *)v19 + 20), Status)) && (!v56 || v56 == v19[10]) )
      {
        UbpmQueueConsumerClose((void *)v19[17]);
        v35 = (__int64 *)*v19;
        if ( *(__int64 **)(*v19 + 8) != v19 )
          goto LABEL_50;
        v36 = (__int64 **)v19[1];
        if ( *v36 != v19 )
          goto LABEL_50;
        *v36 = v35;
        v35[1] = (__int64)v36;
        v19[1] = (__int64)v19;
        *v19 = (__int64)v19;
        UbpmTriggerConsumerPublishStateChange(a1);
        UBPM_MIDL_user_free(v19[14]);
        UBPM_MIDL_user_free(v19[16]);
        UBPM_MIDL_user_free(v19[12]);
        UBPM_MIDL_user_free(v19);
        v20 = 0;
      }
      v19 = v34;
    }
    while ( v34 != (__int64 *)(a1 + 256) );
  }
  if ( v13 && a6 )
    UbpmpTriggerConsumerReportResult(a1, 2147943691LL, 0);
  if ( v10 == 1168 )
  {
    v10 = v20;
    if ( v20 == 1168 )
      return 1168;
  }
  return v10;
}

```

## disassembly

```asm
0x180003050  mov     [rsp+arg_8], rbx
0x180003055  mov     [rsp+arg_18], r9
0x18000305a  push    rbp
0x18000305b  push    rsi
0x18000305c  push    rdi
0x18000305d  push    r12
0x18000305f  push    r13
0x180003061  push    r14
0x180003063  push    r15
0x180003065  sub     rsp, 60h
0x180003069  mov     rax, [rcx+18h]
0x18000306d  mov     r12d, r8d
0x180003070  mov     [rsp+98h+arg_0], 0
0x18000307b  mov     r13, rdx
0x18000307e  mov     rsi, rcx
0x180003081  mov     ebx, 490h
0x180003086  mov     rdi, [rax+8]
0x18000308a  test    rdi, rdi
0x18000308d  jz      short loc_1800030A9
0x18000308f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003096  inc     rax
0x180003099  cmp     word ptr [rdi+rax*2], 0
0x18000309e  jnz     short loc_180003096
0x1800030a0  cmp     eax, 8
0x1800030a3  ja      loc_180003255
0x1800030a9  lea     r14, [rsi+0E0h]
0x1800030b0  xor     bpl, bpl
0x1800030b3  mov     r15, [r14]
0x1800030b6  cmp     r15, r14
0x1800030b9  jnz     loc_180003294
0x1800030bf  test    r12d, r12d
0x1800030c2  jnz     loc_18000360D
0x1800030c8  test    r13, r13
0x1800030cb  jz      loc_18000319C
0x1800030d1  xor     r12d, r12d
0x1800030d4  lea     rcx, g_QueuedSerialActionsLock
0x1800030db  mov     [rsp+98h+Status], r12d
0x1800030e0  xor     r15b, r15b
0x1800030e3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800030e9  call    cs:__imp_GetCurrentThreadId
0x1800030ef  mov     r14, cs:g_leQueuedSerialActionsListHead
0x1800030f6  lea     rdi, g_leQueuedSerialActionsListHead
0x1800030fd  mov     cs:dword_18004CEA0, eax
0x180003103  cmp     r14, rdi
0x180003106  jnz     loc_180003622
0x18000310c  xor     r12d, r12d
0x18000310f  lea     rcx, g_QueuedSerialActionsLock
0x180003116  mov     cs:dword_18004CEA0, r12d
0x18000311d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000312a  lea     rax, WPP_GLOBAL_Control
0x180003131  cmp     rcx, rax
0x180003134  jz      short loc_180003140
0x180003136  test    byte ptr [rcx+1Ch], 20h
0x18000313a  jnz     loc_180003647
0x180003140  lea     r14, [rsi+100h]
0x180003147  mov     byte ptr [rsi+130h], 0
0x18000314e  mov     r15, [r14]
0x180003151  mov     r12d, 490h
0x180003157  mov     [rsp+98h+Status], 0
0x18000315f  mov     edi, r12d
0x180003162  cmp     r15, r14
0x180003165  jnz     loc_1800033C0
0x18000316b  test    bpl, bpl
0x18000316e  jnz     loc_180003364
0x180003174  cmp     ebx, r12d
0x180003177  jnz     short loc_180003182
0x180003179  cmp     edi, r12d
0x18000317c  mov     ebx, edi
0x18000317e  cmovz   ebx, r12d
0x180003182  mov     eax, ebx
0x180003184  mov     rbx, [rsp+98h+arg_8]
0x18000318c  add     rsp, 60h
0x180003190  pop     r15
0x180003192  pop     r14
0x180003194  pop     r13
0x180003196  pop     r12
0x180003198  pop     rdi
0x180003199  pop     rsi
0x18000319a  pop     rbp
0x18000319b  retn
0x18000319c  mov     r9, [rsp+98h+arg_18]
0x1800031a4  test    r9, r9
0x1800031a7  jnz     loc_180003654
0x1800031ad  mov     rax, [rsi+18h]
0x1800031b1  lea     rcx, g_QueuedSerialActionsLock
0x1800031b8  mov     [rsp+98h+Status], r9d
0x1800031bd  xor     r12b, r12b
0x1800031c0  mov     r15, [rax]
0x1800031c3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800031c9  call    cs:__imp_GetCurrentThreadId
0x1800031cf  mov     r14, cs:g_leQueuedSerialActionsListHead
0x1800031d6  lea     rdi, g_leQueuedSerialActionsListHead
0x1800031dd  mov     cs:dword_18004CEA0, eax
0x1800031e3  cmp     r14, rdi
0x1800031e6  jnz     loc_180003507
0x1800031ec  xor     edi, edi
0x1800031ee  lea     rcx, g_QueuedSerialActionsLock
0x1800031f5  mov     cs:dword_18004CEA0, edi
0x1800031fb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003201  mov     rcx, cs:WPP_GLOBAL_Control
0x180003208  lea     rax, WPP_GLOBAL_Control
0x18000320f  cmp     rcx, rax
0x180003212  jz      loc_180003140
0x180003218  test    byte ptr [rcx+1Ch], 20h
0x18000321c  jz      loc_180003140
0x180003222  test    r12b, r12b
0x180003225  mov     dword ptr [rsp+98h+lpString2], edi
0x180003229  mov     rcx, [rcx+10h]
0x18000322d  lea     rax, aNotRemoved; "Not removed"
0x180003234  lea     r9, aRemoved; "Removed"
0x18000323b  mov     edx, 5Fh ; '_'
0x180003240  cmovz   r9, rax
0x180003244  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000324b  call    WPP_SF_Sd
0x180003250  jmp     loc_180003140
0x180003255  lea     rax, String2; "NT TASK"
0x18000325c  mov     dword ptr [rsp+98h+cchCount2], 7; cchCount2
0x180003264  mov     r9d, 7; cchCount1
0x18000326a  mov     [rsp+98h+lpString2], rax; lpString2
0x18000326f  mov     r8, rdi; lpString1
0x180003272  mov     edx, 1; dwCmpFlags
0x180003277  mov     ecx, 7Fh; Locale
0x18000327c  call    cs:__imp_CompareStringW
0x180003282  cmp     eax, 2
0x180003285  jnz     loc_1800030A9
0x18000328b  add     rdi, 0Eh
0x18000328f  jmp     loc_1800030A9
0x180003294  mov     rax, [r15]
0x180003297  mov     [rsp+98h+var_48], rax
0x18000329c  lea     rax, [r15+34h]
0x1800032a0  mov     [rsp+98h+var_50], rax
0x1800032a5  test    r13, r13
0x1800032a8  jnz     loc_1800033F1
0x1800032ae  mov     [rsp+98h+var_50], rax
0x1800032b3  mov     rax, [rsp+98h+arg_18]
0x1800032bb  test    rax, rax
0x1800032be  jnz     loc_18000352C
0x1800032c4  cmp     [rsp+98h+arg_28], 0
0x1800032cd  mov     ebp, 1
0x1800032d2  jnz     loc_18000353B
0x1800032d8  mov     r8, [r15+18h]
0x1800032dc  cmp     dword ptr [r8+10h], 1
0x1800032e1  jz      loc_180003388
0x1800032e7  lea     r9, [r15+34h]; struct _GUID *
0x1800032eb  mov     r8, rdi; unsigned __int16 *
0x1800032ee  lea     rdx, JOB_TERMINATION; struct _EVENT_DESCRIPTOR *
0x1800032f5  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x1800032fa  xorps   xmm0, xmm0
0x1800032fd  movups  xmmword ptr [rsi+110h], xmm0
0x180003304  mov     rax, [rsi+18h]
0x180003308  cmp     qword ptr [rax+30h], 0
0x18000330d  jnz     loc_1800035BB
0x180003313  mov     rcx, [r15+68h]; void *
0x180003317  call    UbpmQueueConsumerClose
0x18000331c  mov     rcx, [r15]
0x18000331f  cmp     [rcx+8], r15
0x180003323  jnz     loc_180003412
0x180003329  mov     rax, [r15+8]
0x18000332d  cmp     [rax], r15
0x180003330  jnz     loc_180003412
0x180003336  mov     [rax], rcx
0x180003339  mov     bpl, 1
0x18000333c  mov     [rcx+8], rax
0x180003340  mov     rcx, r15
0x180003343  mov     [r15+8], r15
0x180003347  mov     [r15], r15
0x18000334a  call    UBPM_MIDL_user_free
0x18000334f  xor     ebx, ebx
0x180003351  mov     r15, [rsp+98h+var_48]
0x180003356  cmp     r15, r14
0x180003359  jz      loc_1800030BF
0x18000335f  jmp     loc_180003294
0x180003364  cmp     [rsp+98h+arg_28], 0
0x18000336d  jz      loc_180003174
0x180003373  xor     r8d, r8d
0x180003376  mov     edx, 8007050Bh
0x18000337b  mov     rcx, rsi
0x18000337e  call    UbpmpTriggerConsumerReportResult
0x180003383  jmp     loc_180003174
0x180003388  mov     rbx, [r15+20h]
0x18000338c  lea     rdx, [r15+28h]
0x180003390  movzx   r9d, [rsp+98h+arg_20]
0x180003399  mov     rcx, rbx
0x18000339c  call    UbpmpHostTerminateTask
0x1800033a1  mov     [rsp+98h+var_50], rbx
0x1800033a6  test    rbx, rbx
0x1800033a9  jz      loc_1800032E7
0x1800033af  mov     edx, ebp
0x1800033b1  lea     rcx, [rsp+98h+var_50]
0x1800033b6  call    UbpmpDecrementRefAndDelete
0x1800033bb  jmp     loc_1800032E7
0x1800033c0  mov     r12, [r15]
0x1800033c3  test    r13, r13
0x1800033c6  jz      short loc_180003419
0x1800033c8  lea     rdx, [r15+14h]; Uuid2
0x1800033cc  mov     rcx, r13; Uuid1
0x1800033cf  lea     r8, [rsp+98h+Status]; Status
0x1800033d4  call    cs:__imp_UuidEqual
0x1800033da  test    eax, eax
0x1800033dc  jnz     short loc_180003419
0x1800033de  mov     r15, r12
0x1800033e1  cmp     r12, r14
0x1800033e4  jnz     short loc_1800033C0
0x1800033e6  mov     r12d, 490h
0x1800033ec  jmp     loc_18000316B
0x1800033f1  lea     r8, [rsp+98h+arg_0]; Status
0x1800033f9  mov     rdx, rax; Uuid2
0x1800033fc  mov     rcx, r13; Uuid1
0x1800033ff  call    cs:__imp_UuidEqual
0x180003405  test    eax, eax
0x180003407  jnz     loc_1800032B3
0x18000340d  jmp     loc_180003351
0x180003412  mov     ecx, 3
0x180003417  int     29h; Win8: RtlFailFast(ecx)
0x180003419  mov     rax, [rsp+98h+arg_18]
0x180003421  test    rax, rax
0x180003424  jnz     loc_18000366C
0x18000342a  mov     rcx, [r15+88h]; void *
0x180003431  call    UbpmQueueConsumerClose
0x180003436  mov     rax, [r15]
0x180003439  cmp     [rax+8], r15
0x18000343d  jnz     short loc_180003412
0x18000343f  mov     rcx, [r15+8]
0x180003443  cmp     [rcx], r15
0x180003446  jnz     short loc_180003412
0x180003448  mov     [rcx], rax
0x18000344b  mov     [rax+8], rcx
0x18000344f  mov     rcx, rsi
0x180003452  mov     [r15+8], r15
0x180003456  mov     [r15], r15
0x180003459  call    UbpmTriggerConsumerPublishStateChange
0x18000345e  mov     rcx, [r15+70h]
0x180003462  call    UBPM_MIDL_user_free
0x180003467  mov     rcx, [r15+80h]
0x18000346e  call    UBPM_MIDL_user_free
0x180003473  mov     rcx, [r15+60h]
0x180003477  call    UBPM_MIDL_user_free
0x18000347c  mov     rcx, r15
0x18000347f  call    UBPM_MIDL_user_free
0x180003484  xor     edi, edi
0x180003486  jmp     loc_1800033DE
0x18000348b  mov     rax, [r14]
0x18000348e  cmp     [rax+8], r14
0x180003492  jnz     loc_180003412
0x180003498  mov     rcx, [r14+8]
0x18000349c  cmp     [rcx], r14
0x18000349f  jnz     loc_180003412
0x1800034a5  mov     [rcx], rax
0x1800034a8  mov     [rax+8], rcx
0x1800034ac  mov     rcx, r14
0x1800034af  mov     [r14+8], r14
0x1800034b3  mov     [r14], r14
0x1800034b6  call    UBPM_MIDL_user_free
0x1800034bb  mov     r15b, 1
0x1800034be  jmp     loc_18000363F
0x1800034c3  mov     rax, [r14]
0x1800034c6  cmp     [rax+8], r14
0x1800034ca  jnz     loc_180003412
0x1800034d0  mov     rcx, [r14+8]
0x1800034d4  cmp     [rcx], r14
0x1800034d7  jnz     loc_180003412
0x1800034dd  mov     [rcx], rax
0x1800034e0  mov     [rax+8], rcx
0x1800034e4  mov     rcx, r14
0x1800034e7  mov     [r14+8], r14
0x1800034eb  mov     [r14], r14
0x1800034ee  call    UBPM_MIDL_user_free
0x1800034f3  mov     r12b, 1
0x1800034f6  mov     rax, [rsp+98h+var_50]
0x1800034fb  mov     r14, rax
0x1800034fe  cmp     rax, rdi
0x180003501  jz      loc_1800031EC
0x180003507  mov     rax, [r14]
0x18000350a  mov     [rsp+98h+var_50], rax
0x18000350f  test    r15, r15
0x180003512  jz      short loc_1800034FB
0x180003514  lea     rdx, [r14+20h]; Uuid2
0x180003518  mov     rcx, r15; Uuid1
0x18000351b  lea     r8, [rsp+98h+Status]; Status
0x180003520  call    cs:__imp_UuidEqual
0x180003526  test    eax, eax
0x180003528  jz      short loc_1800034F6
0x18000352a  jmp     short loc_1800034C3
0x18000352c  cmp     rax, [r15+50h]
0x180003530  jnz     loc_180003351
0x180003536  jmp     loc_1800032C4
0x18000353b  mov     rcx, [rsp+98h+arg_28]
0x180003543  lea     rax, [rsp+98h+Status]
0x180003548  xor     r9d, r9d
0x18000354b  mov     [rsp+98h+lpString2], rax
0x180003550  xor     r8d, r8d
0x180003553  mov     qword ptr [rsp+98h+Status], 0
0x18000355c  mov     edx, ebp
0x18000355e  call    UbpmUtilsGetAccountNamesFromSid
0x180003563  mov     rbx, qword ptr [rsp+98h+Status]
0x180003568  lea     rax, aNone; "(NONE)"
0x18000356f  mov     r9, [rsp+98h+var_50]; struct _GUID *
0x180003574  test    rbx, rbx
0x180003577  mov     rcx, cs:g_hTaskEventManager; this
  ... truncated ...
```
