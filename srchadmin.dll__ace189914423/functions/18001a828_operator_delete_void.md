# operator delete(void *)

- ea: `0x18001a828`
- end: `0x18001a84f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006170`
- `0x18000decc`
- `0x18000dedc`
- `0x18000e090`
- `0x18000eb60`
- `0x18000eebc`
- `0x18000fd48`
- `0x18000fdd8`
- `0x18000fe10`
- `0x180010034`
- `0x180012a30`
- `0x180014824`
- `0x180016aa0`
- `0x1800196b0`
- `0x18001a354`
- `0x18001ac7c`
- `0x18001ad2c`
- `0x18001b948`
- `0x18001cb38`
- `0x18001d210`
- `0x18001fdd4`
- `0x1800209cc`
- `0x18002c590`
- `0x18002d474`
- `0x18002f130`
- `0x18002f160`

## callees

- `0x18001a828`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a843`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18001a828  test    rcx, rcx
0x18001a82b  jz      short locret_18001A84E
0x18001a82d  push    rbx
0x18001a82e  sub     rsp, 20h
0x18001a832  mov     rbx, rcx
0x18001a835  call    cs:__imp_GetProcessHeap
0x18001a83b  mov     r8, rbx; lpMem
0x18001a83e  xor     edx, edx; dwFlags
0x18001a840  mov     rcx, rax; hHeap
0x18001a843  call    cs:__imp_HeapFree
0x18001a849  add     rsp, 20h
0x18001a84d  pop     rbx
0x18001a84e  retn
```
