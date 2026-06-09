# ChOfferCacheCleanup

- ea: `0x14002dab8`
- end: `0x14002db3d`
- name: `ChOfferCacheCleanup`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b200`

## callees

- `0x14002dab8`
- `0x14002f5a8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002dae4`
- `ntoskrnl!KeSetEvent` at `0x14002dae4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002db0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002db0d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002db20`
- `ntoskrnl!ObfDereferenceObject` at `0x14002db20`

## pseudocode

```c
int ChOfferCacheCleanup()
{
  int result; // eax

  result = DvRundownWorkQueue(&ChLocalOfferRemoveWorkQueue);
  if ( ChLocalOfferRemoveThreadStarted )
  {
    ChLocalOfferRemoveThreadTerminate = 1;
    result = KeSetEvent(&ChLocalOfferRemoveThreadWake, 0, 0);
  }
  if ( ChLocalOfferRemoveThread )
  {
    KeWaitForSingleObject(ChLocalOfferRemoveThread, Executive, 0, 0, 0);
    result = ObfDereferenceObject(ChLocalOfferRemoveThread);
    ChLocalOfferRemoveThread = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002dab8  sub     rsp, 38h
0x14002dabc  lea     rcx, ChLocalOfferRemoveWorkQueue
0x14002dac3  call    DvRundownWorkQueue
0x14002dac8  cmp     cs:ChLocalOfferRemoveThreadStarted, 0
0x14002dacf  jz      short loc_14002DAF0
0x14002dad1  xor     r8d, r8d; Wait
0x14002dad4  mov     cs:ChLocalOfferRemoveThreadTerminate, 1
0x14002dadb  xor     edx, edx; Increment
0x14002dadd  lea     rcx, ChLocalOfferRemoveThreadWake; Event
0x14002dae4  call    cs:__imp_KeSetEvent
0x14002daeb  nop     dword ptr [rax+rax+00h]
0x14002daf0  mov     rcx, cs:ChLocalOfferRemoveThread; Object
0x14002daf7  test    rcx, rcx
0x14002dafa  jz      short loc_14002DB37
0x14002dafc  xor     r9d, r9d; Alertable
0x14002daff  mov     [rsp+38h+Timeout], 0; Timeout
0x14002db08  xor     r8d, r8d; WaitMode
0x14002db0b  xor     edx, edx; WaitReason
0x14002db0d  call    cs:__imp_KeWaitForSingleObject
0x14002db14  nop     dword ptr [rax+rax+00h]
0x14002db19  mov     rcx, cs:ChLocalOfferRemoveThread; Object
0x14002db20  call    cs:__imp_ObfDereferenceObject
0x14002db27  nop     dword ptr [rax+rax+00h]
0x14002db2c  mov     cs:ChLocalOfferRemoveThread, 0
0x14002db37  add     rsp, 38h
0x14002db3b  retn
```
