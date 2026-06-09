# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180011a14`
- end: `0x180011a1e`
- name: `?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fc70`
- `0x180010410`
- `0x180012508`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011a17`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180011a14  mov     rcx, [rcx]
0x180011a17  jmp     cs:__imp_free
```
