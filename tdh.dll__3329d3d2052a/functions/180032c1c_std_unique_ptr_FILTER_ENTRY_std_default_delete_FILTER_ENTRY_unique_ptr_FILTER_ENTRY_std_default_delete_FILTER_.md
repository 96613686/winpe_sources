# std::unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>>::~unique_ptr<FILTER_ENTRY,std::default_delete<FILTER_ENTRY>>(void)

- ea: `0x180032c1c`
- end: `0x180032c45`
- name: `??1?$unique_ptr@VFILTER_ENTRY@@U?$default_delete@VFILTER_ENTRY@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011b30`
- `0x18002cd04`
- `0x18003479c`
- `0x180036d30`
- `0x180039878`
- `0x18004a210`
- `0x18004af37`
- `0x18004af49`
- `0x18004b07a`
- `0x18004b08c`
- `0x18004b32f`
- `0x18004b681`

## callees

- `0x180020828`
- `0x180032c1c`
- `0x180033558`

## pseudocode

```c
void __fastcall std::unique_ptr<FILTER_ENTRY>::~unique_ptr<FILTER_ENTRY>(FILTER_ENTRY **a1)
{
  FILTER_ENTRY *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    FILTER_ENTRY::~FILTER_ENTRY(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0x98);
  }
}

```

## disassembly

```asm
0x180032c1c  push    rbx
0x180032c1e  sub     rsp, 20h
0x180032c22  mov     rbx, [rcx]
0x180032c25  test    rbx, rbx
0x180032c28  jz      short loc_180032C3F
0x180032c2a  mov     rcx, rbx; this
0x180032c2d  call    ??1FILTER_ENTRY@@QEAA@XZ; FILTER_ENTRY::~FILTER_ENTRY(void)
0x180032c32  mov     edx, 98h; struct std::nothrow_t *
0x180032c37  mov     rcx, rbx; void *
0x180032c3a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032c3f  add     rsp, 20h
0x180032c43  pop     rbx
0x180032c44  retn
```
