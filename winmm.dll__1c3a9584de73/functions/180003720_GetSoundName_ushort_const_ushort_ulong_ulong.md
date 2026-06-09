# GetSoundName(ushort const *,ushort *,ulong,ulong &)

- ea: `0x180003720`
- end: `0x1800039b1`
- name: `?GetSoundName@@YAHPEBGPEAGKAEAK@Z`
- size: `657`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x1800027a0`
- `0x180004e0c`

## callees

- `0x180003720`
- `0x180003a70`
- `0x180004700`
- `0x180007380`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180003870`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800038dc`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180003870`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800038dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000382c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003995`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000382c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003995`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x180003984`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x180003984`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x18000381b`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x18000381b`
- `AudioSes!__imp_GetSoundAlias` at `0x18000376b`
- `AudioSes!__imp_GetSoundAlias` at `0x18000376b`

## string_xrefs

- `0x18000388c`: `MediaPath`

## pseudocode

```c
_BOOL8 __fastcall GetSoundName(const unsigned __int16 *a1, size_t *a2, __int64 a3, unsigned int *a4)
{
  int v4; // eax
  const unsigned __int16 *v7; // rbx
  __int64 v8; // rbp
  size_t *v9; // r8
  __int64 v10; // rax
  __int64 v11; // rdx
  size_t *v12; // rcx
  int v13; // r10d
  _BOOL8 result; // rax
  size_t *v15; // r8
  const WCHAR *v16; // rcx
  unsigned __int16 *v17; // r8
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-458h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-458h]
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-448h] BYREF
  wchar_t pszDest[256]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR Path[264]; // [rsp+240h] [rbp-238h] BYREF

  v4 = *a4;
  FilePart[0] = 0;
  v7 = a1;
  v8 = 2147483646;
  if ( (v4 & 0x10000) != 0 || (v4 & 0x20000) == 0 )
  {
    if ( (unsigned int)GetSoundAlias(a1, a2, 256) )
      goto LABEL_11;
    v10 = 2147483646;
    v11 = 256;
    v9 = a2;
    do
    {
      if ( !v10 )
        break;
      if ( !*v7 )
        break;
      *(_WORD *)v9 = *v7++;
      v9 = (size_t *)((char *)v9 + 2);
      --v10;
      --v11;
    }
    while ( v11 );
    v12 = (size_t *)((char *)v9 - 2);
    v13 = -2147024774;
    if ( v11 )
    {
      v12 = v9;
      v13 = 0;
    }
    *(_WORD *)v12 = 0;
  }
  else
  {
    v13 = StringCbCopyW((unsigned __int16 *)a2, 0x200u, a1);
  }
  if ( v13 )
  {
LABEL_13:
    result = 0;
    *(_WORD *)a2 = 0;
    return result;
  }
LABEL_11:
  if ( (*a4 & 0x200000) != 0 )
    return 1;
  if ( StringCopyWorkerW(pszDest, 0x100u, v9, (STRSAFE_PCNZWCH)a2, (size_t)lpBuffer) )
    goto LABEL_13;
  if ( !PathCchStripToRoot(pszDest, 0x100u) && PathCchIsRoot(pszDest) )
  {
    if ( GetFileAttributesW((LPCWSTR)a2) != -1 )
      return 1;
    v18 = 256;
    v20 = (unsigned __int16 *)a2;
    while ( *v20 )
    {
      ++v20;
      if ( !--v18 )
        goto LABEL_16;
    }
    v16 = L".WAV";
    v17 = (unsigned __int16 *)a2 + 256 - v18;
    do
    {
      if ( !v8 )
        break;
      if ( !*v16 )
        break;
      *v17++ = *v16++;
      --v8;
      --v18;
    }
    while ( v18 );
    v19 = v17 - 1;
    if ( v18 )
      v19 = v17;
    *v19 = 0;
    if ( v18 )
      return 1;
  }
LABEL_16:
  if ( GetFileAttributesW((LPCWSTR)a2) != -1 )
    return 1;
  if ( StringCopyWorkerW(pszDest, 0x100u, v15, (STRSAFE_PCNZWCH)a2, (size_t)lpBuffera) )
    goto LABEL_13;
  if ( SearchPathW(0, pszDest, L".WAV", 0x100u, (LPWSTR)a2, FilePart)
    || !(unsigned int)mmRegQueryValue(HKEY_LOCAL_MACHINE, aszSetup, aszValMedia, 0x104u, Path) )
  {
    return 1;
  }
  return SearchPathW(Path, pszDest, L".WAV", 0x100u, (LPWSTR)a2, FilePart) != 0;
}

```

