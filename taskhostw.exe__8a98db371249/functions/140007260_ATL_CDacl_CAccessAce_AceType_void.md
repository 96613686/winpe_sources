# ATL::CDacl::CAccessAce::AceType(void)

- ea: `0x140007260`
- end: `0x14000726b`
- name: `?AceType@CAccessAce@CDacl@ATL@@UEBAEXZ`
- size: `11`
- prototype: `bool __fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
bool __fastcall ATL::CDacl::CAccessAce::AceType(ATL::CDacl::CAccessAce *this)
{
  return *((_BYTE *)this + 144) == 0;
}

```

## disassembly

```asm
0x140007260  cmp     byte ptr [rcx+90h], 0
0x140007267  setz    al
0x14000726a  retn
```
