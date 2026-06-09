# OncRpcDrcpCachePurgeThread

- ea: `0x140011280`
- end: `0x140011347`
- name: `OncRpcDrcpCachePurgeThread`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140011280`
- `0x14001143c`
- `0x1400115f4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400112a6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001131c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400112a6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001131c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400112fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001132f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400112fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001132f`

## pseudocode

```c
void __fastcall OncRpcDrcpCachePurgeThread(__int64 a1)
{
  _QWORD *v2; // rsi
  __int64 v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // rbp
  unsigned __int64 v6; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  v2 = (_QWORD *)(a1 + 40);
  v3 = MEMORY[0xFFFFF78000000014];
  while ( 1 )
  {
    v4 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    v5 = v4 - 5;
    v6 = v3 - v4[6];
    if ( v6 / 0x989680 <= *(unsigned int *)(a1 + 72) )
      break;
    OncRpcDrcpTableEntryRemove(v6, v5);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    OncRpcDrcpTableEntryFree(a1, v5);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x140011280  push    rbx
0x140011282  push    rbp
0x140011283  push    rsi
0x140011284  push    rdi
0x140011285  push    r14
0x140011287  sub     rsp, 40h
0x14001128b  mov     rdi, rcx
0x14001128e  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140011293  xorps   xmm0, xmm0
0x140011296  xor     eax, eax
0x140011298  add     rcx, 38h ; '8'; SpinLock
0x14001129c  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x1400112a1  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x1400112a6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400112ad  nop     dword ptr [rax+rax+00h]
0x1400112b2  mov     rbx, 0FFFFF78000000014h
0x1400112bc  lea     rsi, [rdi+28h]
0x1400112c0  mov     rbx, [rbx]
0x1400112c3  mov     rax, [rsi]
0x1400112c6  cmp     rax, rsi
0x1400112c9  jz      short loc_14001132A
0x1400112cb  lea     rbp, [rax-28h]
0x1400112cf  mov     rcx, rbx
0x1400112d2  sub     rcx, [rbp+58h]
0x1400112d6  mov     rax, 0D6BF94D5E57A42BDh
0x1400112e0  mul     rcx
0x1400112e3  mov     eax, [rdi+48h]
0x1400112e6  shr     rdx, 17h
0x1400112ea  cmp     rdx, rax
0x1400112ed  jbe     short loc_14001132A
0x1400112ef  mov     rdx, rbp
0x1400112f2  call    OncRpcDrcpTableEntryRemove
0x1400112f7  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400112fc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011303  nop     dword ptr [rax+rax+00h]
0x140011308  mov     rdx, rbp
0x14001130b  mov     rcx, rdi
0x14001130e  call    OncRpcDrcpTableEntryFree
0x140011313  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140011318  lea     rcx, [rdi+38h]; SpinLock
0x14001131c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011323  nop     dword ptr [rax+rax+00h]
0x140011328  jmp     short loc_1400112C3
0x14001132a  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14001132f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011336  nop     dword ptr [rax+rax+00h]
0x14001133b  add     rsp, 40h
0x14001133f  pop     r14
0x140011341  pop     rdi
0x140011342  pop     rsi
0x140011343  pop     rbp
0x140011344  pop     rbx
0x140011345  retn
```
