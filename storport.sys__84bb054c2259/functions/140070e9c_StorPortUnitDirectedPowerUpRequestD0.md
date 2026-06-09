# StorPortUnitDirectedPowerUpRequestD0

- ea: `0x140070e9c`
- end: `0x140071056`
- name: `StorPortUnitDirectedPowerUpRequestD0`
- size: `442`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a6cc0`

## callees

- `0x1400016cc`
- `0x140005c50`
- `0x140066a60`
- `0x140070e9c`
- `0x1400712a0`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140070f9a`
- `ntoskrnl!PoFxIdleComponent` at `0x140070f9a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140070fad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140070fad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140070ec1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140070ec1`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x140070fd6`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x140070fd6`
- `ntoskrnl!PoRequestPowerIrp` at `0x140070f24`
- `ntoskrnl!PoRequestPowerIrp` at `0x140070f24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070ee7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070f43`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070f5c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070ee7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070f43`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140070f5c`

## pseudocode

```c
_QWORD *__fastcall StorPortUnitDirectedPowerUpRequestD0(char *Context)
{
  _QWORD **v2; // rsi
  _QWORD *v3; // r14
  _QWORD *result; // rax
  __int64 v5; // rbx
  __int64 v6; // r9
  int v7; // ecx
  int v8; // r8d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)Context + 6, &LockHandle);
  if ( *((_DWORD *)Context + 137) != 1 || (Context[505] & 1) != 0 )
  {
    v3 = Context + 8;
    if ( PoRequestPowerIrp(
           *((PDEVICE_OBJECT *)Context + 1),
           2u,
           (POWER_STATE)1,
           StorPortUnitDirectedPowerUpCompletion,
           Context,
           0) == 259 )
    {
      Context[504] |= 0x80u;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      return (_QWORD *)(unsigned int)_InterlockedExchange((volatile __int32 *)Context + 472, 0);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v2 = (_QWORD **)(Context + 1872);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)Context + 234) + 36LL), 0, 1) )
    {
      v5 = *((_QWORD *)Context + 3);
      if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
      {
        PoFxIdleComponent(**v2, 0, 0);
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
      }
      if ( *(_QWORD *)(v5 + 5024) )
        RaidAdapterPoFxIdleComponent(v5, 0, 0, v6);
    }
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v2 = (_QWORD **)(Context + 1872);
    v3 = Context + 8;
  }
  PoFxReportDevicePoweredOn(**v2);
  if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
    McTemplateK0pquuuq_EtwWriteTransfer(
      v7,
      (unsigned int)EventUnitDirectedPowerUpStop,
      v8,
      **v2,
      *(_DWORD *)(*((_QWORD *)Context + 3) + 56LL),
      Context[104],
      Context[105],
      Context[106],
      0);
  result = Context + 3496;
  if ( (_QWORD *)*result != result )
    return (_QWORD *)RaFlushDFxQueue(*v3);
  Context[507] &= ~2u;
  return result;
}

```

## disassembly

