# ChOfferCacheCleanup

- ea: `0x14002da68`
- end: `0x14002daed`
- name: `ChOfferCacheCleanup`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b1b0`

## callees

- `0x14002da68`
- `0x14002f558`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002da94`
- `ntoskrnl!KeSetEvent` at `0x14002da94`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002dabd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002dabd`
- `ntoskrnl!ObfDereferenceObject` at `0x14002dad0`
- `ntoskrnl!ObfDereferenceObject` at `0x14002dad0`

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
0x14002da68  sub     rsp, 38h
0x14002da6c  lea     rcx, ChLocalOfferRemoveWorkQueue
0x14002da73  call    DvRundownWorkQueue
0x14002da78  cmp     cs:ChLocalOfferRemoveThreadStarted, 0
0x14002da7f  jz      short loc_14002DAA0
0x14002da81  xor     r8d, r8d; Wait
0x14002da84  mov     cs:ChLocalOfferRemoveThreadTerminate, 1
0x14002da8b  xor     edx, edx; Increment
0x14002da8d  lea     rcx, ChLocalOfferRemoveThreadWake; Event
0x14002da94  call    cs:__imp_KeSetEvent
0x14002da9b  nop     dword ptr [rax+rax+00h]
0x14002daa0  mov     rcx, cs:ChLocalOfferRemoveThread; Object
0x14002daa7  test    rcx, rcx
0x14002daaa  jz      short loc_14002DAE7
0x14002daac  xor     r9d, r9d; Alertable
0x14002daaf  mov     [rsp+38h+Timeout], 0; Timeout
0x14002dab8  xor     r8d, r8d; WaitMode
0x14002dabb  xor     edx, edx; WaitReason
0x14002dabd  call    cs:__imp_KeWaitForSingleObject
0x14002dac4  nop     dword ptr [rax+rax+00h]
0x14002dac9  mov     rcx, cs:ChLocalOfferRemoveThread; Object
0x14002dad0  call    cs:__imp_ObfDereferenceObject
0x14002dad7  nop     dword ptr [rax+rax+00h]
0x14002dadc  mov     cs:ChLocalOfferRemoveThread, 0
0x14002dae7  add     rsp, 38h
0x14002daeb  retn
```
