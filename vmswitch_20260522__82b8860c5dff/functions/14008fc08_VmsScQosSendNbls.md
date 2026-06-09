# VmsScQosSendNbls

- ea: `0x14008fc08`
- end: `0x14009018d`
- name: `VmsScQosSendNbls`
- size: `1413`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002fe4c`
- `0x140032d3c`

## callees

- `0x140027a64`
- `0x1400329f0`
- `0x14006b084`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x14008fc08`
- `0x1401519cc`
- `0x140152c08`
- `0x140153118`
- `0x14015319c`
- `0x140153498`
- `0x140153574`
- `0x1401b6b9c`
- `0x1401b6c4c`
- `0x1401b7214`
- `0x1401b7284`
- `0x1401b72dc`
- `0x1401b731c`
- `0x1401b7f60`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14008ffc3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14008ffc3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008fcac`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008fcac`
- `ntoskrnl!KeLowerIrql` at `0x14009016c`
- `ntoskrnl!KeLowerIrql` at `0x14009016c`
- `ntoskrnl!KfRaiseIrql` at `0x14008fc9b`
- `ntoskrnl!KfRaiseIrql` at `0x14008fc9b`
- `NDIS!NdisReleaseRWLock` at `0x14008feef`
- `NDIS!NdisReleaseRWLock` at `0x140090029`
- `NDIS!NdisReleaseRWLock` at `0x140090123`
- `NDIS!NdisReleaseRWLock` at `0x14008feef`
- `NDIS!NdisReleaseRWLock` at `0x140090029`
- `NDIS!NdisReleaseRWLock` at `0x140090123`
- `NDIS!NdisAcquireRWLockWrite` at `0x14008feb6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009000b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14008feb6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009000b`

## pseudocode

