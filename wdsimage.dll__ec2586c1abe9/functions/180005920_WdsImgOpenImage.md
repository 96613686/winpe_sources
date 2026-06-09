# WdsImgOpenImage

- ea: `0x180005920`
- end: `0x180005a84`
- name: `WdsImgOpenImage`
- size: `356`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, CImage **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x180003c68`
- `0x180005920`
- `0x18000ae64`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005a12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005a12`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059b1`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059b1`

## pseudocode

```c
__int64 __fastcall WdsImgOpenImage(__int64 a1, const unsigned __int16 *a2, unsigned int a3, CImage **a4)
{
  __int64 v4; // rbx
  CImage *v8; // rax
  CImage *v9; // rax
  CImage *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned __int16 *v21; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  if ( !a2 || !a4 )
    goto LABEL_22;
  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 2 || *(_DWORD *)(a1 + 16) == 3 )
    {
      v4 = a1;
      goto LABEL_7;
    }
LABEL_22:
    LODWORD(v12) = -2147024809;
    return (unsigned int)v12;
  }
LABEL_7:
  v8 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 && (v9 = CImage::CImage(v8), (v10 = v9) != 0) )
  {
    if ( v4 )
    {
      v11 = *(_QWORD *)(v4 + 32);
      v21 = 0;
      v12 = (unsigned int)ConcatenatePaths(v11, a2, &v21);
      if ( (unsigned int)ElValidateWin32_4(v12, v13, v14, 221) )
      {
        if ( (int)v12 > 0 )
          LODWORD(v12) = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        v12 = (unsigned int)CImage::Initialize(v10, v21, a3, 0);
        ElValidateHr_5(v12, v17, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 224);
      }
      if ( v21 )
        operator delete(v21);
      v18 = 236;
      v19 = (unsigned int)v12;
    }
    else
    {
      v12 = (unsigned int)CImage::Initialize(v9, a2, a3, 0);
      v18 = 241;
      v19 = v12;
    }
    if ( (int)ElValidateHr_0(v19, v15, v16, v18) < 0 )
      (*(void (__fastcall **)(CImage *))(*(_QWORD *)v10 + 8LL))(v10);
    else
      *a4 = v10;
  }
  else
  {
    LODWORD(v12) = -2147024882;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005920  mov     [rsp+arg_0], rbx
0x180005925  mov     [rsp+arg_10], rbp
0x18000592a  push    rsi
0x18000592b  push    rdi
0x18000592c  push    r14
0x18000592e  sub     rsp, 20h
0x180005932  xor     ebx, ebx
0x180005934  mov     r14, r9
0x180005937  mov     ebp, r8d
0x18000593a  mov     rsi, rdx
0x18000593d  test    rdx, rdx
0x180005940  jz      loc_180005A69
0x180005946  test    r9, r9
0x180005949  jz      loc_180005A69
0x18000594f  test    rcx, rcx
0x180005952  jz      short loc_180005968
0x180005954  mov     edx, [rcx+10h]
0x180005957  sub     edx, 2
0x18000595a  jz      short loc_180005965
0x18000595c  cmp     edx, 1
0x18000595f  jnz     loc_180005A69
0x180005965  mov     rbx, rcx
0x180005968  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000596f  mov     ecx, 190h; unsigned __int64
0x180005974  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005979  test    rax, rax
0x18000597c  jz      loc_180005A62
0x180005982  mov     rcx, rax; this
0x180005985  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x18000598a  mov     rdi, rax
0x18000598d  test    rax, rax
0x180005990  jz      loc_180005A62
0x180005996  mov     rdx, rsi; unsigned __int16 *
0x180005999  test    rbx, rbx
0x18000599c  jz      loc_180005A28
0x1800059a2  mov     rcx, [rbx+20h]
0x1800059a6  lea     r8, [rsp+38h+arg_8]
0x1800059ab  and     [rsp+38h+arg_8], 0
0x1800059b1  call    cs:__imp_ConcatenatePaths
0x1800059b8  nop     dword ptr [rax+rax+00h]
0x1800059bd  mov     ecx, eax
0x1800059bf  mov     r9d, 0DDh
0x1800059c5  mov     ebx, eax
0x1800059c7  call    ElValidateWin32_4
0x1800059cc  test    eax, eax
0x1800059ce  jz      short loc_1800059DF
0x1800059d0  test    ebx, ebx
0x1800059d2  jle     short loc_180005A08
0x1800059d4  movzx   ebx, bx
0x1800059d7  or      ebx, 80070000h
0x1800059dd  jmp     short loc_180005A08
0x1800059df  mov     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x1800059e4  xor     r9d, r9d; unsigned int
0x1800059e7  mov     r8d, ebp; unsigned int
0x1800059ea  mov     rcx, rdi; this
0x1800059ed  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x1800059f2  mov     r9d, 0E0h
0x1800059f8  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x1800059ff  mov     ecx, eax
0x180005a01  mov     ebx, eax
0x180005a03  call    ElValidateHr_5
0x180005a08  mov     rcx, [rsp+38h+arg_8]
0x180005a0d  test    rcx, rcx
0x180005a10  jz      short loc_180005A1E
0x180005a12  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005a19  nop     dword ptr [rax+rax+00h]
0x180005a1e  mov     r9d, 0ECh
0x180005a24  mov     ecx, ebx
0x180005a26  jmp     short loc_180005A40
0x180005a28  xor     r9d, r9d; unsigned int
0x180005a2b  mov     r8d, ebp; unsigned int
0x180005a2e  mov     rcx, rdi; this
0x180005a31  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x180005a36  mov     ebx, eax
0x180005a38  mov     r9d, 0F1h
0x180005a3e  mov     ecx, eax
0x180005a40  mov     rsi, rdi
0x180005a43  call    ElValidateHr_0
0x180005a48  test    eax, eax
0x180005a4a  js      short loc_180005A51
0x180005a4c  mov     [r14], rdi
0x180005a4f  jmp     short loc_180005A6E
0x180005a51  mov     rax, [rsi]
0x180005a54  mov     rcx, rsi
0x180005a57  mov     rax, [rax+8]
0x180005a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a60  jmp     short loc_180005A6E
0x180005a62  mov     ebx, 8007000Eh
0x180005a67  jmp     short loc_180005A6E
0x180005a69  mov     ebx, 80070057h
0x180005a6e  mov     rbp, [rsp+38h+arg_10]
0x180005a73  mov     eax, ebx
0x180005a75  mov     rbx, [rsp+38h+arg_0]
0x180005a7a  add     rsp, 20h
0x180005a7e  pop     r14
0x180005a80  pop     rdi
0x180005a81  pop     rsi
0x180005a82  retn
```
