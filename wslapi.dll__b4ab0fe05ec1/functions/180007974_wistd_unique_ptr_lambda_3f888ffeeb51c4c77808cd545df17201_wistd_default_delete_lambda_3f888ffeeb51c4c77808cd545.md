# wistd::unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____::_unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____

- ea: `0x180007974`
- end: `0x180007999`
- name: `wistd::unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____::_unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c041`

## callees

- `0x180002190`
- `0x180007974`

## pseudocode

```c
void __fastcall wistd::unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____::_unique_ptr__lambda_3f888ffeeb51c4c77808cd545df17201__wistd::default_delete__lambda_3f888ffeeb51c4c77808cd545df17201_____(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x28);
}

```

## disassembly

```asm
0x180007974  sub     rsp, 28h
0x180007978  mov     rax, [rcx]
0x18000797b  mov     qword ptr [rcx], 0
0x180007982  test    rax, rax
0x180007985  jz      short loc_180007994
0x180007987  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000798c  mov     rcx, rax; void *
0x18000798f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007994  add     rsp, 28h
0x180007998  retn
```
