# TiUnlockSession

- ea: `0x140002e58`
- end: `0x140002e72`
- name: `TiUnlockSession`
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

- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002e60`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002e60`

## pseudocode

```c
void __fastcall TiUnlockSession(__int64 a1)
{
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 8));
}

```

## disassembly

```asm
0x140002e58  sub     rsp, 28h
0x140002e5c  add     rcx, 8; Mutex
0x140002e60  call    cs:__imp_KeReleaseGuardedMutex
0x140002e67  nop     dword ptr [rax+rax+00h]
0x140002e6c  add     rsp, 28h
0x140002e70  retn
```
