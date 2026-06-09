# PplAllocateFromLookasideListProcessor

- ea: `0x1400094e0`
- end: `0x14000951b`
- name: `PplAllocateFromLookasideListProcessor`
- size: `59`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400010f0`
- `0x140001d70`
- `0x140004250`
- `0x140012b50`
- `0x140020484`

## callees

- `0x1400094e0`
- `0x14000f3dc`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140009508`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140009508`

## pseudocode

```c
PVOID __fastcall PplAllocateFromLookasideListProcessor(__int64 a1, int a2)
{
  __int64 v2; // rbx

  v2 = a1 + ((unsigned __int64)(unsigned int)(a2 + 1) << 7);
  if ( !*(_BYTE *)(v2 + 176) )
    PplpLazyInitializeLookasideList(a1, v2 + 64);
  return ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v2 + 64));
}

```

## disassembly

```asm
0x1400094e0  push    rbx
0x1400094e2  sub     rsp, 20h
0x1400094e6  lea     ebx, [rdx+1]
0x1400094e9  shl     rbx, 7
0x1400094ed  add     rbx, rcx
0x1400094f0  movzx   eax, byte ptr [rbx+0B0h]
0x1400094f7  test    al, al
0x1400094f9  jnz     short loc_140009504
0x1400094fb  lea     rdx, [rbx+40h]
0x1400094ff  call    PplpLazyInitializeLookasideList
0x140009504  lea     rcx, [rbx+40h]; Lookaside
0x140009508  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000950f  nop     dword ptr [rax+rax+00h]
0x140009514  add     rsp, 20h
0x140009518  pop     rbx
0x140009519  retn
```
