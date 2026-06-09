# _xarray<Unitoken,_xarray_item<Unitoken>>::`scalar deleting destructor'(uint)

- ea: `0x100407a70`
- end: `0x100407b03`
- name: `??_G?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@UEAAPEAXI@Z`
- size: `147`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1004011f0`
- `0x1004077e0`
- `0x100407a70`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100407ad4`
- `KERNEL32!HeapFree` at `0x100407ad4`

## pseudocode

```c
struct IMalloc **__fastcall _xarray<Unitoken,_xarray_item<Unitoken>>::`scalar deleting destructor'(
        struct IMalloc **a1,
        char a2)
{
  struct IMalloc *v4; // rcx

  _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>((__int64)a1);
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
0x100407a70  mov     [rsp+arg_0], rbx
0x100407a75  push    rdi
0x100407a76  sub     rsp, 20h
0x100407a7a  mov     edi, edx
0x100407a7c  mov     rbx, rcx
0x100407a7f  call    ??1?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@UEAA@XZ; _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>(void)
0x100407a84  test    dil, 1
0x100407a88  jz      short loc_100407AF5
0x100407a8a  test    dil, 4
0x100407a8e  jnz     short loc_100407AE8
0x100407a90  test    rbx, rbx
0x100407a93  jz      short loc_100407AF5
0x100407a95  mov     rcx, [rbx+8]
0x100407a99  test    rcx, rcx
0x100407a9c  jz      short loc_100407ABC
0x100407a9e  mov     rax, [rcx]
0x100407aa1  mov     rdx, rbx
0x100407aa4  mov     rax, [rax+28h]
0x100407aa8  call    cs:__guard_dispatch_icall_fptr
0x100407aae  mov     rax, rbx
0x100407ab1  mov     rbx, [rsp+28h+arg_0]
0x100407ab6  add     rsp, 20h
0x100407aba  pop     rdi
0x100407abb  retn
0x100407abc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407ac3  test    rcx, rcx
0x100407ac6  jnz     short loc_100407A9E
0x100407ac8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407acf  mov     r8, rbx; lpMem
0x100407ad2  xor     edx, edx; dwFlags
0x100407ad4  call    cs:__imp_HeapFree
0x100407ada  mov     rax, rbx
0x100407add  mov     rbx, [rsp+28h+arg_0]
0x100407ae2  add     rsp, 20h
0x100407ae6  pop     rdi
0x100407ae7  retn
0x100407ae8  mov     edx, 20h ; ' '; unsigned __int64
0x100407aed  mov     rcx, rbx; void *
0x100407af0  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100407af5  mov     rax, rbx
0x100407af8  mov     rbx, [rsp+28h+arg_0]
0x100407afd  add     rsp, 20h
0x100407b01  pop     rdi
0x100407b02  retn
```