```c
void __fastcall VmsScQosSendNbls(_QWORD *a1, _KDPC *a2, _QWORD *a3, char a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v9; // r13
  char v10; // r12
  ULONG CurrentProcessorNumber; // eax
  const char *v12; // r8
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int **v16; // rdi
  void *SystemArgument1; // rdx
  unsigned int *v18; // rdi
  _SINGLE_LIST_ENTRY *p_DpcListEntry; // rbx
  _QWORD *v20; // r8
  void *v21; // rdx
  int v22; // r12d
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 CurrentTime; // rax
  __int64 v27; // r13
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // edx
  __int64 v31; // r12
  __int64 v32; // rbx
  int v33; // edx
  int v34; // r9d
  int v35; // edx
  _QWORD *v36; // rdx
  _QWORD *v37; // rbx
  __int64 v38; // r13
  int v39; // [rsp+20h] [rbp-B9h]
  __int64 v40; // [rsp+40h] [rbp-99h] BYREF
  __int64 v41; // [rsp+48h] [rbp-91h] BYREF
  _QWORD *v42; // [rsp+50h] [rbp-89h] BYREF
  __int64 *v43; // [rsp+58h] [rbp-81h] BYREF
  ULONG v44; // [rsp+60h] [rbp-79h]
  unsigned int *v45; // [rsp+68h] [rbp-71h]
  _QWORD *v46; // [rsp+70h] [rbp-69h] BYREF
  _QWORD *v47; // [rsp+78h] [rbp-61h]
  __int64 v48; // [rsp+80h] [rbp-59h] BYREF
  __int64 v49; // [rsp+88h] [rbp-51h] BYREF
  __int64 v50; // [rsp+90h] [rbp-49h] BYREF
  __int64 *v51; // [rsp+98h] [rbp-41h] BYREF
  _OWORD v52[2]; // [rsp+A0h] [rbp-39h] BYREF
  int v53; // [rsp+C0h] [rbp-19h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-11h] BYREF
  void *retaddr; // [rsp+128h] [rbp+4Fh]
  KIRQL NewIrql; // [rsp+130h] [rbp+57h]
  struct _LOCK_STATE_EX LockState; // [rsp+138h] [rbp+5Fh] BYREF
  struct _LOCK_STATE_EX v58; // [rsp+140h] [rbp+67h] BYREF
  char v59; // [rsp+148h] [rbp+6Fh]

  v59 = a4;
  v41 = 0;
  v53 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v9 = a1;
  *(_WORD *)&v58.OldIrql = 0;
  v10 = 0;
  v58.Flags = 0;
  v43 = &v50;
  v51 = &v48;
  v40 = 0;
  v42 = 0;
  v46 = 0;
  v50 = 0;
  v48 = 0;
  v47 = a1;
  v49 = 0;
  NewIrql = 0;
  memset(v52, 0, sizeof(v52));
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a4 )
    NewIrql = KfRaiseIrql(2u);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v12 = "VmsScQosSendNbls";
  v13 = CurrentProcessorNumber;
  v44 = CurrentProcessorNumber;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a3 )
    {
      v14 = a3[36];
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 16);
        if ( v15 )
        {
          *(_QWORD *)(v15 + 176) = "VmsScQosSendNbls";
          *(_DWORD *)(v15 + 184) = 3551;
          *(_QWORD *)(v15 + 168) = retaddr;
        }
      }
    }
  }
  v16 = (unsigned int **)(a1 + 749);
  if ( a2 == WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
  {
    ++*(_DWORD *)((v13 << 6) + WPP_MAIN_CB.Dpc.ProcessorHistory + 16);
    ++*(_DWORD *)(192 * v13 + *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement + 168);
    SystemArgument1 = (void *)a1[748];
  }
  else
  {
    if ( *v16 )
      goto LABEL_14;
    v10 = 1;
    SystemArgument1 = a2[3].SystemArgument1;
    v9 = *(_QWORD **)(*(_QWORD *)(a1[155] + 4264LL) + 1984LL);
    v47 = v9;
  }
  if ( !SystemArgument1 )
  {
    VmsNblHelperAppendNblsMoveLast(&v43, a3);
    goto LABEL_62;
  }
LABEL_14:
  LOBYTE(v12) = 1;
  VmsOmObjectLockExclusive(v9, &v58, v12);
  if ( a2 == WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
  {
    v18 = (unsigned int *)a1[748];
  }
  else if ( v10 )
  {
    v18 = (unsigned int *)a2[3].SystemArgument1;
  }
  else
  {
    v18 = *v16;
  }
  if ( v18 )
  {
    v45 = 0;
    if ( a3 )
    {
      p_DpcListEntry = &a2->DpcListEntry;
      do
      {
        v20 = a3;
        v21 = retaddr;
        v22 = (int)a3;
        v41 = 0;
        v40 = 0;
        v23 = *a3;
        a3 = (_QWORD *)*a3;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v23 )
          {
            v24 = *(_QWORD *)(v23 + 288);
            if ( v24 )
            {
              v25 = *(_QWORD *)(v24 + 16);
              if ( v25 )
              {
                *(_DWORD *)(v25 + 184) = 3639;
                *(_QWORD *)(v25 + 176) = "VmsScQosSendNbls";
                *(_QWORD *)(v25 + 168) = retaddr;
              }
            }
          }
        }
        *v20 = 0;
        LOBYTE(v20) = 1;
        LOBYTE(v21) = 1;
        CurrentTime = QosTimerGetCurrentTime((unsigned int)v13, v21, v20);
        v27 = CurrentTime;
        if ( v18 != v45 )
        {
          v45 = v18;
          if ( *v18 != (_DWORD)v13 )
          {
            v28 = *((_QWORD *)v18 + 17);
            if ( (unsigned int *)v28 != v18 + 34 && *(_QWORD *)(v28 + 24) - CurrentTime <= 0 )
              VmsScQospFlowDelay(v18, (unsigned int)v13);
          }
        }
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(v18 + 10, v27, v52) )
        {
          NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)&a2->TargetInfoAsUlong, &LockState, 0);
          if ( (unsigned __int8)QosLineNeedSignal(p_DpcListEntry, (unsigned int)v13) )
            QosLineSignalExternalEvent(p_DpcListEntry, (unsigned int)v13);
          QosLineQueryQueueFeedback(p_DpcListEntry, v29, v52);
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)&a2->TargetInfoAsUlong, &LockState);
          QosTbcAdjustSendWindow(v18 + 10, v52);
        }
        if ( (unsigned __int8)QosFlowSendNetBufferLists(
                                (int)v18 + 40,
                                v13,
                                (_DWORD)p_DpcListEntry,
                                v22,
                                v39,
                                (__int64)&v41,
                                (__int64)&v40) )
        {
          v31 = *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement + 192LL * *v18;
          if ( v18[116] )
          {
            WPP_RECORDER_SF_s(
              VmsIfrPortLog,
              v30,
              19,
              64,
              (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
              (__int64)"flow->FlowType == VmsFlowLimit");
            if ( v18[116] )
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          v32 = *(_QWORD *)(*((_QWORD *)v18 + 17) + 24LL);
          RtlAcquireWriteLockAtDpcLevel(v31, &LockHandle);
          VmsScQospSetTimer(v31, v27, v32);
          VmsScQospSetFlowTimer(v31, v18, v32);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          p_DpcListEntry = &a2->DpcListEntry;
        }
        if ( v40 )
          VmsNblHelperAppendNblsMoveLast(&v51, v40);
        if ( v41 )
        {
          if ( (unsigned __int8)QosLineNeedSignal(p_DpcListEntry, (unsigned int)v13) )
          {
            NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)&a2->TargetInfoAsUlong, &LockState, 1u);
            QosLineSignalExternalEvent(p_DpcListEntry, (unsigned int)v13);
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)&a2->TargetInfoAsUlong, &LockState);
          }
          QosLineSendNetBufferLists((_DWORD)p_DpcListEntry, v33, v41, v34, (__int64)&v42, (__int64)&v40);
          if ( v18[116] == 1 )
          {
            v37 = v42;
            if ( v42 )
            {
              do
              {
                v38 = v37[36];
                if ( !v38 || (v38 = *(_QWORD *)(v38 + 16)) == 0 )
                {
                  WPP_RECORDER_SF_s(
                    VmsIfrLog,
                    v35,
                    19,
                    65,
                    (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
                    (__int64)"nblContext != NULL");
                  MicrosoftTelemetryAssertTriggeredNoArgsKM();
                }
                *(_QWORD *)(v38 + 32) = v18;
                v37 = (_QWORD *)*v37;
              }
              while ( v37 );
              LODWORD(v13) = v44;
            }
            v36 = v42;
          }
          else
          {
            VmsScQosCompleteNbls(v18, a2, v42, &v46);
            v36 = v46;
          }
          VmsNblHelperAppendNblsMoveLast(&v43, v36);
        }
        p_DpcListEntry = &a2->DpcListEntry;
      }
      while ( a3 );
      v9 = v47;
    }
  }
  else
  {
    VmsNblHelperAppendNblsMoveLast(&v43, a3);
  }
  if ( v48 )
    VmsScQosDropNbls((_DWORD)v18, (_DWORD)a2, v48, (unsigned int)&v49, -536862682);
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v9[7], &v58);
LABEL_62:
  *a6 = v49;
  if ( v50 )
    *a5 = v50;
  if ( a2 == WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
  {
    VmsScQospIndicateTimerUnitConsumerEnd((unsigned int)v13);
    VmsScQospIndicateDelayQueueConsumerEnd((unsigned int)v13);
  }
  if ( !v59 )
    KeLowerIrql(NewIrql);
}

```

