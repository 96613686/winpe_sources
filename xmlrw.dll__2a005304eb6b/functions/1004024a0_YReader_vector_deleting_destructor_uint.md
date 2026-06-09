# YReader::`vector deleting destructor'(uint)

- ea: `0x1004024a0`
- end: `0x100402533`
- name: `??_EYReader@@UEAAPEAXI@Z`
- size: `147`
- prototype: `void *__fastcall(YReader *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100401310`
- `0x1004024a0`
- `0x100402540`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100402504`
- `KERNEL32!HeapFree` at `0x100402504`

## pseudocode

```c
YReader *__fastcall YReader::`vector deleting destructor'(struct IMalloc **this, char a2)
{
  struct IMalloc *v4; // rcx

  YReader::~YReader((YReader *)this);
  if ( (a2 & 1) == 0 )
    return (YReader *)this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return (YReader *)this;
  }
  if ( !this )
    return (YReader *)this;
  v4 = this[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, this);
    return (YReader *)this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return (YReader *)this;
  }
}

```

## disassembly

```asm
0x1004024a0  mov     [rsp+arg_0], rbx
0x1004024a5  push    rdi
0x1004024a6  sub     rsp, 20h
0x1004024aa  mov     edi, edx
0x1004024ac  mov     rbx, rcx
0x1004024af  call    ??1YReader@@UEAA@XZ; YReader::~YReader(void)
0x1004024b4  test    dil, 1
0x1004024b8  jz      short loc_100402525
0x1004024ba  test    dil, 4
0x1004024be  jnz     short loc_100402518
0x1004024c0  test    rbx, rbx
0x1004024c3  jz      short loc_100402525
0x1004024c5  mov     rcx, [rbx+8]
0x1004024c9  test    rcx, rcx
0x1004024cc  jz      short loc_1004024EC
0x1004024ce  mov     rax, [rcx]
0x1004024d1  mov     rdx, rbx
0x1004024d4  mov     rax, [rax+28h]
0x1004024d8  call    cs:__guard_dispatch_icall_fptr
0x1004024de  mov     rax, rbx
0x1004024e1  mov     rbx, [rsp+28h+arg_0]
0x1004024e6  add     rsp, 20h
0x1004024ea  pop     rdi
0x1004024eb  retn
0x1004024ec  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004024f3  test    rcx, rcx
0x1004024f6  jnz     short loc_1004024CE
0x1004024f8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004024ff  mov     r8, rbx; lpMem
0x100402502  xor     edx, edx; dwFlags
0x100402504  call    cs:__imp_HeapFree
0x10040250a  mov     rax, rbx
0x10040250d  mov     rbx, [rsp+28h+arg_0]
0x100402512  add     rsp, 20h
0x100402516  pop     rdi
0x100402517  retn
0x100402518  mov     edx, 2050h; unsigned __int64
0x10040251d  mov     rcx, rbx; void *
0x100402520  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100402525  mov     rax, rbx
0x100402528  mov     rbx, [rsp+28h+arg_0]
0x10040252d  add     rsp, 20h
0x100402531  pop     rdi
0x100402532  retn
```
