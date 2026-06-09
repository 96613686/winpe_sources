# operator delete(void *,IMalloc *)

- ea: `0x100401300`
- end: `0x100401346`
- name: `??3@YAXPEAXPEAUIMalloc@@@Z`
- size: `70`
- prototype: `void __fastcall(void *, struct IMalloc *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100412e30`

## callees

- `0x100401300`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040133e`

## pseudocode

```c
void __fastcall operator delete(void *a1, struct IMalloc *a2)
{
  struct IMalloc *v2; // r8
  struct IMallocVtbl *lpVtbl; // rax

  v2 = a2;
  if ( a1 )
  {
    if ( a2 )
    {
      lpVtbl = a2->lpVtbl;
LABEL_6:
      ((void (__fastcall *)(struct IMalloc *, void *))lpVtbl->Free)(v2, a1);
      return;
    }
    v2 = g_pMalloc;
    if ( g_pMalloc )
    {
      lpVtbl = g_pMalloc->lpVtbl;
      goto LABEL_6;
    }
    HeapFree(g_hHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x100401300  mov     r8, rdx
0x100401303  test    rcx, rcx
0x100401306  jz      short locret_100401345
0x100401308  test    rdx, rdx
0x10040130b  jz      short loc_100401312
0x10040130d  mov     rax, [rdx]
0x100401310  jmp     short loc_100401321
0x100401312  mov     r8, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100401319  test    r8, r8
0x10040131c  jz      short loc_100401332
0x10040131e  mov     rax, [r8]
0x100401321  mov     rax, [rax+28h]
0x100401325  mov     rdx, rcx
0x100401328  mov     rcx, r8
0x10040132b  jmp     cs:__guard_dispatch_icall_fptr
0x100401332  mov     r8, rcx
0x100401335  xor     edx, edx
0x100401337  mov     rcx, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x10040133e  jmp     cs:__imp_HeapFree
0x100401345  retn
```
