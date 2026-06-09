# StorPortUnitPowerRequiredStep2

- ea: `0x1400039c4`
- end: `0x140003b75`
- name: `StorPortUnitPowerRequiredStep2`
- size: `433`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003c60`

## callees

- `0x1400016cc`
- `0x1400039c4`
- `0x140003df0`
- `0x140005c50`
- `0x140066a60`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140003ae9`
- `ntoskrnl!PoFxIdleComponent` at `0x140003ae9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003afc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003afc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400039e9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400039e9`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14014bff0`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14014bff0`
- `ntoskrnl!PoRequestPowerIrp` at `0x140003a3d`
- `ntoskrnl!PoRequestPowerIrp` at `0x140003a3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a60`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a88`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b4c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a60`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003a88`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b4c`

## pseudocode

```c
__int64 __fastcall StorPortUnitPowerRequiredStep2(PVOID Context)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // rbx
  __int64 v5; // r9
  int v6; // r8d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)Context + 6, &LockHandle);
  v2 = *((_QWORD *)Context + 234);
  if ( (*(_DWORD *)(v2 + 32) & 4) != 0 && (*(_DWORD *)(*(_QWORD *)(v2 + 8) + 12LL) & 1) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( *(_QWORD *)(*((_QWORD *)Context + 3) + 5024LL)
      && !_InterlockedCompareExchange((volatile signed __int32 *)Context + 904, 1, 0) )
    {
      RaidAdapterPoFxActivateComponent(*((_QWORD *)Context + 3), 0, 0);
    }
  }
  else if ( *((_DWORD *)Context + 137) != 1 || (*((_BYTE *)Context + 505) & 1) != 0 )
  {
    if ( PoRequestPowerIrp(
           *((PDEVICE_OBJECT *)Context + 1),
           2u,
           (POWER_STATE)1,
           RaidUnitDeviceStackPowerUpCompletion,
           Context,
           0) == 259 )
    {
      *((_BYTE *)Context + 504) |= 0x80u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return (unsigned int)_InterlockedExchange((volatile __int32 *)Context + 472, 0);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)Context + 234) + 36LL), 0, 1) )
    {
      v4 = *((_QWORD *)Context + 3);
      if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
      {
        PoFxIdleComponent(**((_QWORD **)Context + 234), 0, 0);
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
      }
      if ( *(_QWORD *)(v4 + 5024) )
        RaidAdapterPoFxIdleComponent(v4, 0, 0, v5);
    }
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  result = PoFxReportDevicePoweredOn(**((_QWORD **)Context + 234));
  if ( StorEtwLoggingEnabled )
  {
    if ( (byte_140177432 & 0x10) != 0 )
      return McTemplateK0pquuuq_EtwWriteTransfer(
               *((_QWORD *)Context + 3),
               (unsigned int)EventUnitPowerRequiredStop,
               v6,
               **((_QWORD **)Context + 234),
               *(_DWORD *)(*((_QWORD *)Context + 3) + 56LL),
               *((_BYTE *)Context + 104),
               *((_BYTE *)Context + 105),
               *((_BYTE *)Context + 106),
               0);
  }
  return result;
}

```

## disassembly

