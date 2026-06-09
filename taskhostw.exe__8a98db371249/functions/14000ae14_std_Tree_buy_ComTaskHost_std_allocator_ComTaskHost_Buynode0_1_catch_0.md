# _std::_Tree_buy_ComTaskHost___std::allocator_ComTaskHost_____::_Buynode0_::_1_::catch$0

- ea: `0x14000ae14`
- end: `0x14000ae35`
- name: `_std::_Tree_buy_ComTaskHost___std::allocator_ComTaskHost_____::_Buynode0_::_1_::catch$0`
- size: `33`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14000894c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000ae25`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ae25`

## pseudocode

```c
void __fastcall __noreturn std::_Tree_buy_ComTaskHost___std::allocator_ComTaskHost_____::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
  throw;
}

```

## disassembly

```asm
0x14000ae14  mov     [rsp+arg_8], rdx
0x14000ae19  push    rbp
0x14000ae1a  sub     rsp, 20h
0x14000ae1e  mov     rbp, rdx
0x14000ae21  mov     rcx, [rbp+38h]
0x14000ae25  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ae2b  xor     edx, edx; pThrowInfo
0x14000ae2d  xor     ecx, ecx; pExceptionObject
0x14000ae2f  call    _CxxThrowException_0
```
