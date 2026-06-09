# CDynArray<ushort *,CDeallocateString>::Grow(void)

- ea: `0x18000e054`
- end: `0x18000e109`
- name: `?Grow@?$CDynArray@PEAGVCDeallocateString@@@@AEAAKXZ`
- size: `181`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d1b8`
- `0x18000d270`
- `0x18000df74`
- `0x18000e5f8`
- `0x18000e724`

## callees

- `0x1800016b8`
- `0x1800025e4`
- `0x18000e054`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e0ca`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e0ca`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000e0e3`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000e0e3`

## pseudocode

```c
__int64 __fastcall CDynArray<unsigned short *,CDeallocateString>::Grow(__int64 a1)
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
        operator delete(*(void **)a1);
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
0x18000e054  mov     [rsp+arg_0], rbx
0x18000e059  mov     [rsp+arg_8], rbp
0x18000e05e  mov     [rsp+arg_10], rsi
0x18000e063  push    rdi
0x18000e064  sub     rsp, 20h
0x18000e068  mov     rbx, rcx
0x18000e06b  xor     edi, edi
0x18000e06d  mov     ecx, [rcx+8]
0x18000e070  cmp     [rbx+0Ch], ecx
0x18000e073  jnz     short loc_18000E0F1
0x18000e075  lea     edx, [rdi+20h]
0x18000e078  mov     eax, ecx
0x18000e07a  shr     eax, 1
0x18000e07c  cmp     eax, edx
0x18000e07e  cmovb   eax, edx
0x18000e081  lea     edx, [rcx+rax]
0x18000e084  cmp     edx, ecx
0x18000e086  jb      short loc_18000E0DE
0x18000e088  mov     ebp, edx
0x18000e08a  lea     rcx, [rdi-1]
0x18000e08e  lea     eax, [rdi+8]
0x18000e091  mul     rbp
0x18000e094  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e09b  cmovo   rax, rcx
0x18000e09f  mov     rcx, rax; unsigned __int64
0x18000e0a2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e0a7  mov     rsi, rax
0x18000e0aa  test    rax, rax
0x18000e0ad  jnz     short loc_18000E0B4
0x18000e0af  lea     edi, [rax+8]
0x18000e0b2  jmp     short loc_18000E0F1
0x18000e0b4  mov     r8d, [rbx+8]
0x18000e0b8  mov     rcx, rsi; void *
0x18000e0bb  mov     rdx, [rbx]; Src
0x18000e0be  shl     r8, 3; Size
0x18000e0c2  call    memmove_0
0x18000e0c7  mov     rcx, [rbx]
0x18000e0ca  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e0d1  nop     dword ptr [rax+rax+00h]
0x18000e0d6  mov     [rbx], rsi
0x18000e0d9  mov     [rbx+8], ebp
0x18000e0dc  jmp     short loc_18000E0F1
0x18000e0de  mov     ecx, 80070216h
0x18000e0e3  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000e0ea  nop     dword ptr [rax+rax+00h]
0x18000e0ef  mov     edi, eax
0x18000e0f1  mov     rbx, [rsp+28h+arg_0]
0x18000e0f6  mov     eax, edi
0x18000e0f8  mov     rbp, [rsp+28h+arg_8]
0x18000e0fd  mov     rsi, [rsp+28h+arg_10]
0x18000e102  add     rsp, 20h
0x18000e106  pop     rdi
0x18000e107  retn
```
