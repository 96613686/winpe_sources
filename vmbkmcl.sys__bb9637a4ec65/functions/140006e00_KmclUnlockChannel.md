# KmclUnlockChannel

- ea: `0x140006e00`
- end: `0x140006e29`
- name: `KmclUnlockChannel`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1400069c0`
- `0x140006c70`
- `0x14000a8c8`
- `0x14000abe0`
- `0x14000afe8`
- `0x14000bb70`
- `0x14000c87c`
- `0x14000cdb0`
- `0x14000cfe4`
- `0x14000d310`
- `0x14000d83c`
- `0x14000d9b0`
- `0x14000defc`
- `0x14000e4e0`
- `0x14000e9e0`
- `0x14000ed00`
- `0x14000f340`
- `0x14001d3b0`
- `0x14001d4f0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006e0b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006e0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e17`

## pseudocode

```c
void __fastcall KmclUnlockChannel(__int64 a1)
{
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 2288));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140006e00  sub     rsp, 28h
0x140006e04  add     rcx, 8F0h; FastMutex
0x140006e0b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006e12  nop     dword ptr [rax+rax+00h]
0x140006e17  call    cs:__imp_KeLeaveCriticalRegion
0x140006e1e  nop     dword ptr [rax+rax+00h]
0x140006e23  add     rsp, 28h
0x140006e27  retn
```
