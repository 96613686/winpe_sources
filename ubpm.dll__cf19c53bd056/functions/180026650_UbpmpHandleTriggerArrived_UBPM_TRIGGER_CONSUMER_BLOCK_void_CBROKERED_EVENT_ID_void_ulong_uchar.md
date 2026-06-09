# UbpmpHandleTriggerArrived(_UBPM_TRIGGER_CONSUMER_BLOCK *,void *,_CBROKERED_EVENT_ID,void *,ulong,uchar)

- ea: `0x180026650`
- end: `0x180026f39`
- name: `?UbpmpHandleTriggerArrived@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAXU_CBROKERED_EVENT_ID@@1KE@Z`
- size: `2281`
- prototype: `ULONG __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, __int64, __int64, __int64, unsigned int, char)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800265f0`
- `0x180026620`

## callees

- `0x180004058`
- `0x180007c50`
- `0x180007e30`
- `0x180013244`
- `0x18001e9f4`
- `0x180026650`
- `0x18002c480`
- `0x180032dd8`
- `0x180035764`
- `0x18003d7c6`
- `0x18003d810`
- `0x18003e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800268d5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026980`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026b43`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800268d5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026980`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180026b43`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ab3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ac9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ba0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ab3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ac9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026ba0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026774`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026e6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026f0c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026774`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026e6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026f0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800268db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800268db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026848`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026848`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026cf2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026cf2`

## pseudocode

