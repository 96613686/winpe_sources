# __vcrt_getptd

- ea: `0x180011f98`
- end: `0x180011fb1`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180011278`
- `0x180011914`
- `0x180011954`
- `0x1800119b0`
- `0x1800119c8`
- `0x1800119e0`
- `0x180011a00`
- `0x180011a20`
- `0x180011af0`
- `0x180011b78`
- `0x180011bdc`
- `0x180012608`
- `0x180012b48`
- `0x1800130c4`
- `0x180013370`
- `0x180013600`
- `0x1800139dc`
- `0x180013a78`
- `0x180013ab0`

## callees

- `0x180010238`
- `0x180011f98`
- `0x180011fb8`

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
0x180011f98  sub     rsp, 28h
0x180011f9c  call    __vcrt_getptd_noexit
0x180011fa1  test    rax, rax
0x180011fa4  jz      short loc_180011FAB
0x180011fa6  add     rsp, 28h
0x180011faa  retn
0x180011fab  call    abort
```
