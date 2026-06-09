# operator/(path const &,std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x140004b00`
- end: `0x140004d61`
- name: `??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003ea0`

## callees

- `0x140004b00`
- `0x140004d68`
- `0x1400055ac`
- `0x140014280`
- `0x140016c8c`
- `0x140016ce4`
- `0x140018c20`
- `0x140019844`
- `0x14001cc0c`
- `0x140026c20`
- `0x140027084`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140004bc9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140004bc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004d36`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140004b93`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140004b93`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall operator/(__int64 a1, const WCHAR *a2, unsigned __int64 *a3)
{
  unsigned __int64 v5; // rcx
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 v8; // r8
  PWSTR v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  __int128 *v12; // rdx
  int v13; // [rsp+20h] [rbp-29h] BYREF
  void *v14; // [rsp+28h] [rbp-21h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  __int128 v16; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+48h] [rbp-1h]
  unsigned __int64 v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+60h] [rbp+17h]
  PWSTR ppszPathOut; // [rsp+68h] [rbp+1Fh] BYREF
  PWSTR pszSpec[2]; // [rsp+70h] [rbp+27h] BYREF
  WCHAR *v22; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v19 = a1;
  v5 = *a3;
  v6 = 2 * a3[1];
  *(_OWORD *)pszSpec = 0;
  v22 = 0;
  v15 = v5;
  v14 = (void *)(v6 + v5);
  std::vector<unsigned short>::_Construct_n<unsigned short const *,unsigned short const *>(pszSpec, v6 >> 1, &v15, &v14);
  LOWORD(v13) = 0;
  if ( pszSpec[1] == v22 )
    std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(pszSpec, pszSpec[1], &v13);
  else
    *pszSpec[1]++ = 0;
  if ( PathCleanupSpec(0, pszSpec[0]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)0x80070057LL,
      v13);
  ppszPathOut = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v7 = PathAllocCombine(a2, pszSpec[0], 1u, &ppszPathOut);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)(unsigned int)v7,
      v13);
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v8 = -1;
  do
    ++v8;
  while ( ppszPathOut[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&v16, ppszPathOut, v8);
  v14 = &v16;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct_empty(a1);
  if ( (__int128 *)a1 != &v16 )
  {
    v12 = &v16;
    if ( v18 > 7 )
      v12 = (__int128 *)v16;
    std::wstring::assign(a1, v12, v17);
  }
  if ( v18 > 7 )
    std::_Deallocate<16>(v16, 2 * v18 + 2);
  v17 = 0;
  v18 = 7;
  LOWORD(v16) = 0;
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  v9 = pszSpec[0];
  if ( pszSpec[0] )
  {
    v10 = (const struct std::nothrow_t *)(2 * (v22 - pszSpec[0]));
    v15 = (unsigned __int64)v10;
    v14 = pszSpec[0];
    if ( (unsigned __int64)v10 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v14, &v15);
      v10 = (const struct std::nothrow_t *)v15;
      v9 = (PWSTR)v14;
    }
    operator delete(v9, v10);
  }
  return a1;
}

```

## disassembly

