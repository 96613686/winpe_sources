# OncRpcConnMgrpEndpointClosePostIrpCompletionCallback

- ea: `0x140006300`
- end: `0x140006396`
- name: `OncRpcConnMgrpEndpointClosePostIrpCompletionCallback`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400059a4`
- `0x140006300`
- `0x14000642c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006322`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006322`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000637b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000637b`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpEndpointClosePostIrpCompletionCallback(__int64 a1)
{
  __int64 v1; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v1 + 40), &LockHandle);
  *(_QWORD *)(v1 + 96) = 0;
  *(_DWORD *)(v1 + 48) = 3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids, v1, 3);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return OncRpcConnMgrpEndpointFreeInternal((PVOID)v1);
}

```

## disassembly

```asm
0x140006300  push    rbx
0x140006302  sub     rsp, 50h
0x140006306  mov     rbx, [rcx+38h]
0x14000630a  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14000630f  xorps   xmm0, xmm0
0x140006312  xor     eax, eax
0x140006314  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140006319  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14000631e  lea     rcx, [rbx+28h]; SpinLock
0x140006322  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140006329  nop     dword ptr [rax+rax+00h]
0x14000632e  mov     r8d, 3
0x140006334  mov     qword ptr [rbx+60h], 0
0x14000633c  mov     [rbx+30h], r8d
0x140006340  mov     rcx, cs:WPP_GLOBAL_Control
0x140006347  lea     rax, WPP_GLOBAL_Control
0x14000634e  cmp     rcx, rax
0x140006351  jz      short loc_140006376
0x140006353  mov     eax, [rcx+2Ch]
0x140006356  test    al, 8
0x140006358  jz      short loc_140006376
0x14000635a  mov     rcx, [rcx+18h]
0x14000635e  lea     edx, [r8+10h]
0x140006362  mov     [rsp+58h+var_38], r8d
0x140006367  mov     r9, rbx
0x14000636a  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x140006371  call    WPP_SF_qd
0x140006376  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14000637b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140006382  nop     dword ptr [rax+rax+00h]
0x140006387  mov     rcx, rbx; P
0x14000638a  call    OncRpcConnMgrpEndpointFreeInternal
0x14000638f  add     rsp, 50h
0x140006393  pop     rbx
0x140006394  retn
```
