# _InitializeLaunchPermissions_::_1_::dtor$4

- ea: `0x18001ea43`
- end: `0x18001ea51`
- name: `_InitializeLaunchPermissions_::_1_::dtor$4`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001ea4a`

## pseudocode

```c
void __fastcall InitializeLaunchPermissions_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CNtSid::~CNtSid((CNtSid *)(a2 + 136));
}

```

## disassembly

```asm
0x18001ea43  lea     rcx, [rdx+88h]
0x18001ea4a  jmp     cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
```
