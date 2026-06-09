# _stack<YReader::Element,16>::`vector deleting destructor'(uint)

- ea: `0x10040c370`
- end: `0x10040c44b`
- name: `??_E?$_stack@UElement@YReader@@$0BA@@@UEAAPEAXI@Z`
- size: `219`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100401310`
- `0x10040c370`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040c3cb`
- `KERNEL32!HeapFree` at `0x10040c41c`
- `KERNEL32!HeapFree` at `0x10040c3cb`
- `KERNEL32!HeapFree` at `0x10040c41c`

## pseudocode

```c
_QWORD *__fastcall _stack<YReader::Element,16>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  _QWORD *v2; // r8
  struct IMalloc *v5; // rcx
  struct IMalloc *v6; // rcx

  v2 = (_QWORD *)a1[2];
  *a1 = &_stack<YReader::Element,16>::`vftable';
  if ( v2 && v2 != a1 + 4 )
  {
    v5 = (struct IMalloc *)a1[1];
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
  }
  if ( (a2 & 1) == 0 )
    return a1;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(a1);
    return a1;
  }
  v6 = (struct IMalloc *)a1[1];
  if ( v6 || (v6 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, _QWORD *))v6->lpVtbl->Free)(v6, a1);
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
0x10040c370  mov     [rsp+arg_0], rbx
0x10040c375  push    rdi
0x10040c376  sub     rsp, 20h
0x10040c37a  mov     r8, [rcx+10h]; lpMem
0x10040c37e  lea     rax, ??_7?$_stack@UElement@YReader@@$0BA@@@6B@; const _stack<YReader::Element,16>::`vftable'
0x10040c385  mov     [rcx], rax
0x10040c388  mov     edi, edx
0x10040c38a  mov     rbx, rcx
0x10040c38d  test    r8, r8
0x10040c390  jz      short loc_10040C3D1
0x10040c392  lea     rax, [rcx+20h]
0x10040c396  cmp     r8, rax
0x10040c399  jz      short loc_10040C3D1
0x10040c39b  mov     rcx, [rcx+8]
0x10040c39f  test    rcx, rcx
0x10040c3a2  jnz     short loc_10040C3B0
0x10040c3a4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c3ab  test    rcx, rcx
0x10040c3ae  jz      short loc_10040C3C2
0x10040c3b0  mov     rax, [rcx]
0x10040c3b3  mov     rdx, r8
0x10040c3b6  mov     rax, [rax+28h]
0x10040c3ba  call    cs:__guard_dispatch_icall_fptr
0x10040c3c0  jmp     short loc_10040C3D1
0x10040c3c2  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c3c9  xor     edx, edx; dwFlags
0x10040c3cb  call    cs:__imp_HeapFree
0x10040c3d1  test    dil, 1
0x10040c3d5  jz      short loc_10040C43D
0x10040c3d7  test    dil, 4
0x10040c3db  jnz     short loc_10040C430
0x10040c3dd  mov     rcx, [rbx+8]
0x10040c3e1  test    rcx, rcx
0x10040c3e4  jz      short loc_10040C404
0x10040c3e6  mov     rax, [rcx]
0x10040c3e9  mov     rdx, rbx
0x10040c3ec  mov     rax, [rax+28h]
0x10040c3f0  call    cs:__guard_dispatch_icall_fptr
0x10040c3f6  mov     rax, rbx
0x10040c3f9  mov     rbx, [rsp+28h+arg_0]
0x10040c3fe  add     rsp, 20h
0x10040c402  pop     rdi
0x10040c403  retn
0x10040c404  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c40b  test    rcx, rcx
0x10040c40e  jnz     short loc_10040C3E6
0x10040c410  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c417  mov     r8, rbx; lpMem
0x10040c41a  xor     edx, edx; dwFlags
0x10040c41c  call    cs:__imp_HeapFree
0x10040c422  mov     rax, rbx
0x10040c425  mov     rbx, [rsp+28h+arg_0]
0x10040c42a  add     rsp, 20h
0x10040c42e  pop     rdi
0x10040c42f  retn
0x10040c430  mov     edx, 3A0h; unsigned __int64
0x10040c435  mov     rcx, rbx; void *
0x10040c438  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x10040c43d  mov     rax, rbx
0x10040c440  mov     rbx, [rsp+28h+arg_0]
0x10040c445  add     rsp, 20h
0x10040c449  pop     rdi
0x10040c44a  retn
```
