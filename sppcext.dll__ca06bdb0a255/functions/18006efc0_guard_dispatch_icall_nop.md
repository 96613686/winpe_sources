# _guard_dispatch_icall_nop

- ea: `0x18006efc0`
- end: `0x18006efc2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002d90`
- `0x180003004`
- `0x180003218`
- `0x180041380`
- `0x180041574`
- `0x1800415c0`
- `0x180041830`
- `0x1800419a8`
- `0x180041af8`
- `0x180041d9c`
- `0x180041e50`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`
- `0x18006eff0`

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
0x18006efc0  jmp     rax
```
