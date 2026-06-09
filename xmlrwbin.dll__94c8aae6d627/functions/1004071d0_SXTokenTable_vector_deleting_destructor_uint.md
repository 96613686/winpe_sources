# SXTokenTable::`vector deleting destructor'(uint)

- ea: `0x1004071d0`
- end: `0x10040731e`
- name: `??_ESXTokenTable@@UEAAPEAXI@Z`
- size: `334`
- prototype: `void *__fastcall(SXTokenTable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1004011f0`
- `0x1004071d0`
- `0x100407330`
- `0x1004077e0`
- `0x1004078b0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100407242`
- `KERNEL32!HeapFree` at `0x100407295`
- `KERNEL32!HeapFree` at `0x1004072ef`
- `KERNEL32!HeapFree` at `0x100407242`
- `KERNEL32!HeapFree` at `0x100407295`
- `KERNEL32!HeapFree` at `0x1004072ef`

## pseudocode

```c
SXTokenTable *__fastcall SXTokenTable::`vector deleting destructor'(SXTokenTable *this, char a2)
{
  void *v4; // r8
  struct IMalloc *v5; // rcx
  void *v6; // r8
  struct IMalloc *v7; // rcx
  struct IMalloc *v8; // rcx

  *(_QWORD *)this = &SXTokenTable::`vftable';
  WriterHandleEntry::~WriterHandleEntry((SXTokenTable *)((char *)this + 176));
  v4 = (void *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 16) = &_htablesx::`vftable';
  if ( v4 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 17);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v4);
    else
      HeapFree(g_hHeap, 0, v4);
  }
  _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>((char *)this + 96);
  v6 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 6) = &_htablesx::`vftable';
  if ( v6 )
  {
    v7 = (struct IMalloc *)*((_QWORD *)this + 7);
    if ( v7 || (v7 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v7->lpVtbl->Free)(v7, v6);
    else
      HeapFree(g_hHeap, 0, v6);
  }
  _xarray<RStringPtr,_xarray_item<RStringPtr>>::~_xarray<RStringPtr,_xarray_item<RStringPtr>>((char *)this + 16);
  if ( (a2 & 1) == 0 )
    return this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return this;
  }
  v8 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v8 || (v8 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, SXTokenTable *))v8->lpVtbl->Free)(v8, this);
    return this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return this;
  }
}

```

## disassembly

```asm
0x1004071d0  mov     [rsp+arg_0], rbx
0x1004071d5  push    rdi
0x1004071d6  sub     rsp, 20h
0x1004071da  lea     rax, ??_7SXTokenTable@@6B@; const SXTokenTable::`vftable'
0x1004071e1  mov     rbx, rcx
0x1004071e4  mov     [rcx], rax
0x1004071e7  mov     edi, edx
0x1004071e9  add     rcx, 0B0h; this
0x1004071f0  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x1004071f5  mov     r8, [rbx+90h]; lpMem
0x1004071fc  lea     rax, ??_7_htablesx@@6B@; const _htablesx::`vftable'
0x100407203  mov     [rbx+80h], rax
0x10040720a  test    r8, r8
0x10040720d  jz      short loc_100407248
0x10040720f  mov     rcx, [rbx+88h]
0x100407216  test    rcx, rcx
0x100407219  jnz     short loc_100407227
0x10040721b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407222  test    rcx, rcx
0x100407225  jz      short loc_100407239
0x100407227  mov     rax, [rcx]
0x10040722a  mov     rdx, r8
0x10040722d  mov     rax, [rax+28h]
0x100407231  call    cs:__guard_dispatch_icall_fptr
0x100407237  jmp     short loc_100407248
0x100407239  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407240  xor     edx, edx; dwFlags
0x100407242  call    cs:__imp_HeapFree
0x100407248  lea     rcx, [rbx+60h]
0x10040724c  call    ??1?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@UEAA@XZ; _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>(void)
0x100407251  mov     r8, [rbx+40h]; lpMem
0x100407255  lea     rax, ??_7_htablesx@@6B@; const _htablesx::`vftable'
0x10040725c  mov     [rbx+30h], rax
0x100407260  test    r8, r8
0x100407263  jz      short loc_10040729B
0x100407265  mov     rcx, [rbx+38h]
0x100407269  test    rcx, rcx
0x10040726c  jnz     short loc_10040727A
0x10040726e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407275  test    rcx, rcx
0x100407278  jz      short loc_10040728C
0x10040727a  mov     rax, [rcx]
0x10040727d  mov     rdx, r8
0x100407280  mov     rax, [rax+28h]
0x100407284  call    cs:__guard_dispatch_icall_fptr
0x10040728a  jmp     short loc_10040729B
0x10040728c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407293  xor     edx, edx; dwFlags
0x100407295  call    cs:__imp_HeapFree
0x10040729b  lea     rcx, [rbx+10h]
0x10040729f  call    ??1?$_xarray@VRStringPtr@@V?$_xarray_item@VRStringPtr@@@@@@UEAA@XZ; _xarray<RStringPtr,_xarray_item<RStringPtr>>::~_xarray<RStringPtr,_xarray_item<RStringPtr>>(void)
0x1004072a4  test    dil, 1
0x1004072a8  jz      short loc_100407310
0x1004072aa  test    dil, 4
0x1004072ae  jnz     short loc_100407303
0x1004072b0  mov     rcx, [rbx+8]
0x1004072b4  test    rcx, rcx
0x1004072b7  jz      short loc_1004072D7
0x1004072b9  mov     rax, [rcx]
0x1004072bc  mov     rdx, rbx
0x1004072bf  mov     rax, [rax+28h]
0x1004072c3  call    cs:__guard_dispatch_icall_fptr
0x1004072c9  mov     rax, rbx
0x1004072cc  mov     rbx, [rsp+28h+arg_0]
0x1004072d1  add     rsp, 20h
0x1004072d5  pop     rdi
0x1004072d6  retn
0x1004072d7  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004072de  test    rcx, rcx
0x1004072e1  jnz     short loc_1004072B9
0x1004072e3  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004072ea  mov     r8, rbx; lpMem
0x1004072ed  xor     edx, edx; dwFlags
0x1004072ef  call    cs:__imp_HeapFree
0x1004072f5  mov     rax, rbx
0x1004072f8  mov     rbx, [rsp+28h+arg_0]
0x1004072fd  add     rsp, 20h
0x100407301  pop     rdi
0x100407302  retn
0x100407303  mov     edx, 0D8h; unsigned __int64
0x100407308  mov     rcx, rbx; void *
0x10040730b  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100407310  mov     rax, rbx
0x100407313  mov     rbx, [rsp+28h+arg_0]
0x100407318  add     rsp, 20h
0x10040731c  pop     rdi
0x10040731d  retn
```
