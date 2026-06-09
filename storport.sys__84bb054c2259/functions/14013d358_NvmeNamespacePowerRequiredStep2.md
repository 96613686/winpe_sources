# NvmeNamespacePowerRequiredStep2

- ea: `0x14013d358`
- end: `0x14013d560`
- name: `NvmeNamespacePowerRequiredStep2`
- size: `520`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14013d2e0`

## callees

- `0x140033454`
- `0x14003348c`
- `0x14013d358`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14013d4f5`
- `ntoskrnl!PoFxIdleComponent` at `0x14013d520`
- `ntoskrnl!PoFxIdleComponent` at `0x14013d4f5`
- `ntoskrnl!PoFxIdleComponent` at `0x14013d520`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14013d54a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14013d54a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d3a2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013d3a2`
- `ntoskrnl!PoFxActivateComponent` at `0x14013d40d`
- `ntoskrnl!PoFxActivateComponent` at `0x14013d40d`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14013d53a`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14013d53a`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d462`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013d462`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d3cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d42f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d47a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d49a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d3cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d42f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d47a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013d49a`

## pseudocode

```c
void __fastcall NvmeNamespacePowerRequiredStep2(PVOID Context)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rsi
  char v5; // bp
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  v2 = *((_QWORD *)Context + 2);
  v3 = *((_QWORD *)Context + 16);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = *(_QWORD *)(v2 + 128);
  v5 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL) + 12LL) & 1;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 88), &LockHandle);
  v6 = *((_QWORD *)Context + 16);
  if ( (*(_DWORD *)(*(_QWORD *)(v6 + 8) + 32LL) & 2) != 0 && v5 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( **(_BYTE **)(v4 + 168) == 1
      && !_InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)Context + 16) + 96LL), 1, 0) )
    {
      PoFxActivateComponent(**(_QWORD **)(*(_QWORD *)(v4 + 168) + 8LL), 0, 0);
    }
  }
  else if ( *(_DWORD *)(v6 + 72) != 1 || (*(_DWORD *)(v6 + 80) & 4) != 0 )
  {
    *(_DWORD *)(v6 + 80) |= 2u;
    if ( PoRequestPowerIrp(
           *((PDEVICE_OBJECT *)Context + 1),
           2u,
           (POWER_STATE)1,
           NvmeNamespaceDeviceStackPowerUpCompletion,
           Context,
           0) == 259 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      _InterlockedExchange((volatile __int32 *)(*((_QWORD *)Context + 16) + 180LL), 0);
      return;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    ++*(_DWORD *)(*((_QWORD *)Context + 16) + 168LL);
    if ( _InterlockedCompareExchange(
           (volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)Context + 16) + 8LL) + 36LL),
           0,
           1) )
    {
      v7 = *(_QWORD *)(*((_QWORD *)Context + 2) + 128LL);
      if ( (unsigned __int8)NvmeNamespaceCheckAndAcquirePoFx(Context) )
      {
        PoFxIdleComponent(**(_QWORD **)(*((_QWORD *)Context + 16) + 8LL), 0, 0);
        NvmeNamespaceReleasePoFx(Context);
      }
      v8 = *(_QWORD *)(v7 + 168);
      if ( *(_BYTE *)v8 == 1 )
        PoFxIdleComponent(**(_QWORD **)(v8 + 8), 0, 0);
    }
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  PoFxReportDevicePoweredOn(**(_QWORD **)(*((_QWORD *)Context + 16) + 8LL));
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 15));
}

```

## disassembly

