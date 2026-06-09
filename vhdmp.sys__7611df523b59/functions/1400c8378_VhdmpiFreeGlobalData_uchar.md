# VhdmpiFreeGlobalData(uchar)

- ea: `0x1400c8378`
- end: `0x1400c842a`
- name: `?VhdmpiFreeGlobalData@@YAXE@Z`
- size: `178`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400cab70`
- `0x1400ee2ac`

## callees

- `0x1400c8378`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400c83a7`
- `ntoskrnl!IoFreeMdl` at `0x1400c83a7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400c83f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400c83f7`
- `ntoskrnl!MmUnlockPages` at `0x1400c8394`
- `ntoskrnl!MmUnlockPages` at `0x1400c8394`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400c83cd`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400c83cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8412`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8412`

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
0x1400c8378  mov     [rsp+arg_0], rbx
0x1400c837d  push    rdi
0x1400c837e  sub     rsp, 20h
0x1400c8382  mov     al, cl
0x1400c8384  mov     rcx, cs:VhdZeroPageMdl; MemoryDescriptorList
0x1400c838b  test    rcx, rcx
0x1400c838e  jz      short loc_1400C83BE
0x1400c8390  test    al, al
0x1400c8392  jz      short loc_1400C83A0
0x1400c8394  call    cs:__imp_MmUnlockPages
0x1400c839b  nop     dword ptr [rax+rax+00h]
0x1400c83a0  mov     rcx, cs:VhdZeroPageMdl; Mdl
0x1400c83a7  call    cs:__imp_IoFreeMdl
0x1400c83ae  nop     dword ptr [rax+rax+00h]
0x1400c83b3  mov     cs:VhdZeroPageMdl, 0
0x1400c83be  cmp     cs:VhdPerProcData, 0
0x1400c83c6  jz      short loc_1400C841E
0x1400c83c8  mov     ecx, 0FFFFh; GroupNumber
0x1400c83cd  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400c83d4  nop     dword ptr [rax+rax+00h]
0x1400c83d9  xor     ebx, ebx
0x1400c83db  mov     edi, eax
0x1400c83dd  test    eax, eax
0x1400c83df  jz      short loc_1400C8409
0x1400c83e1  mov     rcx, cs:VhdPerProcData
0x1400c83e8  lea     rdx, [rbx+rbx*2]
0x1400c83ec  shl     rdx, 6
0x1400c83f0  add     rcx, 40h ; '@'
0x1400c83f4  add     rcx, rdx; Lookaside
0x1400c83f7  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400c83fe  nop     dword ptr [rax+rax+00h]
0x1400c8403  inc     ebx
0x1400c8405  cmp     ebx, edi
0x1400c8407  jb      short loc_1400C83E1
0x1400c8409  mov     rcx, cs:VhdPerProcData; P
0x1400c8410  xor     edx, edx; Tag
0x1400c8412  call    cs:__imp_ExFreePoolWithTag
0x1400c8419  nop     dword ptr [rax+rax+00h]
0x1400c841e  mov     rbx, [rsp+28h+arg_0]
0x1400c8423  add     rsp, 20h
0x1400c8427  pop     rdi
0x1400c8428  retn
```
