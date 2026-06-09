# _tag_TOKEN_SCARD_READERSTATE::_tag_TOKEN_SCARD_READERSTATE(void)

- ea: `0x180036ec4`
- end: `0x180036ed0`
- name: `??0_tag_TOKEN_SCARD_READERSTATE@@QEAA@XZ`
- size: `12`
- prototype: `_tag_TOKEN_SCARD_READERSTATE *__fastcall(_tag_TOKEN_SCARD_READERSTATE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180038090`

## pseudocode

```c
_tag_TOKEN_SCARD_READERSTATE *__fastcall _tag_TOKEN_SCARD_READERSTATE::_tag_TOKEN_SCARD_READERSTATE(
        _tag_TOKEN_SCARD_READERSTATE *this)
{
  *((_QWORD *)this + 8) = 0;
  return this;
}

```

## disassembly

```asm
0x180036ec4  mov     qword ptr [rcx+40h], 0
0x180036ecc  mov     rax, rcx
0x180036ecf  retn
```
