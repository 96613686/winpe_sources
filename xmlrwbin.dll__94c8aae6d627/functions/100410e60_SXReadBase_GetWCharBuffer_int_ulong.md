# SXReadBase::GetWCharBuffer(int,ulong)

- ea: `0x100410e60`
- end: `0x100410fec`
- name: `?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z`
- size: `396`
- prototype: `wchar_t *__fastcall(SXReadBase *__hidden this, int, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x10040edb0`
- `0x10040f590`
- `0x10040f9a0`
- `0x10040fbf0`
- `0x10040ff60`
- `0x1004100d0`

## callees

- `0x100401350`
- `0x100410e60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100410ee0`
- `KERNEL32!HeapAlloc` at `0x100410f82`
- `KERNEL32!HeapAlloc` at `0x100410ee0`
- `KERNEL32!HeapAlloc` at `0x100410f82`
- `KERNEL32!HeapFree` at `0x100410fd2`
- `KERNEL32!HeapFree` at `0x100410fd2`

## pseudocode

```c
wchar_t *__fastcall SXReadBase::GetWCharBuffer(SXReadBase *this, int a2, unsigned int a3)
{
  struct IMalloc *v4; // rcx
  bool v5; // of
  SIZE_T v6; // r8
  bool v7; // zf
  wchar_t *result; // rax
  char *v9; // rbx
  struct IMalloc *v10; // rcx
  unsigned int v11; // ebp
  void *v12; // rdi
  SIZE_T v13; // r8
  LPVOID v14; // rax
  struct IMalloc *v15; // rcx

  if ( a3 >= 0x7FFFFFFF )
    goto LABEL_31;
  if ( a2 == -1 )
  {
    v4 = (struct IMalloc *)*((_QWORD *)this + 1);
    v5 = ((a3 + 1) * (unsigned __int128)2uLL) >> 64 != 0;
    v6 = 2LL * (a3 + 1);
    if ( v5 )
      v6 = -1;
    if ( v4 )
    {
      _mm_lfence();
    }
    else
    {
      v7 = g_pMalloc == 0;
      _mm_lfence();
      if ( v7 )
      {
        result = (wchar_t *)HeapAlloc(g_hHeap, 0, v6);
LABEL_11:
        if ( result )
        {
          _mm_lfence();
          return result;
        }
LABEL_31:
        MXRRaiseException(-2147024882);
        JUMPOUT(0x100410FEBLL);
      }
      v4 = g_pMalloc;
    }
    result = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v4->lpVtbl->Alloc)(v4, v6);
    goto LABEL_11;
  }
  v9 = (char *)this + 16 * a2 + 16;
  if ( *(_DWORD *)v9 >= a3 )
    return (wchar_t *)*((_QWORD *)v9 + 1);
  v10 = (struct IMalloc *)*((_QWORD *)this + 1);
  v11 = 2 * *(_DWORD *)v9;
  v12 = (void *)*((_QWORD *)v9 + 1);
  if ( a3 > v11 )
    v11 = a3;
  v13 = 2LL * v11;
  if ( !is_mul_ok(v11, 2u) )
    v13 = -1;
  if ( v10 )
  {
    _mm_lfence();
LABEL_22:
    v14 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v10->lpVtbl->Alloc)(v10, v13);
    goto LABEL_24;
  }
  v7 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v7 )
  {
    v10 = g_pMalloc;
    goto LABEL_22;
  }
  v14 = HeapAlloc(g_hHeap, 0, v13);
LABEL_24:
  if ( !v14 )
    goto LABEL_31;
  *((_QWORD *)v9 + 1) = v14;
  *(_DWORD *)v9 = v11;
  v15 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v12 )
  {
    if ( v15 || (v15 = g_pMalloc) != 0 )
    {
      ((void (__fastcall *)(struct IMalloc *, void *))v15->lpVtbl->Free)(v15, v12);
      return (wchar_t *)*((_QWORD *)v9 + 1);
    }
    HeapFree(g_hHeap, 0, v12);
  }
  return (wchar_t *)*((_QWORD *)v9 + 1);
}

```

## disassembly

