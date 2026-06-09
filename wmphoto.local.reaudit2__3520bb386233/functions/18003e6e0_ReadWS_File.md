# ReadWS_File

- ea: `0x18003e6e0`
- end: `0x18003e716`
- name: `ReadWS_File`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003e6f9`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003e6f9`

## pseudocode

```c
__int64 __fastcall ReadWS_File(FILE **a1, void *a2, size_t a3)
{
  return fread(a2, a3, 1u, *a1) != 1 ? 0xFFFFFF9A : 0;
}

```

## disassembly

```asm
0x18003e6e0  sub     rsp, 28h
0x18003e6e4  mov     r9, [rcx]; Stream
0x18003e6e7  mov     rax, r8
0x18003e6ea  mov     r10, rdx
0x18003e6ed  mov     r8d, 1; ElementCount
0x18003e6f3  mov     rdx, rax; ElementSize
0x18003e6f6  mov     rcx, r10; Buffer
0x18003e6f9  call    cs:__imp_fread
0x18003e700  nop     dword ptr [rax+rax+00h]
0x18003e705  dec     rax
0x18003e708  neg     rax
0x18003e70b  sbb     eax, eax
0x18003e70d  and     eax, 0FFFFFF9Ah
0x18003e710  add     rsp, 28h
0x18003e714  retn
```
