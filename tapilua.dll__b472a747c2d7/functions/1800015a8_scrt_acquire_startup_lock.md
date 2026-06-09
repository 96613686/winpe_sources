# __scrt_acquire_startup_lock

- ea: `0x1800015a8`
- end: `0x1800015e1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001158`
- `0x180001258`

## callees

- `0x1800015a8`
- `0x180001c54`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange64(&_scrt_native_startup_lock, (signed __int64)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800015a8  sub     rsp, 28h
0x1800015ac  call    __scrt_is_ucrt_dll_in_use
0x1800015b1  test    eax, eax
0x1800015b3  jz      short loc_1800015D6
0x1800015b5  mov     rax, gs:30h
0x1800015be  mov     rcx, [rax+8]
0x1800015c2  jmp     short loc_1800015C9
0x1800015c4  cmp     rcx, rax
0x1800015c7  jz      short loc_1800015DD
0x1800015c9  xor     eax, eax
0x1800015cb  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015d4  jnz     short loc_1800015C4
0x1800015d6  xor     al, al
0x1800015d8  add     rsp, 28h
0x1800015dc  retn
0x1800015dd  mov     al, 1
0x1800015df  jmp     short loc_1800015D8
```
