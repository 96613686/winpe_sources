# IppGetThreadCompartmentInfo

- ea: `0x14004b9c0`
- end: `0x14004bb6e`
- name: `IppGetThreadCompartmentInfo`
- size: `430`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013420`
- `0x140048cf0`
- `0x14004931c`
- `0x140049a00`
- `0x14004a640`
- `0x14004b7e0`
- `0x1400e1cb0`
- `0x1400ef300`
- `0x1400f5f60`
- `0x1401145b0`
- `0x14013e150`
- `0x140140050`

## callees

- `0x14004b9c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004ba1f`
- `ntoskrnl!KfRaiseIrql` at `0x14004ba1f`
- `ntoskrnl!KeLowerIrql` at `0x14004bad0`
- `ntoskrnl!KeLowerIrql` at `0x14004bb54`
- `ntoskrnl!KeLowerIrql` at `0x14004bad0`
- `ntoskrnl!KeLowerIrql` at `0x14004bb54`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bb32`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bb32`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004ba61`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004ba61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004ba76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004ba76`
- `ntoskrnl!KeTestSpinLock` at `0x14004ba45`
- `ntoskrnl!KeTestSpinLock` at `0x14004ba45`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004b9ec`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004b9ec`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004ba08`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004ba08`

## pseudocode

```c
void __fastcall IppGetThreadCompartmentInfo(__int64 a1, __int64 a2)
{
  int ThreadObjectCompartmentId; // esi
  KIRQL v5; // r15
  _QWORD **v6; // rdx
  _QWORD *i; // rax
  _QWORD *v8; // rbx
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), a2, a2 + 4);
  ThreadObjectCompartmentId = *(_DWORD *)(a2 + 4);
  if ( !ThreadObjectCompartmentId )
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v5 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 19888));
  if ( !KeTestSpinLock((PKSPIN_LOCK)(a1 + 19880)) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 19888));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 19880), &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 19888));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v6 = (_QWORD **)(*(_QWORD *)(a1 + 19872)
                 + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(a1 + 19868) - 1)));
  for ( i = *v6; ; i = (_QWORD *)*i )
  {
    if ( i == v6 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 19888));
      KeLowerIrql(v5);
      return;
    }
    v8 = i - 6;
    if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
      break;
  }
  if ( _InterlockedIncrement64(v8 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 19888));
  KeLowerIrql(v5);
  if ( v8 )
  {
    *(_OWORD *)(a2 + 8) = *(_OWORD *)((char *)v8 + 4);
    v9 = _InterlockedExchangeAdd64(v8 + 4, 0xFFFFFFFFFFFFFFFFuLL);
    v10 = v9 <= 1;
    v11 = v9 - 1;
    if ( v10 )
    {
      if ( v11 )
        __fastfail(0xEu);
      IoQueueWorkItem((PIO_WORKITEM)v8[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v8);
    }
  }
}

