# std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>::~unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>(void)

- ea: `0x180032b8c`
- end: `0x180032bb5`
- name: `??1?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001c440`
- `0x18002cc5c`
- `0x180034cbc`
- `0x18004a61a`
- `0x18004af75`
- `0x18004af87`
- `0x18004af99`
- `0x18004b1fb`

## callees

- `0x180020828`
- `0x180032b8c`
- `0x180032e6c`

## pseudocode

```c
void __fastcall std::unique_ptr<CHANNEL_ENTRY>::~unique_ptr<CHANNEL_ENTRY>(CHANNEL_ENTRY **a1)
{
  CHANNEL_ENTRY *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CHANNEL_ENTRY::~CHANNEL_ENTRY(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0xC0);
  }
}

```

## disassembly

```asm
0x180032b8c  push    rbx
0x180032b8e  sub     rsp, 20h
0x180032b92  mov     rbx, [rcx]
0x180032b95  test    rbx, rbx
0x180032b98  jz      short loc_180032BAF
0x180032b9a  mov     rcx, rbx; this
0x180032b9d  call    ??1CHANNEL_ENTRY@@QEAA@XZ; CHANNEL_ENTRY::~CHANNEL_ENTRY(void)
0x180032ba2  mov     edx, 0C0h; struct std::nothrow_t *
0x180032ba7  mov     rcx, rbx; void *
0x180032baa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032baf  add     rsp, 20h
0x180032bb3  pop     rbx
0x180032bb4  retn
```
