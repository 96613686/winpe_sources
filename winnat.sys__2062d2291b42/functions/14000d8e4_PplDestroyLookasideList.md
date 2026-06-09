# PplDestroyLookasideList

- ea: `0x14000d8e4`
- end: `0x14000d94c`
- name: `PplDestroyLookasideList`
- size: `104`
- prototype: `__int64 __fastcall(PVOID P, ULONG Tag)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000daf0`
- `0x140019fdc`
- `0x14001b34c`

## callees

- `0x14000d8e4`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14000d919`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14000d919`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d92f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d92f`

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
0x14000d8e4  test    rcx, rcx
0x14000d8e7  jz      short locret_14000D94A
0x14000d8e9  mov     [rsp+arg_0], rbx
0x14000d8ee  mov     [rsp+arg_8], rsi
0x14000d8f3  push    rdi
0x14000d8f4  sub     rsp, 20h
0x14000d8f8  mov     edi, [rcx]
0x14000d8fa  mov     esi, edx
0x14000d8fc  mov     rbx, rcx
0x14000d8ff  jmp     short loc_14000D925
0x14000d901  mov     ecx, edi
0x14000d903  shl     rcx, 7
0x14000d907  mov     al, [rcx+rbx+0B0h]
0x14000d90e  test    al, al
0x14000d910  jz      short loc_14000D925
0x14000d912  add     rcx, 40h ; '@'
0x14000d916  add     rcx, rbx; Lookaside
0x14000d919  call    cs:__imp_ExDeleteLookasideListEx
0x14000d920  nop     dword ptr [rax+rax+00h]
0x14000d925  sub     edi, 1
0x14000d928  jns     short loc_14000D901
0x14000d92a  mov     edx, esi; Tag
0x14000d92c  mov     rcx, rbx; P
0x14000d92f  call    cs:__imp_ExFreePoolWithTag
0x14000d936  nop     dword ptr [rax+rax+00h]
0x14000d93b  mov     rbx, [rsp+28h+arg_0]
0x14000d940  mov     rsi, [rsp+28h+arg_8]
0x14000d945  add     rsp, 20h
0x14000d949  pop     rdi
0x14000d94a  retn
```
