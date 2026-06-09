# __scrt_release_startup_lock

- ea: `0x180005b78`
- end: `0x180005b9c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005418`
- `0x180005518`

## callees

- `0x180005b78`
- `0x180005f10`

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
0x180005b78  push    rbx
0x180005b7a  sub     rsp, 20h
0x180005b7e  mov     bl, cl
0x180005b80  call    __scrt_is_ucrt_dll_in_use
0x180005b85  test    eax, eax
0x180005b87  jz      short loc_180005B96
0x180005b89  test    bl, bl
0x180005b8b  jnz     short loc_180005B96
0x180005b8d  xor     eax, eax
0x180005b8f  xchg    rax, cs:__scrt_native_startup_lock
0x180005b96  add     rsp, 20h
0x180005b9a  pop     rbx
0x180005b9b  retn
```
