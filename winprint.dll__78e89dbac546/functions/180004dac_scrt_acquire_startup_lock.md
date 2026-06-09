# __scrt_acquire_startup_lock

- ea: `0x180004dac`
- end: `0x180004de5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004968`
- `0x180004a68`

## callees

- `0x180004dac`
- `0x18000544c`

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
0x180004dac  sub     rsp, 28h
0x180004db0  call    __scrt_is_ucrt_dll_in_use
0x180004db5  test    eax, eax
0x180004db7  jz      short loc_180004DDA
0x180004db9  mov     rax, gs:30h
0x180004dc2  mov     rcx, [rax+8]
0x180004dc6  jmp     short loc_180004DCD
0x180004dc8  cmp     rcx, rax
0x180004dcb  jz      short loc_180004DE1
0x180004dcd  xor     eax, eax
0x180004dcf  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180004dd8  jnz     short loc_180004DC8
0x180004dda  xor     al, al
0x180004ddc  add     rsp, 28h
0x180004de0  retn
0x180004de1  mov     al, 1
0x180004de3  jmp     short loc_180004DDC
```
