# _CxxThrowException_0

- ea: `0x180008fce`
- end: `0x180008fd4`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e28`
- `0x18000805c`
- `0x180008700`
- `0x1800087f8`
- `0x180008824`
- `0x18000f2ac`
- `0x18000f680`
- `0x18000f7dc`
- `0x1800118ec`
- `0x1800119a4`
- `0x180011b54`
- `0x18001308c`
- `0x18001317c`
- `0x18001be00`
- `0x18001be1d`
- `0x18001be47`
- `0x18001be64`
- `0x18001c1b7`
- `0x18001c1f0`
- `0x18001c217`
- `0x18001c24d`
- `0x18001c27c`
- `0x18001c2ce`
- `0x18001c30a`
- `0x18001c433`
- `0x18001c45d`
- `0x18001c48b`
- `0x18001c51f`
- `0x18001c571`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180008fce`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x180008fce  jmp     cs:__imp__CxxThrowException
```
