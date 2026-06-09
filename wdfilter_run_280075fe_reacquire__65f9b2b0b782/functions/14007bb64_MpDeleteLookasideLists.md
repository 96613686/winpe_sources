# MpDeleteLookasideLists

- ea: `0x14007bb64`
- end: `0x14007bca4`
- name: `MpDeleteLookasideLists`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14007bca4`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14007bbc4`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14007bbde`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14007bbc4`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14007bbde`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bb76`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bb90`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bbaa`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bbf8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc12`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc2c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc46`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc60`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc7a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bb76`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bb90`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bbaa`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bbf8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc12`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc2c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc46`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc60`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc7a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007bc98`

## pseudocode

```c
void MpDeleteLookasideLists()
{
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1536));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 896));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1024));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 1152));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 1408));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1664));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1792));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2112));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1280));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2240));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 4224));
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 4352));
}

```

## disassembly

```asm
0x14007bb64  sub     rsp, 28h
0x14007bb68  mov     rcx, cs:MpData
0x14007bb6f  add     rcx, 600h; Lookaside
0x14007bb76  call    cs:__imp_ExDeletePagedLookasideList
0x14007bb7d  nop     dword ptr [rax+rax+00h]
0x14007bb82  mov     rcx, cs:MpData
0x14007bb89  add     rcx, 380h; Lookaside
0x14007bb90  call    cs:__imp_ExDeletePagedLookasideList
0x14007bb97  nop     dword ptr [rax+rax+00h]
0x14007bb9c  mov     rcx, cs:MpData
0x14007bba3  add     rcx, 400h; Lookaside
0x14007bbaa  call    cs:__imp_ExDeletePagedLookasideList
0x14007bbb1  nop     dword ptr [rax+rax+00h]
0x14007bbb6  mov     rcx, cs:MpData
0x14007bbbd  add     rcx, 480h; Lookaside
0x14007bbc4  call    cs:__imp_ExDeleteNPagedLookasideList
0x14007bbcb  nop     dword ptr [rax+rax+00h]
0x14007bbd0  mov     rcx, cs:MpData
0x14007bbd7  add     rcx, 580h; Lookaside
0x14007bbde  call    cs:__imp_ExDeleteNPagedLookasideList
0x14007bbe5  nop     dword ptr [rax+rax+00h]
0x14007bbea  mov     rcx, cs:MpData
0x14007bbf1  add     rcx, 680h; Lookaside
0x14007bbf8  call    cs:__imp_ExDeletePagedLookasideList
0x14007bbff  nop     dword ptr [rax+rax+00h]
0x14007bc04  mov     rcx, cs:MpData
0x14007bc0b  add     rcx, 700h; Lookaside
0x14007bc12  call    cs:__imp_ExDeletePagedLookasideList
0x14007bc19  nop     dword ptr [rax+rax+00h]
0x14007bc1e  mov     rcx, cs:MpData
0x14007bc25  add     rcx, 840h; Lookaside
0x14007bc2c  call    cs:__imp_ExDeletePagedLookasideList
0x14007bc33  nop     dword ptr [rax+rax+00h]
0x14007bc38  mov     rcx, cs:MpData
0x14007bc3f  add     rcx, 500h; Lookaside
0x14007bc46  call    cs:__imp_ExDeletePagedLookasideList
0x14007bc4d  nop     dword ptr [rax+rax+00h]
0x14007bc52  mov     rcx, cs:MpData
0x14007bc59  add     rcx, 8C0h; Lookaside
0x14007bc60  call    cs:__imp_ExDeletePagedLookasideList
0x14007bc67  nop     dword ptr [rax+rax+00h]
0x14007bc6c  mov     rcx, cs:MpData
0x14007bc73  add     rcx, 1080h; Lookaside
0x14007bc7a  call    cs:__imp_ExDeletePagedLookasideList
0x14007bc81  nop     dword ptr [rax+rax+00h]
0x14007bc86  mov     rcx, cs:MpData
0x14007bc8d  add     rcx, 1100h
0x14007bc94  add     rsp, 28h
0x14007bc98  jmp     cs:__imp_ExDeletePagedLookasideList
```
