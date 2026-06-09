# FileProvInitializeCompression

- ea: `0x14002f134`
- end: `0x14002f1fb`
- name: `FileProvInitializeCompression`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ef08`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f1e9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f1e9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f179`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f1b6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f179`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f1b6`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002f13d`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002f13d`

## pseudocode

```c
void FileProvInitializeCompression()
{
  FileProvNumberProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  ExInitializeNPagedLookasideList(&FileProvCompressContextLookaside, 0, 0, 0x200u, 0x130u, 0x44527066u, 0);
  ExInitializeNPagedLookasideList(
    &FileProvCompressWorkitemsLookaside,
    0,
    0,
    0x200u,
    136LL * (unsigned int)FileProvNumberProcessors,
    0x44527066u,
    0);
  ExInitializePagedLookasideList(&FileProvCompressReadLookaside, 0, 0, 0, 0x40000u, 0x44527066u, 0);
}

```

## disassembly

```asm
0x14002f134  sub     rsp, 48h
0x14002f138  mov     ecx, 0FFFFh; GroupNumber
0x14002f13d  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14002f144  nop     dword ptr [rax+rax+00h]
0x14002f149  mov     cs:FileProvNumberProcessors, eax
0x14002f14f  mov     r9d, 200h; Flags
0x14002f155  xor     eax, eax
0x14002f157  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14002f15e  mov     [rsp+48h+Depth], ax; Depth
0x14002f163  xor     r8d, r8d; Free
0x14002f166  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f16e  xor     edx, edx; Allocate
0x14002f170  mov     [rsp+48h+Size], 130h; Size
0x14002f179  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002f180  nop     dword ptr [rax+rax+00h]
0x14002f185  mov     eax, cs:FileProvNumberProcessors
0x14002f18b  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14002f192  imul    rax, 88h
0x14002f199  xor     edx, edx; Allocate
0x14002f19b  mov     r9d, 200h; Flags
0x14002f1a1  mov     [rsp+48h+Depth], dx; Depth
0x14002f1a6  xor     r8d, r8d; Free
0x14002f1a9  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f1b1  mov     [rsp+48h+Size], rax; Size
0x14002f1b6  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002f1bd  nop     dword ptr [rax+rax+00h]
0x14002f1c2  xor     eax, eax
0x14002f1c4  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14002f1cb  mov     [rsp+48h+Depth], ax; Depth
0x14002f1d0  xor     r9d, r9d; Flags
0x14002f1d3  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f1db  xor     r8d, r8d; Free
0x14002f1de  xor     edx, edx; Allocate
0x14002f1e0  mov     [rsp+48h+Size], 40000h; Size
0x14002f1e9  call    cs:__imp_ExInitializePagedLookasideList
0x14002f1f0  nop     dword ptr [rax+rax+00h]
0x14002f1f5  add     rsp, 48h
0x14002f1f9  retn
```
