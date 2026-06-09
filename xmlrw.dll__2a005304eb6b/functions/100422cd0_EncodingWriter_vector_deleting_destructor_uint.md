# EncodingWriter::`vector deleting destructor'(uint)

- ea: `0x100422cd0`
- end: `0x100422d63`
- name: `??_EEncodingWriter@@UEAAPEAXI@Z`
- size: `147`
- prototype: `void *__fastcall(EncodingWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100401310`
- `0x100422cd0`
- `0x100423040`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100422d34`
- `KERNEL32!HeapFree` at `0x100422d34`

## pseudocode

```c
EncodingWriter *__fastcall EncodingWriter::`vector deleting destructor'(struct IMalloc **this, char a2)
{
  struct IMalloc *v4; // rcx

  EncodingWriter::~EncodingWriter((EncodingWriter *)this);
  if ( (a2 & 1) == 0 )
    return (EncodingWriter *)this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return (EncodingWriter *)this;
  }
  if ( !this )
    return (EncodingWriter *)this;
  v4 = this[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, this);
    return (EncodingWriter *)this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return (EncodingWriter *)this;
  }
}

```

## disassembly

```asm
0x100422cd0  mov     [rsp+arg_0], rbx
0x100422cd5  push    rdi
0x100422cd6  sub     rsp, 20h
0x100422cda  mov     edi, edx
0x100422cdc  mov     rbx, rcx
0x100422cdf  call    ??1EncodingWriter@@UEAA@XZ; EncodingWriter::~EncodingWriter(void)
0x100422ce4  test    dil, 1
0x100422ce8  jz      short loc_100422D55
0x100422cea  test    dil, 4
0x100422cee  jnz     short loc_100422D48
0x100422cf0  test    rbx, rbx
0x100422cf3  jz      short loc_100422D55
0x100422cf5  mov     rcx, [rbx+8]
0x100422cf9  test    rcx, rcx
0x100422cfc  jz      short loc_100422D1C
0x100422cfe  mov     rax, [rcx]
0x100422d01  mov     rdx, rbx
0x100422d04  mov     rax, [rax+28h]
0x100422d08  call    cs:__guard_dispatch_icall_fptr
0x100422d0e  mov     rax, rbx
0x100422d11  mov     rbx, [rsp+28h+arg_0]
0x100422d16  add     rsp, 20h
0x100422d1a  pop     rdi
0x100422d1b  retn
0x100422d1c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100422d23  test    rcx, rcx
0x100422d26  jnz     short loc_100422CFE
0x100422d28  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100422d2f  mov     r8, rbx; lpMem
0x100422d32  xor     edx, edx; dwFlags
0x100422d34  call    cs:__imp_HeapFree
0x100422d3a  mov     rax, rbx
0x100422d3d  mov     rbx, [rsp+28h+arg_0]
0x100422d42  add     rsp, 20h
0x100422d46  pop     rdi
0x100422d47  retn
0x100422d48  mov     edx, 68h ; 'h'; unsigned __int64
0x100422d4d  mov     rcx, rbx; void *
0x100422d50  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100422d55  mov     rax, rbx
0x100422d58  mov     rbx, [rsp+28h+arg_0]
0x100422d5d  add     rsp, 20h
0x100422d61  pop     rdi
0x100422d62  retn
```
