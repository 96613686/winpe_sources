# UbpmTerminateActionsForConsumer

- ea: `0x18000a230`
- end: `0x18000a86d`
- name: `UbpmTerminateActionsForConsumer`
- size: `1597`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180001f40`
- `0x180002ec0`
- `0x180003100`
- `0x1800381e0`

## callees

- `0x1800033b0`
- `0x180003790`
- `0x180004c30`
- `0x180005320`
- `0x180006820`
- `0x180007e9c`
- `0x18000a230`
- `0x18000a880`
- `0x18000a9ac`
- `0x18000fbf0`
- `0x1800182a0`
- `0x18001af64`
- `0x180024740`
- `0x1800265d0`
- `0x180030d58`
- `0x18003937c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a2b0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a393`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a799`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a2b0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a393`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a799`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a2f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a3d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a7e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a2f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a3d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a7e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a39f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a39f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a7a5`
- `RPCRT4!UuidEqual` at `0x18000a590`
- `RPCRT4!UuidEqual` at `0x18000a5c5`
- `RPCRT4!UuidEqual` at `0x18000a6ea`
- `RPCRT4!UuidEqual` at `0x18000a81a`
- `RPCRT4!UuidEqual` at `0x18000a590`
- `RPCRT4!UuidEqual` at `0x18000a5c5`
- `RPCRT4!UuidEqual` at `0x18000a6ea`
- `RPCRT4!UuidEqual` at `0x18000a81a`

## string_xrefs

- `0x18000a76a`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18000a416`: `Removed`
- `0x18000a40f`: `Not removed`

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
  __int64 v7; // r15
  unsigned int v10; // ebx
  _QWORD *v11; // rsi
  _QWORD *v12; // r14
  char v13; // r12
  char v14; // bp
  DWORD v15; // eax
  UUID *v16; // r14
  _QWORD *v17; // rcx
  unsigned __int16 *v18; // r15
  int v19; // esi
  UUID **v21; // rax
  UUID *v22; // rbp
  DWORD v23; // eax
  unsigned __int16 *v24; // r14
  bool v25; // zf
  __int64 v26; // rcx
  const wchar_t *v27; // r9
  __int64 v28; // rcx
  unsigned __int16 *v29; // r12
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  unsigned __int16 *v36; // rbx
  __int64 v37; // rbp
  unsigned __int16 *v38; // rax
  unsigned __int16 *v39; // rax
  unsigned __int16 **v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  UUID *v53; // rax
  UUID **v54; // rcx
  unsigned __int16 *v55; // rax
  unsigned __int16 **v56; // rcx
  unsigned __int16 *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  const struct _EVENT_DESCRIPTOR *v61; // rdx
  unsigned __int16 *v62; // rbx
  unsigned __int16 *v63; // rax
  int v64; // edx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  DWORD CurrentThreadId; // eax
  __int64 v70; // r8
  UUID *v71; // r15
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  void *v75; // [rsp+28h] [rbp-70h]
  const struct _GUID *v76; // [rsp+30h] [rbp-68h]
  RPC_STATUS Status[2]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v78; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 *ConsumerFriendlyName; // [rsp+50h] [rbp-48h]
  _QWORD *v80; // [rsp+58h] [rbp-40h]
  RPC_STATUS v81; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v82; // [rsp+B8h] [rbp+20h]

  v82 = a4;
  v81 = 0;
  v7 = a4;
  v10 = 1168;
  v11 = (_QWORD *)(a1 + 224);
  ConsumerFriendlyName = (unsigned __int16 *)UbpmpGetConsumerFriendlyName(*(PCNZWCH *)(*(_QWORD *)(a1 + 24) + 8LL));
  v12 = (_QWORD *)*v11;
  v13 = 0;
  if ( (_QWORD *)*v11 != v11 )
  {
    v28 = 1;
    while ( 1 )
    {
      v80 = (_QWORD *)*v12;
      *(_QWORD *)Status = (char *)v12 + 52;
      if ( !a2 )
        break;
      if ( UuidEqual(a2, (UUID *)((char *)v12 + 52), &v81) )
      {
        v28 = 1;
        goto LABEL_26;
      }
LABEL_34:
      v12 = v80;
      v28 = 1;
      if ( v80 == v11 )
        goto LABEL_2;
    }
    *(_QWORD *)Status = (char *)v12 + 52;
LABEL_26:
    if ( !v7 || v7 == v12[10] )
    {
      if ( a6 )
      {
        v78 = 0;
        UbpmUtilsGetAccountNamesFromSid(a6, 1, 0, 0, (__int64)&v78);
        v62 = v78;
        v63 = L"(NONE)";
        v29 = ConsumerFriendlyName;
        if ( v78 )
          v63 = v78;
        v64 = EventManager::EvtReport(
                g_hTaskEventManager,
                v61,
                ConsumerFriendlyName,
                *(const struct _GUID **)Status,
                v63,
                v75,
                v76);
        v65 = (unsigned __int16)v64;
        if ( v64 >= 0 )
          v65 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", STOPPING_ON_REQUEST, v65);
        UBPM_MIDL_user_free(v62, v66, v67, v68);
      }
      else
      {
        v29 = ConsumerFriendlyName;
      }
      v30 = v12[3];
      if ( *(_DWORD *)(v30 + 16) == 1 )
      {
        v36 = (unsigned __int16 *)v12[4];
        UbpmpHostTerminateTask(v36, v12 + 5, v30, a5);
        v78 = v36;
        if ( v36 )
          UbpmpDecrementRefAndDelete(&v78, 1);
      }
      ReportTaskEvent((void *)v28, &JOB_TERMINATION, v29, (const struct _GUID *)((char *)v12 + 52));
      *(_OWORD *)(a1 + 272) = 0;
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) )
      {
        RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
        CurrentThreadId = GetCurrentThreadId();
        v70 = 6;
        dword_18004FFE8 = CurrentThreadId;
        if ( !a5 )
          v70 = 1;
        UbpmpMaintenanceTaskStoppedCallout(a1, v12, v70);
        dword_18004FFE8 = 0;
        RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
      }
      UbpmQueueConsumerClose((void *)v12[13]);
      v34 = (_QWORD *)*v12;
      if ( *(_QWORD **)(*v12 + 8LL) != v12 || (v35 = (_QWORD *)v12[1], (_QWORD *)*v35 != v12) )
