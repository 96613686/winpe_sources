# SXReadBase::`vector deleting destructor'(uint)

- ea: `0x10040e590`
- end: `0x10040e623`
- name: `??_ESXReadBase@@MEAAPEAXI@Z`
- size: `147`
- prototype: `void *__fastcall(SXReadBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1004011f0`
- `0x10040e590`
- `0x10040e630`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040e5f4`
- `KERNEL32!HeapFree` at `0x10040e5f4`

## pseudocode

```c
SXReadBase *__fastcall SXReadBase::`vector deleting destructor'(struct IMalloc **this, char a2)
{
  struct IMalloc *v4; // rcx

  SXReadBase::~SXReadBase((SXReadBase *)this);
  if ( (a2 & 1) == 0 )
    return (SXReadBase *)this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return (SXReadBase *)this;
  }
  if ( !this )
    return (SXReadBase *)this;
  v4 = this[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, this);
    return (SXReadBase *)this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return (SXReadBase *)this;
  }
}

```

## disassembly

```asm
0x10040e590  mov     [rsp+arg_0], rbx
0x10040e595  push    rdi
0x10040e596  sub     rsp, 20h
0x10040e59a  mov     edi, edx
0x10040e59c  mov     rbx, rcx
0x10040e59f  call    ??1SXReadBase@@MEAA@XZ; SXReadBase::~SXReadBase(void)
0x10040e5a4  test    dil, 1
0x10040e5a8  jz      short loc_10040E615
0x10040e5aa  test    dil, 4
0x10040e5ae  jnz     short loc_10040E608
0x10040e5b0  test    rbx, rbx
0x10040e5b3  jz      short loc_10040E615
0x10040e5b5  mov     rcx, [rbx+8]
0x10040e5b9  test    rcx, rcx
0x10040e5bc  jz      short loc_10040E5DC
0x10040e5be  mov     rax, [rcx]
0x10040e5c1  mov     rdx, rbx
0x10040e5c4  mov     rax, [rax+28h]
0x10040e5c8  call    cs:__guard_dispatch_icall_fptr
0x10040e5ce  mov     rax, rbx
0x10040e5d1  mov     rbx, [rsp+28h+arg_0]
0x10040e5d6  add     rsp, 20h
0x10040e5da  pop     rdi
0x10040e5db  retn
0x10040e5dc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040e5e3  test    rcx, rcx
0x10040e5e6  jnz     short loc_10040E5BE
0x10040e5e8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040e5ef  mov     r8, rbx; lpMem
0x10040e5f2  xor     edx, edx; dwFlags
0x10040e5f4  call    cs:__imp_HeapFree
0x10040e5fa  mov     rax, rbx
0x10040e5fd  mov     rbx, [rsp+28h+arg_0]
0x10040e602  add     rsp, 20h
0x10040e606  pop     rdi
0x10040e607  retn
0x10040e608  mov     edx, 5B0h; unsigned __int64
0x10040e60d  mov     rcx, rbx; void *
0x10040e610  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x10040e615  mov     rax, rbx
0x10040e618  mov     rbx, [rsp+28h+arg_0]
0x10040e61d  add     rsp, 20h
0x10040e621  pop     rdi
0x10040e622  retn
```
