# WriterHandleEntry::~WriterHandleEntry(void)

- ea: `0x100407330`
- end: `0x100407438`
- name: `??1WriterHandleEntry@@QEAA@XZ`
- size: `264`
- prototype: `void __fastcall(WriterHandleEntry *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1004071d0`
- `0x100407440`
- `0x100407710`
- `0x1004077e0`
- `0x100407bb0`
- `0x100409320`
- `0x1004098d0`
- `0x10040aab0`
- `0x10040ace0`
- `0x10040af70`
- `0x100410010`

## callees

- `0x100407330`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100407389`
- `KERNEL32!HeapFree` at `0x1004073d4`
- `KERNEL32!HeapFree` at `0x100407427`
- `KERNEL32!HeapFree` at `0x100407389`
- `KERNEL32!HeapFree` at `0x1004073d4`
- `KERNEL32!HeapFree` at `0x100407427`

## pseudocode

```c
void __fastcall WriterHandleEntry::~WriterHandleEntry(WriterHandleEntry *this)
{
  __int64 v1; // r8
  bool v3; // zf
  struct IMalloc *v4; // rcx
  __int64 v5; // r8
  struct IMalloc *v6; // rcx
  __int64 v7; // r8
  struct IMalloc *v8; // rcx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    v3 = (*(_DWORD *)(v1 + 20))-- == 1;
    if ( v3 && (void ***)v1 != &cspNull )
    {
      v4 = *(struct IMalloc **)(v1 + 8);
      if ( v4 || (v4 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v4->lpVtbl->Free)(v4, v1);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v1);
    }
  }
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    v3 = (*(_DWORD *)(v5 + 20))-- == 1;
    if ( v3 && (void ***)v5 != &cspNull )
    {
      v6 = *(struct IMalloc **)(v5 + 8);
      if ( v6 || (v6 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v6->lpVtbl->Free)(v6, v5);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v5);
    }
  }
  v7 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    v3 = (*(_DWORD *)(v7 + 20))-- == 1;
    if ( v3 && (void ***)v7 != &cspNull )
    {
      v8 = *(struct IMalloc **)(v7 + 8);
      if ( v8 || (v8 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v8->lpVtbl->Free)(v8, v7);
      else
        HeapFree(g_hHeap, 0, (LPVOID)v7);
    }
  }
}

```

## disassembly

```asm
0x100407330  mov     [rsp+arg_0], rbx
0x100407335  push    rdi
0x100407336  sub     rsp, 20h
0x10040733a  mov     r8, [rcx+10h]; lpMem
0x10040733e  lea     rdi, ?cspNull@@3VCStringPtr@@A; CStringPtr cspNull
0x100407345  mov     rbx, rcx
0x100407348  test    r8, r8
0x10040734b  jz      short loc_10040738F
0x10040734d  add     dword ptr [r8+14h], 0FFFFFFFFh
0x100407352  jnz     short loc_10040738F
0x100407354  cmp     r8, rdi
0x100407357  jz      short loc_10040738F
0x100407359  mov     rcx, [r8+8]
0x10040735d  test    rcx, rcx
0x100407360  jnz     short loc_10040736E
0x100407362  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407369  test    rcx, rcx
0x10040736c  jz      short loc_100407380
0x10040736e  mov     rax, [rcx]
0x100407371  mov     rdx, r8
0x100407374  mov     rax, [rax+28h]
0x100407378  call    cs:__guard_dispatch_icall_fptr
0x10040737e  jmp     short loc_10040738F
0x100407380  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407387  xor     edx, edx; dwFlags
0x100407389  call    cs:__imp_HeapFree
0x10040738f  mov     r8, [rbx+8]; lpMem
0x100407393  test    r8, r8
0x100407396  jz      short loc_1004073DA
0x100407398  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040739d  jnz     short loc_1004073DA
0x10040739f  cmp     r8, rdi
0x1004073a2  jz      short loc_1004073DA
0x1004073a4  mov     rcx, [r8+8]
0x1004073a8  test    rcx, rcx
0x1004073ab  jnz     short loc_1004073B9
0x1004073ad  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004073b4  test    rcx, rcx
0x1004073b7  jz      short loc_1004073CB
0x1004073b9  mov     rax, [rcx]
0x1004073bc  mov     rdx, r8
0x1004073bf  mov     rax, [rax+28h]
0x1004073c3  call    cs:__guard_dispatch_icall_fptr
0x1004073c9  jmp     short loc_1004073DA
0x1004073cb  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004073d2  xor     edx, edx; dwFlags
0x1004073d4  call    cs:__imp_HeapFree
0x1004073da  mov     r8, [rbx]; lpMem
0x1004073dd  test    r8, r8
0x1004073e0  jz      short loc_10040742D
0x1004073e2  add     dword ptr [r8+14h], 0FFFFFFFFh
0x1004073e7  jnz     short loc_10040742D
0x1004073e9  cmp     r8, rdi
0x1004073ec  jz      short loc_10040742D
0x1004073ee  mov     rcx, [r8+8]
0x1004073f2  test    rcx, rcx
0x1004073f5  jnz     short loc_100407403
0x1004073f7  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004073fe  test    rcx, rcx
0x100407401  jz      short loc_10040741E
0x100407403  mov     rax, [rcx]
0x100407406  mov     rdx, r8
0x100407409  mov     rax, [rax+28h]
0x10040740d  mov     rbx, [rsp+28h+arg_0]
0x100407412  add     rsp, 20h
0x100407416  pop     rdi
0x100407417  jmp     cs:__guard_dispatch_icall_fptr
0x10040741e  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407425  xor     edx, edx; dwFlags
0x100407427  call    cs:__imp_HeapFree
0x10040742d  mov     rbx, [rsp+28h+arg_0]
0x100407432  add     rsp, 20h
0x100407436  pop     rdi
0x100407437  retn
```
