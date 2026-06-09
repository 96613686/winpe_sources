# _OpenPolicyRootRegKey_::_1_::catch$5

- ea: `0x18001d572`
- end: `0x18001d59c`
- name: `_OpenPolicyRootRegKey_::_1_::catch$5`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001af84`

## pseudocode

```c
__int64 __fastcall OpenPolicyRootRegKey_::_1_::catch_5(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)a2,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001d572  mov     [rsp+arg_8], rdx
0x18001d577  push    rbp
0x18001d578  sub     rsp, 30h
0x18001d57c  mov     rbp, rdx
0x18001d57f  mov     rcx, [rbp+68h]; this
0x18001d583  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001d588  mov     [rbp+30h], eax
0x18001d58b  mov     rax, 0
0x18001d595  add     rsp, 30h
0x18001d599  pop     rbp
0x18001d59a  retn
```
