# SAXWriter::saveEncoding(wchar_t const *)

- ea: `0x10041d130`
- end: `0x10041d269`
- name: `?saveEncoding@SAXWriter@@QEAAXPEB_W@Z`
- size: `313`
- prototype: `void(SAXWriter *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10041d460`
- `0x10041e750`

## callees

- `0x100401780`
- `0x10041d130`
- `0x100425d50`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041d205`
- `KERNEL32!HeapAlloc` at `0x10041d205`
- `KERNEL32!HeapFree` at `0x10041d1b1`
- `KERNEL32!HeapFree` at `0x10041d1b1`

## pseudocode

```c
void __fastcall SAXWriter::saveEncoding(SAXWriter *this, const wchar_t *a2)
{
  __int64 v3; // rbx
  __int64 v5; // rbx
  char *v6; // r8
  struct IMalloc *v7; // rcx
  struct IMalloc *v8; // rcx
  SIZE_T v9; // r8
  bool v10; // zf
  LPVOID v11; // rax
  void *v12; // rcx

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v5 = (unsigned int)(v3 + 1);
  if ( (unsigned int)v5 <= *((_DWORD *)this + 42) )
  {
    v12 = (void *)*((_QWORD *)this + 20);
    goto LABEL_21;
  }
  v6 = (char *)*((_QWORD *)this + 20);
  if ( v6 != (char *)this + 112 )
  {
    v7 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v6 )
    {
      if ( v7 || (v7 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, char *))v7->lpVtbl->Free)(v7, v6);
      else
        HeapFree(g_hHeap, 0, v6);
    }
  }
  v8 = (struct IMalloc *)*((_QWORD *)this + 1);
  v9 = 2LL * (unsigned int)v5;
  if ( !is_mul_ok((unsigned int)v5, 2u) )
    v9 = -1;
  if ( v8 )
  {
    _mm_lfence();
  }
  else
  {
    v10 = g_pMalloc == 0;
    _mm_lfence();
    if ( v10 )
    {
      v11 = HeapAlloc(g_hHeap, 0, v9);
      goto LABEL_18;
    }
    v8 = g_pMalloc;
  }
  v11 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v8->lpVtbl->Alloc)(v8, v9);
LABEL_18:
  if ( !v11 )
  {
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  *((_QWORD *)this + 20) = v11;
  v12 = v11;
  *((_DWORD *)this + 42) = v5;
LABEL_21:
  if ( 2 * v5 < (unsigned __int64)(unsigned int)v5 )
  {
    MXRRaiseException(-2147467259);
    JUMPOUT(0x10041D268LL);
  }
  _mm_lfence();
  memmove(v12, a2, 2 * v5);
}

```

## disassembly

```asm
0x10041d130  mov     [rsp+arg_0], rbx
0x10041d135  mov     [rsp+arg_8], rbp
0x10041d13a  mov     [rsp+arg_10], rsi
0x10041d13f  push    rdi
0x10041d140  sub     rsp, 20h
0x10041d144  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x10041d14b  mov     rsi, rdx
0x10041d14e  mov     rbx, rbp
0x10041d151  mov     rdi, rcx
0x10041d154  inc     rbx
0x10041d157  cmp     word ptr [rdx+rbx*2], 0
0x10041d15c  jnz     short loc_10041D154
0x10041d15e  inc     ebx
0x10041d160  cmp     ebx, [rcx+0A8h]
0x10041d166  jbe     loc_10041D222
0x10041d16c  mov     r8, [rcx+0A0h]; lpMem
0x10041d173  lea     rax, [rcx+70h]
0x10041d177  cmp     r8, rax
0x10041d17a  jz      short loc_10041D1B7
0x10041d17c  mov     rcx, [rcx+8]
0x10041d180  test    r8, r8
0x10041d183  jz      short loc_10041D1B7
0x10041d185  test    rcx, rcx
0x10041d188  jnz     short loc_10041D196
0x10041d18a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041d191  test    rcx, rcx
0x10041d194  jz      short loc_10041D1A8
0x10041d196  mov     rax, [rcx]
0x10041d199  mov     rdx, r8
0x10041d19c  mov     rax, [rax+28h]
0x10041d1a0  call    cs:__guard_dispatch_icall_fptr
0x10041d1a6  jmp     short loc_10041D1B7
0x10041d1a8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041d1af  xor     edx, edx; dwFlags
0x10041d1b1  call    cs:__imp_HeapFree
0x10041d1b7  mov     rcx, [rdi+8]
0x10041d1bb  mov     eax, 2
0x10041d1c0  mov     edx, ebx
0x10041d1c2  mul     rdx
0x10041d1c5  mov     r8, rax
0x10041d1c8  cmovo   r8, rbp; dwBytes
0x10041d1cc  test    rcx, rcx
0x10041d1cf  jz      short loc_10041D1D6
0x10041d1d1  lfence
0x10041d1d4  jmp     short loc_10041D1EA
0x10041d1d6  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x10041d1de  lfence
0x10041d1e1  jz      short loc_10041D1FC
0x10041d1e3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041d1ea  mov     rax, [rcx]
0x10041d1ed  mov     rdx, r8
0x10041d1f0  mov     rax, [rax+18h]
0x10041d1f4  call    cs:__guard_dispatch_icall_fptr
0x10041d1fa  jmp     short loc_10041D20B
0x10041d1fc  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041d203  xor     edx, edx; dwFlags
0x10041d205  call    cs:__imp_HeapAlloc
0x10041d20b  test    rax, rax
0x10041d20e  jz      short loc_10041D253
0x10041d210  mov     [rdi+0A0h], rax
0x10041d217  mov     rcx, rax
0x10041d21a  mov     [rdi+0A8h], ebx
0x10041d220  jmp     short loc_10041D229
0x10041d222  mov     rcx, [rcx+0A0h]; void *
0x10041d229  mov     eax, ebx
0x10041d22b  lea     r8, [rbx+rbx]; Size
0x10041d22f  cmp     r8, rax
0x10041d232  jb      short loc_10041D25E
0x10041d234  lfence
0x10041d237  mov     rdx, rsi; Src
0x10041d23a  mov     rbx, [rsp+28h+arg_0]
0x10041d23f  mov     rbp, [rsp+28h+arg_8]
0x10041d244  mov     rsi, [rsp+28h+arg_10]
0x10041d249  add     rsp, 20h
0x10041d24d  pop     rdi
0x10041d24e  jmp     memmove
0x10041d253  mov     ecx, 8007000Eh; int
0x10041d258  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041d25d  int     3; Trap to Debugger
0x10041d25e  mov     ecx, 80004005h; int
0x10041d263  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