```asm
0x140070e9c  push    rbx
0x140070e9e  push    rsi
0x140070e9f  push    rdi
0x140070ea0  push    r14
0x140070ea2  sub     rsp, 78h
0x140070ea6  mov     rdi, rcx
0x140070ea9  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140070eae  xorps   xmm0, xmm0
0x140070eb1  xor     eax, eax
0x140070eb3  add     rcx, 30h ; '0'; SpinLock
0x140070eb7  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140070ebc  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x140070ec1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140070ec8  nop     dword ptr [rax+rax+00h]
0x140070ecd  mov     ebx, 1
0x140070ed2  cmp     [rdi+224h], ebx
0x140070ed8  jnz     short loc_140070F03
0x140070eda  test    [rdi+1F9h], bl
0x140070ee0  jnz     short loc_140070F03
0x140070ee2  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140070ee7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070eee  nop     dword ptr [rax+rax+00h]
0x140070ef3  lea     rsi, [rdi+750h]
0x140070efa  lea     r14, [rdi+8]
0x140070efe  jmp     loc_140070FD0
0x140070f03  lea     r14, [rdi+8]
0x140070f07  mov     [rsp+98h+Irp], 0; Irp
0x140070f10  mov     rcx, [r14]; DeviceObject
0x140070f13  lea     r9, StorPortUnitDirectedPowerUpCompletion; CompletionFunction
0x140070f1a  mov     r8d, ebx; PowerState
0x140070f1d  mov     [rsp+98h+Context], rdi; Context
0x140070f22  mov     dl, 2; MinorFunction
0x140070f24  call    cs:__imp_PoRequestPowerIrp
0x140070f2b  nop     dword ptr [rax+rax+00h]
0x140070f30  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140070f35  cmp     eax, 103h
0x140070f3a  jnz     short loc_140070F5C
0x140070f3c  or      byte ptr [rdi+1F8h], 80h
0x140070f43  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070f4a  nop     dword ptr [rax+rax+00h]
0x140070f4f  xor     eax, eax
0x140070f51  xchg    eax, [rdi+760h]
0x140070f57  jmp     loc_14007104B
0x140070f5c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140070f63  nop     dword ptr [rax+rax+00h]
0x140070f68  lea     rsi, [rdi+750h]
0x140070f6f  xor     ecx, ecx
0x140070f71  mov     rdx, [rsi]
0x140070f74  mov     eax, ebx
0x140070f76  lock cmpxchg [rdx+24h], ecx
0x140070f7b  test    eax, eax
0x140070f7d  jz      short loc_140070FD0
0x140070f7f  mov     rbx, [rdi+18h]
0x140070f83  mov     rcx, rdi
0x140070f86  call    RaidUnitCheckAndAcquirePoFx
0x140070f8b  test    al, al
0x140070f8d  jz      short loc_140070FB9
0x140070f8f  mov     rcx, [rsi]
0x140070f92  xor     r8d, r8d
0x140070f95  xor     edx, edx
0x140070f97  mov     rcx, [rcx]
0x140070f9a  call    cs:__imp_PoFxIdleComponent
0x140070fa1  nop     dword ptr [rax+rax+00h]
0x140070fa6  mov     rcx, [rdi+748h]; RunRefCacheAware
0x140070fad  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140070fb4  nop     dword ptr [rax+rax+00h]
0x140070fb9  cmp     qword ptr [rbx+13A0h], 0
0x140070fc1  jz      short loc_140070FD0
0x140070fc3  xor     r8d, r8d
0x140070fc6  xor     edx, edx
0x140070fc8  mov     rcx, rbx
0x140070fcb  call    RaidAdapterPoFxIdleComponent
0x140070fd0  mov     rcx, [rsi]
0x140070fd3  mov     rcx, [rcx]
0x140070fd6  call    cs:__imp_PoFxReportDevicePoweredOn
0x140070fdd  nop     dword ptr [rax+rax+00h]
0x140070fe2  cmp     cs:StorEtwLoggingEnabled, 0
0x140070fe9  jz      short loc_14007102E
0x140070feb  test    cs:byte_140177432, 10h
0x140070ff2  jz      short loc_14007102E
0x140070ff4  mov     al, [rdi+6Ah]
0x140070ff7  mov     rdx, [rdi+18h]
0x140070ffb  mov     r9, [rsi]
0x140070ffe  mov     [rsp+98h+var_58], 0
0x140071006  mov     [rsp+98h+var_60], al
0x14007100a  mov     al, [rdi+69h]
0x14007100d  mov     r9, [r9]
0x140071010  mov     [rsp+98h+var_68], al
0x140071014  mov     al, [rdi+68h]
0x140071017  mov     byte ptr [rsp+98h+Irp], al
0x14007101b  mov     eax, [rdx+38h]
0x14007101e  lea     rdx, EventUnitDirectedPowerUpStop
0x140071025  mov     dword ptr [rsp+98h+Context], eax
0x140071029  call    McTemplateK0pquuuq_EtwWriteTransfer
0x14007102e  lea     rax, [rdi+0DA8h]
0x140071035  cmp     [rax], rax
0x140071038  jz      short loc_140071044
0x14007103a  mov     rcx, [r14]
0x14007103d  call    RaFlushDFxQueue
0x140071042  jmp     short loc_14007104B
0x140071044  and     byte ptr [rdi+1FBh], 0FDh
0x14007104b  add     rsp, 78h
0x14007104f  pop     r14
0x140071051  pop     rdi
0x140071052  pop     rsi
0x140071053  pop     rbx
0x140071054  retn
```
