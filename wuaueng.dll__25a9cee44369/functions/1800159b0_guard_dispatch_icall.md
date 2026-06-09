# _guard_dispatch_icall

- ea: `0x1800159b0`
- end: `0x1800159b6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x180001e74`
- `0x18000215c`
- `0x180002354`
- `0x180002520`
- `0x180002fc8`
- `0x180002fe8`
- `0x180003190`
- `0x180003280`
- `0x18000358c`
- `0x180003880`
- `0x1800038f0`
- `0x180004230`
- `0x180004580`
- `0x180004b60`
- `0x180004ff8`
- `0x180005524`
- `0x180006230`
- `0x1800062d0`
- `0x180006400`
- `0x180006790`
- `0x180006840`
- `0x180006a30`
- `0x180006a98`
- `0x180006e34`
- `0x1800071e0`
- `0x180008714`
- `0x180008c38`
- `0x180009af8`
- `0x18000a00c`
- `0x18000a070`
- `0x18000a430`
- `0x18000ecac`
- `0x18000eee0`
- `0x18000ef70`
- `0x18000efa4`
- `0x18000fd98`
- `0x180010188`
- `0x18001032c`
- `0x180010bf8`
- `0x180010c3c`
- `0x180010c88`
- `0x180010ce4`
- `0x180011a40`
- `0x180011e68`
- `0x180012350`
- `0x180012548`
- `0x180013cc0`
- `0x180013ef4`
- `0x180016463`

## callees

- `0x1800159d0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x1800159b0  jmp     cs:__guard_dispatch_icall_fptr
```
