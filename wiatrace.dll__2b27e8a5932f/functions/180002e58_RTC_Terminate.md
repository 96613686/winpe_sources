# _RTC_Terminate

- ea: `0x180002e58`
- end: `0x180002e93`
- name: `_RTC_Terminate`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002768`

## callees

- `0x180002e58`
- `0x180004010`

## pseudocode

```c
void __cdecl RTC_Terminate()
{
  void (**i)(void); // rbx

  for ( i = (void (**)(void))&_rtc_tzz; i < (void (**)(void))&_rtc_tzz; ++i )
  {
    if ( *i )
      (*i)();
  }
}

```

## disassembly

```asm
0x180002e58  mov     [rsp+arg_0], rbx
0x180002e5d  push    rdi
0x180002e5e  sub     rsp, 20h
0x180002e62  lea     rbx, __rtc_tzz
0x180002e69  lea     rdi, __rtc_tzz
0x180002e70  jmp     short loc_180002E83
0x180002e72  mov     rax, [rbx]
0x180002e75  test    rax, rax
0x180002e78  jz      short loc_180002E7F
0x180002e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7f  add     rbx, 8
0x180002e83  cmp     rbx, rdi
0x180002e86  jb      short loc_180002E72
0x180002e88  mov     rbx, [rsp+28h+arg_0]
0x180002e8d  add     rsp, 20h
0x180002e91  pop     rdi
0x180002e92  retn
```
