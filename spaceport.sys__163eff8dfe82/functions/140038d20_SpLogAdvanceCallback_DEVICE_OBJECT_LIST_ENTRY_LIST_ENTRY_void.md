# SpLogAdvanceCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x140038d20`
- end: `0x140038f06`
- name: `?SpLogAdvanceCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400368e0`

## callees

- `0x140011970`
- `0x14001dfb0`
- `0x14001e160`
- `0x14001efe0`
- `0x140025710`
- `0x140038d20`
- `0x1400b1190`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140038e01`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038e01`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140038ee5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140038ee5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038e86`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038e86`
- `ntoskrnl!KeSetEvent` at `0x140038e51`
- `ntoskrnl!KeSetEvent` at `0x140038e69`
- `ntoskrnl!KeSetEvent` at `0x140038e51`
- `ntoskrnl!KeSetEvent` at `0x140038e69`
- `ntoskrnl!KeReleaseMutex` at `0x140038e27`
- `ntoskrnl!KeReleaseMutex` at `0x140038e27`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038eb0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038eb0`

## pseudocode

```c
__int64 __fastcall SpLogAdvanceCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  char *DeviceExtension; // r15
  int CheckpointDistance; // r14d
  __int64 v6; // r13
  __int64 v7; // rbp
  signed __int64 v8; // rbx
  SIO_LOG *v9; // rcx
  bool v10; // r12
  __int64 v11; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v14; // [rsp+A0h] [rbp+8h] BYREF

  DeviceExtension = (char *)a1->DeviceExtension;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v14 = 0;
  CheckpointDistance = SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 1);
  if ( CheckpointDistance < 0 )
    return (unsigned int)CheckpointDistance;
  v6 = *((_QWORD *)DeviceExtension + 404);
  v7 = *(_QWORD *)(v6 + 1176);
  v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 136), 0);
  CheckpointDistance = SIO_SPACE::FlushSynchronous((SIO_SPACE *)v6);
  if ( CheckpointDistance >= 0 )
  {
    v9 = *(SIO_LOG **)(v6 + 376);
    v10 = 0;
    if ( *((_BYTE *)v9 + 252) )
      goto LABEL_6;
    CheckpointDistance = SIO_LOG::GetCheckpointDistance(v9, &v14);
    if ( CheckpointDistance >= 0 )
    {
      v10 = v14 >= *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66) >> 2;
LABEL_6:
      KeWaitForSingleObject((PVOID)(v6 + 1184), Executive, 0, 0, 0);
      LOBYTE(v11) = v10;
      CheckpointDistance = SIO_LOG::Advance(*(_QWORD *)(v6 + 376), v8, v11);
      KeReleaseMutex((PRKMUTEX)(v6 + 1184), 0);
      if ( CheckpointDistance >= 0 )
      {
        if ( !*(_DWORD *)(v7 + 52) )
          KeSetEvent((PRKEVENT)(*(_QWORD *)(v6 + 1160) + 432LL), 0, 0);
        KeSetEvent((PRKEVENT)(DeviceExtension + 2624), 0, 0);
      }
    }
  }
  if ( v7 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v7 + 152), &LockHandle);
    if ( ScIsWorseStatus(CheckpointDistance, *(_DWORD *)(v7 + 144)) )
      *(_DWORD *)(v7 + 144) = CheckpointDistance;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v8 != _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 136), SL_LSN_INVALID, v8) )
      SP_WORKITEM::Insert(DeviceExtension + 2664, 0, 0, 0);
  }
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
  return (unsigned int)CheckpointDistance;
}

