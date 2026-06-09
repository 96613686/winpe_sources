# ReleaseMemoryWorker

- ea: `0x1800034c4`
- end: `0x1800034e8`
- name: `ReleaseMemoryWorker`
- size: `36`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020fc`
- `0x180003190`
- `0x180003434`
- `0x18000461c`
- `0x180004800`
- `0x180004b20`
- `0x180004bb0`
- `0x1800062a0`
- `0x1800063fc`

## callees

- `0x1800034c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034d5`

## pseudocode

```c
HLOCAL __fastcall ReleaseMemoryWorker(void **a1)
{
  void *v2; // rcx
  HLOCAL result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = LocalFree(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800034c4  push    rbx
0x1800034c6  sub     rsp, 20h
0x1800034ca  mov     rbx, rcx
0x1800034cd  mov     rcx, [rcx]; hMem
0x1800034d0  test    rcx, rcx
0x1800034d3  jz      short loc_1800034E2
0x1800034d5  call    cs:__imp_LocalFree
0x1800034db  mov     qword ptr [rbx], 0
0x1800034e2  add     rsp, 20h
0x1800034e6  pop     rbx
0x1800034e7  retn
```
