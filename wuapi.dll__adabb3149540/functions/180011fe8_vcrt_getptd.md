# __vcrt_getptd

- ea: `0x180011fe8`
- end: `0x180012001`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180010cd8`
- `0x180010d34`
- `0x180010d90`
- `0x18001181c`
- `0x18001185c`
- `0x1800118b8`
- `0x1800118d0`
- `0x1800118e8`
- `0x180011908`
- `0x180011928`
- `0x1800119b4`
- `0x180011a90`
- `0x180011b18`
- `0x180011b7c`
- `0x180012aec`
- `0x180012fec`
- `0x18001352c`
- `0x180013794`
- `0x180013d10`
- `0x180013f44`
- `0x1800141fc`
- `0x180014480`
- `0x180014680`
- `0x180014a5c`
- `0x180014af8`
- `0x180014b30`
- `0x180014cc0`

## callees

- `0x18000fc84`
- `0x180011fe8`
- `0x180012008`

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
0x180011fe8  sub     rsp, 28h
0x180011fec  call    __vcrt_getptd_noexit
0x180011ff1  test    rax, rax
0x180011ff4  jz      short loc_180011FFB
0x180011ff6  add     rsp, 28h
0x180011ffa  retn
0x180011ffb  call    abort
```
