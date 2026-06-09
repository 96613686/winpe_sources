# RtlAcquireScalableWriteLockAtDpcLevel

- ea: `0x14000baf8`
- end: `0x14000bb31`
- name: `RtlAcquireScalableWriteLockAtDpcLevel`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ed0`
- `0x14000a9d0`
- `0x14000f5cc`
- `0x140018b00`
- `0x140018c7c`
- `0x14001a398`

## callees

- `0x14000baf8`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000bb01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000bb01`

## pseudocode

```c
void __fastcall RtlAcquireScalableWriteLockAtDpcLevel(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2)
{
  int i; // edx

  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)a1, a2);
  for ( i = 0; i <= *(_DWORD *)(a1 + 8); ++i )
  {
    while ( *(_DWORD *)(((__int64)i << 6) + a1 + 64) )
      ;
  }
}

```

## disassembly

```asm
0x14000baf8  push    rbx
0x14000bafa  sub     rsp, 20h
0x14000bafe  mov     rbx, rcx
0x14000bb01  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000bb08  nop     dword ptr [rax+rax+00h]
0x14000bb0d  xor     edx, edx
0x14000bb0f  cmp     [rbx+8], edx
0x14000bb12  jl      short loc_14000BB2A
0x14000bb14  movsxd  rcx, edx
0x14000bb17  shl     rcx, 6
0x14000bb1b  mov     eax, [rcx+rbx+40h]
0x14000bb1f  test    eax, eax
0x14000bb21  jnz     short loc_14000BB1B
0x14000bb23  inc     edx
0x14000bb25  cmp     edx, [rbx+8]
0x14000bb28  jle     short loc_14000BB14
0x14000bb2a  add     rsp, 20h
0x14000bb2e  pop     rbx
0x14000bb2f  retn
```
