# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180009288`
- end: `0x180009292`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008624`
- `0x18000a348`

## import_xrefs

- `msvcrt!free` at `0x18000928b`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180009288  mov     rcx, [rcx]
0x18000928b  jmp     cs:__imp_free
```
