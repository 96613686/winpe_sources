# j__guard_dispatch_icall

- ea: `0x18001c010`
- end: `0x18001c015`
- name: `j__guard_dispatch_icall`
- size: `5`
- prototype: ``
- caller_count: `138`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001c40`
- `0x1800025c8`
- `0x180002754`
- `0x1800029dc`
- `0x180002f80`
- `0x180002fc8`
- `0x180003150`
- `0x180003194`
- `0x180003724`
- `0x180003ba4`
- `0x180003eb0`
- `0x1800042ac`
- `0x1800043dc`
- `0x180004ba0`
- `0x180004d34`
- `0x180004df0`
- `0x180004f70`
- `0x1800050c0`
- `0x18000519c`
- `0x180005230`
- `0x180005268`
- `0x1800052d4`
- `0x180005360`
- `0x1800055b4`
- `0x180005990`
- `0x180005a10`
- `0x1800062e0`
- `0x18000674c`
- `0x180006848`
- `0x180007898`
- `0x180007c14`
- `0x180008354`
- `0x1800083c8`
- `0x1800097e0`
- `0x18000a710`
- `0x18000a824`
- `0x18000a964`
- `0x18000b3fc`
- `0x18000b428`
- `0x18000b468`
- `0x18000b8ec`
- `0x18000b9e8`
- `0x18000ba8c`
- `0x18000bac0`
- `0x18000bc40`
- `0x18000be40`
- `0x18000be80`
- `0x18000bec0`
- `0x18000c5f0`
- `0x18000c890`

## callees

- `0x18001b0b0`

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
0x18001c010  jmp     _guard_dispatch_icall
```
