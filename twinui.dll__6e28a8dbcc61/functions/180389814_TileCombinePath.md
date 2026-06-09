# TileCombinePath

- ea: `0x180389814`
- end: `0x18038995d`
- name: `TileCombinePath`
- size: `329`
- prototype: `__int64 __fastcall(LPCWSTR pszPrefix, PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1802e155c`

## callees

- `0x180389814`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1803898f4`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1803898f4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803898b0`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803898b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803898d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180389924`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038993e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803898d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180389924`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038993e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180389882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180389882`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803898df`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803898df`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18038990b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18038990b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18038983f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18038983f`

## pseudocode

```c
__int64 __fastcall TileCombinePath(LPCWSTR pszPrefix, PCWSTR pszMore, __int64 a3, WCHAR **a4)
{
  WCHAR *v5; // rsi
  HRESULT v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rbp
  size_t v11; // r14
  WCHAR *v12; // rax
  bool v13; // zf
  HRESULT v14; // eax
  BOOL IsPrefixW; // eax
  int v16; // ecx
  LPWSTR ppwsz; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v5 = 0;
  if ( !PathIsRelativeW(pszMore) )
    goto LABEL_20;
  if ( !pszPrefix )
  {
    v8 = -2147467261;
    goto LABEL_21;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( pszPrefix[v10] );
  do
    ++v9;
  while ( pszMore[v9] );
  v11 = v10 + v9 + 2;
  v12 = (WCHAR *)CoTaskMemAlloc(2 * v11);
  v5 = v12;
  if ( !v12 )
  {
    v8 = -2147024882;
    goto LABEL_21;
  }
  if ( !*pszPrefix )
  {
LABEL_20:
    v8 = -2147024809;
    goto LABEL_21;
  }
  v8 = PathCchCombine(v12, v11, pszPrefix, pszMore);
  if ( v8 >= 0 )
  {
    if ( *pszPrefix == 45 )
      goto LABEL_19;
    v13 = pszPrefix[v10 - 1] == 92;
    ppwsz = 0;
    if ( !v13
      || (CoTaskMemFree(0), v8 = SHStrDupW(pszPrefix, &ppwsz), v8 >= 0)
      && (v14 = PathCchRemoveBackslash(ppwsz, v10 + 1), pszPrefix = ppwsz, v8 = v14, v14 >= 0) )
    {
      IsPrefixW = PathIsPrefixW(pszPrefix, v5);
      v16 = v8;
      if ( !IsPrefixW )
        v16 = -2147024809;
      v8 = v16;
    }
    CoTaskMemFree(ppwsz);
    if ( v8 >= 0 )
    {
LABEL_19:
      *a4 = v5;
      v5 = 0;
    }
  }
LABEL_21:
  CoTaskMemFree(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180389814  mov     [rsp+arg_0], rbx
0x180389819  mov     [rsp+arg_8], rbp
0x18038981e  push    rsi
0x18038981f  push    rdi
0x180389820  push    r12
0x180389822  push    r14
0x180389824  push    r15
0x180389826  sub     rsp, 20h
0x18038982a  mov     rdi, rcx
0x18038982d  xor     r12d, r12d
0x180389830  mov     rcx, rdx; pszPath
0x180389833  mov     [r9], r12
0x180389836  mov     esi, r12d
0x180389839  mov     r15, r9
0x18038983c  mov     rbx, rdx
0x18038983f  call    cs:__imp_PathIsRelativeW
0x180389845  test    eax, eax
0x180389847  jz      loc_180389936
0x18038984d  test    rdi, rdi
0x180389850  jnz     short loc_18038985C
0x180389852  mov     ebx, 80004003h
0x180389857  jmp     loc_18038993B
0x18038985c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180389860  mov     rbp, rax
0x180389863  inc     rbp
0x180389866  cmp     [rdi+rbp*2], r12w
0x18038986b  jnz     short loc_180389863
0x18038986d  inc     rax
0x180389870  cmp     [rbx+rax*2], r12w
0x180389875  jnz     short loc_18038986D
0x180389877  lea     r14, [rax+2]
0x18038987b  add     r14, rbp
0x18038987e  lea     rcx, [r14+r14]; cb
0x180389882  call    cs:__imp_CoTaskMemAlloc
0x180389888  mov     rsi, rax
0x18038988b  test    rax, rax
0x18038988e  jnz     short loc_18038989A
0x180389890  mov     ebx, 8007000Eh
0x180389895  jmp     loc_18038993B
0x18038989a  cmp     [rdi], r12w
0x18038989e  jz      loc_180389936
0x1803898a4  mov     r9, rbx; pszMore
0x1803898a7  mov     r8, rdi; pszPathIn
0x1803898aa  mov     rdx, r14; cchPathOut
0x1803898ad  mov     rcx, rsi; pszPathOut
0x1803898b0  call    cs:__imp_PathCchCombine
0x1803898b6  mov     ebx, eax
0x1803898b8  test    eax, eax
0x1803898ba  js      short loc_18038993B
0x1803898bc  cmp     word ptr [rdi], 2Dh ; '-'
0x1803898c0  jz      short loc_18038992E
0x1803898c2  cmp     word ptr [rdi+rbp*2-2], 5Ch ; '\'
0x1803898c8  mov     [rsp+48h+ppwsz], r12
0x1803898cd  jnz     short loc_180389905
0x1803898cf  xor     ecx, ecx; pv
0x1803898d1  call    cs:__imp_CoTaskMemFree
0x1803898d7  lea     rdx, [rsp+48h+ppwsz]; ppwsz
0x1803898dc  mov     rcx, rdi; psz
0x1803898df  call    cs:__imp_SHStrDupW
0x1803898e5  mov     ebx, eax
0x1803898e7  test    eax, eax
0x1803898e9  js      short loc_18038991F
0x1803898eb  mov     rcx, [rsp+48h+ppwsz]; pszPath
0x1803898f0  lea     rdx, [rbp+1]; cchPath
0x1803898f4  call    cs:__imp_PathCchRemoveBackslash
0x1803898fa  mov     rdi, [rsp+48h+ppwsz]
0x1803898ff  mov     ebx, eax
0x180389901  test    eax, eax
0x180389903  js      short loc_18038991F
0x180389905  mov     rdx, rsi; pszPath
0x180389908  mov     rcx, rdi; pszPrefix
0x18038990b  call    cs:__imp_PathIsPrefixW
0x180389911  mov     ecx, ebx
0x180389913  mov     ebx, 80070057h
0x180389918  test    eax, eax
0x18038991a  cmovz   ecx, ebx
0x18038991d  mov     ebx, ecx
0x18038991f  mov     rcx, [rsp+48h+ppwsz]; pv
0x180389924  call    cs:__imp_CoTaskMemFree
0x18038992a  test    ebx, ebx
0x18038992c  js      short loc_18038993B
0x18038992e  mov     [r15], rsi
0x180389931  mov     rsi, r12
0x180389934  jmp     short loc_18038993B
0x180389936  mov     ebx, 80070057h
0x18038993b  mov     rcx, rsi; pv
0x18038993e  call    cs:__imp_CoTaskMemFree
0x180389944  mov     rbp, [rsp+48h+arg_8]
0x180389949  mov     eax, ebx
0x18038994b  mov     rbx, [rsp+48h+arg_0]
0x180389950  add     rsp, 20h
0x180389954  pop     r15
0x180389956  pop     r14
0x180389958  pop     r12
0x18038995a  pop     rdi
0x18038995b  pop     rsi
0x18038995c  retn
```
