# mmTaskYieldStub

- ea: `0x18000f6d0`
- end: `0x18000f6d7`
- name: `mmTaskYieldStub`
- size: `7`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `WINMMBASE!mmTaskYield` at `0x18000f6d0`

## pseudocode

```c
// attributes: thunk
void __stdcall mmTaskYieldStub()
{
  mmTaskYield();
}

```

## disassembly

```asm
0x18000f6d0  jmp     cs:__imp_mmTaskYield
```
