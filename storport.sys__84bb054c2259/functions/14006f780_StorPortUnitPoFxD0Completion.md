# StorPortUnitPoFxD0Completion

- ea: `0x14006f780`
- end: `0x14006f910`
- name: `StorPortUnitPoFxD0Completion`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000528c`

## callees

- `0x1400016cc`
- `0x140005c50`
- `0x14004912c`
- `0x140066a60`
- `0x14006f780`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14006f7e0`
- `ntoskrnl!PoFxIdleComponent` at `0x14006f7e0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006f7f3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006f8d6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006f7f3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006f8d6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006f81f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006f81f`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14006f858`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14006f858`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006f838`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006f838`

## pseudocode

```c
void __fastcall StorPortUnitPoFxD0Completion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  __int64 v6; // r9
  int v7; // r8d
  __int64 *v8; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !(unsigned __int8)RaidUnitCheckAndAcquirePoFx(a4) )
    goto LABEL_17;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(a4 + 1872) + 36LL), 0, 1) )
  {
    v5 = *(_QWORD *)(a4 + 24);
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a4) )
    {
      PoFxIdleComponent(**(_QWORD **)(a4 + 1872), 0, 0);
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a4 + 1864));
    }
    if ( *(_QWORD *)(v5 + 5024) )
      RaidAdapterPoFxIdleComponent(v5, 0, 0, v6);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a4 + 48), &LockHandle);
  RaidUnitCancelWaitWakeIrp(a4);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (*(_DWORD *)(a4 + 512) & 0x20) == 0 )
    PoFxReportDevicePoweredOn(**(_QWORD **)(a4 + 1872));
  if ( StorEtwLoggingEnabled )
  {
    if ( (*(_BYTE *)(a4 + 507) & 2) != 0 )
    {
      if ( (byte_140177432 & 0x10) != 0 )
      {
        v8 = EventUnitDirectedPowerUpStop;
LABEL_15:
        McTemplateK0pquuuq_EtwWriteTransfer(
          *(_QWORD *)(a4 + 24),
          (_DWORD)v8,
          v7,
          **(_QWORD **)(a4 + 1872),
          *(_DWORD *)(*(_QWORD *)(a4 + 24) + 56LL),
          *(_BYTE *)(a4 + 104),
          *(_BYTE *)(a4 + 105),
          *(_BYTE *)(a4 + 106),
          1);
      }
    }
    else if ( (byte_140177432 & 0x10) != 0 )
    {
      v8 = EventUnitPowerRequiredStop;
      goto LABEL_15;
    }
  }
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a4 + 1864));
LABEL_17:
  if ( *(_DWORD *)(a4 + 3432) == 7 )
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a4 + 24) + 1024LL) + 48LL)
                                                    + 1060LL));
}

```

## disassembly

