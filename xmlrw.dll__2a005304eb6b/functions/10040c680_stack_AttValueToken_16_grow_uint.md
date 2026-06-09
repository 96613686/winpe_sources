# _stack<AttValueToken,16>::grow(uint)

- ea: `0x10040c680`
- end: `0x10040c7a7`
- name: `?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z`
- size: `295`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100404670`
- `0x1004055d0`

## callees

- `0x100401780`
- `0x10040c680`
- `0x100425d50`
- `0x1004277a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10040c6f6`
- `KERNEL32!HeapAlloc` at `0x10040c6f6`
- `KERNEL32!HeapFree` at `0x10040c77f`
- `KERNEL32!HeapFree` at `0x10040c77f`

## pseudocode

```c
int __fastcall _stack<AttValueToken,16>::grow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // eax
  __int64 v4; // rbx
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
    if ( (unsigned int)v4 < v2 )
      goto LABEL_19;
    v2 *= 2;
  }
  while ( (unsigned int)v4 < a2 );
  v5 = *(struct IMalloc **)(a1 + 8);
  if ( v5 )
  {
    _mm_lfence();
LABEL_7:
    v6 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v5->lpVtbl->Alloc)(v5, 24 * v4);
    goto LABEL_11;
  }
  v7 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v7 )
  {
    v5 = g_pMalloc;
    goto LABEL_7;
  }
  v6 = (char *)HeapAlloc(g_hHeap, 0, 24 * v4);
LABEL_11:
  v8 = v6;
  if ( !v6 )
  {
LABEL_19:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10040C7A6LL);
  }
  memmove(v6, *(const void **)(a1 + 16), 24LL * *(unsigned int *)(a1 + 24));
  memset(&v8[24 * *(unsigned int *)(a1 + 24)], 0, 24LL * (unsigned int)(v4 - *(_DWORD *)(a1 + 24)));
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
0x10040c680  mov     [rsp+arg_8], rbx
0x10040c685  push    rdi
0x10040c686  sub     rsp, 20h
0x10040c68a  mov     eax, [rcx+1Ch]
0x10040c68d  mov     rdi, rcx
0x10040c690  cmp     [rcx+18h], eax
0x10040c693  jbe     short loc_10040C698
0x10040c695  mov     [rcx+18h], eax
0x10040c698  mov     [rsp+28h+arg_0], rsi
0x10040c69d  nop     dword ptr [rax]
0x10040c6a0  lea     ebx, [rax+rax]
0x10040c6a3  cmp     ebx, eax
0x10040c6a5  jb      loc_10040C79C
0x10040c6ab  mov     eax, ebx
0x10040c6ad  cmp     ebx, edx
0x10040c6af  jb      short loc_10040C6A0
0x10040c6b1  mov     rcx, [rcx+8]
0x10040c6b5  lea     r8, [rbx+rbx*2]
0x10040c6b9  shl     r8, 3; dwBytes
0x10040c6bd  test    rcx, rcx
0x10040c6c0  jz      short loc_10040C6D7
0x10040c6c2  lfence
0x10040c6c5  mov     rax, [rcx]
0x10040c6c8  mov     rdx, r8
0x10040c6cb  mov     rax, [rax+18h]
0x10040c6cf  call    cs:__guard_dispatch_icall_fptr
0x10040c6d5  jmp     short loc_10040C6FC
0x10040c6d7  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x10040c6df  lfence
0x10040c6e2  jz      short loc_10040C6ED
0x10040c6e4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c6eb  jmp     short loc_10040C6C5
0x10040c6ed  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c6f4  xor     edx, edx; dwFlags
0x10040c6f6  call    cs:__imp_HeapAlloc
0x10040c6fc  mov     rsi, rax
0x10040c6ff  test    rax, rax
0x10040c702  jz      loc_10040C79C
0x10040c708  mov     eax, [rdi+18h]
0x10040c70b  mov     rcx, rsi; void *
0x10040c70e  mov     rdx, [rdi+10h]; Src
0x10040c712  lea     r8, [rax+rax*2]
0x10040c716  shl     r8, 3; Size
0x10040c71a  call    memmove
0x10040c71f  mov     ecx, [rdi+18h]
0x10040c722  mov     eax, ebx
0x10040c724  sub     eax, ecx
0x10040c726  xor     edx, edx; Val
0x10040c728  lea     r8, [rax+rax*2]
0x10040c72c  lea     rax, [rcx+rcx*2]
0x10040c730  shl     r8, 3; Size
0x10040c734  lea     rcx, [rsi+rax*8]; void *
0x10040c738  call    memset
0x10040c73d  mov     r8, [rdi+10h]; lpMem
0x10040c741  lea     rax, [rdi+20h]
0x10040c745  cmp     r8, rax
0x10040c748  jz      short loc_10040C785
0x10040c74a  mov     rcx, [rdi+8]
0x10040c74e  test    r8, r8
0x10040c751  jz      short loc_10040C785
0x10040c753  test    rcx, rcx
0x10040c756  jnz     short loc_10040C764
0x10040c758  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040c75f  test    rcx, rcx
0x10040c762  jz      short loc_10040C776
0x10040c764  mov     rax, [rcx]
0x10040c767  mov     rdx, r8
0x10040c76a  mov     rax, [rax+28h]
0x10040c76e  call    cs:__guard_dispatch_icall_fptr
0x10040c774  jmp     short loc_10040C785
0x10040c776  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040c77d  xor     edx, edx; dwFlags
0x10040c77f  call    cs:__imp_HeapFree
0x10040c785  mov     [rdi+1Ch], ebx
0x10040c788  mov     rbx, [rsp+28h+arg_8]
0x10040c78d  mov     [rdi+10h], rsi
0x10040c791  mov     rsi, [rsp+28h+arg_0]
0x10040c796  add     rsp, 20h
0x10040c79a  pop     rdi
0x10040c79b  retn
0x10040c79c  mov     ecx, 8007000Eh; int
0x10040c7a1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
