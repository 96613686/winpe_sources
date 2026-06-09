# __scrt_acquire_startup_lock

- ea: `0x180001eec`
- end: `0x180001f25`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001aa8`
- `0x180001ba8`

## callees

- `0x180001eec`
- `0x180002598`

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
0x180001eec  sub     rsp, 28h
0x180001ef0  call    __scrt_is_ucrt_dll_in_use
0x180001ef5  test    eax, eax
0x180001ef7  jz      short loc_180001F1A
0x180001ef9  mov     rax, gs:30h
0x180001f02  mov     rcx, [rax+8]
0x180001f06  jmp     short loc_180001F0D
0x180001f08  cmp     rcx, rax
0x180001f0b  jz      short loc_180001F21
0x180001f0d  xor     eax, eax
0x180001f0f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001f18  jnz     short loc_180001F08
0x180001f1a  xor     al, al
0x180001f1c  add     rsp, 28h
0x180001f20  retn
0x180001f21  mov     al, 1
0x180001f23  jmp     short loc_180001F1C
```
