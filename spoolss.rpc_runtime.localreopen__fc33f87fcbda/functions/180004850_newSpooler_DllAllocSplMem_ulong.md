# newSpooler::DllAllocSplMem(ulong)

- ea: `0x180004850`
- end: `0x18000488a`
- name: `?DllAllocSplMem@newSpooler@@YAPEAXK@Z`
- size: `58`
- prototype: `void *__fastcall(SIZE_T uBytes, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001bb0`
- `0x1800047f8`
- `0x180004a08`
- `0x18000d250`
- `0x18000d2d0`

## callees

- `0x180004850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004874`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004874`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000485d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000485d`

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
0x180004850  push    rbx
0x180004852  sub     rsp, 20h
0x180004856  mov     edx, ecx; uBytes
0x180004858  mov     ecx, 40h ; '@'; uFlags
0x18000485d  call    cs:__imp_LocalAlloc
0x180004864  nop     dword ptr [rax+rax+00h]
0x180004869  mov     rbx, rax
0x18000486c  test    rax, rax
0x18000486f  jnz     short loc_180004880
0x180004871  lea     ecx, [rax+8]; dwErrCode
0x180004874  call    cs:__imp_SetLastError
0x18000487b  nop     dword ptr [rax+rax+00h]
0x180004880  mov     rax, rbx
0x180004883  add     rsp, 20h
0x180004887  pop     rbx
0x180004888  retn
```
