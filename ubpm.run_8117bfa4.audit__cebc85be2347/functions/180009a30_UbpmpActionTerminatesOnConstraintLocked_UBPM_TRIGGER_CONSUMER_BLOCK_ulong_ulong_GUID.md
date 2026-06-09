# UbpmpActionTerminatesOnConstraintLocked(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,_GUID *)

- ea: `0x180009a30`
- end: `0x18000a227`
- name: `?UbpmpActionTerminatesOnConstraintLocked@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAU_GUID@@@Z`
- size: `2039`
- prototype: `void __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, unsigned int, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a940`
- `0x18000ae00`
- `0x18000d0d0`

## callees

- `0x180003790`
- `0x180004c30`
- `0x180005320`
- `0x180006820`
- `0x180008430`
- `0x180009a30`
- `0x18000a880`
- `0x18000a9ac`
- `0x18000d9bc`
- `0x18000fbf0`
- `0x180013c90`
- `0x18001af64`
- `0x18001b5cc`
- `0x180030d58`
- `0x1800373c0`
- `0x1800383b8`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009b2e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009c74`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009e3e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009b2e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009c74`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009e3e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009b71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009cba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009e7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009b71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009cba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e4a`
- `RPCRT4!UuidEqual` at `0x18000a007`
- `RPCRT4!UuidEqual` at `0x18000a0c9`
- `RPCRT4!UuidEqual` at `0x18000a121`
- `RPCRT4!UuidEqual` at `0x18000a1a7`
- `RPCRT4!UuidEqual` at `0x18000a1d1`
- `RPCRT4!UuidEqual` at `0x18000a007`
- `RPCRT4!UuidEqual` at `0x18000a0c9`
- `RPCRT4!UuidEqual` at `0x18000a121`
- `RPCRT4!UuidEqual` at `0x18000a1a7`
- `RPCRT4!UuidEqual` at `0x18000a1d1`

## string_xrefs

- `0x180009af2`: `Removed`
- `0x18000a0e6`: `Not removed`
- `0x18000a1fb`: `Not removed`

## pseudocode

```c
void __fastcall UbpmpActionTerminatesOnConstraintLocked(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        int a2,
        RPC_STATUS a3,
        struct _GUID *a4)
{
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v4; // r15
  __int64 v5; // rcx
  char v6; // r13
  int v7; // r12d
  __int64 v8; // rbx
  const WCHAR *v9; // rcx
  const unsigned __int16 *ConsumerFriendlyName; // rax
  __int64 v11; // r8
  unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rcx
  PVOID *v14; // rcx
  char *v15; // rbx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v16; // rdi
  char v17; // si
  const wchar_t *v18; // r14
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v19; // rdi
  UUID **v20; // rax
  char v21; // bp
  UUID *v22; // rdi
  DWORD v23; // eax
  UUID *v24; // rbx
  int v25; // r8d
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v26; // rbp
  unsigned __int8 v27; // r13
  char v28; // r12
  DWORD CurrentThreadId; // eax
  UUID *v30; // rsi
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v34; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v35; // rax
  int v36; // r8d
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v37; // rbp
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v38; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v39; // rax
  __int64 v40; // rsi
  UUID *v41; // rcx
  UUID **v42; // rax
  UUID *v43; // rax
  UUID **v44; // rcx
  int v45; // r8d
  UUID *v46; // rbp
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  const wchar_t *v50; // r9
  int v51; // r8d
  UUID *v52; // r15
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  RPC_STATUS v56; // [rsp+30h] [rbp-278h] BYREF
  RPC_STATUS Status; // [rsp+34h] [rbp-274h] BYREF
  UUID *Uuid2; // [rsp+38h] [rbp-270h]
  RPC_STATUS v59[2]; // [rsp+40h] [rbp-268h] BYREF
  int v60; // [rsp+48h] [rbp-260h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v61; // [rsp+50h] [rbp-258h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v62; // [rsp+58h] [rbp-250h]
  unsigned __int16 v63[256]; // [rsp+60h] [rbp-248h] BYREF

