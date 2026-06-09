# std::unique_ptr<wchar_t [0],std::default_delete<wchar_t [0]>>::~unique_ptr<wchar_t [0],std::default_delete<wchar_t [0]>>(void)

- ea: `0x180004ca0`
- end: `0x180004cb6`
- name: `??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000dc98`
- `0x18000dcce`

## callees

- `0x180001794`
- `0x180004ca0`

## pseudocode

```c
void __fastcall std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180004ca0  sub     rsp, 28h
0x180004ca4  mov     rcx, [rcx]; Block
0x180004ca7  test    rcx, rcx
0x180004caa  jz      short loc_180004CB1
0x180004cac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004cb1  add     rsp, 28h
0x180004cb5  retn
```