```

## disassembly

```asm
0x14004b9c0  push    rbx
0x14004b9c2  push    rbp
0x14004b9c3  push    rsi
0x14004b9c4  push    rdi
0x14004b9c5  push    r14
0x14004b9c7  push    r15
0x14004b9c9  sub     rsp, 48h
0x14004b9cd  xorps   xmm0, xmm0
0x14004b9d0  lea     r8, [rdx+4]
0x14004b9d4  movups  xmmword ptr [rdx], xmm0
0x14004b9d7  xor     eax, eax
0x14004b9d9  mov     r14, rcx
0x14004b9dc  mov     [rdx+10h], rax
0x14004b9e0  mov     rbp, rdx
0x14004b9e3  mov     rcx, gs:188h
0x14004b9ec  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14004b9f3  nop     dword ptr [rax+rax+00h]
0x14004b9f8  mov     esi, [rbp+4]
0x14004b9fb  test    esi, esi
0x14004b9fd  jnz     short loc_14004BA16
0x14004b9ff  mov     rcx, gs:188h
0x14004ba08  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14004ba0f  nop     dword ptr [rax+rax+00h]
0x14004ba14  mov     esi, eax
0x14004ba16  mov     cl, 2; NewIrql
0x14004ba18  lea     rdi, [r14+4DA8h]
0x14004ba1f  call    cs:__imp_KfRaiseIrql
0x14004ba26  nop     dword ptr [rax+rax+00h]
0x14004ba2b  movzx   r15d, al
0x14004ba2f  xorps   xmm0, xmm0
0x14004ba32  xor     eax, eax
0x14004ba34  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14004ba39  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14004ba3e  lock inc dword ptr [rdi+8]
0x14004ba42  mov     rcx, rdi; SpinLock
0x14004ba45  call    cs:__imp_KeTestSpinLock
0x14004ba4c  nop     dword ptr [rax+rax+00h]
0x14004ba51  test    al, al
0x14004ba53  jnz     short loc_14004BA82
0x14004ba55  lock dec dword ptr [rdi+8]
0x14004ba59  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14004ba5e  mov     rcx, rdi; SpinLock
0x14004ba61  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004ba68  nop     dword ptr [rax+rax+00h]
0x14004ba6d  lock inc dword ptr [rdi+8]
0x14004ba71  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14004ba76  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004ba7d  nop     dword ptr [rax+rax+00h]
0x14004ba82  mov     edx, [r14+4D9Ch]
0x14004ba89  dec     edx
0x14004ba8b  mov     eax, esi
0x14004ba8d  and     rdx, rax
0x14004ba90  shl     rdx, 4
0x14004ba94  add     rdx, [r14+4DA0h]
0x14004ba9b  mov     rax, [rdx]
0x14004ba9e  cmp     rax, rdx
0x14004baa1  jz      loc_14004BB4C
0x14004baa7  cmp     [rax-30h], esi
0x14004baaa  lea     rbx, [rax-30h]
0x14004baae  jnz     short loc_14004BB16
0x14004bab0  mov     eax, 1
0x14004bab5  lock xadd [rbx+20h], rax
0x14004babb  inc     rax
0x14004babe  cmp     rax, 1
0x14004bac2  jle     loc_14004BB62
0x14004bac8  lock dec dword ptr [rdi+8]
0x14004bacc  movzx   ecx, r15b; NewIrql
0x14004bad0  call    cs:__imp_KeLowerIrql
0x14004bad7  nop     dword ptr [rax+rax+00h]
0x14004badc  test    rbx, rbx
0x14004badf  jz      short loc_14004BB08
0x14004bae1  movups  xmm0, xmmword ptr [rbx+4]
0x14004bae5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14004baec  movups  xmmword ptr [rbp+8], xmm0
0x14004baf0  lock xadd [rbx+20h], rax
0x14004baf6  sub     rax, 1
0x14004bafa  jg      short loc_14004BB08
0x14004bafc  test    rax, rax
0x14004baff  jz      short loc_14004BB1B
0x14004bb01  mov     ecx, 0Eh
0x14004bb06  int     29h; Win8: RtlFailFast(ecx)
0x14004bb08  add     rsp, 48h
0x14004bb0c  pop     r15
0x14004bb0e  pop     r14
0x14004bb10  pop     rdi
0x14004bb11  pop     rsi
0x14004bb12  pop     rbp
0x14004bb13  pop     rbx
0x14004bb14  retn
0x14004bb16  mov     rax, [rax]
0x14004bb19  jmp     short loc_14004BA9E
0x14004bb1b  mov     rcx, [rbx+80h]; IoWorkItem
0x14004bb22  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14004bb29  mov     r9, rbx; Context
0x14004bb2c  mov     r8d, 1; QueueType
0x14004bb32  call    cs:__imp_IoQueueWorkItem
0x14004bb39  nop     dword ptr [rax+rax+00h]
0x14004bb3e  add     rsp, 48h
0x14004bb42  pop     r15
0x14004bb44  pop     r14
0x14004bb46  pop     rdi
0x14004bb47  pop     rsi
0x14004bb48  pop     rbp
0x14004bb49  pop     rbx
0x14004bb4a  retn
0x14004bb4c  lock dec dword ptr [rdi+8]
0x14004bb50  movzx   ecx, r15b; NewIrql
0x14004bb54  call    cs:__imp_KeLowerIrql
0x14004bb5b  nop     dword ptr [rax+rax+00h]
0x14004bb60  jmp     short loc_14004BB08
0x14004bb62  mov     ecx, 0Eh
0x14004bb67  int     29h; Win8: RtlFailFast(ecx)
0x14004bb69  jmp     loc_14004BAC8
```
