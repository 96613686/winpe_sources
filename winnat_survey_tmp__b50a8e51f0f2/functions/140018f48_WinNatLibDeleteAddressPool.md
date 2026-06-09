# WinNatLibDeleteAddressPool

- ea: `0x140018f48`
- end: `0x1400190c8`
- name: `WinNatLibDeleteAddressPool`
- size: `384`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f6e0`
- `0x1400300c4`
- `0x140031300`

## callees

- `0x14000a638`
- `0x14000a7dc`
- `0x14000c9d8`
- `0x14000d4a4`
- `0x140018f48`
- `0x1400190d0`
- `0x14001b0ac`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019042`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019042`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f81`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteAddressPool(__int64 a1, _QWORD *a2)
{
  KSPIN_LOCK *v2; // rbx
  KIRQL v5; // al
  __int64 v6; // r9
  _QWORD *v7; // r8
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // r8
  __int64 ***v12; // rax
  __int64 *v13; // rbx
  __int64 *v14; // rax
  __int64 *v16; // [rsp+20h] [rbp-38h] BYREF
  __int64 **v17; // [rsp+28h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v2 = (KSPIN_LOCK *)(a1 + 1280);
  v17 = &v16;
  v16 = (__int64 *)&v16;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1280));
  v6 = a2[40];
  if ( *(_QWORD **)(v6 + 8) != a2 + 40 || (v7 = (_QWORD *)a2[41], (_QWORD *)*v7 != a2 + 40) )
LABEL_15:
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  KeReleaseSpinLock(v2, v5);
  RtlAcquireScalableWriteLock((__int64)a2, &LockHandle);
  WinNatLibDeleteNat64PrefixTree((__int64)a2);
  v8 = (_QWORD *)a2[43];
  while ( v8 != a2 + 43 )
  {
    *((_BYTE *)v8 + 204) |= 2u;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_15;
    v10 = (_QWORD *)v8[1];
    if ( (_QWORD *)*v10 != v8 )
      goto LABEL_15;
    *v10 = v9;
    v9[1] = v10;
    v11 = v17;
    if ( *v17 != (__int64 *)&v16 )
      goto LABEL_15;
    v12 = (__int64 ***)v8;
    v8[1] = v17;
    v8 = v9;
    *v12 = &v16;
    *v11 = v12;
    v17 = (__int64 **)v12;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v13 = v16;
    if ( v16 == (__int64 *)&v16 )
      return WinNatLibDereferenceAddressPool(a2);
    if ( (__int64 **)v16[1] != &v16 )
      goto LABEL_15;
    v14 = (__int64 *)*v16;
    if ( *(__int64 **)(*v16 + 8) != v16 )
      goto LABEL_15;
    v16 = (__int64 *)*v16;
    v14[1] = (__int64)&v16;
    WinNatDeleteSessionsOnAddress(a1 + 128, v13 - 1);
    WinNatDeleteBindingsForAddress(a1 + 768, v13[2], *((unsigned __int16 *)v13 + 49), *((unsigned __int16 *)v13 + 50));
    WinNatLibDereferenceAddressEntry(v13 - 1);
  }
}

