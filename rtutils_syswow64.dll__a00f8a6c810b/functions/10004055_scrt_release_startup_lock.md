# ___scrt_release_startup_lock

- ea: `0x10004055`
- end: `0x10004074`
- name: `___scrt_release_startup_lock`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100038db`
- `0x100039eb`

## callees

- `0x10004055`
- `0x100044c5`

## pseudocode

```c
__int32 __cdecl __scrt_release_startup_lock(char a1)
{
  __int32 result; // eax

  result = __scrt_is_ucrt_dll_in_use();
  if ( result )
  {
    if ( !a1 )
      return _InterlockedExchange(&__scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x10004055  mov     edi, edi
0x10004057  push    ebp
0x10004058  mov     ebp, esp
0x1000405a  call    ___scrt_is_ucrt_dll_in_use
0x1000405f  test    eax, eax
0x10004061  jz      short loc_10004072
0x10004063  cmp     [ebp+arg_0], 0
0x10004067  jnz     short loc_10004072
0x10004069  xor     eax, eax
0x1000406b  mov     ecx, offset ___scrt_native_startup_lock
0x10004070  xchg    eax, [ecx]
0x10004072  pop     ebp
0x10004073  retn
```
