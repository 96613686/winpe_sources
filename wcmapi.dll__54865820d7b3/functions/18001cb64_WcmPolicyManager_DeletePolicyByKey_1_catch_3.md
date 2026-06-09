# _WcmPolicyManager::DeletePolicyByKey_::_1_::catch$3

- ea: `0x18001cb64`
- end: `0x18001cb89`
- name: `_WcmPolicyManager::DeletePolicyByKey_::_1_::catch$3`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall WcmPolicyManager::DeletePolicyByKey_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024322;
  return 0;
}

```

## disassembly

```asm
0x18001cb64  mov     [rsp+arg_8], rdx
0x18001cb69  push    rbp
0x18001cb6a  sub     rsp, 30h
0x18001cb6e  mov     rbp, rdx
0x18001cb71  mov     dword ptr [rbp+30h], 8007023Eh
0x18001cb78  mov     rax, 0
0x18001cb82  add     rsp, 30h
0x18001cb86  pop     rbp
0x18001cb87  retn
```
