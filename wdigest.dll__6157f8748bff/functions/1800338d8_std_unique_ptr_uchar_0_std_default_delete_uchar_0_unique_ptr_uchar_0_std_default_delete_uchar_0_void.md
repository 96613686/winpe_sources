# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x1800338d8`
- end: `0x1800338ee`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180033bb0`

## callees

- `0x180012c50`
- `0x1800338d8`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800338d8  sub     rsp, 28h
0x1800338dc  mov     rcx, [rcx]; void *
0x1800338df  test    rcx, rcx
0x1800338e2  jz      short loc_1800338E9
0x1800338e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800338e9  add     rsp, 28h
0x1800338ed  retn
```
