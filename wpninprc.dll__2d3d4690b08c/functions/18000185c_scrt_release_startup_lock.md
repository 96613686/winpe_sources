# __scrt_release_startup_lock

- ea: `0x18000185c`
- end: `0x180001880`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011f8`
- `0x1800012f8`

## callees

- `0x18000185c`
- `0x180001da4`

## pseudocode

```c
__int64 __fastcall _scrt_release_startup_lock(char a1)
{
  __int64 result; // rax

  result = _scrt_is_ucrt_dll_in_use();
  if ( (_DWORD)result )
  {
    if ( !a1 )
      return _InterlockedExchange64(&_scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000185c  push    rbx
0x18000185e  sub     rsp, 20h
0x180001862  mov     bl, cl
0x180001864  call    __scrt_is_ucrt_dll_in_use
0x180001869  test    eax, eax
0x18000186b  jz      short loc_18000187A
0x18000186d  test    bl, bl
0x18000186f  jnz     short loc_18000187A
0x180001871  xor     eax, eax
0x180001873  xchg    rax, cs:__scrt_native_startup_lock
0x18000187a  add     rsp, 20h
0x18000187e  pop     rbx
0x18000187f  retn
```
