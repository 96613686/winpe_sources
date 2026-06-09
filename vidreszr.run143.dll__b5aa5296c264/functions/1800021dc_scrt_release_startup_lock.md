# __scrt_release_startup_lock

- ea: `0x1800021dc`
- end: `0x180002200`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001aa8`
- `0x180001ba8`

## callees

- `0x1800021dc`
- `0x180002598`

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
0x1800021dc  push    rbx
0x1800021de  sub     rsp, 20h
0x1800021e2  mov     bl, cl
0x1800021e4  call    __scrt_is_ucrt_dll_in_use
0x1800021e9  test    eax, eax
0x1800021eb  jz      short loc_1800021FA
0x1800021ed  test    bl, bl
0x1800021ef  jnz     short loc_1800021FA
0x1800021f1  xor     eax, eax
0x1800021f3  xchg    rax, cs:__scrt_native_startup_lock
0x1800021fa  add     rsp, 20h
0x1800021fe  pop     rbx
0x1800021ff  retn
```
