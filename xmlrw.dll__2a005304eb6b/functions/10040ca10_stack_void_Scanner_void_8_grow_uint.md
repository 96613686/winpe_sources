# _stack<void (Scanner::*)(void),8>::grow(uint)

- ea: `0x10040ca10`
- end: `0x10040cb2d`
- name: `?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z`
- size: `285`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `35`
- callee_count: `5`
- tags: ``

## callers

- `0x100402f30`
- `0x1004038d0`
- `0x100405110`
- `0x10040a750`
- `0x10040dd40`
- `0x10040ded0`
- `0x10040ee90`
- `0x10040f330`
- `0x10040f530`
- `0x10040fa30`
- `0x100410060`
- `0x1004104a0`
- `0x100410780`
- `0x100410d40`
- `0x100411960`
- `0x100411a50`
- `0x100411bb0`
- `0x100411cf0`
- `0x100411d60`
- `0x1004123a0`
- `0x100412520`
- `0x100412590`
- `0x1004127e0`
- `0x100412a10`
- `0x100412dc0`
- `0x100413250`
- `0x1004134e0`
- `0x1004136f0`
- `0x100413810`
- `0x100413e50`
- `0x100414110`
- `0x100414340`
- `0x1004144b0`
- `0x100414a30`
- `0x100414b40`

## callees

- `0x100401780`
- `0x10040ca10`
- `0x100425d50`
- `0x1004277a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10040ca85`
- `KERNEL32!HeapAlloc` at `0x10040ca85`
- `KERNEL32!HeapFree` at `0x10040cb05`
- `KERNEL32!HeapFree` at `0x10040cb05`

## pseudocode

```c
int __fastcall _stack<void (Scanner::*)(void),8>::grow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // eax
  unsigned int v4; // ebx
  struct IMalloc *v5; // rcx
  char *v6; // rax
  bool v7; // zf
  char *v8; // rsi
  void *v9; // r8
  int result; // eax
  struct IMalloc *v11; // rcx

  v2 = *(_DWORD *)(a1 + 28);
  if ( *(_DWORD *)(a1 + 24) > v2 )
    *(_DWORD *)(a1 + 24) = v2;
  do
  {
    v4 = 2 * v2;
    if ( 2 * v2 < v2 )
      goto LABEL_19;
    v2 *= 2;
  }
  while ( v4 < a2 );
  v5 = *(struct IMalloc **)(a1 + 8);
  if ( v5 )
  {
    _mm_lfence();
LABEL_7:
    v6 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v5->lpVtbl->Alloc)(v5, 8LL * v4);
    goto LABEL_11;
  }
  v7 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v7 )
  {
    v5 = g_pMalloc;
    goto LABEL_7;
  }
  v6 = (char *)HeapAlloc(g_hHeap, 0, 8LL * v4);
LABEL_11:
  v8 = v6;
  if ( !v6 )
  {
LABEL_19:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10040CB2CLL);
  }
  memmove(v6, *(const void **)(a1 + 16), 8LL * *(unsigned int *)(a1 + 24));
  memset(&v8[8 * *(unsigned int *)(a1 + 24)], 0, 8LL * (v4 - *(_DWORD *)(a1 + 24)));
  v9 = *(void **)(a1 + 16);
  result = a1 + 32;
  if ( v9 != (void *)(a1 + 32) )
  {
    v11 = *(struct IMalloc **)(a1 + 8);
    if ( v9 )
    {
      if ( v11 || (v11 = g_pMalloc) != 0 )
        result = ((__int64 (__fastcall *)(struct IMalloc *, _QWORD))v11->lpVtbl->Free)(v11, *(_QWORD *)(a1 + 16));
      else
        result = HeapFree(g_hHeap, 0, v9);
    }
  }
  *(_DWORD *)(a1 + 28) = v4;
  *(_QWORD *)(a1 + 16) = v8;
  return result;
}

```

## disassembly

