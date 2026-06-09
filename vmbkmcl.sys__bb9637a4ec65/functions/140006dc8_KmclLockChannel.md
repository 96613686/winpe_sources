# KmclLockChannel

- ea: `0x140006dc8`
- end: `0x140006df7`
- name: `KmclLockChannel`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1400069c0`
- `0x140006c70`
- `0x14000a8c8`
- `0x14000abe0`
- `0x14000c87c`
- `0x14000cfe4`
- `0x14000d310`
- `0x14000d9b0`
- `0x14000e4e0`
- `0x14000e9e0`
- `0x14000ed00`
- `0x14000f340`
- `0x14001d3b0`
- `0x14001d4f0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006de4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006de4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006dd1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006dd1`

## pseudocode

```c
void __fastcall KmclLockChannel(__int64 a1)
{
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 2288));
}

```

## disassembly

```asm
0x140006dc8  push    rbx
0x140006dca  sub     rsp, 20h
0x140006dce  mov     rbx, rcx
0x140006dd1  call    cs:__imp_KeEnterCriticalRegion
0x140006dd8  nop     dword ptr [rax+rax+00h]
0x140006ddd  lea     rcx, [rbx+8F0h]; FastMutex
0x140006de4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140006deb  nop     dword ptr [rax+rax+00h]
0x140006df0  add     rsp, 20h
0x140006df4  pop     rbx
0x140006df5  retn
```