```asm
0x1400039c4  mov     [rsp+arg_0], rbx
0x1400039c9  push    rdi
0x1400039ca  sub     rsp, 70h
0x1400039ce  mov     rdi, rcx
0x1400039d1  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400039d6  xorps   xmm0, xmm0
0x1400039d9  xor     eax, eax
0x1400039db  add     rcx, 30h ; '0'; SpinLock
0x1400039df  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400039e4  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400039e9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400039f0  nop     dword ptr [rax+rax+00h]
0x1400039f5  mov     rcx, [rdi+750h]
0x1400039fc  mov     ebx, 1
0x140003a01  mov     eax, [rcx+20h]
0x140003a04  test    al, 4
0x140003a06  jz      short loc_140003A13
0x140003a08  mov     rax, [rcx+8]
0x140003a0c  mov     ecx, [rax+0Ch]
0x140003a0f  test    bl, cl
0x140003a11  jnz     short loc_140003A83
0x140003a13  cmp     [rdi+224h], ebx
0x140003a19  jz      loc_140003B29
0x140003a1f  mov     rcx, [rdi+8]; DeviceObject
0x140003a23  lea     r9, RaidUnitDeviceStackPowerUpCompletion; CompletionFunction
0x140003a2a  mov     [rsp+78h+Irp], 0; Irp
0x140003a33  mov     r8d, ebx; PowerState
0x140003a36  mov     dl, 2; MinorFunction
0x140003a38  mov     [rsp+78h+Context], rdi; Context
0x140003a3d  call    cs:__imp_PoRequestPowerIrp
0x140003a44  nop     dword ptr [rax+rax+00h]
0x140003a49  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140003a4e  cmp     eax, 103h
0x140003a53  jnz     loc_140003B4C
0x140003a59  or      byte ptr [rdi+1F8h], 80h
0x140003a60  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003a67  nop     dword ptr [rax+rax+00h]
0x140003a6c  xor     eax, eax
0x140003a6e  xchg    eax, [rdi+760h]
0x140003a74  mov     rbx, [rsp+78h+arg_0]
0x140003a7c  add     rsp, 70h
0x140003a80  pop     rdi
0x140003a81  retn
0x140003a83  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140003a88  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003a8f  nop     dword ptr [rax+rax+00h]
0x140003a94  mov     rax, [rdi+18h]
0x140003a98  cmp     qword ptr [rax+13A0h], 0
0x140003aa0  jz      loc_14014BFE6
0x140003aa6  xor     eax, eax
0x140003aa8  lock cmpxchg [rdi+0E20h], ebx
0x140003ab0  jnz     loc_14014BFE6
0x140003ab6  mov     rcx, [rdi+18h]
0x140003aba  xor     r8d, r8d
0x140003abd  xor     edx, edx
0x140003abf  call    RaidAdapterPoFxActivateComponent
0x140003ac4  nop
0x140003ac5  jmp     loc_14014BFE6
0x140003aca  mov     rbx, [rdi+18h]
0x140003ace  mov     rcx, rdi
0x140003ad1  call    RaidUnitCheckAndAcquirePoFx
0x140003ad6  test    al, al
0x140003ad8  jz      short loc_140003B08
0x140003ada  mov     rcx, [rdi+750h]
0x140003ae1  xor     r8d, r8d
0x140003ae4  xor     edx, edx
0x140003ae6  mov     rcx, [rcx]
0x140003ae9  call    cs:__imp_PoFxIdleComponent
0x140003af0  nop     dword ptr [rax+rax+00h]
0x140003af5  mov     rcx, [rdi+748h]; RunRefCacheAware
0x140003afc  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140003b03  nop     dword ptr [rax+rax+00h]
0x140003b08  cmp     qword ptr [rbx+13A0h], 0
0x140003b10  jz      loc_14014BFE6
0x140003b16  xor     r8d, r8d
0x140003b19  xor     edx, edx
0x140003b1b  mov     rcx, rbx
0x140003b1e  call    RaidAdapterPoFxIdleComponent
0x140003b23  nop
0x140003b24  jmp     loc_14014BFE6
0x140003b29  test    [rdi+1F9h], bl
0x140003b2f  jnz     loc_140003A1F
0x140003b35  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140003b3a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003b41  nop     dword ptr [rax+rax+00h]
0x140003b46  nop
0x140003b47  jmp     loc_14014BFE6
0x140003b4c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003b53  nop     dword ptr [rax+rax+00h]
0x140003b58  mov     rdx, [rdi+750h]
0x140003b5f  xor     ecx, ecx
0x140003b61  mov     eax, ebx
0x140003b63  lock cmpxchg [rdx+24h], ecx
0x140003b68  test    eax, eax
0x140003b6a  jz      loc_14014BFE6
0x140003b70  jmp     loc_140003ACA
0x14014bfe6  mov     rcx, [rdi+750h]
0x14014bfed  mov     rcx, [rcx]
0x14014bff0  call    cs:__imp_PoFxReportDevicePoweredOn
0x14014bff7  nop     dword ptr [rax+rax+00h]
0x14014bffc  cmp     cs:StorEtwLoggingEnabled, 0
0x14014c003  jz      loc_140003A74
0x14014c009  test    cs:byte_140177432, 10h
0x14014c010  jz      loc_140003A74
0x14014c016  mov     al, [rdi+6Ah]
0x14014c019  lea     rdx, EventUnitPowerRequiredStop
0x14014c020  mov     rcx, [rdi+18h]
0x14014c024  mov     r9, [rdi+750h]
0x14014c02b  mov     [rsp+78h+var_38], 0
0x14014c033  mov     [rsp+78h+var_40], al
0x14014c037  mov     al, [rdi+69h]
0x14014c03a  mov     r9, [r9]
0x14014c03d  mov     [rsp+78h+var_48], al
0x14014c041  mov     al, [rdi+68h]
0x14014c044  mov     byte ptr [rsp+78h+Irp], al
0x14014c048  mov     eax, [rcx+38h]
0x14014c04b  mov     dword ptr [rsp+78h+Context], eax
0x14014c04f  call    McTemplateK0pquuuq_EtwWriteTransfer
0x14014c054  nop
0x14014c055  jmp     loc_140003A74
```
