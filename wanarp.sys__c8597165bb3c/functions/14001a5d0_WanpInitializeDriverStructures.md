# WanpInitializeDriverStructures

- ea: `0x14001a5d0`
- end: `0x14001a854`
- name: `WanpInitializeDriverStructures`
- size: `644`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001a078`

## callees

- `0x14001782c`
- `0x14001a5d0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a807`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a83a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a807`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a83a`
- `ntoskrnl!KeInitializeEvent` at `0x14001a607`
- `ntoskrnl!KeInitializeEvent` at `0x14001a61f`
- `ntoskrnl!KeInitializeEvent` at `0x14001a639`
- `ntoskrnl!KeInitializeEvent` at `0x14001a653`
- `ntoskrnl!KeInitializeEvent` at `0x14001a68f`
- `ntoskrnl!KeInitializeEvent` at `0x14001a607`
- `ntoskrnl!KeInitializeEvent` at `0x14001a61f`
- `ntoskrnl!KeInitializeEvent` at `0x14001a639`
- `ntoskrnl!KeInitializeEvent` at `0x14001a653`
- `ntoskrnl!KeInitializeEvent` at `0x14001a68f`
- `ntoskrnl!ExAllocatePool2` at `0x14001a796`
- `ntoskrnl!ExAllocatePool2` at `0x14001a796`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a5e1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6e1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a7d5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a5e1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6e1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a7d5`

## pseudocode

```c
char WanpInitializeDriverStructures()
{
  struct _KEVENT *v0; // rbx
  int v1; // edi
  _QWORD *Pool2; // rax

  KeInitializeSpinLock(&g_rlStateLock);
  v0 = (struct _KEVENT *)&g_ModuleV4;
  v1 = 2;
  do
  {
    KeInitializeEvent(v0 + 8, SynchronizationEvent, 0);
    KeInitializeEvent(v0 + 7, NotificationEvent, 0);
    KeInitializeEvent(v0 + 9, SynchronizationEvent, 0);
    KeInitializeEvent(v0 + 10, SynchronizationEvent, 0);
    v0 = (struct _KEVENT *)&g_ModuleV6;
    --v1;
  }
  while ( v1 );
  WanpInitializeResource(&g_wrBindMutex);
  WanpInitializeResource(WfpMutex);
  KeInitializeEvent(&g_DriverRefCountEvent, NotificationEvent, 0);
  KeInitializeSpinLock(&g_rwlIfLock);
  KeInitializeSpinLock(&qword_140009C48);
  dword_140009C50 = 0;
  KeInitializeSpinLock(&g_rwlAdapterLock);
  KeInitializeSpinLock(&SpinLock);
  dword_140009CB0 = 0;
  qword_140009C28 = (__int64)&g_leIfList;
  g_leIfList = (__int64)&g_leIfList;
  qword_140009D68 = (__int64)&g_lePendingV4NotificationList;
  g_lePendingV4NotificationList = &g_lePendingV4NotificationList;
  qword_140009C88 = (__int64)&g_lePendingV6NotificationList;
  g_lePendingV6NotificationList = (__int64)&g_lePendingV6NotificationList;
  qword_140009CE8 = (__int64)&g_lePendingV4IrpList;
  g_lePendingV4IrpList = (__int64)&g_lePendingV4IrpList;
  qword_140009C68 = (__int64)&g_lePendingV6IrpList;
  g_lePendingV6IrpList = (__int64)&g_lePendingV6IrpList;
  qword_140009D28 = (__int64)&g_leMappedAdapterList;
  g_leMappedAdapterList = (__int64)&g_leMappedAdapterList;
  qword_140009CC8 = (__int64)&g_leDialInAdapterList;
  g_leDialInAdapterList = (__int64)&g_leDialInAdapterList;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 128, 1668313687);
  g_puipConnTable = Pool2;
  if ( Pool2 )
  {
    g_ulNextConnIndex = 1;
    g_ulConnTableSize = 16;
    *Pool2 = -1;
    KeInitializeSpinLock(&g_rlConnTableLock);
    ExInitializeNPagedLookasideList(&g_llConnBlocks, 0, 0, 0x200u, 0x130u, 0x63707257u, 0x10u);
    ExInitializeNPagedLookasideList(&g_llNotificationBlocks, 0, 0, 0x200u, 0x650u, 0x6E707257u, 4u);
    LOBYTE(Pool2) = 1;
  }
  return (char)Pool2;
}

```

