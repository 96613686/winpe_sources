# SXWriter::streamXfer(IStream *,ulong)

- ea: `0x100408840`
- end: `0x1004089b3`
- name: `?streamXfer@SXWriter@@AEAAXPEAUIStream@@K@Z`
- size: `371`
- prototype: `void __fastcall(SXWriter *__hidden this, struct IStream *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1004097a0`

## callees

- `0x100401350`
- `0x1004086f0`
- `0x100408840`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004088f0`
- `KERNEL32!HeapAlloc` at `0x1004088f0`
- `KERNEL32!HeapFree` at `0x1004088a3`
- `KERNEL32!HeapFree` at `0x1004088a3`

## pseudocode

```c
void __fastcall SXWriter::streamXfer(SXWriter *this, struct IStream *a2, unsigned int a3)
{
  unsigned int v3; // esi
  void *v6; // r8
  struct IMalloc *v7; // rcx
  struct IMalloc *v8; // rcx
  unsigned int v9; // eax
  LPVOID v10; // rax
  char *v11; // rdi
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rbp
  int v15; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v3 = a3;
    if ( *((_DWORD *)this + 85) < a3 )
    {
      v6 = (void *)*((_QWORD *)this + 43);
      v7 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v6 )
      {
        if ( v7 || (v7 = g_pMalloc) != 0 )
          ((void (__fastcall *)(struct IMalloc *, _QWORD))v7->lpVtbl->Free)(v7, *((_QWORD *)this + 43));
        else
          HeapFree(g_hHeap, 0, v6);
      }
      v8 = (struct IMalloc *)*((_QWORD *)this + 1);
      v9 = 2 * *((_DWORD *)this + 85);
      if ( v3 > v9 )
        v9 = v3;
      *((_DWORD *)this + 85) = v9;
      if ( v8 || (v8 = g_pMalloc) != 0 )
        v10 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))v8->lpVtbl->Alloc)(v8, v9);
      else
        v10 = HeapAlloc(g_hHeap, 0, v9);
      if ( !v10 )
      {
        MXRRaiseException(-2147024882);
        __debugbreak();
      }
      *((_QWORD *)this + 43) = v10;
    }
    v11 = (char *)*((_QWORD *)this + 43);
    v12 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, int *))a2->lpVtbl->Read)(a2, v11, v3, &v15);
    if ( v12 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v12);
      __debugbreak();
    }
    if ( v15 != v3 )
    {
      MXRRaiseException(-2147467259);
      JUMPOUT(0x1004089B2LL);
    }
    while ( 1 )
    {
      v13 = v3;
      if ( *((_DWORD *)this + 78) - *((_DWORD *)this + 76) <= v3 )
        v13 = *((_DWORD *)this + 78) - *((_DWORD *)this + 76);
      v14 = v13;
      memmove(*((void **)this + 38), v11, v13);
      *((_QWORD *)this + 38) += v14;
      v3 -= v14;
      if ( !v3 )
        break;
      SXWriter::writeBuffer(this);
      v11 += v14;
    }
  }
}

```

## disassembly

```asm
0x100408840  test    r8d, r8d
0x100408843  jz      locret_100408991
0x100408849  push    rbx
0x10040884a  push    rsi
0x10040884b  push    r14
0x10040884d  sub     rsp, 30h
0x100408851  mov     esi, r8d
0x100408854  mov     r14, rdx
0x100408857  mov     rbx, rcx
0x10040885a  cmp     [rcx+154h], r8d
0x100408861  jnb     loc_100408906
0x100408867  mov     r8, [rbx+158h]; lpMem
0x10040886e  mov     rcx, [rcx+8]
0x100408872  test    r8, r8
0x100408875  jz      short loc_1004088A9
0x100408877  test    rcx, rcx
0x10040887a  jnz     short loc_100408888
0x10040887c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100408883  test    rcx, rcx
0x100408886  jz      short loc_10040889A
0x100408888  mov     rax, [rcx]
0x10040888b  mov     rdx, r8
0x10040888e  mov     rax, [rax+28h]
0x100408892  call    cs:__guard_dispatch_icall_fptr
0x100408898  jmp     short loc_1004088A9
0x10040889a  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004088a1  xor     edx, edx; dwFlags
0x1004088a3  call    cs:__imp_HeapFree
0x1004088a9  mov     eax, [rbx+154h]
0x1004088af  mov     rcx, [rbx+8]
0x1004088b3  add     eax, eax
0x1004088b5  cmp     esi, eax
0x1004088b7  cmova   eax, esi
0x1004088ba  mov     r8d, eax; dwBytes
0x1004088bd  mov     [rbx+154h], r8d
0x1004088c4  test    rcx, rcx
0x1004088c7  jnz     short loc_1004088D5
0x1004088c9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004088d0  test    rcx, rcx
0x1004088d3  jz      short loc_1004088E7
0x1004088d5  mov     rax, [rcx]
0x1004088d8  mov     rdx, r8
0x1004088db  mov     rax, [rax+18h]
0x1004088df  call    cs:__guard_dispatch_icall_fptr
0x1004088e5  jmp     short loc_1004088F6
0x1004088e7  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004088ee  xor     edx, edx; dwFlags
0x1004088f0  call    cs:__imp_HeapAlloc
0x1004088f6  test    rax, rax
0x1004088f9  jz      loc_100408992
0x1004088ff  mov     [rbx+158h], rax
0x100408906  mov     rax, [r14]
0x100408909  lea     r9, [rsp+48h+arg_10]
0x10040890e  mov     [rsp+48h+arg_8], rdi
0x100408913  mov     r8d, esi
0x100408916  mov     rdi, [rbx+158h]
0x10040891d  mov     rcx, r14
0x100408920  mov     rdx, rdi
0x100408923  mov     rax, [rax+18h]
0x100408927  call    cs:__guard_dispatch_icall_fptr
0x10040892d  test    eax, eax
0x10040892f  js      short loc_10040899D
0x100408931  cmp     [rsp+48h+arg_10], esi
0x100408935  jnz     short loc_1004089A8
0x100408937  mov     [rsp+48h+arg_0], rbp
0x10040893c  nop     dword ptr [rax+00h]
0x100408940  mov     ecx, [rbx+138h]
0x100408946  mov     eax, esi
0x100408948  sub     ecx, [rbx+130h]
0x10040894e  mov     rdx, rdi; Src
0x100408951  cmp     ecx, esi
0x100408953  cmovbe  eax, ecx
0x100408956  mov     rcx, [rbx+130h]; void *
0x10040895d  mov     r8d, eax; Size
0x100408960  mov     ebp, eax
0x100408962  call    memmove
0x100408967  add     [rbx+130h], rbp
0x10040896e  sub     esi, ebp
0x100408970  jz      short loc_10040897F
0x100408972  mov     rcx, rbx; this
0x100408975  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040897a  add     rdi, rbp
0x10040897d  jmp     short loc_100408940
0x10040897f  mov     rbp, [rsp+48h+arg_0]
0x100408984  mov     rdi, [rsp+48h+arg_8]
0x100408989  add     rsp, 30h
0x10040898d  pop     r14
0x10040898f  pop     rsi
0x100408990  pop     rbx
0x100408991  retn
0x100408992  mov     ecx, 8007000Eh; int
0x100408997  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040899c  int     3; Trap to Debugger
0x10040899d  lfence
0x1004089a0  mov     ecx, eax; int
0x1004089a2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004089a7  int     3; Trap to Debugger
0x1004089a8  mov     ecx, 80004005h; int
0x1004089ad  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
