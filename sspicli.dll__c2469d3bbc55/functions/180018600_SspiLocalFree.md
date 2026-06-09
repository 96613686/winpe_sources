# SspiLocalFree

- ea: `0x180018600`
- end: `0x180018614`
- name: `SspiLocalFree`
- size: `20`
- prototype: `void __stdcall(PVOID DataBuffer)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8e4`
- `0x18000fa60`
- `0x18000fae0`
- `0x18000ffb0`
- `0x1800100b0`
- `0x180010f00`
- `0x1800110f0`
- `0x1800113a0`
- `0x180014520`
- `0x180015068`
- `0x180017410`
- `0x180017760`
- `0x180017970`
- `0x180017e40`
- `0x180018430`
- `0x18001d880`
- `0x18001fe8c`
- `0x180020080`

## callees

- `0x180018600`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018609`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018609`

## pseudocode

```c
void __stdcall SspiLocalFree(PVOID DataBuffer)
{
  if ( DataBuffer )
    LocalFree(DataBuffer);
}

```

## disassembly

```asm
0x180018600  sub     rsp, 28h
0x180018604  test    rcx, rcx
0x180018607  jz      short loc_18001860F
0x180018609  call    cs:__imp_LocalFree
0x18001860f  add     rsp, 28h
0x180018613  retn
```
