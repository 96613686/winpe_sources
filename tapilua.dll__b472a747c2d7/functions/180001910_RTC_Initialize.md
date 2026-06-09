# _RTC_Initialize

- ea: `0x180001910`
- end: `0x18000194b`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001158`

## callees

- `0x180001910`
- `0x180006010`

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
0x180001910  mov     [rsp+arg_0], rbx
0x180001915  push    rdi
0x180001916  sub     rsp, 20h
0x18000191a  lea     rbx, __rtc_izz
0x180001921  lea     rdi, __rtc_izz
0x180001928  jmp     short loc_18000193B
0x18000192a  mov     rax, [rbx]
0x18000192d  test    rax, rax
0x180001930  jz      short loc_180001937
0x180001932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001937  add     rbx, 8
0x18000193b  cmp     rbx, rdi
0x18000193e  jb      short loc_18000192A
0x180001940  mov     rbx, [rsp+28h+arg_0]
0x180001945  add     rsp, 20h
0x180001949  pop     rdi
0x18000194a  retn
```
