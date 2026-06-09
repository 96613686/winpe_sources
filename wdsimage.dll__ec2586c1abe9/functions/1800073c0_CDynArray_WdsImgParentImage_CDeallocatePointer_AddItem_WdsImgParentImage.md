# CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)

- ea: `0x1800073c0`
- end: `0x18000748b`
- name: `?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z`
- size: `203`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800074f8`
- `0x18000844c`
- `0x1800096c0`
- `0x18000a13c`
- `0x18000a948`
- `0x18000d300`

## callees

- `0x1800015d8`
- `0x1800024b4`
- `0x1800073c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000743c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000743c`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180007456`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180007456`

## pseudocode

```c
__int64 __fastcall CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ecx
  int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // r14d
  unsigned __int64 v9; // rax
  void *v10; // rax
  void *v11; // rsi

  v3 = 0;
  v4 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 12) != v4 )
    goto LABEL_11;
  v6 = v4 >> 1;
  if ( v4 >> 1 < 0x20 )
    v6 = 32;
  v7 = v4 + v6;
  if ( v4 + v6 < v4 )
  {
    v3 = WIN32_FROM_HRESULT(-2147024362);
    if ( v3 )
      return v3;
LABEL_11:
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a1 + 12))++) = a2;
    return v3;
  }
  v8 = v4 + v6;
  v9 = 8LL * v7;
  if ( !is_mul_ok(v7, 8u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    memmove_0(v10, *(const void **)a1, 8LL * *(unsigned int *)(a1 + 8));
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = v11;
    *(_DWORD *)(a1 + 8) = v8;
    goto LABEL_11;
  }
  return 8;
}

```

## disassembly

```asm
0x1800073c0  mov     [rsp+arg_8], rbx
0x1800073c5  mov     [rsp+arg_10], rbp
0x1800073ca  push    rsi
0x1800073cb  push    rdi
0x1800073cc  push    r14
0x1800073ce  sub     rsp, 20h
0x1800073d2  mov     rbx, rcx
0x1800073d5  xor     edi, edi
0x1800073d7  mov     ecx, [rcx+8]
0x1800073da  mov     rbp, rdx
0x1800073dd  cmp     [rbx+0Ch], ecx
0x1800073e0  jnz     loc_180007468
0x1800073e6  lea     edx, [rdi+20h]
0x1800073e9  mov     eax, ecx
0x1800073eb  shr     eax, 1
0x1800073ed  cmp     eax, edx
0x1800073ef  cmovb   eax, edx
0x1800073f2  lea     edx, [rcx+rax]
0x1800073f5  cmp     edx, ecx
0x1800073f7  jb      short loc_180007451
0x1800073f9  mov     r14d, edx
0x1800073fc  lea     rcx, [rdi-1]
0x180007400  lea     eax, [rdi+8]
0x180007403  mul     r14
0x180007406  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000740d  cmovo   rax, rcx
0x180007411  mov     rcx, rax; unsigned __int64
0x180007414  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007419  mov     rsi, rax
0x18000741c  test    rax, rax
0x18000741f  jnz     short loc_180007426
0x180007421  lea     edi, [rax+8]
0x180007424  jmp     short loc_180007475
0x180007426  mov     r8d, [rbx+8]
0x18000742a  mov     rcx, rsi; void *
0x18000742d  mov     rdx, [rbx]; Src
0x180007430  shl     r8, 3; Size
0x180007434  call    memmove_0
0x180007439  mov     rcx, [rbx]
0x18000743c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007443  nop     dword ptr [rax+rax+00h]
0x180007448  mov     [rbx], rsi
0x18000744b  mov     [rbx+8], r14d
0x18000744f  jmp     short loc_180007468
0x180007451  mov     ecx, 80070216h
0x180007456  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000745d  nop     dword ptr [rax+rax+00h]
0x180007462  mov     edi, eax
0x180007464  test    eax, eax
0x180007466  jnz     short loc_180007475
0x180007468  mov     edx, [rbx+0Ch]
0x18000746b  mov     rcx, [rbx]
0x18000746e  mov     [rcx+rdx*8], rbp
0x180007472  inc     dword ptr [rbx+0Ch]
0x180007475  mov     rbx, [rsp+38h+arg_8]
0x18000747a  mov     eax, edi
0x18000747c  mov     rbp, [rsp+38h+arg_10]
0x180007481  add     rsp, 20h
0x180007485  pop     r14
0x180007487  pop     rdi
0x180007488  pop     rsi
0x180007489  retn
```
