# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x1800157a4`
- end: `0x1800157a9`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036dc`
- `0x1800040ac`
- `0x180006ab0`
- `0x180006ff0`
- `0x180008b68`
- `0x180009b3c`
- `0x18000a3f0`
- `0x18000a870`
- `0x18000ae38`
- `0x18000b228`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000be10`
- `0x18000bf44`
- `0x18000c03c`
- `0x18000c158`
- `0x18000c2d0`
- `0x180012cd4`
- `0x1800130dc`
- `0x180013648`
- `0x180013b48`
- `0x180013c14`
- `0x180013d50`
- `0x180013dcc`
- `0x180013ea4`
- `0x18001465c`

## callees

- `0x18001577c`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  return operator new(a1, a2);
}

```

## disassembly

```asm
0x1800157a4  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
```