LABEL_47:
        __fastfail(3u);
      *v35 = v34;
      v13 = 1;
      v34[1] = v35;
      v12[1] = v12;
      *v12 = v12;
      UBPM_MIDL_user_free(v12, v31, v32, v33);
      v10 = 0;
    }
    goto LABEL_34;
  }
LABEL_2:
  if ( a3 )
    UbpmStatsOperation(a1, 2, 0);
  if ( a2 )
  {
    Status[0] = 0;
    v14 = 0;
    RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
    v15 = GetCurrentThreadId();
    v16 = (UUID *)g_leQueuedSerialActionsListHead;
    dword_18004FFA0 = v15;
    while ( v16 != (UUID *)&g_leQueuedSerialActionsListHead )
    {
      v71 = *(UUID **)&v16->Data1;
      if ( UuidEqual(a2, v16 + 1, Status) )
      {
        v53 = *(UUID **)&v16->Data1;
        if ( *(UUID **)(*(_QWORD *)&v16->Data1 + 8LL) != v16 )
          goto LABEL_47;
        v54 = *(UUID ***)v16->Data4;
        if ( *v54 != v16 )
          goto LABEL_47;
        *v54 = v53;
        *(_QWORD *)v53->Data4 = v54;
        *(_QWORD *)v16->Data4 = v16;
        *(_QWORD *)&v16->Data1 = v16;
        UBPM_MIDL_user_free(v16, v72, v73, v74);
        v14 = 1;
      }
      v16 = v71;
    }
    dword_18004FFA0 = 0;
    RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_9;
    v25 = v14 == 0;
LABEL_20:
    v26 = v17[2];
    v27 = L"Removed";
    if ( v25 )
      v27 = L"Not removed";
    WPP_SF_Sd(v26, 95, (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, (_DWORD)v27, 0);
    goto LABEL_9;
  }
  if ( v7 )
  {
    UbpmpRemoveQueuedSerialActions(0, 0, 0, 0);
    goto LABEL_9;
  }
  v21 = *(UUID ***)(a1 + 24);
  Status[0] = 0;
  v22 = *v21;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  v23 = GetCurrentThreadId();
  v24 = (unsigned __int16 *)g_leQueuedSerialActionsListHead;
  dword_18004FFA0 = v23;
  if ( g_leQueuedSerialActionsListHead != (_UNKNOWN *)&g_leQueuedSerialActionsListHead )
  {
    do
    {
      v57 = *(unsigned __int16 **)v24;
      ConsumerFriendlyName = *(unsigned __int16 **)v24;
      if ( v22 )
      {
        if ( UuidEqual(v22, (UUID *)v24 + 2, Status) )
        {
          v55 = *(unsigned __int16 **)v24;
          if ( *(unsigned __int16 **)(*(_QWORD *)v24 + 8LL) != v24 )
            goto LABEL_47;
          v56 = (unsigned __int16 **)*((_QWORD *)v24 + 1);
          if ( *v56 != v24 )
            goto LABEL_47;
          *v56 = v55;
          *((_QWORD *)v55 + 1) = v56;
          *((_QWORD *)v24 + 1) = v24;
          *(_QWORD *)v24 = v24;
          UBPM_MIDL_user_free(v24, v58, v59, v60);
          LOBYTE(v7) = 1;
        }
        v57 = ConsumerFriendlyName;
      }
      v24 = v57;
    }
    while ( v57 != (unsigned __int16 *)&g_leQueuedSerialActionsListHead );
  }
  dword_18004FFA0 = 0;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v25 = (_BYTE)v7 == 0;
    goto LABEL_20;
  }
