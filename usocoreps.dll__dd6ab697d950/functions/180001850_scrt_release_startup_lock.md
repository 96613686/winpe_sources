# __scrt_release_startup_lock

- ea: `0x180001850`
- end: `0x180001874`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011e8`
- `0x1800012e8`

## callees

- `0x180001850`
- `0x180001db4`

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
0x180001850  push    rbx
0x180001852  sub     rsp, 20h
0x180001856  mov     bl, cl
0x180001858  call    __scrt_is_ucrt_dll_in_use
0x18000185d  test    eax, eax
0x18000185f  jz      short loc_18000186E
0x180001861  test    bl, bl
0x180001863  jnz     short loc_18000186E
0x180001865  xor     eax, eax
0x180001867  xchg    rax, cs:__scrt_native_startup_lock
0x18000186e  add     rsp, 20h
0x180001872  pop     rbx
0x180001873  retn
```