```asm
0x10040ca10  mov     [rsp+arg_8], rbx
0x10040ca15  push    rdi
0x10040ca16  sub     rsp, 20h
0x10040ca1a  mov     eax, [rcx+1Ch]
0x10040ca1d  mov     rdi, rcx
0x10040ca20  cmp     [rcx+18h], eax
0x10040ca23  jbe     short loc_10040CA28
0x10040ca25  mov     [rcx+18h], eax
0x10040ca28  mov     [rsp+28h+arg_0], rsi
0x10040ca2d  nop     dword ptr [rax]
0x10040ca30  lea     ebx, [rax+rax]
0x10040ca33  cmp     ebx, eax
0x10040ca35  jb      loc_10040CB22
0x10040ca3b  mov     eax, ebx
0x10040ca3d  cmp     ebx, edx
0x10040ca3f  jb      short loc_10040CA30
0x10040ca41  mov     rcx, [rcx+8]
0x10040ca45  mov     r8d, ebx
0x10040ca48  shl     r8, 3; dwBytes
0x10040ca4c  test    rcx, rcx
0x10040ca4f  jz      short loc_10040CA66
0x10040ca51  lfence
0x10040ca54  mov     rax, [rcx]
0x10040ca57  mov     rdx, r8
0x10040ca5a  mov     rax, [rax+18h]
0x10040ca5e  call    cs:__guard_dispatch_icall_fptr
0x10040ca64  jmp     short loc_10040CA8B
0x10040ca66  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x10040ca6e  lfence
0x10040ca71  jz      short loc_10040CA7C
0x10040ca73  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ca7a  jmp     short loc_10040CA54
0x10040ca7c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ca83  xor     edx, edx; dwFlags
0x10040ca85  call    cs:__imp_HeapAlloc
0x10040ca8b  mov     rsi, rax
0x10040ca8e  test    rax, rax
0x10040ca91  jz      loc_10040CB22
0x10040ca97  mov     r8d, [rdi+18h]
0x10040ca9b  mov     rcx, rax; void *
0x10040ca9e  mov     rdx, [rdi+10h]; Src
0x10040caa2  shl     r8, 3; Size
0x10040caa6  call    memmove
0x10040caab  mov     ecx, [rdi+18h]
0x10040caae  mov     r8d, ebx
0x10040cab1  sub     r8d, ecx
0x10040cab4  xor     edx, edx; Val
0x10040cab6  shl     r8, 3; Size
0x10040caba  lea     rcx, [rsi+rcx*8]; void *
0x10040cabe  call    memset
0x10040cac3  mov     r8, [rdi+10h]; lpMem
0x10040cac7  lea     rax, [rdi+20h]
0x10040cacb  cmp     r8, rax
0x10040cace  jz      short loc_10040CB0B
0x10040cad0  mov     rcx, [rdi+8]
0x10040cad4  test    r8, r8
0x10040cad7  jz      short loc_10040CB0B
0x10040cad9  test    rcx, rcx
0x10040cadc  jnz     short loc_10040CAEA
0x10040cade  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040cae5  test    rcx, rcx
0x10040cae8  jz      short loc_10040CAFC
0x10040caea  mov     rax, [rcx]
0x10040caed  mov     rdx, r8
0x10040caf0  mov     rax, [rax+28h]
0x10040caf4  call    cs:__guard_dispatch_icall_fptr
0x10040cafa  jmp     short loc_10040CB0B
0x10040cafc  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040cb03  xor     edx, edx; dwFlags
0x10040cb05  call    cs:__imp_HeapFree
0x10040cb0b  mov     [rdi+1Ch], ebx
0x10040cb0e  mov     rbx, [rsp+28h+arg_8]
0x10040cb13  mov     [rdi+10h], rsi
0x10040cb17  mov     rsi, [rsp+28h+arg_0]
0x10040cb1c  add     rsp, 20h
0x10040cb20  pop     rdi
0x10040cb21  retn
0x10040cb22  mov     ecx, 8007000Eh; int
0x10040cb27  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
