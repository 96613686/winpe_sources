# __vcrt_uninitialize_ptd

- ea: `0x14000314c`
- end: `0x140003172`
- name: `__vcrt_uninitialize_ptd`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f98`
- `0x1400030fc`

## callees

- `0x14000314c`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x14000315b`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x14000315b`

## pseudocode

```c
char _vcrt_uninitialize_ptd()
{
  if ( dwFlsIndex != -1 )
  {
    FlsFree(dwFlsIndex);
    dwFlsIndex = -1;
  }
  return 1;
}

```

## disassembly

```asm
0x14000314c  sub     rsp, 28h
0x140003150  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x140003156  cmp     ecx, 0FFFFFFFFh
0x140003159  jz      short loc_14000316B
0x14000315b  call    cs:__imp_FlsFree
0x140003161  mov     cs:dwFlsIndex, 0FFFFFFFFh
0x14000316b  mov     al, 1
0x14000316d  add     rsp, 28h
0x140003171  retn
```
