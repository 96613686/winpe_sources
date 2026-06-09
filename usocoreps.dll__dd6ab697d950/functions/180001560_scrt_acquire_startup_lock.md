# __scrt_acquire_startup_lock

- ea: `0x180001560`
- end: `0x180001599`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e8`
- `0x1800012e8`

## callees

- `0x180001560`
- `0x180001db4`

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
0x180001560  sub     rsp, 28h
0x180001564  call    __scrt_is_ucrt_dll_in_use
0x180001569  test    eax, eax
0x18000156b  jz      short loc_18000158E
0x18000156d  mov     rax, gs:30h
0x180001576  mov     rcx, [rax+8]
0x18000157a  jmp     short loc_180001581
0x18000157c  cmp     rcx, rax
0x18000157f  jz      short loc_180001595
0x180001581  xor     eax, eax
0x180001583  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x18000158c  jnz     short loc_18000157C
0x18000158e  xor     al, al
0x180001590  add     rsp, 28h
0x180001594  retn
0x180001595  mov     al, 1
0x180001597  jmp     short loc_180001590
```
