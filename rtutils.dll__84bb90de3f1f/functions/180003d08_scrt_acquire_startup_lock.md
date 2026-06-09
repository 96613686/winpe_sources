# __scrt_acquire_startup_lock

- ea: `0x180003d08`
- end: `0x180003d41`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003898`
- `0x180003998`

## callees

- `0x180003d08`
- `0x180004390`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( _scrt_is_ucrt_dll_in_use() )
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
0x180003d08  sub     rsp, 28h
0x180003d0c  call    __scrt_is_ucrt_dll_in_use
0x180003d11  test    eax, eax
0x180003d13  jz      short loc_180003D36
0x180003d15  mov     rax, gs:30h
0x180003d1e  mov     rcx, [rax+8]
0x180003d22  jmp     short loc_180003D29
0x180003d24  cmp     rcx, rax
0x180003d27  jz      short loc_180003D3D
0x180003d29  xor     eax, eax
0x180003d2b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180003d34  jnz     short loc_180003D24
0x180003d36  xor     al, al
0x180003d38  add     rsp, 28h
0x180003d3c  retn
0x180003d3d  mov     al, 1
0x180003d3f  jmp     short loc_180003D38
```
