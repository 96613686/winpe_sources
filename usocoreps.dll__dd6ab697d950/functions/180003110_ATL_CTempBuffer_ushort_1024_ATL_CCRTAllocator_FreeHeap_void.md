# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180003110`
- end: `0x18000311a`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002228`
- `0x18000271c`
- `0x180003978`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003113`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180003110  mov     rcx, [rcx]
0x180003113  jmp     cs:__imp_free
```