```asm
0x140004b00  mov     [rsp-8+arg_10], rbx
0x140004b05  mov     [rsp-8+arg_18], rsi
0x140004b0a  push    rbp
0x140004b0b  push    rdi
0x140004b0c  push    r14
0x140004b0e  lea     rbp, [rsp-47h]
0x140004b13  sub     rsp, 90h
0x140004b1a  mov     rax, cs:__security_cookie
0x140004b21  xor     rax, rsp
0x140004b24  mov     [rbp+57h+var_18], rax
0x140004b28  mov     rbx, rdx
0x140004b2b  mov     rdi, rcx
0x140004b2e  mov     [rbp+57h+var_40], rcx
0x140004b32  xor     r14d, r14d
0x140004b35  mov     rcx, [r8]
0x140004b38  mov     rax, [r8+8]
0x140004b3c  lea     rdx, [rax+rax]
0x140004b40  xorps   xmm0, xmm0
0x140004b43  movdqu  xmmword ptr [rbp+57h+pszSpec], xmm0
0x140004b48  mov     [rbp+57h+var_20], r14
0x140004b4c  mov     [rbp+57h+var_70], rcx
0x140004b50  lea     rax, [rdx+rcx]
0x140004b54  mov     [rbp+57h+var_78], rax
0x140004b58  sar     rdx, 1
0x140004b5b  lea     r9, [rbp+57h+var_78]
0x140004b5f  lea     r8, [rbp+57h+var_70]
0x140004b63  lea     rcx, [rbp+57h+pszSpec]
0x140004b67  call    ??$_Construct_n@PEBGPEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K$$QEAPEBG1@Z; std::vector<ushort>::_Construct_n<ushort const *,ushort const *>(unsigned __int64,ushort const * &&,ushort const * &&)
0x140004b6c  nop
0x140004b6d  mov     word ptr [rbp+57h+var_80], r14w
0x140004b72  mov     rdx, [rbp+57h+pszSpec+8]
0x140004b76  cmp     rdx, [rbp+57h+var_20]
0x140004b7a  jz      loc_140004CD4
0x140004b80  mov     [rdx], r14w
0x140004b84  add     [rbp+57h+pszSpec+8], 2
0x140004b89  mov     rsi, [rbp+5Fh]
0x140004b8d  mov     rdx, [rbp+57h+pszSpec]; pszSpec
0x140004b91  xor     ecx, ecx; pszDir
0x140004b93  call    cs:__imp_PathCleanupSpec
0x140004b9a  nop     dword ptr [rax+rax+00h]
0x140004b9f  shr     eax, 1Fh
0x140004ba2  test    al, al
0x140004ba4  jnz     loc_140004CE6
0x140004baa  mov     [rbp+57h+ppszPathOut], r14
0x140004bae  cmp     qword ptr [rbx+18h], 7
0x140004bb3  jbe     short loc_140004BB8
0x140004bb5  mov     rbx, [rbx]
0x140004bb8  lea     r9, [rbp+57h+ppszPathOut]; ppszPathOut
0x140004bbc  mov     r8d, 1; dwFlags
0x140004bc2  mov     rdx, [rbp+57h+pszSpec]; pszMore
0x140004bc6  mov     rcx, rbx; pszPathIn
0x140004bc9  call    cs:__imp_PathAllocCombine
0x140004bd0  nop     dword ptr [rax+rax+00h]
0x140004bd5  mov     rcx, [rbp+5Fh]; this
0x140004bd9  test    eax, eax
0x140004bdb  jns     short loc_140004BF2
0x140004bdd  mov     r9d, eax; char *
0x140004be0  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140004be7  mov     edx, 182h; void *
0x140004bec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140004bf2  mov     rdx, [rbp+57h+ppszPathOut]
0x140004bf6  xorps   xmm0, xmm0
0x140004bf9  movups  [rbp+57h+var_68], xmm0
0x140004bfd  mov     [rbp+57h+var_58], r14
0x140004c01  mov     [rbp+57h+var_50], r14
0x140004c05  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140004c0c  nop     dword ptr [rax+00h]
0x140004c10  inc     r8
0x140004c13  cmp     word ptr [rdx+r8*2], 0
0x140004c19  jnz     short loc_140004C10
0x140004c1b  lea     rcx, [rbp+57h+var_68]
0x140004c1f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140004c24  lea     rax, [rbp+57h+var_68]
0x140004c28  mov     [rbp+57h+var_78], rax
0x140004c2c  xorps   xmm0, xmm0
0x140004c2f  movups  xmmword ptr [rdi], xmm0
0x140004c32  mov     [rdi+10h], r14
0x140004c36  mov     [rdi+18h], r14
0x140004c3a  mov     rcx, rdi
0x140004c3d  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140004c42  nop
0x140004c43  lea     rax, [rbp+57h+var_68]
0x140004c47  cmp     rdi, rax
0x140004c4a  jnz     loc_140004D01
0x140004c50  mov     rdx, [rbp+57h+var_50]
0x140004c54  cmp     rdx, 7
0x140004c58  ja      loc_140004D20
0x140004c5e  mov     [rbp+57h+var_58], r14
0x140004c62  mov     [rbp+57h+var_50], 7
0x140004c6a  mov     word ptr [rbp+57h+var_68], r14w
0x140004c6f  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x140004c73  test    rcx, rcx
0x140004c76  jnz     loc_140004D36
0x140004c7c  mov     rcx, [rbp+57h+pszSpec]; void *
0x140004c80  test    rcx, rcx
0x140004c83  jz      short loc_140004CAC
0x140004c85  mov     rdx, [rbp+57h+var_20]
0x140004c89  sub     rdx, rcx
0x140004c8c  sar     rdx, 1
0x140004c8f  add     rdx, rdx; struct std::nothrow_t *
0x140004c92  mov     [rbp+57h+var_70], rdx
0x140004c96  mov     [rbp+57h+var_78], rcx
0x140004c9a  cmp     rdx, 1000h
0x140004ca1  jnb     loc_140004D47
0x140004ca7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004cac  mov     rax, rdi
0x140004caf  mov     rcx, [rbp+57h+var_18]
0x140004cb3  xor     rcx, rsp; StackCookie
0x140004cb6  call    __security_check_cookie
0x140004cbb  lea     r11, [rsp+0A0h+var_10]
0x140004cc3  mov     rbx, [r11+30h]
0x140004cc7  mov     rsi, [r11+38h]
0x140004ccb  mov     rsp, r11
0x140004cce  pop     r14
0x140004cd0  pop     rdi
0x140004cd1  pop     rbp
0x140004cd2  retn
0x140004cd4  lea     r8, [rbp+57h+var_80]
0x140004cd8  lea     rcx, [rbp+57h+pszSpec]
0x140004cdc  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x140004ce1  jmp     loc_140004B89
0x140004ce6  mov     r9d, 80070057h; char *
0x140004cec  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140004cf3  mov     edx, 17Fh; void *
0x140004cf8  mov     rcx, rsi; this
0x140004cfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140004d01  lea     rdx, [rbp+57h+var_68]
0x140004d05  cmp     [rbp+57h+var_50], 7
0x140004d0a  cmova   rdx, qword ptr [rbp+57h+var_68]
0x140004d0f  mov     r8, [rbp+57h+var_58]
0x140004d13  mov     rcx, rdi
0x140004d16  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x140004d1b  jmp     loc_140004C50
0x140004d20  lea     rdx, ds:2[rdx*2]
0x140004d28  mov     rcx, qword ptr [rbp+57h+var_68]
0x140004d2c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140004d31  jmp     loc_140004C5E
0x140004d36  call    cs:__imp_LocalFree
0x140004d3d  nop     dword ptr [rax+rax+00h]
0x140004d42  jmp     loc_140004C7C
0x140004d47  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x140004d4b  lea     rcx, [rbp+57h+var_78]; void **
0x140004d4f  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140004d54  mov     rdx, [rbp+57h+var_70]
0x140004d58  mov     rcx, [rbp+57h+var_78]
0x140004d5c  jmp     loc_140004CA7
```
