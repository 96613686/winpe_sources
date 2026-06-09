# mmTaskBlockStub

- ea: `0x18000f6a0`
- end: `0x18000f6a7`
- name: `mmTaskBlockStub`
- size: `7`
- prototype: `void __stdcall(DWORD h)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `WINMMBASE!mmTaskBlock` at `0x18000f6a0`

## pseudocode

```c
// attributes: thunk
void __stdcall mmTaskBlockStub(DWORD h)
{
  mmTaskBlock(h);
}

```

## disassembly

```asm
0x18000f6a0  jmp     cs:__imp_mmTaskBlock
```
