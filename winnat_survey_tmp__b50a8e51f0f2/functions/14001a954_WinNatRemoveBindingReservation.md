# WinNatRemoveBindingReservation

- ea: `0x14001a954`
- end: `0x14001aa14`
- name: `WinNatRemoveBindingReservation`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, int, char, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001b7dc`

## callees

- `0x140004a80`
- `0x14000a638`
- `0x1400199fc`
- `0x140019d5c`
- `0x14001a954`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a9ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a9ed`

## pseudocode

```c
__int64 __fastcall WinNatRemoveBindingReservation(__int64 a1, __int64 a2, _WORD *a3, int a4, char a5, int a6)
{
  char v10; // r14
  struct _LIST_ENTRY **BindingUnderLock; // rax
  struct _LIST_ENTRY **v12; // rbx
  unsigned int v13; // edi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v10 = 0;
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  BindingUnderLock = WinNatFindBindingUnderLock(a1, a4, a3, a2, a5, 1, a6);
  v12 = BindingUnderLock;
  if ( BindingUnderLock )
  {
    if ( ((_BYTE)BindingUnderLock[11] & 1) != 0 )
    {
      v13 = 0;
      if ( !*((_DWORD *)BindingUnderLock + 16) )
      {
        WinNatFreeBindingUnderLock(BindingUnderLock);
        v10 = 1;
      }
      *((_BYTE *)v12 + 88) &= ~1u;
    }
    else
    {
      v13 = -1073741811;
    }
  }
  else
  {
    v13 = -1073741275;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v10 )
    WinNatCleanupBinding(v12);
  return v13;
}

```

## disassembly

```asm
0x14001a954  push    rbx
0x14001a956  push    rbp
0x14001a957  push    rsi
0x14001a958  push    rdi
0x14001a959  push    r14
0x14001a95b  sub     rsp, 60h
0x14001a95f  mov     rbx, rdx
0x14001a962  mov     rsi, rcx
0x14001a965  xorps   xmm0, xmm0
0x14001a968  lea     rdx, [rsp+88h+LockHandle]
0x14001a96d  xor     eax, eax
0x14001a96f  add     rcx, 40h ; '@'
0x14001a973  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14001a978  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14001a97d  mov     ebp, r9d
0x14001a980  mov     rdi, r8
0x14001a983  xor     r14b, r14b
0x14001a986  call    RtlAcquireScalableWriteLock
0x14001a98b  mov     eax, [rsp+88h+arg_28]
0x14001a992  mov     r9, rbx
0x14001a995  mov     [rsp+88h+var_58], eax
0x14001a999  mov     r8, rdi
0x14001a99c  mov     al, [rsp+88h+arg_20]
0x14001a9a3  mov     edx, ebp
0x14001a9a5  mov     [rsp+88h+var_60], 1
0x14001a9aa  mov     rcx, rsi
0x14001a9ad  mov     [rsp+88h+var_68], al
0x14001a9b1  call    WinNatFindBindingUnderLock
0x14001a9b6  mov     rbx, rax
0x14001a9b9  test    rax, rax
0x14001a9bc  jnz     short loc_14001A9C5
0x14001a9be  mov     edi, 0C0000225h
0x14001a9c3  jmp     short loc_14001A9E8
0x14001a9c5  test    byte ptr [rax+58h], 1
0x14001a9c9  jnz     short loc_14001A9D2
0x14001a9cb  mov     edi, 0C000000Dh
0x14001a9d0  jmp     short loc_14001A9E8
0x14001a9d2  xor     edi, edi
0x14001a9d4  cmp     [rax+40h], edi
0x14001a9d7  jnz     short loc_14001A9E4
0x14001a9d9  mov     rcx, rbx
0x14001a9dc  call    WinNatFreeBindingUnderLock
0x14001a9e1  mov     r14b, 1
0x14001a9e4  and     byte ptr [rbx+58h], 0FEh
0x14001a9e8  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14001a9ed  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001a9f4  nop     dword ptr [rax+rax+00h]
0x14001a9f9  test    r14b, r14b
0x14001a9fc  jz      short loc_14001AA06
0x14001a9fe  mov     rcx, rbx
0x14001aa01  call    WinNatCleanupBinding
0x14001aa06  mov     eax, edi
0x14001aa08  add     rsp, 60h
0x14001aa0c  pop     r14
0x14001aa0e  pop     rdi
0x14001aa0f  pop     rsi
0x14001aa10  pop     rbp
0x14001aa11  pop     rbx
0x14001aa12  retn
```