```

## disassembly

```asm
0x140018f48  push    rbp
0x140018f4a  push    rbx
0x140018f4b  push    rsi
0x140018f4c  push    rdi
0x140018f4d  mov     rbp, rsp
0x140018f50  sub     rsp, 58h
0x140018f54  xor     eax, eax
0x140018f56  lea     rbx, [rcx+500h]
0x140018f5d  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140018f61  mov     rsi, rcx
0x140018f64  lea     rax, [rbp+var_38]
0x140018f68  xorps   xmm0, xmm0
0x140018f6b  mov     [rbp+var_30], rax
0x140018f6f  mov     rcx, rbx; SpinLock
0x140018f72  lea     rax, [rbp+var_38]
0x140018f76  mov     rdi, rdx
0x140018f79  mov     [rbp+var_38], rax
0x140018f7d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140018f81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018f88  nop     dword ptr [rax+rax+00h]
0x140018f8d  lea     rdx, [rdi+140h]
0x140018f94  mov     r9, [rdx]
0x140018f97  cmp     [r9+8], rdx
0x140018f9b  jnz     loc_1400190C1
0x140018fa1  mov     r8, [rdx+8]
0x140018fa5  cmp     [r8], rdx
0x140018fa8  jnz     loc_1400190C1
0x140018fae  mov     [r8], r9
0x140018fb1  mov     dl, al; NewIrql
0x140018fb3  mov     rcx, rbx; SpinLock
0x140018fb6  mov     [r9+8], r8
0x140018fba  call    cs:__imp_KeReleaseSpinLock
0x140018fc1  nop     dword ptr [rax+rax+00h]
0x140018fc6  lea     rdx, [rbp+LockHandle]
0x140018fca  mov     rcx, rdi
0x140018fcd  call    RtlAcquireScalableWriteLock
0x140018fd2  mov     rcx, rdi
0x140018fd5  call    WinNatLibDeleteNat64PrefixTree
0x140018fda  lea     r10, [rdi+158h]
0x140018fe1  mov     rcx, [r10]
0x140018fe4  jmp     short loc_140019039
0x140018fe6  or      byte ptr [rcx+0CCh], 2
0x140018fed  mov     rdx, [rcx]
0x140018ff0  cmp     [rdx+8], rcx
0x140018ff4  jnz     loc_1400190C1
0x140018ffa  lea     r9, [rcx+8]
0x140018ffe  mov     rax, [r9]
0x140019001  cmp     [rax], rcx
0x140019004  jnz     loc_1400190C1
0x14001900a  mov     [rax], rdx
0x14001900d  mov     [rdx+8], rax
0x140019011  lea     rax, [rbp+var_38]
0x140019015  mov     r8, [rbp+var_30]
0x140019019  cmp     [r8], rax
0x14001901c  jnz     loc_1400190C1
0x140019022  mov     rax, rcx
0x140019025  mov     [r9], r8
0x140019028  mov     rcx, rdx
0x14001902b  lea     rdx, [rbp+var_38]
0x14001902f  mov     [rax], rdx
0x140019032  mov     [r8], rax
0x140019035  mov     [rbp+var_30], rax
0x140019039  cmp     rcx, r10
0x14001903c  jnz     short loc_140018FE6
0x14001903e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140019042  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019049  nop     dword ptr [rax+rax+00h]
0x14001904e  mov     rbx, [rbp+var_38]
0x140019052  lea     rax, [rbp+var_38]
0x140019056  cmp     rbx, rax
0x140019059  jz      short loc_1400190AF
0x14001905b  lea     rax, [rbp+var_38]
0x14001905f  cmp     [rbx+8], rax
0x140019063  jnz     short loc_1400190C1
0x140019065  mov     rax, [rbx]
0x140019068  cmp     [rax+8], rbx
0x14001906c  jnz     short loc_1400190C1
0x14001906e  lea     rcx, [rbp+var_38]
0x140019072  mov     [rbp+var_38], rax
0x140019076  mov     [rax+8], rcx
0x14001907a  lea     rdx, [rbx-8]
0x14001907e  lea     rcx, [rsi+80h]
0x140019085  call    WinNatDeleteSessionsOnAddress
0x14001908a  movzx   r9d, word ptr [rbx+64h]
0x14001908f  lea     rcx, [rsi+300h]
0x140019096  movzx   r8d, word ptr [rbx+62h]
0x14001909b  mov     rdx, [rbx+10h]
0x14001909f  call    WinNatDeleteBindingsForAddress
0x1400190a4  lea     rcx, [rbx-8]
0x1400190a8  call    WinNatLibDereferenceAddressEntry
0x1400190ad  jmp     short loc_14001904E
0x1400190af  mov     rcx, rdi
0x1400190b2  call    WinNatLibDereferenceAddressPool
0x1400190b7  add     rsp, 58h
0x1400190bb  pop     rdi
0x1400190bc  pop     rsi
0x1400190bd  pop     rbx
0x1400190be  pop     rbp
0x1400190bf  retn
0x1400190c1  mov     ecx, 3
0x1400190c6  int     29h; Win8: RtlFailFast(ecx)
```