LABEL_9:
  *(_BYTE *)(a1 + 304) = 0;
  v18 = *(unsigned __int16 **)(a1 + 256);
  Status[0] = 0;
  v19 = 1168;
  if ( v18 != (unsigned __int16 *)(a1 + 256) )
  {
    v37 = v82;
    do
    {
      v38 = *(unsigned __int16 **)v18;
      v78 = *(unsigned __int16 **)v18;
      if ( !a2 || (v25 = UuidEqual(a2, (UUID *)(v18 + 10), Status) == 0, v38 = v78, !v25) )
      {
        if ( !v37 || v37 == *((_QWORD *)v18 + 10) )
        {
          UbpmQueueConsumerClose(*((void **)v18 + 17));
          v39 = *(unsigned __int16 **)v18;
          if ( *(unsigned __int16 **)(*(_QWORD *)v18 + 8LL) != v18 )
            goto LABEL_47;
          v40 = (unsigned __int16 **)*((_QWORD *)v18 + 1);
          if ( *v40 != v18 )
            goto LABEL_47;
          *v40 = v39;
          *((_QWORD *)v39 + 1) = v40;
          *((_QWORD *)v18 + 1) = v18;
          *(_QWORD *)v18 = v18;
          UbpmTriggerConsumerPublishStateChange(a1);
          UBPM_MIDL_user_free(*((_QWORD *)v18 + 14), v41, v42, v43);
          UBPM_MIDL_user_free(*((_QWORD *)v18 + 16), v44, v45, v46);
          UBPM_MIDL_user_free(*((_QWORD *)v18 + 12), v47, v48, v49);
          UBPM_MIDL_user_free(v18, v50, v51, v52);
          v38 = v78;
          v19 = 0;
        }
      }
      v18 = v38;
    }
    while ( v38 != (unsigned __int16 *)(a1 + 256) );
  }
  if ( v13 && a6 )
    UbpmpTriggerConsumerReportResult(a1, 2147943691LL, 0);
  if ( v10 == 1168 )
  {
    v10 = v19;
    if ( v19 == 1168 )
      return 1168;
  }
  return v10;
}

