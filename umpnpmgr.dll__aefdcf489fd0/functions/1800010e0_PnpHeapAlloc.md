# PnpHeapAlloc

- ea: `0x1800010e0`
- end: `0x180001102`
- name: `PnpHeapAlloc`
- size: `34`
- prototype: `PVOID __fastcall(SIZE_T)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001190`
- `0x1800024d0`
- `0x180008d20`
- `0x18000aba0`
- `0x18000ff5c`
- `0x180011ab8`
- `0x1800126cc`
- `0x180012ffc`
- `0x180013b90`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x1800010e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800010fb`

## pseudocode

```c
PVOID __fastcall PnpHeapAlloc(SIZE_T a1)
{
  if ( a1 <= 0xF42400 )
    return RtlAllocateHeap(PnpHeapHandle, 8u, a1);
  else
    return 0;
}

```

## disassembly

```asm
0x1800010e0  cmp     rcx, 0F42400h
0x1800010e7  jbe     short loc_1800010EC
0x1800010e9  xor     eax, eax
0x1800010eb  retn
0x1800010ec  mov     r8, rcx
0x1800010ef  mov     edx, 8
0x1800010f4  mov     rcx, cs:PnpHeapHandle
0x1800010fb  jmp     cs:__imp_RtlAllocateHeap
```
