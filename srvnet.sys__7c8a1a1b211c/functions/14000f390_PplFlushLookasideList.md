# PplFlushLookasideList

- ea: `0x14000f390`
- end: `0x14000f3d6`
- name: `PplFlushLookasideList`
- size: `70`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140002060`
- `0x1400022d0`
- `0x140047ab0`

## callees

- `0x14000f390`

## import_xrefs

- `ntoskrnl!ExFlushLookasideListEx` at `0x14000f3b9`
- `ntoskrnl!ExFlushLookasideListEx` at `0x14000f3b9`

## pseudocode

```c
void __fastcall PplFlushLookasideList(unsigned int *a1)
{
  unsigned int v1; // ebx
  unsigned __int64 v3; // rdx

  v1 = *a1;
  while ( (--v1 & 0x80000000) == 0 )
  {
    v3 = (unsigned __int64)v1 << 7;
    if ( *((_BYTE *)a1 + v3 + 176) )
      ExFlushLookasideListEx((PLOOKASIDE_LIST_EX)((char *)a1 + v3 + 64));
  }
}

```

## disassembly

```asm
0x14000f390  mov     [rsp+arg_0], rbx
0x14000f395  push    rdi
0x14000f396  sub     rsp, 20h
0x14000f39a  mov     ebx, [rcx]
0x14000f39c  mov     rdi, rcx
0x14000f39f  jmp     short loc_14000F3C5
0x14000f3a1  mov     edx, ebx
0x14000f3a3  shl     rdx, 7
0x14000f3a7  mov     al, [rdx+rdi+0B0h]
0x14000f3ae  test    al, al
0x14000f3b0  jz      short loc_14000F3C5
0x14000f3b2  lea     rcx, [rdi+40h]
0x14000f3b6  add     rcx, rdx; Lookaside
0x14000f3b9  call    cs:__imp_ExFlushLookasideListEx
0x14000f3c0  nop     dword ptr [rax+rax+00h]
0x14000f3c5  sub     ebx, 1
0x14000f3c8  jns     short loc_14000F3A1
0x14000f3ca  mov     rbx, [rsp+28h+arg_0]
0x14000f3cf  add     rsp, 20h
0x14000f3d3  pop     rdi
0x14000f3d4  retn
```