  v4 = a1;
  v61 = a1;
  v5 = *((_QWORD *)a1 + 3);
  v6 = a3;
  Status = 0;
  v7 = a2;
  Uuid2 = a4;
  v8 = 2147483646;
  v56 = a3;
  v9 = *(const WCHAR **)(v5 + 8);
  v60 = a2;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(v9);
  v11 = 256;
  v12 = v63;
  do
  {
    if ( !v8 )
      break;
    if ( !*ConsumerFriendlyName )
      break;
    *v12++ = *ConsumerFriendlyName++;
    --v8;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  UbpmpActionContextCleanup(v4);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  v15 = (char *)v4 + 224;
  v16 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)*((_QWORD *)v4 + 28);
  v17 = 0;
  v18 = L"Removed";
  if ( v16 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v4 + 224) )
  {
    do
    {
      v25 = *((_DWORD *)v16 + 25);
      v26 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v16;
      v62 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v16;
      if ( (v25 & 0x10001) == 0x10001 )
      {
        if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 )
          goto LABEL_31;
        WPP_SF_SL(
          (unsigned int)v14[2],
          13,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          (unsigned int)v63,
          v25);
      }
      else
      {
        if ( Uuid2 )
        {
          if ( UuidEqual((UUID *)((char *)v16 + 52), Uuid2, &Status) && !Status )
          {
            v14 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_31;
            WPP_SF_S_guid_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v45, (unsigned int)v63, (__int64)Uuid2, v6);
            goto LABEL_30;
          }
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 != 0xFFFF && *((_DWORD *)v16 + 24) != v7 )
          goto LABEL_31;
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
          WPP_SF_Sd(
            (unsigned int)v14[2],
            15,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            (unsigned int)v63,
            *((_DWORD *)v16 + 24));
        if ( *(_DWORD *)(*((_QWORD *)v16 + 3) + 16LL) == 1 )
        {
          v40 = *((_QWORD *)v16 + 4);
          if ( v40 && (unsigned int)UbpmpTerminateNonHostedTask(*((struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)v16 + 4)) )
          {
            UbpmpSendCommandGetResponse(v40, 0, (char *)v16 + 40, 3);
            *(_QWORD *)v59 = v40;
            UbpmpDecrementRefAndDelete(v59, 1);
          }
          else
          {
            *(_QWORD *)v59 = v40;
            if ( v40 )
              UbpmpDecrementRefAndDelete(v59, 1);
          }
        }
        if ( (v6 & 4) != 0 )
        {
          v27 = 3;
          ReportTaskEvent(v14, &STOPPING_ON_BATTERIES, v63, (const struct _GUID *)((char *)v16 + 52));
        }
        else if ( v6 >= 0 )
        {
          v27 = 0;
          if ( (v56 & 0x10000) != 0 )
          {
            v27 = 5;
            ReportTaskEvent(v14, &RUNNING_INSTANCE_STOPPED, v63, (const struct _GUID *)((char *)v16 + 52), Uuid2);
          }
        }
        else
        {
          v27 = 4;
          ReportTaskEvent(v14, &STOPPING_OFF_IDLE, v63, (const struct _GUID *)((char *)v16 + 52));
          *((_BYTE *)v4 + 304) = 1;
        }
        v59[0] = 0;
        *((_OWORD *)v4 + 17) = 0;
        v28 = 0;
        RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
        CurrentThreadId = GetCurrentThreadId();
        v30 = (UUID *)g_leQueuedSerialActionsListHead;
        dword_18004FFA0 = CurrentThreadId;
        while ( v30 != (UUID *)&g_leQueuedSerialActionsListHead )
        {
          v46 = *(UUID **)&v30->Data1;
          if ( v16 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)-52LL
            && UuidEqual((UUID *)((char *)v16 + 52), v30 + 1, v59) )
          {
            v41 = *(UUID **)&v30->Data1;
            if ( *(UUID **)(*(_QWORD *)&v30->Data1 + 8LL) != v30 )
              goto LABEL_56;
            v42 = *(UUID ***)v30->Data4;
            if ( *v42 != v30 )
              goto LABEL_56;
            *v42 = v41;
            *(_QWORD *)v41->Data4 = v42;
            *(_QWORD *)v30->Data4 = v30;
            *(_QWORD *)&v30->Data1 = v30;
            UBPM_MIDL_user_free(v30, v47, v48, v49);
            v28 = 1;
          }
          v30 = v46;
        }
        dword_18004FFA0 = 0;
        RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          v50 = L"Removed";
          if ( !v28 )
            v50 = L"Not removed";
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            (_DWORD)v50,
            0);
        }
        v4 = v61;
        if ( *(_QWORD *)(*((_QWORD *)v61 + 3) + 48LL) )
        {
          RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
          dword_18004FFE8 = GetCurrentThreadId();
          UbpmpMaintenanceTaskStoppedCallout(v4, v16, v27);
          dword_18004FFE8 = 0;
          RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
        }
        UbpmQueueConsumerClose(*((void **)v16 + 13));
        v34 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v16;
        if ( *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(*(_QWORD *)v16 + 8LL) != v16
          || (v35 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v16 + 1), *v35 != v16) )
        {
LABEL_56:
          __fastfail(3u);
        }
        *v35 = v34;
        v17 = 1;
        *((_QWORD *)v34 + 1) = v35;
        *((_QWORD *)v16 + 1) = v16;
        *(_QWORD *)v16 = v16;
        UBPM_MIDL_user_free(v16, v31, v32, v33);
        v26 = v62;
        v7 = v60;
        v6 = v56;
      }
