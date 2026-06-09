# NvmeNamespacePowerNotRequiredStep2

- ea: `0x14013d08c`
- end: `0x14013d29d`
- name: `NvmeNamespacePowerNotRequiredStep2`
- size: `529`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14013d010`
- `0x14013d2b0`

## callees

- `0x14013d08c`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14013d125`
- `ntoskrnl!PoFxIdleComponent` at `0x14013d125`
- `ntoskrnl!IoQueueWorkItem` at `0x14013d1a2`
- `ntoskrnl!IoQueueWorkItem` at `0x14013d1a2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d0c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d1f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d0c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d1f3`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d1d5`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d235`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d1d5`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d235`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14013d287`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14013d287`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013d160`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013d160`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d154`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d26d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d154`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d26d`

## pseudocode

```c
void __fastcall NvmeNamespacePowerNotRequiredStep2(PVOID Context)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rbp
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // r8d
  KIRQL CurrentIrql; // al
  __int64 v9; // rcx
  NTSTATUS v10; // ebp
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  v2 = *((_QWORD *)Context + 2);
  v3 = *((_QWORD *)Context + 16);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = *(_QWORD *)(v2 + 128);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 88), &LockHandle);
  v5 = *((_QWORD *)Context + 16);
  v6 = *(_QWORD *)(v5 + 8);
  v7 = *(_DWORD *)(v6 + 32);
  if ( (v7 & 2) != 0 && (*(_DWORD *)(*(_QWORD *)(v6 + 8) + 12LL) & 2) != 0 )
  {
    if ( **(_BYTE **)(v4 + 168) == 1 && _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 96), 0, 1) == 1 )
      PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v4 + 168) + 8LL), 0, 0);
    goto LABEL_17;
  }
  if ( *(_DWORD *)(v5 + 72) != 1 )
  {
LABEL_17:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    PoFxCompleteDevicePowerNotRequired(**(_QWORD **)(*((_QWORD *)Context + 16) + 8LL));
    return;
  }
  if ( (v7 & 1) == 0 )
  {
LABEL_14:
    v11 = PoRequestPowerIrp(
            *((PDEVICE_OBJECT *)Context + 1),
            2u,
            (POWER_STATE)4,
            NvmeNamespacePoFxD3Completion,
            Context,
            0);
    v12 = *((_QWORD *)Context + 16);
    if ( v11 == 259 )
    {
      *(_DWORD *)(v12 + 80) |= 4u;
      _InterlockedExchange((volatile __int32 *)(*((_QWORD *)Context + 16) + 184LL), 0);
    }
    else
    {
      ++*(_DWORD *)(v12 + 172);
    }
    goto LABEL_17;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  CurrentIrql = KeGetCurrentIrql();
  v9 = *((_QWORD *)Context + 16);
  if ( !CurrentIrql )
  {
    v10 = PoRequestPowerIrp(
            *((PDEVICE_OBJECT *)Context + 1),
            0,
            (POWER_STATE)1,
            (PREQUEST_POWER_COMPLETE)NvmeNamespacePoFxWaitWakeCompletion,
            Context,
            (PIRP *)(*(_QWORD *)(v9 + 8) + 72LL));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*((_QWORD *)Context + 16) + 88LL), &LockHandle);
    if ( v10 != 259 )
      ++*(_DWORD *)(*((_QWORD *)Context + 16) + 176LL);
    if ( v10 < 0 )
      goto LABEL_17;
    goto LABEL_14;
  }
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v9 + 160), 1, 0) )
    IoQueueWorkItem(
      *(PIO_WORKITEM *)(*((_QWORD *)Context + 16) + 144LL),
      NvmeNamespacePowerNotRequiredStep2Passive,
      DelayedWorkQueue,
      Context);
}

