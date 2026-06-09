# std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()(mi::MiAsyncOperation::MiOperationArgs *)

- ea: `0x180027f58`
- end: `0x180027f80`
- name: `??R?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@QEBAXPEAUMiOperationArgs@MiAsyncOperation@mi@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, mi::MiAsyncOperation::MiOperationArgs *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027b38`

## callees

- `0x180002510`
- `0x180027cdc`
- `0x180027f58`

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
0x180027f58  test    rdx, rdx
0x180027f5b  jz      short locret_180027F7F
0x180027f5d  push    rbx
0x180027f5e  sub     rsp, 20h
0x180027f62  mov     rcx, rdx; this
0x180027f65  mov     rbx, rdx
0x180027f68  call    ??1MiOperationArgs@MiAsyncOperation@mi@@QEAA@XZ; mi::MiAsyncOperation::MiOperationArgs::~MiOperationArgs(void)
0x180027f6d  mov     edx, 1D0h; unsigned __int64
0x180027f72  mov     rcx, rbx; void *
0x180027f75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027f7a  add     rsp, 20h
0x180027f7e  pop     rbx
0x180027f7f  retn
```
