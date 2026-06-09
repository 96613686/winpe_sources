# OncRpcConnMgrpConnectionDisconnectBySystem

- ea: `0x140008034`
- end: `0x1400080ff`
- name: `OncRpcConnMgrpConnectionDisconnectBySystem`
- size: `203`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400085c0`
- `0x140008760`
- `0x14000df80`
- `0x14000fc70`

## callees

- `0x1400020c0`
- `0x1400070c4`
- `0x140007d58`
- `0x140008034`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000805e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000805e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008091`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008091`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpConnectionDisconnectBySystem(__int64 a1)
{
  unsigned int v2; // esi
  bool v3; // di
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = 0;
  v3 = 0;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 72), &LockHandle);
  if ( !*(_QWORD *)(a1 + 104) && *(_QWORD *)(a1 + 64) && !*(_QWORD *)(a1 + 88) )
    v3 = *(_DWORD *)(a1 + 80) != 5;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  OncRpcConnMgrpConnectionDisconnect(a1, 0, 0, 3);
  if ( v3 )
    v2 = OncRpcConnMgrConnectionClose(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x19u,
      (__int64)WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids,
      v2);
  return v2;
}

```

## disassembly

```asm
0x140008034  push    rbx
0x140008036  push    rsi
0x140008037  push    rdi
0x140008038  push    r14
0x14000803a  sub     rsp, 48h
0x14000803e  mov     rbx, rcx
0x140008041  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140008046  xorps   xmm0, xmm0
0x140008049  xor     eax, eax
0x14000804b  add     rcx, 48h ; 'H'; SpinLock
0x14000804f  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140008054  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140008059  xor     esi, esi
0x14000805b  xor     dil, dil
0x14000805e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008065  nop     dword ptr [rax+rax+00h]
0x14000806a  lea     r14d, [rsi+1]
0x14000806e  cmp     [rbx+68h], rsi
0x140008072  jnz     short loc_14000808C
0x140008074  cmp     [rbx+40h], rsi
0x140008078  jz      short loc_14000808C
0x14000807a  cmp     [rbx+58h], rsi
0x14000807e  jnz     short loc_14000808C
0x140008080  cmp     dword ptr [rbx+50h], 5
0x140008084  movzx   edi, dil
0x140008088  cmovnz  edi, r14d
0x14000808c  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140008091  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008098  nop     dword ptr [rax+rax+00h]
0x14000809d  mov     r9d, 3
0x1400080a3  xor     r8d, r8d
0x1400080a6  xor     edx, edx
0x1400080a8  mov     rcx, rbx
0x1400080ab  call    OncRpcConnMgrpConnectionDisconnect
0x1400080b0  test    dil, dil
0x1400080b3  jz      short loc_1400080BF
0x1400080b5  mov     rcx, rbx
0x1400080b8  call    OncRpcConnMgrConnectionClose
0x1400080bd  mov     esi, eax
0x1400080bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080c6  lea     rax, WPP_GLOBAL_Control
0x1400080cd  cmp     rcx, rax
0x1400080d0  jz      short loc_1400080F2
0x1400080d2  mov     edx, [rcx+2Ch]
0x1400080d5  test    r14b, dl
0x1400080d8  jz      short loc_1400080F2
0x1400080da  mov     rcx, [rcx+18h]
0x1400080de  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x1400080e5  mov     edx, 19h
0x1400080ea  mov     r9d, esi
0x1400080ed  call    WPP_SF_d
0x1400080f2  mov     eax, esi
0x1400080f4  add     rsp, 48h
0x1400080f8  pop     r14
0x1400080fa  pop     rdi
0x1400080fb  pop     rsi
0x1400080fc  pop     rbx
0x1400080fd  retn
```