## disassembly

```asm
0x14008fc08  mov     [rsp-8+arg_18], r9b
0x14008fc0d  push    rbp
0x14008fc0e  push    rbx
0x14008fc0f  push    rsi
0x14008fc10  push    rdi
0x14008fc11  push    r12
0x14008fc13  push    r13
0x14008fc15  push    r14
0x14008fc17  push    r15
0x14008fc19  lea     rbp, [rsp-0Fh]
0x14008fc1e  sub     rsp, 0E8h
0x14008fc25  xor     edi, edi
0x14008fc27  mov     rbx, rcx
0x14008fc2a  xor     ecx, ecx
0x14008fc2c  mov     [rsp+120h+var_D8], rdi
0x14008fc31  mov     [rbp+47h+var_60], ecx
0x14008fc34  xorps   xmm0, xmm0
0x14008fc37  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rcx
0x14008fc3b  mov     r15, r8
0x14008fc3e  mov     word ptr [rbp+47h+LockState.OldIrql], cx
0x14008fc42  mov     rsi, rdx
0x14008fc45  mov     [rbp+47h+LockState.Flags], cl
0x14008fc48  mov     r13, rbx
0x14008fc4b  mov     word ptr [rbp+47h+arg_10.OldIrql], cx
0x14008fc4f  mov     r12b, dil
0x14008fc52  mov     [rbp+47h+arg_10.Flags], cl
0x14008fc55  lea     rcx, [rbp+47h+var_90]
0x14008fc59  mov     [rsp+120h+var_C8], rcx
0x14008fc5e  lea     rcx, [rbp+47h+var_A0]
0x14008fc62  mov     [rbp+47h+var_88], rcx
0x14008fc66  mov     [rsp+120h+var_E0], rdi
0x14008fc6b  mov     [rsp+120h+var_D0], rdi
0x14008fc70  mov     [rbp+47h+var_B0], rdi
0x14008fc74  mov     [rbp+47h+var_90], rdi
0x14008fc78  mov     [rbp+47h+var_A0], rdi
0x14008fc7c  mov     [rbp+47h+var_A8], rbx
0x14008fc80  mov     [rbp+47h+var_98], rdi
0x14008fc84  mov     [rbp+47h+NewIrql], dil
0x14008fc88  movups  [rbp+47h+var_80], xmm0
0x14008fc8c  movups  [rbp+47h+var_70], xmm0
0x14008fc90  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x14008fc94  test    r9b, r9b
0x14008fc97  jnz     short loc_14008FCAA
0x14008fc99  mov     cl, 2; NewIrql
0x14008fc9b  call    cs:__imp_KfRaiseIrql
0x14008fca2  nop     dword ptr [rax+rax+00h]
0x14008fca7  mov     [rbp+47h+NewIrql], al
0x14008fcaa  xor     ecx, ecx; ProcNumber
0x14008fcac  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008fcb3  nop     dword ptr [rax+rax+00h]
0x14008fcb8  mov     ecx, cs:VmsDiagnosticFlags
0x14008fcbe  lea     r8, aVmsscqossendnb; "VmsScQosSendNbls"
0x14008fcc5  mov     rdx, [rbp+4Fh]
0x14008fcc9  mov     r14d, eax
0x14008fccc  mov     [rbp+47h+var_C0], r14d
0x14008fcd0  test    cl, 1
0x14008fcd3  jz      short loc_14008FD07
0x14008fcd5  test    r15, r15
0x14008fcd8  jz      short loc_14008FD07
0x14008fcda  mov     rax, [r15+120h]
0x14008fce1  test    rax, rax
0x14008fce4  jz      short loc_14008FD07
0x14008fce6  mov     rax, [rax+10h]
0x14008fcea  test    rax, rax
0x14008fced  jz      short loc_14008FD07
0x14008fcef  mov     [rax+0B0h], r8
0x14008fcf6  mov     dword ptr [rax+0B8h], 0DDFh
0x14008fd00  mov     [rax+0A8h], rdx
0x14008fd07  cmp     rsi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14008fd0e  lea     rdi, [rbx+1768h]
0x14008fd15  jnz     short loc_14008FD48
0x14008fd17  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x14008fd1e  mov     rcx, r14
0x14008fd21  shl     rcx, 6
0x14008fd25  inc     dword ptr [rcx+rax+10h]
0x14008fd29  lea     rcx, [r14+r14*2]
0x14008fd2d  mov     rax, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x14008fd34  shl     rcx, 6
0x14008fd38  inc     dword ptr [rcx+rax+0A8h]
0x14008fd3f  mov     rdx, [rbx+1760h]
0x14008fd46  jmp     short loc_14008FD71
0x14008fd48  cmp     qword ptr [rdi], 0
0x14008fd4c  jnz     short loc_14008FD88
0x14008fd4e  mov     rax, [rbx+4D8h]
0x14008fd55  mov     r12b, 1
0x14008fd58  mov     rdx, [rsi+0E8h]
0x14008fd5f  mov     rcx, [rax+10A8h]
0x14008fd66  mov     r13, [rcx+7C0h]
0x14008fd6d  mov     [rbp+47h+var_A8], r13
0x14008fd71  test    rdx, rdx
0x14008fd74  jnz     short loc_14008FD88
0x14008fd76  mov     rdx, r15
0x14008fd79  lea     rcx, [rsp+120h+var_C8]
0x14008fd7e  call    VmsNblHelperAppendNblsMoveLast
0x14008fd83  jmp     loc_14009012F
0x14008fd88  mov     r8b, 1
0x14008fd8b  lea     rdx, [rbp+47h+arg_10]
0x14008fd8f  mov     rcx, r13
0x14008fd92  call    VmsOmObjectLockExclusive
0x14008fd97  cmp     rsi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14008fd9e  jnz     short loc_14008FDA9
0x14008fda0  mov     rdi, [rbx+1760h]
0x14008fda7  jmp     short loc_14008FDBA
0x14008fda9  test    r12b, r12b
0x14008fdac  jz      short loc_14008FDB7
0x14008fdae  mov     rdi, [rsi+0E8h]
0x14008fdb5  jmp     short loc_14008FDBA
0x14008fdb7  mov     rdi, [rdi]
0x14008fdba  test    rdi, rdi
0x14008fdbd  jnz     short loc_14008FDD1
0x14008fdbf  mov     rdx, r15
0x14008fdc2  lea     rcx, [rsp+120h+var_C8]
0x14008fdc7  call    VmsNblHelperAppendNblsMoveLast
0x14008fdcc  jmp     loc_1400900FB
0x14008fdd1  mov     [rbp+47h+var_B8], 0
0x14008fdd9  test    r15, r15
0x14008fddc  jz      loc_1400900FB
0x14008fde2  lea     rbx, [rsi+8]
0x14008fde6  mov     eax, cs:VmsDiagnosticFlags
0x14008fdec  mov     r8, r15
0x14008fdef  mov     rdx, [rbp+4Fh]
0x14008fdf3  mov     r12, r15
0x14008fdf6  mov     [rsp+120h+var_D8], 0
0x14008fdff  mov     [rsp+120h+var_E0], 0
0x14008fe08  mov     rcx, [r15]
0x14008fe0b  mov     r15, rcx
0x14008fe0e  test    al, 1
0x14008fe10  jz      short loc_14008FE4B
0x14008fe12  test    rcx, rcx
0x14008fe15  jz      short loc_14008FE4B
0x14008fe17  mov     rax, [rcx+120h]
0x14008fe1e  test    rax, rax
0x14008fe21  jz      short loc_14008FE4B
0x14008fe23  mov     rax, [rax+10h]
0x14008fe27  test    rax, rax
0x14008fe2a  jz      short loc_14008FE4B
0x14008fe2c  lea     rcx, aVmsscqossendnb; "VmsScQosSendNbls"
0x14008fe33  mov     dword ptr [rax+0B8h], 0E37h
0x14008fe3d  mov     [rax+0B0h], rcx
0x14008fe44  mov     [rax+0A8h], rdx
0x14008fe4b  mov     qword ptr [r8], 0
0x14008fe52  mov     ecx, r14d
0x14008fe55  mov     r8b, 1
0x14008fe58  mov     dl, r8b
0x14008fe5b  call    QosTimerGetCurrentTime
0x14008fe60  mov     r13, rax
0x14008fe63  cmp     rdi, [rbp+47h+var_B8]
0x14008fe67  jz      short loc_14008FE98
0x14008fe69  mov     [rbp+47h+var_B8], rdi
0x14008fe6d  cmp     [rdi], r14d
0x14008fe70  jz      short loc_14008FE98
0x14008fe72  lea     rcx, [rdi+88h]
0x14008fe79  mov     rdx, [rcx]
0x14008fe7c  cmp     rdx, rcx
0x14008fe7f  jz      short loc_14008FE98
0x14008fe81  mov     rcx, [rdx+18h]
0x14008fe85  sub     rcx, rax
0x14008fe88  test    rcx, rcx
0x14008fe8b  jg      short loc_14008FE98
0x14008fe8d  mov     edx, r14d
0x14008fe90  mov     rcx, rdi
0x14008fe93  call    VmsScQospFlowDelay
0x14008fe98  lea     r8, [rbp+47h+var_80]
0x14008fe9c  mov     rdx, r13
0x14008fe9f  lea     rcx, [rdi+28h]
0x14008fea3  call    QosFlowNeedQueueFeedback
0x14008fea8  test    al, al
0x14008feaa  jz      short loc_14008FF08
0x14008feac  mov     rcx, [rsi]; Lock
0x14008feaf  lea     rdx, [rbp+47h+LockState]; LockState
0x14008feb3  xor     r8d, r8d; Flags
0x14008feb6  call    cs:__imp_NdisAcquireRWLockWrite
0x14008febd  nop     dword ptr [rax+rax+00h]
0x14008fec2  mov     edx, r14d
0x14008fec5  mov     rcx, rbx
0x14008fec8  call    QosLineNeedSignal
0x14008fecd  test    al, al
0x14008fecf  jz      short loc_14008FEDC
0x14008fed1  mov     edx, r14d
0x14008fed4  mov     rcx, rbx
0x14008fed7  call    QosLineSignalExternalEvent
0x14008fedc  lea     r8, [rbp+47h+var_80]
0x14008fee0  mov     rcx, rbx
0x14008fee3  call    QosLineQueryQueueFeedback
0x14008fee8  mov     rcx, [rsi]; Lock
0x14008feeb  lea     rdx, [rbp+47h+LockState]; LockState
0x14008feef  call    cs:__imp_NdisReleaseRWLock
0x14008fef6  nop     dword ptr [rax+rax+00h]
0x14008fefb  lea     rdx, [rbp+47h+var_80]
0x14008feff  lea     rcx, [rdi+28h]
0x14008ff03  call    QosTbcAdjustSendWindow
0x14008ff08  lea     rax, [rsp+120h+var_E0]
0x14008ff0d  mov     r9, r12
0x14008ff10  mov     [rsp+120h+var_F0], rax
0x14008ff15  lea     rcx, [rdi+28h]
0x14008ff19  lea     rax, [rsp+120h+var_D8]
0x14008ff1e  mov     r8, rbx
0x14008ff21  mov     edx, r14d
0x14008ff24  mov     [rsp+120h+var_F8], rax
0x14008ff29  call    QosFlowSendNetBufferLists
0x14008ff2e  test    al, al
0x14008ff30  jz      loc_14008FFD3
0x14008ff36  mov     eax, [rdi]
0x14008ff38  lea     r12, [rax+rax*2]
0x14008ff3c  shl     r12, 6
0x14008ff40  add     r12, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x14008ff47  cmp     dword ptr [rdi+1D0h], 0
0x14008ff4e  jz      short loc_14008FF8C
0x14008ff50  mov     rcx, cs:VmsIfrPortLog
0x14008ff57  lea     rax, aFlowFlowtypeVm_1; "flow->FlowType == VmsFlowLimit"
0x14008ff5e  mov     [rsp+120h+var_F8], rax
0x14008ff63  mov     r9d, 40h ; '@'
0x14008ff69  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x14008ff70  mov     [rsp+120h+var_100], rax
0x14008ff75  lea     r8d, [r9-2Dh]
0x14008ff79  call    WPP_RECORDER_SF_s
0x14008ff7e  cmp     dword ptr [rdi+1D0h], 0
0x14008ff85  jz      short loc_14008FF8C
0x14008ff87  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flow->FlowType == VmsFlowLimit")
0x14008ff8c  mov     rax, [rdi+88h]
0x14008ff93  lea     rdx, [rbp+47h+LockHandle]
0x14008ff97  mov     rcx, r12
0x14008ff9a  mov     rbx, [rax+18h]
0x14008ff9e  call    RtlAcquireWriteLockAtDpcLevel
0x14008ffa3  mov     r8, rbx
0x14008ffa6  mov     rdx, r13
0x14008ffa9  mov     rcx, r12
0x14008ffac  call    VmsScQospSetTimer
0x14008ffb1  mov     r8, rbx
0x14008ffb4  mov     rdx, rdi
0x14008ffb7  mov     rcx, r12
0x14008ffba  call    VmsScQospSetFlowTimer
0x14008ffbf  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14008ffc3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14008ffca  nop     dword ptr [rax+rax+00h]
0x14008ffcf  lea     rbx, [rsi+8]
0x14008ffd3  mov     rdx, [rsp+120h+var_E0]
0x14008ffd8  test    rdx, rdx
0x14008ffdb  jz      short loc_14008FFE6
0x14008ffdd  lea     rcx, [rbp+47h+var_88]
0x14008ffe1  call    VmsNblHelperAppendNblsMoveLast
0x14008ffe6  cmp     [rsp+120h+var_D8], 0
0x14008ffec  jz      loc_1400900EA
0x14008fff2  mov     edx, r14d
0x14008fff5  mov     rcx, rbx
0x14008fff8  call    QosLineNeedSignal
0x14008fffd  test    al, al
0x14008ffff  jz      short loc_140090035
0x140090001  mov     rcx, [rsi]; Lock
0x140090004  lea     rdx, [rbp+47h+LockState]; LockState
0x140090008  mov     r8b, 1; Flags
0x14009000b  call    cs:__imp_NdisAcquireRWLockWrite
0x140090012  nop     dword ptr [rax+rax+00h]
0x140090017  mov     edx, r14d
0x14009001a  mov     rcx, rbx
0x14009001d  call    QosLineSignalExternalEvent
0x140090022  mov     rcx, [rsi]; Lock
0x140090025  lea     rdx, [rbp+47h+LockState]; LockState
0x140090029  call    cs:__imp_NdisReleaseRWLock
0x140090030  nop     dword ptr [rax+rax+00h]
0x140090035  mov     r8, [rsp+120h+var_D8]
0x14009003a  lea     rax, [rsp+120h+var_E0]
0x14009003f  mov     [rsp+120h+var_F8], rax
0x140090044  mov     rcx, rbx
0x140090047  lea     rax, [rsp+120h+var_D0]
0x14009004c  mov     [rsp+120h+var_100], rax
0x140090051  call    QosLineSendNetBufferLists
0x140090056  cmp     dword ptr [rdi+1D0h], 1
0x14009005d  jz      short loc_140090079
0x14009005f  mov     r8, [rsp+120h+var_D0]
0x140090064  lea     r9, [rbp+47h+var_B0]
0x140090068  mov     rdx, rsi
0x14009006b  mov     rcx, rdi
0x14009006e  call    VmsScQosCompleteNbls
0x140090073  mov     rdx, [rbp+47h+var_B0]
0x140090077  jmp     short loc_1400900E0
0x140090079  mov     rbx, [rsp+120h+var_D0]
0x14009007e  test    rbx, rbx
0x140090081  jz      short loc_1400900DB
0x140090083  lea     r14, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x14009008a  mov     r13, [rbx+120h]
0x140090091  test    r13, r13
0x140090094  jz      short loc_14009009F
0x140090096  mov     r13, [r13+10h]
0x14009009a  test    r13, r13
0x14009009d  jnz     short loc_1400900CB
0x14009009f  mov     rcx, cs:VmsIfrLog
0x1400900a6  lea     rax, aNblcontextNull; "nblContext != NULL"
0x1400900ad  mov     r9d, 41h ; 'A'
0x1400900b3  mov     [rsp+120h+var_F8], rax
0x1400900b8  mov     [rsp+120h+var_100], r14
0x1400900bd  lea     r8d, [r9-2Eh]
0x1400900c1  call    WPP_RECORDER_SF_s
0x1400900c6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "nblContext != ((void *)0)")
0x1400900cb  mov     [r13+20h], rdi
0x1400900cf  mov     rbx, [rbx]
0x1400900d2  test    rbx, rbx
0x1400900d5  jnz     short loc_14009008A
0x1400900d7  mov     r14d, [rbp+47h+var_C0]
0x1400900db  mov     rdx, [rsp+120h+var_D0]
  ... truncated ...
```
