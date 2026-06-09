# CThumbnailCache::_GetDataFilePath(int,THUMBSIZE,ushort *,uint)

- ea: `0x1800177e0`
- end: `0x180017ae8`
- name: `?_GetDataFilePath@CThumbnailCache@@AEAAJHW4THUMBSIZE@@PEAGI@Z`
- size: `776`
- prototype: `__int64 __fastcall(__int64, int, int, _WORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bffc`
- `0x18001773c`
- `0x1800287c4`
- `0x18002d7b0`
- `0x180042e24`

## callees

- `0x1800177e0`
- `0x180017af0`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18001789b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800179d2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18001789b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800179d2`

## string_xrefs

- `0x18001795e`: `thumbcache_%d.db`
- `0x180017a4f`: `thumbcache_wide_alternate.db`
- `0x180017a21`: `thumbcache_wide.db`
- `0x18001787c`: `thumbcache_idx.db`
- `0x180017883`: `iconcache_idx.db`
- `0x180017965`: `iconcache_%d.db`
- `0x1800179f2`: `thumbcache_exif.db`
- `0x1800179f9`: `iconcache_exif.db`
- `0x180017a15`: `iconcache_sr.db`
- `0x180017a0e`: `thumbcache_sr.db`
- `0x180017a28`: `iconcache_wide.db`
- `0x180017a56`: `iconcache_wide_alternate.db`
- `0x180017a6d`: `iconcache_custom_stream.db`
- `0x180017a66`: `thumbcache_custom_stream.db`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailCache::_GetDataFilePath(__int64 a1, int a2, int a3, _WORD *a4)
{
  __int64 v4; // rbx
  WCHAR *v5; // r10
  __int64 v6; // rdi
  WCHAR *v7; // r14
  __int64 v9; // r11
  __int64 v10; // r9
  WCHAR *v14; // rcx
  unsigned int v15; // ebp
  unsigned int v16; // edx
  const wchar_t *v17; // rax
  const WCHAR *v18; // rdx
  BOOL v19; // eax
  int v20; // ecx
  WCHAR *v21; // rcx
  _WORD *v22; // rdx
  __int64 result; // rax
  const unsigned __int16 *v24; // r8
  __int64 v25; // r9
  WCHAR *v26; // rdx
  const wchar_t *v27; // rax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-468h] BYREF
  WCHAR pszMore[264]; // [rsp+230h] [rbp-258h] BYREF

  v4 = 2147483646;
  v5 = (WCHAR *)(a1 + 72);
  v6 = 260;
  v7 = pszPath;
  v9 = 260;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*v5 )
      break;
    *v7++ = *v5++;
    --v10;
    --v9;
  }
  while ( v9 );
  v14 = v7 - 1;
  v15 = -2147024774;
  v16 = -2147024774;
  if ( v9 )
  {
    v14 = v7;
    v16 = 0;
  }
  *v14 = 0;
  if ( !v9 )
    return v16;
  if ( a2 )
  {
    v17 = L"thumbcache_idx.db";
    v18 = L"iconcache_idx.db";
    goto LABEL_10;
  }
  switch ( a3 )
  {
    case 9:
      v17 = L"thumbcache_sr.db";
      v18 = L"iconcache_sr.db";
      goto LABEL_10;
    case 10:
      v27 = L"thumbcache_wide.db";
      v26 = L"iconcache_wide.db";
LABEL_41:
      if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
        v26 = (WCHAR *)v27;
      goto LABEL_37;
    case 12:
      v26 = L"iconcache_wide_alternate.db";
      if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
        v26 = L"thumbcache_wide_alternate.db";
LABEL_37:
      if ( !PathAppendW(pszPath, v26) )
        return 2147500037LL;
LABEL_15:
      v21 = pszPath;
      do
      {
        if ( !v4 )
          break;
        if ( !*v21 )
          break;
        *a4++ = *v21++;
        --v4;
        --v6;
      }
      while ( v6 );
      v22 = a4 - 1;
      if ( v6 )
      {
        v22 = a4;
        v15 = 0;
      }
      result = v15;
      *v22 = 0;
      return result;
    case 11:
      v27 = L"thumbcache_exif.db";
      v26 = L"iconcache_exif.db";
      goto LABEL_41;
    case 13:
      v17 = L"thumbcache_custom_stream.db";
      v18 = L"iconcache_custom_stream.db";
LABEL_10:
      if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
        v18 = v17;
      v19 = PathAppendW(pszPath, v18);
      v20 = 0;
      if ( !v19 )
        v20 = -2147467259;
      if ( v20 < 0 )
        return (unsigned int)v20;
      goto LABEL_15;
  }
  v24 = L"iconcache_%d.db";
  if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
    v24 = L"thumbcache_%d.db";
  if ( a3 == 2 )
  {
    v25 = 48;
  }
  else if ( a3 == 3 )
  {
    v25 = 96;
  }
  else
  {
    switch ( a3 )
    {
      case 0:
        v25 = 16;
        break;
      case 1:
        v25 = 32;
        break;
      case 4:
      case 9:
        v25 = 256;
        break;
      case 5:
        v25 = 768;
        break;
      case 6:
        v25 = 1280;
        break;
      case 7:
        v25 = 1920;
        break;
      case 8:
        v25 = 2560;
        break;
      default:
        v25 = 0;
        break;
    }
  }
  result = StringCchPrintfW(pszMore, 0x104u, v24, v25);
  if ( (int)result >= 0 )
  {
    v26 = pszMore;
    goto LABEL_37;
  }
  return result;
}

```