```asm
0x14006f780  mov     [rsp+arg_0], rbx
0x14006f785  push    rdi
0x14006f786  sub     rsp, 70h
0x14006f78a  xorps   xmm0, xmm0
0x14006f78d  xor     eax, eax
0x14006f78f  mov     rcx, r9
0x14006f792  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14006f797  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14006f79c  mov     rbx, r9
0x14006f79f  call    RaidUnitCheckAndAcquirePoFx
0x14006f7a4  test    al, al
0x14006f7a6  jz      loc_14006F8E2
0x14006f7ac  mov     rdx, [rbx+750h]
0x14006f7b3  xor     ecx, ecx
0x14006f7b5  lea     eax, [rcx+1]
0x14006f7b8  lock cmpxchg [rdx+24h], ecx
0x14006f7bd  test    eax, eax
0x14006f7bf  jz      short loc_14006F816
0x14006f7c1  mov     rdi, [rbx+18h]
0x14006f7c5  mov     rcx, rbx
0x14006f7c8  call    RaidUnitCheckAndAcquirePoFx
0x14006f7cd  test    al, al
0x14006f7cf  jz      short loc_14006F7FF
0x14006f7d1  mov     rcx, [rbx+750h]
0x14006f7d8  xor     r8d, r8d
0x14006f7db  xor     edx, edx
0x14006f7dd  mov     rcx, [rcx]
0x14006f7e0  call    cs:__imp_PoFxIdleComponent
0x14006f7e7  nop     dword ptr [rax+rax+00h]
0x14006f7ec  mov     rcx, [rbx+748h]; RunRefCacheAware
0x14006f7f3  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14006f7fa  nop     dword ptr [rax+rax+00h]
0x14006f7ff  cmp     qword ptr [rdi+13A0h], 0
0x14006f807  jz      short loc_14006F816
0x14006f809  xor     r8d, r8d
0x14006f80c  xor     edx, edx
0x14006f80e  mov     rcx, rdi
0x14006f811  call    RaidAdapterPoFxIdleComponent
0x14006f816  lea     rcx, [rbx+30h]; SpinLock
0x14006f81a  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14006f81f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006f826  nop     dword ptr [rax+rax+00h]
0x14006f82b  mov     rcx, rbx
0x14006f82e  call    RaidUnitCancelWaitWakeIrp
0x14006f833  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14006f838  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006f83f  nop     dword ptr [rax+rax+00h]
0x14006f844  mov     eax, [rbx+200h]
0x14006f84a  test    al, 20h
0x14006f84c  jnz     short loc_14006F864
0x14006f84e  mov     rcx, [rbx+750h]
0x14006f855  mov     rcx, [rcx]
0x14006f858  call    cs:__imp_PoFxReportDevicePoweredOn
0x14006f85f  nop     dword ptr [rax+rax+00h]
0x14006f864  cmp     cs:StorEtwLoggingEnabled, 0
0x14006f86b  jz      short loc_14006F8CF
0x14006f86d  test    byte ptr [rbx+1FBh], 2
0x14006f874  jz      short loc_14006F888
0x14006f876  test    cs:byte_140177432, 10h
0x14006f87d  jz      short loc_14006F8CF
0x14006f87f  lea     rdx, EventUnitDirectedPowerUpStop
0x14006f886  jmp     short loc_14006F898
0x14006f888  test    cs:byte_140177432, 10h
0x14006f88f  jz      short loc_14006F8CF
0x14006f891  lea     rdx, EventUnitPowerRequiredStop
0x14006f898  mov     al, [rbx+6Ah]
0x14006f89b  mov     rcx, [rbx+18h]
0x14006f89f  mov     r9, [rbx+750h]
0x14006f8a6  mov     [rsp+78h+var_38], 1
0x14006f8ae  mov     [rsp+78h+var_40], al
0x14006f8b2  mov     al, [rbx+69h]
0x14006f8b5  mov     r9, [r9]
0x14006f8b8  mov     [rsp+78h+var_48], al
0x14006f8bc  mov     al, [rbx+68h]
0x14006f8bf  mov     [rsp+78h+var_50], al
0x14006f8c3  mov     eax, [rcx+38h]
0x14006f8c6  mov     [rsp+78h+var_58], eax
0x14006f8ca  call    McTemplateK0pquuuq_EtwWriteTransfer
0x14006f8cf  mov     rcx, [rbx+748h]; RunRefCacheAware
0x14006f8d6  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14006f8dd  nop     dword ptr [rax+rax+00h]
0x14006f8e2  cmp     dword ptr [rbx+0D68h], 7
0x14006f8e9  jnz     short loc_14006F901
0x14006f8eb  mov     rax, [rbx+18h]
0x14006f8ef  mov     rcx, [rax+400h]
0x14006f8f6  mov     rax, [rcx+30h]
0x14006f8fa  lock dec dword ptr [rax+424h]
0x14006f901  mov     rbx, [rsp+78h+arg_0]
0x14006f909  add     rsp, 70h
0x14006f90d  pop     rdi
0x14006f90e  retn
```
