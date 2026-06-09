# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180013f40`
- end: `0x180013f53`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `19`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180011e80`
- `0x1800126ec`
- `0x180014950`

## import_xrefs

- `msvcrt!free` at `0x180013f47`
- `msvcrt!free` at `0x180013f47`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180013f40  sub     rsp, 28h
0x180013f44  mov     rcx, [rcx]; Block
0x180013f47  call    cs:__imp_free
0x180013f4d  nop
0x180013f4e  add     rsp, 28h
0x180013f52  retn
```