## disassembly

```asm
0x14001a5d0  mov     [rsp+arg_0], rbx
0x14001a5d5  push    rdi
0x14001a5d6  sub     rsp, 40h
0x14001a5da  lea     rcx, g_rlStateLock; SpinLock
0x14001a5e1  call    cs:__imp_KeInitializeSpinLock
0x14001a5e8  nop     dword ptr [rax+rax+00h]
0x14001a5ed  lea     rbx, g_ModuleV4
0x14001a5f4  mov     edi, 2
0x14001a5f9  xor     r8d, r8d; State
0x14001a5fc  lea     rcx, [rbx+0C0h]; Event
0x14001a603  lea     edx, [r8+1]; Type
0x14001a607  call    cs:__imp_KeInitializeEvent
0x14001a60e  nop     dword ptr [rax+rax+00h]
0x14001a613  lea     rcx, [rbx+0A8h]; Event
0x14001a61a  xor     r8d, r8d; State
0x14001a61d  xor     edx, edx; Type
0x14001a61f  call    cs:__imp_KeInitializeEvent
0x14001a626  nop     dword ptr [rax+rax+00h]
0x14001a62b  xor     r8d, r8d; State
0x14001a62e  lea     rcx, [rbx+0D8h]; Event
0x14001a635  lea     edx, [r8+1]; Type
0x14001a639  call    cs:__imp_KeInitializeEvent
0x14001a640  nop     dword ptr [rax+rax+00h]
0x14001a645  xor     r8d, r8d; State
0x14001a648  lea     rcx, [rbx+0F0h]; Event
0x14001a64f  lea     edx, [r8+1]; Type
0x14001a653  call    cs:__imp_KeInitializeEvent
0x14001a65a  nop     dword ptr [rax+rax+00h]
0x14001a65f  lea     rbx, g_ModuleV6
0x14001a666  add     edi, 0FFFFFFFFh
0x14001a669  jnz     short loc_14001A5F9
0x14001a66b  lea     rcx, g_wrBindMutex
0x14001a672  call    WanpInitializeResource
0x14001a677  lea     rcx, WfpMutex
0x14001a67e  call    WanpInitializeResource
0x14001a683  xor     r8d, r8d; State
0x14001a686  lea     rcx, g_DriverRefCountEvent; Event
0x14001a68d  xor     edx, edx; Type
0x14001a68f  call    cs:__imp_KeInitializeEvent
0x14001a696  nop     dword ptr [rax+rax+00h]
0x14001a69b  lea     rcx, g_rwlIfLock; SpinLock
0x14001a6a2  call    cs:__imp_KeInitializeSpinLock
0x14001a6a9  nop     dword ptr [rax+rax+00h]
0x14001a6ae  lea     rcx, qword_140009C48; SpinLock
0x14001a6b5  call    cs:__imp_KeInitializeSpinLock
0x14001a6bc  nop     dword ptr [rax+rax+00h]
0x14001a6c1  lea     rcx, g_rwlAdapterLock; SpinLock
0x14001a6c8  mov     cs:dword_140009C50, edi
0x14001a6ce  call    cs:__imp_KeInitializeSpinLock
0x14001a6d5  nop     dword ptr [rax+rax+00h]
0x14001a6da  lea     rcx, SpinLock; SpinLock
0x14001a6e1  call    cs:__imp_KeInitializeSpinLock
0x14001a6e8  nop     dword ptr [rax+rax+00h]
0x14001a6ed  lea     rax, g_leIfList
0x14001a6f4  mov     cs:dword_140009CB0, edi
0x14001a6fa  mov     cs:qword_140009C28, rax
0x14001a701  mov     edx, 80h
0x14001a706  mov     cs:g_leIfList, rax
0x14001a70d  mov     edi, 63707257h
0x14001a712  lea     rax, g_lePendingV4NotificationList
0x14001a719  mov     r8d, edi
0x14001a71c  mov     cs:qword_140009D68, rax
0x14001a723  mov     cs:g_lePendingV4NotificationList, rax
0x14001a72a  lea     ecx, [rdx-40h]
0x14001a72d  lea     rax, g_lePendingV6NotificationList
0x14001a734  mov     cs:qword_140009C88, rax
0x14001a73b  mov     cs:g_lePendingV6NotificationList, rax
0x14001a742  lea     rax, g_lePendingV4IrpList
0x14001a749  mov     cs:qword_140009CE8, rax
0x14001a750  mov     cs:g_lePendingV4IrpList, rax
0x14001a757  lea     rax, g_lePendingV6IrpList
0x14001a75e  mov     cs:qword_140009C68, rax
0x14001a765  mov     cs:g_lePendingV6IrpList, rax
0x14001a76c  lea     rax, g_leMappedAdapterList
0x14001a773  mov     cs:qword_140009D28, rax
0x14001a77a  mov     cs:g_leMappedAdapterList, rax
0x14001a781  lea     rax, g_leDialInAdapterList
0x14001a788  mov     cs:qword_140009CC8, rax
0x14001a78f  mov     cs:g_leDialInAdapterList, rax
0x14001a796  call    cs:__imp_ExAllocatePool2
0x14001a79d  nop     dword ptr [rax+rax+00h]
0x14001a7a2  mov     cs:g_puipConnTable, rax
0x14001a7a9  test    rax, rax
0x14001a7ac  jz      loc_14001A848
0x14001a7b2  mov     ebx, 10h
0x14001a7b7  mov     cs:g_ulNextConnIndex, 1
0x14001a7c1  mov     cs:g_ulConnTableSize, ebx
0x14001a7c7  lea     rcx, g_rlConnTableLock; SpinLock
0x14001a7ce  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x14001a7d5  call    cs:__imp_KeInitializeSpinLock
0x14001a7dc  nop     dword ptr [rax+rax+00h]
0x14001a7e1  mov     [rsp+48h+Depth], bx; Depth
0x14001a7e6  lea     rcx, g_llConnBlocks; Lookaside
0x14001a7ed  mov     ebx, 200h
0x14001a7f2  mov     [rsp+48h+Tag], edi; Tag
0x14001a7f6  mov     r9d, ebx; Flags
0x14001a7f9  mov     [rsp+48h+Size], 130h; Size
0x14001a802  xor     r8d, r8d; Free
0x14001a805  xor     edx, edx; Allocate
0x14001a807  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001a80e  nop     dword ptr [rax+rax+00h]
0x14001a813  mov     [rsp+48h+Depth], 4; Depth
0x14001a81a  lea     rcx, g_llNotificationBlocks; Lookaside
0x14001a821  mov     [rsp+48h+Tag], 6E707257h; Tag
0x14001a829  mov     r9d, ebx; Flags
0x14001a82c  xor     r8d, r8d; Free
0x14001a82f  mov     [rsp+48h+Size], 650h; Size
0x14001a838  xor     edx, edx; Allocate
0x14001a83a  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001a841  nop     dword ptr [rax+rax+00h]
0x14001a846  mov     al, 1
0x14001a848  mov     rbx, [rsp+48h+arg_0]
0x14001a84d  add     rsp, 40h
0x14001a851  pop     rdi
0x14001a852  retn
```
