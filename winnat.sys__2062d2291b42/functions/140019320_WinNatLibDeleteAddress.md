# WinNatLibDeleteAddress

- ea: `0x140019320`
- end: `0x140019420`
- name: `WinNatLibDeleteAddress`
- size: `256`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140007bb0`
- `0x14000f624`
- `0x140014dcc`
- `0x140032228`

## callees

- `0x14000a638`
- `0x14000a7dc`
- `0x14000b404`
- `0x14000c9d8`
- `0x140019320`
- `0x14001b58c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400193ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400193ae`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int16 a5)
{
  __int64 result; // rax
  __int64 v7; // rbx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  result = WinNatLibFindAddressEntry((PKSPIN_LOCK)(a1 + 1280), a5, 0, 0, 0, 0);
  v7 = result;
  if ( result )
  {
    RtlAcquireScalableWriteLock(*(_QWORD *)(result + 112), &LockHandle);
    v8 = *(_QWORD *)(v7 + 8);
    if ( *(_QWORD *)(v8 + 8) != v7 + 8 || (v9 = *(_QWORD **)(v7 + 16), *v9 != v7 + 8) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    *(_BYTE *)(v7 + 212) |= 2u;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    WinNatDeleteSessionsOnAddress(a1 + 128, v7);
    WinNatDeleteBindingsForAddress(
      a1 + 768,
      *(_QWORD *)(v7 + 24),
      *(unsigned __int16 *)(v7 + 106),
      *(unsigned __int16 *)(v7 + 108));
    _InterlockedAdd(
      (volatile signed __int32 *)(*(_QWORD *)(v7 + 112) + 368LL),
      *(unsigned __int16 *)(v7 + 106) - *(unsigned __int16 *)(v7 + 108) - 1);
    WinNatLibDereferenceAddressEntry(v7);
    return WinNatLibDereferenceAddressEntry(v7);
  }
  return result;
}

```

## disassembly

```asm
0x140019320  mov     r11, rsp
0x140019323  mov     [r11+8], rbx
0x140019327  push    rdi
0x140019328  sub     rsp, 70h
0x14001932c  xor     eax, eax
0x14001932e  xorps   xmm0, xmm0
0x140019331  mov     [r11-38h], rax
0x140019335  mov     rdi, rcx
0x140019338  mov     [r11-40h], rax
0x14001933c  add     rcx, 500h; SpinLock
0x140019343  mov     [rsp+78h+var_48], al; char
0x140019347  mov     [rsp+78h+var_50], ax; __int16
0x14001934c  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140019351  mov     [r11-18h], rax
0x140019355  movzx   eax, [rsp+78h+arg_20]
0x14001935d  mov     [rsp+78h+var_58], ax; __int16
0x140019362  call    WinNatLibFindAddressEntry
0x140019367  mov     rbx, rax
0x14001936a  test    rax, rax
0x14001936d  jz      loc_14001940A
0x140019373  mov     rcx, [rax+70h]
0x140019377  lea     rdx, [rsp+78h+LockHandle]
0x14001937c  call    RtlAcquireScalableWriteLock
0x140019381  lea     rax, [rbx+8]
0x140019385  mov     rdx, [rax]
0x140019388  cmp     [rdx+8], rax
0x14001938c  jnz     loc_140019419
0x140019392  mov     rcx, [rax+8]
0x140019396  cmp     [rcx], rax
0x140019399  jnz     short loc_140019419
0x14001939b  mov     [rcx], rdx
0x14001939e  mov     [rdx+8], rcx
0x1400193a2  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400193a7  or      byte ptr [rbx+0D4h], 2
0x1400193ae  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400193b5  nop     dword ptr [rax+rax+00h]
0x1400193ba  lea     rcx, [rdi+80h]
0x1400193c1  mov     rdx, rbx
0x1400193c4  call    WinNatDeleteSessionsOnAddress
0x1400193c9  movzx   r9d, word ptr [rbx+6Ch]
0x1400193ce  lea     rcx, [rdi+300h]
0x1400193d5  movzx   r8d, word ptr [rbx+6Ah]
0x1400193da  mov     rdx, [rbx+18h]
0x1400193de  call    WinNatDeleteBindingsForAddress
0x1400193e3  movzx   eax, word ptr [rbx+6Ch]
0x1400193e7  movzx   ecx, word ptr [rbx+6Ah]
0x1400193eb  sub     ecx, eax
0x1400193ed  mov     rax, [rbx+70h]
0x1400193f1  dec     ecx
0x1400193f3  lock add [rax+170h], ecx
0x1400193fa  mov     rcx, rbx
0x1400193fd  call    WinNatLibDereferenceAddressEntry
0x140019402  mov     rcx, rbx
0x140019405  call    WinNatLibDereferenceAddressEntry
0x14001940a  mov     rbx, [rsp+78h+arg_0]
0x140019412  add     rsp, 70h
0x140019416  pop     rdi
0x140019417  retn
0x140019419  mov     ecx, 3
0x14001941e  int     29h; Win8: RtlFailFast(ecx)
```
