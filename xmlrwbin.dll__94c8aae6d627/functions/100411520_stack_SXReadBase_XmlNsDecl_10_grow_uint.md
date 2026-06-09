# _stack<SXReadBase::XmlNsDecl,10>::grow(uint)

- ea: `0x100411520`
- end: `0x10041164a`
- name: `?grow@?$_stack@UXmlNsDecl@SXReadBase@@$09@@AEAAXI@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x100410810`
- `0x100410d20`

## callees

- `0x100401350`
- `0x100411520`
- `0x100415d60`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100411596`
- `KERNEL32!HeapAlloc` at `0x100411596`
- `KERNEL32!HeapFree` at `0x100411622`
- `KERNEL32!HeapFree` at `0x100411622`

## pseudocode

```c
int __fastcall _stack<SXReadBase::XmlNsDecl,10>::grow(__int64 a1, unsigned int a2)
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
    v6 = (char *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v5->lpVtbl->Alloc)(v5, 48 * v4);
    goto LABEL_11;
  }
  v7 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v7 )
  {
    v5 = g_pMalloc;
    goto LABEL_7;
  }
  v6 = (char *)HeapAlloc(g_hHeap, 0, 48 * v4);
LABEL_11:
  v8 = v6;
  if ( !v6 )
  {
LABEL_19:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x100411649LL);
  }
  memmove(v6, *(const void **)(a1 + 16), 48LL * *(unsigned int *)(a1 + 24));
  memset(&v8[48 * *(unsigned int *)(a1 + 24)], 0, 48LL * (unsigned int)(v4 - *(_DWORD *)(a1 + 24)));
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
0x100411520  mov     [rsp+arg_8], rbx
0x100411525  push    rdi
0x100411526  sub     rsp, 20h
0x10041152a  mov     eax, [rcx+1Ch]
0x10041152d  mov     rdi, rcx
0x100411530  cmp     [rcx+18h], eax
0x100411533  jbe     short loc_100411538
0x100411535  mov     [rcx+18h], eax
0x100411538  mov     [rsp+28h+arg_0], rsi
0x10041153d  nop     dword ptr [rax]
0x100411540  lea     ebx, [rax+rax]
0x100411543  cmp     ebx, eax
0x100411545  jb      loc_10041163F
0x10041154b  mov     eax, ebx
0x10041154d  cmp     ebx, edx
0x10041154f  jb      short loc_100411540
0x100411551  mov     rcx, [rcx+8]
0x100411555  lea     r8, [rbx+rbx*2]
0x100411559  shl     r8, 4; dwBytes
0x10041155d  test    rcx, rcx
0x100411560  jz      short loc_100411577
0x100411562  lfence
0x100411565  mov     rax, [rcx]
0x100411568  mov     rdx, r8
0x10041156b  mov     rax, [rax+18h]
0x10041156f  call    cs:__guard_dispatch_icall_fptr
0x100411575  jmp     short loc_10041159C
0x100411577  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x10041157f  lfence
0x100411582  jz      short loc_10041158D
0x100411584  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041158b  jmp     short loc_100411565
0x10041158d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100411594  xor     edx, edx; dwFlags
0x100411596  call    cs:__imp_HeapAlloc
0x10041159c  mov     rsi, rax
0x10041159f  test    rax, rax
0x1004115a2  jz      loc_10041163F
0x1004115a8  mov     eax, [rdi+18h]
0x1004115ab  mov     rcx, rsi; void *
0x1004115ae  mov     rdx, [rdi+10h]; Src
0x1004115b2  lea     r8, [rax+rax*2]
0x1004115b6  shl     r8, 4; Size
0x1004115ba  call    memmove
0x1004115bf  mov     ecx, [rdi+18h]
0x1004115c2  mov     eax, ebx
0x1004115c4  sub     eax, ecx
0x1004115c6  xor     edx, edx; Val
0x1004115c8  lea     rcx, [rcx+rcx*2]
0x1004115cc  lea     r8, [rax+rax*2]
0x1004115d0  shl     rcx, 4
0x1004115d4  shl     r8, 4; Size
0x1004115d8  add     rcx, rsi; void *
0x1004115db  call    memset
0x1004115e0  mov     r8, [rdi+10h]; lpMem
0x1004115e4  lea     rax, [rdi+20h]
0x1004115e8  cmp     r8, rax
0x1004115eb  jz      short loc_100411628
0x1004115ed  mov     rcx, [rdi+8]
0x1004115f1  test    r8, r8
0x1004115f4  jz      short loc_100411628
0x1004115f6  test    rcx, rcx
0x1004115f9  jnz     short loc_100411607
0x1004115fb  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100411602  test    rcx, rcx
0x100411605  jz      short loc_100411619
0x100411607  mov     rax, [rcx]
0x10041160a  mov     rdx, r8
0x10041160d  mov     rax, [rax+28h]
0x100411611  call    cs:__guard_dispatch_icall_fptr
0x100411617  jmp     short loc_100411628
0x100411619  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100411620  xor     edx, edx; dwFlags
0x100411622  call    cs:__imp_HeapFree
0x100411628  mov     [rdi+1Ch], ebx
0x10041162b  mov     rbx, [rsp+28h+arg_8]
0x100411630  mov     [rdi+10h], rsi
0x100411634  mov     rsi, [rsp+28h+arg_0]
0x100411639  add     rsp, 20h
0x10041163d  pop     rdi
0x10041163e  retn
0x10041163f  mov     ecx, 8007000Eh; int
0x100411644  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
