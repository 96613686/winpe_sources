# WanpUnmapServerInterface

- ea: `0x14000f250`
- end: `0x14000f3f5`
- name: `WanpUnmapServerInterface`
- size: `421`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400028b0`
- `0x1400124bc`

## callees

- `0x1400024d0`
- `0x140002ac0`
- `0x1400033f4`
- `0x14000f250`
- `0x14000f728`
- `0x14000f78c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f2d6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f2f0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f36b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f37b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f2d6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f2f0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f36b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f37b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f2c3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f358`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f2c3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f358`
- `ntoskrnl!KeLowerIrql` at `0x14000f328`
- `ntoskrnl!KeLowerIrql` at `0x14000f3b3`
- `ntoskrnl!KeLowerIrql` at `0x14000f328`
- `ntoskrnl!KeLowerIrql` at `0x14000f3b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f317`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f317`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3a2`

## pseudocode

```c
__int64 __fastcall WanpUnmapServerInterface(__int64 a1, KIRQL a2, char a3)
{
  unsigned int v6; // edi
  unsigned __int64 v7; // rcx
  __int64 v8; // rsi
  int *v9; // rbx
  KSPIN_LOCK *v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // rcx
  KSPIN_LOCK *v13; // rcx

  if ( *(_BYTE *)(a1 + 148) != 6 )
  {
    v6 = 0;
LABEL_10:
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 120));
    if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      KeReleaseSpinLock(&SpinLock, a2);
    else
      KeLowerIrql(a2);
    LOBYTE(v12) = a3;
    WanpSetCloseEventIfRequired(v12);
    WanpReleaseResource((__int64)&g_wrBindMutex);
    return v6;
  }
  v6 = 0;
  v7 = -(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFF8uLL;
  v8 = *(_QWORD *)(v7 + a1 + 176);
  if ( !v8 )
    goto LABEL_10;
  v9 = (int *)(v8 + 164);
  if ( g_bEnableLinkDownAtStop )
    WanpRemoveConnections(a3, *v9);
  LOBYTE(v7) = a3;
  if ( !(unsigned __int8)WanpIsConnectionTableEmpty(v7, (unsigned int)*v9) )
  {
    v6 = -1073741567;
    goto LABEL_10;
  }
  v10 = (KSPIN_LOCK *)(v8 + 56);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 56));
  v11 = *(_QWORD *)(v8 + 40);
  KeReleaseSpinLockFromDpcLevel(v10);
  if ( !v11 )
  {
    v6 = -1073741772;
    goto LABEL_10;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 128));
  KeAcquireSpinLockAtDpcLevel(*(PKSPIN_LOCK *)(v11 + 80));
  v13 = *(KSPIN_LOCK **)(v11 + 80);
  *(_DWORD *)(v11 + 124) = 0;
  KeReleaseSpinLockFromDpcLevel(v13);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 120));
  if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
    KeReleaseSpinLock(&SpinLock, a2);
  else
    KeLowerIrql(a2);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 96), 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry((char *)v11);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 96), 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry((char *)v11);
  return v6;
}

```

## disassembly

