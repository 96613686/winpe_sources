# RtlAcquireScalableWriteLock

- ea: `0x14000a638`
- end: `0x14000a671`
- name: `RtlAcquireScalableWriteLock`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x140004648`
- `0x1400085d0`
- `0x140009b04`
- `0x14000f738`
- `0x14000fa5c`
- `0x140010060`
- `0x140011360`
- `0x1400158dc`
- `0x1400159e8`
- `0x140015ce8`
- `0x140019320`
- `0x140019428`
- `0x1400196a4`
- `0x14001988c`
- `0x140019a08`
- `0x140019adc`
- `0x140019bc0`
- `0x140019c78`
- `0x140019fdc`
- `0x14001a658`
- `0x14001ae34`
- `0x14001b34c`
- `0x14001b58c`
- `0x14001b9ec`
- `0x14001bce8`

## callees

- `0x14000a638`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a641`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a641`

## pseudocode

```c
void __fastcall RtlAcquireScalableWriteLock(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2)
{
  int i; // edx

  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1, a2);
  for ( i = 0; i <= *(_DWORD *)(a1 + 8); ++i )
  {
    while ( *(_DWORD *)(((__int64)i << 6) + a1 + 64) )
      ;
  }
}

```

## disassembly

```asm
0x14000a638  push    rbx
0x14000a63a  sub     rsp, 20h
0x14000a63e  mov     rbx, rcx
0x14000a641  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a648  nop     dword ptr [rax+rax+00h]
0x14000a64d  xor     edx, edx
0x14000a64f  cmp     [rbx+8], edx
0x14000a652  jl      short loc_14000A66A
0x14000a654  movsxd  rcx, edx
0x14000a657  shl     rcx, 6
0x14000a65b  mov     eax, [rcx+rbx+40h]
0x14000a65f  test    eax, eax
0x14000a661  jnz     short loc_14000A65B
0x14000a663  inc     edx
0x14000a665  cmp     edx, [rbx+8]
0x14000a668  jle     short loc_14000A654
0x14000a66a  add     rsp, 20h
0x14000a66e  pop     rbx
0x14000a66f  retn
```
