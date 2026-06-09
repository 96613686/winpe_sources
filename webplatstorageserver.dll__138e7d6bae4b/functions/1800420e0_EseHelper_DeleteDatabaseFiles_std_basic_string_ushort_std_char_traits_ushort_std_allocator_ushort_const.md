# EseHelper::DeleteDatabaseFiles(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800420e0`
- end: `0x1800422a9`
- name: `?DeleteDatabaseFiles@EseHelper@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18003490c`
- `0x1800722f0`
- `0x1800bf3c6`

## callees

- `0x1800420e0`
- `0x180042310`
- `0x18004464c`
- `0x180064ec8`
- `0x18006c458`
- `0x180080fb0`
- `0x180084265`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042173`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042187`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042256`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042173`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042187`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042256`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180042110`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004219c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180042110`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004219c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EseHelper::DeleteDatabaseFiles(WCHAR *pszPath)
{
  WCHAR *v1; // rbx
  LPWSTR ExtensionW; // rax
  WCHAR *v3; // rdx
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rcx
  LPWSTR v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rdi
  LPCWSTR *v11; // rbx
  const WCHAR *v12; // rcx
  LPCWSTR Src[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v14; // [rsp+40h] [rbp-9h]
  unsigned __int64 v15; // [rsp+48h] [rbp-1h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp+7h] BYREF
  __int128 v17; // [rsp+60h] [rbp+17h]

  v1 = pszPath;
  if ( *((_QWORD *)pszPath + 3) > 7u )
    pszPath = *(WCHAR **)pszPath;
  ExtensionW = PathFindExtensionW(pszPath);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v3 = v1;
  else
    v3 = *(WCHAR **)v1;
  *(_OWORD *)lpFileName = 0;
  v17 = 0;
  if ( v3 == ExtensionW )
  {
    *((_QWORD *)&v17 + 1) = 7;
    LOWORD(lpFileName[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(lpFileName, v3, ExtensionW - v3);
  }
  std::wstring::append(lpFileName, L".jfm");
  v4 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v4 = lpFileName[0];
  DeleteFileW(v4);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v5 = v1;
  else
    v5 = *(const WCHAR **)v1;
  DeleteFileW(v5);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v6 = v1;
  else
    v6 = *(const WCHAR **)v1;
  v7 = PathFindExtensionW(v6);
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(WCHAR **)v1;
  *(_OWORD *)Src = 0;
  v8 = 0;
  v14 = 0;
  v15 = 0;
  if ( v1 == v7 )
  {
    v9 = 7;
    v15 = 7;
    LOWORD(Src[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(Src, v1, v7 - v1);
    v9 = v15;
    v8 = v14;
  }
  if ( v9 - v8 < 0xA )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      Src,
      10);
  }
  else
  {
    v10 = v8 + 10;
    v14 = v8 + 10;
    v11 = Src;
    if ( v9 > 7 )
      v11 = (LPCWSTR *)Src[0];
    memmove_0((char *)v11 + 2 * v8, L".corrupted", 0x14u);
    *((_WORD *)v11 + v10) = 0;
  }
  v12 = (const WCHAR *)Src;
  if ( v15 > 7 )
    v12 = Src[0];
  DeleteFileW(v12);
  if ( v15 > 7 )
    std::_Deallocate<16>((void *)Src[0], 2 * v15 + 2);
  if ( *((_QWORD *)&v17 + 1) > 7u )
    std::_Deallocate<16>((void *)lpFileName[0], 2LL * *((_QWORD *)&v17 + 1) + 2);
}

```

## disassembly

```asm
0x1800420e0  push    rbp
0x1800420e2  push    rbx
0x1800420e3  push    rsi
0x1800420e4  push    rdi
0x1800420e5  lea     rbp, [rsp-3Fh]
0x1800420ea  sub     rsp, 88h
0x1800420f1  mov     rax, cs:__security_cookie
0x1800420f8  xor     rax, rsp
0x1800420fb  mov     [rbp+57h+var_30], rax
0x1800420ff  mov     rbx, rcx
0x180042102  mov     esi, 7
0x180042107  cmp     [rcx+18h], rsi
0x18004210b  jbe     short loc_180042110
0x18004210d  mov     rcx, [rcx]; pszPath
0x180042110  call    cs:__imp_PathFindExtensionW
0x180042116  cmp     [rbx+18h], rsi
0x18004211a  jbe     short loc_180042121
0x18004211c  mov     rdx, [rbx]
0x18004211f  jmp     short loc_180042124
0x180042121  mov     rdx, rbx
0x180042124  xorps   xmm0, xmm0
0x180042127  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18004212b  xorps   xmm1, xmm1
0x18004212e  movdqu  [rbp+57h+var_40], xmm1
0x180042133  cmp     rdx, rax
0x180042136  jnz     short loc_180042144
0x180042138  mov     qword ptr [rbp+57h+var_40+8], rsi
0x18004213c  xor     eax, eax
0x18004213e  mov     word ptr [rbp+57h+lpFileName], ax
0x180042142  jmp     short loc_180042156
0x180042144  sub     rax, rdx
0x180042147  sar     rax, 1
0x18004214a  mov     r8, rax
0x18004214d  lea     rcx, [rbp+57h+lpFileName]
0x180042151  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042156  lea     rdx, aJfm; ".jfm"
0x18004215d  lea     rcx, [rbp+57h+lpFileName]; Src
0x180042161  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180042166  lea     rcx, [rbp+57h+lpFileName]
0x18004216a  cmp     qword ptr [rbp+57h+var_40+8], rsi
0x18004216e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180042173  call    cs:__imp_DeleteFileW
0x180042179  cmp     [rbx+18h], rsi
0x18004217d  jbe     short loc_180042184
0x18004217f  mov     rcx, [rbx]
0x180042182  jmp     short loc_180042187
0x180042184  mov     rcx, rbx; lpFileName
0x180042187  call    cs:__imp_DeleteFileW
0x18004218d  nop
0x18004218e  cmp     [rbx+18h], rsi
0x180042192  jbe     short loc_180042199
0x180042194  mov     rcx, [rbx]
0x180042197  jmp     short loc_18004219C
0x180042199  mov     rcx, rbx; pszPath
0x18004219c  call    cs:__imp_PathFindExtensionW
0x1800421a2  cmp     [rbx+18h], rsi
0x1800421a6  jbe     short loc_1800421AB
0x1800421a8  mov     rbx, [rbx]
0x1800421ab  xorps   xmm0, xmm0
0x1800421ae  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800421b2  xor     ecx, ecx
0x1800421b4  mov     [rbp+57h+var_60], rcx
0x1800421b8  mov     [rbp+57h+var_58], rcx
0x1800421bc  cmp     rbx, rax
0x1800421bf  jnz     short loc_1800421D0
0x1800421c1  mov     rdx, rsi
0x1800421c4  mov     [rbp+57h+var_58], rdx
0x1800421c8  xor     eax, eax
0x1800421ca  mov     word ptr [rbp+57h+Src], ax
0x1800421ce  jmp     short loc_1800421ED
0x1800421d0  sub     rax, rbx
0x1800421d3  sar     rax, 1
0x1800421d6  mov     r8, rax
0x1800421d9  mov     rdx, rbx
0x1800421dc  lea     rcx, [rbp+57h+Src]
0x1800421e0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800421e5  mov     rdx, [rbp+57h+var_58]
0x1800421e9  mov     rcx, [rbp+57h+var_60]
0x1800421ed  mov     rax, rdx
0x1800421f0  sub     rax, rcx
0x1800421f3  mov     r8d, 0Ah
0x1800421f9  cmp     rax, r8
0x1800421fc  jb      short loc_180042230
0x1800421fe  lea     rdi, [rcx+0Ah]
0x180042202  mov     [rbp+57h+var_60], rdi
0x180042206  lea     rbx, [rbp+57h+Src]
0x18004220a  cmp     rdx, rsi
0x18004220d  cmova   rbx, [rbp+57h+Src]
0x180042212  lea     rcx, [rbx+rcx*2]; void *
0x180042216  mov     r8d, 14h; Size
0x18004221c  lea     rdx, aCorrupted; ".corrupted"
0x180042223  call    memmove_0
0x180042228  xor     eax, eax
0x18004222a  mov     [rbx+rdi*2], ax
0x18004222e  jmp     short loc_180042249
0x180042230  mov     [rsp+0A0h+var_80], r8; __int64
0x180042235  lea     r9, aCorrupted; ".corrupted"
0x18004223c  mov     rdx, r8
0x18004223f  lea     rcx, [rbp+57h+Src]; Src
0x180042243  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180042248  nop
0x180042249  lea     rcx, [rbp+57h+Src]
0x18004224d  cmp     [rbp+57h+var_58], rsi
0x180042251  cmova   rcx, [rbp+57h+Src]; lpFileName
0x180042256  call    cs:__imp_DeleteFileW
0x18004225c  mov     rdx, [rbp+57h+var_58]
0x180042260  cmp     rdx, rsi
0x180042263  jbe     short loc_180042276
0x180042265  lea     rdx, ds:2[rdx*2]
0x18004226d  mov     rcx, [rbp+57h+Src]
0x180042271  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180042276  mov     rdx, qword ptr [rbp+57h+var_40+8]
0x18004227a  cmp     rdx, rsi
0x18004227d  jbe     short loc_180042291
0x18004227f  lea     rdx, ds:2[rdx*2]
0x180042287  mov     rcx, [rbp+57h+lpFileName]
0x18004228b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180042290  nop
0x180042291  mov     rcx, [rbp+57h+var_30]
0x180042295  xor     rcx, rsp; StackCookie
0x180042298  call    __security_check_cookie
0x18004229d  add     rsp, 88h
0x1800422a4  pop     rdi
0x1800422a5  pop     rsi
0x1800422a6  pop     rbx
0x1800422a7  pop     rbp
0x1800422a8  retn
```
