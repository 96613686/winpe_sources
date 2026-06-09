# __scrt_release_startup_lock

- ea: `0x180002d9c`
- end: `0x180002dc0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002668`
- `0x180002768`

## callees

- `0x180002d9c`
- `0x180003158`

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
0x180002d9c  push    rbx
0x180002d9e  sub     rsp, 20h
0x180002da2  mov     bl, cl
0x180002da4  call    __scrt_is_ucrt_dll_in_use
0x180002da9  test    eax, eax
0x180002dab  jz      short loc_180002DBA
0x180002dad  test    bl, bl
0x180002daf  jnz     short loc_180002DBA
0x180002db1  xor     eax, eax
0x180002db3  xchg    rax, cs:__scrt_native_startup_lock
0x180002dba  add     rsp, 20h
0x180002dbe  pop     rbx
0x180002dbf  retn
```
