# CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow(void)

- ea: `0x180008c70`
- end: `0x180008d25`
- name: `?Grow@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@AEAAKXZ`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008150`
- `0x1800092ec`

## callees

- `0x1800016b8`
- `0x1800025e4`
- `0x180008c70`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ce6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ce6`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008cff`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180008cff`

## pseudocode

```c
__int64 __fastcall CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow(__int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // ecx
  int v4; // eax
  unsigned int v5; // edx
  unsigned int v6; // ebp
  unsigned __int64 v7; // rax
  void *v8; // rax
  void *v9; // rsi

  v2 = 0;
  v3 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 12) == v3 )
  {
    v4 = v3 >> 1;
    if ( v3 >> 1 < 0x20 )
      v4 = 32;
    v5 = v3 + v4;
    if ( v3 + v4 < v3 )
    {
      return WIN32_FROM_HRESULT(-2147024362);
    }
    else
    {
      v6 = v3 + v4;
      v7 = 8LL * v5;
      if ( !is_mul_ok(v5, 8u) )
        v7 = -1;
      v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        memmove_0(v8, *(const void **)a1, 8LL * *(unsigned int *)(a1 + 8));
        operator delete[](*(void **)a1);
        *(_QWORD *)a1 = v9;
        *(_DWORD *)(a1 + 8) = v6;
      }
      else
      {
        return 8;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180008c70  mov     [rsp+arg_0], rbx
0x180008c75  mov     [rsp+arg_8], rbp
0x180008c7a  mov     [rsp+arg_10], rsi
0x180008c7f  push    rdi
0x180008c80  sub     rsp, 20h
0x180008c84  mov     rbx, rcx
0x180008c87  xor     edi, edi
0x180008c89  mov     ecx, [rcx+8]
0x180008c8c  cmp     [rbx+0Ch], ecx
0x180008c8f  jnz     short loc_180008D0D
0x180008c91  lea     edx, [rdi+20h]
0x180008c94  mov     eax, ecx
0x180008c96  shr     eax, 1
0x180008c98  cmp     eax, edx
0x180008c9a  cmovb   eax, edx
0x180008c9d  lea     edx, [rcx+rax]
0x180008ca0  cmp     edx, ecx
0x180008ca2  jb      short loc_180008CFA
0x180008ca4  mov     ebp, edx
0x180008ca6  lea     rcx, [rdi-1]
0x180008caa  lea     eax, [rdi+8]
0x180008cad  mul     rbp
0x180008cb0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008cb7  cmovo   rax, rcx
0x180008cbb  mov     rcx, rax; unsigned __int64
0x180008cbe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008cc3  mov     rsi, rax
0x180008cc6  test    rax, rax
0x180008cc9  jnz     short loc_180008CD0
0x180008ccb  lea     edi, [rax+8]
0x180008cce  jmp     short loc_180008D0D
0x180008cd0  mov     r8d, [rbx+8]
0x180008cd4  mov     rcx, rsi; void *
0x180008cd7  mov     rdx, [rbx]; Src
0x180008cda  shl     r8, 3; Size
0x180008cde  call    memmove_0
0x180008ce3  mov     rcx, [rbx]
0x180008ce6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008ced  nop     dword ptr [rax+rax+00h]
0x180008cf2  mov     [rbx], rsi
0x180008cf5  mov     [rbx+8], ebp
0x180008cf8  jmp     short loc_180008D0D
0x180008cfa  mov     ecx, 80070216h
0x180008cff  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180008d06  nop     dword ptr [rax+rax+00h]
0x180008d0b  mov     edi, eax
0x180008d0d  mov     rbx, [rsp+28h+arg_0]
0x180008d12  mov     eax, edi
0x180008d14  mov     rbp, [rsp+28h+arg_8]
0x180008d19  mov     rsi, [rsp+28h+arg_10]
0x180008d1e  add     rsp, 20h
0x180008d22  pop     rdi
0x180008d23  retn
```
