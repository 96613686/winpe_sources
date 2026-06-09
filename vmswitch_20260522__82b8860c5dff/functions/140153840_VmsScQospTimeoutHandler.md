# VmsScQospTimeoutHandler

- ea: `0x140153840`
- end: `0x140153dcd`
- name: `VmsScQospTimeoutHandler`
- size: `1421`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015319c`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14006b084`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x1401519cc`
- `0x140152be0`
- `0x140153118`
- `0x140153574`
- `0x140153840`
- `0x1401b6b9c`
- `0x1401b6be8`
- `0x1401b7214`
- `0x1401b7284`
- `0x1401b72dc`
- `0x1401b731c`
- `0x1401b7f60`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14015397a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153b99`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153da4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14015397a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153b99`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153da4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140153886`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140153886`
- `ntoskrnl!KeCancelTimer` at `0x140153d7b`
- `ntoskrnl!KeCancelTimer` at `0x140153d7b`
- `NDIS!NdisReleaseRWLock` at `0x140153ad4`
- `NDIS!NdisReleaseRWLock` at `0x140153bda`
- `NDIS!NdisReleaseRWLock` at `0x140153c42`
- `NDIS!NdisReleaseRWLock` at `0x140153ad4`
- `NDIS!NdisReleaseRWLock` at `0x140153bda`
- `NDIS!NdisReleaseRWLock` at `0x140153c42`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153a97`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153c24`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153a97`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153c24`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153937`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153d4d`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153937`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153d4d`
- `NETIO!RtlSuspendTimerWheel` at `0x140153d64`
- `NETIO!RtlSuspendTimerWheel` at `0x140153d64`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140153954`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140153954`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153967`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153b86`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153967`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153b86`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140153b6c`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140153b6c`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140153d36`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140153d36`

## pseudocode

```c
void __fastcall VmsScQospTimeoutHandler(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 CurrentProcessorNumber; // r12
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned __int64 CurrentTime; // rsi
  unsigned __int64 v9; // rdi
  unsigned int v10; // eax
  int v11; // ecx
  __int64 NextExpiredTimerWheelEntry; // r14
  _QWORD *v13; // r8
  unsigned int *v14; // rsi
  _QWORD *v15; // r15
  int v16; // edx
  PNDIS_RW_LOCK_EX *BufferChainingDpc; // rdi
  unsigned __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  int v21; // ecx
  __int64 v22; // rcx
  int v23; // r13d
  int v24; // edx
  int v25; // r9d
  int v26; // edx
  _QWORD *v27; // r15
  __int64 v28; // r9
  _QWORD *v29; // rax
  int NextExpirationTimerWheelTick; // eax
  struct _LOCK_STATE_EX v31; // [rsp+30h] [rbp-89h] BYREF
  _QWORD *v32; // [rsp+38h] [rbp-81h] BYREF
  int v33; // [rsp+40h] [rbp-79h] BYREF
  __int64 v34; // [rsp+48h] [rbp-71h] BYREF
  __int64 v35; // [rsp+50h] [rbp-69h] BYREF
  __int64 v36; // [rsp+58h] [rbp-61h] BYREF
  __int64 v37; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-51h]
  unsigned __int64 v39; // [rsp+70h] [rbp-49h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-41h] BYREF
  __int64 v41; // [rsp+90h] [rbp-29h]
  __int64 v42; // [rsp+98h] [rbp-21h]
  _OWORD v43[2]; // [rsp+A0h] [rbp-19h] BYREF
  int v44; // [rsp+C0h] [rbp+7h]
  struct _LOCK_STATE_EX LockState; // [rsp+128h] [rbp+6Fh] BYREF

  v44 = 0;
  memset(v43, 0, sizeof(v43));
  *(_WORD *)&v31.OldIrql = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v31.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v6) = 1;
  LOBYTE(v7) = 1;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v7, v6);
  v39 = CurrentTime;
  v36 = 0;
  v34 = 0;
  v37 = 0;
  v9 = CurrentTime / 0xFA;
  v38 = CurrentTime / 0xFA;
  v35 = 0;
  ++*(_DWORD *)(((unsigned __int64)(unsigned int)CurrentProcessorNumber << 6) + WPP_MAIN_CB.Dpc.ProcessorHistory + 16);
  v33 = 0;
  RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  v10 = *((_DWORD *)DeferredContext + 43) & 0xFFFFFFFE;
  v11 = ~(*((_DWORD *)DeferredContext + 43) >> 1);
  *((_QWORD *)DeferredContext + 2) = CurrentTime;
  *((_DWORD *)DeferredContext + 43) = v10 | v11 & 1;
  if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 20)) )
  {
    RtlUpdateCurrentTimerWheelTick(*((_QWORD *)DeferredContext + 20), (unsigned int)v9);
    NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(*((_QWORD *)DeferredContext + 20));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( NextExpiredTimerWheelEntry )
    {
      do
      {
        v14 = (unsigned int *)(NextExpiredTimerWheelEntry - 8);
        v41 = NextExpiredTimerWheelEntry;
        if ( (char *)(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement
                    + 192LL * *(unsigned int *)(NextExpiredTimerWheelEntry - 8)) != DeferredContext )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            (unsigned int)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
            19,
            17,
            (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
            (__int64)"&VmsTimerUnits[flow->TimerUnitIndex] == timerUnit");
          if ( (char *)(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement + 192LL * *v14) != DeferredContext )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v15 = (_QWORD *)*((_QWORD *)v14 + 60);
        v32 = v15;
        LOBYTE(v13) = 1;
        VmsOmObjectLockExclusive(v15, &v31, v13);
        if ( v14[116] == 1 )
          BufferChainingDpc = *(PNDIS_RW_LOCK_EX **)(v15[155] + 8680LL);
        else
          BufferChainingDpc = (PNDIS_RW_LOCK_EX *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
        if ( !BufferChainingDpc )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v16,
            19,
            18,
            (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
            (__int64)"line != NULL");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v18 = v39;
        *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = 0;
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(v14 + 10, v18, v43) && BufferChainingDpc )
        {
          NdisAcquireRWLockWrite(*BufferChainingDpc, &LockState, 1u);
          if ( (unsigned __int8)QosLineNeedSignal(BufferChainingDpc + 1, (unsigned int)CurrentProcessorNumber) )
            QosLineSignalExternalEvent(BufferChainingDpc + 1, (unsigned int)CurrentProcessorNumber);
          QosLineQueryQueueFeedback(BufferChainingDpc + 1, v19, v43);
          NdisReleaseRWLock(*BufferChainingDpc, &LockState);
          QosTbcAdjustSendWindow(v14 + 10, v43);
          v15 = v32;
        }
        if ( (unsigned __int8)QosFlowProcessQueuedNetBufferLists(
                                (int)v14 + 40,
                                CurrentProcessorNumber,
                                (unsigned int)&v36,
                                (unsigned int)&v33,
                                (__int64)&v34) )
        {
          v20 = *(_QWORD *)(*(_QWORD *)(NextExpiredTimerWheelEntry + 128) + 24LL) / 0xFAuLL;
          v21 = v20 + 1;
          if ( (int)v20 - (int)v38 > 0 )
            v21 = *(_QWORD *)(*(_QWORD *)(NextExpiredTimerWheelEntry + 128) + 24LL) / 0xFAuLL;
          if ( !v21 )
            v21 = 1;
          *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = v21;
        }
        RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
        RtlReturnTimerWheelEntry(*((_QWORD *)DeferredContext + 20), NextExpiredTimerWheelEntry);
        v22 = *((_QWORD *)DeferredContext + 20);
        v42 = *(_QWORD *)NextExpiredTimerWheelEntry;
        NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(v22);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        v32 = (_QWORD *)*((_QWORD *)v14 + 59);
        if ( v34 )
          VmsScQosDropNbls((_DWORD)v14, (_DWORD)BufferChainingDpc, v34, (unsigned int)&v35, -536862684);
        NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v15[7], &v31);
        if ( v35 )
          VmsNblHelperRefCountDecrementMany(v35, 1);
        v23 = v36;
        if ( v36 )
        {
          if ( (unsigned __int8)QosLineNeedSignal(BufferChainingDpc + 1, (unsigned int)CurrentProcessorNumber) )
          {
            NdisAcquireRWLockWrite(*BufferChainingDpc, &LockState, 1u);
            QosLineSignalExternalEvent(BufferChainingDpc + 1, (unsigned int)CurrentProcessorNumber);
            NdisReleaseRWLock(*BufferChainingDpc, &LockState);
          }
          QosLineSendNetBufferLists((_DWORD)BufferChainingDpc + 8, v24, v23, v25, (__int64)&v37, (__int64)&v34);
          v27 = v32;
          if ( !v32 )
          {
            WPP_RECORDER_SF_s(
              VmsIfrLog,
              v26,
              19,
              19,
              (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
              (__int64)"nic != NULL");
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          v32 = 0;
          VmsScQosCompleteNbls(v14, BufferChainingDpc, v37, &v32);
          v13 = v32;
          if ( v32 )
          {
            LODWORD(v28) = 0;
            v29 = v32;
            do
            {
              v29 = (_QWORD *)*v29;
              v28 = (unsigned int)(v28 + 1);
            }
            while ( v29 );
            VmsScQospSendProcessedNbls(v14[116], v27, v32, v28);
          }
        }
        if ( v42 == v41 )
          VmsScQospDereferenceFlow(v14);
      }
      while ( NextExpiredTimerWheelEntry );
      LODWORD(v9) = v38;
      CurrentTime = v39;
    }
    RtlAcquireWriteLockAtDpcLevel(DeferredContext, &LockHandle);
  }
  NextExpirationTimerWheelTick = RtlGetNextExpirationTimerWheelTick(*((_QWORD *)DeferredContext + 20));
  if ( NextExpirationTimerWheelTick )
  {
    VmsScQospSetTimer(
      DeferredContext,
      CurrentTime,
      CurrentTime + 250LL * (unsigned int)(NextExpirationTimerWheelTick - v9));
  }
  else
  {
    if ( !(unsigned __int8)RtlIsTimerWheelSuspended(*((_QWORD *)DeferredContext + 20)) )
      RtlSuspendTimerWheel(*((_QWORD *)DeferredContext + 20));
    *((_DWORD *)DeferredContext + 43) |= 1u;
    KeCancelTimer((PKTIMER)(DeferredContext + 96));
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  VmsScQospIndicateDelayQueueConsumerEnd((unsigned int)CurrentProcessorNumber);
}

```

## disassembly

```asm
0x140153840  push    rbp
0x140153842  push    rbx
0x140153843  push    rsi
0x140153844  push    rdi
0x140153845  push    r12
0x140153847  push    r13
0x140153849  push    r14
0x14015384b  push    r15
0x14015384d  lea     rbp, [rsp-1Fh]
0x140153852  sub     rsp, 0D8h
0x140153859  xor     eax, eax
0x14015385b  xorps   xmm0, xmm0
0x14015385e  xor     ecx, ecx; ProcNumber
0x140153860  mov     [rbp+57h+var_50], eax
0x140153863  movups  [rbp+57h+var_70], xmm0
0x140153867  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14015386b  mov     rbx, rdx
0x14015386e  movups  [rbp+57h+var_60], xmm0
0x140153872  mov     word ptr [rsp+110h+var_E0.OldIrql], ax
0x140153877  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14015387b  mov     [rsp+110h+var_E0.Flags], al
0x14015387f  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140153883  mov     [rbp+57h+LockState.Flags], al
0x140153886  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14015388d  nop     dword ptr [rax+rax+00h]
0x140153892  mov     r13d, 1
0x140153898  mov     r12d, eax
0x14015389b  mov     r8b, r13b
0x14015389e  mov     dl, r13b
0x1401538a1  mov     ecx, eax
0x1401538a3  call    QosTimerGetCurrentTime
0x1401538a8  mov     rsi, rax
0x1401538ab  mov     [rbp+57h+var_A0], rax
0x1401538af  xor     r15d, r15d
0x1401538b2  mov     [rbp+57h+var_B8], 0
0x1401538ba  mov     rax, 624DD2F1A9FBE77h
0x1401538c4  mov     [rbp+57h+var_C8], 0
0x1401538cc  mul     rsi
0x1401538cf  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x1401538d6  mov     rdi, rsi
0x1401538d9  sub     rdi, rdx
0x1401538dc  mov     [rbp+57h+var_B0], 0
0x1401538e4  shr     rdi, 1
0x1401538e7  mov     ecx, r12d
0x1401538ea  shl     rcx, 6
0x1401538ee  add     rdi, rdx
0x1401538f1  shr     rdi, 7
0x1401538f5  lea     rdx, [rbp+57h+LockHandle]
0x1401538f9  mov     [rbp+57h+var_A8], rdi
0x1401538fd  mov     [rbp+57h+var_C0], r15
0x140153901  add     [rcx+rax+10h], r13d
0x140153906  mov     rcx, rbx
0x140153909  mov     [rbp+57h+var_D0], r15d
0x14015390d  call    RtlAcquireWriteLockAtDpcLevel
0x140153912  mov     eax, [rbx+0ACh]
0x140153918  mov     ecx, eax
0x14015391a  shr     ecx, 1
0x14015391c  and     eax, 0FFFFFFFEh
0x14015391f  not     ecx
0x140153921  mov     [rbx+10h], rsi
0x140153925  and     ecx, r13d
0x140153928  or      ecx, eax
0x14015392a  mov     [rbx+0ACh], ecx
0x140153930  mov     rcx, [rbx+0A0h]
0x140153937  call    cs:__imp_RtlIsTimerWheelSuspended
0x14015393e  nop     dword ptr [rax+rax+00h]
0x140153943  test    al, al
0x140153945  jnz     loc_140153D2F
0x14015394b  mov     rcx, [rbx+0A0h]
0x140153952  mov     edx, edi
0x140153954  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14015395b  nop     dword ptr [rax+rax+00h]
0x140153960  mov     rcx, [rbx+0A0h]
0x140153967  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x14015396e  nop     dword ptr [rax+rax+00h]
0x140153973  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140153977  mov     r14, rax
0x14015397a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140153981  nop     dword ptr [rax+rax+00h]
0x140153986  test    r14, r14
0x140153989  jz      loc_140153D23
0x14015398f  lea     rdx, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153996  lea     rsi, [r14-8]
0x14015399a  mov     [rbp+57h+var_80], r14
0x14015399e  mov     eax, [rsi]
0x1401539a0  lea     rcx, [rax+rax*2]
0x1401539a4  shl     rcx, 6
0x1401539a8  add     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1401539af  cmp     rcx, rbx
0x1401539b2  jz      short loc_1401539F6
0x1401539b4  mov     rcx, cs:VmsIfrLog
0x1401539bb  lea     rax, aVmstimerunitsF; "&VmsTimerUnits[flow->TimerUnitIndex] =="...
0x1401539c2  mov     r9d, 11h
0x1401539c8  mov     [rsp+110h+var_E8], rax
0x1401539cd  mov     [rsp+110h+var_F0], rdx
0x1401539d2  lea     r8d, [r9+2]
0x1401539d6  call    WPP_RECORDER_SF_s
0x1401539db  mov     eax, [rsi]
0x1401539dd  lea     rcx, [rax+rax*2]
0x1401539e1  shl     rcx, 6
0x1401539e5  add     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1401539ec  cmp     rcx, rbx
0x1401539ef  jz      short loc_1401539F6
0x1401539f1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "&VmsTimerUnits[flow->TimerUnitIndex] == timerUnit")
0x1401539f6  mov     r15, [rsi+1E0h]
0x1401539fd  lea     rdx, [rsp+110h+var_E0]
0x140153a02  mov     rcx, r15
0x140153a05  mov     [rsp+110h+var_D8], r15
0x140153a0a  mov     r8b, r13b
0x140153a0d  call    VmsOmObjectLockExclusive
0x140153a12  cmp     [rsi+1D0h], r13d
0x140153a19  jnz     short loc_140153A2B
0x140153a1b  mov     rax, [r15+4D8h]
0x140153a22  mov     rdi, [rax+21E8h]
0x140153a29  jmp     short loc_140153A32
0x140153a2b  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140153a32  test    rdi, rdi
0x140153a35  jnz     short loc_140153A68
0x140153a37  mov     rcx, cs:VmsIfrLog
0x140153a3e  lea     rax, aLineNull; "line != NULL"
0x140153a45  mov     [rsp+110h+var_E8], rax
0x140153a4a  lea     r9d, [rdi+12h]
0x140153a4e  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153a55  lea     r8d, [rdi+13h]
0x140153a59  mov     [rsp+110h+var_F0], rax
0x140153a5e  call    WPP_RECORDER_SF_s
0x140153a63  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "line != ((void *)0)")
0x140153a68  mov     rdx, [rbp+57h+var_A0]
0x140153a6c  lea     r13, [rsi+28h]
0x140153a70  mov     rcx, r13
0x140153a73  mov     dword ptr [r14+14h], 0
0x140153a7b  lea     r8, [rbp+57h+var_70]
0x140153a7f  call    QosFlowNeedQueueFeedback
0x140153a84  test    al, al
0x140153a86  jz      short loc_140153AF1
0x140153a88  test    rdi, rdi
0x140153a8b  jz      short loc_140153AF1
0x140153a8d  mov     rcx, [rdi]; Lock
0x140153a90  lea     rdx, [rbp+57h+LockState]; LockState
0x140153a94  mov     r8b, 1; Flags
0x140153a97  call    cs:__imp_NdisAcquireRWLockWrite
0x140153a9e  nop     dword ptr [rax+rax+00h]
0x140153aa3  lea     r15, [rdi+8]
0x140153aa7  mov     edx, r12d
0x140153aaa  mov     rcx, r15
0x140153aad  call    QosLineNeedSignal
0x140153ab2  test    al, al
0x140153ab4  jz      short loc_140153AC1
0x140153ab6  mov     edx, r12d
0x140153ab9  mov     rcx, r15
0x140153abc  call    QosLineSignalExternalEvent
0x140153ac1  lea     r8, [rbp+57h+var_70]
0x140153ac5  mov     rcx, r15
0x140153ac8  call    QosLineQueryQueueFeedback
0x140153acd  mov     rcx, [rdi]; Lock
0x140153ad0  lea     rdx, [rbp+57h+LockState]; LockState
0x140153ad4  call    cs:__imp_NdisReleaseRWLock
0x140153adb  nop     dword ptr [rax+rax+00h]
0x140153ae0  lea     rdx, [rbp+57h+var_70]
0x140153ae4  mov     rcx, r13
0x140153ae7  call    QosTbcAdjustSendWindow
0x140153aec  mov     r15, [rsp+110h+var_D8]
0x140153af1  lea     rax, [rbp+57h+var_C8]
0x140153af5  mov     edx, r12d
0x140153af8  lea     r9, [rbp+57h+var_D0]
0x140153afc  mov     [rsp+110h+var_F0], rax
0x140153b01  lea     r8, [rbp+57h+var_B8]
0x140153b05  mov     rcx, r13
0x140153b08  call    QosFlowProcessQueuedNetBufferLists
0x140153b0d  mov     r13d, 1
0x140153b13  test    al, al
0x140153b15  jz      short loc_140153B56
0x140153b17  mov     rax, [r14+80h]
0x140153b1e  mov     r8, [rax+18h]
0x140153b22  mov     rax, 624DD2F1A9FBE77h
0x140153b2c  mul     r8
0x140153b2f  sub     r8, rdx
0x140153b32  shr     r8, 1
0x140153b35  add     r8, rdx
0x140153b38  shr     r8, 7
0x140153b3c  mov     eax, r8d
0x140153b3f  sub     eax, dword ptr [rbp+57h+var_A8]
0x140153b42  test    eax, eax
0x140153b44  lea     ecx, [r8+1]
0x140153b48  cmovg   ecx, r8d
0x140153b4c  test    ecx, ecx
0x140153b4e  cmovz   ecx, r13d
0x140153b52  mov     [r14+14h], ecx
0x140153b56  lea     rdx, [rbp+57h+LockHandle]
0x140153b5a  mov     rcx, rbx
0x140153b5d  call    RtlAcquireWriteLockAtDpcLevel
0x140153b62  mov     rcx, [rbx+0A0h]
0x140153b69  mov     rdx, r14
0x140153b6c  call    cs:__imp_RtlReturnTimerWheelEntry
0x140153b73  nop     dword ptr [rax+rax+00h]
0x140153b78  mov     rax, [r14]
0x140153b7b  mov     rcx, [rbx+0A0h]
0x140153b82  mov     [rbp+57h+var_78], rax
0x140153b86  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x140153b8d  nop     dword ptr [rax+rax+00h]
0x140153b92  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140153b96  mov     r14, rax
0x140153b99  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140153ba0  nop     dword ptr [rax+rax+00h]
0x140153ba5  mov     r8, [rbp+57h+var_C8]
0x140153ba9  mov     rax, [rsi+1D8h]
0x140153bb0  mov     [rsp+110h+var_D8], rax
0x140153bb5  test    r8, r8
0x140153bb8  jz      short loc_140153BD1
0x140153bba  lea     r9, [rbp+57h+var_C0]
0x140153bbe  mov     dword ptr [rsp+110h+var_F0], 0E0002024h
0x140153bc6  mov     rdx, rdi
0x140153bc9  mov     rcx, rsi
0x140153bcc  call    VmsScQosDropNbls
0x140153bd1  mov     rcx, [r15+38h]; Lock
0x140153bd5  lea     rdx, [rsp+110h+var_E0]; LockState
0x140153bda  call    cs:__imp_NdisReleaseRWLock
0x140153be1  nop     dword ptr [rax+rax+00h]
0x140153be6  mov     r15, [rbp+57h+var_C0]
0x140153bea  test    r15, r15
0x140153bed  jz      short loc_140153BFA
0x140153bef  mov     edx, r13d
0x140153bf2  mov     rcx, r15
0x140153bf5  call    VmsNblHelperRefCountDecrementMany
0x140153bfa  mov     r13, [rbp+57h+var_B8]
0x140153bfe  test    r13, r13
0x140153c01  jz      loc_140153CF3
0x140153c07  lea     r15, [rdi+8]
0x140153c0b  mov     edx, r12d
0x140153c0e  mov     rcx, r15
0x140153c11  call    QosLineNeedSignal
0x140153c16  test    al, al
0x140153c18  jz      short loc_140153C4E
0x140153c1a  mov     rcx, [rdi]; Lock
0x140153c1d  lea     rdx, [rbp+57h+LockState]; LockState
0x140153c21  mov     r8b, 1; Flags
0x140153c24  call    cs:__imp_NdisAcquireRWLockWrite
0x140153c2b  nop     dword ptr [rax+rax+00h]
0x140153c30  mov     edx, r12d
0x140153c33  mov     rcx, r15
0x140153c36  call    QosLineSignalExternalEvent
0x140153c3b  mov     rcx, [rdi]; Lock
0x140153c3e  lea     rdx, [rbp+57h+LockState]; LockState
0x140153c42  call    cs:__imp_NdisReleaseRWLock
0x140153c49  nop     dword ptr [rax+rax+00h]
0x140153c4e  lea     rax, [rbp+57h+var_C8]
0x140153c52  mov     r8, r13
0x140153c55  mov     [rsp+110h+var_E8], rax
0x140153c5a  mov     rcx, r15
0x140153c5d  lea     rax, [rbp+57h+var_B0]
0x140153c61  mov     [rsp+110h+var_F0], rax
0x140153c66  call    QosLineSendNetBufferLists
0x140153c6b  mov     r15, [rsp+110h+var_D8]
0x140153c70  test    r15, r15
0x140153c73  jnz     short loc_140153CA8
0x140153c75  lea     ecx, [r15+13h]
0x140153c79  lea     rax, aNicNull_0; "nic != NULL"
0x140153c80  mov     r9d, ecx
0x140153c83  mov     [rsp+110h+var_E8], rax
0x140153c88  mov     r8d, ecx
0x140153c8b  mov     rcx, cs:VmsIfrLog
0x140153c92  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153c99  mov     [rsp+110h+var_F0], rax
0x140153c9e  call    WPP_RECORDER_SF_s
0x140153ca3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "nic != ((void *)0)")
0x140153ca8  mov     r8, [rbp+57h+var_B0]
0x140153cac  lea     r9, [rsp+110h+var_D8]
0x140153cb1  mov     rdx, rdi
0x140153cb4  mov     [rsp+110h+var_D8], 0
0x140153cbd  mov     rcx, rsi
0x140153cc0  call    VmsScQosCompleteNbls
0x140153cc5  mov     r8, [rsp+110h+var_D8]
0x140153cca  test    r8, r8
0x140153ccd  jz      short loc_140153CF3
0x140153ccf  xor     r9d, r9d
0x140153cd2  mov     rax, r8
0x140153cd5  test    r8, r8
0x140153cd8  jz      short loc_140153CE5
0x140153cda  mov     rax, [rax]
0x140153cdd  inc     r9d
0x140153ce0  test    rax, rax
0x140153ce3  jnz     short loc_140153CDA
0x140153ce5  mov     ecx, [rsi+1D0h]
0x140153ceb  mov     rdx, r15
0x140153cee  call    VmsScQospSendProcessedNbls
0x140153cf3  mov     rax, [rbp+57h+var_80]
0x140153cf7  cmp     [rbp+57h+var_78], rax
0x140153cfb  jnz     short loc_140153D05
0x140153cfd  mov     rcx, rsi
0x140153d00  call    VmsScQospDereferenceFlow
0x140153d05  lea     rdx, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153d0c  mov     r13d, 1
0x140153d12  test    r14, r14
0x140153d15  jnz     loc_140153996
0x140153d1b  mov     rdi, [rbp+57h+var_A8]
0x140153d1f  mov     rsi, [rbp+57h+var_A0]
0x140153d23  lea     rdx, [rbp+57h+LockHandle]
0x140153d27  mov     rcx, rbx
0x140153d2a  call    RtlAcquireWriteLockAtDpcLevel
0x140153d2f  mov     rcx, [rbx+0A0h]
  ... truncated ...
```
