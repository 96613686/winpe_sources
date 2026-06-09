# wistd::unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____::_unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____

- ea: `0x1800079a0`
- end: `0x1800079c5`
- name: `wistd::unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____::_unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c053`

## callees

- `0x180002190`
- `0x1800079a0`

## pseudocode

```c
void __fastcall wistd::unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____::_unique_ptr__lambda_d4251f4926f6295bfcc87f753188dddd__wistd::default_delete__lambda_d4251f4926f6295bfcc87f753188dddd_____(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x40);
}

```

## disassembly

```asm
0x1800079a0  sub     rsp, 28h
0x1800079a4  mov     rax, [rcx]
0x1800079a7  mov     qword ptr [rcx], 0
0x1800079ae  test    rax, rax
0x1800079b1  jz      short loc_1800079C0
0x1800079b3  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x1800079b8  mov     rcx, rax; void *
0x1800079bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800079c0  add     rsp, 28h
0x1800079c4  retn
```
