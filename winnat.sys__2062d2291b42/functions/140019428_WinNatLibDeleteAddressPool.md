# WinNatLibDeleteAddressPool

- ea: `0x140019428`
- end: `0x1400195a8`
- name: `WinNatLibDeleteAddressPool`
- size: `384`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f738`
- `0x1400311f4`
- `0x140032430`

## callees

- `0x14000a638`
- `0x14000a7dc`
- `0x14000c9d8`
- `0x14000d474`
- `0x140019428`
- `0x1400195b0`
- `0x14001b58c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019522`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019522`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001949a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001949a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019461`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019461`

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
0x140019428  push    rbp
0x14001942a  push    rbx
0x14001942b  push    rsi
0x14001942c  push    rdi
0x14001942d  mov     rbp, rsp
0x140019430  sub     rsp, 58h
0x140019434  xor     eax, eax
0x140019436  lea     rbx, [rcx+500h]
0x14001943d  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140019441  mov     rsi, rcx
0x140019444  lea     rax, [rbp+var_38]
0x140019448  xorps   xmm0, xmm0
0x14001944b  mov     [rbp+var_30], rax
0x14001944f  mov     rcx, rbx; SpinLock
0x140019452  lea     rax, [rbp+var_38]
0x140019456  mov     rdi, rdx
0x140019459  mov     [rbp+var_38], rax
0x14001945d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140019461  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019468  nop     dword ptr [rax+rax+00h]
0x14001946d  lea     rdx, [rdi+140h]
0x140019474  mov     r9, [rdx]
0x140019477  cmp     [r9+8], rdx
0x14001947b  jnz     loc_1400195A1
0x140019481  mov     r8, [rdx+8]
0x140019485  cmp     [r8], rdx
0x140019488  jnz     loc_1400195A1
0x14001948e  mov     [r8], r9
0x140019491  mov     dl, al; NewIrql
0x140019493  mov     rcx, rbx; SpinLock
0x140019496  mov     [r9+8], r8
0x14001949a  call    cs:__imp_KeReleaseSpinLock
0x1400194a1  nop     dword ptr [rax+rax+00h]
0x1400194a6  lea     rdx, [rbp+LockHandle]
0x1400194aa  mov     rcx, rdi
0x1400194ad  call    RtlAcquireScalableWriteLock
0x1400194b2  mov     rcx, rdi
0x1400194b5  call    WinNatLibDeleteNat64PrefixTree
0x1400194ba  lea     r10, [rdi+158h]
0x1400194c1  mov     rcx, [r10]
0x1400194c4  jmp     short loc_140019519
0x1400194c6  or      byte ptr [rcx+0CCh], 2
0x1400194cd  mov     rdx, [rcx]
0x1400194d0  cmp     [rdx+8], rcx
0x1400194d4  jnz     loc_1400195A1
0x1400194da  lea     r9, [rcx+8]
0x1400194de  mov     rax, [r9]
0x1400194e1  cmp     [rax], rcx
0x1400194e4  jnz     loc_1400195A1
0x1400194ea  mov     [rax], rdx
0x1400194ed  mov     [rdx+8], rax
0x1400194f1  lea     rax, [rbp+var_38]
0x1400194f5  mov     r8, [rbp+var_30]
0x1400194f9  cmp     [r8], rax
0x1400194fc  jnz     loc_1400195A1
0x140019502  mov     rax, rcx
0x140019505  mov     [r9], r8
0x140019508  mov     rcx, rdx
0x14001950b  lea     rdx, [rbp+var_38]
0x14001950f  mov     [rax], rdx
0x140019512  mov     [r8], rax
0x140019515  mov     [rbp+var_30], rax
0x140019519  cmp     rcx, r10
0x14001951c  jnz     short loc_1400194C6
0x14001951e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140019522  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019529  nop     dword ptr [rax+rax+00h]
0x14001952e  mov     rbx, [rbp+var_38]
0x140019532  lea     rax, [rbp+var_38]
0x140019536  cmp     rbx, rax
0x140019539  jz      short loc_14001958F
0x14001953b  lea     rax, [rbp+var_38]
0x14001953f  cmp     [rbx+8], rax
0x140019543  jnz     short loc_1400195A1
0x140019545  mov     rax, [rbx]
0x140019548  cmp     [rax+8], rbx
0x14001954c  jnz     short loc_1400195A1
0x14001954e  lea     rcx, [rbp+var_38]
0x140019552  mov     [rbp+var_38], rax
0x140019556  mov     [rax+8], rcx
0x14001955a  lea     rdx, [rbx-8]
0x14001955e  lea     rcx, [rsi+80h]
0x140019565  call    WinNatDeleteSessionsOnAddress
0x14001956a  movzx   r9d, word ptr [rbx+64h]
0x14001956f  lea     rcx, [rsi+300h]
0x140019576  movzx   r8d, word ptr [rbx+62h]
0x14001957b  mov     rdx, [rbx+10h]
0x14001957f  call    WinNatDeleteBindingsForAddress
0x140019584  lea     rcx, [rbx-8]
0x140019588  call    WinNatLibDereferenceAddressEntry
0x14001958d  jmp     short loc_14001952E
0x14001958f  mov     rcx, rdi
0x140019592  call    WinNatLibDereferenceAddressPool
0x140019597  add     rsp, 58h
0x14001959b  pop     rdi
0x14001959c  pop     rsi
0x14001959d  pop     rbx
0x14001959e  pop     rbp
0x14001959f  retn
0x1400195a1  mov     ecx, 3
0x1400195a6  int     29h; Win8: RtlFailFast(ecx)
```
