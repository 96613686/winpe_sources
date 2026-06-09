# _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>(void)

- ea: `0x100407710`
- end: `0x1004077d8`
- name: `??1?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@UEAA@XZ`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100407440`
- `0x1004079d0`

## callees

- `0x100407330`
- `0x100407710`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1004077c2`
- `KERNEL32!HeapFree` at `0x1004077c2`

## pseudocode

```c
int __fastcall _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>(
        __int64 a1)
{
  WriterHandleEntry *v1; // rbx
  unsigned int v3; // eax
  WriterHandleEntry *v4; // rsi
  void *v5; // r8
  void **v6; // rax
  struct IMalloc *v7; // rcx

  v1 = *(WriterHandleEntry **)(a1 + 24);
  *(_QWORD *)a1 = &_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vftable';
  v3 = *(_DWORD *)(a1 + 20);
  v4 = (WriterHandleEntry *)((char *)v1 + 32 * v3);
  if ( v1 != v4 )
  {
    do
    {
      WriterHandleEntry::~WriterHandleEntry(v1);
      v1 = (WriterHandleEntry *)((char *)v1 + 32);
    }
    while ( v1 != v4 );
    v3 = *(_DWORD *)(a1 + 20);
    v1 = *(WriterHandleEntry **)(a1 + 24);
  }
  memset(v1, 0, 32LL * v3);
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
0x100407710  mov     [rsp+arg_0], rbx
0x100407715  mov     [rsp+arg_8], rsi
0x10040771a  push    rdi
0x10040771b  sub     rsp, 20h
0x10040771f  mov     rbx, [rcx+18h]
0x100407723  lea     rax, ??_7?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@6B@; const _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::`vftable'
0x10040772a  mov     [rcx], rax
0x10040772d  mov     rdi, rcx
0x100407730  mov     eax, [rcx+14h]
0x100407733  mov     esi, eax
0x100407735  shl     rsi, 5
0x100407739  add     rsi, rbx
0x10040773c  cmp     rbx, rsi
0x10040773f  jz      short loc_100407759
0x100407741  mov     rcx, rbx; this
0x100407744  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100407749  add     rbx, 20h ; ' '
0x10040774d  cmp     rbx, rsi
0x100407750  jnz     short loc_100407741
0x100407752  mov     eax, [rdi+14h]
0x100407755  mov     rbx, [rdi+18h]
0x100407759  mov     r8d, eax
0x10040775c  xor     edx, edx; Val
0x10040775e  shl     r8, 5; Size
0x100407762  mov     rcx, rbx; void *
0x100407765  call    memset
0x10040776a  mov     r8, [rdi+18h]; lpMem
0x10040776e  lea     rax, ??_7_varray_base@@6B@; const _varray_base::`vftable'
0x100407775  mov     dword ptr [rdi+14h], 0
0x10040777c  mov     [rdi], rax
0x10040777f  test    r8, r8
0x100407782  jz      short loc_1004077C8
0x100407784  mov     rcx, [rdi+8]
0x100407788  test    rcx, rcx
0x10040778b  jnz     short loc_100407799
0x10040778d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407794  test    rcx, rcx
0x100407797  jz      short loc_1004077B9
0x100407799  mov     rax, [rcx]
0x10040779c  mov     rdx, r8
0x10040779f  mov     rax, [rax+28h]
0x1004077a3  mov     rbx, [rsp+28h+arg_0]
0x1004077a8  mov     rsi, [rsp+28h+arg_8]
0x1004077ad  add     rsp, 20h
0x1004077b1  pop     rdi
0x1004077b2  jmp     cs:__guard_dispatch_icall_fptr
0x1004077b9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004077c0  xor     edx, edx; dwFlags
0x1004077c2  call    cs:__imp_HeapFree
0x1004077c8  mov     rbx, [rsp+28h+arg_0]
0x1004077cd  mov     rsi, [rsp+28h+arg_8]
0x1004077d2  add     rsp, 20h
0x1004077d6  pop     rdi
0x1004077d7  retn
```
