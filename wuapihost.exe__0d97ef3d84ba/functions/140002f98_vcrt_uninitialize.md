# __vcrt_uninitialize

- ea: `0x140002f98`
- end: `0x140002fb1`
- name: `__vcrt_uninitialize`
- size: `25`
- prototype: `__vcrt_bool __cdecl(__vcrt_bool Terminating)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400019b4`
- `0x140001b54`

## callees

- `0x140002f98`
- `0x14000314c`
- `0x140005308`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_uninitialize(__vcrt_bool Terminating)
{
  if ( !Terminating )
  {
    _vcrt_uninitialize_ptd();
    _vcrt_uninitialize_locks();
  }
  return 1;
}

```

## disassembly

```asm
0x140002f98  sub     rsp, 28h
0x140002f9c  test    cl, cl
0x140002f9e  jnz     short loc_140002FAA
0x140002fa0  call    __vcrt_uninitialize_ptd
0x140002fa5  call    __vcrt_uninitialize_locks
0x140002faa  mov     al, 1
0x140002fac  add     rsp, 28h
0x140002fb0  retn
```
