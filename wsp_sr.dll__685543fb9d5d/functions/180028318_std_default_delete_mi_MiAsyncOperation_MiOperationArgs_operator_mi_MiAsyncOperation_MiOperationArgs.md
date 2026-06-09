# std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()(mi::MiAsyncOperation::MiOperationArgs *)

- ea: `0x180028318`
- end: `0x180028341`
- name: `??R?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@QEBAXPEAUMiOperationArgs@MiAsyncOperation@mi@@@Z`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027eb4`

## callees

- `0x180002540`
- `0x180028078`
- `0x180028318`

## pseudocode

```c
void __fastcall std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()(
        __int64 a1,
        mi::MiAsyncOperation::MiOperationArgs *a2)
{
  if ( a2 )
  {
    mi::MiAsyncOperation::MiOperationArgs::~MiOperationArgs(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180028318  test    rdx, rdx
0x18002831b  jz      short locret_18002833F
0x18002831d  push    rbx
0x18002831e  sub     rsp, 20h
0x180028322  mov     rcx, rdx; this
0x180028325  mov     rbx, rdx
0x180028328  call    ??1MiOperationArgs@MiAsyncOperation@mi@@QEAA@XZ; mi::MiAsyncOperation::MiOperationArgs::~MiOperationArgs(void)
0x18002832d  mov     edx, 1D0h; unsigned __int64
0x180028332  mov     rcx, rbx; void *
0x180028335  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002833a  add     rsp, 20h
0x18002833e  pop     rbx
0x18002833f  retn
```
