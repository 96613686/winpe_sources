# wistd::unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____::_unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____

- ea: `0x180007094`
- end: `0x1800070b9`
- name: `wistd::unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____::_unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bf7b`

## callees

- `0x180002190`
- `0x180007094`

## pseudocode

```c
void __fastcall wistd::unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____::_unique_ptr__lambda_4e29967ac626feff930376ab7442d83b__wistd::default_delete__lambda_4e29967ac626feff930376ab7442d83b_____(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x180007094  sub     rsp, 28h
0x180007098  mov     rax, [rcx]
0x18000709b  mov     qword ptr [rcx], 0
0x1800070a2  test    rax, rax
0x1800070a5  jz      short loc_1800070B4
0x1800070a7  mov     edx, 18h; struct std::nothrow_t *
0x1800070ac  mov     rcx, rax; void *
0x1800070af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800070b4  add     rsp, 28h
0x1800070b8  retn
```
