# PplDestroyLookasideList

- ea: `0x14001b86c`
- end: `0x14001b8d4`
- name: `PplDestroyLookasideList`
- size: `104`
- prototype: `__int64 __fastcall(PVOID P, ULONG Tag)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140013a84`
- `0x140047a64`

## callees

- `0x14001b86c`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001b8a1`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001b8a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b8b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b8b7`

## pseudocode

```c
void __fastcall PplDestroyLookasideList(char *P, ULONG Tag)
{
  unsigned int v2; // edi
  unsigned __int64 v5; // rcx

  if ( P )
  {
    v2 = *(_DWORD *)P;
    while ( (--v2 & 0x80000000) == 0 )
    {
      v5 = (unsigned __int64)v2 << 7;
      if ( P[v5 + 176] )
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&P[v5 + 64]);
    }
    ExFreePoolWithTag(P, Tag);
  }
}

```

## disassembly

```asm
0x14001b86c  test    rcx, rcx
0x14001b86f  jz      short locret_14001B8D2
0x14001b871  mov     [rsp+arg_0], rbx
0x14001b876  mov     [rsp+arg_8], rsi
0x14001b87b  push    rdi
0x14001b87c  sub     rsp, 20h
0x14001b880  mov     edi, [rcx]
0x14001b882  mov     esi, edx
0x14001b884  mov     rbx, rcx
0x14001b887  jmp     short loc_14001B8AD
0x14001b889  mov     ecx, edi
0x14001b88b  shl     rcx, 7
0x14001b88f  mov     al, [rcx+rbx+0B0h]
0x14001b896  test    al, al
0x14001b898  jz      short loc_14001B8AD
0x14001b89a  add     rcx, 40h ; '@'
0x14001b89e  add     rcx, rbx; Lookaside
0x14001b8a1  call    cs:__imp_ExDeleteLookasideListEx
0x14001b8a8  nop     dword ptr [rax+rax+00h]
0x14001b8ad  sub     edi, 1
0x14001b8b0  jns     short loc_14001B889
0x14001b8b2  mov     edx, esi; Tag
0x14001b8b4  mov     rcx, rbx; P
0x14001b8b7  call    cs:__imp_ExFreePoolWithTag
0x14001b8be  nop     dword ptr [rax+rax+00h]
0x14001b8c3  mov     rbx, [rsp+28h+arg_0]
0x14001b8c8  mov     rsi, [rsp+28h+arg_8]
0x14001b8cd  add     rsp, 20h
0x14001b8d1  pop     rdi
0x14001b8d2  retn
```
