# VmbPacketFree

- ea: `0x14000a6d0`
- end: `0x14000a708`
- name: `VmbPacketFree`
- size: `56`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000a380`

## callees

- `0x14000a6d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a6f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a6f6`

## pseudocode

```c
void __fastcall VmbPacketFree(_DWORD *Entry)
{
  if ( Entry[6] != 1 )
    __fastfail(5u);
  Entry[6] = 6;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 2) + 320LL), Entry);
}

```

## disassembly

```asm
0x14000a6d0  sub     rsp, 28h
0x14000a6d4  cmp     dword ptr [rcx+18h], 1
0x14000a6d8  mov     rdx, rcx; Entry
0x14000a6db  jz      short loc_14000A6E4
0x14000a6dd  mov     ecx, 5
0x14000a6e2  int     29h; Win8: RtlFailFast(ecx)
0x14000a6e4  mov     dword ptr [rcx+18h], 6
0x14000a6eb  mov     rcx, [rcx+10h]
0x14000a6ef  add     rcx, 140h; Lookaside
0x14000a6f6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000a6fd  nop     dword ptr [rax+rax+00h]
0x14000a702  add     rsp, 28h
0x14000a706  retn
```
