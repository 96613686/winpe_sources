# j__guard_dispatch_icall

- ea: `0x18003b010`
- end: `0x18003b015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `165`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001208`
- `0x180001394`
- `0x180001794`
- `0x180001a84`
- `0x180001ac8`
- `0x180009314`
- `0x18000961c`
- `0x18000965c`
- `0x1800096a0`
- `0x1800097a0`
- `0x180009c0c`
- `0x180009d80`
- `0x18000a310`
- `0x18000a3b0`
- `0x18000a420`
- `0x18000a6a0`
- `0x18000a7b0`
- `0x18000a8b0`
- `0x18000a930`
- `0x18000a9b0`
- `0x18000abc0`
- `0x18000acd0`
- `0x18000ad50`
- `0x18000b73c`
- `0x18000b870`
- `0x18000b960`
- `0x18000ba60`
- `0x18000ba90`
- `0x18000bb40`
- `0x18000bc30`
- `0x18000bd30`
- `0x18000bdb0`
- `0x18000bde0`
- `0x18000be70`
- `0x18000c040`
- `0x18000c130`
- `0x18000c5d0`
- `0x18000c768`
- `0x18000cce0`
- `0x18000cde0`
- `0x18000cfa0`
- `0x18000d070`
- `0x18000d290`
- `0x18000d2d0`
- `0x18000d5b0`
- `0x18000d6f0`
- `0x18000e500`
- `0x18000e780`
- `0x18000e940`
- `0x18000ed50`

## callees

- `0x180039b60`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j__guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x18003b010  jmp     _guard_dispatch_icall
```
