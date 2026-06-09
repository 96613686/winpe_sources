# utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)

- ea: `0x140004a14`
- end: `0x140004a2a`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001cc95`

## callees

- `0x140003224`
- `0x140004a14`

## pseudocode

```c
void __fastcall utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(
        void **a1,
        const struct std::nothrow_t *a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x140004a14  sub     rsp, 28h
0x140004a18  mov     rcx, [rcx]; void *
0x140004a1b  test    rcx, rcx
0x140004a1e  jz      short loc_140004A25
0x140004a20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004a25  add     rsp, 28h
0x140004a29  retn
```