```asm
0x14013d358  push    rbx
0x14013d35a  push    rbp
0x14013d35b  push    rsi
0x14013d35c  push    rdi
0x14013d35d  sub     rsp, 58h
0x14013d361  xor     eax, eax
0x14013d363  mov     rdi, rcx
0x14013d366  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14013d36b  xorps   xmm0, xmm0
0x14013d36e  mov     rax, [rcx+10h]
0x14013d372  mov     ebx, 1
0x14013d377  mov     rcx, [rcx+80h]
0x14013d37e  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14013d383  mov     rsi, [rax+80h]
0x14013d38a  mov     rax, [rcx+8]
0x14013d38e  add     rcx, 58h ; 'X'; SpinLock
0x14013d392  mov     rdx, [rax+8]
0x14013d396  mov     bpl, [rdx+0Ch]
0x14013d39a  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14013d39f  and     bpl, bl
0x14013d3a2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14013d3a9  nop     dword ptr [rax+rax+00h]
0x14013d3ae  mov     rdx, [rdi+80h]
0x14013d3b5  mov     rax, [rdx+8]
0x14013d3b9  mov     ecx, [rax+20h]
0x14013d3bc  test    cl, 2
0x14013d3bf  jz      short loc_14013D41E
0x14013d3c1  test    bpl, bpl
0x14013d3c4  jz      short loc_14013D41E
0x14013d3c6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14013d3cb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d3d2  nop     dword ptr [rax+rax+00h]
0x14013d3d7  mov     rax, [rsi+0A8h]
0x14013d3de  cmp     [rax], bl
0x14013d3e0  jnz     loc_14013D52C
0x14013d3e6  mov     rcx, [rdi+80h]
0x14013d3ed  xor     eax, eax
0x14013d3ef  lock cmpxchg [rcx+60h], ebx
0x14013d3f4  jnz     loc_14013D52C
0x14013d3fa  mov     rax, [rsi+0A8h]
0x14013d401  xor     r8d, r8d
0x14013d404  xor     edx, edx
0x14013d406  mov     rcx, [rax+8]
0x14013d40a  mov     rcx, [rcx]
0x14013d40d  call    cs:__imp_PoFxActivateComponent
0x14013d414  nop     dword ptr [rax+rax+00h]
0x14013d419  jmp     loc_14013D52C
0x14013d41e  cmp     [rdx+48h], ebx
0x14013d421  jnz     short loc_14013D440
0x14013d423  mov     eax, [rdx+50h]
0x14013d426  test    al, 4
0x14013d428  jnz     short loc_14013D440
0x14013d42a  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14013d42f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d436  nop     dword ptr [rax+rax+00h]
0x14013d43b  jmp     loc_14013D52C
0x14013d440  or      dword ptr [rdx+50h], 2
0x14013d444  lea     r9, NvmeNamespaceDeviceStackPowerUpCompletion; CompletionFunction
0x14013d44b  mov     rcx, [rdi+8]; DeviceObject
0x14013d44f  mov     dl, 2; MinorFunction
0x14013d451  mov     [rsp+78h+Irp], 0; Irp
0x14013d45a  mov     r8d, ebx; PowerState
0x14013d45d  mov     [rsp+78h+Context], rdi; Context
0x14013d462  call    cs:__imp_PoRequestPowerIrp
0x14013d469  nop     dword ptr [rax+rax+00h]
0x14013d46e  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14013d473  cmp     eax, 103h
0x14013d478  jnz     short loc_14013D49A
0x14013d47a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d481  nop     dword ptr [rax+rax+00h]
0x14013d486  mov     rcx, [rdi+80h]
0x14013d48d  xor     eax, eax
0x14013d48f  xchg    eax, [rcx+0B4h]
0x14013d495  jmp     loc_14013D556
0x14013d49a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14013d4a1  nop     dword ptr [rax+rax+00h]
0x14013d4a6  mov     rax, [rdi+80h]
0x14013d4ad  add     [rax+0A8h], ebx
0x14013d4b3  mov     rax, [rdi+80h]
0x14013d4ba  xor     ecx, ecx
0x14013d4bc  mov     rdx, [rax+8]
0x14013d4c0  mov     eax, ebx
0x14013d4c2  lock cmpxchg [rdx+24h], ecx
0x14013d4c7  test    eax, eax
0x14013d4c9  jz      short loc_14013D52C
0x14013d4cb  mov     rax, [rdi+10h]
0x14013d4cf  mov     rcx, rdi
0x14013d4d2  mov     rsi, [rax+80h]
0x14013d4d9  call    NvmeNamespaceCheckAndAcquirePoFx
0x14013d4de  test    al, al
0x14013d4e0  jz      short loc_14013D509
0x14013d4e2  mov     rax, [rdi+80h]
0x14013d4e9  xor     r8d, r8d
0x14013d4ec  xor     edx, edx
0x14013d4ee  mov     rcx, [rax+8]
0x14013d4f2  mov     rcx, [rcx]
0x14013d4f5  call    cs:__imp_PoFxIdleComponent
0x14013d4fc  nop     dword ptr [rax+rax+00h]
0x14013d501  mov     rcx, rdi
0x14013d504  call    NvmeNamespaceReleasePoFx
0x14013d509  mov     rcx, [rsi+0A8h]
0x14013d510  cmp     [rcx], bl
0x14013d512  jnz     short loc_14013D52C
0x14013d514  mov     rcx, [rcx+8]
0x14013d518  xor     r8d, r8d
0x14013d51b  xor     edx, edx
0x14013d51d  mov     rcx, [rcx]
0x14013d520  call    cs:__imp_PoFxIdleComponent
0x14013d527  nop     dword ptr [rax+rax+00h]
0x14013d52c  mov     rax, [rdi+80h]
0x14013d533  mov     rcx, [rax+8]
0x14013d537  mov     rcx, [rcx]
0x14013d53a  call    cs:__imp_PoFxReportDevicePoweredOn
0x14013d541  nop     dword ptr [rax+rax+00h]
0x14013d546  mov     rcx, [rdi+78h]; RunRefCacheAware
0x14013d54a  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14013d551  nop     dword ptr [rax+rax+00h]
0x14013d556  add     rsp, 58h
0x14013d55a  pop     rdi
0x14013d55b  pop     rsi
0x14013d55c  pop     rbp
0x14013d55d  pop     rbx
0x14013d55e  retn
```
