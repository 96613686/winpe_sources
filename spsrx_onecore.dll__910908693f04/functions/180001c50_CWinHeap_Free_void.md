# CWinHeap::Free(void *)

- ea: `0x180001c50`
- end: `0x180001c7f`
- name: `?Free@CWinHeap@@QEAA_NPEAX@Z`
- size: `47`
- prototype: `bool(CWinHeap *__hidden this, void *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c30`
- `0x1800040f0`
- `0x180004f5c`
- `0x18000500c`
- `0x1800052f4`
- `0x1800057c8`
- `0x180005b00`
- `0x1800069e4`
- `0x180009218`
- `0x180009930`
- `0x18000afe0`
- `0x18000b208`
- `0x18000b770`
- `0x18000bcd4`
- `0x18000d1c0`
- `0x18000d8d4`
- `0x18000e53c`
- `0x18000e7c4`
- `0x18000e838`

## callees

- `0x180001c50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c66`

## pseudocode

```c
bool __fastcall CWinHeap::Free(void **this, void *a2)
{
  void *v2; // rcx

  if ( !a2 )
    return 1;
  v2 = *this;
  if ( !v2 )
    return 0;
  return HeapFree(v2, 0, a2);
}

```

## disassembly

```asm
0x180001c50  sub     rsp, 28h
0x180001c54  test    rdx, rdx
0x180001c57  jz      short loc_180001C70
0x180001c59  mov     rcx, [rcx]; hHeap
0x180001c5c  test    rcx, rcx
0x180001c5f  jz      short loc_180001C7B
0x180001c61  mov     r8, rdx; lpMem
0x180001c64  xor     edx, edx; dwFlags
0x180001c66  call    cs:__imp_HeapFree
0x180001c6c  test    eax, eax
0x180001c6e  jz      short loc_180001C77
0x180001c70  mov     al, 1
0x180001c72  add     rsp, 28h
0x180001c76  retn
0x180001c77  xor     eax, eax
0x180001c79  jmp     short loc_180001C72
0x180001c7b  xor     al, al
0x180001c7d  jmp     short loc_180001C72
```