## disassembly

```asm
0x180003720  mov     [rsp+arg_10], rbx
0x180003725  push    rbp
0x180003726  push    rsi
0x180003727  push    rdi
0x180003728  sub     rsp, 460h
0x18000372f  mov     rax, cs:__security_cookie
0x180003736  xor     rax, rsp
0x180003739  mov     [rsp+478h+var_28], rax
0x180003741  mov     eax, [r9]
0x180003744  mov     rsi, r9
0x180003747  mov     [rsp+478h+FilePart], 0
0x180003750  mov     rdi, rdx
0x180003753  mov     rbx, rcx
0x180003756  mov     ebp, 7FFFFFFEh
0x18000375b  bt      eax, 10h
0x18000375f  jnb     loc_18000395D
0x180003765  mov     r8d, 100h
0x18000376b  call    cs:__imp_GetSoundAlias
0x180003771  test    eax, eax
0x180003773  jnz     short loc_1800037C4
0x180003775  mov     rax, rbp
0x180003778  mov     edx, 100h
0x18000377d  mov     r8, rdi
0x180003780  test    rax, rax
0x180003783  jz      short loc_1800037A2
0x180003785  movzx   ecx, word ptr [rbx]
0x180003788  test    cx, cx
0x18000378b  jz      short loc_1800037A2
0x18000378d  mov     [r8], cx
0x180003791  add     rbx, 2
0x180003795  add     r8, 2; pcchNewDestLength
0x180003799  dec     rax
0x18000379c  sub     rdx, 1
0x1800037a0  jnz     short loc_180003780
0x1800037a2  test    rdx, rdx
0x1800037a5  lea     rcx, [r8-2]
0x1800037a9  mov     r10d, 8007007Ah
0x1800037af  cmovnz  rcx, r8
0x1800037b3  xor     eax, eax
0x1800037b5  test    rdx, rdx
0x1800037b8  cmovnz  r10d, eax
0x1800037bc  mov     [rcx], ax
0x1800037bf  test    r10d, r10d
0x1800037c2  jnz     short loc_1800037F4
0x1800037c4  test    dword ptr [rsi], 200000h
0x1800037ca  jz      short loc_1800037FB
0x1800037cc  mov     eax, 1
0x1800037d1  mov     rcx, [rsp+478h+var_28]
0x1800037d9  xor     rcx, rsp; StackCookie
0x1800037dc  call    __security_check_cookie
0x1800037e1  mov     rbx, [rsp+478h+arg_10]
0x1800037e9  add     rsp, 460h
0x1800037f0  pop     rdi
0x1800037f1  pop     rsi
0x1800037f2  pop     rbp
0x1800037f3  retn
0x1800037f4  xor     eax, eax
0x1800037f6  mov     [rdi], ax
0x1800037f9  jmp     short loc_1800037D1
0x1800037fb  mov     r9, rdi; pszSrc
0x1800037fe  lea     rcx, [rsp+478h+pszDest]; pszDest
0x180003803  mov     edx, 100h; cchDest
0x180003808  call    StringCopyWorkerW
0x18000380d  test    eax, eax
0x18000380f  jnz     short loc_1800037F4
0x180003811  mov     edx, 100h; cchPath
0x180003816  lea     rcx, [rsp+478h+pszDest]; pszPath
0x18000381b  call    cs:__imp_PathCchStripToRoot
0x180003821  test    eax, eax
0x180003823  jz      loc_18000397F
0x180003829  mov     rcx, rdi; lpFileName
0x18000382c  call    cs:__imp_GetFileAttributesW
0x180003832  cmp     eax, 0FFFFFFFFh
0x180003835  jnz     short loc_1800037CC
0x180003837  mov     r9, rdi; pszSrc
0x18000383a  lea     rcx, [rsp+478h+pszDest]; pszDest
0x18000383f  mov     edx, 100h; cchDest
0x180003844  call    StringCopyWorkerW
0x180003849  test    eax, eax
0x18000384b  jnz     short loc_1800037F4
0x18000384d  lea     rax, [rsp+478h+FilePart]
0x180003852  mov     r9d, 100h; nBufferLength
0x180003858  mov     [rsp+478h+lpFilePart], rax; lpFilePart
0x18000385d  lea     r8, Extension; ".WAV"
0x180003864  lea     rdx, [rsp+478h+pszDest]; lpFileName
0x180003869  mov     [rsp+478h+lpBuffer], rdi; lpBuffer
0x18000386e  xor     ecx, ecx; lpPath
0x180003870  call    cs:__imp_SearchPathW
0x180003876  test    eax, eax
0x180003878  jnz     loc_1800037CC
0x18000387e  lea     rax, [rsp+478h+Path]
0x180003886  mov     r9d, 104h; unsigned int
0x18000388c  lea     r8, ?aszValMedia@@3PAGA; "MediaPath"
0x180003893  mov     [rsp+478h+lpBuffer], rax; PVOID
0x180003898  lea     rdx, ?aszSetup@@3PAGA; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000389f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800038a6  call    ?mmRegQueryValue@@YAHPEAUHKEY__@@PEBG1KPEAG@Z; mmRegQueryValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort *)
0x1800038ab  test    eax, eax
0x1800038ad  jz      loc_1800037CC
0x1800038b3  lea     rax, [rsp+478h+FilePart]
0x1800038b8  mov     r9d, 100h; nBufferLength
0x1800038be  mov     [rsp+478h+lpFilePart], rax; lpFilePart
0x1800038c3  lea     r8, Extension; ".WAV"
0x1800038ca  lea     rdx, [rsp+478h+pszDest]; lpFileName
0x1800038cf  mov     [rsp+478h+lpBuffer], rdi; lpBuffer
0x1800038d4  lea     rcx, [rsp+478h+Path]; lpPath
0x1800038dc  call    cs:__imp_SearchPathW
0x1800038e2  xor     ecx, ecx
0x1800038e4  test    eax, eax
0x1800038e6  setnz   cl
0x1800038e9  mov     eax, ecx
0x1800038eb  jmp     loc_1800037D1
0x1800038f0  cmp     word ptr [rax], 0
0x1800038f4  jnz     short loc_18000394E
0x1800038f6  mov     eax, 100h
0x1800038fb  lea     rcx, Extension; ".WAV"
0x180003902  sub     rax, rdx
0x180003905  lea     r8, [rdi+rax*2]
0x180003909  test    rdx, rdx
0x18000390c  jz      short loc_180003930
0x18000390e  test    rbp, rbp
0x180003911  jz      short loc_180003930
0x180003913  movzx   eax, word ptr [rcx]
0x180003916  test    ax, ax
0x180003919  jz      short loc_180003930
0x18000391b  mov     [r8], ax
0x18000391f  add     rcx, 2
0x180003923  add     r8, 2
0x180003927  dec     rbp
0x18000392a  sub     rdx, 1
0x18000392e  jnz     short loc_18000390E
0x180003930  test    rdx, rdx
0x180003933  lea     rcx, [r8-2]
0x180003937  cmovnz  rcx, r8
0x18000393b  xor     eax, eax
0x18000393d  mov     [rcx], ax
0x180003940  test    rdx, rdx
0x180003943  jnz     loc_1800037CC
0x180003949  jmp     loc_180003829
0x18000394e  add     rax, 2
0x180003952  sub     rdx, 1
0x180003956  jnz     short loc_1800038F0
0x180003958  jmp     loc_180003829
0x18000395d  bt      eax, 11h
0x180003961  jnb     loc_180003765
0x180003967  mov     r8, rcx; unsigned __int16 *
0x18000396a  mov     edx, 200h; unsigned __int64
0x18000396f  mov     rcx, rdi; unsigned __int16 *
0x180003972  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180003977  mov     r10d, eax
0x18000397a  jmp     loc_1800037BF
0x18000397f  lea     rcx, [rsp+478h+pszDest]; pszPath
0x180003984  call    cs:__imp_PathCchIsRoot
0x18000398a  test    eax, eax
0x18000398c  jz      loc_180003829
0x180003992  mov     rcx, rdi; lpFileName
0x180003995  call    cs:__imp_GetFileAttributesW
0x18000399b  cmp     eax, 0FFFFFFFFh
0x18000399e  jnz     loc_1800037CC
0x1800039a4  mov     edx, 100h
0x1800039a9  mov     rax, rdi
0x1800039ac  jmp     loc_1800038F0
```
