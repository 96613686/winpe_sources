# ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180010f34`
- end: `0x180010f3e`
- name: `?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f804`
- `0x180011800`

## import_xrefs

- `msvcrt!free` at `0x180010f37`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180010f34  mov     rcx, [rcx]
0x180010f37  jmp     cs:__imp_free
```
