# MatchByGuid

- ea: `0x14000b870`
- end: `0x14000b897`
- name: `MatchByGuid`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000b87e`
- `ntoskrnl!RtlCompareMemory` at `0x14000b87e`

## pseudocode

```c
bool __fastcall MatchByGuid(__int64 a1, const void *a2)
{
  return RtlCompareMemory((const void *)(a1 + 20), a2, 0x10u) == 16;
}

```

## disassembly

```asm
0x14000b870  sub     rsp, 28h
0x14000b874  add     rcx, 14h; Source1
0x14000b878  mov     r8d, 10h; Length
0x14000b87e  call    cs:__imp_RtlCompareMemory
0x14000b885  nop     dword ptr [rax+rax+00h]
0x14000b88a  cmp     rax, 10h
0x14000b88e  setz    al
0x14000b891  add     rsp, 28h
0x14000b895  retn
```
