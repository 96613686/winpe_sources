# VhdmpiFreeGlobalData(uchar)

- ea: `0x1400c8368`
- end: `0x1400c841a`
- name: `?VhdmpiFreeGlobalData@@YAXE@Z`
- size: `178`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400cab60`
- `0x1400ee2ac`

## callees

- `0x1400c8368`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400c8397`
- `ntoskrnl!IoFreeMdl` at `0x1400c8397`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400c83e7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400c83e7`
- `ntoskrnl!MmUnlockPages` at `0x1400c8384`
- `ntoskrnl!MmUnlockPages` at `0x1400c8384`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400c83bd`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400c83bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8402`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8402`

## pseudocode

```c
void __fastcall VhdmpiFreeGlobalData(char a1)
{
  __int64 v1; // rbx
  ULONG MaximumProcessorCount; // edi

  if ( VhdZeroPageMdl )
  {
    if ( a1 )
      MmUnlockPages(VhdZeroPageMdl);
    IoFreeMdl(VhdZeroPageMdl);
    VhdZeroPageMdl = 0;
  }
  if ( VhdPerProcData )
  {
    v1 = 0;
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    if ( MaximumProcessorCount )
    {
      do
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)VhdPerProcData + 192 * v1 + 64));
        v1 = (unsigned int)(v1 + 1);
      }
      while ( (unsigned int)v1 < MaximumProcessorCount );
    }
    ExFreePoolWithTag(VhdPerProcData, 0);
  }
}

```

## disassembly

```asm
0x1400c8368  mov     [rsp+arg_0], rbx
0x1400c836d  push    rdi
0x1400c836e  sub     rsp, 20h
0x1400c8372  mov     al, cl
0x1400c8374  mov     rcx, cs:VhdZeroPageMdl; MemoryDescriptorList
0x1400c837b  test    rcx, rcx
0x1400c837e  jz      short loc_1400C83AE
0x1400c8380  test    al, al
0x1400c8382  jz      short loc_1400C8390
0x1400c8384  call    cs:__imp_MmUnlockPages
0x1400c838b  nop     dword ptr [rax+rax+00h]
0x1400c8390  mov     rcx, cs:VhdZeroPageMdl; Mdl
0x1400c8397  call    cs:__imp_IoFreeMdl
0x1400c839e  nop     dword ptr [rax+rax+00h]
0x1400c83a3  mov     cs:VhdZeroPageMdl, 0
0x1400c83ae  cmp     cs:VhdPerProcData, 0
0x1400c83b6  jz      short loc_1400C840E
0x1400c83b8  mov     ecx, 0FFFFh; GroupNumber
0x1400c83bd  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400c83c4  nop     dword ptr [rax+rax+00h]
0x1400c83c9  xor     ebx, ebx
0x1400c83cb  mov     edi, eax
0x1400c83cd  test    eax, eax
0x1400c83cf  jz      short loc_1400C83F9
0x1400c83d1  mov     rcx, cs:VhdPerProcData
0x1400c83d8  lea     rdx, [rbx+rbx*2]
0x1400c83dc  shl     rdx, 6
0x1400c83e0  add     rcx, 40h ; '@'
0x1400c83e4  add     rcx, rdx; Lookaside
0x1400c83e7  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400c83ee  nop     dword ptr [rax+rax+00h]
0x1400c83f3  inc     ebx
0x1400c83f5  cmp     ebx, edi
0x1400c83f7  jb      short loc_1400C83D1
0x1400c83f9  mov     rcx, cs:VhdPerProcData; P
0x1400c8400  xor     edx, edx; Tag
0x1400c8402  call    cs:__imp_ExFreePoolWithTag
0x1400c8409  nop     dword ptr [rax+rax+00h]
0x1400c840e  mov     rbx, [rsp+28h+arg_0]
0x1400c8413  add     rsp, 20h
0x1400c8417  pop     rdi
0x1400c8418  retn
```
