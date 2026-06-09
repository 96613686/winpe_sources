# _guard_dispatch_icall_nop

- ea: `0x18000ba60`
- end: `0x18000ba62`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000ba40`
- `0x18000ba80`

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
0x18000ba60  jmp     rax
```
