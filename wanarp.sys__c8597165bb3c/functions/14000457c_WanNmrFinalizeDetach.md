# WanNmrFinalizeDetach

- ea: `0x14000457c`
- end: `0x14000459d`
- name: `WanNmrFinalizeDetach`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000d310`
- `0x14000d3e4`
- `0x14000e310`

## import_xrefs

- `NETIO!NmrProviderDetachClientComplete` at `0x14000458b`
- `NETIO!NmrProviderDetachClientComplete` at `0x14000458b`

## pseudocode

```c
void __fastcall WanNmrFinalizeDetach(__int64 a1)
{
  NmrProviderDetachClientComplete(*(HANDLE *)(*(_QWORD *)(a1 + 216) + 16LL));
}

```

## disassembly

```asm
0x14000457c  sub     rsp, 28h
0x140004580  mov     rcx, [rcx+0D8h]
0x140004587  mov     rcx, [rcx+10h]; NmrBindingHandle
0x14000458b  call    cs:__imp_NmrProviderDetachClientComplete
0x140004592  nop     dword ptr [rax+rax+00h]
0x140004597  add     rsp, 28h
0x14000459b  retn
```
