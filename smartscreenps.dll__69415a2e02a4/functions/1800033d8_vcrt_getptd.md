# __vcrt_getptd

- ea: `0x1800033d8`
- end: `0x1800033f1`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180002068`
- `0x1800020c4`
- `0x180002120`
- `0x180002b1c`
- `0x180002b5c`
- `0x180002bb8`
- `0x180002bd0`
- `0x180002be8`
- `0x180002c08`
- `0x180002c28`
- `0x180002ca0`
- `0x180002e10`
- `0x180002e90`
- `0x180002ef8`
- `0x180003e48`
- `0x180004304`
- `0x180004820`
- `0x180004a60`
- `0x180004f94`
- `0x1800051a8`
- `0x180005434`
- `0x180005670`
- `0x180005890`
- `0x180005c8c`
- `0x180005d18`
- `0x180005d50`
- `0x180005ef4`

## callees

- `0x1800033d8`
- `0x1800033f8`
- `0x18000693e`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort_0();
  return result;
}

```

## disassembly

```asm
0x1800033d8  sub     rsp, 28h
0x1800033dc  call    __vcrt_getptd_noexit
0x1800033e1  test    rax, rax
0x1800033e4  jz      short loc_1800033EB
0x1800033e6  add     rsp, 28h
0x1800033ea  retn
0x1800033eb  call    abort_0
```
