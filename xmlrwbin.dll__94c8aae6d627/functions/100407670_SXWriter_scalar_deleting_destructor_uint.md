# SXWriter::`scalar deleting destructor'(uint)

- ea: `0x100407670`
- end: `0x100407703`
- name: `??_GSXWriter@@MEAAPEAXI@Z`
- size: `147`
- prototype: `void *__fastcall(SXWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1004011f0`
- `0x100407440`
- `0x100407670`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1004076d4`
- `KERNEL32!HeapFree` at `0x1004076d4`

## pseudocode

```c
SXWriter *__fastcall SXWriter::`scalar deleting destructor'(struct IMalloc **this, char a2)
{
  struct IMalloc *v4; // rcx

  SXWriter::~SXWriter((SXWriter *)this);
  if ( (a2 & 1) == 0 )
    return (SXWriter *)this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return (SXWriter *)this;
  }
  if ( !this )
    return (SXWriter *)this;
  v4 = this[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, this);
    return (SXWriter *)this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return (SXWriter *)this;
  }
}

```

## disassembly

```asm
0x100407670  mov     [rsp+arg_0], rbx
0x100407675  push    rdi
0x100407676  sub     rsp, 20h
0x10040767a  mov     edi, edx
0x10040767c  mov     rbx, rcx
0x10040767f  call    ??1SXWriter@@MEAA@XZ; SXWriter::~SXWriter(void)
0x100407684  test    dil, 1
0x100407688  jz      short loc_1004076F5
0x10040768a  test    dil, 4
0x10040768e  jnz     short loc_1004076E8
0x100407690  test    rbx, rbx
0x100407693  jz      short loc_1004076F5
0x100407695  mov     rcx, [rbx+8]
0x100407699  test    rcx, rcx
0x10040769c  jz      short loc_1004076BC
0x10040769e  mov     rax, [rcx]
0x1004076a1  mov     rdx, rbx
0x1004076a4  mov     rax, [rax+28h]
0x1004076a8  call    cs:__guard_dispatch_icall_fptr
0x1004076ae  mov     rax, rbx
0x1004076b1  mov     rbx, [rsp+28h+arg_0]
0x1004076b6  add     rsp, 20h
0x1004076ba  pop     rdi
0x1004076bb  retn
0x1004076bc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004076c3  test    rcx, rcx
0x1004076c6  jnz     short loc_10040769E
0x1004076c8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004076cf  mov     r8, rbx; lpMem
0x1004076d2  xor     edx, edx; dwFlags
0x1004076d4  call    cs:__imp_HeapFree
0x1004076da  mov     rax, rbx
0x1004076dd  mov     rbx, [rsp+28h+arg_0]
0x1004076e2  add     rsp, 20h
0x1004076e6  pop     rdi
0x1004076e7  retn
0x1004076e8  mov     edx, 968h; unsigned __int64
0x1004076ed  mov     rcx, rbx; void *
0x1004076f0  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x1004076f5  mov     rax, rbx
0x1004076f8  mov     rbx, [rsp+28h+arg_0]
0x1004076fd  add     rsp, 20h
0x100407701  pop     rdi
0x100407702  retn
```
