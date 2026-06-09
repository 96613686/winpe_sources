# _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vector deleting destructor'(uint)

- ea: `0x1004079d0`
- end: `0x100407a63`
- name: `??_E?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@UEAAPEAXI@Z`
- size: `147`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1004011f0`
- `0x100407710`
- `0x1004079d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100407a34`
- `KERNEL32!HeapFree` at `0x100407a34`

## pseudocode

```c
struct IMalloc **__fastcall _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vector deleting destructor'(
        struct IMalloc **a1,
        char a2)
{
  struct IMalloc *v4; // rcx

  _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>((__int64)a1);
  if ( (a2 & 1) == 0 )
    return a1;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(a1);
    return a1;
  }
  if ( !a1 )
    return a1;
  v4 = a1[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, a1);
    return a1;
  }
  else
  {
    HeapFree(g_hHeap, 0, a1);
    return a1;
  }
}

```

## disassembly

```asm
0x1004079d0  mov     [rsp+arg_0], rbx
0x1004079d5  push    rdi
0x1004079d6  sub     rsp, 20h
0x1004079da  mov     edi, edx
0x1004079dc  mov     rbx, rcx
0x1004079df  call    ??1?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@UEAA@XZ; _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>(void)
0x1004079e4  test    dil, 1
0x1004079e8  jz      short loc_100407A55
0x1004079ea  test    dil, 4
0x1004079ee  jnz     short loc_100407A48
0x1004079f0  test    rbx, rbx
0x1004079f3  jz      short loc_100407A55
0x1004079f5  mov     rcx, [rbx+8]
0x1004079f9  test    rcx, rcx
0x1004079fc  jz      short loc_100407A1C
0x1004079fe  mov     rax, [rcx]
0x100407a01  mov     rdx, rbx
0x100407a04  mov     rax, [rax+28h]
0x100407a08  call    cs:__guard_dispatch_icall_fptr
0x100407a0e  mov     rax, rbx
0x100407a11  mov     rbx, [rsp+28h+arg_0]
0x100407a16  add     rsp, 20h
0x100407a1a  pop     rdi
0x100407a1b  retn
0x100407a1c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407a23  test    rcx, rcx
0x100407a26  jnz     short loc_1004079FE
0x100407a28  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407a2f  mov     r8, rbx; lpMem
0x100407a32  xor     edx, edx; dwFlags
0x100407a34  call    cs:__imp_HeapFree
0x100407a3a  mov     rax, rbx
0x100407a3d  mov     rbx, [rsp+28h+arg_0]
0x100407a42  add     rsp, 20h
0x100407a46  pop     rdi
0x100407a47  retn
0x100407a48  mov     edx, 20h ; ' '; unsigned __int64
0x100407a4d  mov     rcx, rbx; void *
0x100407a50  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100407a55  mov     rax, rbx
0x100407a58  mov     rbx, [rsp+28h+arg_0]
0x100407a5d  add     rsp, 20h
0x100407a61  pop     rdi
0x100407a62  retn
```
