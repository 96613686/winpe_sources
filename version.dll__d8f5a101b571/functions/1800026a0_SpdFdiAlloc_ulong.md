# SpdFdiAlloc(ulong)

- ea: `0x1800026a0`
- end: `0x1800026ab`
- name: `?SpdFdiAlloc@@YAPEAXK@Z`
- size: `11`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026a4`

## pseudocode

```c
HLOCAL __fastcall SpdFdiAlloc(unsigned int a1)
{
  return LocalAlloc(0, a1);
}

```

## disassembly

```asm
0x1800026a0  mov     edx, ecx
0x1800026a2  xor     ecx, ecx
0x1800026a4  jmp     cs:__imp_LocalAlloc
```