```

## disassembly

```asm
0x18000a230  mov     [rsp+arg_8], rbx
0x18000a235  mov     [rsp+arg_18], r9
0x18000a23a  push    rbp
0x18000a23b  push    rsi
0x18000a23c  push    rdi
0x18000a23d  push    r12
0x18000a23f  push    r13
0x18000a241  push    r14
0x18000a243  push    r15
0x18000a245  sub     rsp, 60h
0x18000a249  mov     rdi, rcx
0x18000a24c  mov     [rsp+98h+arg_0], 0
0x18000a257  mov     rcx, [rcx+18h]
0x18000a25b  mov     r15, r9
0x18000a25e  mov     ebp, r8d
0x18000a261  mov     r13, rdx
0x18000a264  mov     ebx, 490h
0x18000a269  mov     rcx, [rcx+8]; lpString1
0x18000a26d  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x18000a272  lea     rsi, [rdi+0E0h]
0x18000a279  mov     [rsp+98h+var_48], rax
0x18000a27e  mov     r14, [rsi]
0x18000a281  xor     r12b, r12b
0x18000a284  cmp     r14, rsi
0x18000a287  jnz     loc_18000A437
0x18000a28d  test    ebp, ebp
0x18000a28f  jnz     loc_18000A7F6
0x18000a295  test    r13, r13
0x18000a298  jz      loc_18000A377
0x18000a29e  xor     r15d, r15d
0x18000a2a1  lea     rcx, g_QueuedSerialActionsLock
0x18000a2a8  mov     [rsp+98h+Status], r15d
0x18000a2ad  xor     bpl, bpl
0x18000a2b0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a2b7  nop     dword ptr [rax+rax+00h]
0x18000a2bc  call    cs:__imp_GetCurrentThreadId
0x18000a2c3  nop     dword ptr [rax+rax+00h]
0x18000a2c8  mov     r14, cs:g_leQueuedSerialActionsListHead
0x18000a2cf  lea     rsi, g_leQueuedSerialActionsListHead
0x18000a2d6  mov     cs:dword_18004FFA0, eax
0x18000a2dc  cmp     r14, rsi
0x18000a2df  jnz     loc_18000A80B
0x18000a2e5  xor     r15d, r15d
0x18000a2e8  lea     rcx, g_QueuedSerialActionsLock
0x18000a2ef  mov     cs:dword_18004FFA0, r15d
0x18000a2f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a2fd  nop     dword ptr [rax+rax+00h]
0x18000a302  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a309  lea     rax, WPP_GLOBAL_Control
0x18000a310  cmp     rcx, rax
0x18000a313  jz      short loc_18000A31F
0x18000a315  test    byte ptr [rcx+1Ch], 20h
0x18000a319  jnz     loc_18000A836
0x18000a31f  lea     r14, [rdi+100h]
0x18000a326  mov     byte ptr [rdi+130h], 0
0x18000a32d  mov     r15, [r14]
0x18000a330  mov     ebp, 490h
0x18000a335  mov     [rsp+98h+Status], 0
0x18000a33d  mov     esi, ebp
0x18000a33f  cmp     r15, r14
0x18000a342  jnz     loc_18000A56F
0x18000a348  test    r12b, r12b
0x18000a34b  jnz     loc_18000A50E
0x18000a351  cmp     ebx, ebp
0x18000a353  jnz     short loc_18000A35C
0x18000a355  cmp     esi, ebp
0x18000a357  mov     ebx, esi
0x18000a359  cmovz   ebx, ebp
0x18000a35c  mov     eax, ebx
0x18000a35e  mov     rbx, [rsp+98h+arg_8]
0x18000a366  add     rsp, 60h
0x18000a36a  pop     r15
0x18000a36c  pop     r14
0x18000a36e  pop     r13
0x18000a370  pop     r12
0x18000a372  pop     rdi
0x18000a373  pop     rsi
0x18000a374  pop     rbp
0x18000a375  retn
0x18000a377  test    r15, r15
0x18000a37a  jnz     loc_18000A843
0x18000a380  mov     rax, [rdi+18h]
0x18000a384  lea     rcx, g_QueuedSerialActionsLock
0x18000a38b  mov     [rsp+98h+Status], r15d
0x18000a390  mov     rbp, [rax]
0x18000a393  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a39a  nop     dword ptr [rax+rax+00h]
0x18000a39f  call    cs:__imp_GetCurrentThreadId
0x18000a3a6  nop     dword ptr [rax+rax+00h]
0x18000a3ab  mov     r14, cs:g_leQueuedSerialActionsListHead
0x18000a3b2  lea     rsi, g_leQueuedSerialActionsListHead
0x18000a3b9  mov     cs:dword_18004FFA0, eax
0x18000a3bf  cmp     r14, rsi
0x18000a3c2  jnz     loc_18000A6D1
0x18000a3c8  xor     esi, esi
0x18000a3ca  lea     rcx, g_QueuedSerialActionsLock
0x18000a3d1  mov     cs:dword_18004FFA0, esi
0x18000a3d7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a3de  nop     dword ptr [rax+rax+00h]
0x18000a3e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3ea  lea     rax, WPP_GLOBAL_Control
0x18000a3f1  cmp     rcx, rax
0x18000a3f4  jz      loc_18000A31F
0x18000a3fa  test    byte ptr [rcx+1Ch], 20h
0x18000a3fe  jz      loc_18000A31F
0x18000a404  test    r15b, r15b
0x18000a407  mov     dword ptr [rsp+98h+var_78], esi
0x18000a40b  mov     rcx, [rcx+10h]
0x18000a40f  lea     rax, aNotRemoved; "Not removed"
0x18000a416  lea     r9, aRemoved; "Removed"
0x18000a41d  mov     edx, 5Fh ; '_'
0x18000a422  cmovz   r9, rax
0x18000a426  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000a42d  call    WPP_SF_Sd
0x18000a432  jmp     loc_18000A31F
0x18000a437  mov     ecx, 1; void *
0x18000a43c  mov     rax, [r14]
0x18000a43f  mov     [rsp+98h+var_40], rax
0x18000a444  lea     rax, [r14+34h]
0x18000a448  mov     qword ptr [rsp+98h+Status], rax
0x18000a44d  test    r13, r13
0x18000a450  jnz     loc_18000A5B7
0x18000a456  mov     qword ptr [rsp+98h+Status], rax
0x18000a45b  test    r15, r15
0x18000a45e  jnz     loc_18000A6FC
0x18000a464  cmp     [rsp+98h+arg_28], 0
0x18000a46d  jnz     loc_18000A70B
0x18000a473  mov     r12, [rsp+98h+var_48]
0x18000a478  mov     r8, [r14+18h]
0x18000a47c  cmp     dword ptr [r8+10h], 1
0x18000a481  jz      loc_18000A532
0x18000a487  mov     ebx, 1
0x18000a48c  lea     r9, [r14+34h]; struct _GUID *
0x18000a490  mov     r8, r12; unsigned __int16 *
0x18000a493  lea     rdx, JOB_TERMINATION; struct _EVENT_DESCRIPTOR *
0x18000a49a  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000a49f  xorps   xmm0, xmm0
0x18000a4a2  movups  xmmword ptr [rdi+110h], xmm0
0x18000a4a9  mov     rax, [rdi+18h]
0x18000a4ad  cmp     qword ptr [rax+30h], 0
0x18000a4b2  jnz     loc_18000A792
0x18000a4b8  mov     rcx, [r14+68h]; void *
0x18000a4bc  call    UbpmQueueConsumerClose
0x18000a4c1  mov     rcx, [r14]
0x18000a4c4  cmp     [rcx+8], r14
0x18000a4c8  jnz     loc_18000A5E3
0x18000a4ce  mov     rax, [r14+8]
0x18000a4d2  cmp     [rax], r14
0x18000a4d5  jnz     loc_18000A5E3
0x18000a4db  mov     [rax], rcx
0x18000a4de  mov     r12b, 1
0x18000a4e1  mov     [rcx+8], rax
0x18000a4e5  mov     rcx, r14
0x18000a4e8  mov     [r14+8], r14
0x18000a4ec  mov     [r14], r14
0x18000a4ef  call    UBPM_MIDL_user_free
0x18000a4f4  xor     ebx, ebx
0x18000a4f6  mov     r14, [rsp+98h+var_40]
0x18000a4fb  mov     ecx, 1
0x18000a500  cmp     r14, rsi
0x18000a503  jz      loc_18000A28D
0x18000a509  jmp     loc_18000A43C
0x18000a50e  cmp     [rsp+98h+arg_28], 0
0x18000a517  jz      loc_18000A351
0x18000a51d  xor     r8d, r8d
0x18000a520  mov     edx, 8007050Bh
0x18000a525  mov     rcx, rdi
0x18000a528  call    UbpmpTriggerConsumerReportResult
0x18000a52d  jmp     loc_18000A351
0x18000a532  mov     rbx, [r14+20h]
0x18000a536  lea     rdx, [r14+28h]
0x18000a53a  movzx   r9d, [rsp+98h+arg_20]
0x18000a543  mov     rcx, rbx
0x18000a546  call    UbpmpHostTerminateTask
0x18000a54b  test    rbx, rbx
0x18000a54e  mov     [rsp+98h+var_50], rbx
0x18000a553  mov     ebx, 1
0x18000a558  jz      loc_18000A48C
0x18000a55e  mov     edx, ebx
0x18000a560  lea     rcx, [rsp+98h+var_50]
0x18000a565  call    UbpmpDecrementRefAndDelete
0x18000a56a  jmp     loc_18000A48C
0x18000a56f  mov     rbp, [rsp+98h+arg_18]
0x18000a577  mov     rax, [r15]
0x18000a57a  mov     [rsp+98h+var_50], rax
0x18000a57f  test    r13, r13
0x18000a582  jz      short loc_18000A5EA
0x18000a584  lea     rdx, [r15+14h]; Uuid2
0x18000a588  mov     rcx, r13; Uuid1
0x18000a58b  lea     r8, [rsp+98h+Status]; Status
0x18000a590  call    cs:__imp_UuidEqual
0x18000a597  nop     dword ptr [rax+rax+00h]
0x18000a59c  test    eax, eax
0x18000a59e  mov     rax, [rsp+98h+var_50]
0x18000a5a3  jnz     short loc_18000A5EA
0x18000a5a5  mov     r15, rax
0x18000a5a8  cmp     rax, r14
0x18000a5ab  jnz     short loc_18000A577
0x18000a5ad  mov     ebp, 490h
0x18000a5b2  jmp     loc_18000A348
0x18000a5b7  lea     r8, [rsp+98h+arg_0]; Status
0x18000a5bf  mov     rdx, rax; Uuid2
0x18000a5c2  mov     rcx, r13; Uuid1
0x18000a5c5  call    cs:__imp_UuidEqual
0x18000a5cc  nop     dword ptr [rax+rax+00h]
0x18000a5d1  test    eax, eax
0x18000a5d3  jz      loc_18000A4F6
0x18000a5d9  mov     ecx, 1
0x18000a5de  jmp     loc_18000A45B
0x18000a5e3  mov     ecx, 3
0x18000a5e8  int     29h; Win8: RtlFailFast(ecx)
0x18000a5ea  test    rbp, rbp
0x18000a5ed  jnz     loc_18000A85E
0x18000a5f3  mov     rcx, [r15+88h]; void *
0x18000a5fa  call    UbpmQueueConsumerClose
0x18000a5ff  mov     rax, [r15]
0x18000a602  cmp     [rax+8], r15
0x18000a606  jnz     short loc_18000A5E3
0x18000a608  mov     rcx, [r15+8]
0x18000a60c  cmp     [rcx], r15
0x18000a60f  jnz     short loc_18000A5E3
0x18000a611  mov     [rcx], rax
0x18000a614  mov     [rax+8], rcx
0x18000a618  mov     rcx, rdi
0x18000a61b  mov     [r15+8], r15
0x18000a61f  mov     [r15], r15
0x18000a622  call    UbpmTriggerConsumerPublishStateChange
0x18000a627  mov     rcx, [r15+70h]
0x18000a62b  call    UBPM_MIDL_user_free
0x18000a630  mov     rcx, [r15+80h]
0x18000a637  call    UBPM_MIDL_user_free
0x18000a63c  mov     rcx, [r15+60h]
0x18000a640  call    UBPM_MIDL_user_free
0x18000a645  mov     rcx, r15
0x18000a648  call    UBPM_MIDL_user_free
0x18000a64d  mov     rax, [rsp+98h+var_50]
0x18000a652  xor     esi, esi
0x18000a654  jmp     loc_18000A5A5
0x18000a659  mov     rax, [r14]
0x18000a65c  cmp     [rax+8], r14
0x18000a660  jnz     short loc_18000A5E3
0x18000a662  mov     rcx, [r14+8]
0x18000a666  cmp     [rcx], r14
0x18000a669  jnz     loc_18000A5E3
0x18000a66f  mov     [rcx], rax
0x18000a672  mov     [rax+8], rcx
0x18000a676  mov     rcx, r14
0x18000a679  mov     [r14+8], r14
0x18000a67d  mov     [r14], r14
0x18000a680  call    UBPM_MIDL_user_free
0x18000a685  mov     bpl, 1
0x18000a688  jmp     loc_18000A82E
0x18000a68d  mov     rax, [r14]
0x18000a690  cmp     [rax+8], r14
0x18000a694  jnz     loc_18000A5E3
0x18000a69a  mov     rcx, [r14+8]
0x18000a69e  cmp     [rcx], r14
0x18000a6a1  jnz     loc_18000A5E3
0x18000a6a7  mov     [rcx], rax
0x18000a6aa  mov     [rax+8], rcx
0x18000a6ae  mov     rcx, r14
0x18000a6b1  mov     [r14+8], r14
0x18000a6b5  mov     [r14], r14
0x18000a6b8  call    UBPM_MIDL_user_free
0x18000a6bd  mov     r15b, 1
0x18000a6c0  mov     rax, [rsp+98h+var_48]
0x18000a6c5  mov     r14, rax
0x18000a6c8  cmp     rax, rsi
0x18000a6cb  jz      loc_18000A3C8
0x18000a6d1  mov     rax, [r14]
0x18000a6d4  mov     [rsp+98h+var_48], rax
0x18000a6d9  test    rbp, rbp
0x18000a6dc  jz      short loc_18000A6C5
0x18000a6de  lea     rdx, [r14+20h]; Uuid2
0x18000a6e2  mov     rcx, rbp; Uuid1
0x18000a6e5  lea     r8, [rsp+98h+Status]; Status
0x18000a6ea  call    cs:__imp_UuidEqual
0x18000a6f1  nop     dword ptr [rax+rax+00h]
0x18000a6f6  test    eax, eax
0x18000a6f8  jz      short loc_18000A6C0
0x18000a6fa  jmp     short loc_18000A68D
0x18000a6fc  cmp     r15, [r14+50h]
0x18000a700  jnz     loc_18000A4F6
0x18000a706  jmp     loc_18000A464
0x18000a70b  lea     rax, [rsp+98h+var_50]
0x18000a710  mov     [rsp+98h+var_50], 0
0x18000a719  mov     edx, ecx
0x18000a71b  mov     [rsp+98h+var_78], rax
0x18000a720  mov     rcx, [rsp+98h+arg_28]
0x18000a728  xor     r9d, r9d
0x18000a72b  xor     r8d, r8d
0x18000a72e  call    UbpmUtilsGetAccountNamesFromSid
0x18000a733  mov     rbx, [rsp+98h+var_50]
0x18000a738  lea     rax, aNone; "(NONE)"
0x18000a73f  mov     r12, [rsp+98h+var_48]
0x18000a744  test    rbx, rbx
0x18000a747  mov     r9, qword ptr [rsp+98h+Status]; struct _GUID *
0x18000a74c  mov     r8, r12; unsigned __int16 *
0x18000a74f  mov     rcx, cs:g_hTaskEventManager; this
0x18000a756  cmovnz  rax, rbx
  ... truncated ...
```
