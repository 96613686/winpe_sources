# CNtAcl::`default constructor closure'(void)

- ea: `0x180011940`
- end: `0x18001194c`
- name: `??_FCNtAcl@@QEAAXXZ`
- size: `12`
- prototype: `void __fastcall(CNtAcl *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x180011945`

## pseudocode

```c
void __fastcall CNtAcl::`default constructor closure'(CNtAcl *this)
{
  CNtAcl::CNtAcl(this, 0x80u);
}

```

## disassembly

```asm
0x180011940  mov     edx, 80h
0x180011945  jmp     cs:__imp_??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
```
