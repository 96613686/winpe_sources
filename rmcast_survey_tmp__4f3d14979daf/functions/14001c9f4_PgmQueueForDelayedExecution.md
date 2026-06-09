# PgmQueueForDelayedExecution

- ea: `0x14001c9f4`
- end: `0x14001cb05`
- name: `PgmQueueForDelayedExecution`
- size: `273`
- prototype: `__int64 __fastcall(WORKER_THREAD_ROUTINE *, void *, struct _LIST_ENTRY *, __int64, char)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023b8`
- `0x1400067f4`
- `0x14000cf04`
- `0x140014540`

## callees

- `0x14001c9f4`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14001cacb`
- `ntoskrnl!ExQueueWorkItem` at `0x14001cacb`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca3c`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001caea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001caea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ca1f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ca1f`

## pseudocode

```c
__int64 __fastcall PgmQueueForDelayedExecution(
        WORKER_THREAD_ROUTINE *a1,
        void *a2,
        struct _LIST_ENTRY *a3,
        __int64 a4,
        char a5)
{
  KIRQL v5; // di
  unsigned int v9; // ebx
  struct _WORK_QUEUE_ITEM *Pool2; // rax
  _QWORD *p_Flink; // rdx
  _QWORD *ProcessorHistory; // rax

  v5 = 0;
  v9 = -1073741670;
  if ( !a5 )
    v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  Pool2 = (struct _WORK_QUEUE_ITEM *)ExAllocatePool2(64, 80, 846030672);
  if ( Pool2 )
  {
    p_Flink = &Pool2[1].List.Flink;
    Pool2[1].List.Blink = &Pool2[1].List;
    Pool2[1].List.Flink = &Pool2[1].List;
    Pool2[1].Parameter = a2;
    Pool2[2].List.Flink = a3;
    Pool2[2].List.Blink = 0;
    Pool2[1].WorkerRoutine = a1;
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument2 & 1) != 0 )
    {
      ProcessorHistory = (_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory;
      if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.ProcessorHistory != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcListEntry )
        __fastfail(3u);
      *p_Flink = &WPP_MAIN_CB.Dpc.DpcListEntry;
      p_Flink[1] = ProcessorHistory;
      *ProcessorHistory = p_Flink;
      WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)p_Flink;
    }
    else
    {
      ++HIDWORD(WPP_MAIN_CB.Dpc.SystemArgument2);
      Pool2->WorkerRoutine = (PWORKER_THREAD_ROUTINE)PgmExecuteWorker;
      Pool2->Parameter = Pool2;
      Pool2->List.Flink = 0;
      ExQueueWorkItem(Pool2, DelayedWorkQueue);
    }
    v9 = 0;
  }
  if ( !a5 )
    KeReleaseSpinLock(&SpinLock, v5);
  return v9;
}

```

## disassembly

```asm
0x14001c9f4  push    rbx
0x14001c9f6  push    rbp
0x14001c9f7  push    rdi
0x14001c9f8  push    r14
0x14001c9fa  push    r15
0x14001c9fc  sub     rsp, 20h
0x14001ca00  xor     dil, dil
0x14001ca03  mov     rbp, r8
0x14001ca06  mov     r14, rdx
0x14001ca09  mov     r15, rcx
0x14001ca0c  mov     ebx, 0C000009Ah
0x14001ca11  cmp     [rsp+48h+arg_20], dil
0x14001ca16  jnz     short loc_14001CA2E
0x14001ca18  lea     rcx, SpinLock; SpinLock
0x14001ca1f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ca26  nop     dword ptr [rax+rax+00h]
0x14001ca2b  mov     dil, al
0x14001ca2e  mov     edx, 50h ; 'P'
0x14001ca33  mov     r8d, 326D6750h
0x14001ca39  lea     ecx, [rdx-10h]
0x14001ca3c  call    cs:__imp_ExAllocatePool2
0x14001ca43  nop     dword ptr [rax+rax+00h]
0x14001ca48  mov     rcx, rax; WorkItem
0x14001ca4b  test    rax, rax
0x14001ca4e  jz      loc_14001CAD9
0x14001ca54  lea     rdx, [rax+20h]
0x14001ca58  mov     [rdx+8], rdx
0x14001ca5c  mov     [rdx], rdx
0x14001ca5f  mov     [rax+38h], r14
0x14001ca63  mov     [rax+40h], rbp
0x14001ca67  mov     qword ptr [rax+48h], 0
0x14001ca6f  mov     [rax+30h], r15
0x14001ca73  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2
0x14001ca79  test    al, 1
0x14001ca7b  jz      short loc_14001CAAA
0x14001ca7d  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x14001ca84  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry
0x14001ca8b  cmp     [rax], rcx
0x14001ca8e  jz      short loc_14001CA97
0x14001ca90  mov     ecx, 3
0x14001ca95  int     29h; Win8: RtlFailFast(ecx)
0x14001ca97  mov     [rdx], rcx
0x14001ca9a  mov     [rdx+8], rax
0x14001ca9e  mov     [rax], rdx
0x14001caa1  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rdx
0x14001caa8  jmp     short loc_14001CAD7
0x14001caaa  inc     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2+4
0x14001cab0  lea     rax, PgmExecuteWorker
0x14001cab7  mov     edx, 1; QueueType
0x14001cabc  mov     [rcx+10h], rax
0x14001cac0  mov     [rcx+18h], rcx
0x14001cac4  mov     qword ptr [rcx], 0
0x14001cacb  call    cs:__imp_ExQueueWorkItem
0x14001cad2  nop     dword ptr [rax+rax+00h]
0x14001cad7  xor     ebx, ebx
0x14001cad9  cmp     [rsp+48h+arg_20], 0
0x14001cade  jnz     short loc_14001CAF6
0x14001cae0  mov     dl, dil; NewIrql
0x14001cae3  lea     rcx, SpinLock; SpinLock
0x14001caea  call    cs:__imp_KeReleaseSpinLock
0x14001caf1  nop     dword ptr [rax+rax+00h]
0x14001caf6  mov     eax, ebx
0x14001caf8  add     rsp, 20h
0x14001cafc  pop     r15
0x14001cafe  pop     r14
0x14001cb00  pop     rdi
0x14001cb01  pop     rbp
0x14001cb02  pop     rbx
0x14001cb03  retn
```
