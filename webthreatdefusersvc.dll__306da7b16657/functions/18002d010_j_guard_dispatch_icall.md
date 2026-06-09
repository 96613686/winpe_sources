# j__guard_dispatch_icall

- ea: `0x18002d010`
- end: `0x18002d015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `330`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002ad0`
- `0x180003378`
- `0x180003504`
- `0x1800036b4`
- `0x180003724`
- `0x18000385c`
- `0x180003d04`
- `0x180003d48`
- `0x1800043d8`
- `0x180004610`
- `0x180004688`
- `0x180004790`
- `0x180004804`
- `0x180004878`
- `0x1800048ec`
- `0x1800049c8`
- `0x180004ae8`
- `0x180004b68`
- `0x180004bf8`
- `0x180004cc0`
- `0x180004d38`
- `0x180004ea4`
- `0x180004ed8`
- `0x180004fe0`
- `0x180005084`
- `0x1800050dc`
- `0x1800051c4`
- `0x1800051fc`
- `0x18000538c`
- `0x1800056a0`
- `0x1800058d0`
- `0x180005b30`
- `0x180005cec`
- `0x180005de8`
- `0x18000631c`
- `0x180006388`
- `0x180006400`
- `0x180006468`
- `0x1800066d0`
- `0x180006794`
- `0x1800069fc`
- `0x180006aec`
- `0x180006dac`
- `0x180006ed0`
- `0x180006f08`
- `0x180006f3c`
- `0x180006f90`
- `0x180006ff8`
- `0x180007088`
- `0x1800071b8`

## callees

- `0x18002a540`

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
0x18002d010  jmp     _guard_dispatch_icall
```
