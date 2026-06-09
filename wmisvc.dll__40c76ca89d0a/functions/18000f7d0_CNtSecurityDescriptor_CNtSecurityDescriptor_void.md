# CNtSecurityDescriptor::~CNtSecurityDescriptor(void)

- ea: `0x18000f7d0`
- end: `0x18000f7d6`
- name: `??1CNtSecurityDescriptor@@QEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(CNtSecurityDescriptor *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18000f7d0`

## pseudocode

```c
// attributes: thunk
void __fastcall CNtSecurityDescriptor::~CNtSecurityDescriptor(CNtSecurityDescriptor *this)
{
  __imp_??1CNtSecurityDescriptor@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x18000f7d0  jmp     cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ
```
