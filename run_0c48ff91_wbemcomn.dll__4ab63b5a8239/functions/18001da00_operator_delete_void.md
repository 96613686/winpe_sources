# operator delete(void *)

- ea: `0x18001da00`
- end: `0x18001da29`
- name: `??3@YAXPEAX@Z`
- size: `41`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002dba0`
- `0x18002dbd0`
- `0x18002dc10`
- `0x18002dc48`
- `0x18002dd48`
- `0x18002e980`
- `0x180044490`
- `0x18004490e`
- `0x1800449da`
- `0x180044a50`
- `0x180044ab0`
- `0x180044af0`
- `0x180044b10`
- `0x180044b30`
- `0x180044b50`
- `0x180044b70`
- `0x180044bb0`
- `0x180044bf0`
- `0x180044c30`
- `0x180044cc1`
- `0x180044e8f`
- `0x180044ef0`
- `0x180044f02`
- `0x180044f55`
- `0x18004533a`
- `0x1800458c6`
- `0x1800464de`
- `0x18004656e`
- `0x180046580`
- `0x1800465ec`

## callees

- `0x18001da00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da1d`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  if ( hHeap )
  {
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18001da00  sub     rsp, 28h
0x18001da04  mov     rax, cs:hHeap
0x18001da0b  test    rax, rax
0x18001da0e  jz      short loc_18001DA24
0x18001da10  test    rcx, rcx
0x18001da13  jz      short loc_18001DA24
0x18001da15  mov     r8, rcx; lpMem
0x18001da18  xor     edx, edx; dwFlags
0x18001da1a  mov     rcx, rax; hHeap
0x18001da1d  call    cs:__imp_HeapFree
0x18001da23  nop
0x18001da24  add     rsp, 28h
0x18001da28  retn
```
