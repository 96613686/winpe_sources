# UsbcForwardIrp

- ea: `0x1400029d0`
- end: `0x140002abe`
- name: `UsbcForwardIrp`
- size: `238`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400018b0`
- `0x140001acc`
- `0x140002200`
- `0x140002630`
- `0x140022008`
- `0x14002ad60`
- `0x14002c08c`
- `0x14002c8a0`
- `0x14002d458`

## callees

- `0x1400029d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002a66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a66`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002a93`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002a93`
- `ntoskrnl!IofCallDriver` at `0x1400029fa`
- `ntoskrnl!IofCallDriver` at `0x1400029fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002a77`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002a77`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002a23`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002a23`

## pseudocode

```c
__int64 __fastcall UsbcForwardIrp(__int64 a1, struct _DEVICE_OBJECT *a2, IRP *a3)
{
  unsigned int v5; // esi
  _QWORD *i; // rcx
  _QWORD *v7; // rdx
  _QWORD *v8; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  ++a3->CurrentLocation;
  ++a3->Tail.Overlay.CurrentStackLocation;
  v5 = IofCallDriver(a2, a3);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 248), &LockHandle);
  for ( i = *(_QWORD **)(a1 + 232); i != (_QWORD *)(a1 + 232); i = (_QWORD *)*i )
  {
    v7 = (_QWORD *)*i;
    if ( (IRP *)i[3] == a3 )
    {
      if ( (_QWORD *)v7[1] != i || (v8 = (_QWORD *)i[1], (_QWORD *)*v8 != i) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = v8;
      ExFreePoolWithTag(i - 1, 0x43627355u);
      break;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a3, 0x20u);
  return v5;
}

```

## disassembly

```asm
0x1400029d0  mov     [rsp+arg_0], rbx
0x1400029d5  mov     [rsp+arg_8], rsi
0x1400029da  push    rdi
0x1400029db  sub     rsp, 40h
0x1400029df  inc     byte ptr [r8+43h]
0x1400029e3  mov     rax, rdx
0x1400029e6  add     qword ptr [r8+0B8h], 48h ; 'H'
0x1400029ee  mov     rdi, rcx
0x1400029f1  mov     rcx, rax; DeviceObject
0x1400029f4  mov     rdx, r8; Irp
0x1400029f7  mov     rbx, r8
0x1400029fa  call    cs:__imp_IofCallDriver
0x140002a01  nop     dword ptr [rax+rax+00h]
0x140002a06  xorps   xmm0, xmm0
0x140002a09  lea     rcx, [rdi+0F8h]; SpinLock
0x140002a10  mov     esi, eax
0x140002a12  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140002a17  xor     eax, eax
0x140002a19  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140002a1e  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140002a23  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002a2a  nop     dword ptr [rax+rax+00h]
0x140002a2f  lea     r8, [rdi+0E8h]
0x140002a36  mov     rcx, [r8]
0x140002a39  cmp     rcx, r8
0x140002a3c  jz      short loc_140002A72
0x140002a3e  mov     rdx, [rcx]
0x140002a41  cmp     [rcx+18h], rbx
0x140002a45  jnz     short loc_140002AB2
0x140002a47  cmp     [rdx+8], rcx
0x140002a4b  jnz     short loc_140002AB7
0x140002a4d  mov     r8, [rcx+8]
0x140002a51  cmp     [r8], rcx
0x140002a54  jnz     short loc_140002AB7
0x140002a56  mov     [r8], rdx
0x140002a59  add     rcx, 0FFFFFFFFFFFFFFF8h; P
0x140002a5d  mov     [rdx+8], r8
0x140002a61  mov     edx, 43627355h; Tag
0x140002a66  call    cs:__imp_ExFreePoolWithTag
0x140002a6d  nop     dword ptr [rax+rax+00h]
0x140002a72  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140002a77  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002a7e  nop     dword ptr [rax+rax+00h]
0x140002a83  lea     rcx, [rdi+0C8h]; RemoveLock
0x140002a8a  mov     r8d, 20h ; ' '; RemlockSize
0x140002a90  mov     rdx, rbx; Tag
0x140002a93  call    cs:__imp_IoReleaseRemoveLockEx
0x140002a9a  nop     dword ptr [rax+rax+00h]
0x140002a9f  mov     rbx, [rsp+48h+arg_0]
0x140002aa4  mov     eax, esi
0x140002aa6  mov     rsi, [rsp+48h+arg_8]
0x140002aab  add     rsp, 40h
0x140002aaf  pop     rdi
0x140002ab0  retn
0x140002ab2  mov     rcx, rdx
0x140002ab5  jmp     short loc_140002A39
0x140002ab7  mov     ecx, 3
0x140002abc  int     29h; Win8: RtlFailFast(ecx)
```