```

## disassembly

```asm
0x140038d20  mov     r11, rsp
0x140038d23  push    rbx
0x140038d24  push    rbp
0x140038d25  push    rsi
0x140038d26  push    rdi
0x140038d27  push    r12
0x140038d29  push    r13
0x140038d2b  push    r14
0x140038d2d  push    r15
0x140038d2f  sub     rsp, 58h
0x140038d33  mov     r15, [rcx+40h]
0x140038d37  xorps   xmm0, xmm0
0x140038d3a  mov     rdi, cs:?SL_LSN_INVALID@@3T_SL_LSN@@B; _SL_LSN const SL_LSN_INVALID
0x140038d41  xor     eax, eax
0x140038d43  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140038d48  mov     qword ptr [r11+8], 0
0x140038d50  lea     rcx, [r15+8]; this
0x140038d54  mov     [r11-58h], rax
0x140038d58  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x140038d5d  mov     r14d, eax
0x140038d60  test    eax, eax
0x140038d62  js      loc_140038EF1
0x140038d68  mov     r13, [r15+0CA0h]
0x140038d6f  xor     ebx, ebx
0x140038d71  mov     rbp, [r13+498h]
0x140038d78  lock xadd [rbp+88h], rbx
0x140038d81  mov     rcx, r13; this
0x140038d84  call    ?FlushSynchronous@SIO_SPACE@@QEAAJXZ; SIO_SPACE::FlushSynchronous(void)
0x140038d89  mov     r14d, eax
0x140038d8c  test    eax, eax
0x140038d8e  js      loc_140038E75
0x140038d94  mov     rcx, [r13+178h]; this
0x140038d9b  xor     r12b, r12b
0x140038d9e  cmp     [rcx+0FCh], r12b
0x140038da5  jnz     short loc_140038DE6
0x140038da7  lea     rdx, [rsp+98h+arg_0]; unsigned __int64 *
0x140038daf  call    ?GetCheckpointDistance@SIO_LOG@@QEAAJPEA_K@Z; SIO_LOG::GetCheckpointDistance(unsigned __int64 *)
0x140038db4  mov     r14d, eax
0x140038db7  test    eax, eax
0x140038db9  js      loc_140038E75
0x140038dbf  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140038dc6  movzx   r12d, r12b
0x140038dca  mov     rcx, [rax+210h]
0x140038dd1  mov     eax, 1
0x140038dd6  shr     rcx, 2
0x140038dda  cmp     [rsp+98h+arg_0], rcx
0x140038de2  cmovnb  r12d, eax
0x140038de6  lea     rsi, [r13+4A0h]
0x140038ded  mov     [rsp+98h+Timeout], 0; Timeout
0x140038df6  mov     rcx, rsi; Object
0x140038df9  xor     r9d, r9d; Alertable
0x140038dfc  xor     r8d, r8d; WaitMode
0x140038dff  xor     edx, edx; WaitReason
0x140038e01  call    cs:__imp_KeWaitForSingleObject
0x140038e08  nop     dword ptr [rax+rax+00h]
0x140038e0d  mov     rcx, [r13+178h]
0x140038e14  mov     r8b, r12b
0x140038e17  mov     rdx, rbx
0x140038e1a  call    ?Advance@SIO_LOG@@QEAAJT_SL_LSN@@E@Z; SIO_LOG::Advance(_SL_LSN,uchar)
0x140038e1f  xor     edx, edx; Wait
0x140038e21  mov     rcx, rsi; Mutex
0x140038e24  mov     r14d, eax
0x140038e27  call    cs:__imp_KeReleaseMutex
0x140038e2e  nop     dword ptr [rax+rax+00h]
0x140038e33  test    r14d, r14d
0x140038e36  js      short loc_140038E75
0x140038e38  cmp     dword ptr [rbp+34h], 0
0x140038e3c  jnz     short loc_140038E5D
0x140038e3e  mov     rcx, [r13+488h]
0x140038e45  xor     r8d, r8d; Wait
0x140038e48  add     rcx, 1B0h; Event
0x140038e4f  xor     edx, edx; Increment
0x140038e51  call    cs:__imp_KeSetEvent
0x140038e58  nop     dword ptr [rax+rax+00h]
0x140038e5d  lea     rcx, [r15+0A40h]; Event
0x140038e64  xor     r8d, r8d; Wait
0x140038e67  xor     edx, edx; Increment
0x140038e69  call    cs:__imp_KeSetEvent
0x140038e70  nop     dword ptr [rax+rax+00h]
0x140038e75  test    rbp, rbp
0x140038e78  jz      short loc_140038EDE
0x140038e7a  lea     rcx, [rbp+98h]; SpinLock
0x140038e81  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140038e86  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140038e8d  nop     dword ptr [rax+rax+00h]
0x140038e92  mov     edx, [rbp+90h]; int
0x140038e98  mov     ecx, r14d; int
0x140038e9b  call    ?ScIsWorseStatus@@YAEJJ@Z; ScIsWorseStatus(long,long)
0x140038ea0  test    al, al
0x140038ea2  jz      short loc_140038EAB
0x140038ea4  mov     [rbp+90h], r14d
0x140038eab  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140038eb0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140038eb7  nop     dword ptr [rax+rax+00h]
0x140038ebc  mov     rax, rbx
0x140038ebf  lock cmpxchg [rbp+88h], rdi
0x140038ec8  jz      short loc_140038EDE
0x140038eca  lea     rcx, [r15+0A68h]; Context
0x140038ed1  xor     r9d, r9d; unsigned __int8
0x140038ed4  xor     r8d, r8d; unsigned int
0x140038ed7  xor     edx, edx; struct _LIST_ENTRY *
0x140038ed9  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x140038ede  mov     rcx, [r15+0F8h]; RunRefCacheAware
0x140038ee5  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140038eec  nop     dword ptr [rax+rax+00h]
0x140038ef1  mov     eax, r14d
0x140038ef4  add     rsp, 58h
0x140038ef8  pop     r15
0x140038efa  pop     r14
0x140038efc  pop     r13
0x140038efe  pop     r12
0x140038f00  pop     rdi
0x140038f01  pop     rsi
0x140038f02  pop     rbp
0x140038f03  pop     rbx
0x140038f04  retn
```
