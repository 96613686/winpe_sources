# WinHvpCleanupHypercallLookasideBuffer

- ea: `0x14001bfac`
- end: `0x14001c037`
- name: `WinHvpCleanupHypercallLookasideBuffer`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001c040`
- `0x14001e5ec`

## callees

- `0x14000b040`
- `0x14001bfac`
- `0x14001d8c8`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001bfd5`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001bfd5`

## pseudocode

```c
__int64 WinHvpCleanupHypercallLookasideBuffer()
{
  unsigned __int8 i; // bl
  __int64 result; // rax

  if ( WinHvpNodeToHypercallLookaside )
  {
    for ( i = 0; i < (unsigned int)WinHvpNodeCount; ++i )
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside + ((unsigned __int64)i << 7)));
    WinHvpFreePoolWithTag(WinHvpNodeToHypercallLookaside, 1282820183);
  }
  WinHvpNodeToHypercallLookaside = 0;
  result = WinHvpTeardownNodeInfo();
  if ( WinHvpSratInfo )
  {
    result = WinHvpFreePoolWithTag(WinHvpSratInfo, 1198934103);
    WinHvpSratInfo = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001bfac  push    rbx
0x14001bfae  sub     rsp, 20h
0x14001bfb2  cmp     cs:WinHvpNodeToHypercallLookaside, 0
0x14001bfba  jz      short loc_14001BFFF
0x14001bfbc  xor     bl, bl
0x14001bfbe  cmp     cs:WinHvpNodeCount, 0
0x14001bfc5  jbe     short loc_14001BFEE
0x14001bfc7  movzx   ecx, bl
0x14001bfca  shl     rcx, 7
0x14001bfce  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x14001bfd5  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001bfdc  nop     dword ptr [rax+rax+00h]
0x14001bfe1  inc     bl
0x14001bfe3  movzx   eax, bl
0x14001bfe6  cmp     eax, cs:WinHvpNodeCount
0x14001bfec  jb      short loc_14001BFC7
0x14001bfee  mov     rcx, cs:WinHvpNodeToHypercallLookaside
0x14001bff5  mov     edx, 4C764857h
0x14001bffa  call    WinHvpFreePoolWithTag
0x14001bfff  mov     cs:WinHvpNodeToHypercallLookaside, 0
0x14001c00a  call    WinHvpTeardownNodeInfo
0x14001c00f  mov     rcx, cs:WinHvpSratInfo
0x14001c016  test    rcx, rcx
0x14001c019  jz      short loc_14001C030
0x14001c01b  mov     edx, 47764857h
0x14001c020  call    WinHvpFreePoolWithTag
0x14001c025  mov     cs:WinHvpSratInfo, 0
0x14001c030  add     rsp, 20h
0x14001c034  pop     rbx
0x14001c035  retn
```
