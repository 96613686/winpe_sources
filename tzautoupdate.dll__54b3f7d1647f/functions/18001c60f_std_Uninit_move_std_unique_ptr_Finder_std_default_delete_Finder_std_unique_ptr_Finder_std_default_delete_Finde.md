# _std::_Uninit_move_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______std::allocator_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______::_1_::catch$0

- ea: `0x18001c60f`
- end: `0x18001c655`
- name: `_std::_Uninit_move_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______std::allocator_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______::_1_::catch$0`
- size: `70`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002960`
- `0x18001c60f`
- `0x18001d010`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______std::allocator_std::unique_ptr_Finder_std::default_delete_Finder______std::unique_ptr_Finder_std::default_delete_Finder______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *i; // rbx

  for ( i = *(_QWORD **)(a2 + 72); i != *(_QWORD **)(a2 + 64); ++i )
  {
    if ( *i )
      (**(void (__fastcall ***)(_QWORD, __int64))*i)(*i, 1);
  }
  throw;
}

```

## disassembly

```asm
0x18001c60f  mov     [rsp+arg_8], rdx
0x18001c614  push    rbx
0x18001c615  push    rbp
0x18001c616  sub     rsp, 28h
0x18001c61a  mov     rbp, rdx
0x18001c61d  mov     rbx, [rbp+48h]
0x18001c621  jmp     short loc_18001C645
0x18001c623  cmp     qword ptr [rbx], 0
0x18001c627  jz      short loc_18001C641
0x18001c629  mov     rcx, [rbx]
0x18001c62c  test    rcx, rcx
0x18001c62f  jz      short loc_18001C641
0x18001c631  mov     rax, [rcx]
0x18001c634  mov     edx, 1
0x18001c639  mov     rax, [rax]
0x18001c63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c641  add     rbx, 8
0x18001c645  cmp     rbx, [rbp+40h]
0x18001c649  jnz     short loc_18001C623
0x18001c64b  xor     edx, edx; pThrowInfo
0x18001c64d  xor     ecx, ecx; pExceptionObject
0x18001c64f  call    _CxxThrowException_0
```
