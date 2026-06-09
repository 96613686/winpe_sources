# std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs,std::default_delete<mi::MiAsyncOperation::MiOperationArgs>>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs,std::default_delete<mi::MiAsyncOperation::MiOperationArgs>>(void)

- ea: `0x180027eb4`
- end: `0x180027ecb`
- name: `??1?$unique_ptr@UMiOperationArgs@MiAsyncOperation@mi@@U?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@@std@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027f54`

## callees

- `0x180027eb4`
- `0x180028318`

## pseudocode

```c
void __fastcall std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>(
        mi::MiAsyncOperation::MiOperationArgs **a1)
{
  if ( *a1 )
    std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()((__int64)a1, *a1);
}

```

## disassembly

```asm
0x180027eb4  sub     rsp, 28h
0x180027eb8  mov     rdx, [rcx]
0x180027ebb  test    rdx, rdx
0x180027ebe  jz      short loc_180027EC5
0x180027ec0  call    ??R?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@QEBAXPEAUMiOperationArgs@MiAsyncOperation@mi@@@Z; std::default_delete<mi::MiAsyncOperation::MiOperationArgs>::operator()(mi::MiAsyncOperation::MiOperationArgs *)
0x180027ec5  add     rsp, 28h
0x180027ec9  retn
```