```

## disassembly

```asm
0x14013d08c  push    rbx
0x14013d08e  push    rbp
0x14013d08f  push    rsi
0x14013d090  push    rdi
0x14013d091  sub     rsp, 58h
0x14013d095  xor     eax, eax
0x14013d097  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14013d09c  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14013d0a1  mov     rdi, rcx
0x14013d0a4  mov     rax, [rcx+10h]
0x14013d0a8  xorps   xmm0, xmm0
0x14013d0ab  mov     rcx, [rcx+80h]
0x14013d0b2  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14013d0b7  add     rcx, 58h ; 'X'; SpinLock
0x14013d0bb  mov     rbp, [rax+80h]
0x14013d0c2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14013d0c9  nop     dword ptr [rax+rax+00h]
0x14013d0ce  mov     rdx, [rdi+80h]
0x14013d0d5  mov     rax, [rdx+8]
0x14013d0d9  mov     r8d, [rax+20h]
0x14013d0dd  test    r8b, 2
0x14013d0e1  jz      short loc_14013D136
0x14013d0e3  mov     rax, [rax+8]
0x14013d0e7  mov     ecx, [rax+0Ch]
0x14013d0ea  test    cl, 2
0x14013d0ed  jz      short loc_14013D136
0x14013d0ef  mov     rax, [rbp+0A8h]
0x14013d0f6  mov     ebx, 1
0x14013d0fb  cmp     [rax], bl
0x14013d0fd  jnz     loc_14013D268
0x14013d103  xor     esi, esi
0x14013d105  mov     eax, ebx
0x14013d107  lock cmpxchg [rdx+60h], esi
0x14013d10c  jnz     loc_14013D268
0x14013d112  mov     rax, [rbp+0A8h]
0x14013d119  xor     r8d, r8d
0x14013d11c  xor     edx, edx
0x14013d11e  mov     rcx, [rax+8]
0x14013d122  mov     rcx, [rcx]
0x14013d125  call    cs:__imp_PoFxIdleComponent
0x14013d12c  nop     dword ptr [rax+rax+00h]
0x14013d131  jmp     loc_14013D268
0x14013d136  mov     ebx, 1
0x14013d13b  cmp     [rdx+48h], ebx
0x14013d13e  jnz     loc_14013D268
0x14013d144  xor     esi, esi
0x14013d146  test    bl, r8b
0x14013d149  jz      loc_14013D218
0x14013d14f  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14013d154  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d15b  nop     dword ptr [rax+rax+00h]
0x14013d160  call    cs:__imp_KeGetCurrentIrql
0x14013d167  nop     dword ptr [rax+rax+00h]
0x14013d16c  mov     rcx, [rdi+80h]
0x14013d173  test    al, al
0x14013d175  jz      short loc_14013D1B3
0x14013d177  xor     eax, eax
0x14013d179  lock cmpxchg [rcx+0A0h], ebx
0x14013d181  jnz     loc_14013D293
0x14013d187  mov     rcx, [rdi+80h]
0x14013d18e  lea     rdx, NvmeNamespacePowerNotRequiredStep2Passive; WorkerRoutine
0x14013d195  mov     r9, rdi; Context
0x14013d198  mov     r8d, ebx; QueueType
0x14013d19b  mov     rcx, [rcx+90h]; IoWorkItem
0x14013d1a2  call    cs:__imp_IoQueueWorkItem
0x14013d1a9  nop     dword ptr [rax+rax+00h]
0x14013d1ae  jmp     loc_14013D293
0x14013d1b3  mov     rax, [rcx+8]
0x14013d1b7  lea     r9, NvmeNamespacePoFxWaitWakeCompletion; CompletionFunction
0x14013d1be  mov     rcx, [rdi+8]; DeviceObject
0x14013d1c2  add     rax, 48h ; 'H'
0x14013d1c6  mov     [rsp+78h+Irp], rax; Irp
0x14013d1cb  mov     r8d, ebx; PowerState
0x14013d1ce  xor     edx, edx; MinorFunction
0x14013d1d0  mov     [rsp+78h+Context], rdi; Context
0x14013d1d5  call    cs:__imp_PoRequestPowerIrp
0x14013d1dc  nop     dword ptr [rax+rax+00h]
0x14013d1e1  mov     rcx, [rdi+80h]
0x14013d1e8  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14013d1ed  add     rcx, 58h ; 'X'; SpinLock
0x14013d1f1  mov     ebp, eax
0x14013d1f3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14013d1fa  nop     dword ptr [rax+rax+00h]
0x14013d1ff  cmp     ebp, 103h
0x14013d205  jz      short loc_14013D214
0x14013d207  mov     rcx, [rdi+80h]
0x14013d20e  add     [rcx+0B0h], ebx
0x14013d214  test    ebp, ebp
0x14013d216  js      short loc_14013D268
0x14013d218  mov     rcx, [rdi+8]; DeviceObject
0x14013d21c  lea     r9, NvmeNamespacePoFxD3Completion; CompletionFunction
0x14013d223  mov     [rsp+78h+Irp], rsi; Irp
0x14013d228  mov     r8d, 4; PowerState
0x14013d22e  mov     dl, 2; MinorFunction
0x14013d230  mov     [rsp+78h+Context], rdi; Context
0x14013d235  call    cs:__imp_PoRequestPowerIrp
0x14013d23c  nop     dword ptr [rax+rax+00h]
0x14013d241  mov     rcx, [rdi+80h]
0x14013d248  cmp     eax, 103h
0x14013d24d  jnz     short loc_14013D262
0x14013d24f  or      dword ptr [rcx+50h], 4
0x14013d253  mov     rax, [rdi+80h]
0x14013d25a  xchg    esi, [rax+0B8h]
0x14013d260  jmp     short loc_14013D268
0x14013d262  add     [rcx+0ACh], ebx
0x14013d268  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14013d26d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d274  nop     dword ptr [rax+rax+00h]
0x14013d279  mov     rax, [rdi+80h]
0x14013d280  mov     rcx, [rax+8]
0x14013d284  mov     rcx, [rcx]
0x14013d287  call    cs:__imp_PoFxCompleteDevicePowerNotRequired
0x14013d28e  nop     dword ptr [rax+rax+00h]
0x14013d293  add     rsp, 58h
0x14013d297  pop     rdi
0x14013d298  pop     rsi
0x14013d299  pop     rbp
0x14013d29a  pop     rbx
0x14013d29b  retn
```
