# UbpmpActionTerminatesOnConstraintLocked(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,_GUID *)

- ea: `0x180008f30`
- end: `0x1800096ce`
- name: `?UbpmpActionTerminatesOnConstraintLocked@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAU_GUID@@@Z`
- size: `1950`
- prototype: `void __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, unsigned int, unsigned int, struct _GUID *)`
- caller_count: `4`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009fb8`
- `0x180019dc0`
- `0x18001c400`
- `0x18002b880`

## callees

- `0x1800049b4`
- `0x180004e10`
- `0x180005ed0`
- `0x180007990`
- `0x180008f30`
- `0x1800096e0`
- `0x180009750`
- `0x18000a03c`
- `0x18000e660`
- `0x180017e88`
- `0x180019d90`
- `0x18001e9f4`
- `0x18001f010`
- `0x18002eb98`
- `0x180034ec4`
- `0x180035e28`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000902e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009164`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009315`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000902e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009164`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009315`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009065`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000919e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009347`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009065`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000919e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000916a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000931b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000916a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000931b`
- `RPCRT4!UuidEqual` at `0x1800094cc`
- `RPCRT4!UuidEqual` at `0x180009588`
- `RPCRT4!UuidEqual` at `0x1800095da`
- `RPCRT4!UuidEqual` at `0x18000965a`
- `RPCRT4!UuidEqual` at `0x18000967e`
- `RPCRT4!UuidEqual` at `0x1800094cc`
- `RPCRT4!UuidEqual` at `0x180009588`
- `RPCRT4!UuidEqual` at `0x1800095da`
- `RPCRT4!UuidEqual` at `0x18000965a`
- `RPCRT4!UuidEqual` at `0x18000967e`

## string_xrefs

- `0x180008ff2`: `Removed`
- `0x18000959f`: `Not removed`
- `0x1800096a2`: `Not removed`

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
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v31; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v32; // rax
  int v33; // r8d
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v34; // rbp
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v35; // rcx
  struct _UBPM_TRIGGER_CONSUMER_BLOCK **v36; // rax
  __int64 v37; // rsi
  UUID *v38; // rcx
  UUID **v39; // rax
  UUID *v40; // rax
  UUID **v41; // rcx
  int v42; // r8d
  UUID *v43; // rbp
  const wchar_t *v44; // r9
  int v45; // r8d
  UUID *v46; // r15
  RPC_STATUS v47; // [rsp+30h] [rbp-278h] BYREF
  RPC_STATUS Status; // [rsp+34h] [rbp-274h] BYREF
  UUID *Uuid2; // [rsp+38h] [rbp-270h]
  RPC_STATUS v50[2]; // [rsp+40h] [rbp-268h] BYREF
  int v51; // [rsp+48h] [rbp-260h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v52; // [rsp+50h] [rbp-258h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v53; // [rsp+58h] [rbp-250h]
  unsigned __int16 v54[256]; // [rsp+60h] [rbp-248h] BYREF

  v4 = a1;
  v52 = a1;
  v5 = *((_QWORD *)a1 + 3);
  v6 = a3;
  Status = 0;
  v7 = a2;
  Uuid2 = a4;
  v8 = 2147483646;
  v47 = a3;
  v9 = *(const WCHAR **)(v5 + 8);
  v51 = a2;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(v9);
  v11 = 256;
  v12 = v54;
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
      v53 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v16;
      if ( (v25 & 0x10001) == 0x10001 )
      {
        if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 )
          goto LABEL_31;
        WPP_SF_SL(
          (unsigned int)v14[2],
          13,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          (unsigned int)v54,
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
            WPP_SF_S_guid_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v42, (unsigned int)v54, (__int64)Uuid2, v6);
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
            (unsigned int)v54,
            *((_DWORD *)v16 + 24));
        if ( *(_DWORD *)(*((_QWORD *)v16 + 3) + 16LL) == 1 )
        {
          v37 = *((_QWORD *)v16 + 4);
          if ( v37 && (unsigned int)UbpmpTerminateNonHostedTask(*((struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)v16 + 4)) )
          {
            UbpmpSendCommandGetResponse(v37, 0, (_QWORD *)v16 + 5, 3u);
            *(_QWORD *)v50 = v37;
            UbpmpDecrementRefAndDelete(v50, 1);
          }
          else
          {
            *(_QWORD *)v50 = v37;
            if ( v37 )
              UbpmpDecrementRefAndDelete(v50, 1);
          }
        }
        if ( (v6 & 4) != 0 )
        {
          v27 = 3;
          ReportTaskEvent(v14, &STOPPING_ON_BATTERIES, v54, (const struct _GUID *)((char *)v16 + 52));
        }
        else if ( v6 >= 0 )
        {
          v27 = 0;
          if ( (v47 & 0x10000) != 0 )
          {
            v27 = 5;
            ReportTaskEvent(v14, &RUNNING_INSTANCE_STOPPED, v54, (const struct _GUID *)((char *)v16 + 52), Uuid2);
          }
        }
        else
        {
          v27 = 4;
          ReportTaskEvent(v14, &STOPPING_OFF_IDLE, v54, (const struct _GUID *)((char *)v16 + 52));
          *((_BYTE *)v4 + 304) = 1;
        }
        v50[0] = 0;
        *((_OWORD *)v4 + 17) = 0;
        v28 = 0;
        RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
        CurrentThreadId = GetCurrentThreadId();
        v30 = (UUID *)g_leQueuedSerialActionsListHead;
        dword_18004CEA0 = CurrentThreadId;
        while ( v30 != (UUID *)&g_leQueuedSerialActionsListHead )
        {
          v43 = *(UUID **)&v30->Data1;
          if ( v16 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)-52LL
            && UuidEqual((UUID *)((char *)v16 + 52), v30 + 1, v50) )
          {
            v38 = *(UUID **)&v30->Data1;
            if ( *(UUID **)(*(_QWORD *)&v30->Data1 + 8LL) != v30 )
              goto LABEL_56;
            v39 = *(UUID ***)v30->Data4;
            if ( *v39 != v30 )
              goto LABEL_56;
            *v39 = v38;
            *(_QWORD *)v38->Data4 = v39;
            *(_QWORD *)v30->Data4 = v30;
            *(_QWORD *)&v30->Data1 = v30;
            UBPM_MIDL_user_free(v30);
            v28 = 1;
          }
          v30 = v43;
        }
        dword_18004CEA0 = 0;
        RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          v44 = L"Removed";
          if ( !v28 )
            v44 = L"Not removed";
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            (_DWORD)v44,
            0);
        }
        v4 = v52;
        if ( *(_QWORD *)(*((_QWORD *)v52 + 3) + 48LL) )
        {
          RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
          dword_18004CEE8 = GetCurrentThreadId();
          UbpmpMaintenanceTaskStoppedCallout(v4, v16, v27);
          dword_18004CEE8 = 0;
          RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
        }
        UbpmQueueConsumerClose(*((void **)v16 + 13));
        v31 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v16;
        if ( *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(*(_QWORD *)v16 + 8LL) != v16
          || (v32 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v16 + 1), *v32 != v16) )
        {
LABEL_56:
          __fastfail(3u);
        }
        *v32 = v31;
        v17 = 1;
        *((_QWORD *)v31 + 1) = v32;
        *((_QWORD *)v16 + 1) = v16;
        *(_QWORD *)v16 = v16;
        UBPM_MIDL_user_free(v16);
        v26 = v53;
        v7 = v51;
        v6 = v47;
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
      v33 = *((_DWORD *)v19 + 30);
      v34 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v19;
      if ( (v33 & 0x10001) == 0x10001 )
        break;
      if ( Uuid2 )
      {
        if ( UuidEqual((UUID *)((char *)v19 + 20), Uuid2, &Status) && !Status )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_40;
          WPP_SF_S_guid_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v45, (unsigned int)v54, (__int64)Uuid2, v6);
          goto LABEL_39;
        }
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v19 + 22) == v7 )
      {
        UbpmQueueConsumerClose(*((void **)v19 + 17));
        v35 = *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)v19;
        if ( *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)(*(_QWORD *)v19 + 8LL) != v19 )
          goto LABEL_56;
        v36 = (struct _UBPM_TRIGGER_CONSUMER_BLOCK **)*((_QWORD *)v19 + 1);
        if ( *v36 != v19 )
          goto LABEL_56;
        *v36 = v35;
        *((_QWORD *)v35 + 1) = v36;
        *((_QWORD *)v19 + 1) = v19;
        *(_QWORD *)v19 = v19;
        UbpmTriggerConsumerPublishStateChange(v4);
        v17 = 1;
LABEL_39:
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_40:
      v19 = v34;
      if ( v34 == (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v4 + 256) )
        goto LABEL_9;
    }
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 )
      goto LABEL_40;
    WPP_SF_SL(
      (unsigned int)v14[2],
      16,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      (unsigned int)v54,
      v33);
    goto LABEL_39;
  }
LABEL_9:
  v20 = (UUID **)*((_QWORD *)v4 + 3);
  v21 = 0;
  v47 = 0;
  v22 = *v20;
  RtlAcquireSRWLockExclusive(&g_QueuedSerialActionsLock);
  v23 = GetCurrentThreadId();
  v24 = (UUID *)g_leQueuedSerialActionsListHead;
  dword_18004CEA0 = v23;
  if ( g_leQueuedSerialActionsListHead != (_UNKNOWN *)&g_leQueuedSerialActionsListHead )
  {
    do
    {
      v46 = *(UUID **)&v24->Data1;
      if ( v22 && UuidEqual(v22, v24 + 2, &v47) && (!Uuid2 || !UuidEqual(Uuid2, v24 + 1, &v47)) )
      {
        v40 = *(UUID **)&v24->Data1;
        if ( *(UUID **)(*(_QWORD *)&v24->Data1 + 8LL) != v24 )
          goto LABEL_56;
        v41 = *(UUID ***)v24->Data4;
        if ( *v41 != v24 )
          goto LABEL_56;
        *v41 = v40;
        *(_QWORD *)v40->Data4 = v41;
        *(_QWORD *)v24->Data4 = v24;
        *(_QWORD *)&v24->Data1 = v24;
        UBPM_MIDL_user_free(v24);
        v21 = 1;
      }
      v24 = v46;
    }
    while ( v46 != (UUID *)&g_leQueuedSerialActionsListHead );
    v4 = v52;
  }
  dword_18004CEA0 = 0;
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
0x180008f30  push    rbx
0x180008f32  push    rsi
0x180008f33  push    rdi
0x180008f34  push    r12
0x180008f36  push    r13
0x180008f38  push    r14
0x180008f3a  push    r15
0x180008f3c  sub     rsp, 270h
0x180008f43  mov     rax, cs:__security_cookie
0x180008f4a  xor     rax, rsp
0x180008f4d  mov     [rsp+2A8h+var_48], rax
0x180008f55  mov     r15, rcx
0x180008f58  mov     [rsp+2A8h+var_258], rcx
0x180008f5d  mov     rcx, [rcx+18h]
0x180008f61  mov     r13d, r8d
0x180008f64  mov     [rsp+2A8h+Status], 0
0x180008f6c  mov     r12d, edx
0x180008f6f  mov     [rsp+2A8h+Uuid2], r9
0x180008f74  mov     ebx, 7FFFFFFEh
0x180008f79  mov     [rsp+2A8h+var_278], r8d
0x180008f7e  mov     rcx, [rcx+8]; lpString1
0x180008f82  mov     [rsp+2A8h+var_260], edx
0x180008f86  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x180008f8b  mov     r8d, 100h
0x180008f91  lea     rdx, [rsp+2A8h+var_248]
0x180008f96  test    rbx, rbx
0x180008f99  jz      short loc_180008FB7
0x180008f9b  movzx   ecx, word ptr [rax]
0x180008f9e  test    cx, cx
0x180008fa1  jz      short loc_180008FB7
0x180008fa3  mov     [rdx], cx
0x180008fa6  add     rax, 2
0x180008faa  add     rdx, 2
0x180008fae  dec     rbx
0x180008fb1  sub     r8, 1
0x180008fb5  jnz     short loc_180008F96
0x180008fb7  test    r8, r8
0x180008fba  mov     [rsp+2A8h+arg_8], rbp
0x180008fc2  lea     rcx, [rdx-2]
0x180008fc6  cmovnz  rcx, rdx
0x180008fca  xor     eax, eax
0x180008fcc  mov     [rcx], ax
0x180008fcf  mov     rcx, r15
0x180008fd2  call    UbpmpActionContextCleanup
0x180008fd7  mov     rcx, cs:WPP_GLOBAL_Control; void *
0x180008fde  lea     rbx, [r15+0E0h]
0x180008fe5  mov     rdi, [rbx]
0x180008fe8  lea     rdx, WPP_GLOBAL_Control
0x180008fef  xor     sil, sil
0x180008ff2  lea     r14, aRemoved; "Removed"
0x180008ff9  cmp     rdi, rbx
0x180008ffc  jnz     loc_1800090D0
0x180009002  lea     rbx, [r15+100h]
0x180009009  mov     rdi, [rbx]
0x18000900c  cmp     rdi, rbx
0x18000900f  jnz     loc_180009240
0x180009015  mov     rax, [r15+18h]
0x180009019  lea     rcx, g_QueuedSerialActionsLock
0x180009020  xor     r13d, r13d
0x180009023  xor     bpl, bpl
0x180009026  mov     [rsp+2A8h+var_278], r13d
0x18000902b  mov     rdi, [rax]
0x18000902e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009034  call    cs:__imp_GetCurrentThreadId
0x18000903a  mov     rbx, cs:g_leQueuedSerialActionsListHead
0x180009041  lea     r12, g_leQueuedSerialActionsListHead
0x180009048  mov     cs:dword_18004CEA0, eax
0x18000904e  cmp     rbx, r12
0x180009051  jnz     loc_180009646
0x180009057  lea     rcx, g_QueuedSerialActionsLock
0x18000905e  mov     cs:dword_18004CEA0, r13d
0x180009065  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000906b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009072  lea     rax, WPP_GLOBAL_Control
0x180009079  cmp     rcx, rax
0x18000907c  jz      short loc_180009088
0x18000907e  test    byte ptr [rcx+1Ch], 20h
0x180009082  jnz     loc_18000969E
0x180009088  test    sil, sil
0x18000908b  jnz     short loc_1800090B8
0x18000908d  mov     rbp, [rsp+2A8h+arg_8]
0x180009095  mov     rcx, [rsp+2A8h+var_48]
0x18000909d  xor     rcx, rsp; StackCookie
0x1800090a0  call    __security_check_cookie
0x1800090a5  add     rsp, 270h
0x1800090ac  pop     r15
0x1800090ae  pop     r14
0x1800090b0  pop     r13
0x1800090b2  pop     r12
0x1800090b4  pop     rdi
0x1800090b5  pop     rsi
0x1800090b6  pop     rbx
0x1800090b7  retn
0x1800090b8  xor     r8d, r8d
0x1800090bb  mov     edx, 8007042Bh
0x1800090c0  mov     rcx, r15
0x1800090c3  call    UbpmpTriggerConsumerReportResult
0x1800090c8  jmp     short loc_18000908D
0x1800090d0  mov     r8d, [rdi+64h]
0x1800090d4  mov     eax, r8d
0x1800090d7  mov     rbp, [rdi]
0x1800090da  and     eax, 10001h
0x1800090df  mov     [rsp+2A8h+var_250], rbp
0x1800090e4  cmp     eax, 10001h
0x1800090e9  jz      loc_180009489
0x1800090ef  mov     rax, [rsp+2A8h+Uuid2]
0x1800090f4  test    rax, rax
0x1800090f7  jnz     loc_1800094C0
0x1800090fd  cmp     r12d, 0FFFFh
0x180009104  jnz     loc_180009374
0x18000910a  cmp     rcx, rdx
0x18000910d  jnz     loc_1800093E8
0x180009113  mov     rdx, [rdi+18h]
0x180009117  cmp     dword ptr [rdx+10h], 1
0x18000911b  jz      loc_1800092CC
0x180009121  test    r13b, 4
0x180009125  jz      loc_1800093BA
0x18000912b  lea     r9, [rdi+34h]; struct _GUID *
0x18000912f  mov     r13b, 3
0x180009132  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x180009137  lea     rdx, STOPPING_ON_BATTERIES; struct _EVENT_DESCRIPTOR *
0x18000913e  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x180009143  xorps   xmm0, xmm0
0x180009146  mov     [rsp+2A8h+var_268], 0
0x18000914e  movups  xmmword ptr [r15+110h], xmm0
0x180009156  lea     rcx, g_QueuedSerialActionsLock
0x18000915d  xor     r12b, r12b
0x180009160  lea     r15, [rdi+34h]
0x180009164  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000916a  call    cs:__imp_GetCurrentThreadId
0x180009170  mov     rsi, cs:g_leQueuedSerialActionsListHead
0x180009177  mov     cs:dword_18004CEA0, eax
0x18000917d  lea     rax, g_leQueuedSerialActionsListHead
0x180009184  cmp     rsi, rax
0x180009187  jnz     loc_180009570
0x18000918d  lea     rcx, g_QueuedSerialActionsLock
0x180009194  mov     cs:dword_18004CEA0, 0
0x18000919e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800091a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091ab  lea     rax, WPP_GLOBAL_Control
0x1800091b2  cmp     rcx, rax
0x1800091b5  jz      short loc_1800091C1
0x1800091b7  test    byte ptr [rcx+1Ch], 20h
0x1800091bb  jnz     loc_18000959B
0x1800091c1  mov     r15, [rsp+2A8h+var_258]
0x1800091c6  mov     rax, [r15+18h]
0x1800091ca  cmp     qword ptr [rax+30h], 0
0x1800091cf  jnz     loc_18000930E
0x1800091d5  mov     rcx, [rdi+68h]; void *
0x1800091d9  call    UbpmQueueConsumerClose
0x1800091de  mov     rcx, [rdi]
0x1800091e1  cmp     [rcx+8], rdi
0x1800091e5  jnz     loc_180009418
0x1800091eb  mov     rax, [rdi+8]
0x1800091ef  cmp     [rax], rdi
0x1800091f2  jnz     loc_180009418
0x1800091f8  mov     [rax], rcx
0x1800091fb  mov     sil, 1
0x1800091fe  mov     [rcx+8], rax
0x180009202  mov     rcx, rdi
0x180009205  mov     [rdi+8], rdi
0x180009209  mov     [rdi], rdi
0x18000920c  call    UBPM_MIDL_user_free
0x180009211  mov     rbp, [rsp+2A8h+var_250]
0x180009216  mov     r12d, [rsp+2A8h+var_260]
0x18000921b  mov     r13d, [rsp+2A8h+var_278]
0x180009220  mov     rcx, cs:WPP_GLOBAL_Control
0x180009227  lea     rdx, WPP_GLOBAL_Control
0x18000922e  mov     rdi, rbp
0x180009231  cmp     rbp, rbx
0x180009234  jz      loc_180009002
0x18000923a  jmp     loc_1800090D0
0x180009240  mov     r8d, [rdi+78h]
0x180009244  mov     eax, r8d
0x180009247  mov     rbp, [rdi]
0x18000924a  and     eax, 10001h
0x18000924f  cmp     eax, 10001h
0x180009254  jz      loc_180009383
0x18000925a  mov     rax, [rsp+2A8h+Uuid2]
0x18000925f  test    rax, rax
0x180009262  jnz     loc_1800095CE
0x180009268  cmp     [rdi+58h], r12d
0x18000926c  jnz     short loc_1800092BB
0x18000926e  mov     rcx, [rdi+88h]; void *
0x180009275  call    UbpmQueueConsumerClose
0x18000927a  mov     rcx, [rdi]
0x18000927d  cmp     [rcx+8], rdi
0x180009281  jnz     loc_180009418
0x180009287  mov     rax, [rdi+8]
0x18000928b  cmp     [rax], rdi
0x18000928e  jnz     loc_180009418
0x180009294  mov     [rax], rcx
0x180009297  mov     [rcx+8], rax
0x18000929b  mov     rcx, r15
0x18000929e  mov     [rdi+8], rdi
0x1800092a2  mov     [rdi], rdi
0x1800092a5  call    UbpmTriggerConsumerPublishStateChange
0x1800092aa  mov     sil, 1
0x1800092ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092b4  lea     rdx, WPP_GLOBAL_Control
0x1800092bb  mov     rdi, rbp
0x1800092be  cmp     rbp, rbx
0x1800092c1  jz      loc_180009015
0x1800092c7  jmp     loc_180009240
0x1800092cc  mov     rsi, [rdi+20h]
0x1800092d0  test    rsi, rsi
0x1800092d3  jz      short loc_180009352
0x1800092d5  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x1800092d8  call    UbpmpTerminateNonHostedTask
0x1800092dd  test    eax, eax
0x1800092df  jz      short loc_180009352
0x1800092e1  mov     r9d, 3
0x1800092e7  lea     r8, [rdi+28h]
0x1800092eb  xor     edx, edx
0x1800092ed  mov     rcx, rsi
0x1800092f0  call    UbpmpSendCommandGetResponse
0x1800092f5  mov     edx, 1
0x1800092fa  mov     qword ptr [rsp+2A8h+var_268], rsi
0x1800092ff  lea     rcx, [rsp+2A8h+var_268]
0x180009304  call    UbpmpDecrementRefAndDelete
0x180009309  jmp     loc_180009121
0x18000930e  lea     rcx, g_MaintenanceLaunchLock
0x180009315  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000931b  call    cs:__imp_GetCurrentThreadId
0x180009321  movzx   r8d, r13b
0x180009325  mov     rdx, rdi
0x180009328  mov     rcx, r15
0x18000932b  mov     cs:dword_18004CEE8, eax
0x180009331  call    UbpmpMaintenanceTaskStoppedCallout
0x180009336  lea     rcx, g_MaintenanceLaunchLock
0x18000933d  mov     cs:dword_18004CEE8, 0
0x180009347  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000934d  jmp     loc_1800091D5
0x180009352  mov     qword ptr [rsp+2A8h+var_268], rsi
0x180009357  test    rsi, rsi
0x18000935a  jz      loc_180009121
0x180009360  mov     edx, 1
0x180009365  lea     rcx, [rsp+2A8h+var_268]
0x18000936a  call    UbpmpDecrementRefAndDelete
0x18000936f  jmp     loc_180009121
0x180009374  cmp     [rdi+60h], r12d
0x180009378  jz      loc_18000910A
0x18000937e  jmp     loc_18000922E
0x180009383  cmp     rcx, rdx
0x180009386  jz      loc_1800092BB
0x18000938c  test    byte ptr [rcx+1Ch], 4
0x180009390  jz      loc_1800092BB
0x180009396  mov     rcx, [rcx+10h]
0x18000939a  lea     r9, [rsp+2A8h+var_248]
0x18000939f  mov     dword ptr [rsp+2A8h+var_288], r8d
0x1800093a4  mov     edx, 10h
0x1800093a9  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x1800093b0  call    WPP_SF_SL
0x1800093b5  jmp     loc_1800092AD
0x1800093ba  test    r13b, r13b
0x1800093bd  jns     loc_180009538
0x1800093c3  lea     r9, [rdi+34h]; struct _GUID *
0x1800093c7  mov     r13b, 4
0x1800093ca  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x1800093cf  lea     rdx, STOPPING_OFF_IDLE; struct _EVENT_DESCRIPTOR *
0x1800093d6  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x1800093db  mov     byte ptr [r15+130h], 1
0x1800093e3  jmp     loc_180009143
0x1800093e8  test    byte ptr [rcx+1Ch], 4
0x1800093ec  jz      loc_180009113
0x1800093f2  mov     eax, [rdi+60h]
0x1800093f5  lea     r9, [rsp+2A8h+var_248]
0x1800093fa  mov     rcx, [rcx+10h]
0x1800093fe  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180009405  mov     edx, 0Fh
0x18000940a  mov     dword ptr [rsp+2A8h+var_288], eax
0x18000940e  call    WPP_SF_Sd
0x180009413  jmp     loc_180009113
0x180009418  mov     ecx, 3
0x18000941d  int     29h; Win8: RtlFailFast(ecx)
0x18000941f  mov     rcx, [rsi]
0x180009422  cmp     [rcx+8], rsi
0x180009426  jnz     short loc_180009418
0x180009428  mov     rax, [rsi+8]
0x18000942c  cmp     [rax], rsi
0x18000942f  jnz     short loc_180009418
0x180009431  mov     [rax], rcx
0x180009434  mov     [rcx+8], rax
0x180009438  mov     rcx, rsi
0x18000943b  mov     [rsi+8], rsi
0x18000943f  mov     [rsi], rsi
0x180009442  call    UBPM_MIDL_user_free
0x180009447  mov     r12b, 1
0x18000944a  lea     rax, g_leQueuedSerialActionsListHead
0x180009451  mov     rsi, rbp
0x180009454  jmp     loc_180009184
0x180009459  mov     rax, [rbx]
0x18000945c  cmp     [rax+8], rbx
0x180009460  jnz     short loc_180009418
0x180009462  mov     rcx, [rbx+8]
0x180009466  cmp     [rcx], rbx
0x180009469  jnz     short loc_180009418
0x18000946b  mov     [rcx], rax
0x18000946e  mov     [rax+8], rcx
0x180009472  mov     rcx, rbx
  ... truncated ...
```
