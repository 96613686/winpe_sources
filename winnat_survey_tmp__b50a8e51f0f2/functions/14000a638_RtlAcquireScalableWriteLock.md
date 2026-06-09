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
- `0x14000f6e0`
- `0x14000f9fc`
- `0x140010000`
- `0x140011300`
- `0x140014f60`
- `0x14001506c`
- `0x14001536c`
- `0x140018e40`
- `0x140018f48`
- `0x1400191c4`
- `0x1400193ac`
- `0x140019528`
- `0x1400195fc`
- `0x1400196e0`
- `0x140019798`
- `0x140019afc`
- `0x14001a178`
- `0x14001a954`
- `0x14001ae6c`
- `0x14001b0ac`
- `0x14001b50c`
- `0x14001b808`

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