LABEL_30:
      v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_31:
      v16 = v26;
    }
    while ( v26 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)v15 );
  }
  v19 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)*((_QWORD *)v4 + 32);
  if ( v19 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v4 + 256) )
  {
    while ( 1 )
    {
      v36 = *((_DWORD *)v19 + 30);
      v37 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v19;
      if ( (v36 & 0x10001) == 0x10001 )
        break;
      if ( Uuid2 )
      {
        if ( UuidEqual((UUID *)((char *)v19 + 20), Uuid2, &Status) && !Status )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_40;
          WPP_SF_S_guid_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v51, (unsigned int)v63, (__int64)Uuid2, v6);
          goto LABEL_39;
        }
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v19 + 22) == v7 )
      {
        UbpmQueueConsumerClose(*((void **)v19 + 17));
        v38 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v19;
        if ( *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(*(_QWORD *)v19 + 8LL) != v19 )
          goto LABEL_56;
        v39 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v19 + 1);
        if ( *v39 != v19 )
          goto LABEL_56;
        *v39 = v38;
        *((_QWORD *)v38 + 1) = v39;
        *((_QWORD *)v19 + 1) = v19;
        *(_QWORD *)v19 = v19;
        UbpmTriggerConsumerPublishStateChange(v4);
        v17 = 1;
LABEL_39:
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_40:
      v19 = v37;
      if ( v37 == (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v4 + 256) )
        goto LABEL_9;
    }
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 )
      goto LABEL_40;
    WPP_SF_SL(
      (unsigned int)v14[2],
      16,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      (unsigned int)v63,
      v36);
    goto LABEL_39;
  }
LABEL_9:
  v20 = (UUID **)*((_QWORD *)v4 + 3);
  v21 = 0;
  v56 = 0;
  v22 = *v20;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  v23 = GetCurrentThreadId();
  v24 = (UUID *)g_leQueuedSerialActionsListHead;
  dword_18004FFA0 = v23;
  if ( g_leQueuedSerialActionsListHead != (_UNKNOWN *)&g_leQueuedSerialActionsListHead )
  {
    do
    {
      v52 = *(UUID **)&v24->Data1;
      if ( v22 && UuidEqual(v22, v24 + 2, &v56) && (!Uuid2 || !UuidEqual(Uuid2, v24 + 1, &v56)) )
      {
        v43 = *(UUID **)&v24->Data1;
        if ( *(UUID **)(*(_QWORD *)&v24->Data1 + 8LL) != v24 )
          goto LABEL_56;
        v44 = *(UUID ***)v24->Data4;
        if ( *v44 != v24 )
          goto LABEL_56;
        *v44 = v43;
        *(_QWORD *)v43->Data4 = v44;
        *(_QWORD *)v24->Data4 = v24;
        *(_QWORD *)&v24->Data1 = v24;
        UBPM_MIDL_user_free(v24, v53, v54, v55);
        v21 = 1;
      }
      v24 = v52;
    }
    while ( v52 != (UUID *)&g_leQueuedSerialActionsListHead );
    v4 = v61;
  }
  dword_18004FFA0 = 0;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    if ( !v21 )
      v18 = L"Not removed";
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      (_DWORD)v18,
      0);
  }
  if ( v17 )
    UbpmpTriggerConsumerReportResult(v4, 2147943467LL, 0);
}

