# utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)

- ea: `0x18000f6b0`
- end: `0x18000f6c6`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ff3c`
- `0x180012084`
- `0x180012d68`

## callees

- `0x180003038`
- `0x18000f6b0`

## pseudocode

```c
void __fastcall utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000f6b0  sub     rsp, 28h
0x18000f6b4  mov     rcx, [rcx]; Block
0x18000f6b7  test    rcx, rcx
0x18000f6ba  jz      short loc_18000F6C1
0x18000f6bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f6c1  add     rsp, 28h
0x18000f6c5  retn
```
