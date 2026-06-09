# SXReadBase::Clear(void)

- ea: `0x10040eb50`
- end: `0x10040eceb`
- name: `?Clear@SXReadBase@@IEAAXXZ`
- size: `411`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100404f80`
- `0x10040e630`

## callees

- `0x10040eb50`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040eb9e`
- `KERNEL32!HeapFree` at `0x10040ebf5`
- `KERNEL32!HeapFree` at `0x10040ec43`
- `KERNEL32!HeapFree` at `0x10040ec91`
- `KERNEL32!HeapFree` at `0x10040eb9e`
- `KERNEL32!HeapFree` at `0x10040ebf5`
- `KERNEL32!HeapFree` at `0x10040ec43`
- `KERNEL32!HeapFree` at `0x10040ec91`

## pseudocode

```c
void __fastcall SXReadBase::Clear(SXReadBase *this)
{
  void *v1; // r8
  struct IMalloc *v3; // rcx
  wchar_t near **v4; // r8
  struct IMalloc *v5; // rcx
  wchar_t near **v6; // r8
  struct IMalloc *v7; // rcx
  wchar_t near **v8; // r8
  struct IMalloc *v9; // rcx
  __int64 v10; // rcx

  v1 = (void *)*((_QWORD *)this + 142);
  if ( v1 )
  {
    v3 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v3 || (v3 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v3->lpVtbl->Free)(v3, v1);
    else
      HeapFree(g_hHeap, 0, v1);
  }
  v4 = (wchar_t near **)*((_QWORD *)this + 175);
  *((_QWORD *)this + 142) = 0;
  if ( v4 != &nullwstr && v4 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, wchar_t near **))v5->lpVtbl->Free)(v5, v4);
    else
      HeapFree(g_hHeap, 0, v4);
  }
  v6 = (wchar_t near **)*((_QWORD *)this + 173);
  *((_QWORD *)this + 175) = 0;
  if ( v6 != &nullwstr && v6 )
  {
    v7 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v7 || (v7 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, wchar_t near **))v7->lpVtbl->Free)(v7, v6);
    else
      HeapFree(g_hHeap, 0, v6);
  }
  v8 = (wchar_t near **)*((_QWORD *)this + 171);
  *((_QWORD *)this + 173) = 0;
  if ( v8 != &nullwstr && v8 )
  {
    v9 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v9 || (v9 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, wchar_t near **))v9->lpVtbl->Free)(v9, v8);
    else
      HeapFree(g_hHeap, 0, v8);
  }
  v10 = *((_QWORD *)this + 90);
  for ( *((_QWORD *)this + 171) = 0; v10; v10 = *((_QWORD *)this + 90) )
  {
    *((_QWORD *)this + 90) = *(_QWORD *)(v10 + 168);
    (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
  }
}

```

## disassembly