```asm
0x14000f250  push    rbx
0x14000f252  push    rbp
0x14000f253  push    rsi
0x14000f254  push    rdi
0x14000f255  push    r14
0x14000f257  push    r15
0x14000f259  sub     rsp, 28h
0x14000f25d  cmp     byte ptr [rcx+94h], 6
0x14000f264  mov     r15b, r8b
0x14000f267  mov     r14b, dl
0x14000f26a  mov     rbp, rcx
0x14000f26d  jz      short loc_14000F273
0x14000f26f  xor     edi, edi
0x14000f271  jmp     short loc_14000F2EC
0x14000f273  mov     al, r15b
0x14000f276  neg     al
0x14000f278  sbb     rcx, rcx
0x14000f27b  xor     edi, edi
0x14000f27d  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14000f281  mov     rsi, [rcx+rbp+0B0h]
0x14000f289  test    rsi, rsi
0x14000f28c  jz      short loc_14000F2EC
0x14000f28e  cmp     cs:g_bEnableLinkDownAtStop, edi
0x14000f294  lea     rbx, [rsi+0A4h]
0x14000f29b  jz      short loc_14000F2A7
0x14000f29d  mov     edx, [rbx]
0x14000f29f  mov     cl, r15b
0x14000f2a2  call    WanpRemoveConnections
0x14000f2a7  mov     edx, [rbx]
0x14000f2a9  mov     cl, r15b
0x14000f2ac  call    WanpIsConnectionTableEmpty
0x14000f2b1  test    al, al
0x14000f2b3  jnz     short loc_14000F2BC
0x14000f2b5  mov     edi, 0C0000101h
0x14000f2ba  jmp     short loc_14000F2EC
0x14000f2bc  lea     rbx, [rsi+38h]
0x14000f2c0  mov     rcx, rbx; SpinLock
0x14000f2c3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000f2ca  nop     dword ptr [rax+rax+00h]
0x14000f2cf  mov     rsi, [rsi+28h]
0x14000f2d3  mov     rcx, rbx; SpinLock
0x14000f2d6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000f2dd  nop     dword ptr [rax+rax+00h]
0x14000f2e2  test    rsi, rsi
0x14000f2e5  jnz     short loc_14000F34D
0x14000f2e7  mov     edi, 0C0000034h
0x14000f2ec  lea     rcx, [rbp+78h]; SpinLock
0x14000f2f0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000f2f7  nop     dword ptr [rax+rax+00h]
0x14000f2fc  or      ebx, 0FFFFFFFFh
0x14000f2ff  mov     eax, ebx
0x14000f301  lock xadd cs:dword_140009CB0, eax
0x14000f309  add     eax, ebx
0x14000f30b  jnz     short loc_14000F325
0x14000f30d  mov     dl, r14b; NewIrql
0x14000f310  lea     rcx, SpinLock; SpinLock
0x14000f317  call    cs:__imp_KeReleaseSpinLock
0x14000f31e  nop     dword ptr [rax+rax+00h]
0x14000f323  jmp     short loc_14000F334
0x14000f325  mov     cl, r14b; NewIrql
0x14000f328  call    cs:__imp_KeLowerIrql
0x14000f32f  nop     dword ptr [rax+rax+00h]
0x14000f334  mov     cl, r15b
0x14000f337  call    WanpSetCloseEventIfRequired
0x14000f33c  lea     rcx, g_wrBindMutex
0x14000f343  call    WanpReleaseResource
0x14000f348  jmp     loc_14000F3E5
0x14000f34d  lock inc dword ptr [rbp+80h]
0x14000f354  mov     rcx, [rsi+50h]; SpinLock
0x14000f358  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000f35f  nop     dword ptr [rax+rax+00h]
0x14000f364  mov     rcx, [rsi+50h]; SpinLock
0x14000f368  mov     [rsi+7Ch], edi
0x14000f36b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000f372  nop     dword ptr [rax+rax+00h]
0x14000f377  lea     rcx, [rbp+78h]; SpinLock
0x14000f37b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000f382  nop     dword ptr [rax+rax+00h]
0x14000f387  or      ebx, 0FFFFFFFFh
0x14000f38a  mov     eax, ebx
0x14000f38c  lock xadd cs:dword_140009CB0, eax
0x14000f394  add     eax, ebx
0x14000f396  jnz     short loc_14000F3B0
0x14000f398  mov     dl, r14b; NewIrql
0x14000f39b  lea     rcx, SpinLock; SpinLock
0x14000f3a2  call    cs:__imp_KeReleaseSpinLock
0x14000f3a9  nop     dword ptr [rax+rax+00h]
0x14000f3ae  jmp     short loc_14000F3BF
0x14000f3b0  mov     cl, r14b; NewIrql
0x14000f3b3  call    cs:__imp_KeLowerIrql
0x14000f3ba  nop     dword ptr [rax+rax+00h]
0x14000f3bf  mov     eax, ebx
0x14000f3c1  lock xadd [rsi+60h], eax
0x14000f3c6  add     eax, ebx
0x14000f3c8  jnz     short loc_14000F3D2
0x14000f3ca  mov     rcx, rsi; Entry
0x14000f3cd  call    WanpDeleteConnEntry
0x14000f3d2  mov     edx, ebx
0x14000f3d4  lock xadd [rsi+60h], edx
0x14000f3d9  add     edx, ebx
0x14000f3db  jnz     short loc_14000F3E5
0x14000f3dd  mov     rcx, rsi; Entry
0x14000f3e0  call    WanpDeleteConnEntry
0x14000f3e5  mov     eax, edi
0x14000f3e7  add     rsp, 28h
0x14000f3eb  pop     r15
0x14000f3ed  pop     r14
0x14000f3ef  pop     rdi
0x14000f3f0  pop     rsi
0x14000f3f1  pop     rbp
0x14000f3f2  pop     rbx
0x14000f3f3  retn
```