```asm
0x100410e60  mov     [rsp+arg_0], rbx
0x100410e65  mov     [rsp+arg_8], rbp
0x100410e6a  mov     [rsp+arg_10], rsi
0x100410e6f  push    rdi
0x100410e70  sub     rsp, 20h
0x100410e74  mov     rsi, rcx
0x100410e77  cmp     r8d, 7FFFFFFFh
0x100410e7e  jnb     loc_100410FE1
0x100410e84  cmp     edx, 0FFFFFFFFh
0x100410e87  jnz     short loc_100410F07
0x100410e89  mov     rcx, [rcx+8]
0x100410e8d  lea     edx, [r8+1]
0x100410e91  mov     eax, 2
0x100410e96  mul     rdx
0x100410e99  mov     r8, rax
0x100410e9c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100410ea3  cmovo   r8, rax; dwBytes
0x100410ea7  test    rcx, rcx
0x100410eaa  jz      short loc_100410EB1
0x100410eac  lfence
0x100410eaf  jmp     short loc_100410EC5
0x100410eb1  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x100410eb9  lfence
0x100410ebc  jz      short loc_100410ED7
0x100410ebe  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410ec5  mov     rax, [rcx]
0x100410ec8  mov     rdx, r8
0x100410ecb  mov     rax, [rax+18h]
0x100410ecf  call    cs:__guard_dispatch_icall_fptr
0x100410ed5  jmp     short loc_100410EE6
0x100410ed7  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410ede  xor     edx, edx; dwFlags
0x100410ee0  call    cs:__imp_HeapAlloc
0x100410ee6  test    rax, rax
0x100410ee9  jz      loc_100410FE1
0x100410eef  lfence
0x100410ef2  mov     rbx, [rsp+28h+arg_0]
0x100410ef7  mov     rbp, [rsp+28h+arg_8]
0x100410efc  mov     rsi, [rsp+28h+arg_10]
0x100410f01  add     rsp, 20h
0x100410f05  pop     rdi
0x100410f06  retn
0x100410f07  movsxd  rbx, edx
0x100410f0a  inc     rbx
0x100410f0d  shl     rbx, 4
0x100410f11  add     rbx, rsi
0x100410f14  mov     eax, [rbx]
0x100410f16  cmp     eax, r8d
0x100410f19  jnb     loc_100410FD8
0x100410f1f  mov     rcx, [rcx+8]
0x100410f23  lea     ebp, [rax+rax]
0x100410f26  mov     rdi, [rbx+8]
0x100410f2a  cmp     r8d, ebp
0x100410f2d  mov     eax, 2
0x100410f32  cmova   ebp, r8d
0x100410f36  mov     edx, ebp
0x100410f38  mul     rdx
0x100410f3b  mov     r8, rax
0x100410f3e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100410f45  cmovo   r8, rax; dwBytes
0x100410f49  test    rcx, rcx
0x100410f4c  jz      short loc_100410F53
0x100410f4e  lfence
0x100410f51  jmp     short loc_100410F67
0x100410f53  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x100410f5b  lfence
0x100410f5e  jz      short loc_100410F79
0x100410f60  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410f67  mov     rax, [rcx]
0x100410f6a  mov     rdx, r8
0x100410f6d  mov     rax, [rax+18h]
0x100410f71  call    cs:__guard_dispatch_icall_fptr
0x100410f77  jmp     short loc_100410F88
0x100410f79  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410f80  xor     edx, edx; dwFlags
0x100410f82  call    cs:__imp_HeapAlloc
0x100410f88  test    rax, rax
0x100410f8b  jz      short loc_100410FE1
0x100410f8d  mov     [rbx+8], rax
0x100410f91  mov     [rbx], ebp
0x100410f93  mov     rcx, [rsi+8]
0x100410f97  test    rdi, rdi
0x100410f9a  jz      short loc_100410FD8
0x100410f9c  test    rcx, rcx
0x100410f9f  jnz     short loc_100410FAD
0x100410fa1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410fa8  test    rcx, rcx
0x100410fab  jz      short loc_100410FC6
0x100410fad  mov     rax, [rcx]
0x100410fb0  mov     rdx, rdi
0x100410fb3  mov     rax, [rax+28h]
0x100410fb7  call    cs:__guard_dispatch_icall_fptr
0x100410fbd  mov     rax, [rbx+8]
0x100410fc1  jmp     loc_100410EF2
0x100410fc6  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410fcd  mov     r8, rdi; lpMem
0x100410fd0  xor     edx, edx; dwFlags
0x100410fd2  call    cs:__imp_HeapFree
0x100410fd8  mov     rax, [rbx+8]
0x100410fdc  jmp     loc_100410EF2
0x100410fe1  mov     ecx, 8007000Eh; int
0x100410fe6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
