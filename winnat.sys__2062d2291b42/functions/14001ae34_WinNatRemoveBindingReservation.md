# WinNatRemoveBindingReservation

- ea: `0x14001ae34`
- end: `0x14001aef4`
- name: `WinNatRemoveBindingReservation`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001bcbc`

## callees

- `0x140004a80`
- `0x14000a638`
- `0x140019edc`
- `0x14001a23c`
- `0x14001ae34`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001aecd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001aecd`

## pseudocode

```c
__int64 __fastcall WinNatRemoveBindingReservation(__int64 a1, __int64 a2, _WORD *a3, int a4, char a5, int a6)
{
  char v10; // r14
  struct _LIST_ENTRY **BindingUnderLock; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _LIST_ENTRY **v14; // rbx
  unsigned int v15; // edi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v10 = 0;
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  BindingUnderLock = WinNatFindBindingUnderLock(a1, a4, a3, a2, a5, 1, a6);
  v14 = BindingUnderLock;
  if ( BindingUnderLock )
  {
    if ( ((_BYTE)BindingUnderLock[11] & 1) != 0 )
    {
      v15 = 0;
      if ( !*((_DWORD *)BindingUnderLock + 16) )
      {
        WinNatFreeBindingUnderLock((__int64)BindingUnderLock, v12, v13);
        v10 = 1;
      }
      *((_BYTE *)v14 + 88) &= ~1u;
    }
    else
    {
      v15 = -1073741811;
    }
  }
  else
  {
    v15 = -1073741275;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v10 )
    WinNatCleanupBinding(v14);
  return v15;
}

```

## disassembly

```asm
0x14001ae34  push    rbx
0x14001ae36  push    rbp
0x14001ae37  push    rsi
0x14001ae38  push    rdi
0x14001ae39  push    r14
0x14001ae3b  sub     rsp, 60h
0x14001ae3f  mov     rbx, rdx
0x14001ae42  mov     rsi, rcx
0x14001ae45  xorps   xmm0, xmm0
0x14001ae48  lea     rdx, [rsp+88h+LockHandle]
0x14001ae4d  xor     eax, eax
0x14001ae4f  add     rcx, 40h ; '@'
0x14001ae53  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14001ae58  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14001ae5d  mov     ebp, r9d
0x14001ae60  mov     rdi, r8
0x14001ae63  xor     r14b, r14b
0x14001ae66  call    RtlAcquireScalableWriteLock
0x14001ae6b  mov     eax, [rsp+88h+arg_28]
0x14001ae72  mov     r9, rbx
0x14001ae75  mov     [rsp+88h+var_58], eax
0x14001ae79  mov     r8, rdi
0x14001ae7c  mov     al, [rsp+88h+arg_20]
0x14001ae83  mov     edx, ebp
0x14001ae85  mov     [rsp+88h+var_60], 1
0x14001ae8a  mov     rcx, rsi
0x14001ae8d  mov     [rsp+88h+var_68], al
0x14001ae91  call    WinNatFindBindingUnderLock
0x14001ae96  mov     rbx, rax
0x14001ae99  test    rax, rax
0x14001ae9c  jnz     short loc_14001AEA5
0x14001ae9e  mov     edi, 0C0000225h
0x14001aea3  jmp     short loc_14001AEC8
0x14001aea5  test    byte ptr [rax+58h], 1
0x14001aea9  jnz     short loc_14001AEB2
0x14001aeab  mov     edi, 0C000000Dh
0x14001aeb0  jmp     short loc_14001AEC8
0x14001aeb2  xor     edi, edi
0x14001aeb4  cmp     [rax+40h], edi
0x14001aeb7  jnz     short loc_14001AEC4
0x14001aeb9  mov     rcx, rbx
0x14001aebc  call    WinNatFreeBindingUnderLock
0x14001aec1  mov     r14b, 1
0x14001aec4  and     byte ptr [rbx+58h], 0FEh
0x14001aec8  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14001aecd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001aed4  nop     dword ptr [rax+rax+00h]
0x14001aed9  test    r14b, r14b
0x14001aedc  jz      short loc_14001AEE6
0x14001aede  mov     rcx, rbx
0x14001aee1  call    WinNatCleanupBinding
0x14001aee6  mov     eax, edi
0x14001aee8  add     rsp, 60h
0x14001aeec  pop     r14
0x14001aeee  pop     rdi
0x14001aeef  pop     rsi
0x14001aef0  pop     rbp
0x14001aef1  pop     rbx
0x14001aef2  retn
```
