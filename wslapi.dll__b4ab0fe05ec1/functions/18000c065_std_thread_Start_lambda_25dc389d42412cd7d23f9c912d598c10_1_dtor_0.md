# _std::thread::_Start__lambda_25dc389d42412cd7d23f9c912d598c10____::_1_::dtor$0

- ea: `0x18000c065`
- end: `0x18000c071`
- name: `_std::thread::_Start__lambda_25dc389d42412cd7d23f9c912d598c10____::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800085ac`

## pseudocode

```c
__int64 __fastcall std::thread::_Start__lambda_25dc389d42412cd7d23f9c912d598c10____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______::_unique_ptr_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std::default_delete_std::tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______(a2 + 48);
}

```

## disassembly

```asm
0x18000c065  lea     rcx, [rdx+30h]
0x18000c06c  jmp     std__unique_ptr_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std__default_delete_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10__________unique_ptr_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10____std__default_delete_std__tuple__lambda_25dc389d42412cd7d23f9c912d598c10_______
```
