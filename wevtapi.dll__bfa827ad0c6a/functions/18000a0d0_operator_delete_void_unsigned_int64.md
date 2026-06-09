# operator delete(void *,unsigned __int64)

- ea: `0x18000a0d0`
- end: `0x18000a0d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `47`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008fd4`
- `0x18000a12c`
- `0x18000a208`
- `0x18000a250`
- `0x18000a4e0`
- `0x18000b6a0`
- `0x18000bb80`
- `0x180013e30`
- `0x1800154a0`
- `0x180015610`
- `0x180015650`
- `0x180018130`
- `0x18001992c`
- `0x18001a420`
- `0x18001a4ac`
- `0x18001cfc0`
- `0x18001d050`
- `0x18001d190`
- `0x18001e170`
- `0x18001ea80`
- `0x18001eac0`
- `0x1800200b0`
- `0x180020270`
- `0x180023d70`
- `0x1800258c0`
- `0x1800266b0`
- `0x180027f30`
- `0x180027f70`
- `0x18002862c`
- `0x180028860`
- `0x1800288a0`
- `0x180029dd0`
- `0x180029e10`
- `0x18002dde0`
- `0x18002df90`
- `0x1800310d4`
- `0x180032dbc`
- `0x18003316c`
- `0x180034fd8`
- `0x180036688`
- `0x180036bb0`
- `0x180039534`
- `0x180039c7a`
- `0x180039cb2`
- `0x180039d65`
- `0x18003a789`
- `0x18003aaf6`

## callees

- `0x18000a100`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x18000a0d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
