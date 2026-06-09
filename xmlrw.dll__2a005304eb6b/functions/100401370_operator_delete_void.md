# operator delete(void *)

- ea: `0x100401370`
- end: `0x1004013a9`
- name: `??3@YAXPEAX@Z`
- size: `57`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x10043925c`

## callees

- `0x100401370`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1004013a1`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
  {
    if ( g_pMalloc )
      ((void (__fastcall *)(struct IMalloc *, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, a1);
    else
      HeapFree(g_hHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x100401370  test    rcx, rcx
0x100401373  jz      short locret_1004013A8
0x100401375  mov     r8, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040137c  test    r8, r8
0x10040137f  jz      short loc_100401395
0x100401381  mov     rax, [r8]
0x100401384  mov     rdx, rcx
0x100401387  mov     rcx, r8
0x10040138a  mov     rax, [rax+28h]
0x10040138e  jmp     cs:__guard_dispatch_icall_fptr
0x100401395  mov     r8, rcx
0x100401398  xor     edx, edx
0x10040139a  mov     rcx, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x1004013a1  jmp     cs:__imp_HeapFree
0x1004013a8  retn
```
