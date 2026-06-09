# __vcrt_getptd

- ea: `0x180011f98`
- end: `0x180011fb1`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180010c88`
- `0x180010ce4`
- `0x180010d40`
- `0x1800117cc`
- `0x18001180c`
- `0x180011868`
- `0x180011880`
- `0x180011898`
- `0x1800118b8`
- `0x1800118d8`
- `0x180011964`
- `0x180011a40`
- `0x180011ac8`
- `0x180011b2c`
- `0x180012a9c`
- `0x180012f9c`
- `0x1800134dc`
- `0x180013744`
- `0x180013cc0`
- `0x180013ef4`
- `0x1800141ac`
- `0x180014430`
- `0x180014630`
- `0x180014a0c`
- `0x180014aa8`
- `0x180014ae0`
- `0x180014c70`

## callees

- `0x18000fc34`
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
