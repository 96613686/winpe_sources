# OncRpcConnMgrpConnectionClosePostIrpCompletionCallback

- ea: `0x140007cc0`
- end: `0x140007d52`
- name: `OncRpcConnMgrpConnectionClosePostIrpCompletionCallback`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006798`
- `0x140007cc0`
- `0x1400083b8`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007d14`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007d14`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007d37`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007d37`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpConnectionClosePostIrpCompletionCallback(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids, v1);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v1 + 72), &LockHandle);
  *(_QWORD *)(v1 + 216) = 0;
  *(_DWORD *)(v1 + 80) = 6;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return OncRpcConnMgrpConnectionFreeInternal(v1, v2, v3);
}

```

## disassembly

```asm
0x140007cc0  push    rbx
0x140007cc2  sub     rsp, 40h
0x140007cc6  mov     rbx, [rcx+38h]
0x140007cca  xorps   xmm0, xmm0
0x140007ccd  xor     eax, eax
0x140007ccf  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140007cd4  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140007cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ce0  lea     rax, WPP_GLOBAL_Control
0x140007ce7  cmp     rcx, rax
0x140007cea  jz      short loc_140007D0B
0x140007cec  mov     eax, [rcx+2Ch]
0x140007cef  test    al, 8
0x140007cf1  jz      short loc_140007D0B
0x140007cf3  mov     rcx, [rcx+18h]
0x140007cf7  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x140007cfe  mov     edx, 1Ah
0x140007d03  mov     r9, rbx
0x140007d06  call    WPP_SF_q
0x140007d0b  lea     rcx, [rbx+48h]; SpinLock
0x140007d0f  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140007d14  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007d1b  nop     dword ptr [rax+rax+00h]
0x140007d20  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140007d25  mov     qword ptr [rbx+0D8h], 0
0x140007d30  mov     dword ptr [rbx+50h], 6
0x140007d37  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007d3e  nop     dword ptr [rax+rax+00h]
0x140007d43  mov     rcx, rbx
0x140007d46  call    OncRpcConnMgrpConnectionFreeInternal
0x140007d4b  add     rsp, 40h
0x140007d4f  pop     rbx
0x140007d50  retn
```
