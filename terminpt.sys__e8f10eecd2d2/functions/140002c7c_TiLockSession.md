# TiLockSession

- ea: `0x140002c7c`
- end: `0x140002c96`
- name: `TiLockSession`
- size: `26`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400092f0`
- `0x14000af20`
- `0x14000b2d0`

## import_xrefs

- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002c84`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002c84`

## pseudocode

```c
void __fastcall TiLockSession(__int64 a1)
{
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 8));
}

```

## disassembly

```asm
0x140002c7c  sub     rsp, 28h
0x140002c80  add     rcx, 8; Mutex
0x140002c84  call    cs:__imp_KeAcquireGuardedMutex
0x140002c8b  nop     dword ptr [rax+rax+00h]
0x140002c90  add     rsp, 28h
0x140002c94  retn
```
