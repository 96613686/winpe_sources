# wistd::unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____::_unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____

- ea: `0x1800070c0`
- end: `0x1800070e5`
- name: `wistd::unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____::_unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bf8d`
- `0x18000bfb1`

## callees

- `0x180002190`
- `0x1800070c0`

## pseudocode

```c
void __fastcall wistd::unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____::_unique_ptr__lambda_9e18749395fb31002599b6510f759e9a__wistd::default_delete__lambda_9e18749395fb31002599b6510f759e9a_____(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x10);
}

```

## disassembly

```asm
0x1800070c0  sub     rsp, 28h
0x1800070c4  mov     rax, [rcx]
0x1800070c7  mov     qword ptr [rcx], 0
0x1800070ce  test    rax, rax
0x1800070d1  jz      short loc_1800070E0
0x1800070d3  mov     edx, 10h; struct std::nothrow_t *
0x1800070d8  mov     rcx, rax; void *
0x1800070db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800070e0  add     rsp, 28h
0x1800070e4  retn
```
