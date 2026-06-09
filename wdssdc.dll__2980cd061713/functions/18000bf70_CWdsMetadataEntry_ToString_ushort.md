# CWdsMetadataEntry::ToString(ushort * *)

- ea: `0x18000bf70`
- end: `0x18000c0a8`
- name: `?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z`
- size: `312`
- prototype: `unsigned int __fastcall(CWdsMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005fe8`
- `0x18000906c`
- `0x18000b6d4`
- `0x18000c7f8`

## callees

- `0x1800015d4`
- `0x180001934`
- `0x18000befc`
- `0x18000bf70`
- `0x18000c178`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c06f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c06f`

## pseudocode

```c
__int64 __fastcall CWdsMetadataEntry::ToString(CWdsMetadataEntry *this, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rsi
  __int64 v13; // r9
  __int64 *v14; // r8
  __int64 *v15; // rcx
  __int64 *v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8

  v2 = 0;
  v4 = *(_QWORD *)this;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v5 += v8 + 2;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v9) );
  v10 = v5 + v9 + 2;
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    v13 = *((_QWORD *)this + 2);
    v14 = (__int64 *)L"]";
    v15 = &qword_18000F478;
    v16 = (__int64 *)L"[";
    if ( v13 )
      v15 = (__int64 *)*((_QWORD *)this + 2);
    else
      v14 = &qword_18000F478;
    if ( !v13 )
      v16 = &qword_18000F478;
    v17 = StringCchPrintfW(v12, v10, L"%s%s%s%s=%s", *(_QWORD *)this, v16, v15, v14, *((_QWORD *)this + 1));
    if ( (int)ElValidateHr_1(v17, v18, v19, 2545) >= 0 )
    {
      *a2 = v12;
    }
    else
    {
      v2 = WIN32_FROM_HRESULT(v17);
      operator delete(v12);
    }
  }
  else
  {
    return 8;
  }
  return v2;
}

```

## disassembly

```asm
0x18000bf70  mov     rax, rsp
0x18000bf73  mov     [rax+8], rbx
0x18000bf77  mov     [rax+10h], rbp
0x18000bf7b  mov     [rax+18h], rsi
0x18000bf7f  mov     [rax+20h], rdi
0x18000bf83  push    r14
0x18000bf85  sub     rsp, 40h
0x18000bf89  xor     ebx, ebx
0x18000bf8b  mov     rdi, rcx
0x18000bf8e  mov     rcx, [rcx]
0x18000bf91  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bf95  mov     rax, r8
0x18000bf98  mov     r14, rdx
0x18000bf9b  inc     rax
0x18000bf9e  cmp     [rcx+rax*2], bx
0x18000bfa2  jnz     short loc_18000BF9B
0x18000bfa4  mov     rdx, [rdi+10h]
0x18000bfa8  test    rdx, rdx
0x18000bfab  jz      short loc_18000BFC0
0x18000bfad  mov     rcx, r8
0x18000bfb0  inc     rcx
0x18000bfb3  cmp     [rdx+rcx*2], bx
0x18000bfb7  jnz     short loc_18000BFB0
0x18000bfb9  add     rax, 2
0x18000bfbd  add     rax, rcx
0x18000bfc0  mov     rdx, [rdi+8]
0x18000bfc4  mov     rcx, r8
0x18000bfc7  inc     rcx
0x18000bfca  cmp     [rdx+rcx*2], bx
0x18000bfce  jnz     short loc_18000BFC7
0x18000bfd0  lea     rbp, [rcx+2]
0x18000bfd4  add     rbp, rax
0x18000bfd7  mov     eax, 2
0x18000bfdc  mul     rbp
0x18000bfdf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bfe6  cmovb   rax, r8
0x18000bfea  mov     rcx, rax; unsigned __int64
0x18000bfed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000bff2  mov     rsi, rax
0x18000bff5  test    rax, rax
0x18000bff8  jnz     short loc_18000C002
0x18000bffa  lea     ebx, [rax+8]
0x18000bffd  jmp     loc_18000C08A
0x18000c002  mov     r9, [rdi+10h]
0x18000c006  lea     rdx, qword_18000F478
0x18000c00d  mov     r10, [rdi+8]
0x18000c011  lea     r8, asc_18000F924; "]"
0x18000c018  test    r9, r9
0x18000c01b  mov     [rsp+48h+var_10], r10
0x18000c020  mov     rcx, rdx
0x18000c023  lea     rax, asc_18000F928; "["
0x18000c02a  cmovz   r8, rdx
0x18000c02e  cmovnz  rcx, r9
0x18000c032  mov     r9, [rdi]
0x18000c035  cmovz   rax, rdx
0x18000c039  mov     [rsp+48h+var_18], r8
0x18000c03e  mov     rdx, rbp; unsigned __int64
0x18000c041  mov     [rsp+48h+var_20], rcx
0x18000c046  lea     r8, aSSSSS; "%s%s%s%s=%s"
0x18000c04d  mov     rcx, rsi; unsigned __int16 *
0x18000c050  mov     [rsp+48h+var_28], rax
0x18000c055  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c05a  mov     r9d, 9F1h
0x18000c060  mov     ecx, eax
0x18000c062  mov     edi, eax
0x18000c064  call    ElValidateHr_1
0x18000c069  test    eax, eax
0x18000c06b  jns     short loc_18000C087
0x18000c06d  mov     ecx, edi
0x18000c06f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c076  nop     dword ptr [rax+rax+00h]
0x18000c07b  mov     rcx, rsi; Block
0x18000c07e  mov     ebx, eax
0x18000c080  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c085  jmp     short loc_18000C08A
0x18000c087  mov     [r14], rsi
0x18000c08a  mov     rbp, [rsp+48h+arg_8]
0x18000c08f  mov     eax, ebx
0x18000c091  mov     rbx, [rsp+48h+arg_0]
0x18000c096  mov     rsi, [rsp+48h+arg_10]
0x18000c09b  mov     rdi, [rsp+48h+arg_18]
0x18000c0a0  add     rsp, 40h
0x18000c0a4  pop     r14
0x18000c0a6  retn
```
