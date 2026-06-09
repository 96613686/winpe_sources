# UsbcReleaseRemoveLock

- ea: `0x1400054a0`
- end: `0x140005543`
- name: `UsbcReleaseRemoveLock`
- size: `163`
- prototype: ``
- caller_count: `35`
- callee_count: `1`
- tags: ``

## callers

- `0x14000159c`
- `0x140003d08`
- `0x140003e88`
- `0x1400046c0`
- `0x1400047d0`
- `0x140004b08`
- `0x140004e30`
- `0x140004ed0`
- `0x140004f50`
- `0x1400052c0`
- `0x140005350`
- `0x1400055c0`
- `0x140005eb0`
- `0x140006f58`
- `0x140007c38`
- `0x140007e70`
- `0x140008230`
- `0x1400084c0`
- `0x140009210`
- `0x140009804`
- `0x140009d20`
- `0x140009f10`
- `0x14000a390`
- `0x14000a448`
- `0x14000b670`
- `0x14000d630`
- `0x14000d81c`
- `0x14000de40`
- `0x14000e360`
- `0x140013eb0`
- `0x140014060`
- `0x1400145e0`
- `0x140014890`
- `0x14002cfb0`
- `0x14002d458`

## callees

- `0x1400054a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000550e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000550e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000551f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000551f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400054cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400054cb`

## pseudocode

```c
void __fastcall UsbcReleaseRemoveLock(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *i; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 248), &LockHandle);
  v4 = (_QWORD *)(a1 + 232);
  for ( i = (_QWORD *)*v4; i != v4; i = (_QWORD *)*i )
  {
    v6 = (_QWORD *)*i;
    if ( i[3] == a2 )
    {
      if ( (_QWORD *)v6[1] != i || (v7 = (_QWORD *)i[1], (_QWORD *)*v7 != i) )
        __fastfail(3u);
      *v7 = v6;
      v6[1] = v7;
      ExFreePoolWithTag(i - 1, 0x43627355u);
      break;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x1400054a0  mov     [rsp+arg_0], rbx
0x1400054a5  push    rdi
0x1400054a6  sub     rsp, 40h
0x1400054aa  mov     rdi, rdx
0x1400054ad  mov     rbx, rcx
0x1400054b0  xorps   xmm0, xmm0
0x1400054b3  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400054b8  xor     eax, eax
0x1400054ba  add     rcx, 0F8h; SpinLock
0x1400054c1  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400054c6  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1400054cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400054d2  nop     dword ptr [rax+rax+00h]
0x1400054d7  add     rbx, 0E8h
0x1400054de  mov     rax, [rbx]
0x1400054e1  cmp     rax, rbx
0x1400054e4  jz      short loc_14000551A
0x1400054e6  lea     rcx, [rax-8]; P
0x1400054ea  mov     rdx, [rax]
0x1400054ed  cmp     [rcx+20h], rdi
0x1400054f1  jnz     short loc_140005537
0x1400054f3  cmp     [rdx+8], rax
0x1400054f7  jnz     short loc_14000553C
0x1400054f9  mov     r8, [rax+8]
0x1400054fd  cmp     [r8], rax
0x140005500  jnz     short loc_14000553C
0x140005502  mov     [r8], rdx
0x140005505  mov     [rdx+8], r8
0x140005509  mov     edx, 43627355h; Tag
0x14000550e  call    cs:__imp_ExFreePoolWithTag
0x140005515  nop     dword ptr [rax+rax+00h]
0x14000551a  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14000551f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005526  nop     dword ptr [rax+rax+00h]
0x14000552b  mov     rbx, [rsp+48h+arg_0]
0x140005530  add     rsp, 40h
0x140005534  pop     rdi
0x140005535  retn
0x140005537  mov     rax, rdx
0x14000553a  jmp     short loc_1400054E1
0x14000553c  mov     ecx, 3
0x140005541  int     29h; Win8: RtlFailFast(ecx)
```
