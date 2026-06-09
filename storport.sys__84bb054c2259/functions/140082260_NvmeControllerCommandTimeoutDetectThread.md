# NvmeControllerCommandTimeoutDetectThread

- ea: `0x140082260`
- end: `0x140082518`
- name: `NvmeControllerCommandTimeoutDetectThread`
- size: `696`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400759bc`
- `0x140082260`
- `0x140082520`
- `0x140082798`
- `0x1400e7d6c`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14008244e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14008244e`
- `ntoskrnl!KeCancelTimer` at `0x140082330`
- `ntoskrnl!KeCancelTimer` at `0x1400823f4`
- `ntoskrnl!KeCancelTimer` at `0x140082330`
- `ntoskrnl!KeCancelTimer` at `0x1400823f4`
- `ntoskrnl!IoQueueWorkItem` at `0x1400823b0`
- `ntoskrnl!IoQueueWorkItem` at `0x1400823b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008229f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400824cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008229f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400824cc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400824f1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400824f1`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14008249d`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14008249d`
- `ntoskrnl!KeClearEvent` at `0x140082390`
- `ntoskrnl!KeClearEvent` at `0x140082390`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14008234b`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14008240f`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14008234b`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14008240f`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400824ff`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400824ff`

## pseudocode

```c
NTSTATUS __fastcall NvmeControllerCommandTimeoutDetectThread(char *DeferredContext)
{
  __int64 v2; // rax
  int v3; // eax
  ULONGLONG *v4; // rdi

  if ( (int)NvmeControllerAcquireRundown() >= 0 )
  {
    KeWaitForSingleObject((PVOID)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 200LL), Executive, 0, 0, 0);
    v2 = *((_QWORD *)DeferredContext + 17);
    if ( (v2 & 0x80000000) == 0 )
    {
      while ( 1 )
      {
        if ( (v2 & 2) != 0 && *((_DWORD *)DeferredContext + 142) == 4 )
          goto LABEL_18;
        _interlockedbittestandreset((volatile signed __int32 *)DeferredContext + 270, 3u);
        if ( **((_DWORD **)DeferredContext + 164) )
          goto LABEL_18;
        v3 = NvmeControllerDetectCommandTimeout(DeferredContext) - 2;
        if ( !v3 )
          break;
        if ( v3 == 1 )
        {
          if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 192LL) )
          {
            KeCancelTimer((PKTIMER)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 128LL));
            KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 64LL));
            _InterlockedCompareExchange(
              (volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 192LL),
              0,
              1);
          }
          if ( (DeferredContext[136] & 2) == 0 )
          {
            NvmeControllerResetRecovery(DeferredContext);
LABEL_16:
            v4 = *(ULONGLONG **)(*((_QWORD *)DeferredContext + 164) + 40LL);
            *v4 = KeQueryUnbiasedInterruptTime();
            if ( !_InterlockedCompareExchange(
                    (volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 192LL),
                    1,
                    0) )
              KeSetCoalescableTimer(
                (PKTIMER)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 128LL),
                (LARGE_INTEGER)-50000000LL,
                0x7D0u,
                0x12Cu,
                (PKDPC)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 64LL));
            goto LABEL_18;
          }
          *((_DWORD *)DeferredContext + 142) = 4;
          *((_DWORD *)DeferredContext + 304) = 39;
          KeClearEvent((PRKEVENT)(DeferredContext + 232));
          IoQueueWorkItem(
            *((PIO_WORKITEM *)DeferredContext + 20),
            NvmeAdapterFabricNvmeControllerRebuildAssociationWork,
            DelayedWorkQueue,
            DeferredContext);
        }
LABEL_18:
        KeWaitForSingleObject(
          (PVOID)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 200LL),
          Executive,
          0,
          0,
          0);
        v2 = *((_QWORD *)DeferredContext + 17);
        if ( (v2 & 0x80000000) != 0 )
          goto LABEL_19;
      }
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 192LL) )
      {
        KeCancelTimer((PKTIMER)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 128LL));
        KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 64LL));
        _InterlockedCompareExchange(
          (volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 40LL) + 192LL),
          0,
          1);
      }
      NvmeDeviceHierarchicalReset(DeferredContext, *(PSLIST_HEADER *)(*((_QWORD *)DeferredContext + 164) + 32LL));
      goto LABEL_16;
    }
LABEL_19:
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeferredContext + 69));
  }
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140082260  push    rbp
0x140082262  push    rsi
0x140082263  push    rdi
0x140082264  push    r12
0x140082266  push    r14
0x140082268  sub     rsp, 30h
0x14008226c  mov     rsi, rcx
0x14008226f  call    NvmeControllerAcquireRundown
0x140082274  test    eax, eax
0x140082276  js      loc_1400824FD
0x14008227c  mov     rax, [rsi+520h]
0x140082283  xor     r9d, r9d; Alertable
0x140082286  xor     r8d, r8d; WaitMode
0x140082289  mov     [rsp+58h+Timeout], 0; Timeout
0x140082292  xor     edx, edx; WaitReason
0x140082294  mov     rcx, [rax+28h]
0x140082298  add     rcx, 0C8h; Object
0x14008229f  call    cs:__imp_KeWaitForSingleObject
0x1400822a6  nop     dword ptr [rax+rax+00h]
0x1400822ab  mov     rax, [rsi+88h]
0x1400822b2  bt      rax, 1Fh
0x1400822b7  jb      loc_1400824EA
0x1400822bd  mov     ebp, 1
0x1400822c2  mov     r14d, 0C0h
0x1400822c8  test    al, 2
0x1400822ca  jz      short loc_1400822D9
0x1400822cc  cmp     dword ptr [rsi+238h], 4
0x1400822d3  jz      loc_1400824A9
0x1400822d9  lock btr dword ptr [rsi+438h], 3
0x1400822e2  mov     rax, [rsi+520h]
0x1400822e9  mov     ecx, [rax]
0x1400822eb  test    ecx, ecx
0x1400822ed  jnz     loc_1400824A9
0x1400822f3  mov     rcx, rsi
0x1400822f6  call    NvmeControllerDetectCommandTimeout
0x1400822fb  sub     eax, 2
0x1400822fe  jz      loc_1400823D0
0x140082304  cmp     eax, ebp
0x140082306  jnz     loc_1400824A9
0x14008230c  mov     rax, [rsi+520h]
0x140082313  mov     rcx, [rax+28h]
0x140082317  mov     eax, [rcx+0C0h]
0x14008231d  test    eax, eax
0x14008231f  jz      short loc_14008236C
0x140082321  mov     rax, [rsi+520h]
0x140082328  mov     rcx, [rax+28h]
0x14008232c  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x140082330  call    cs:__imp_KeCancelTimer
0x140082337  nop     dword ptr [rax+rax+00h]
0x14008233c  mov     rax, [rsi+520h]
0x140082343  mov     rcx, [rax+28h]
0x140082347  add     rcx, 40h ; '@'; Dpc
0x14008234b  call    cs:__imp_KeRemoveQueueDpc
0x140082352  nop     dword ptr [rax+rax+00h]
0x140082357  mov     rax, [rsi+520h]
0x14008235e  xor     ecx, ecx
0x140082360  mov     rdx, [rax+28h]
0x140082364  mov     eax, ebp
0x140082366  lock cmpxchg [rdx+r14], ecx
0x14008236c  test    byte ptr [rsi+88h], 2
0x140082373  jz      short loc_1400823C1
0x140082375  lea     rcx, [rsi+0E8h]; Event
0x14008237c  mov     dword ptr [rsi+238h], 4
0x140082386  mov     dword ptr [rsi+4C0h], 27h ; '''
0x140082390  call    cs:__imp_KeClearEvent
0x140082397  nop     dword ptr [rax+rax+00h]
0x14008239c  mov     rcx, [rsi+0A0h]; IoWorkItem
0x1400823a3  lea     rdx, NvmeAdapterFabricNvmeControllerRebuildAssociationWork; WorkerRoutine
0x1400823aa  mov     r9, rsi; Context
0x1400823ad  mov     r8d, ebp; QueueType
0x1400823b0  call    cs:__imp_IoQueueWorkItem
0x1400823b7  nop     dword ptr [rax+rax+00h]
0x1400823bc  jmp     loc_1400824A9
0x1400823c1  mov     edx, 3
0x1400823c6  mov     rcx, rsi; DeferredContext
0x1400823c9  call    NvmeControllerResetRecovery
0x1400823ce  jmp     short loc_140082443
0x1400823d0  mov     rax, [rsi+520h]
0x1400823d7  mov     rcx, [rax+28h]
0x1400823db  mov     eax, [rcx+0C0h]
0x1400823e1  test    eax, eax
0x1400823e3  jz      short loc_140082430
0x1400823e5  mov     rax, [rsi+520h]
0x1400823ec  mov     rcx, [rax+28h]
0x1400823f0  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x1400823f4  call    cs:__imp_KeCancelTimer
0x1400823fb  nop     dword ptr [rax+rax+00h]
0x140082400  mov     rax, [rsi+520h]
0x140082407  mov     rcx, [rax+28h]
0x14008240b  add     rcx, 40h ; '@'; Dpc
0x14008240f  call    cs:__imp_KeRemoveQueueDpc
0x140082416  nop     dword ptr [rax+rax+00h]
0x14008241b  mov     rax, [rsi+520h]
0x140082422  xor     ecx, ecx
0x140082424  mov     rdx, [rax+28h]
0x140082428  mov     eax, ebp
0x14008242a  lock cmpxchg [rdx+r14], ecx
0x140082430  mov     rdx, [rsi+520h]
0x140082437  mov     rcx, rsi; DeferredContext
0x14008243a  mov     rdx, [rdx+20h]; ListHead
0x14008243e  call    NvmeDeviceHierarchicalReset
0x140082443  mov     rax, [rsi+520h]
0x14008244a  mov     rdi, [rax+28h]
0x14008244e  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140082455  nop     dword ptr [rax+rax+00h]
0x14008245a  mov     [rdi], rax
0x14008245d  mov     rax, [rsi+520h]
0x140082464  mov     rcx, [rax+28h]
0x140082468  xor     eax, eax
0x14008246a  lock cmpxchg [rcx+r14], ebp
0x140082470  jnz     short loc_1400824A9
0x140082472  mov     rax, [rsi+520h]
0x140082479  mov     r9d, 12Ch; TolerableDelay
0x14008247f  mov     r8d, 7D0h; Period
0x140082485  mov     rdx, 0FFFFFFFFFD050F80h; DueTime
0x14008248c  mov     rcx, [rax+28h]
0x140082490  lea     rax, [rcx+40h]
0x140082494  sub     rcx, 0FFFFFFFFFFFFFF80h; Timer
0x140082498  mov     [rsp+58h+Timeout], rax; Dpc
0x14008249d  call    cs:__imp_KeSetCoalescableTimer
0x1400824a4  nop     dword ptr [rax+rax+00h]
0x1400824a9  mov     rax, [rsi+520h]
0x1400824b0  xor     r9d, r9d; Alertable
0x1400824b3  xor     r8d, r8d; WaitMode
0x1400824b6  mov     [rsp+58h+Timeout], 0; Timeout
0x1400824bf  xor     edx, edx; WaitReason
0x1400824c1  mov     rcx, [rax+28h]
0x1400824c5  add     rcx, 0C8h; Object
0x1400824cc  call    cs:__imp_KeWaitForSingleObject
0x1400824d3  nop     dword ptr [rax+rax+00h]
0x1400824d8  mov     rax, [rsi+88h]
0x1400824df  bt      rax, 1Fh
0x1400824e4  jnb     loc_1400822C8
0x1400824ea  mov     rcx, [rsi+228h]; RunRefCacheAware
0x1400824f1  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400824f8  nop     dword ptr [rax+rax+00h]
0x1400824fd  xor     ecx, ecx; ExitStatus
0x1400824ff  call    cs:__imp_PsTerminateSystemThread
0x140082506  nop     dword ptr [rax+rax+00h]
0x14008250b  add     rsp, 30h
0x14008250f  pop     r14
0x140082511  pop     r12
0x140082513  pop     rdi
0x140082514  pop     rsi
0x140082515  pop     rbp
0x140082516  retn
```
