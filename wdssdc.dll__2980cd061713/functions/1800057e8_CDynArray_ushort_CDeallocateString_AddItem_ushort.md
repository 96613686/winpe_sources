# CDynArray<ushort *,CDeallocateString>::AddItem(ushort *)

- ea: `0x1800057e8`
- end: `0x1800058b7`
- name: `?AddItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005fe8`
- `0x180007214`
- `0x180008ec0`

## callees

- `0x1800015d4`
- `0x180001934`
- `0x1800057e8`
- `0x18000cc1c`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000587f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000587f`

## pseudocode

```c
__int64 __fastcall CDynArray<unsigned short *,CDeallocateString>::AddItem(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ecx
  int v6; // eax
  unsigned int v7; // r15d
  unsigned __int64 v8; // rax
  void *v9; // rax
  void *v10; // r14

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
  v8 = 8LL * v7;
  if ( !is_mul_ok(v7, 8u) )
    v8 = -1;
  v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    memmove_0(v9, *(const void **)a1, 8LL * *(unsigned int *)(a1 + 8));
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = v10;
    *(_DWORD *)(a1 + 8) = v7;
    goto LABEL_11;
  }
  return 8;
}

```

## disassembly

```asm
0x1800057e8  mov     [rsp+arg_8], rbx
0x1800057ed  mov     [rsp+arg_10], rbp
0x1800057f2  push    rsi
0x1800057f3  push    rdi
0x1800057f4  push    r12
0x1800057f6  push    r14
0x1800057f8  push    r15
0x1800057fa  sub     rsp, 20h
0x1800057fe  mov     rbx, rcx
0x180005801  xor     edi, edi
0x180005803  mov     ecx, [rcx+8]
0x180005806  mov     r12, rdx
0x180005809  lea     rsi, [rbx+0Ch]
0x18000580d  mov     rbp, rsi
0x180005810  cmp     [rsi], ecx
0x180005812  jnz     short loc_180005891
0x180005814  lea     edx, [rdi+20h]
0x180005817  mov     eax, ecx
0x180005819  shr     eax, 1
0x18000581b  cmp     eax, edx
0x18000581d  cmovb   eax, edx
0x180005820  lea     r15d, [rcx+rax]
0x180005824  cmp     r15d, ecx
0x180005827  jb      short loc_18000587A
0x180005829  mov     ecx, r15d
0x18000582c  lea     eax, [rdi+8]
0x18000582f  mul     rcx
0x180005832  lea     rcx, [rdi-1]
0x180005836  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000583d  cmovb   rax, rcx
0x180005841  mov     rcx, rax; unsigned __int64
0x180005844  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005849  mov     r14, rax
0x18000584c  test    rax, rax
0x18000584f  jnz     short loc_180005856
0x180005851  lea     edi, [rax+8]
0x180005854  jmp     short loc_18000589D
0x180005856  mov     r8d, [rbx+8]
0x18000585a  mov     rcx, r14; void *
0x18000585d  mov     rdx, [rbx]; Src
0x180005860  shl     r8, 3; Size
0x180005864  call    memmove_0
0x180005869  mov     rcx, [rbx]; Block
0x18000586c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005871  mov     [rbx], r14
0x180005874  mov     [rbx+8], r15d
0x180005878  jmp     short loc_180005891
0x18000587a  mov     ecx, 80070216h
0x18000587f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180005886  nop     dword ptr [rax+rax+00h]
0x18000588b  mov     edi, eax
0x18000588d  test    eax, eax
0x18000588f  jnz     short loc_18000589D
0x180005891  mov     edx, [rsi]
0x180005893  mov     rcx, [rbx]
0x180005896  mov     [rcx+rdx*8], r12
0x18000589a  inc     dword ptr [rbp+0]
0x18000589d  mov     rbx, [rsp+48h+arg_8]
0x1800058a2  mov     eax, edi
0x1800058a4  mov     rbp, [rsp+48h+arg_10]
0x1800058a9  add     rsp, 20h
0x1800058ad  pop     r15
0x1800058af  pop     r14
0x1800058b1  pop     r12
0x1800058b3  pop     rdi
0x1800058b4  pop     rsi
0x1800058b5  retn
```
