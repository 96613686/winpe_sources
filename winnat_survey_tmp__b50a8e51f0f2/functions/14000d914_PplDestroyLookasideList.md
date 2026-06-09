# PplDestroyLookasideList

- ea: `0x14000d914`
- end: `0x14000d97c`
- name: `PplDestroyLookasideList`
- size: `104`
- prototype: `__int64 __fastcall(PVOID P, ULONG Tag)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000db20`
- `0x140019afc`
- `0x14001ae6c`

## callees

- `0x14000d914`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14000d949`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14000d949`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d95f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d95f`

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
0x14000d914  test    rcx, rcx
0x14000d917  jz      short locret_14000D97A
0x14000d919  mov     [rsp+arg_0], rbx
0x14000d91e  mov     [rsp+arg_8], rsi
0x14000d923  push    rdi
0x14000d924  sub     rsp, 20h
0x14000d928  mov     edi, [rcx]
0x14000d92a  mov     esi, edx
0x14000d92c  mov     rbx, rcx
0x14000d92f  jmp     short loc_14000D955
0x14000d931  mov     ecx, edi
0x14000d933  shl     rcx, 7
0x14000d937  mov     al, [rcx+rbx+0B0h]
0x14000d93e  test    al, al
0x14000d940  jz      short loc_14000D955
0x14000d942  add     rcx, 40h ; '@'
0x14000d946  add     rcx, rbx; Lookaside
0x14000d949  call    cs:__imp_ExDeleteLookasideListEx
0x14000d950  nop     dword ptr [rax+rax+00h]
0x14000d955  sub     edi, 1
0x14000d958  jns     short loc_14000D931
0x14000d95a  mov     edx, esi; Tag
0x14000d95c  mov     rcx, rbx; P
0x14000d95f  call    cs:__imp_ExFreePoolWithTag
0x14000d966  nop     dword ptr [rax+rax+00h]
0x14000d96b  mov     rbx, [rsp+28h+arg_0]
0x14000d970  mov     rsi, [rsp+28h+arg_8]
0x14000d975  add     rsp, 20h
0x14000d979  pop     rdi
0x14000d97a  retn
```
