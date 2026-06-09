# operator delete(void *)

- ea: `0x100401250`
- end: `0x100401289`
- name: `??3@YAXPEAX@Z`
- size: `57`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100423a8c`

## callees

- `0x100401250`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100401281`

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
0x100401250  test    rcx, rcx
0x100401253  jz      short locret_100401288
0x100401255  mov     r8, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040125c  test    r8, r8
0x10040125f  jz      short loc_100401275
0x100401261  mov     rax, [r8]
0x100401264  mov     rdx, rcx
0x100401267  mov     rcx, r8
0x10040126a  mov     rax, [rax+28h]
0x10040126e  jmp     cs:__guard_dispatch_icall_fptr
0x100401275  mov     r8, rcx
0x100401278  xor     edx, edx
0x10040127a  mov     rcx, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x100401281  jmp     cs:__imp_HeapFree
0x100401288  retn
```
