# WanpIpDeleteSpecialSubInterfaceComplete

- ea: `0x14000e6f8`
- end: `0x14000e893`
- name: `WanpIpDeleteSpecialSubInterfaceComplete`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140015f60`

## callees

- `0x1400024d0`
- `0x140002ac0`
- `0x14000e280`
- `0x14000e310`
- `0x14000e6f8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e719`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e719`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e82f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e82f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000e756`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000e756`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e743`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e743`
- `ntoskrnl!KeLowerIrql` at `0x14000e791`
- `ntoskrnl!KeLowerIrql` at `0x14000e791`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e780`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e842`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e780`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e842`

## pseudocode

```c
__int64 __fastcall WanpIpDeleteSpecialSubInterfaceComplete(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbx
  KIRQL v4; // si
  unsigned int v5; // esi
  KIRQL v6; // al
  char v7; // bp
  KIRQL v8; // r15
  __int64 v9; // rcx

  v1 = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 8);
  v4 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
  KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
  if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
    KeReleaseSpinLock(&SpinLock, v4);
  else
    KeLowerIrql(v4);
  if ( !v1 || !v3 )
    return 3221225860LL;
  v5 = WanpDeleteInterfaceFromIp((char *)v1);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 120));
  v7 = *(_BYTE *)(a1 + 4);
  v8 = v6;
  if ( !*(_QWORD *)((v7 != 0 ? 8 : 0) + v3 + 168) )
    *(_BYTE *)(v3 + 148) = 3;
  *(_QWORD *)(v1 + 24) = 0;
  *(_QWORD *)(v1 + 88) = 0;
  *(_QWORD *)(v1 + 40) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) == 1 )
    WanpDeleteAdapter((PVOID)v3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 64), 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)v1, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 120), v8);
  LOBYTE(v9) = v7;
  WanpSetCloseEventIfRequired(v9);
  WanpReleaseResource(&g_wrBindMutex);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) == 1 )
    WanpDeleteAdapter((PVOID)v3);
  return v5;
}

```

## disassembly

```asm
0x14000e6f8  push    rbx
0x14000e6fa  push    rbp
0x14000e6fb  push    rsi
0x14000e6fc  push    rdi
0x14000e6fd  push    r12
0x14000e6ff  push    r14
0x14000e701  push    r15
0x14000e703  sub     rsp, 20h
0x14000e707  mov     rdi, [rcx+10h]
0x14000e70b  mov     rbp, rcx
0x14000e70e  mov     rbx, [rcx+8]
0x14000e712  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000e719  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e720  nop     dword ptr [rax+rax+00h]
0x14000e725  mov     sil, al
0x14000e728  mov     edx, 1
0x14000e72d  lock xadd cs:dword_140009CB0, edx
0x14000e735  inc     edx
0x14000e737  cmp     edx, 1
0x14000e73a  jnz     short loc_14000E74F
0x14000e73c  lea     rcx, SpinLock; SpinLock
0x14000e743  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000e74a  nop     dword ptr [rax+rax+00h]
0x14000e74f  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000e756  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000e75d  nop     dword ptr [rax+rax+00h]
0x14000e762  or      r12d, 0FFFFFFFFh
0x14000e766  mov     eax, r12d
0x14000e769  lock xadd cs:dword_140009CB0, eax
0x14000e771  add     eax, r12d
0x14000e774  jnz     short loc_14000E78E
0x14000e776  mov     dl, sil; NewIrql
0x14000e779  lea     rcx, SpinLock; SpinLock
0x14000e780  call    cs:__imp_KeReleaseSpinLock
0x14000e787  nop     dword ptr [rax+rax+00h]
0x14000e78c  jmp     short loc_14000E79D
0x14000e78e  mov     cl, sil; NewIrql
0x14000e791  call    cs:__imp_KeLowerIrql
0x14000e798  nop     dword ptr [rax+rax+00h]
0x14000e79d  test    rdi, rdi
0x14000e7a0  jz      loc_14000E87E
0x14000e7a6  test    rbx, rbx
0x14000e7a9  jz      loc_14000E87E
0x14000e7af  mov     rcx, rdi; P
0x14000e7b2  call    WanpDeleteInterfaceFromIp
0x14000e7b7  lea     rcx, [rbx+78h]; SpinLock
0x14000e7bb  mov     esi, eax
0x14000e7bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e7c4  nop     dword ptr [rax+rax+00h]
0x14000e7c9  mov     bpl, [rbp+4]
0x14000e7cd  mov     r15b, al
0x14000e7d0  mov     cl, bpl
0x14000e7d3  neg     cl
0x14000e7d5  sbb     rdx, rdx
0x14000e7d8  and     edx, 8
0x14000e7db  cmp     qword ptr [rdx+rbx+0A8h], 0
0x14000e7e4  jnz     short loc_14000E7ED
0x14000e7e6  mov     byte ptr [rbx+94h], 3
0x14000e7ed  mov     qword ptr [rdi+18h], 0
0x14000e7f5  mov     eax, r12d
0x14000e7f8  mov     qword ptr [rdi+58h], 0
0x14000e800  mov     qword ptr [rdi+28h], 0
0x14000e808  lock xadd [rbx+80h], eax
0x14000e810  add     eax, r12d
0x14000e813  jnz     short loc_14000E81D
0x14000e815  mov     rcx, rbx; P
0x14000e818  call    WanpDeleteAdapter
0x14000e81d  mov     eax, r12d
0x14000e820  lock xadd [rdi+40h], eax
0x14000e825  add     eax, r12d
0x14000e828  jnz     short loc_14000E83B
0x14000e82a  xor     edx, edx; Tag
0x14000e82c  mov     rcx, rdi; P
0x14000e82f  call    cs:__imp_ExFreePoolWithTag
0x14000e836  nop     dword ptr [rax+rax+00h]
0x14000e83b  mov     dl, r15b; NewIrql
0x14000e83e  lea     rcx, [rbx+78h]; SpinLock
0x14000e842  call    cs:__imp_KeReleaseSpinLock
0x14000e849  nop     dword ptr [rax+rax+00h]
0x14000e84e  mov     cl, bpl
0x14000e851  call    WanpSetCloseEventIfRequired
0x14000e856  lea     rcx, g_wrBindMutex
0x14000e85d  call    WanpReleaseResource
0x14000e862  mov     eax, r12d
0x14000e865  lock xadd [rbx+80h], eax
0x14000e86d  add     eax, r12d
0x14000e870  jnz     short loc_14000E87A
0x14000e872  mov     rcx, rbx; P
0x14000e875  call    WanpDeleteAdapter
0x14000e87a  mov     eax, esi
0x14000e87c  jmp     short loc_14000E883
0x14000e87e  mov     eax, 0C0000184h
0x14000e883  add     rsp, 20h
0x14000e887  pop     r15
0x14000e889  pop     r14
0x14000e88b  pop     r12
0x14000e88d  pop     rdi
0x14000e88e  pop     rsi
0x14000e88f  pop     rbp
0x14000e890  pop     rbx
0x14000e891  retn
```
