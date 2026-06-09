# wistd::unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____::_unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____

- ea: `0x180006900`
- end: `0x180006925`
- name: `wistd::unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____::_unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bf33`

## callees

- `0x180002190`
- `0x180006900`

## pseudocode

```c
void __fastcall wistd::unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____::_unique_ptr__lambda_30c9907fbca49ad387fb0dd3a4426001__wistd::default_delete__lambda_30c9907fbca49ad387fb0dd3a4426001_____(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x180006900  sub     rsp, 28h
0x180006904  mov     rax, [rcx]
0x180006907  mov     qword ptr [rcx], 0
0x18000690e  test    rax, rax
0x180006911  jz      short loc_180006920
0x180006913  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180006918  mov     rcx, rax; void *
0x18000691b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006920  add     rsp, 28h
0x180006924  retn
```
