# XMLOutputHelper::`scalar deleting destructor'(uint)

- ea: `0x1004213a0`
- end: `0x100421433`
- name: `??_GXMLOutputHelper@@UEAAPEAXI@Z`
- size: `147`
- prototype: `void *__fastcall(XMLOutputHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x100401310`
- `0x1004213a0`
- `0x1004224d0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100421404`
- `KERNEL32!HeapFree` at `0x100421404`

## pseudocode

```c
XMLOutputHelper *__fastcall XMLOutputHelper::`scalar deleting destructor'(struct IMalloc **this, char a2)
{
  struct IMalloc *v4; // rcx

  OutputHelper::~OutputHelper((OutputHelper *)this);
  if ( (a2 & 1) == 0 )
    return (XMLOutputHelper *)this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return (XMLOutputHelper *)this;
  }
  if ( !this )
    return (XMLOutputHelper *)this;
  v4 = this[1];
  if ( v4 || (v4 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, struct IMalloc **))v4->lpVtbl->Free)(v4, this);
    return (XMLOutputHelper *)this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return (XMLOutputHelper *)this;
  }
}

```

## disassembly

```asm
0x1004213a0  mov     [rsp+arg_0], rbx
0x1004213a5  push    rdi
0x1004213a6  sub     rsp, 20h
0x1004213aa  mov     edi, edx
0x1004213ac  mov     rbx, rcx
0x1004213af  call    ??1OutputHelper@@UEAA@XZ; OutputHelper::~OutputHelper(void)
0x1004213b4  test    dil, 1
0x1004213b8  jz      short loc_100421425
0x1004213ba  test    dil, 4
0x1004213be  jnz     short loc_100421418
0x1004213c0  test    rbx, rbx
0x1004213c3  jz      short loc_100421425
0x1004213c5  mov     rcx, [rbx+8]
0x1004213c9  test    rcx, rcx
0x1004213cc  jz      short loc_1004213EC
0x1004213ce  mov     rax, [rcx]
0x1004213d1  mov     rdx, rbx
0x1004213d4  mov     rax, [rax+28h]
0x1004213d8  call    cs:__guard_dispatch_icall_fptr
0x1004213de  mov     rax, rbx
0x1004213e1  mov     rbx, [rsp+28h+arg_0]
0x1004213e6  add     rsp, 20h
0x1004213ea  pop     rdi
0x1004213eb  retn
0x1004213ec  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004213f3  test    rcx, rcx
0x1004213f6  jnz     short loc_1004213CE
0x1004213f8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004213ff  mov     r8, rbx; lpMem
0x100421402  xor     edx, edx; dwFlags
0x100421404  call    cs:__imp_HeapFree
0x10042140a  mov     rax, rbx
0x10042140d  mov     rbx, [rsp+28h+arg_0]
0x100421412  add     rsp, 20h
0x100421416  pop     rdi
0x100421417  retn
0x100421418  mov     edx, 1918h; unsigned __int64
0x10042141d  mov     rcx, rbx; void *
0x100421420  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100421425  mov     rax, rbx
0x100421428  mov     rbx, [rsp+28h+arg_0]
0x10042142d  add     rsp, 20h
0x100421431  pop     rdi
0x100421432  retn
```
