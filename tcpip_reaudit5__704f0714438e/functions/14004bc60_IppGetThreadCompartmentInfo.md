# IppGetThreadCompartmentInfo

- ea: `0x14004bc60`
- end: `0x14004be0e`
- name: `IppGetThreadCompartmentInfo`
- size: `430`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013420`
- `0x140048f90`
- `0x1400495bc`
- `0x140049ca0`
- `0x14004a8e0`
- `0x14004ba80`
- `0x1400e1a90`
- `0x1400ef1f0`
- `0x1400f5e50`
- `0x1401146f0`
- `0x14013e2e0`
- `0x1401401e0`

## callees

- `0x14004bc60`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004bcbf`
- `ntoskrnl!KfRaiseIrql` at `0x14004bcbf`
- `ntoskrnl!KeLowerIrql` at `0x14004bd70`
- `ntoskrnl!KeLowerIrql` at `0x14004bdf4`
- `ntoskrnl!KeLowerIrql` at `0x14004bd70`
- `ntoskrnl!KeLowerIrql` at `0x14004bdf4`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bdd2`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bdd2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bd01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bd01`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bd16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bd16`
- `ntoskrnl!KeTestSpinLock` at `0x14004bce5`
- `ntoskrnl!KeTestSpinLock` at `0x14004bce5`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004bc8c`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004bc8c`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004bca8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004bca8`

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
0x14004bc60  push    rbx
0x14004bc62  push    rbp
0x14004bc63  push    rsi
0x14004bc64  push    rdi
0x14004bc65  push    r14
0x14004bc67  push    r15
0x14004bc69  sub     rsp, 48h
0x14004bc6d  xorps   xmm0, xmm0
0x14004bc70  lea     r8, [rdx+4]
0x14004bc74  movups  xmmword ptr [rdx], xmm0
0x14004bc77  xor     eax, eax
0x14004bc79  mov     r14, rcx
0x14004bc7c  mov     [rdx+10h], rax
0x14004bc80  mov     rbp, rdx
0x14004bc83  mov     rcx, gs:188h
0x14004bc8c  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14004bc93  nop     dword ptr [rax+rax+00h]
0x14004bc98  mov     esi, [rbp+4]
0x14004bc9b  test    esi, esi
0x14004bc9d  jnz     short loc_14004BCB6
0x14004bc9f  mov     rcx, gs:188h
0x14004bca8  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14004bcaf  nop     dword ptr [rax+rax+00h]
0x14004bcb4  mov     esi, eax
0x14004bcb6  mov     cl, 2; NewIrql
0x14004bcb8  lea     rdi, [r14+4DA8h]
0x14004bcbf  call    cs:__imp_KfRaiseIrql
0x14004bcc6  nop     dword ptr [rax+rax+00h]
0x14004bccb  movzx   r15d, al
0x14004bccf  xorps   xmm0, xmm0
0x14004bcd2  xor     eax, eax
0x14004bcd4  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14004bcd9  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14004bcde  lock inc dword ptr [rdi+8]
0x14004bce2  mov     rcx, rdi; SpinLock
0x14004bce5  call    cs:__imp_KeTestSpinLock
0x14004bcec  nop     dword ptr [rax+rax+00h]
0x14004bcf1  test    al, al
0x14004bcf3  jnz     short loc_14004BD22
0x14004bcf5  lock dec dword ptr [rdi+8]
0x14004bcf9  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14004bcfe  mov     rcx, rdi; SpinLock
0x14004bd01  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004bd08  nop     dword ptr [rax+rax+00h]
0x14004bd0d  lock inc dword ptr [rdi+8]
0x14004bd11  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14004bd16  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004bd1d  nop     dword ptr [rax+rax+00h]
0x14004bd22  mov     edx, [r14+4D9Ch]
0x14004bd29  dec     edx
0x14004bd2b  mov     eax, esi
0x14004bd2d  and     rdx, rax
0x14004bd30  shl     rdx, 4
0x14004bd34  add     rdx, [r14+4DA0h]
0x14004bd3b  mov     rax, [rdx]
0x14004bd3e  cmp     rax, rdx
0x14004bd41  jz      loc_14004BDEC
0x14004bd47  cmp     [rax-30h], esi
0x14004bd4a  lea     rbx, [rax-30h]
0x14004bd4e  jnz     short loc_14004BDB6
0x14004bd50  mov     eax, 1
0x14004bd55  lock xadd [rbx+20h], rax
0x14004bd5b  inc     rax
0x14004bd5e  cmp     rax, 1
0x14004bd62  jle     loc_14004BE02
0x14004bd68  lock dec dword ptr [rdi+8]
0x14004bd6c  movzx   ecx, r15b; NewIrql
0x14004bd70  call    cs:__imp_KeLowerIrql
0x14004bd77  nop     dword ptr [rax+rax+00h]
0x14004bd7c  test    rbx, rbx
0x14004bd7f  jz      short loc_14004BDA8
0x14004bd81  movups  xmm0, xmmword ptr [rbx+4]
0x14004bd85  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14004bd8c  movups  xmmword ptr [rbp+8], xmm0
0x14004bd90  lock xadd [rbx+20h], rax
0x14004bd96  sub     rax, 1
0x14004bd9a  jg      short loc_14004BDA8
0x14004bd9c  test    rax, rax
0x14004bd9f  jz      short loc_14004BDBB
0x14004bda1  mov     ecx, 0Eh
0x14004bda6  int     29h; Win8: RtlFailFast(ecx)
0x14004bda8  add     rsp, 48h
0x14004bdac  pop     r15
0x14004bdae  pop     r14
0x14004bdb0  pop     rdi
0x14004bdb1  pop     rsi
0x14004bdb2  pop     rbp
0x14004bdb3  pop     rbx
0x14004bdb4  retn
0x14004bdb6  mov     rax, [rax]
0x14004bdb9  jmp     short loc_14004BD3E
0x14004bdbb  mov     rcx, [rbx+80h]; IoWorkItem
0x14004bdc2  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14004bdc9  mov     r9, rbx; Context
0x14004bdcc  mov     r8d, 1; QueueType
0x14004bdd2  call    cs:__imp_IoQueueWorkItem
0x14004bdd9  nop     dword ptr [rax+rax+00h]
0x14004bdde  add     rsp, 48h
0x14004bde2  pop     r15
0x14004bde4  pop     r14
0x14004bde6  pop     rdi
0x14004bde7  pop     rsi
0x14004bde8  pop     rbp
0x14004bde9  pop     rbx
0x14004bdea  retn
0x14004bdec  lock dec dword ptr [rdi+8]
0x14004bdf0  movzx   ecx, r15b; NewIrql
0x14004bdf4  call    cs:__imp_KeLowerIrql
0x14004bdfb  nop     dword ptr [rax+rax+00h]
0x14004be00  jmp     short loc_14004BDA8
0x14004be02  mov     ecx, 0Eh
0x14004be07  int     29h; Win8: RtlFailFast(ecx)
0x14004be09  jmp     loc_14004BD68
```
