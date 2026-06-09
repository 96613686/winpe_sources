# _RTC_Initialize

- ea: `0x180001894`
- end: `0x1800018cf`
- name: `_RTC_Initialize`
- size: `59`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001894`
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
0x180001894  mov     [rsp+arg_0], rbx
0x180001899  push    rdi
0x18000189a  sub     rsp, 20h
0x18000189e  lea     rbx, __rtc_izz
0x1800018a5  lea     rdi, __rtc_izz
0x1800018ac  jmp     short loc_1800018BF
0x1800018ae  mov     rax, [rbx]
0x1800018b1  test    rax, rax
0x1800018b4  jz      short loc_1800018BB
0x1800018b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018bb  add     rbx, 8
0x1800018bf  cmp     rbx, rdi
0x1800018c2  jb      short loc_1800018AE
0x1800018c4  mov     rbx, [rsp+28h+arg_0]
0x1800018c9  add     rsp, 20h
0x1800018cd  pop     rdi
0x1800018ce  retn
```
