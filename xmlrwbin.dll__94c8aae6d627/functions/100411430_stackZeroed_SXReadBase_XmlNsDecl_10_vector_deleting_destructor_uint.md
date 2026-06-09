# _stackZeroed<SXReadBase::XmlNsDecl,10>::`vector deleting destructor'(uint)

- ea: `0x100411430`
- end: `0x10041150b`
- name: `??_E?$_stackZeroed@UXmlNsDecl@SXReadBase@@$09@@UEAAPEAXI@Z`
- size: `219`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1004011f0`
- `0x100411430`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10041148b`
- `KERNEL32!HeapFree` at `0x1004114dc`
- `KERNEL32!HeapFree` at `0x10041148b`
- `KERNEL32!HeapFree` at `0x1004114dc`

## pseudocode

```c
_QWORD *__fastcall _stackZeroed<SXReadBase::XmlNsDecl,10>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  _QWORD *v2; // r8
  struct IMalloc *v5; // rcx
  struct IMalloc *v6; // rcx

  v2 = (_QWORD *)a1[2];
  *a1 = &_stackZeroed<SXReadBase::XmlNsDecl,10>::`vftable';
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
0x100411430  mov     [rsp+arg_0], rbx
0x100411435  push    rdi
0x100411436  sub     rsp, 20h
0x10041143a  mov     r8, [rcx+10h]; lpMem
0x10041143e  lea     rax, ??_7?$_stackZeroed@UXmlNsDecl@SXReadBase@@$09@@6B@; const _stackZeroed<SXReadBase::XmlNsDecl,10>::`vftable'
0x100411445  mov     [rcx], rax
0x100411448  mov     edi, edx
0x10041144a  mov     rbx, rcx
0x10041144d  test    r8, r8
0x100411450  jz      short loc_100411491
0x100411452  lea     rax, [rcx+20h]
0x100411456  cmp     r8, rax
0x100411459  jz      short loc_100411491
0x10041145b  mov     rcx, [rcx+8]
0x10041145f  test    rcx, rcx
0x100411462  jnz     short loc_100411470
0x100411464  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041146b  test    rcx, rcx
0x10041146e  jz      short loc_100411482
0x100411470  mov     rax, [rcx]
0x100411473  mov     rdx, r8
0x100411476  mov     rax, [rax+28h]
0x10041147a  call    cs:__guard_dispatch_icall_fptr
0x100411480  jmp     short loc_100411491
0x100411482  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100411489  xor     edx, edx; dwFlags
0x10041148b  call    cs:__imp_HeapFree
0x100411491  test    dil, 1
0x100411495  jz      short loc_1004114FD
0x100411497  test    dil, 4
0x10041149b  jnz     short loc_1004114F0
0x10041149d  mov     rcx, [rbx+8]
0x1004114a1  test    rcx, rcx
0x1004114a4  jz      short loc_1004114C4
0x1004114a6  mov     rax, [rcx]
0x1004114a9  mov     rdx, rbx
0x1004114ac  mov     rax, [rax+28h]
0x1004114b0  call    cs:__guard_dispatch_icall_fptr
0x1004114b6  mov     rax, rbx
0x1004114b9  mov     rbx, [rsp+28h+arg_0]
0x1004114be  add     rsp, 20h
0x1004114c2  pop     rdi
0x1004114c3  retn
0x1004114c4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004114cb  test    rcx, rcx
0x1004114ce  jnz     short loc_1004114A6
0x1004114d0  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004114d7  mov     r8, rbx; lpMem
0x1004114da  xor     edx, edx; dwFlags
0x1004114dc  call    cs:__imp_HeapFree
0x1004114e2  mov     rax, rbx
0x1004114e5  mov     rbx, [rsp+28h+arg_0]
0x1004114ea  add     rsp, 20h
0x1004114ee  pop     rdi
0x1004114ef  retn
0x1004114f0  mov     edx, 200h; unsigned __int64
0x1004114f5  mov     rcx, rbx; void *
0x1004114f8  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x1004114fd  mov     rax, rbx
0x100411500  mov     rbx, [rsp+28h+arg_0]
0x100411505  add     rsp, 20h
0x100411509  pop     rdi
0x10041150a  retn
```
