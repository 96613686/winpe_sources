# MatchByProcessId

- ea: `0x14000b8a0`
- end: `0x14000b8a9`
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
0x14000b8a0  mov     eax, [rdx]
0x14000b8a2  cmp     [rcx+38h], eax
0x14000b8a5  setz    al
0x14000b8a8  retn
```
