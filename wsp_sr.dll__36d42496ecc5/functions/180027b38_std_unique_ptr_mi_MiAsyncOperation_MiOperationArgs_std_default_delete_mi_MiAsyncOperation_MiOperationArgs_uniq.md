# std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs,std::default_delete<mi::MiAsyncOperation::MiOperationArgs>>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs,std::default_delete<mi::MiAsyncOperation::MiOperationArgs>>(void)

- ea: `0x180027b38`
- end: `0x180027b4e`
- name: `??1?$unique_ptr@UMiOperationArgs@MiAsyncOperation@mi@@U?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027bbc`

## callees

- `0x180027b38`
- `0x180027f58`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()();
  return result;
}

```

## disassembly

```asm
0x180027b38  sub     rsp, 28h
0x180027b3c  mov     rdx, [rcx]
0x180027b3f  test    rdx, rdx
0x180027b42  jz      short loc_180027B49
0x180027b44  call    ??R?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@QEBAXPEAUMiOperationArgs@MiAsyncOperation@mi@@@Z; std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()(mi::MiAsyncOperation::MiOperationArgs *)
0x180027b49  add     rsp, 28h
0x180027b4d  retn
```
