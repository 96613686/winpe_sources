# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x14000339c`
- end: `0x1400033a6`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400021dc`
- `0x1400028bc`
- `0x140003fac`
- `0x140006fe8`
- `0x140007258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000339f`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x14000339c  mov     rcx, [rcx]
0x14000339f  jmp     cs:__imp_free
```
