# MatchByProcessId

- ea: `0x14000b940`
- end: `0x14000b949`
- name: `MatchByProcessId`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
bool __fastcall MatchByProcessId(__int64 a1, _DWORD *a2)
{
  return *(_DWORD *)(a1 + 56) == *a2;
}

```

## disassembly

```asm
0x14000b940  mov     eax, [rdx]
0x14000b942  cmp     [rcx+38h], eax
0x14000b945  setz    al
0x14000b948  retn
```
