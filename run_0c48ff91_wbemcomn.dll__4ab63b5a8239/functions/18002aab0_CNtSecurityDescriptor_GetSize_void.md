# CNtSecurityDescriptor::GetSize(void)

- ea: `0x18002aab0`
- end: `0x18002aac9`
- name: `?GetSize@CNtSecurityDescriptor@@QEAAKXZ`
- size: `25`
- prototype: `unsigned int __fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002aab0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18002aac2`

## pseudocode

```c
ULONG __fastcall CNtSecurityDescriptor::GetSize(PSECURITY_DESCRIPTOR *this)
{
  if ( !*this || *((_DWORD *)this + 2) )
    return 0;
  else
    return RtlLengthSecurityDescriptor(*this);
}

```

## disassembly

```asm
0x18002aab0  cmp     qword ptr [rcx], 0
0x18002aab4  jnz     short loc_18002AAB9
0x18002aab6  xor     eax, eax
0x18002aab8  retn
0x18002aab9  cmp     dword ptr [rcx+8], 0
0x18002aabd  jnz     short loc_18002AAB6
0x18002aabf  mov     rcx, [rcx]
0x18002aac2  jmp     cs:__imp_RtlLengthSecurityDescriptor
```
