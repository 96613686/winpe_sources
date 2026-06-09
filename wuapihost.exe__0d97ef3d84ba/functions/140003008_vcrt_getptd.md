# __vcrt_getptd

- ea: `0x140003008`
- end: `0x140003021`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x140002348`
- `0x1400029e4`
- `0x140002a24`
- `0x140002a80`
- `0x140002a98`
- `0x140002ab0`
- `0x140002ad0`
- `0x140002af0`
- `0x140002bc0`
- `0x140002c48`
- `0x140002cac`
- `0x140002d18`
- `0x140002d30`
- `0x140003624`
- `0x140003b64`
- `0x1400040e0`
- `0x14000438c`
- `0x140004670`
- `0x140004a4c`
- `0x140004ae8`
- `0x140004b20`

## callees

- `0x140003008`
- `0x140003028`
- `0x1400056be`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x140003008  sub     rsp, 28h
0x14000300c  call    __vcrt_getptd_noexit
0x140003011  test    rax, rax
0x140003014  jz      short loc_14000301B
0x140003016  add     rsp, 28h
0x14000301a  retn
0x14000301b  call    abort
```