```asm
0x10040eb50  mov     [rsp+arg_0], rbx
0x10040eb55  mov     [rsp+arg_8], rsi
0x10040eb5a  push    rdi
0x10040eb5b  sub     rsp, 20h
0x10040eb5f  mov     r8, [rcx+470h]; lpMem
0x10040eb66  mov     rbx, rcx
0x10040eb69  test    r8, r8
0x10040eb6c  jz      short loc_10040EBA4
0x10040eb6e  mov     rcx, [rcx+8]
0x10040eb72  test    rcx, rcx
0x10040eb75  jnz     short loc_10040EB83
0x10040eb77  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040eb7e  test    rcx, rcx
0x10040eb81  jz      short loc_10040EB95
0x10040eb83  mov     rax, [rcx]
0x10040eb86  mov     rdx, r8
0x10040eb89  mov     rax, [rax+28h]
0x10040eb8d  call    cs:__guard_dispatch_icall_fptr
0x10040eb93  jmp     short loc_10040EBA4
0x10040eb95  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040eb9c  xor     edx, edx; dwFlags
0x10040eb9e  call    cs:__imp_HeapFree
0x10040eba4  mov     r8, [rbx+578h]; lpMem
0x10040ebab  lea     rsi, ?nullwstr@@3PA_WA; wchar_t near * nullwstr
0x10040ebb2  xor     edi, edi
0x10040ebb4  mov     [rbx+470h], rdi
0x10040ebbb  cmp     r8, rsi
0x10040ebbe  jz      short loc_10040EBFB
0x10040ebc0  test    r8, r8
0x10040ebc3  jz      short loc_10040EBFB
0x10040ebc5  mov     rcx, [rbx+8]
0x10040ebc9  test    rcx, rcx
0x10040ebcc  jnz     short loc_10040EBDA
0x10040ebce  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ebd5  test    rcx, rcx
0x10040ebd8  jz      short loc_10040EBEC
0x10040ebda  mov     rax, [rcx]
0x10040ebdd  mov     rdx, r8
0x10040ebe0  mov     rax, [rax+28h]
0x10040ebe4  call    cs:__guard_dispatch_icall_fptr
0x10040ebea  jmp     short loc_10040EBFB
0x10040ebec  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ebf3  xor     edx, edx; dwFlags
0x10040ebf5  call    cs:__imp_HeapFree
0x10040ebfb  mov     r8, [rbx+568h]; lpMem
0x10040ec02  mov     [rbx+578h], rdi
0x10040ec09  cmp     r8, rsi
0x10040ec0c  jz      short loc_10040EC49
0x10040ec0e  test    r8, r8
0x10040ec11  jz      short loc_10040EC49
0x10040ec13  mov     rcx, [rbx+8]
0x10040ec17  test    rcx, rcx
0x10040ec1a  jnz     short loc_10040EC28
0x10040ec1c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ec23  test    rcx, rcx
0x10040ec26  jz      short loc_10040EC3A
0x10040ec28  mov     rax, [rcx]
0x10040ec2b  mov     rdx, r8
0x10040ec2e  mov     rax, [rax+28h]
0x10040ec32  call    cs:__guard_dispatch_icall_fptr
0x10040ec38  jmp     short loc_10040EC49
0x10040ec3a  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ec41  xor     edx, edx; dwFlags
0x10040ec43  call    cs:__imp_HeapFree
0x10040ec49  mov     r8, [rbx+558h]; lpMem
0x10040ec50  mov     [rbx+568h], rdi
0x10040ec57  cmp     r8, rsi
0x10040ec5a  jz      short loc_10040EC97
0x10040ec5c  test    r8, r8
0x10040ec5f  jz      short loc_10040EC97
0x10040ec61  mov     rcx, [rbx+8]
0x10040ec65  test    rcx, rcx
0x10040ec68  jnz     short loc_10040EC76
0x10040ec6a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ec71  test    rcx, rcx
0x10040ec74  jz      short loc_10040EC88
0x10040ec76  mov     rax, [rcx]
0x10040ec79  mov     rdx, r8
0x10040ec7c  mov     rax, [rax+28h]
0x10040ec80  call    cs:__guard_dispatch_icall_fptr
0x10040ec86  jmp     short loc_10040EC97
0x10040ec88  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ec8f  xor     edx, edx; dwFlags
0x10040ec91  call    cs:__imp_HeapFree
0x10040ec97  mov     rcx, [rbx+2D0h]
0x10040ec9e  mov     [rbx+558h], rdi
0x10040eca5  test    rcx, rcx
0x10040eca8  jz      short loc_10040ECDB
0x10040ecaa  nop     word ptr [rax+rax+00h]
0x10040ecb0  mov     rax, [rcx+0A8h]
0x10040ecb7  mov     edx, 1
0x10040ecbc  mov     [rbx+2D0h], rax
0x10040ecc3  mov     rax, [rcx]
0x10040ecc6  mov     rax, [rax]
0x10040ecc9  call    cs:__guard_dispatch_icall_fptr
0x10040eccf  mov     rcx, [rbx+2D0h]
0x10040ecd6  test    rcx, rcx
0x10040ecd9  jnz     short loc_10040ECB0
0x10040ecdb  mov     rbx, [rsp+28h+arg_0]
0x10040ece0  mov     rsi, [rsp+28h+arg_8]
0x10040ece5  add     rsp, 20h
0x10040ece9  pop     rdi
0x10040ecea  retn
```
