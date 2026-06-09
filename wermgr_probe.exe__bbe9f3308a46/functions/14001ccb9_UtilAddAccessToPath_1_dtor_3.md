# _UtilAddAccessToPath_::_1_::dtor$3

- ea: `0x14001ccb9`
- end: `0x14001ccc5`
- name: `_UtilAddAccessToPath_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004ab4`

## pseudocode

```c
void __fastcall UtilAddAccessToPath_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  utl::unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>::~unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>((void **)(a2 + 64));
}

```

## disassembly

```asm
0x14001ccb9  lea     rcx, [rdx+40h]
0x14001ccc0  jmp     ??1?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>::~unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>(void)
```
