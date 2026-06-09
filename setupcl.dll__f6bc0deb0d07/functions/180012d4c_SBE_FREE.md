# SBE_FREE

- ea: `0x180012d4c`
- end: `0x180012d6b`
- name: `SBE_FREE`
- size: `31`
- prototype: `__int64 (*__fastcall(__int64))(void)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800129a0`
- `0x180012b30`
- `0x180012dfc`
- `0x180013100`
- `0x180013134`
- `0x1800135b0`
- `0x180013b10`
- `0x1800144b0`
- `0x1800145d0`
- `0x180014784`

## callees

- `0x180012d4c`
- `0x180018010`

## pseudocode

```c
__int64 (*__fastcall SBE_FREE(__int64 a1))(void)
{
  __int64 (*result)(void); // rax

  if ( a1 )
  {
    result = FreeRoutine;
    if ( FreeRoutine )
      return (__int64 (*)(void))FreeRoutine();
  }
  return result;
}

```

## disassembly

```asm
0x180012d4c  sub     rsp, 28h
0x180012d50  test    rcx, rcx
0x180012d53  jz      short loc_180012D66
0x180012d55  mov     rax, cs:FreeRoutine
0x180012d5c  test    rax, rax
0x180012d5f  jz      short loc_180012D66
0x180012d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d66  add     rsp, 28h
0x180012d6a  retn
```
