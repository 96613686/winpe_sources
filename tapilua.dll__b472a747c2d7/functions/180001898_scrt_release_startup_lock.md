# __scrt_release_startup_lock

- ea: `0x180001898`
- end: `0x1800018bc`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001158`
- `0x180001258`

## callees

- `0x180001898`
- `0x180001c54`

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
0x180001898  push    rbx
0x18000189a  sub     rsp, 20h
0x18000189e  mov     bl, cl
0x1800018a0  call    __scrt_is_ucrt_dll_in_use
0x1800018a5  test    eax, eax
0x1800018a7  jz      short loc_1800018B6
0x1800018a9  test    bl, bl
0x1800018ab  jnz     short loc_1800018B6
0x1800018ad  xor     eax, eax
0x1800018af  xchg    rax, cs:__scrt_native_startup_lock
0x1800018b6  add     rsp, 20h
0x1800018ba  pop     rbx
0x1800018bb  retn
```
