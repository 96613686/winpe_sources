# _guard_dispatch_icall_nop

- ea: `0x140017a50`
- end: `0x140017a52`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140004820`
- `0x140005670`
- `0x140005870`
- `0x140005d80`
- `0x140005f40`
- `0x140006050`
- `0x1400061a0`
- `0x140006600`
- `0x140006620`
- `0x140006e50`
- `0x140006ec0`
- `0x140006f30`
- `0x1400071f0`
- `0x140017a80`
- `0x140017ab0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140017a50  jmp     rax
```
