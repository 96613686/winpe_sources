# _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>(void)

- ea: `0x1004077e0`
- end: `0x1004078aa`
- name: `??1?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@UEAA@XZ`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1004071d0`
- `0x100407a70`

## callees

- `0x100407330`
- `0x1004077e0`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100407894`
- `KERNEL32!HeapFree` at `0x100407894`

## pseudocode

```c
int __fastcall _xarray<Unitoken,_xarray_item<Unitoken>>::~_xarray<Unitoken,_xarray_item<Unitoken>>(__int64 a1)
{
  WriterHandleEntry *v1; // rbx
  __int64 v3; // rcx
  WriterHandleEntry *v4; // rsi
  void *v5; // r8
  void **v6; // rax
  struct IMalloc *v7; // rcx

  v1 = *(WriterHandleEntry **)(a1 + 24);
  *(_QWORD *)a1 = &_xarray<Unitoken,_xarray_item<Unitoken>>::`vftable';
  v3 = *(unsigned int *)(a1 + 20);
  v4 = (WriterHandleEntry *)((char *)v1 + 40 * v3);
  if ( v1 != v4 )
  {
    do
    {
      WriterHandleEntry::~WriterHandleEntry(v1);
      v1 = (WriterHandleEntry *)((char *)v1 + 40);
    }
    while ( v1 != v4 );
    LODWORD(v3) = *(_DWORD *)(a1 + 20);
    v1 = *(WriterHandleEntry **)(a1 + 24);
  }
  memset(v1, 0, 40LL * (unsigned int)v3);
  v5 = *(void **)(a1 + 24);
  v6 = &_varray_base::`vftable';
  *(_DWORD *)(a1 + 20) = 0;
  *(_QWORD *)a1 = &_varray_base::`vftable';
  if ( v5 )
  {
    v7 = *(struct IMalloc **)(a1 + 8);
    if ( v7 || (v7 = g_pMalloc) != 0 )
      LODWORD(v6) = ((__int64 (__fastcall *)(struct IMalloc *, void *))v7->lpVtbl->Free)(v7, v5);
    else
      LODWORD(v6) = HeapFree(g_hHeap, 0, v5);
  }
  return (int)v6;
}

```

## disassembly

```asm
0x1004077e0  mov     [rsp+arg_0], rbx
0x1004077e5  mov     [rsp+arg_8], rsi
0x1004077ea  push    rdi
0x1004077eb  sub     rsp, 20h
0x1004077ef  mov     rbx, [rcx+18h]
0x1004077f3  lea     rax, ??_7?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@6B@; const _xarray<Unitoken,_xarray_item<Unitoken>>::`vftable'
0x1004077fa  mov     [rcx], rax
0x1004077fd  mov     rdi, rcx
0x100407800  mov     ecx, [rcx+14h]
0x100407803  lea     rax, [rcx+rcx*4]
0x100407807  lea     rsi, [rbx+rax*8]
0x10040780b  cmp     rbx, rsi
0x10040780e  jz      short loc_100407828
0x100407810  mov     rcx, rbx; this
0x100407813  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100407818  add     rbx, 28h ; '('
0x10040781c  cmp     rbx, rsi
0x10040781f  jnz     short loc_100407810
0x100407821  mov     ecx, [rdi+14h]
0x100407824  mov     rbx, [rdi+18h]
0x100407828  mov     eax, ecx
0x10040782a  xor     edx, edx; Val
0x10040782c  mov     rcx, rbx; void *
0x10040782f  lea     r8, [rax+rax*4]
0x100407833  shl     r8, 3; Size
0x100407837  call    memset
0x10040783c  mov     r8, [rdi+18h]; lpMem
0x100407840  lea     rax, ??_7_varray_base@@6B@; const _varray_base::`vftable'
0x100407847  mov     dword ptr [rdi+14h], 0
0x10040784e  mov     [rdi], rax
0x100407851  test    r8, r8
0x100407854  jz      short loc_10040789A
0x100407856  mov     rcx, [rdi+8]
0x10040785a  test    rcx, rcx
0x10040785d  jnz     short loc_10040786B
0x10040785f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407866  test    rcx, rcx
0x100407869  jz      short loc_10040788B
0x10040786b  mov     rax, [rcx]
0x10040786e  mov     rdx, r8
0x100407871  mov     rax, [rax+28h]
0x100407875  mov     rbx, [rsp+28h+arg_0]
0x10040787a  mov     rsi, [rsp+28h+arg_8]
0x10040787f  add     rsp, 20h
0x100407883  pop     rdi
0x100407884  jmp     cs:__guard_dispatch_icall_fptr
0x10040788b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407892  xor     edx, edx; dwFlags
0x100407894  call    cs:__imp_HeapFree
0x10040789a  mov     rbx, [rsp+28h+arg_0]
0x10040789f  mov     rsi, [rsp+28h+arg_8]
0x1004078a4  add     rsp, 20h
0x1004078a8  pop     rdi
0x1004078a9  retn
```
