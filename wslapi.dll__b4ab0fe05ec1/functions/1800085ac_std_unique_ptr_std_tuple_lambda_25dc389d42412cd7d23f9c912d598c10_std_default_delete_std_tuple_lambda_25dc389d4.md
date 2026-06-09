# std::unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______::_unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______

- ea: `0x1800085ac`
- end: `0x1800085c7`
- name: `std::unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______::_unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800082a0`
- `0x180008328`
- `0x18000c065`

## callees

- `0x180002190`
- `0x1800085ac`

## pseudocode

```c
void __fastcall std::unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______::_unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)8);
}

```

## disassembly

```asm
0x1800085ac  sub     rsp, 28h
0x1800085b0  mov     rcx, [rcx]; void *
0x1800085b3  test    rcx, rcx
0x1800085b6  jz      short loc_1800085C2
0x1800085b8  mov     edx, 8; struct std::nothrow_t *
0x1800085bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800085c2  add     rsp, 28h
0x1800085c6  retn
```
