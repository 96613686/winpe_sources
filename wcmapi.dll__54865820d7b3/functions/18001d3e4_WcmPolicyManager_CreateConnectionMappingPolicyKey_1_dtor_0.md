# _WcmPolicyManager::CreateConnectionMappingPolicyKey_::_1_::dtor$0

- ea: `0x18001d3e4`
- end: `0x18001d404`
- name: `_WcmPolicyManager::CreateConnectionMappingPolicyKey_::_1_::dtor$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180008ab4`

## pseudocode

```c
void __fastcall WcmPolicyManager::CreateConnectionMappingPolicyKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x18001d3e4  push    rbp
0x18001d3e6  sub     rsp, 20h
0x18001d3ea  mov     rbp, rdx
0x18001d3ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001d3f4  mov     rcx, [rbp+68h]; Block
0x18001d3f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d3fd  add     rsp, 20h
0x18001d401  pop     rbp
0x18001d402  retn
```