```

## disassembly

```asm
0x180009a30  push    rbx
0x180009a32  push    rsi
0x180009a33  push    rdi
0x180009a34  push    r12
0x180009a36  push    r13
0x180009a38  push    r14
0x180009a3a  push    r15
0x180009a3c  sub     rsp, 270h
0x180009a43  mov     rax, cs:__security_cookie
0x180009a4a  xor     rax, rsp
0x180009a4d  mov     [rsp+2A8h+var_48], rax
0x180009a55  mov     r15, rcx
0x180009a58  mov     [rsp+2A8h+var_258], rcx
0x180009a5d  mov     rcx, [rcx+18h]
0x180009a61  mov     r13d, r8d
0x180009a64  mov     [rsp+2A8h+Status], 0
0x180009a6c  mov     r12d, edx
0x180009a6f  mov     [rsp+2A8h+Uuid2], r9
0x180009a74  mov     ebx, 7FFFFFFEh
0x180009a79  mov     [rsp+2A8h+var_278], r8d
0x180009a7e  mov     rcx, [rcx+8]; lpString1
0x180009a82  mov     [rsp+2A8h+var_260], edx
0x180009a86  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x180009a8b  mov     r8d, 100h
0x180009a91  lea     rdx, [rsp+2A8h+var_248]
0x180009a96  test    rbx, rbx
0x180009a99  jz      short loc_180009AB7
0x180009a9b  movzx   ecx, word ptr [rax]
0x180009a9e  test    cx, cx
0x180009aa1  jz      short loc_180009AB7
0x180009aa3  mov     [rdx], cx
0x180009aa6  add     rax, 2
0x180009aaa  add     rdx, 2
0x180009aae  dec     rbx
0x180009ab1  sub     r8, 1
0x180009ab5  jnz     short loc_180009A96
0x180009ab7  test    r8, r8
0x180009aba  mov     [rsp+2A8h+arg_8], rbp
0x180009ac2  lea     rcx, [rdx-2]
0x180009ac6  cmovnz  rcx, rdx
0x180009aca  xor     eax, eax
0x180009acc  mov     [rcx], ax
0x180009acf  mov     rcx, r15
0x180009ad2  call    UbpmpActionContextCleanup
0x180009ad7  mov     rcx, cs:WPP_GLOBAL_Control; void *
0x180009ade  lea     rbx, [r15+0E0h]
0x180009ae5  mov     rdi, [rbx]
0x180009ae8  lea     rdx, WPP_GLOBAL_Control
0x180009aef  xor     sil, sil
0x180009af2  lea     r14, aRemoved; "Removed"
0x180009af9  cmp     rdi, rbx
0x180009afc  jnz     loc_180009BE0
0x180009b02  lea     rbx, [r15+100h]
0x180009b09  mov     rdi, [rbx]
0x180009b0c  cmp     rdi, rbx
0x180009b0f  jnz     loc_180009D61
0x180009b15  mov     rax, [r15+18h]
0x180009b19  lea     rcx, g_QueuedSerialActionsLock
0x180009b20  xor     r13d, r13d
0x180009b23  xor     bpl, bpl
0x180009b26  mov     [rsp+2A8h+var_278], r13d
0x180009b2b  mov     rdi, [rax]
0x180009b2e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009b35  nop     dword ptr [rax+rax+00h]
0x180009b3a  call    cs:__imp_GetCurrentThreadId
0x180009b41  nop     dword ptr [rax+rax+00h]
0x180009b46  mov     rbx, cs:g_leQueuedSerialActionsListHead
0x180009b4d  lea     r12, g_leQueuedSerialActionsListHead
0x180009b54  mov     cs:dword_18004FFA0, eax
0x180009b5a  cmp     rbx, r12
0x180009b5d  jnz     loc_18000A193
0x180009b63  lea     rcx, g_QueuedSerialActionsLock
0x180009b6a  mov     cs:dword_18004FFA0, r13d
0x180009b71  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009b78  nop     dword ptr [rax+rax+00h]
0x180009b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b84  lea     rax, WPP_GLOBAL_Control
0x180009b8b  cmp     rcx, rax
0x180009b8e  jz      short loc_180009B9A
0x180009b90  test    byte ptr [rcx+1Ch], 20h
0x180009b94  jnz     loc_18000A1F7
0x180009b9a  test    sil, sil
0x180009b9d  jnz     short loc_180009BCB
0x180009b9f  mov     rbp, [rsp+2A8h+arg_8]
0x180009ba7  mov     rcx, [rsp+2A8h+var_48]
0x180009baf  xor     rcx, rsp; StackCookie
0x180009bb2  call    __security_check_cookie
0x180009bb7  add     rsp, 270h
0x180009bbe  pop     r15
0x180009bc0  pop     r14
0x180009bc2  pop     r13
0x180009bc4  pop     r12
0x180009bc6  pop     rdi
0x180009bc7  pop     rsi
0x180009bc8  pop     rbx
0x180009bc9  retn
0x180009bcb  xor     r8d, r8d
0x180009bce  mov     edx, 8007042Bh
0x180009bd3  mov     rcx, r15
0x180009bd6  call    UbpmpTriggerConsumerReportResult
0x180009bdb  jmp     short loc_180009B9F
0x180009be0  mov     r8d, [rdi+64h]
0x180009be4  mov     eax, r8d
0x180009be7  mov     rbp, [rdi]
0x180009bea  and     eax, 10001h
0x180009bef  mov     [rsp+2A8h+var_250], rbp
0x180009bf4  cmp     eax, 10001h
0x180009bf9  jz      loc_180009FC4
0x180009bff  mov     rax, [rsp+2A8h+Uuid2]
0x180009c04  test    rax, rax
0x180009c07  jnz     loc_180009FFB
0x180009c0d  cmp     r12d, 0FFFFh
0x180009c14  jnz     loc_180009EAF
0x180009c1a  cmp     rcx, rdx
0x180009c1d  jnz     loc_180009F23
0x180009c23  mov     rdx, [rdi+18h]
0x180009c27  cmp     dword ptr [rdx+10h], 1
0x180009c2b  jz      loc_180009DED
0x180009c31  test    r13b, 4
0x180009c35  jz      loc_180009EF5
0x180009c3b  lea     r9, [rdi+34h]; struct _GUID *
0x180009c3f  mov     r13b, 3
0x180009c42  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x180009c47  lea     rdx, STOPPING_ON_BATTERIES; struct _EVENT_DESCRIPTOR *
0x180009c4e  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180009c53  xorps   xmm0, xmm0
0x180009c56  mov     [rsp+2A8h+var_268], 0
0x180009c5e  movups  xmmword ptr [r15+110h], xmm0
0x180009c66  lea     rcx, g_QueuedSerialActionsLock
0x180009c6d  xor     r12b, r12b
0x180009c70  lea     r15, [rdi+34h]
0x180009c74  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009c7b  nop     dword ptr [rax+rax+00h]
0x180009c80  call    cs:__imp_GetCurrentThreadId
0x180009c87  nop     dword ptr [rax+rax+00h]
0x180009c8c  mov     rsi, cs:g_leQueuedSerialActionsListHead
0x180009c93  mov     cs:dword_18004FFA0, eax
0x180009c99  lea     rax, g_leQueuedSerialActionsListHead
0x180009ca0  cmp     rsi, rax
0x180009ca3  jnz     loc_18000A0B1
0x180009ca9  lea     rcx, g_QueuedSerialActionsLock
0x180009cb0  mov     cs:dword_18004FFA0, 0
0x180009cba  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009cc1  nop     dword ptr [rax+rax+00h]
0x180009cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ccd  lea     rax, WPP_GLOBAL_Control
0x180009cd4  cmp     rcx, rax
0x180009cd7  jz      short loc_180009CE3
0x180009cd9  test    byte ptr [rcx+1Ch], 20h
0x180009cdd  jnz     loc_18000A0E2
0x180009ce3  mov     r15, [rsp+2A8h+var_258]
0x180009ce8  mov     rax, [r15+18h]
0x180009cec  cmp     qword ptr [rax+30h], 0
0x180009cf1  jnz     loc_180009E37
0x180009cf7  mov     rcx, [rdi+68h]; void *
0x180009cfb  call    UbpmQueueConsumerClose
0x180009d00  mov     rcx, [rdi]
0x180009d03  cmp     [rcx+8], rdi
0x180009d07  jnz     loc_180009F53
0x180009d0d  mov     rax, [rdi+8]
0x180009d11  cmp     [rax], rdi
0x180009d14  jnz     loc_180009F53
0x180009d1a  mov     [rax], rcx
0x180009d1d  mov     sil, 1
0x180009d20  mov     [rcx+8], rax
0x180009d24  mov     rcx, rdi
0x180009d27  mov     [rdi+8], rdi
0x180009d2b  mov     [rdi], rdi
0x180009d2e  call    UBPM_MIDL_user_free
0x180009d33  mov     rbp, [rsp+2A8h+var_250]
0x180009d38  mov     r12d, [rsp+2A8h+var_260]
0x180009d3d  mov     r13d, [rsp+2A8h+var_278]
0x180009d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d49  lea     rdx, WPP_GLOBAL_Control
0x180009d50  mov     rdi, rbp
0x180009d53  cmp     rbp, rbx
0x180009d56  jz      loc_180009B02
0x180009d5c  jmp     loc_180009BE0
0x180009d61  mov     r8d, [rdi+78h]
0x180009d65  mov     eax, r8d
0x180009d68  mov     rbp, [rdi]
0x180009d6b  and     eax, 10001h
0x180009d70  cmp     eax, 10001h
0x180009d75  jz      loc_180009EBE
0x180009d7b  mov     rax, [rsp+2A8h+Uuid2]
0x180009d80  test    rax, rax
0x180009d83  jnz     loc_18000A115
0x180009d89  cmp     [rdi+58h], r12d
0x180009d8d  jnz     short loc_180009DDC
0x180009d8f  mov     rcx, [rdi+88h]; void *
0x180009d96  call    UbpmQueueConsumerClose
0x180009d9b  mov     rcx, [rdi]
0x180009d9e  cmp     [rcx+8], rdi
0x180009da2  jnz     loc_180009F53
0x180009da8  mov     rax, [rdi+8]
0x180009dac  cmp     [rax], rdi
0x180009daf  jnz     loc_180009F53
0x180009db5  mov     [rax], rcx
0x180009db8  mov     [rcx+8], rax
0x180009dbc  mov     rcx, r15
0x180009dbf  mov     [rdi+8], rdi
0x180009dc3  mov     [rdi], rdi
0x180009dc6  call    UbpmTriggerConsumerPublishStateChange
0x180009dcb  mov     sil, 1
0x180009dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dd5  lea     rdx, WPP_GLOBAL_Control
0x180009ddc  mov     rdi, rbp
0x180009ddf  cmp     rbp, rbx
0x180009de2  jz      loc_180009B15
0x180009de8  jmp     loc_180009D61
0x180009ded  mov     rsi, [rdi+20h]
0x180009df1  test    rsi, rsi
0x180009df4  jz      loc_180009E8D
0x180009dfa  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x180009dfd  call    UbpmpTerminateNonHostedTask
0x180009e02  test    eax, eax
0x180009e04  jz      loc_180009E8D
0x180009e0a  mov     r9d, 3
0x180009e10  lea     r8, [rdi+28h]
0x180009e14  xor     edx, edx
0x180009e16  mov     rcx, rsi
0x180009e19  call    UbpmpSendCommandGetResponse
0x180009e1e  mov     edx, 1
0x180009e23  mov     qword ptr [rsp+2A8h+var_268], rsi
0x180009e28  lea     rcx, [rsp+2A8h+var_268]
0x180009e2d  call    UbpmpDecrementRefAndDelete
0x180009e32  jmp     loc_180009C31
0x180009e37  lea     rcx, g_MaintenanceLaunchLock
0x180009e3e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009e45  nop     dword ptr [rax+rax+00h]
0x180009e4a  call    cs:__imp_GetCurrentThreadId
0x180009e51  nop     dword ptr [rax+rax+00h]
0x180009e56  movzx   r8d, r13b
0x180009e5a  mov     rdx, rdi
0x180009e5d  mov     rcx, r15
0x180009e60  mov     cs:dword_18004FFE8, eax
0x180009e66  call    UbpmpMaintenanceTaskStoppedCallout
0x180009e6b  lea     rcx, g_MaintenanceLaunchLock
0x180009e72  mov     cs:dword_18004FFE8, 0
0x180009e7c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009e83  nop     dword ptr [rax+rax+00h]
0x180009e88  jmp     loc_180009CF7
0x180009e8d  mov     qword ptr [rsp+2A8h+var_268], rsi
0x180009e92  test    rsi, rsi
0x180009e95  jz      loc_180009C31
0x180009e9b  mov     edx, 1
0x180009ea0  lea     rcx, [rsp+2A8h+var_268]
0x180009ea5  call    UbpmpDecrementRefAndDelete
0x180009eaa  jmp     loc_180009C31
0x180009eaf  cmp     [rdi+60h], r12d
0x180009eb3  jz      loc_180009C1A
0x180009eb9  jmp     loc_180009D50
0x180009ebe  cmp     rcx, rdx
0x180009ec1  jz      loc_180009DDC
0x180009ec7  test    byte ptr [rcx+1Ch], 4
0x180009ecb  jz      loc_180009DDC
0x180009ed1  mov     rcx, [rcx+10h]
0x180009ed5  lea     r9, [rsp+2A8h+var_248]
0x180009eda  mov     dword ptr [rsp+2A8h+var_288], r8d
0x180009edf  mov     edx, 10h
0x180009ee4  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180009eeb  call    WPP_SF_SL
0x180009ef0  jmp     loc_180009DCE
0x180009ef5  test    r13b, r13b
0x180009ef8  jns     loc_18000A079
0x180009efe  lea     r9, [rdi+34h]; struct _GUID *
0x180009f02  mov     r13b, 4
0x180009f05  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x180009f0a  lea     rdx, STOPPING_OFF_IDLE; struct _EVENT_DESCRIPTOR *
0x180009f11  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180009f16  mov     byte ptr [r15+130h], 1
0x180009f1e  jmp     loc_180009C53
0x180009f23  test    byte ptr [rcx+1Ch], 4
0x180009f27  jz      loc_180009C23
0x180009f2d  mov     eax, [rdi+60h]
0x180009f30  lea     r9, [rsp+2A8h+var_248]
0x180009f35  mov     rcx, [rcx+10h]
0x180009f39  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180009f40  mov     edx, 0Fh
0x180009f45  mov     dword ptr [rsp+2A8h+var_288], eax
0x180009f49  call    WPP_SF_Sd
0x180009f4e  jmp     loc_180009C23
0x180009f53  mov     ecx, 3
0x180009f58  int     29h; Win8: RtlFailFast(ecx)
0x180009f5a  mov     rcx, [rsi]
0x180009f5d  cmp     [rcx+8], rsi
0x180009f61  jnz     short loc_180009F53
0x180009f63  mov     rax, [rsi+8]
0x180009f67  cmp     [rax], rsi
0x180009f6a  jnz     short loc_180009F53
0x180009f6c  mov     [rax], rcx
0x180009f6f  mov     [rcx+8], rax
0x180009f73  mov     rcx, rsi
0x180009f76  mov     [rsi+8], rsi
0x180009f7a  mov     [rsi], rsi
0x180009f7d  call    UBPM_MIDL_user_free
0x180009f82  mov     r12b, 1
0x180009f85  lea     rax, g_leQueuedSerialActionsListHead
0x180009f8c  mov     rsi, rbp
0x180009f8f  jmp     loc_180009CA0
  ... truncated ...
```
