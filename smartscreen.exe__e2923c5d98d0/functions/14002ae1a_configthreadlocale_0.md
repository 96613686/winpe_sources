# _configthreadlocale_0

- ea: `0x14002ae1a`
- end: `0x14002ae20`
- name: `_configthreadlocale_0`
- size: `6`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400257f0`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_configthreadlocale` at `0x14002ae1a`

## pseudocode

```c
// attributes: thunk
int __cdecl configthreadlocale_0(int Flag)
{
  return _configthreadlocale(Flag);
}

```

## disassembly

```asm
0x14002ae1a  jmp     cs:__imp__configthreadlocale
```
