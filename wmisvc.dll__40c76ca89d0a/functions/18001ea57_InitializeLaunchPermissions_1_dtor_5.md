# _InitializeLaunchPermissions_::_1_::dtor$5

- ea: `0x18001ea57`
- end: `0x18001ea65`
- name: `_InitializeLaunchPermissions_::_1_::dtor$5`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18001ea5e`

## pseudocode

```c
void __fastcall InitializeLaunchPermissions_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  CNtAcl::~CNtAcl((CNtAcl *)(a2 + 176));
}

```

## disassembly

```asm
0x18001ea57  lea     rcx, [rdx+0B0h]
0x18001ea5e  jmp     cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
```
