# ReadWS_File

- ea: `0x18003df30`
- end: `0x18003df5f`
- name: `ReadWS_File`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003df49`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003df49`

## pseudocode

```c
__int64 __fastcall ReadWS_File(FILE **a1, void *a2, size_t a3)
{
  return fread(a2, a3, 1u, *a1) != 1 ? 0xFFFFFF9A : 0;
}

```

## disassembly

```asm
0x18003df30  sub     rsp, 28h
0x18003df34  mov     r9, [rcx]; Stream
0x18003df37  mov     rax, r8
0x18003df3a  mov     r10, rdx
0x18003df3d  mov     r8d, 1; ElementCount
0x18003df43  mov     rdx, rax; ElementSize
0x18003df46  mov     rcx, r10; Buffer
0x18003df49  call    cs:__imp_fread
0x18003df4f  dec     rax
0x18003df52  neg     rax
0x18003df55  sbb     eax, eax
0x18003df57  and     eax, 0FFFFFF9Ah
0x18003df5a  add     rsp, 28h
0x18003df5e  retn
```
