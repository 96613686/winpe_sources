# __scrt_acquire_startup_lock

- ea: `0x180002aac`
- end: `0x180002ae5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002668`
- `0x180002768`

## callees

- `0x180002aac`
- `0x180003158`

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
0x180002aac  sub     rsp, 28h
0x180002ab0  call    __scrt_is_ucrt_dll_in_use
0x180002ab5  test    eax, eax
0x180002ab7  jz      short loc_180002ADA
0x180002ab9  mov     rax, gs:30h
0x180002ac2  mov     rcx, [rax+8]
0x180002ac6  jmp     short loc_180002ACD
0x180002ac8  cmp     rcx, rax
0x180002acb  jz      short loc_180002AE1
0x180002acd  xor     eax, eax
0x180002acf  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180002ad8  jnz     short loc_180002AC8
0x180002ada  xor     al, al
0x180002adc  add     rsp, 28h
0x180002ae0  retn
0x180002ae1  mov     al, 1
0x180002ae3  jmp     short loc_180002ADC
```
