# _RTC_Initialize

- ea: `0x180002e14`
- end: `0x180002e4f`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002668`

## callees

- `0x180002e14`
- `0x180004010`

## pseudocode

```c
void __cdecl RTC_Initialize()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_izz; i < (void (**)(void))&_rtc_izz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x180002e14  mov     [rsp+arg_0], rbx
0x180002e19  push    rdi
0x180002e1a  sub     rsp, 20h
0x180002e1e  lea     rbx, __rtc_izz
0x180002e25  lea     rdi, __rtc_izz
0x180002e2c  jmp     short loc_180002E3F
0x180002e2e  mov     rax, [rbx]
0x180002e31  test    rax, rax
0x180002e34  jz      short loc_180002E3B
0x180002e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3b  add     rbx, 8
0x180002e3f  cmp     rbx, rdi
0x180002e42  jb      short loc_180002E2E
0x180002e44  mov     rbx, [rsp+28h+arg_0]
0x180002e49  add     rsp, 20h
0x180002e4d  pop     rdi
0x180002e4e  retn
```
