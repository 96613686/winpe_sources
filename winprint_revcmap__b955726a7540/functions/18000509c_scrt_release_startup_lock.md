# __scrt_release_startup_lock

- ea: `0x18000509c`
- end: `0x1800050c0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004968`
- `0x180004a68`

## callees

- `0x18000509c`
- `0x18000544c`

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
0x18000509c  push    rbx
0x18000509e  sub     rsp, 20h
0x1800050a2  mov     bl, cl
0x1800050a4  call    __scrt_is_ucrt_dll_in_use
0x1800050a9  test    eax, eax
0x1800050ab  jz      short loc_1800050BA
0x1800050ad  test    bl, bl
0x1800050af  jnz     short loc_1800050BA
0x1800050b1  xor     eax, eax
0x1800050b3  xchg    rax, cs:__scrt_native_startup_lock
0x1800050ba  add     rsp, 20h
0x1800050be  pop     rbx
0x1800050bf  retn
```
