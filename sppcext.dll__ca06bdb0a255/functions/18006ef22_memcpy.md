# memcpy

- ea: `0x18006ef22`
- end: `0x18006ef28`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `45`
- callee_count: `0`
- tags: ``

## callers

- `0x180004774`
- `0x180004910`
- `0x180004b44`
- `0x18000503c`
- `0x1800059f8`
- `0x1800073c0`
- `0x180007a90`
- `0x180007ba8`
- `0x180007cec`
- `0x180008af4`
- `0x180014f80`
- `0x180015190`
- `0x180017370`
- `0x180022df4`
- `0x180022efc`
- `0x180028030`
- `0x180034230`
- `0x180036300`
- `0x180037fc0`
- `0x1800390bc`
- `0x18003aa18`
- `0x18003ac84`
- `0x18003b3c4`
- `0x18003b530`
- `0x18003bc34`
- `0x18003bd48`
- `0x18003be50`
- `0x18003c974`
- `0x18003cd80`
- `0x18003e78c`
- `0x18003fc4c`
- `0x18003fd38`
- `0x18003fdcc`
- `0x18004b158`
- `0x18004ca68`
- `0x18004db50`
- `0x18004dfb4`
- `0x18004e600`
- `0x180053f8c`
- `0x1800540a0`
- `0x1800564c4`
- `0x180056c38`
- `0x180057e24`
- `0x180058bd4`
- `0x180059420`

## import_xrefs

- `msvcrt!memcpy` at `0x18006ef22`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18006ef22  jmp     cs:__imp_memcpy
```
