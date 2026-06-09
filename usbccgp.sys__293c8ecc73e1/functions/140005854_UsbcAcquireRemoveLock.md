# UsbcAcquireRemoveLock

- ea: `0x140005854`
- end: `0x140005936`
- name: `UsbcAcquireRemoveLock`
- size: `226`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055c0`
- `0x140005750`
- `0x1400059e4`
- `0x140007a8c`
- `0x140007c38`
- `0x140009590`
- `0x14000a068`
- `0x14000eb6c`

## callees

- `0x140005854`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005915`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005915`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400058e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400058e2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140005894`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140005894`
- `ntoskrnl!ExAllocatePool2` at `0x1400058b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400058b4`

## pseudocode

```c
__int64 __fastcall UsbcAcquireRemoveLock(__int64 a1, int a2, void *a3)
{
  NTSTATUS v6; // esi
  __int64 Pool2; // rax
  __int64 v8; // rbx
  _QWORD *v9; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a3, File, 1u, 0x20u);
  if ( v6 >= 0 )
  {
    Pool2 = ExAllocatePool2(64, 40, 1130525525);
    v8 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 1801678668;
      *(_DWORD *)(Pool2 + 24) = a2;
      *(_QWORD *)(Pool2 + 32) = a3;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 248), &LockHandle);
      v9 = *(_QWORD **)(a1 + 240);
      if ( *v9 != a1 + 232 )
        __fastfail(3u);
      *(_QWORD *)(v8 + 8) = a1 + 232;
      *(_QWORD *)(v8 + 16) = v9;
      *v9 = v8 + 8;
      *(_QWORD *)(a1 + 240) = v8 + 8;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005854  push    rbx
0x140005856  push    rbp
0x140005857  push    rsi
0x140005858  push    rdi
0x140005859  push    r14
0x14000585b  sub     rsp, 50h
0x14000585f  xor     eax, eax
0x140005861  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140005869  mov     rbp, r8
0x14000586c  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140005871  mov     r14d, edx
0x140005874  lea     r8, File; File
0x14000587b  mov     rdi, rcx
0x14000587e  xorps   xmm0, xmm0
0x140005881  lea     r9d, [rax+1]; Line
0x140005885  add     rcx, 0C8h; RemoveLock
0x14000588c  mov     rdx, rbp; Tag
0x14000588f  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140005894  call    cs:__imp_IoAcquireRemoveLockEx
0x14000589b  nop     dword ptr [rax+rax+00h]
0x1400058a0  mov     esi, eax
0x1400058a2  test    eax, eax
0x1400058a4  js      short loc_140005921
0x1400058a6  mov     edx, 28h ; '('
0x1400058ab  mov     r8d, 43627355h
0x1400058b1  lea     ecx, [rdx+18h]
0x1400058b4  call    cs:__imp_ExAllocatePool2
0x1400058bb  nop     dword ptr [rax+rax+00h]
0x1400058c0  mov     rbx, rax
0x1400058c3  test    rax, rax
0x1400058c6  jz      short loc_140005921
0x1400058c8  lea     rcx, [rdi+0F8h]; SpinLock
0x1400058cf  mov     dword ptr [rax], 6B636F4Ch
0x1400058d5  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400058da  mov     [rax+18h], r14d
0x1400058de  mov     [rax+20h], rbp
0x1400058e2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400058e9  nop     dword ptr [rax+rax+00h]
0x1400058ee  lea     rcx, [rdi+0E8h]
0x1400058f5  mov     rdx, [rcx+8]
0x1400058f9  cmp     [rdx], rcx
0x1400058fc  jnz     short loc_14000592F
0x1400058fe  lea     rax, [rbx+8]
0x140005902  mov     [rax], rcx
0x140005905  mov     [rax+8], rdx
0x140005909  mov     [rdx], rax
0x14000590c  mov     [rcx+8], rax
0x140005910  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140005915  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000591c  nop     dword ptr [rax+rax+00h]
0x140005921  mov     eax, esi
0x140005923  add     rsp, 50h
0x140005927  pop     r14
0x140005929  pop     rdi
0x14000592a  pop     rsi
0x14000592b  pop     rbp
0x14000592c  pop     rbx
0x14000592d  retn
0x14000592f  mov     ecx, 3
0x140005934  int     29h; Win8: RtlFailFast(ecx)
```
