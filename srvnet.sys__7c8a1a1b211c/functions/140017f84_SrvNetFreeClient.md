# SrvNetFreeClient

- ea: `0x140017f84`
- end: `0x140018086`
- name: `SrvNetFreeClient`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140055f5c`

## callees

- `0x140007360`
- `0x140017f84`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140017ffc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017ffc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001801b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001801b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017fac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017fac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140017f97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140017f97`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018048`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018048`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fc3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018068`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018068`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001800f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001800f`

## pseudocode

```c
PERESOURCE __fastcall SrvNetFreeClient(__int64 a1)
{
  KIRQL v2; // al
  PERESOURCE v3; // rcx
  void (*v4)(void); // rax
  PERESOURCE result; // rax

  *(_DWORD *)(a1 + 132) = 2;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
  *(&SrvNetDeviceExtension[4].OwnerEntry.OwnerThread + *(unsigned int *)(a1 + 232)) = 0;
  v3 = SrvNetDeviceExtension;
  --LODWORD(SrvNetDeviceExtension[5].SystemResourcesList.Flink);
  KeReleaseSpinLock((PKSPIN_LOCK)&v3[1], v2);
  ExReleaseResourceLite(SrvNetDeviceExtension);
  KeLeaveCriticalRegion();
  if ( *(_QWORD *)(a1 + 152) )
  {
    v4 = *(void (**)(void))(a1 + 208);
    if ( v4 )
      v4();
  }
  ExDeleteResourceLite((PERESOURCE)(a1 + 16));
  SrvNetUpdateMemStatistics(*(unsigned int *)(a1 - 12), *(unsigned int *)(a1 - 16), 0);
  ExFreePoolWithTag((PVOID)(a1 - 16), 0);
  result = SrvNetDeviceExtension;
  _InterlockedDecrement((volatile signed __int32 *)&SrvNetDeviceExtension[1].SystemResourcesList.Blink);
  return result;
}

```

## disassembly

```asm
0x140017f84  push    rbx
0x140017f86  sub     rsp, 20h
0x140017f8a  mov     rbx, rcx
0x140017f8d  mov     dword ptr [rcx+84h], 2
0x140017f97  call    cs:__imp_KeEnterCriticalRegion
0x140017f9e  nop     dword ptr [rax+rax+00h]
0x140017fa3  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140017faa  mov     dl, 1; Wait
0x140017fac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140017fb3  nop     dword ptr [rax+rax+00h]
0x140017fb8  mov     rcx, cs:SrvNetDeviceExtension
0x140017fbf  add     rcx, 68h ; 'h'; SpinLock
0x140017fc3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017fca  nop     dword ptr [rax+rax+00h]
0x140017fcf  mov     r8d, [rbx+0E8h]
0x140017fd6  mov     rdx, cs:SrvNetDeviceExtension
0x140017fdd  mov     qword ptr [rdx+r8*8+1D0h], 0
0x140017fe9  mov     dl, al; NewIrql
0x140017feb  mov     rcx, cs:SrvNetDeviceExtension
0x140017ff2  dec     dword ptr [rcx+208h]
0x140017ff8  add     rcx, 68h ; 'h'; SpinLock
0x140017ffc  call    cs:__imp_KeReleaseSpinLock
0x140018003  nop     dword ptr [rax+rax+00h]
0x140018008  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14001800f  call    cs:__imp_ExReleaseResourceLite
0x140018016  nop     dword ptr [rax+rax+00h]
0x14001801b  call    cs:__imp_KeLeaveCriticalRegion
0x140018022  nop     dword ptr [rax+rax+00h]
0x140018027  mov     rcx, [rbx+98h]
0x14001802e  test    rcx, rcx
0x140018031  jz      short loc_140018044
0x140018033  mov     rax, [rbx+0D0h]
0x14001803a  test    rax, rax
0x14001803d  jz      short loc_140018044
0x14001803f  call    _guard_dispatch_icall
0x140018044  lea     rcx, [rbx+10h]; Resource
0x140018048  call    cs:__imp_ExDeleteResourceLite
0x14001804f  nop     dword ptr [rax+rax+00h]
0x140018054  mov     ecx, [rbx-0Ch]
0x140018057  xor     r8d, r8d
0x14001805a  mov     edx, [rbx-10h]
0x14001805d  call    SrvNetUpdateMemStatistics
0x140018062  xor     edx, edx; Tag
0x140018064  lea     rcx, [rbx-10h]; P
0x140018068  call    cs:__imp_ExFreePoolWithTag
0x14001806f  nop     dword ptr [rax+rax+00h]
0x140018074  mov     rax, cs:SrvNetDeviceExtension
0x14001807b  lock dec dword ptr [rax+70h]
0x14001807f  add     rsp, 20h
0x140018083  pop     rbx
0x140018084  retn
```
