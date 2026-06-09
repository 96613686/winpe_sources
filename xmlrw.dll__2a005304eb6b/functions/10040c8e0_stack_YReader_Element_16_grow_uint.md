# _stack<YReader::Element,16>::grow(uint)

- ea: `0x10040c8e0`
- end: `0x10040c9fc`
- name: `?grow@?$_stack@UElement@YReader@@$0BA@@@AEAAXI@Z`
- size: `284`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x100407840`
- `0x1004079d0`
- `0x100408ba0`

## callees

- `0x100401780`
- `0x10040c8e0`
- `0x100425d50`
- `0x1004277a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10040c954`
- `KERNEL32!HeapAlloc` at `0x10040c954`
- `KERNEL32!HeapFree` at `0x10040c9d4`
- `KERNEL32!HeapFree` at `0x10040c9d4`

## pseudocode

```c
int __fastcall _stack<YReader::Element,16>::grow(__int64 a1, unsigned int a2)
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
    v6 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v5->lpVtbl->Alloc)(v5, 56LL * v4);
    goto LABEL_11;
  }
  v7 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v7 )
  {
    v5 = g_pMalloc;
    goto LABEL_7;
  }
  v6 = (char *)HeapAlloc(g_hHeap, 0, 56LL * v4);
LABEL_11:
  v8 = v6;
  if ( !v6 )
  {
LABEL_19:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10040C9FBLL);
  }
  memmove(v6, *(const void **)(a1 + 16), 56LL * *(unsigned int *)(a1 + 24));
  memset(&v8[56 * *(unsigned int *)(a1 + 24)], 0, 56LL * (v4 - *(_DWORD *)(a1 + 24)));
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
0x10040c8e0  mov     [rsp+arg_8], rbx
0x10040c8e5  push    rdi
0x10040c8e6  sub     rsp, 20h
0x10040c8ea  mov     eax, [rcx+1Ch]
0x10040c8ed  mov     rdi, rcx
0x10040c8f0  cmp     [rcx+18h], eax
0x10040c8f3  jbe     short loc_10040C8F8
0x10040c8f5  mov     [rcx+18h], eax
0x10040c8f8  mov     [rsp+28h+arg_0], rsi
0x10040c8fd  nop     dword ptr [rax]
0x10040c900  lea     ebx, [rax+rax]
0x10040c903  cmp     ebx, eax
0x10040c905  jb      loc_10040C9F1
0x10040c90b  mov     eax, ebx
0x10040c90d  cmp     ebx, edx
0x10040c90f  jb      short loc_10040C900
0x10040c911  mov     rcx, [rcx+8]
0x10040c915  mov     eax, ebx
0x10040c917  imul    r8, rax, 38h ; '8'; dwBytes
0x10040c91b  test    rcx, rcx
0x10040c91e  jz      short loc_10040C935
0x10040c920  lfence
0x10040c923  mov     rax, [rcx]
0x10040c926  mov     rdx, r8
0x10040c929  mov     rax, [rax+18h]
0x10040c92d  call    cs:__guard_dispatch_icall_fptr
0x10040c933  jmp     short loc_10040C95A
0x10040c935  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x10040c93d  lfence
0x10040c940  jz      short loc_10040C94B
0x10040c942  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c949  jmp     short loc_10040C923
0x10040c94b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c952  xor     edx, edx; dwFlags
0x10040c954  call    cs:__imp_HeapAlloc
0x10040c95a  mov     rsi, rax
0x10040c95d  test    rax, rax
0x10040c960  jz      loc_10040C9F1
0x10040c966  mov     eax, [rdi+18h]
0x10040c969  mov     rcx, rsi; void *
0x10040c96c  mov     rdx, [rdi+10h]; Src
0x10040c970  imul    r8, rax, 38h ; '8'; Size
0x10040c974  call    memmove
0x10040c979  mov     ecx, [rdi+18h]
0x10040c97c  mov     eax, ebx
0x10040c97e  sub     eax, ecx
0x10040c980  xor     edx, edx; Val
0x10040c982  imul    rcx, 38h ; '8'
0x10040c986  imul    r8, rax, 38h ; '8'; Size
0x10040c98a  add     rcx, rsi; void *
0x10040c98d  call    memset
0x10040c992  mov     r8, [rdi+10h]; lpMem
0x10040c996  lea     rax, [rdi+20h]
0x10040c99a  cmp     r8, rax
0x10040c99d  jz      short loc_10040C9DA
0x10040c99f  mov     rcx, [rdi+8]
0x10040c9a3  test    r8, r8
0x10040c9a6  jz      short loc_10040C9DA
0x10040c9a8  test    rcx, rcx
0x10040c9ab  jnz     short loc_10040C9B9
0x10040c9ad  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c9b4  test    rcx, rcx
0x10040c9b7  jz      short loc_10040C9CB
0x10040c9b9  mov     rax, [rcx]
0x10040c9bc  mov     rdx, r8
0x10040c9bf  mov     rax, [rax+28h]
0x10040c9c3  call    cs:__guard_dispatch_icall_fptr
0x10040c9c9  jmp     short loc_10040C9DA
0x10040c9cb  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c9d2  xor     edx, edx; dwFlags
0x10040c9d4  call    cs:__imp_HeapFree
0x10040c9da  mov     [rdi+1Ch], ebx
0x10040c9dd  mov     rbx, [rsp+28h+arg_8]
0x10040c9e2  mov     [rdi+10h], rsi
0x10040c9e6  mov     rsi, [rsp+28h+arg_0]
0x10040c9eb  add     rsp, 20h
0x10040c9ef  pop     rdi
0x10040c9f0  retn
0x10040c9f1  mov     ecx, 8007000Eh; int
0x10040c9f6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
