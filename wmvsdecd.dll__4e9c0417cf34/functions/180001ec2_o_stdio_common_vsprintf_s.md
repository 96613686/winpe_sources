# _o___stdio_common_vsprintf_s

- ea: `0x180001ec2`
- end: `0x180001ec8`
- name: `_o___stdio_common_vsprintf_s`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x180001ec2`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsprintf_s()
{
  return _o___stdio_common_vsprintf_s();
}

```

## disassembly

```asm
0x180001ec2  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
