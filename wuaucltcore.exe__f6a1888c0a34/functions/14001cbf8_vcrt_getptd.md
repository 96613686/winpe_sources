# __vcrt_getptd

- ea: `0x14001cbf8`
- end: `0x14001cc11`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x14001b958`
- `0x14001b9b4`
- `0x14001ba10`
- `0x14001c49c`
- `0x14001c4dc`
- `0x14001c538`
- `0x14001c550`
- `0x14001c568`
- `0x14001c588`
- `0x14001c5a8`
- `0x14001c634`
- `0x14001c710`
- `0x14001c798`
- `0x14001c7fc`
- `0x14001c868`
- `0x14001c880`
- `0x14001d6fc`
- `0x14001dbfc`
- `0x14001e13c`
- `0x14001e3a4`
- `0x14001e920`
- `0x14001eb54`
- `0x14001ee0c`
- `0x14001f090`
- `0x14001f290`
- `0x14001f66c`
- `0x14001f708`
- `0x14001f740`
- `0x14001f8d0`

## callees

- `0x14001a9f4`
- `0x14001cbf8`
- `0x14001cc18`

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
0x14001cbf8  sub     rsp, 28h
0x14001cbfc  call    __vcrt_getptd_noexit
0x14001cc01  test    rax, rax
0x14001cc04  jz      short loc_14001CC0B
0x14001cc06  add     rsp, 28h
0x14001cc0a  retn
0x14001cc0b  call    abort
```
