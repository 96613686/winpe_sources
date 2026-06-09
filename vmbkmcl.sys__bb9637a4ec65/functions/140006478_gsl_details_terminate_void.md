# gsl::details::terminate(void)

- ea: `0x140006478`
- end: `0x14000648e`
- name: `?terminate@details@gsl@@YAXXZ`
- size: `22`
- prototype: `void __fastcall(gsl::details *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400042b0`
- `0x140005fe0`
- `0x14000618c`
- `0x1400062e0`

## callees

- `0x140011ed0`

## pseudocode

```c
void __fastcall gsl::details::terminate(gsl::details *this)
{
  `gsl::details::get_terminate_handler'::`2'::handler(this);
}

```

## disassembly

```asm
0x140006478  sub     rsp, 28h
0x14000647c  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x140006483  call    _guard_dispatch_icall
0x140006488  add     rsp, 28h
0x14000648c  retn
```
