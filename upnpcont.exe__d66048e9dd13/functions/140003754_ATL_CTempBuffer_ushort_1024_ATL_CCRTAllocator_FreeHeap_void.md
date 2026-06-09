# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x140003754`
- end: `0x14000375e`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002424`
- `0x140004698`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003757`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x140003754  mov     rcx, [rcx]
0x140003757  jmp     cs:__imp_free
```
