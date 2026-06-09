# VmsScQospTimeoutHandler

- ea: `0x1401538b0`
- end: `0x140153e3d`
- name: `VmsScQospTimeoutHandler`
- size: `1421`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015320c`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14006b084`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x140151a3c`
- `0x140152c50`
- `0x140153188`
- `0x1401535e4`
- `0x1401538b0`
- `0x1401b6c0c`
- `0x1401b6c58`
- `0x1401b7284`
- `0x1401b72f4`
- `0x1401b734c`
- `0x1401b738c`
- `0x1401b7fd0`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401539ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153c09`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153e14`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401539ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153c09`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140153e14`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401538f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401538f6`
- `ntoskrnl!KeCancelTimer` at `0x140153deb`
- `ntoskrnl!KeCancelTimer` at `0x140153deb`
- `NDIS!NdisReleaseRWLock` at `0x140153b44`
- `NDIS!NdisReleaseRWLock` at `0x140153c4a`
- `NDIS!NdisReleaseRWLock` at `0x140153cb2`
- `NDIS!NdisReleaseRWLock` at `0x140153b44`
- `NDIS!NdisReleaseRWLock` at `0x140153c4a`
- `NDIS!NdisReleaseRWLock` at `0x140153cb2`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153b07`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153c94`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153b07`
- `NDIS!NdisAcquireRWLockWrite` at `0x140153c94`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1401539a7`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153dbd`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1401539a7`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140153dbd`
- `NETIO!RtlSuspendTimerWheel` at `0x140153dd4`
- `NETIO!RtlSuspendTimerWheel` at `0x140153dd4`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401539c4`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401539c4`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401539d7`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153bf6`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401539d7`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140153bf6`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140153bdc`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140153bdc`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140153da6`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x140153da6`

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
0x1401538b0  push    rbp
0x1401538b2  push    rbx
0x1401538b3  push    rsi
0x1401538b4  push    rdi
0x1401538b5  push    r12
0x1401538b7  push    r13
0x1401538b9  push    r14
0x1401538bb  push    r15
0x1401538bd  lea     rbp, [rsp-1Fh]
0x1401538c2  sub     rsp, 0D8h
0x1401538c9  xor     eax, eax
0x1401538cb  xorps   xmm0, xmm0
0x1401538ce  xor     ecx, ecx; ProcNumber
0x1401538d0  mov     [rbp+57h+var_50], eax
0x1401538d3  movups  [rbp+57h+var_70], xmm0
0x1401538d7  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1401538db  mov     rbx, rdx
0x1401538de  movups  [rbp+57h+var_60], xmm0
0x1401538e2  mov     word ptr [rsp+110h+var_E0.OldIrql], ax
0x1401538e7  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1401538eb  mov     [rsp+110h+var_E0.Flags], al
0x1401538ef  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x1401538f3  mov     [rbp+57h+LockState.Flags], al
0x1401538f6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401538fd  nop     dword ptr [rax+rax+00h]
0x140153902  mov     r13d, 1
0x140153908  mov     r12d, eax
0x14015390b  mov     r8b, r13b
0x14015390e  mov     dl, r13b
0x140153911  mov     ecx, eax
0x140153913  call    QosTimerGetCurrentTime
0x140153918  mov     rsi, rax
0x14015391b  mov     [rbp+57h+var_A0], rax
0x14015391f  xor     r15d, r15d
0x140153922  mov     [rbp+57h+var_B8], 0
0x14015392a  mov     rax, 624DD2F1A9FBE77h
0x140153934  mov     [rbp+57h+var_C8], 0
0x14015393c  mul     rsi
0x14015393f  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x140153946  mov     rdi, rsi
0x140153949  sub     rdi, rdx
0x14015394c  mov     [rbp+57h+var_B0], 0
0x140153954  shr     rdi, 1
0x140153957  mov     ecx, r12d
0x14015395a  shl     rcx, 6
0x14015395e  add     rdi, rdx
0x140153961  shr     rdi, 7
0x140153965  lea     rdx, [rbp+57h+LockHandle]
0x140153969  mov     [rbp+57h+var_A8], rdi
0x14015396d  mov     [rbp+57h+var_C0], r15
0x140153971  add     [rcx+rax+10h], r13d
0x140153976  mov     rcx, rbx
0x140153979  mov     [rbp+57h+var_D0], r15d
0x14015397d  call    RtlAcquireWriteLockAtDpcLevel
0x140153982  mov     eax, [rbx+0ACh]
0x140153988  mov     ecx, eax
0x14015398a  shr     ecx, 1
0x14015398c  and     eax, 0FFFFFFFEh
0x14015398f  not     ecx
0x140153991  mov     [rbx+10h], rsi
0x140153995  and     ecx, r13d
0x140153998  or      ecx, eax
0x14015399a  mov     [rbx+0ACh], ecx
0x1401539a0  mov     rcx, [rbx+0A0h]
0x1401539a7  call    cs:__imp_RtlIsTimerWheelSuspended
0x1401539ae  nop     dword ptr [rax+rax+00h]
0x1401539b3  test    al, al
0x1401539b5  jnz     loc_140153D9F
0x1401539bb  mov     rcx, [rbx+0A0h]
0x1401539c2  mov     edx, edi
0x1401539c4  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x1401539cb  nop     dword ptr [rax+rax+00h]
0x1401539d0  mov     rcx, [rbx+0A0h]
0x1401539d7  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x1401539de  nop     dword ptr [rax+rax+00h]
0x1401539e3  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1401539e7  mov     r14, rax
0x1401539ea  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1401539f1  nop     dword ptr [rax+rax+00h]
0x1401539f6  test    r14, r14
0x1401539f9  jz      loc_140153D93
0x1401539ff  lea     rdx, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153a06  lea     rsi, [r14-8]
0x140153a0a  mov     [rbp+57h+var_80], r14
0x140153a0e  mov     eax, [rsi]
0x140153a10  lea     rcx, [rax+rax*2]
0x140153a14  shl     rcx, 6
0x140153a18  add     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x140153a1f  cmp     rcx, rbx
0x140153a22  jz      short loc_140153A66
0x140153a24  mov     rcx, cs:VmsIfrLog
0x140153a2b  lea     rax, aVmstimerunitsF; "&VmsTimerUnits[flow->TimerUnitIndex] =="...
0x140153a32  mov     r9d, 11h
0x140153a38  mov     [rsp+110h+var_E8], rax
0x140153a3d  mov     [rsp+110h+var_F0], rdx
0x140153a42  lea     r8d, [r9+2]
0x140153a46  call    WPP_RECORDER_SF_s
0x140153a4b  mov     eax, [rsi]
0x140153a4d  lea     rcx, [rax+rax*2]
0x140153a51  shl     rcx, 6
0x140153a55  add     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x140153a5c  cmp     rcx, rbx
0x140153a5f  jz      short loc_140153A66
0x140153a61  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "&VmsTimerUnits[flow->TimerUnitIndex] == timerUnit")
0x140153a66  mov     r15, [rsi+1E0h]
0x140153a6d  lea     rdx, [rsp+110h+var_E0]
0x140153a72  mov     rcx, r15
0x140153a75  mov     [rsp+110h+var_D8], r15
0x140153a7a  mov     r8b, r13b
0x140153a7d  call    VmsOmObjectLockExclusive
0x140153a82  cmp     [rsi+1D0h], r13d
0x140153a89  jnz     short loc_140153A9B
0x140153a8b  mov     rax, [r15+4D8h]
0x140153a92  mov     rdi, [rax+21E8h]
0x140153a99  jmp     short loc_140153AA2
0x140153a9b  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140153aa2  test    rdi, rdi
0x140153aa5  jnz     short loc_140153AD8
0x140153aa7  mov     rcx, cs:VmsIfrLog
0x140153aae  lea     rax, aLineNull; "line != NULL"
0x140153ab5  mov     [rsp+110h+var_E8], rax
0x140153aba  lea     r9d, [rdi+12h]
0x140153abe  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153ac5  lea     r8d, [rdi+13h]
0x140153ac9  mov     [rsp+110h+var_F0], rax
0x140153ace  call    WPP_RECORDER_SF_s
0x140153ad3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "line != ((void *)0)")
0x140153ad8  mov     rdx, [rbp+57h+var_A0]
0x140153adc  lea     r13, [rsi+28h]
0x140153ae0  mov     rcx, r13
0x140153ae3  mov     dword ptr [r14+14h], 0
0x140153aeb  lea     r8, [rbp+57h+var_70]
0x140153aef  call    QosFlowNeedQueueFeedback
0x140153af4  test    al, al
0x140153af6  jz      short loc_140153B61
0x140153af8  test    rdi, rdi
0x140153afb  jz      short loc_140153B61
0x140153afd  mov     rcx, [rdi]; Lock
0x140153b00  lea     rdx, [rbp+57h+LockState]; LockState
0x140153b04  mov     r8b, 1; Flags
0x140153b07  call    cs:__imp_NdisAcquireRWLockWrite
0x140153b0e  nop     dword ptr [rax+rax+00h]
0x140153b13  lea     r15, [rdi+8]
0x140153b17  mov     edx, r12d
0x140153b1a  mov     rcx, r15
0x140153b1d  call    QosLineNeedSignal
0x140153b22  test    al, al
0x140153b24  jz      short loc_140153B31
0x140153b26  mov     edx, r12d
0x140153b29  mov     rcx, r15
0x140153b2c  call    QosLineSignalExternalEvent
0x140153b31  lea     r8, [rbp+57h+var_70]
0x140153b35  mov     rcx, r15
0x140153b38  call    QosLineQueryQueueFeedback
0x140153b3d  mov     rcx, [rdi]; Lock
0x140153b40  lea     rdx, [rbp+57h+LockState]; LockState
0x140153b44  call    cs:__imp_NdisReleaseRWLock
0x140153b4b  nop     dword ptr [rax+rax+00h]
0x140153b50  lea     rdx, [rbp+57h+var_70]
0x140153b54  mov     rcx, r13
0x140153b57  call    QosTbcAdjustSendWindow
0x140153b5c  mov     r15, [rsp+110h+var_D8]
0x140153b61  lea     rax, [rbp+57h+var_C8]
0x140153b65  mov     edx, r12d
0x140153b68  lea     r9, [rbp+57h+var_D0]
0x140153b6c  mov     [rsp+110h+var_F0], rax
0x140153b71  lea     r8, [rbp+57h+var_B8]
0x140153b75  mov     rcx, r13
0x140153b78  call    QosFlowProcessQueuedNetBufferLists
0x140153b7d  mov     r13d, 1
0x140153b83  test    al, al
0x140153b85  jz      short loc_140153BC6
0x140153b87  mov     rax, [r14+80h]
0x140153b8e  mov     r8, [rax+18h]
0x140153b92  mov     rax, 624DD2F1A9FBE77h
0x140153b9c  mul     r8
0x140153b9f  sub     r8, rdx
0x140153ba2  shr     r8, 1
0x140153ba5  add     r8, rdx
0x140153ba8  shr     r8, 7
0x140153bac  mov     eax, r8d
0x140153baf  sub     eax, dword ptr [rbp+57h+var_A8]
0x140153bb2  test    eax, eax
0x140153bb4  lea     ecx, [r8+1]
0x140153bb8  cmovg   ecx, r8d
0x140153bbc  test    ecx, ecx
0x140153bbe  cmovz   ecx, r13d
0x140153bc2  mov     [r14+14h], ecx
0x140153bc6  lea     rdx, [rbp+57h+LockHandle]
0x140153bca  mov     rcx, rbx
0x140153bcd  call    RtlAcquireWriteLockAtDpcLevel
0x140153bd2  mov     rcx, [rbx+0A0h]
0x140153bd9  mov     rdx, r14
0x140153bdc  call    cs:__imp_RtlReturnTimerWheelEntry
0x140153be3  nop     dword ptr [rax+rax+00h]
0x140153be8  mov     rax, [r14]
0x140153beb  mov     rcx, [rbx+0A0h]
0x140153bf2  mov     [rbp+57h+var_78], rax
0x140153bf6  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x140153bfd  nop     dword ptr [rax+rax+00h]
0x140153c02  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140153c06  mov     r14, rax
0x140153c09  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140153c10  nop     dword ptr [rax+rax+00h]
0x140153c15  mov     r8, [rbp+57h+var_C8]
0x140153c19  mov     rax, [rsi+1D8h]
0x140153c20  mov     [rsp+110h+var_D8], rax
0x140153c25  test    r8, r8
0x140153c28  jz      short loc_140153C41
0x140153c2a  lea     r9, [rbp+57h+var_C0]
0x140153c2e  mov     dword ptr [rsp+110h+var_F0], 0E0002024h
0x140153c36  mov     rdx, rdi
0x140153c39  mov     rcx, rsi
0x140153c3c  call    VmsScQosDropNbls
0x140153c41  mov     rcx, [r15+38h]; Lock
0x140153c45  lea     rdx, [rsp+110h+var_E0]; LockState
0x140153c4a  call    cs:__imp_NdisReleaseRWLock
0x140153c51  nop     dword ptr [rax+rax+00h]
0x140153c56  mov     r15, [rbp+57h+var_C0]
0x140153c5a  test    r15, r15
0x140153c5d  jz      short loc_140153C6A
0x140153c5f  mov     edx, r13d
0x140153c62  mov     rcx, r15
0x140153c65  call    VmsNblHelperRefCountDecrementMany
0x140153c6a  mov     r13, [rbp+57h+var_B8]
0x140153c6e  test    r13, r13
0x140153c71  jz      loc_140153D63
0x140153c77  lea     r15, [rdi+8]
0x140153c7b  mov     edx, r12d
0x140153c7e  mov     rcx, r15
0x140153c81  call    QosLineNeedSignal
0x140153c86  test    al, al
0x140153c88  jz      short loc_140153CBE
0x140153c8a  mov     rcx, [rdi]; Lock
0x140153c8d  lea     rdx, [rbp+57h+LockState]; LockState
0x140153c91  mov     r8b, 1; Flags
0x140153c94  call    cs:__imp_NdisAcquireRWLockWrite
0x140153c9b  nop     dword ptr [rax+rax+00h]
0x140153ca0  mov     edx, r12d
0x140153ca3  mov     rcx, r15
0x140153ca6  call    QosLineSignalExternalEvent
0x140153cab  mov     rcx, [rdi]; Lock
0x140153cae  lea     rdx, [rbp+57h+LockState]; LockState
0x140153cb2  call    cs:__imp_NdisReleaseRWLock
0x140153cb9  nop     dword ptr [rax+rax+00h]
0x140153cbe  lea     rax, [rbp+57h+var_C8]
0x140153cc2  mov     r8, r13
0x140153cc5  mov     [rsp+110h+var_E8], rax
0x140153cca  mov     rcx, r15
0x140153ccd  lea     rax, [rbp+57h+var_B0]
0x140153cd1  mov     [rsp+110h+var_F0], rax
0x140153cd6  call    QosLineSendNetBufferLists
0x140153cdb  mov     r15, [rsp+110h+var_D8]
0x140153ce0  test    r15, r15
0x140153ce3  jnz     short loc_140153D18
0x140153ce5  lea     ecx, [r15+13h]
0x140153ce9  lea     rax, aNicNull_0; "nic != NULL"
0x140153cf0  mov     r9d, ecx
0x140153cf3  mov     [rsp+110h+var_E8], rax
0x140153cf8  mov     r8d, ecx
0x140153cfb  mov     rcx, cs:VmsIfrLog
0x140153d02  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153d09  mov     [rsp+110h+var_F0], rax
0x140153d0e  call    WPP_RECORDER_SF_s
0x140153d13  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "nic != ((void *)0)")
0x140153d18  mov     r8, [rbp+57h+var_B0]
0x140153d1c  lea     r9, [rsp+110h+var_D8]
0x140153d21  mov     rdx, rdi
0x140153d24  mov     [rsp+110h+var_D8], 0
0x140153d2d  mov     rcx, rsi
0x140153d30  call    VmsScQosCompleteNbls
0x140153d35  mov     r8, [rsp+110h+var_D8]
0x140153d3a  test    r8, r8
0x140153d3d  jz      short loc_140153D63
0x140153d3f  xor     r9d, r9d
0x140153d42  mov     rax, r8
0x140153d45  test    r8, r8
0x140153d48  jz      short loc_140153D55
0x140153d4a  mov     rax, [rax]
0x140153d4d  inc     r9d
0x140153d50  test    rax, rax
0x140153d53  jnz     short loc_140153D4A
0x140153d55  mov     ecx, [rsi+1D0h]
0x140153d5b  mov     rdx, r15
0x140153d5e  call    VmsScQospSendProcessedNbls
0x140153d63  mov     rax, [rbp+57h+var_80]
0x140153d67  cmp     [rbp+57h+var_78], rax
0x140153d6b  jnz     short loc_140153D75
0x140153d6d  mov     rcx, rsi
0x140153d70  call    VmsScQospDereferenceFlow
0x140153d75  lea     rdx, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140153d7c  mov     r13d, 1
0x140153d82  test    r14, r14
0x140153d85  jnz     loc_140153A06
0x140153d8b  mov     rdi, [rbp+57h+var_A8]
0x140153d8f  mov     rsi, [rbp+57h+var_A0]
0x140153d93  lea     rdx, [rbp+57h+LockHandle]
0x140153d97  mov     rcx, rbx
0x140153d9a  call    RtlAcquireWriteLockAtDpcLevel
0x140153d9f  mov     rcx, [rbx+0A0h]
  ... truncated ...
```
