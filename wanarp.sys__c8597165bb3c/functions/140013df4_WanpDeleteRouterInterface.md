# WanpDeleteRouterInterface

- ea: `0x140013df4`
- end: `0x140013fc0`
- name: `WanpDeleteRouterInterface`
- size: `460`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004124`

## callees

- `0x14000e280`
- `0x140013df4`
- `0x14001404c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013e28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ee9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013e28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ee9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ea6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013e70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013f2f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013e70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013f2f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013e3a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013eff`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013e3a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013eff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013e11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013ed6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013fa2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013e11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013ed6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013fa2`

## pseudocode

```c
__int64 __fastcall WanpDeleteRouterInterface(char *P, KIRQL a2)
{
  __int64 *v2; // rbx
  KSPIN_LOCK *v3; // r14
  char v5; // si
  KIRQL v6; // r15
  __int64 v7; // rdx
  KSPIN_LOCK *v8; // rcx
  KIRQL v9; // di
  KSPIN_LOCK v10; // r8
  __int64 **v11; // rdx

  v2 = (__int64 *)*((_QWORD *)P + 3);
  v3 = (KSPIN_LOCK *)(P + 56);
  KeReleaseSpinLock((PKSPIN_LOCK)P + 7, a2);
  v5 = P[20];
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2 + 15);
  KeAcquireSpinLockAtDpcLevel(v3);
  LOBYTE(v7) = v5;
  WanpFlushQueuedNetBufferLists(v2, v7);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 32, 0xFFFFFFFF) == 1 )
    WanpDeleteAdapter(v2);
  KeReleaseSpinLockFromDpcLevel(v3);
  if ( v5 )
    v2[21] = 0;
  else
    v2[22] = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 16, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag(P, 0);
  v8 = (KSPIN_LOCK *)(v2 + 15);
  if ( *(__int64 *)((char *)v2 + (v5 != 0 ? 8 : 0) + 168) )
  {
    KeReleaseSpinLock(v8, v6);
  }
  else
  {
    *((_BYTE *)v2 + 148) = 4;
    KeReleaseSpinLock(v8, v6);
    v9 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
    v10 = *v2;
    if ( *(__int64 **)(*v2 + 8) != v2 || (v11 = (__int64 **)v2[1], *v11 != v2) )
      __fastfail(3u);
    *v11 = (__int64 *)v10;
    *(_QWORD *)(v10 + 8) = v11;
    KeReleaseSpinLockFromDpcLevel(&SpinLock);
    KeReleaseSpinLock(&g_rwlAdapterLock, v9);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 32, 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter(v2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 32, 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter(v2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 32, 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x140013df4  push    rbx
0x140013df6  push    rbp
0x140013df7  push    rsi
0x140013df8  push    rdi
0x140013df9  push    r12
0x140013dfb  push    r14
0x140013dfd  push    r15
0x140013dff  sub     rsp, 20h
0x140013e03  mov     rbx, [rcx+18h]
0x140013e07  lea     r14, [rcx+38h]
0x140013e0b  mov     rdi, rcx
0x140013e0e  mov     rcx, r14; SpinLock
0x140013e11  call    cs:__imp_KeReleaseSpinLock
0x140013e18  nop     dword ptr [rax+rax+00h]
0x140013e1d  mov     sil, [rdi+14h]
0x140013e21  lea     rbp, [rbx+78h]
0x140013e25  mov     rcx, rbp; SpinLock
0x140013e28  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013e2f  nop     dword ptr [rax+rax+00h]
0x140013e34  mov     rcx, r14; SpinLock
0x140013e37  mov     r15b, al
0x140013e3a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013e41  nop     dword ptr [rax+rax+00h]
0x140013e46  mov     dl, sil
0x140013e49  mov     rcx, rbx
0x140013e4c  call    WanpFlushQueuedNetBufferLists
0x140013e51  or      r12d, 0FFFFFFFFh
0x140013e55  mov     edx, r12d
0x140013e58  lock xadd [rbx+80h], edx
0x140013e60  add     edx, r12d
0x140013e63  jnz     short loc_140013E6D
0x140013e65  mov     rcx, rbx; P
0x140013e68  call    WanpDeleteAdapter
0x140013e6d  mov     rcx, r14; SpinLock
0x140013e70  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013e77  nop     dword ptr [rax+rax+00h]
0x140013e7c  xor     r14d, r14d
0x140013e7f  test    sil, sil
0x140013e82  jz      short loc_140013E8D
0x140013e84  mov     [rbx+0A8h], r14
0x140013e8b  jmp     short loc_140013E94
0x140013e8d  mov     [rbx+0B0h], r14
0x140013e94  mov     eax, r12d
0x140013e97  lock xadd [rdi+40h], eax
0x140013e9c  add     eax, r12d
0x140013e9f  jnz     short loc_140013EB2
0x140013ea1  xor     edx, edx; Tag
0x140013ea3  mov     rcx, rdi; P
0x140013ea6  call    cs:__imp_ExFreePoolWithTag
0x140013ead  nop     dword ptr [rax+rax+00h]
0x140013eb2  neg     sil
0x140013eb5  mov     dl, r15b; NewIrql
0x140013eb8  mov     rcx, rbp; SpinLock
0x140013ebb  sbb     rax, rax
0x140013ebe  and     eax, 8
0x140013ec1  cmp     [rax+rbx+0A8h], r14
0x140013ec9  jnz     loc_140013FA2
0x140013ecf  mov     byte ptr [rbx+94h], 4
0x140013ed6  call    cs:__imp_KeReleaseSpinLock
0x140013edd  nop     dword ptr [rax+rax+00h]
0x140013ee2  lea     rcx, g_rwlAdapterLock; SpinLock
0x140013ee9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013ef0  nop     dword ptr [rax+rax+00h]
0x140013ef5  lea     rcx, SpinLock; SpinLock
0x140013efc  mov     dil, al
0x140013eff  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013f06  nop     dword ptr [rax+rax+00h]
0x140013f0b  mov     r8, [rbx]
0x140013f0e  cmp     [r8+8], rbx
0x140013f12  jnz     loc_140013F9B
0x140013f18  mov     rdx, [rbx+8]
0x140013f1c  cmp     [rdx], rbx
0x140013f1f  jnz     short loc_140013F9B
0x140013f21  mov     [rdx], r8
0x140013f24  lea     rcx, SpinLock; SpinLock
0x140013f2b  mov     [r8+8], rdx
0x140013f2f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013f36  nop     dword ptr [rax+rax+00h]
0x140013f3b  mov     dl, dil; NewIrql
0x140013f3e  lea     rcx, g_rwlAdapterLock; SpinLock
0x140013f45  call    cs:__imp_KeReleaseSpinLock
0x140013f4c  nop     dword ptr [rax+rax+00h]
0x140013f51  mov     eax, r12d
0x140013f54  lock xadd [rbx+80h], eax
0x140013f5c  add     eax, r12d
0x140013f5f  jnz     short loc_140013F69
0x140013f61  mov     rcx, rbx; P
0x140013f64  call    WanpDeleteAdapter
0x140013f69  mov     eax, r12d
0x140013f6c  lock xadd [rbx+80h], eax
0x140013f74  add     eax, r12d
0x140013f77  jnz     short loc_140013F81
0x140013f79  mov     rcx, rbx; P
0x140013f7c  call    WanpDeleteAdapter
0x140013f81  mov     eax, r12d
0x140013f84  lock xadd [rbx+80h], eax
0x140013f8c  add     eax, r12d
0x140013f8f  jnz     short loc_140013FAE
0x140013f91  mov     rcx, rbx; P
0x140013f94  call    WanpDeleteAdapter
0x140013f99  jmp     short loc_140013FAE
0x140013f9b  mov     ecx, 3
0x140013fa0  int     29h; Win8: RtlFailFast(ecx)
0x140013fa2  call    cs:__imp_KeReleaseSpinLock
0x140013fa9  nop     dword ptr [rax+rax+00h]
0x140013fae  xor     eax, eax
0x140013fb0  add     rsp, 20h
0x140013fb4  pop     r15
0x140013fb6  pop     r14
0x140013fb8  pop     r12
0x140013fba  pop     rdi
0x140013fbb  pop     rsi
0x140013fbc  pop     rbp
0x140013fbd  pop     rbx
0x140013fbe  retn
```
