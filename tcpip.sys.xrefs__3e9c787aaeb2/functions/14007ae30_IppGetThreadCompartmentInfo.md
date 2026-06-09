# IppGetThreadCompartmentInfo

- ea: `0x14007ae30`
- end: `0x14007afde`
- name: `IppGetThreadCompartmentInfo`
- size: `430`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004470`
- `0x14005151c`
- `0x140051c00`
- `0x14007ac50`
- `0x14007bbe0`
- `0x14007c640`
- `0x1400f6880`
- `0x1400fdf90`
- `0x14011e5c0`
- `0x14011edf0`
- `0x1401433f0`
- `0x140143f10`

## callees

- `0x14007ae30`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14007ae8f`
- `ntoskrnl!KfRaiseIrql` at `0x14007ae8f`
- `ntoskrnl!KeLowerIrql` at `0x14007af40`
- `ntoskrnl!KeLowerIrql` at `0x14007afc4`
- `ntoskrnl!KeLowerIrql` at `0x14007af40`
- `ntoskrnl!KeLowerIrql` at `0x14007afc4`
- `ntoskrnl!IoQueueWorkItem` at `0x14007afa2`
- `ntoskrnl!IoQueueWorkItem` at `0x14007afa2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14007aed1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14007aed1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14007aee6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14007aee6`
- `ntoskrnl!KeTestSpinLock` at `0x14007aeb5`
- `ntoskrnl!KeTestSpinLock` at `0x14007aeb5`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14007ae5c`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14007ae5c`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14007ae78`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14007ae78`

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
0x14007ae30  push    rbx
0x14007ae32  push    rbp
0x14007ae33  push    rsi
0x14007ae34  push    rdi
0x14007ae35  push    r14
0x14007ae37  push    r15
0x14007ae39  sub     rsp, 48h
0x14007ae3d  xorps   xmm0, xmm0
0x14007ae40  lea     r8, [rdx+4]
0x14007ae44  movups  xmmword ptr [rdx], xmm0
0x14007ae47  xor     eax, eax
0x14007ae49  mov     r14, rcx
0x14007ae4c  mov     [rdx+10h], rax
0x14007ae50  mov     rbp, rdx
0x14007ae53  mov     rcx, gs:188h
0x14007ae5c  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14007ae63  nop     dword ptr [rax+rax+00h]
0x14007ae68  mov     esi, [rbp+4]
0x14007ae6b  test    esi, esi
0x14007ae6d  jnz     short loc_14007AE86
0x14007ae6f  mov     rcx, gs:188h
0x14007ae78  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14007ae7f  nop     dword ptr [rax+rax+00h]
0x14007ae84  mov     esi, eax
0x14007ae86  mov     cl, 2; NewIrql
0x14007ae88  lea     rdi, [r14+4DA8h]
0x14007ae8f  call    cs:__imp_KfRaiseIrql
0x14007ae96  nop     dword ptr [rax+rax+00h]
0x14007ae9b  movzx   r15d, al
0x14007ae9f  xorps   xmm0, xmm0
0x14007aea2  xor     eax, eax
0x14007aea4  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14007aea9  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14007aeae  lock inc dword ptr [rdi+8]
0x14007aeb2  mov     rcx, rdi; SpinLock
0x14007aeb5  call    cs:__imp_KeTestSpinLock
0x14007aebc  nop     dword ptr [rax+rax+00h]
0x14007aec1  test    al, al
0x14007aec3  jnz     short loc_14007AEF2
0x14007aec5  lock dec dword ptr [rdi+8]
0x14007aec9  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14007aece  mov     rcx, rdi; SpinLock
0x14007aed1  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14007aed8  nop     dword ptr [rax+rax+00h]
0x14007aedd  lock inc dword ptr [rdi+8]
0x14007aee1  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14007aee6  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14007aeed  nop     dword ptr [rax+rax+00h]
0x14007aef2  mov     edx, [r14+4D9Ch]
0x14007aef9  dec     edx
0x14007aefb  mov     eax, esi
0x14007aefd  and     rdx, rax
0x14007af00  shl     rdx, 4
0x14007af04  add     rdx, [r14+4DA0h]
0x14007af0b  mov     rax, [rdx]
0x14007af0e  cmp     rax, rdx
0x14007af11  jz      loc_14007AFBC
0x14007af17  cmp     [rax-30h], esi
0x14007af1a  lea     rbx, [rax-30h]
0x14007af1e  jnz     short loc_14007AF86
0x14007af20  mov     eax, 1
0x14007af25  lock xadd [rbx+20h], rax
0x14007af2b  inc     rax
0x14007af2e  cmp     rax, 1
0x14007af32  jle     loc_14007AFD2
0x14007af38  lock dec dword ptr [rdi+8]
0x14007af3c  movzx   ecx, r15b; NewIrql
0x14007af40  call    cs:__imp_KeLowerIrql
0x14007af47  nop     dword ptr [rax+rax+00h]
0x14007af4c  test    rbx, rbx
0x14007af4f  jz      short loc_14007AF78
0x14007af51  movups  xmm0, xmmword ptr [rbx+4]
0x14007af55  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14007af5c  movups  xmmword ptr [rbp+8], xmm0
0x14007af60  lock xadd [rbx+20h], rax
0x14007af66  sub     rax, 1
0x14007af6a  jg      short loc_14007AF78
0x14007af6c  test    rax, rax
0x14007af6f  jz      short loc_14007AF8B
0x14007af71  mov     ecx, 0Eh
0x14007af76  int     29h; Win8: RtlFailFast(ecx)
0x14007af78  add     rsp, 48h
0x14007af7c  pop     r15
0x14007af7e  pop     r14
0x14007af80  pop     rdi
0x14007af81  pop     rsi
0x14007af82  pop     rbp
0x14007af83  pop     rbx
0x14007af84  retn
0x14007af86  mov     rax, [rax]
0x14007af89  jmp     short loc_14007AF0E
0x14007af8b  mov     rcx, [rbx+80h]; IoWorkItem
0x14007af92  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14007af99  mov     r9, rbx; Context
0x14007af9c  mov     r8d, 1; QueueType
0x14007afa2  call    cs:__imp_IoQueueWorkItem
0x14007afa9  nop     dword ptr [rax+rax+00h]
0x14007afae  add     rsp, 48h
0x14007afb2  pop     r15
0x14007afb4  pop     r14
0x14007afb6  pop     rdi
0x14007afb7  pop     rsi
0x14007afb8  pop     rbp
0x14007afb9  pop     rbx
0x14007afba  retn
0x14007afbc  lock dec dword ptr [rdi+8]
0x14007afc0  movzx   ecx, r15b; NewIrql
0x14007afc4  call    cs:__imp_KeLowerIrql
0x14007afcb  nop     dword ptr [rax+rax+00h]
0x14007afd0  jmp     short loc_14007AF78
0x14007afd2  mov     ecx, 0Eh
0x14007afd7  int     29h; Win8: RtlFailFast(ecx)
0x14007afd9  jmp     loc_14007AF38
```
