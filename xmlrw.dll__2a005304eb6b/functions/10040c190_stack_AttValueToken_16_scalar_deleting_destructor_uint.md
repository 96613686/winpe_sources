# _stack<AttValueToken,16>::`scalar deleting destructor'(uint)

- ea: `0x10040c190`
- end: `0x10040c26b`
- name: `??_G?$_stack@UAttValueToken@@$0BA@@@UEAAPEAXI@Z`
- size: `219`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100401310`
- `0x10040c190`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040c1eb`
- `KERNEL32!HeapFree` at `0x10040c23c`
- `KERNEL32!HeapFree` at `0x10040c1eb`
- `KERNEL32!HeapFree` at `0x10040c23c`

## pseudocode

```c
_QWORD *__fastcall _stack<AttValueToken,16>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  _QWORD *v2; // r8
  struct IMalloc *v5; // rcx
  struct IMalloc *v6; // rcx

  v2 = (_QWORD *)a1[2];
  *a1 = &_stack<AttValueToken,16>::`vftable';
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
0x10040c190  mov     [rsp+arg_0], rbx
0x10040c195  push    rdi
0x10040c196  sub     rsp, 20h
0x10040c19a  mov     r8, [rcx+10h]; lpMem
0x10040c19e  lea     rax, ??_7?$_stack@UAttValueToken@@$0BA@@@6B@; const _stack<AttValueToken,16>::`vftable'
0x10040c1a5  mov     [rcx], rax
0x10040c1a8  mov     edi, edx
0x10040c1aa  mov     rbx, rcx
0x10040c1ad  test    r8, r8
0x10040c1b0  jz      short loc_10040C1F1
0x10040c1b2  lea     rax, [rcx+20h]
0x10040c1b6  cmp     r8, rax
0x10040c1b9  jz      short loc_10040C1F1
0x10040c1bb  mov     rcx, [rcx+8]
0x10040c1bf  test    rcx, rcx
0x10040c1c2  jnz     short loc_10040C1D0
0x10040c1c4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c1cb  test    rcx, rcx
0x10040c1ce  jz      short loc_10040C1E2
0x10040c1d0  mov     rax, [rcx]
0x10040c1d3  mov     rdx, r8
0x10040c1d6  mov     rax, [rax+28h]
0x10040c1da  call    cs:__guard_dispatch_icall_fptr
0x10040c1e0  jmp     short loc_10040C1F1
0x10040c1e2  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c1e9  xor     edx, edx; dwFlags
0x10040c1eb  call    cs:__imp_HeapFree
0x10040c1f1  test    dil, 1
0x10040c1f5  jz      short loc_10040C25D
0x10040c1f7  test    dil, 4
0x10040c1fb  jnz     short loc_10040C250
0x10040c1fd  mov     rcx, [rbx+8]
0x10040c201  test    rcx, rcx
0x10040c204  jz      short loc_10040C224
0x10040c206  mov     rax, [rcx]
0x10040c209  mov     rdx, rbx
0x10040c20c  mov     rax, [rax+28h]
0x10040c210  call    cs:__guard_dispatch_icall_fptr
0x10040c216  mov     rax, rbx
0x10040c219  mov     rbx, [rsp+28h+arg_0]
0x10040c21e  add     rsp, 20h
0x10040c222  pop     rdi
0x10040c223  retn
0x10040c224  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c22b  test    rcx, rcx
0x10040c22e  jnz     short loc_10040C206
0x10040c230  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c237  mov     r8, rbx; lpMem
0x10040c23a  xor     edx, edx; dwFlags
0x10040c23c  call    cs:__imp_HeapFree
0x10040c242  mov     rax, rbx
0x10040c245  mov     rbx, [rsp+28h+arg_0]
0x10040c24a  add     rsp, 20h
0x10040c24e  pop     rdi
0x10040c24f  retn
0x10040c250  mov     edx, 1A0h; unsigned __int64
0x10040c255  mov     rcx, rbx; void *
0x10040c258  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x10040c25d  mov     rax, rbx
0x10040c260  mov     rbx, [rsp+28h+arg_0]
0x10040c265  add     rsp, 20h
0x10040c269  pop     rdi
0x10040c26a  retn
```
