# utl::unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>::~unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>(void)

- ea: `0x140004ab4`
- end: `0x140004aca`
- name: `??1?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001ccb9`

## callees

- `0x1400033bc`
- `0x140004ab4`

## pseudocode

```c
void __fastcall utl::unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>::~unique_ptr<_TOKEN_USER,tlx::generic_delete<_TOKEN_USER,tlx::operator_delete_deallocate>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140004ab4  sub     rsp, 28h
0x140004ab8  mov     rcx, [rcx]; Block
0x140004abb  test    rcx, rcx
0x140004abe  jz      short loc_140004AC5
0x140004ac0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004ac5  add     rsp, 28h
0x140004ac9  retn
```
