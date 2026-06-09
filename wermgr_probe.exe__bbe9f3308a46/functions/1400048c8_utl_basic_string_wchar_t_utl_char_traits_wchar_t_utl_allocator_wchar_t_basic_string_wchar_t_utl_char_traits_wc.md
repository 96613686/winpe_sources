# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)

- ea: `0x1400048c8`
- end: `0x1400048e9`
- name: `??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001cb75`
- `0x14001cb87`
- `0x14001cb99`
- `0x14001cbab`
- `0x14001cbbd`
- `0x14001cbcf`
- `0x14001cc4d`
- `0x14001cd01`
- `0x14001ceb3`
- `0x14001cf55`

## callees

- `0x140003224`
- `0x1400048c8`

## pseudocode

```c
void __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        void **a1)
{
  if ( *a1 != a1 + 2 )
    operator delete(*a1, (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x1400048c8  sub     rsp, 28h
0x1400048cc  lea     rax, [rcx+10h]
0x1400048d0  cmp     [rcx], rax
0x1400048d3  jz      short loc_1400048E4
0x1400048d5  mov     rcx, [rcx]; void *
0x1400048d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400048df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400048e4  add     rsp, 28h
0x1400048e8  retn
```
