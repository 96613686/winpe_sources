# SpLogAdvanceCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x140038c60`
- end: `0x140038e46`
- name: `?SpLogAdvanceCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140036820`

## callees

- `0x140011970`
- `0x14001dfb0`
- `0x14001e160`
- `0x14001efe0`
- `0x140025710`
- `0x140038c60`
- `0x1400b0ff0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140038d41`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038d41`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140038e25`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140038e25`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038dc6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038dc6`
- `ntoskrnl!KeSetEvent` at `0x140038d91`
- `ntoskrnl!KeSetEvent` at `0x140038da9`
- `ntoskrnl!KeSetEvent` at `0x140038d91`
- `ntoskrnl!KeSetEvent` at `0x140038da9`
- `ntoskrnl!KeReleaseMutex` at `0x140038d67`
- `ntoskrnl!KeReleaseMutex` at `0x140038d67`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038df0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038df0`

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
0x140038c60  mov     r11, rsp
0x140038c63  push    rbx
0x140038c64  push    rbp
0x140038c65  push    rsi
0x140038c66  push    rdi
0x140038c67  push    r12
0x140038c69  push    r13
0x140038c6b  push    r14
0x140038c6d  push    r15
0x140038c6f  sub     rsp, 58h
0x140038c73  mov     r15, [rcx+40h]
0x140038c77  xorps   xmm0, xmm0
0x140038c7a  mov     rdi, cs:?SL_LSN_INVALID@@3T_SL_LSN@@B; _SL_LSN const SL_LSN_INVALID
0x140038c81  xor     eax, eax
0x140038c83  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140038c88  mov     qword ptr [r11+8], 0
0x140038c90  lea     rcx, [r15+8]; this
0x140038c94  mov     [r11-58h], rax
0x140038c98  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x140038c9d  mov     r14d, eax
0x140038ca0  test    eax, eax
0x140038ca2  js      loc_140038E31
0x140038ca8  mov     r13, [r15+0CA0h]
0x140038caf  xor     ebx, ebx
0x140038cb1  mov     rbp, [r13+498h]
0x140038cb8  lock xadd [rbp+88h], rbx
0x140038cc1  mov     rcx, r13; this
0x140038cc4  call    ?FlushSynchronous@SIO_SPACE@@QEAAJXZ; SIO_SPACE::FlushSynchronous(void)
0x140038cc9  mov     r14d, eax
0x140038ccc  test    eax, eax
0x140038cce  js      loc_140038DB5
0x140038cd4  mov     rcx, [r13+178h]; this
0x140038cdb  xor     r12b, r12b
0x140038cde  cmp     [rcx+0FCh], r12b
0x140038ce5  jnz     short loc_140038D26
0x140038ce7  lea     rdx, [rsp+98h+arg_0]; unsigned __int64 *
0x140038cef  call    ?GetCheckpointDistance@SIO_LOG@@QEAAJPEA_K@Z; SIO_LOG::GetCheckpointDistance(unsigned __int64 *)
0x140038cf4  mov     r14d, eax
0x140038cf7  test    eax, eax
0x140038cf9  js      loc_140038DB5
0x140038cff  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140038d06  movzx   r12d, r12b
0x140038d0a  mov     rcx, [rax+210h]
0x140038d11  mov     eax, 1
0x140038d16  shr     rcx, 2
0x140038d1a  cmp     [rsp+98h+arg_0], rcx
0x140038d22  cmovnb  r12d, eax
0x140038d26  lea     rsi, [r13+4A0h]
0x140038d2d  mov     [rsp+98h+Timeout], 0; Timeout
0x140038d36  mov     rcx, rsi; Object
0x140038d39  xor     r9d, r9d; Alertable
0x140038d3c  xor     r8d, r8d; WaitMode
0x140038d3f  xor     edx, edx; WaitReason
0x140038d41  call    cs:__imp_KeWaitForSingleObject
0x140038d48  nop     dword ptr [rax+rax+00h]
0x140038d4d  mov     rcx, [r13+178h]
0x140038d54  mov     r8b, r12b
0x140038d57  mov     rdx, rbx
0x140038d5a  call    ?Advance@SIO_LOG@@QEAAJT_SL_LSN@@E@Z; SIO_LOG::Advance(_SL_LSN,uchar)
0x140038d5f  xor     edx, edx; Wait
0x140038d61  mov     rcx, rsi; Mutex
0x140038d64  mov     r14d, eax
0x140038d67  call    cs:__imp_KeReleaseMutex
0x140038d6e  nop     dword ptr [rax+rax+00h]
0x140038d73  test    r14d, r14d
0x140038d76  js      short loc_140038DB5
0x140038d78  cmp     dword ptr [rbp+34h], 0
0x140038d7c  jnz     short loc_140038D9D
0x140038d7e  mov     rcx, [r13+488h]
0x140038d85  xor     r8d, r8d; Wait
0x140038d88  add     rcx, 1B0h; Event
0x140038d8f  xor     edx, edx; Increment
0x140038d91  call    cs:__imp_KeSetEvent
0x140038d98  nop     dword ptr [rax+rax+00h]
0x140038d9d  lea     rcx, [r15+0A40h]; Event
0x140038da4  xor     r8d, r8d; Wait
0x140038da7  xor     edx, edx; Increment
0x140038da9  call    cs:__imp_KeSetEvent
0x140038db0  nop     dword ptr [rax+rax+00h]
0x140038db5  test    rbp, rbp
0x140038db8  jz      short loc_140038E1E
0x140038dba  lea     rcx, [rbp+98h]; SpinLock
0x140038dc1  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140038dc6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140038dcd  nop     dword ptr [rax+rax+00h]
0x140038dd2  mov     edx, [rbp+90h]; int
0x140038dd8  mov     ecx, r14d; int
0x140038ddb  call    ?ScIsWorseStatus@@YAEJJ@Z; ScIsWorseStatus(long,long)
0x140038de0  test    al, al
0x140038de2  jz      short loc_140038DEB
0x140038de4  mov     [rbp+90h], r14d
0x140038deb  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140038df0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140038df7  nop     dword ptr [rax+rax+00h]
0x140038dfc  mov     rax, rbx
0x140038dff  lock cmpxchg [rbp+88h], rdi
0x140038e08  jz      short loc_140038E1E
0x140038e0a  lea     rcx, [r15+0A68h]; Context
0x140038e11  xor     r9d, r9d; unsigned __int8
0x140038e14  xor     r8d, r8d; unsigned int
0x140038e17  xor     edx, edx; struct _LIST_ENTRY *
0x140038e19  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x140038e1e  mov     rcx, [r15+0F8h]; RunRefCacheAware
0x140038e25  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140038e2c  nop     dword ptr [rax+rax+00h]
0x140038e31  mov     eax, r14d
0x140038e34  add     rsp, 58h
0x140038e38  pop     r15
0x140038e3a  pop     r14
0x140038e3c  pop     r13
0x140038e3e  pop     r12
0x140038e40  pop     rdi
0x140038e41  pop     rsi
0x140038e42  pop     rbp
0x140038e43  pop     rbx
0x140038e44  retn
```
