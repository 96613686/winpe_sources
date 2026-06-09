# __scrt_acquire_startup_lock

- ea: `0x180005888`
- end: `0x1800058c1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005418`
- `0x180005518`

## callees

- `0x180005888`
- `0x180005f10`

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
0x180005888  sub     rsp, 28h
0x18000588c  call    __scrt_is_ucrt_dll_in_use
0x180005891  test    eax, eax
0x180005893  jz      short loc_1800058B6
0x180005895  mov     rax, gs:30h
0x18000589e  mov     rcx, [rax+8]
0x1800058a2  jmp     short loc_1800058A9
0x1800058a4  cmp     rcx, rax
0x1800058a7  jz      short loc_1800058BD
0x1800058a9  xor     eax, eax
0x1800058ab  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800058b4  jnz     short loc_1800058A4
0x1800058b6  xor     al, al
0x1800058b8  add     rsp, 28h
0x1800058bc  retn
0x1800058bd  mov     al, 1
0x1800058bf  jmp     short loc_1800058B8
```
