# ATL::CAcl::CAce::IsObjectAce(void)

- ea: `0x140007160`
- end: `0x140007163`
- name: `?IsObjectAce@CAce@CAcl@ATL@@UEBA_NXZ`
- size: `3`
- prototype: `bool __fastcall(ATL::CAcl::CAce *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
bool __fastcall ATL::CAcl::CAce::IsObjectAce(ATL::CAcl::CAce *this)
{
  return 0;
}

```

## disassembly

```asm
0x140007160  xor     al, al
0x140007162  retn
```
