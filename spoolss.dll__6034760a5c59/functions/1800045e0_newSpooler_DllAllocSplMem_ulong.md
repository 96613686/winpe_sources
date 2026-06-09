# newSpooler::DllAllocSplMem(ulong)

- ea: `0x1800045e0`
- end: `0x18000460d`
- name: `?DllAllocSplMem@newSpooler@@YAPEAXK@Z`
- size: `45`
- prototype: `void *__fastcall(SIZE_T uBytes, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001ba0`
- `0x180004588`
- `0x1800046d8`
- `0x18000c7a0`
- `0x18000c820`

## callees

- `0x1800045e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045ed`

## pseudocode

```c
HLOCAL __fastcall newSpooler::DllAllocSplMem(SIZE_T uBytes)
{
  HLOCAL v1; // rbx

  v1 = LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( !v1 )
    SetLastError(8u);
  return v1;
}

```

## disassembly

```asm
0x1800045e0  push    rbx
0x1800045e2  sub     rsp, 20h
0x1800045e6  mov     edx, ecx; uBytes
0x1800045e8  mov     ecx, 40h ; '@'; uFlags
0x1800045ed  call    cs:__imp_LocalAlloc
0x1800045f3  mov     rbx, rax
0x1800045f6  test    rax, rax
0x1800045f9  jnz     short loc_180004604
0x1800045fb  lea     ecx, [rax+8]; dwErrCode
0x1800045fe  call    cs:__imp_SetLastError
0x180004604  mov     rax, rbx
0x180004607  add     rsp, 20h
0x18000460b  pop     rbx
0x18000460c  retn
```
