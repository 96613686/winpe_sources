# MatchByGuid

- ea: `0x14000b910`
- end: `0x14000b937`
- name: `MatchByGuid`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000b91e`
- `ntoskrnl!RtlCompareMemory` at `0x14000b91e`

## pseudocode

```c
bool __fastcall MatchByGuid(__int64 a1, const void *a2)
{
  return RtlCompareMemory((const void *)(a1 + 20), a2, 0x10u) == 16;
}

```

## disassembly

```asm
0x14000b910  sub     rsp, 28h
0x14000b914  add     rcx, 14h; Source1
0x14000b918  mov     r8d, 10h; Length
0x14000b91e  call    cs:__imp_RtlCompareMemory
0x14000b925  nop     dword ptr [rax+rax+00h]
0x14000b92a  cmp     rax, 10h
0x14000b92e  setz    al
0x14000b931  add     rsp, 28h
0x14000b935  retn
```