```c
ULONG __fastcall UbpmpHandleTriggerArrived(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        char a6)
{
  char *v6; // r14
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v9; // rsi
  unsigned __int16 v10; // r15
  __int64 v11; // r12
  int *v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  int v16; // eax
  int v17; // r13d
  __int64 v18; // r14
  unsigned int v19; // ebx
  int v20; // esi
  HRESULT v21; // edi
  struct _UBPM_REPETITION_CONTEXT *v22; // r9
  char *v23; // r13
  unsigned int v24; // edx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  struct _UBPM_REPETITION_CONTEXT *v28; // rcx
  int v29; // eax
  unsigned int v30; // eax
  char *v31; // r10
  unsigned int v32; // edx
  __int64 v33; // rbx
  signed __int64 v34; // rdi
  DWORD CurrentThreadId; // eax
  void *v36; // r13
  __int64 v37; // rcx
  int v38; // eax
  int v39; // r8d
  unsigned int v40; // eax
  const WCHAR *v41; // rdi
  const WCHAR *v42; // r14
  __int64 v43; // rsi
  __int64 v44; // rbx
  __int64 v45; // r9
  int v46; // eax
  __int64 v47; // rax
  char *v48; // rbx
  ULONG result; // eax
  __int64 v50; // rax
  int *v51; // rcx
  int v52; // eax
  __int64 v53; // rax
  int *v54; // rcx
  __int64 v55; // rax
  int v56; // eax
  int v57; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v58; // [rsp+44h] [rbp-95h] BYREF
  char *v59; // [rsp+48h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR v60; // [rsp+50h] [rbp-89h] BYREF
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v61; // [rsp+60h] [rbp-79h]
  struct _UBPM_REPETITION_CONTEXT *v62; // [rsp+68h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-49h] BYREF
  __int16 *v66; // [rsp+A0h] [rbp-39h]
  int v67; // [rsp+A8h] [rbp-31h]
  int v68; // [rsp+ACh] [rbp-2Dh]
  int *v69; // [rsp+B0h] [rbp-29h]
  int v70; // [rsp+B8h] [rbp-21h]
  int v71; // [rsp+BCh] [rbp-1Dh]
  int *v72; // [rsp+C0h] [rbp-19h]
  __int64 v73; // [rsp+C8h] [rbp-11h]
  unsigned int *v74; // [rsp+D0h] [rbp-9h]
  __int64 v75; // [rsp+D8h] [rbp-1h]

  v6 = (char *)a1 + 24;
  v61 = a1;
  v59 = (char *)a1 + 24;
  v62 = 0;
  *(_QWORD *)&v60.Id = a4;
  v9 = a1;
  v10 = -1;
  v11 = -1;
  if ( (unsigned int)dword_18004C0F0 <= 4 )
  {
    v59 = (char *)a1 + 24;
  }
  else
  {
    v12 = *(int **)(*(_QWORD *)v6 + 8LL);
    if ( v12 )
    {
      v13 = -1;
      do
        v14 = *((_WORD *)v12 + ++v13) == 0;
      while ( !v14 );
      v15 = 2 * v13 + 2;
    }
    else
    {
      v12 = &dword_1800405F4;
      v15 = 2;
    }
    v70 = v15;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v69 = v12;
    v71 = 0;
    EventDescriptor.Keyword = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v66 = (__int16 *)byte_180043113;
    UserData.Reserved = 2;
    v67 = 29;
    v68 = 1;
    v58 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v16 = UbpmConsumerIncPendingActions(v9);
  v57 = v16;
  if ( !v16 )
  {
    if ( a4 && a5 < 0x14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
          87);
      v17 = 87;
      UbpmConsumerDecPendingActions(v9);
      v6 = v59;
      goto LABEL_81;
    }
    v18 = *(_QWORD *)v6;
    v19 = 0;
    EventDescriptor = 0;
    if ( memcmp_0(&EventDescriptor, (const void *)(v18 + 84), 0x10u) )
    {
      v58 = 0;
      ppv = 0;
      *(_QWORD *)&EventDescriptor.Id = 0;
      v20 = 0;
      v21 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
      if ( v21 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(LPVOID, __int64, EVENT_DESCRIPTOR *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                v18 + 84,
                &EventDescriptor);
        if ( v21 >= 0 )
        {
          v21 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)&EventDescriptor.Id + 96LL))(
                  *(_QWORD *)&EventDescriptor.Id,
                  &v58);
          if ( v21 >= 0 )
          {
            v21 = 0;
            v20 = v58 & 1;
          }
        }
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( *(_QWORD *)&EventDescriptor.Id )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
      if ( v21 >= 0 )
        LOBYTE(v19) = v20 != 0;
      v9 = v61;
    }
    v58 = v19;
    RtlAcquireSRWLockExclusive((char *)v9 + 48);
    *((_DWORD *)v9 + 14) = GetCurrentThreadId();
    if ( (*((_BYTE *)v9 + 41) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
          0);
      v17 = 1223;
      goto LABEL_59;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL));
    if ( a6 )
    {
      RtlAcquireSRWLockExclusive((char *)v9 + 208);
      *((_DWORD *)v9 + 54) = GetCurrentThreadId();
      v22 = (struct _UBPM_REPETITION_CONTEXT *)*((_QWORD *)v9 + 30);
      if ( v22 != (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v9 + 240) )
      {
        while ( 1 )
        {
          v62 = v22;
          if ( *((_QWORD *)v22 + 5) == a2 )
            break;
          v22 = *(struct _UBPM_REPETITION_CONTEXT **)v22;
          if ( v22 == (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)v9 + 240) )
            goto LABEL_57;
        }
        if ( *((_DWORD *)v22 + 20) )
        {
          v23 = v59;
          v10 = 0;
          v24 = *(_DWORD *)(*(_QWORD *)v59 + 20LL);
          if ( v24 )
          {
            while ( *(_QWORD *)(*((_QWORD *)v9 + 4) + 40LL * v10) != *((_QWORD *)v22 + 4) )
            {
              if ( ++v10 >= v24 )
                goto LABEL_57;
            }
            v25 = *((_QWORD *)v22 + 11);
            if ( v25 )
            {
              v26 = *((_DWORD *)v22 + 24) - 20;
              v27 = v25 + 16;
            }
            else
            {
              v26 = 0;
              v27 = 0;
            }
            UbpmpPerformTriggerActions(v9, v27, v26);
            v28 = v62;
            v29 = *((_DWORD *)v62 + 20);
            if ( v29 != -1 )
            {
              *((_DWORD *)v62 + 20) = v29 - 1;
              v28 = v62;
            }
            if ( !*((_QWORD *)v28 + 8) && !*((_DWORD *)v28 + 20) )
            {
              v30 = UbpmpSubmitDeleteRepetitionContextWork(v28);
              v57 = v30;
              if ( v30 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    54,
                    (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
                    *(_QWORD *)(*(_QWORD *)v23 + 8LL),
                    v30);
              }
            }
          }
        }
      }
LABEL_57:
      *((_DWORD *)v9 + 54) = 0;
      RtlReleaseSRWLockExclusive((char *)v9 + 208);
    }
    else
    {
      v31 = v59;
      v10 = 0;
      v32 = *(_DWORD *)(*(_QWORD *)v59 + 20LL);
      if ( v32 )
      {
        while ( *(_QWORD *)(*((_QWORD *)v9 + 4) + 40LL * v10) != a2 )
        {
          if ( ++v10 >= v32 )
            goto LABEL_58;
        }
        v33 = *(_QWORD *)(*(_QWORD *)v59 + 24LL) + 48LL * v10;
        v34 = _InterlockedExchangeAdd64((volatile signed __int64 *)&g_ullCollectionId, 1u);
        if ( *(_DWORD *)(v33 + 16) )
        {
          v36 = *(void **)&v60.Id;
        }
        else
        {
          RtlAcquireSRWLockExclusive((char *)v9 + 208);
          CurrentThreadId = GetCurrentThreadId();
          v36 = *(void **)&v60.Id;
          *((_DWORD *)v9 + 54) = CurrentThreadId;
          if ( v36 )
          {
            v37 = (__int64)v36 + 16;
            v38 = a5 - 20;
          }
          else
          {
            v38 = 0;
            v37 = 0;
          }
          UbpmpPerformTriggerActions(v61, v37, v38);
          *((_DWORD *)v9 + 54) = 0;
          RtlReleaseSRWLockExclusive((char *)v9 + 208);
          v31 = v59;
          v9 = v61;
        }
        v39 = *(_DWORD *)(v33 + 16);
        if ( v39 || *(_DWORD *)(v33 + 24) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_ddS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v39,
              *(_DWORD *)(v33 + 24),
              v39,
              *(_QWORD *)(*(_QWORD *)v31 + 8LL));
          v40 = UbpmpScheduleRepetitionSeries(v9, v10, v34 + 1, v36, a5, 0, &v62);
          v57 = v40;
          if ( !v40 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            v17 = v40;
            goto LABEL_59;
          }
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)v59 + 8LL),
            v40);
        }
      }
    }
LABEL_58:
    v17 = v57;
LABEL_59:
    *((_DWORD *)v9 + 14) = 0;
    RtlReleaseSRWLockExclusive((char *)v9 + 48);
    UbpmConsumerDecPendingActions(v9);
    v6 = v59;
    goto LABEL_81;
  }
  v17 = v16;
LABEL_81:
  v41 = g_CriticalMeasuredTasks;
  if ( !g_CriticalMeasuredTasks )
    goto LABEL_95;
  v42 = *(const WCHAR **)(*(_QWORD *)v6 + 8LL);
  if ( !v42 )
    goto LABEL_95;
  v43 = -1;
  do
    ++v43;
  while ( v42[v43] );
  if ( !*g_CriticalMeasuredTasks )
    goto LABEL_95;
  while ( 1 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v41[v44] );
    if ( (unsigned int)v43 < (unsigned int)v44 )
      goto LABEL_94;
    v45 = (unsigned int)(v44 - 1);
    if ( v41[v45] == 42 )
    {
      v46 = CompareStringW(0x7Fu, 1u, v41, v45, v42, v45);
      goto LABEL_93;
    }
    if ( (_DWORD)v43 == (_DWORD)v44 )
      break;
LABEL_94:
    v47 = (unsigned int)(v44 + 1);
    v14 = v41[v47] == 0;
    v41 += v47;
    if ( v14 )
      goto LABEL_95;
  }
  v46 = CompareStringW(0x7Fu, 1u, v41, v44, v42, v43);
LABEL_93:
  if ( v46 != 2 )
    goto LABEL_94;
  if ( (unsigned int)dword_18004C0F0 <= 4 )
  {
LABEL_95:
    v48 = v59;
    goto LABEL_96;
  }
  v48 = v59;
  v57 = v10;
  v58 = v17;
  v53 = *(_QWORD *)v59;
  v75 = 4;
  v73 = 4;
  v54 = *(int **)(v53 + 8);
  v74 = &v58;
  v72 = &v57;
  if ( v54 )
  {
    v55 = -1;
    do
      v14 = *((_WORD *)v54 + ++v55) == 0;
    while ( !v14 );
    v56 = 2 * v55 + 2;
  }
  else
  {
    v54 = &dword_1800405F4;
    v56 = 2;
  }
  v70 = v56;
  *(_DWORD *)&v60.Level = 4;
  UserData.Ptr = (ULONGLONG)off_18004C0F8;
  v69 = v54;
  v71 = 0;
  v60.Keyword = 0;
  *(_DWORD *)&v60.Id = 184549376;
  UserData.Size = *(unsigned __int16 *)off_18004C0F8;
  v66 = &word_180043CC6;
  UserData.Reserved = 2;
  v67 = 67;
  v68 = 1;
  LODWORD(v59) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EventWriteTransfer(RegHandle, &v60, 0, 0, 5u, &UserData);
LABEL_96:
  result = dword_18004C0F0;
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v50 = *(_QWORD *)v48;
    LODWORD(v59) = v17;
    v73 = 4;
    v51 = *(int **)(v50 + 8);
    v72 = (int *)&v59;
    if ( v51 )
    {
      do
        v14 = *((_WORD *)v51 + ++v11) == 0;
      while ( !v14 );
      v52 = 2 * v11 + 2;
    }
    else
    {
      v51 = &dword_1800405F4;
      v52 = 2;
    }
    v70 = v52;
    *(_DWORD *)&v60.Level = 516;
    UserData.Ptr = (ULONGLONG)off_18004C0F8;
    v69 = v51;
    v71 = 0;
    v60.Keyword = 0;
    *(_DWORD *)&v60.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18004C0F8;
    v66 = (__int16 *)&dword_180043064;
    UserData.Reserved = 2;
    v67 = 40;
    v68 = 1;
    v58 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &v60, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180026650  mov     [rsp-8+arg_8], rbx
0x180026655  push    rbp
0x180026656  push    rsi
0x180026657  push    rdi
0x180026658  push    r12
0x18002665a  push    r13
0x18002665c  push    r14
0x18002665e  push    r15
0x180026660  lea     rbp, [rsp-17h]
0x180026665  sub     rsp, 0F0h
0x18002666c  mov     rax, cs:__security_cookie
0x180026673  xor     rax, rsp
0x180026676  mov     [rbp+47h+var_40], rax
0x18002667a  mov     eax, cs:dword_18004C0F0
0x180026680  lea     r14, [rcx+18h]
0x180026684  mov     r13, rdx
0x180026687  mov     [rbp+47h+var_C0], rcx
0x18002668b  xor     edx, edx
0x18002668d  mov     [rsp+120h+var_D8], r14
0x180026692  mov     [rbp+47h+var_B8], rdx
0x180026696  mov     rbx, r9
0x180026699  mov     qword ptr [rsp+120h+var_D0.Id], rbx
0x18002669e  mov     rsi, rcx
0x1800266a1  lea     r8, _TraceLoggingMetadata
0x1800266a8  mov     r15d, 0FFFFh
0x1800266ae  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800266b5  cmp     eax, 4
0x1800266b8  jbe     loc_18002677C
0x1800266be  mov     rax, [r14]
0x1800266c1  mov     rcx, [rax+8]
0x1800266c5  test    rcx, rcx
0x1800266c8  jz      short loc_1800266E4
0x1800266ca  mov     rax, r12
0x1800266cd  nop     dword ptr [rax]
0x1800266d0  cmp     [rcx+rax*2+2], dx
0x1800266d5  lea     rax, [rax+1]
0x1800266d9  jnz     short loc_1800266D0
0x1800266db  lea     eax, ds:2[rax*2]
0x1800266e2  jmp     short loc_1800266F0
0x1800266e4  lea     rcx, dword_1800405F4
0x1800266eb  mov     eax, 2
0x1800266f0  mov     [rbp+47h+var_68], eax
0x1800266f3  xor     r9d, r9d; RelatedActivityId
0x1800266f6  movzx   eax, cs:word_180043109
0x1800266fd  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180026700  mov     rax, cs:off_18004C0F8
0x180026707  mov     [rbp+47h+var_90.Ptr], rax
0x18002670b  mov     [rbp+47h+var_70], rcx
0x18002670f  mov     [rbp+47h+var_64], edx
0x180026712  mov     [rbp+47h+EventDescriptor.Keyword], rdx
0x180026716  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18002671a  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x180026721  movzx   eax, word ptr [rax]
0x180026724  mov     [rbp+47h+var_90.Size], eax
0x180026727  lea     rax, byte_180043113
0x18002672e  mov     [rbp+47h+var_80], rax
0x180026732  lea     rax, _TraceLoggingMetadataEnd
0x180026739  sub     eax, r8d
0x18002673c  mov     dword ptr [rbp+47h+var_90.0Ch], 2
0x180026743  mov     [rbp+47h+var_78], 1Dh
0x18002674a  xor     r8d, r8d; ActivityId
0x18002674d  mov     [rbp+47h+var_74], 1
0x180026754  mov     [rsp+120h+var_DC], eax
0x180026758  mov     eax, [rsp+120h+var_DC]
0x18002675c  mov     rcx, cs:RegHandle; RegHandle
0x180026763  lea     rax, [rbp+47h+var_90]
0x180026767  mov     [rsp+120h+UserData], rax; UserData
0x18002676c  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x180026774  call    cs:__imp_EventWriteTransfer
0x18002677a  jmp     short loc_180026781
0x18002677c  mov     [rsp+120h+var_D8], r14
0x180026781  mov     rcx, rsi
0x180026784  call    UbpmConsumerIncPendingActions
0x180026789  mov     [rsp+120h+var_E0], eax
0x18002678d  test    eax, eax
0x18002678f  jnz     loc_180026C74
0x180026795  test    rbx, rbx
0x180026798  jz      short loc_1800267F4
0x18002679a  cmp     [rbp+47h+arg_20], 14h
0x18002679e  jnb     short loc_1800267F4
0x1800267a0  mov     edi, 57h ; 'W'
0x1800267a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267ac  lea     r14, WPP_GLOBAL_Control
0x1800267b3  cmp     rcx, r14
0x1800267b6  jz      short loc_1800267DF
0x1800267b8  test    byte ptr [rcx+1Ch], 1
0x1800267bc  jz      short loc_1800267DF
0x1800267be  mov     r9, [rsi+18h]
0x1800267c2  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800267c9  mov     rcx, [rcx+10h]
0x1800267cd  mov     edx, 33h ; '3'
0x1800267d2  mov     [rsp+120h+UserDataCount], edi
0x1800267d6  mov     r9, [r9+8]
0x1800267da  call    WPP_SF_Sd
0x1800267df  mov     rcx, rsi
0x1800267e2  mov     r13d, edi
0x1800267e5  call    UbpmConsumerDecPendingActions
0x1800267ea  mov     r14, [rsp+120h+var_D8]
0x1800267ef  jmp     loc_180026C77
0x1800267f4  mov     r14, [r14]
0x1800267f7  lea     rcx, [rbp+47h+EventDescriptor]; Buf1
0x1800267fb  xorps   xmm0, xmm0
0x1800267fe  mov     r8d, 10h; Size
0x180026804  xor     ebx, ebx
0x180026806  movups  xmmword ptr [rbp+47h+EventDescriptor.Id], xmm0
0x18002680a  lea     rdx, [r14+54h]; Buf2
0x18002680e  call    memcmp_0
0x180026813  test    eax, eax
0x180026815  jz      loc_1800268CD
0x18002681b  lea     rax, [rbp+47h+ppv]
0x18002681f  mov     [rsp+120h+var_DC], ebx
0x180026823  lea     r9, IID_INetworkListManagerPrivate; riid
0x18002682a  mov     qword ptr [rsp+120h+UserDataCount], rax; ppv
0x18002682f  xor     edx, edx; pUnkOuter
0x180026831  mov     [rbp+47h+ppv], rbx
0x180026835  mov     r8d, 4; dwClsContext
0x18002683b  mov     qword ptr [rbp+47h+EventDescriptor.Id], rbx
0x18002683f  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180026846  xor     esi, esi
0x180026848  call    cs:__imp_CoCreateInstance
0x18002684e  mov     edi, eax
0x180026850  test    eax, eax
0x180026852  js      short loc_180026896
0x180026854  mov     rcx, [rbp+47h+ppv]
0x180026858  lea     r8, [rbp+47h+EventDescriptor]
0x18002685c  lea     rdx, [r14+54h]
0x180026860  mov     rax, [rcx]
0x180026863  mov     rax, [rax+30h]
0x180026867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002686c  mov     edi, eax
0x18002686e  test    eax, eax
0x180026870  js      short loc_180026896
0x180026872  mov     rcx, qword ptr [rbp+47h+EventDescriptor.Id]
0x180026876  lea     rdx, [rsp+120h+var_DC]
0x18002687b  mov     rax, [rcx]
0x18002687e  mov     rax, [rax+60h]
0x180026882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026887  mov     edi, eax
0x180026889  test    eax, eax
0x18002688b  js      short loc_180026896
0x18002688d  mov     esi, [rsp+120h+var_DC]
0x180026891  xor     edi, edi
0x180026893  and     esi, 1
0x180026896  mov     rcx, [rbp+47h+ppv]
0x18002689a  test    rcx, rcx
0x18002689d  jz      short loc_1800268AB
0x18002689f  mov     rax, [rcx]
0x1800268a2  mov     rax, [rax+10h]
0x1800268a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ab  mov     rcx, qword ptr [rbp+47h+EventDescriptor.Id]
0x1800268af  test    rcx, rcx
0x1800268b2  jz      short loc_1800268C0
0x1800268b4  mov     rax, [rcx]
0x1800268b7  mov     rax, [rax+10h]
0x1800268bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c0  test    edi, edi
0x1800268c2  js      short loc_1800268C9
0x1800268c4  test    esi, esi
0x1800268c6  setnz   bl
0x1800268c9  mov     rsi, [rbp+47h+var_C0]
0x1800268cd  mov     [rsp+120h+var_DC], ebx
0x1800268d1  lea     rcx, [rsi+30h]
0x1800268d5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800268db  call    cs:__imp_GetCurrentThreadId
0x1800268e1  mov     [rsi+38h], eax
0x1800268e4  test    byte ptr [rsi+29h], 1
0x1800268e8  jnz     short loc_180026933
0x1800268ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268f1  lea     r14, WPP_GLOBAL_Control
0x1800268f8  cmp     rcx, r14
0x1800268fb  jz      short loc_180026928
0x1800268fd  test    byte ptr [rcx+1Ch], 1
0x180026901  jz      short loc_180026928
0x180026903  mov     r9, [rsi+18h]
0x180026907  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002690e  mov     rcx, [rcx+10h]
0x180026912  mov     edx, 34h ; '4'
0x180026917  mov     [rsp+120h+UserDataCount], 0
0x18002691f  mov     r9, [r9+8]
0x180026923  call    WPP_SF_Sd
0x180026928  mov     r13d, 4C7h
0x18002692e  jmp     loc_180026ABE
0x180026933  mov     rcx, cs:WPP_GLOBAL_Control
0x18002693a  lea     r14, WPP_GLOBAL_Control
0x180026941  cmp     rcx, r14
0x180026944  jz      short loc_18002696C
0x180026946  test    dword ptr [rcx+1Ch], 200h
0x18002694d  jz      short loc_18002696C
0x18002694f  mov     r9, [rsi+18h]
0x180026953  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002695a  mov     rcx, [rcx+10h]
0x18002695e  mov     edx, 35h ; '5'
0x180026963  mov     r9, [r9+8]
0x180026967  call    WPP_SF_S
0x18002696c  cmp     [rbp+47h+arg_28], 0
0x180026970  jz      loc_180026AE1
0x180026976  lea     rbx, [rsi+0D0h]
0x18002697d  mov     rcx, rbx
0x180026980  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180026986  call    cs:__imp_GetCurrentThreadId
0x18002698c  mov     [rbx+8], eax
0x18002698f  lea     rax, [rsi+0F0h]
0x180026996  mov     r9, [rax]
0x180026999  cmp     r9, rax
0x18002699c  jz      loc_180026AA9
0x1800269a2  mov     [rbp+47h+var_B8], r9
0x1800269a6  cmp     [r9+28h], r13
0x1800269aa  jz      short loc_1800269B9
0x1800269ac  mov     r9, [r9]
0x1800269af  cmp     r9, rax
0x1800269b2  jnz     short loc_1800269A2
0x1800269b4  jmp     loc_180026AA9
0x1800269b9  cmp     dword ptr [r9+50h], 0
0x1800269be  jbe     loc_180026AA9
0x1800269c4  mov     r13, [rsp+120h+var_D8]
0x1800269c9  xor     eax, eax
0x1800269cb  movzx   r15d, ax
0x1800269cf  mov     rax, [r13+0]
0x1800269d3  mov     edx, [rax+14h]
0x1800269d6  test    edx, edx
0x1800269d8  jz      loc_180026AA9
0x1800269de  mov     r8, [r9+20h]
0x1800269e2  mov     r10, [rsi+20h]
0x1800269e6  nop     word ptr [rax+rax+00000000h]
0x1800269f0  movzx   eax, r15w
0x1800269f4  lea     rcx, [rax+rax*4]
0x1800269f8  cmp     [r10+rcx*8], r8
0x1800269fc  jz      short loc_180026A0F
0x1800269fe  inc     r15w
0x180026a02  movzx   eax, r15w
0x180026a06  cmp     eax, edx
0x180026a08  jb      short loc_1800269F0
0x180026a0a  jmp     loc_180026AA9
0x180026a0f  mov     rcx, [r9+58h]
0x180026a13  test    rcx, rcx
0x180026a16  jz      short loc_180026A25
0x180026a18  mov     eax, [r9+60h]
0x180026a1c  sub     eax, 14h
0x180026a1f  add     rcx, 10h
0x180026a23  jmp     short loc_180026A29
0x180026a25  xor     eax, eax
0x180026a27  xor     ecx, ecx
0x180026a29  mov     r9, [r9+10h]
0x180026a2d  lea     rdx, [rsp+120h+var_DC]
0x180026a32  mov     dword ptr [rsp+120h+UserData], eax; int
0x180026a36  movzx   r8d, r15w
0x180026a3a  mov     qword ptr [rsp+120h+UserDataCount], rcx; __int64
0x180026a3f  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180026a42  call    UbpmpPerformTriggerActions
0x180026a47  mov     rcx, [rbp+47h+var_B8]
0x180026a4b  mov     eax, [rcx+50h]
0x180026a4e  cmp     eax, 0FFFFFFFFh
0x180026a51  jz      short loc_180026A5C
0x180026a53  dec     eax
0x180026a55  mov     [rcx+50h], eax
0x180026a58  mov     rcx, [rbp+47h+var_B8]; struct _UBPM_REPETITION_CONTEXT *
0x180026a5c  cmp     qword ptr [rcx+40h], 0
0x180026a61  jnz     short loc_180026AA9
0x180026a63  cmp     dword ptr [rcx+50h], 0
0x180026a67  jnz     short loc_180026AA9
0x180026a69  call    ?UbpmpSubmitDeleteRepetitionContextWork@@YAKPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpSubmitDeleteRepetitionContextWork(_UBPM_REPETITION_CONTEXT *)
0x180026a6e  mov     [rsp+120h+var_E0], eax
0x180026a72  test    eax, eax
0x180026a74  jz      short loc_180026AA9
0x180026a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a7d  cmp     rcx, r14
0x180026a80  jz      short loc_180026AA9
0x180026a82  test    byte ptr [rcx+1Ch], 1
0x180026a86  jz      short loc_180026AA9
0x180026a88  mov     r9, [r13+0]
0x180026a8c  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180026a93  mov     rcx, [rcx+10h]
0x180026a97  mov     edx, 36h ; '6'
0x180026a9c  mov     [rsp+120h+UserDataCount], eax
0x180026aa0  mov     r9, [r9+8]
0x180026aa4  call    WPP_SF_Sd
0x180026aa9  mov     rcx, rbx
0x180026aac  mov     dword ptr [rbx+8], 0
0x180026ab3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180026ab9  mov     r13d, [rsp+120h+var_E0]
0x180026abe  lea     rcx, [rsi+30h]
0x180026ac2  mov     dword ptr [rcx+8], 0
0x180026ac9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180026acf  mov     rcx, rsi
0x180026ad2  call    UbpmConsumerDecPendingActions
0x180026ad7  mov     r14, [rsp+120h+var_D8]
0x180026adc  jmp     loc_180026C77
0x180026ae1  mov     r10, [rsp+120h+var_D8]
0x180026ae6  xor     eax, eax
0x180026ae8  movzx   r15d, ax
0x180026aec  mov     r9, [r10]
0x180026aef  mov     edx, [r9+14h]
0x180026af3  test    edx, edx
0x180026af5  jz      short loc_180026AB9
0x180026af7  mov     r8, [rsi+20h]
0x180026afb  nop     dword ptr [rax+rax+00h]
0x180026b00  movzx   ecx, r15w
0x180026b04  lea     rax, [rcx+rcx*4]
0x180026b08  cmp     [r8+rax*8], r13
0x180026b0c  jz      short loc_180026B1C
  ... truncated ...
```
