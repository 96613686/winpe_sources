# UsbcCompleteIrp

- ea: `0x140003388`
- end: `0x14000345c`
- name: `UsbcCompleteIrp`
- size: `212`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400018b0`
- `0x140001acc`
- `0x140001bc8`
- `0x140002200`
- `0x140002630`
- `0x140002ad0`
- `0x140003470`
- `0x140007844`
- `0x140010650`
- `0x140022008`
- `0x140028800`
- `0x140028f7c`
- `0x14002ad60`
- `0x14002c08c`
- `0x14002c8a0`
- `0x14002d418`

## callees

- `0x140003388`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000340b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000340b`
- `ntoskrnl!IofCompleteRequest` at `0x1400033a1`
- `ntoskrnl!IofCompleteRequest` at `0x1400033a1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003438`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003438`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000341c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000341c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400033c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400033c8`

## pseudocode

```c
void __fastcall UsbcCompleteIrp(__int64 a1, int a2, IRP *a3)
{
  _QWORD *i; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  a3->IoStatus.Status = a2;
  IofCompleteRequest(a3, 0);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 248), &LockHandle);
  for ( i = *(_QWORD **)(a1 + 232); i != (_QWORD *)(a1 + 232); i = (_QWORD *)*i )
  {
    v6 = (_QWORD *)*i;
    if ( (IRP *)i[3] == a3 )
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
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a3, 0x20u);
}

```

## disassembly

```asm
0x140003388  mov     [rsp+arg_0], rbx
0x14000338d  push    rdi
0x14000338e  sub     rsp, 40h
0x140003392  mov     rdi, rcx
0x140003395  mov     [r8+30h], edx
0x140003399  xor     edx, edx; PriorityBoost
0x14000339b  mov     rcx, r8; Irp
0x14000339e  mov     rbx, r8
0x1400033a1  call    cs:__imp_IofCompleteRequest
0x1400033a8  nop     dword ptr [rax+rax+00h]
0x1400033ad  xorps   xmm0, xmm0
0x1400033b0  lea     rcx, [rdi+0F8h]; SpinLock
0x1400033b7  xor     eax, eax
0x1400033b9  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400033be  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400033c3  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1400033c8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400033cf  nop     dword ptr [rax+rax+00h]
0x1400033d4  lea     rdx, [rdi+0E8h]
0x1400033db  mov     rax, [rdx]
0x1400033de  cmp     rax, rdx
0x1400033e1  jz      short loc_140003417
0x1400033e3  mov     rcx, [rax]
0x1400033e6  cmp     [rax+18h], rbx
0x1400033ea  jnz     short loc_140003450
0x1400033ec  cmp     [rcx+8], rax
0x1400033f0  jnz     short loc_140003455
0x1400033f2  mov     rdx, [rax+8]
0x1400033f6  cmp     [rdx], rax
0x1400033f9  jnz     short loc_140003455
0x1400033fb  mov     [rdx], rcx
0x1400033fe  mov     [rcx+8], rdx
0x140003402  mov     edx, 43627355h; Tag
0x140003407  lea     rcx, [rax-8]; P
0x14000340b  call    cs:__imp_ExFreePoolWithTag
0x140003412  nop     dword ptr [rax+rax+00h]
0x140003417  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14000341c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003423  nop     dword ptr [rax+rax+00h]
0x140003428  lea     rcx, [rdi+0C8h]; RemoveLock
0x14000342f  mov     r8d, 20h ; ' '; RemlockSize
0x140003435  mov     rdx, rbx; Tag
0x140003438  call    cs:__imp_IoReleaseRemoveLockEx
0x14000343f  nop     dword ptr [rax+rax+00h]
0x140003444  mov     rbx, [rsp+48h+arg_0]
0x140003449  add     rsp, 40h
0x14000344d  pop     rdi
0x14000344e  retn
0x140003450  mov     rax, rcx
0x140003453  jmp     short loc_1400033DE
0x140003455  mov     ecx, 3
0x14000345a  int     29h; Win8: RtlFailFast(ecx)
```
