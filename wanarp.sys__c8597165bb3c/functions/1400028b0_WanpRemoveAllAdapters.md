# WanpRemoveAllAdapters

- ea: `0x1400028b0`
- end: `0x140002ab8`
- name: `WanpRemoveAllAdapters`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140019b00`

## callees

- `0x1400024d0`
- `0x140002510`
- `0x1400028b0`
- `0x140002ac0`
- `0x140002b6c`
- `0x14000f250`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002976`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002976`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002908`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400029b3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002908`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400029b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400028f0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002946`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400029a0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400028f0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002946`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400029a0`
- `ntoskrnl!KeLowerIrql` at `0x140002a1b`
- `ntoskrnl!KeLowerIrql` at `0x140002a71`
- `ntoskrnl!KeLowerIrql` at `0x140002a1b`
- `ntoskrnl!KeLowerIrql` at `0x140002a71`
- `ntoskrnl!KeSetEvent` at `0x140002a9f`
- `ntoskrnl!KeSetEvent` at `0x140002a9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a5f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a5f`

## pseudocode

```c
LONG __fastcall WanpRemoveAllAdapters(unsigned __int8 a1)
{
  KIRQL v2; // si
  __int64 i; // r14
  LONG result; // eax

  WanpRemoveAllAdaptersFromIp(a1);
  v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
  KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
  if ( g_ulNumDialInAdapters )
  {
    for ( i = g_leDialInAdapterList; (__int64 *)i != &g_leDialInAdapterList; i = *(_QWORD *)i )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(i + 88));
      WanpUnmapServerInterface(i - 32, v2, a1);
      WanpAcquireResource(&g_wrBindMutex);
      v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
      if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
        KeAcquireSpinLockAtDpcLevel(&SpinLock);
      KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
    }
    if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      KeReleaseSpinLock(&SpinLock, v2);
    else
      KeLowerIrql(v2);
    return WanpReleaseResource(&g_wrBindMutex);
  }
  else
  {
    if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      KeReleaseSpinLock(&SpinLock, v2);
    else
      KeLowerIrql(v2);
    result = WanpSetCloseEventIfRequired(a1);
    if ( _InterlockedExchangeAdd(&g_wrBindMutex, 0xFFFFFFFF) != 1 )
      return KeSetEvent(&Event, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400028b0  push    rsi
0x1400028b2  push    rdi
0x1400028b3  sub     rsp, 28h
0x1400028b7  movzx   edi, cl
0x1400028ba  call    WanpRemoveAllAdaptersFromIp
0x1400028bf  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400028c6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400028cd  nop     dword ptr [rax+rax+00h]
0x1400028d2  movzx   esi, al
0x1400028d5  mov     edx, 1
0x1400028da  lock xadd cs:dword_140009CB0, edx
0x1400028e2  inc     edx
0x1400028e4  cmp     edx, 1
0x1400028e7  jnz     short loc_1400028FC
0x1400028e9  lea     rcx, SpinLock; SpinLock
0x1400028f0  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400028f7  nop     dword ptr [rax+rax+00h]
0x1400028fc  lea     rcx, g_rwlAdapterLock; SpinLock
0x140002903  mov     [rsp+38h+arg_0], rbx
0x140002908  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000290f  nop     dword ptr [rax+rax+00h]
0x140002914  cmp     cs:g_ulNumDialInAdapters, 0
0x14000291b  jz      loc_140002A40
0x140002921  mov     [rsp+38h+arg_10], rbp
0x140002926  lea     rbp, g_leDialInAdapterList
0x14000292d  mov     [rsp+38h+var_18], r14
0x140002932  mov     r14, cs:g_leDialInAdapterList
0x140002939  cmp     r14, rbp
0x14000293c  jz      loc_1400029CB
0x140002942  lea     rcx, [r14+58h]; SpinLock
0x140002946  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000294d  nop     dword ptr [rax+rax+00h]
0x140002952  movzx   r8d, dil
0x140002956  lea     rcx, [r14-20h]
0x14000295a  movzx   edx, sil
0x14000295e  call    WanpUnmapServerInterface
0x140002963  lea     rcx, g_wrBindMutex
0x14000296a  call    WanpAcquireResource
0x14000296f  lea     rcx, g_rwlAdapterLock; SpinLock
0x140002976  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000297d  nop     dword ptr [rax+rax+00h]
0x140002982  movzx   esi, al
0x140002985  mov     eax, 1
0x14000298a  lock xadd cs:dword_140009CB0, eax
0x140002992  inc     eax
0x140002994  cmp     eax, 1
0x140002997  jnz     short loc_1400029AC
0x140002999  lea     rcx, SpinLock; SpinLock
0x1400029a0  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400029a7  nop     dword ptr [rax+rax+00h]
0x1400029ac  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400029b3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400029ba  nop     dword ptr [rax+rax+00h]
0x1400029bf  mov     r14, [r14]
0x1400029c2  cmp     r14, rbp
0x1400029c5  jnz     loc_140002942
0x1400029cb  mov     ebx, 0FFFFFFFFh
0x1400029d0  lock xadd cs:dword_140009CB0, ebx
0x1400029d8  mov     r14, [rsp+38h+var_18]
0x1400029dd  mov     rbp, [rsp+38h+arg_10]
0x1400029e2  cmp     ebx, 1
0x1400029e5  jnz     short loc_140002A17
0x1400029e7  movzx   edx, sil; NewIrql
0x1400029eb  lea     rcx, SpinLock; SpinLock
0x1400029f2  call    cs:__imp_KeReleaseSpinLock
0x1400029f9  nop     dword ptr [rax+rax+00h]
0x1400029fe  lea     rcx, g_wrBindMutex
0x140002a05  call    WanpReleaseResource
0x140002a0a  mov     rbx, [rsp+38h+arg_0]
0x140002a0f  add     rsp, 28h
0x140002a13  pop     rdi
0x140002a14  pop     rsi
0x140002a15  retn
0x140002a17  movzx   ecx, sil; NewIrql
0x140002a1b  call    cs:__imp_KeLowerIrql
0x140002a22  nop     dword ptr [rax+rax+00h]
0x140002a27  lea     rcx, g_wrBindMutex
0x140002a2e  call    WanpReleaseResource
0x140002a33  mov     rbx, [rsp+38h+arg_0]
0x140002a38  add     rsp, 28h
0x140002a3c  pop     rdi
0x140002a3d  pop     rsi
0x140002a3e  retn
0x140002a40  mov     ebx, 0FFFFFFFFh
0x140002a45  mov     eax, ebx
0x140002a47  lock xadd cs:dword_140009CB0, eax
0x140002a4f  cmp     eax, 1
0x140002a52  jnz     short loc_140002A6D
0x140002a54  movzx   edx, sil; NewIrql
0x140002a58  lea     rcx, SpinLock; SpinLock
0x140002a5f  call    cs:__imp_KeReleaseSpinLock
0x140002a66  nop     dword ptr [rax+rax+00h]
0x140002a6b  jmp     short loc_140002A7D
0x140002a6d  movzx   ecx, sil; NewIrql
0x140002a71  call    cs:__imp_KeLowerIrql
0x140002a78  nop     dword ptr [rax+rax+00h]
0x140002a7d  movzx   ecx, dil
0x140002a81  call    WanpSetCloseEventIfRequired
0x140002a86  lock xadd cs:g_wrBindMutex, ebx
0x140002a8e  cmp     ebx, 1
0x140002a91  jz      short loc_140002AAB
0x140002a93  xor     r8d, r8d; Wait
0x140002a96  lea     rcx, Event; Event
0x140002a9d  xor     edx, edx; Increment
0x140002a9f  call    cs:__imp_KeSetEvent
0x140002aa6  nop     dword ptr [rax+rax+00h]
0x140002aab  mov     rbx, [rsp+38h+arg_0]
0x140002ab0  add     rsp, 28h
0x140002ab4  pop     rdi
0x140002ab5  pop     rsi
0x140002ab6  retn
```