## disassembly

```asm
0x1800177e0  mov     [rsp+arg_0], rbx
0x1800177e5  push    rbp
0x1800177e6  push    rsi
0x1800177e7  push    rdi
0x1800177e8  push    r12
0x1800177ea  push    r13
0x1800177ec  push    r14
0x1800177ee  push    r15
0x1800177f0  sub     rsp, 450h
0x1800177f7  mov     rax, cs:__security_cookie
0x1800177fe  xor     rax, rsp
0x180017801  mov     [rsp+488h+var_48], rax
0x180017809  mov     ebx, 7FFFFFFEh
0x18001780e  lea     r10, [rcx+48h]
0x180017812  mov     edi, 104h
0x180017817  lea     r14, [rsp+488h+pszPath]
0x18001781c  mov     rsi, r9
0x18001781f  mov     r11d, edi
0x180017822  mov     r9d, ebx
0x180017825  mov     r12d, r8d
0x180017828  mov     r15d, edx
0x18001782b  mov     r13, rcx
0x18001782e  xchg    ax, ax
0x180017830  test    r9, r9
0x180017833  jz      short loc_180017853
0x180017835  movzx   eax, word ptr [r10]
0x180017839  test    ax, ax
0x18001783c  jz      short loc_180017853
0x18001783e  mov     [r14], ax
0x180017842  add     r10, 2
0x180017846  add     r14, 2
0x18001784a  dec     r9
0x18001784d  sub     r11, 1
0x180017851  jnz     short loc_180017830
0x180017853  xor     eax, eax
0x180017855  lea     rcx, [r14-2]
0x180017859  test    r11, r11
0x18001785c  mov     ebp, 8007007Ah
0x180017861  mov     edx, ebp
0x180017863  cmovnz  rcx, r14
0x180017867  cmovnz  edx, eax
0x18001786a  mov     [rcx], ax
0x18001786d  jz      loc_180017AB4
0x180017873  test    r15d, r15d
0x180017876  jz      loc_180017924
0x18001787c  lea     rax, pszMore; "thumbcache_idx.db"
0x180017883  lea     rdx, aIconcacheIdxDb; "iconcache_idx.db"
0x18001788a  test    byte ptr [r13+300h], 2
0x180017892  lea     rcx, [rsp+488h+pszPath]; pszPath
0x180017897  cmovz   rdx, rax; pszMore
0x18001789b  call    cs:__imp_PathAppendW
0x1800178a1  xor     ecx, ecx
0x1800178a3  mov     edx, 80004005h
0x1800178a8  test    eax, eax
0x1800178aa  cmovz   ecx, edx
0x1800178ad  test    ecx, ecx
0x1800178af  js      loc_180017AA5
0x1800178b5  lea     rcx, [rsp+488h+pszPath]
0x1800178ba  nop     word ptr [rax+rax+00h]
0x1800178c0  test    rbx, rbx
0x1800178c3  jz      short loc_1800178E1
0x1800178c5  movzx   eax, word ptr [rcx]
0x1800178c8  test    ax, ax
0x1800178cb  jz      short loc_1800178E1
0x1800178cd  mov     [rsi], ax
0x1800178d0  add     rcx, 2
0x1800178d4  add     rsi, 2
0x1800178d8  dec     rbx
0x1800178db  sub     rdi, 1
0x1800178df  jnz     short loc_1800178C0
0x1800178e1  test    rdi, rdi
0x1800178e4  lea     rdx, [rsi-2]
0x1800178e8  cmovnz  rdx, rsi
0x1800178ec  xor     ecx, ecx
0x1800178ee  test    rdi, rdi
0x1800178f1  cmovnz  ebp, ecx
0x1800178f4  mov     eax, ebp
0x1800178f6  mov     [rdx], cx
0x1800178f9  mov     rcx, [rsp+488h+var_48]
0x180017901  xor     rcx, rsp; StackCookie
0x180017904  call    __security_check_cookie
0x180017909  mov     rbx, [rsp+488h+arg_0]
0x180017911  add     rsp, 450h
0x180017918  pop     r15
0x18001791a  pop     r14
0x18001791c  pop     r13
0x18001791e  pop     r12
0x180017920  pop     rdi
0x180017921  pop     rsi
0x180017922  pop     rbp
0x180017923  retn
0x180017924  cmp     r12d, 9
0x180017928  jz      loc_180017A0E
0x18001792e  cmp     r12d, 0Ah
0x180017932  jz      loc_180017A21
0x180017938  cmp     r12d, 0Ch
0x18001793c  jz      loc_180017A47
0x180017942  cmp     r12d, 0Bh
0x180017946  jz      loc_1800179F2
0x18001794c  cmp     r12d, 0Dh
0x180017950  jz      loc_180017A66
0x180017956  test    byte ptr [r13+300h], 2
0x18001795e  lea     rax, aThumbcacheDDb; "thumbcache_%d.db"
0x180017965  lea     r8, aIconcacheDDb; "iconcache_%d.db"
0x18001796c  cmovz   r8, rax; unsigned __int16 *
0x180017970  cmp     r12d, 2
0x180017974  jz      short loc_1800179A7
0x180017976  cmp     r12d, 3
0x18001797a  jz      short loc_1800179EA
0x18001797c  lea     eax, [r12+1]; switch 11 cases
0x180017981  cmp     eax, 0Ah
0x180017984  ja      def_18001799D; jumptable 000000018001799D default case, cases -1,2,3
0x18001798a  lea     rdx, __ImageBase
0x180017991  cdqe
0x180017993  mov     ecx, ds:(jpt_18001799D - 180000000h)[rdx+rax*4]
0x18001799a  add     rcx, rdx
0x18001799d  jmp     rcx; switch jump
0x18001799f  mov     r9d, 10h; jumptable 000000018001799D case 0
0x1800179a5  jmp     short loc_1800179AD
0x1800179a7  mov     r9d, 30h ; '0'
0x1800179ad  mov     rdx, rdi; unsigned __int64
0x1800179b0  lea     rcx, [rsp+488h+pszMore]; unsigned __int16 *
0x1800179b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800179bd  test    eax, eax
0x1800179bf  js      loc_1800178F9
0x1800179c5  lea     rdx, [rsp+488h+pszMore]; pszMore
0x1800179cd  lea     rcx, [rsp+488h+pszPath]; pszPath
0x1800179d2  call    cs:__imp_PathAppendW
0x1800179d8  test    eax, eax
0x1800179da  jnz     loc_1800178B5
0x1800179e0  mov     eax, 80004005h
0x1800179e5  jmp     loc_1800178F9
0x1800179ea  mov     r9d, 60h ; '`'
0x1800179f0  jmp     short loc_1800179AD
0x1800179f2  lea     rax, aThumbcacheExif; "thumbcache_exif.db"
0x1800179f9  lea     rdx, aIconcacheExifD; "iconcache_exif.db"
0x180017a00  test    byte ptr [r13+300h], 2
0x180017a08  cmovz   rdx, rax
0x180017a0c  jmp     short loc_1800179CD
0x180017a0e  lea     rax, aThumbcacheSrDb; "thumbcache_sr.db"
0x180017a15  lea     rdx, aIconcacheSrDb; "iconcache_sr.db"
0x180017a1c  jmp     loc_18001788A
0x180017a21  lea     rax, aThumbcacheWide_0; "thumbcache_wide.db"
0x180017a28  lea     rdx, aIconcacheWideD; "iconcache_wide.db"
0x180017a2f  jmp     short loc_180017A00
0x180017a31  mov     r9d, 0A00h; jumptable 000000018001799D case 8
0x180017a37  jmp     loc_1800179AD
0x180017a3c  mov     r9d, 20h ; ' '; jumptable 000000018001799D case 1
0x180017a42  jmp     loc_1800179AD
0x180017a47  test    byte ptr [r13+300h], 2
0x180017a4f  lea     rax, aThumbcacheWide; "thumbcache_wide_alternate.db"
0x180017a56  lea     rdx, aIconcacheWideA; "iconcache_wide_alternate.db"
0x180017a5d  cmovz   rdx, rax
0x180017a61  jmp     loc_1800179CD
0x180017a66  lea     rax, aThumbcacheCust; "thumbcache_custom_stream.db"
0x180017a6d  lea     rdx, aIconcacheCusto; "iconcache_custom_stream.db"
0x180017a74  jmp     loc_18001788A
0x180017a79  mov     r9d, 500h; jumptable 000000018001799D case 6
0x180017a7f  jmp     loc_1800179AD
0x180017a84  mov     r9d, 300h; jumptable 000000018001799D case 5
0x180017a8a  jmp     loc_1800179AD
0x180017a8f  mov     r9d, 100h; jumptable 000000018001799D cases 4,9
0x180017a95  jmp     loc_1800179AD
0x180017a9a  mov     r9d, 780h; jumptable 000000018001799D case 7
0x180017aa0  jmp     loc_1800179AD
0x180017aa5  mov     eax, ecx
0x180017aa7  jmp     loc_1800178F9
0x180017aac  xor     r9d, r9d; jumptable 000000018001799D default case, cases -1,2,3
0x180017aaf  jmp     loc_1800179AD
0x180017ab4  mov     eax, edx
0x180017ab6  jmp     loc_1800178F9
```
