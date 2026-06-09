# __scrt_acquire_startup_lock

- ea: `0x18000156c`
- end: `0x1800015a5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011f8`
- `0x1800012f8`

## callees

- `0x18000156c`
- `0x180001da4`

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
0x18000156c  sub     rsp, 28h
0x180001570  call    __scrt_is_ucrt_dll_in_use
0x180001575  test    eax, eax
0x180001577  jz      short loc_18000159A
0x180001579  mov     rax, gs:30h
0x180001582  mov     rcx, [rax+8]
0x180001586  jmp     short loc_18000158D
0x180001588  cmp     rcx, rax
0x18000158b  jz      short loc_1800015A1
0x18000158d  xor     eax, eax
0x18000158f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001598  jnz     short loc_180001588
0x18000159a  xor     al, al
0x18000159c  add     rsp, 28h
0x1800015a0  retn
0x1800015a1  mov     al, 1
0x1800015a3  jmp     short loc_18000159C
```
