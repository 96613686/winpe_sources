# __vcrt_getptd

- ea: `0x180011058`
- end: `0x180011071`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd48`
- `0x18000fda4`
- `0x18000fe00`
- `0x18001088c`
- `0x1800108cc`
- `0x180010928`
- `0x180010940`
- `0x180010958`
- `0x180010978`
- `0x180010998`
- `0x180010a24`
- `0x180010b00`
- `0x180010b88`
- `0x180010bec`
- `0x180011b5c`
- `0x18001205c`
- `0x18001259c`
- `0x180012804`
- `0x180012d80`
- `0x180012fb4`
- `0x18001326c`
- `0x1800134f0`
- `0x1800136f0`
- `0x180013acc`
- `0x180013b68`
- `0x180013ba0`
- `0x180013d30`

## callees

- `0x18000ecf4`
- `0x180011058`
- `0x180011078`

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
0x180011058  sub     rsp, 28h
0x18001105c  call    __vcrt_getptd_noexit
0x180011061  test    rax, rax
0x180011064  jz      short loc_18001106B
0x180011066  add     rsp, 28h
0x18001106a  retn
0x18001106b  call    abort
```
