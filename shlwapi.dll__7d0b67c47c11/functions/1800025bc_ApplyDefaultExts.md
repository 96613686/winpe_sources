# ApplyDefaultExts

- ea: `0x1800025bc`
- end: `0x1800028a8`
- name: `ApplyDefaultExts`
- size: `748`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022c0`

## callees

- `0x1800025bc`
- `0x1800028b0`
- `0x180003400`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002724`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180002724`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800026c0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800026c0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002731`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002731`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180002621`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180002621`

## pseudocode

```c
__int64 __fastcall ApplyDefaultExts(LPCWSTR lpFileName, __int64 a2, __int64 a3, _OWORD *a4)
{
  _OWORD *v4; // rbx
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rsi
  __int64 v8; // rbp
  unsigned int v9; // r15d
  unsigned __int64 v10; // r12
  __int64 v11; // rdx
  const wchar_t *v12; // r9
  unsigned __int64 v13; // r8
  WCHAR *v14; // rax
  WCHAR *v15; // rdx
  HANDLE FirstFileW; // rdi
  unsigned int v18; // eax
  _OWORD *v19; // rcx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int64 v27; // rbp
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int64 v32; // rcx
  const WCHAR *v33; // r14
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
  _OWORD *v35; // rax
  __int64 v36; // rdx
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  _BYTE v48[592]; // [rsp+20h] [rbp-4E8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+270h] [rbp-298h] BYREF

  v4 = a4;
  if ( a4 )
    memset_0(a4, 0, 0x250u);
  v6 = -1;
  do
    ++v6;
  while ( lpFileName[v6] );
  if ( v6 > 0xFF )
    return 0;
  v7 = (WCHAR *)&lpFileName[v6];
  v8 = v7 - PathFindFileNameW(lpFileName);
  v9 = 7;
  memset_0(v48, 0, sizeof(v48));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10 = 260 - v6;
  if ( 260 - v6 > 0x7FFFFFFF )
  {
    *v7 = 0;
  }
  else
  {
    v11 = 2147483646;
    v12 = L".*";
    v13 = 260 - v6;
    v14 = (WCHAR *)&lpFileName[v6];
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v14++ = *v12++;
      --v11;
      --v13;
    }
    while ( v13 );
    v15 = v14 - 1;
    if ( v13 )
      v15 = v14;
    *v15 = 0;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_15;
  v32 = (unsigned int)v8;
  v27 = 4;
  v33 = &FindFileData.cFileName[v32];
  do
  {
    v18 = FindInDefExts(v33);
    if ( v18 < v9 )
    {
      v9 = v18;
      p_FindFileData = &FindFileData;
      v35 = v48;
      v36 = 4;
      do
      {
        v37 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
        *v35 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
        v38 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
        v35[1] = v37;
        v39 = *(_OWORD *)&p_FindFileData->cFileName[2];
        v35[2] = v38;
        v40 = *(_OWORD *)&p_FindFileData->cFileName[10];
        v35[3] = v39;
        v41 = *(_OWORD *)&p_FindFileData->cFileName[18];
        v35[4] = v40;
        v42 = *(_OWORD *)&p_FindFileData->cFileName[26];
        v35[5] = v41;
        v43 = *(_OWORD *)&p_FindFileData->cFileName[34];
        p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
        v35[6] = v42;
        v35[7] = v43;
        v35 += 8;
        --v36;
      }
      while ( v36 );
      v44 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
      *v35 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      v45 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
      v35[1] = v44;
      v46 = *(_OWORD *)&p_FindFileData->cFileName[2];
      v35[2] = v45;
      v47 = *(_OWORD *)&p_FindFileData->cFileName[10];
      v35[3] = v46;
      v35[4] = v47;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
  if ( v9 >= 7 )
  {
LABEL_15:
    *v7 = 0;
    return 0;
  }
  StringCchCopyW(v7, v10, (const unsigned __int16 *)(&c_aDefExtList)[v9]);
  if ( v4 )
  {
    v19 = v48;
    do
    {
      v20 = v19[1];
      *v4 = *v19;
      v21 = v19[2];
      v4[1] = v20;
      v22 = v19[3];
      v4[2] = v21;
      v23 = v19[4];
      v4[3] = v22;
      v24 = v19[5];
      v4[4] = v23;
      v25 = v19[6];
      v4[5] = v24;
      v26 = v19[7];
      v19 += 8;
      v4[6] = v25;
      v4[7] = v26;
      v4 += 8;
      --v27;
    }
    while ( v27 );
    v28 = v19[1];
    *v4 = *v19;
    v29 = v19[2];
    v4[1] = v28;
    v30 = v19[3];
    v4[2] = v29;
    v31 = v19[4];
    v4[3] = v30;
    v4[4] = v31;
  }
  return 1;
}

```

## disassembly

```asm
0x1800025bc  mov     [rsp+arg_8], rbx
0x1800025c1  push    rbp
0x1800025c2  push    rsi
0x1800025c3  push    rdi
0x1800025c4  push    r12
0x1800025c6  push    r13
0x1800025c8  push    r14
0x1800025ca  push    r15
0x1800025cc  sub     rsp, 4D0h
0x1800025d3  mov     rax, cs:__security_cookie
0x1800025da  xor     rax, rsp
0x1800025dd  mov     [rsp+508h+var_48], rax
0x1800025e5  xor     eax, eax
0x1800025e7  mov     rbx, r9
0x1800025ea  mov     r13d, r8d
0x1800025ed  mov     r14, rcx
0x1800025f0  mov     r12d, 250h
0x1800025f6  test    r9, r9
0x1800025f9  jnz     loc_1800027E4
0x1800025ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002603  inc     rdi
0x180002606  cmp     [r14+rdi*2], ax
0x18000260b  jnz     short loc_180002603
0x18000260d  cmp     rdi, 0FFh
0x180002614  ja      loc_1800026D8
0x18000261a  mov     rcx, r14; pszPath
0x18000261d  lea     rsi, [r14+rdi*2]
0x180002621  call    cs:__imp_PathFindFileNameW
0x180002627  mov     rbp, rsi
0x18000262a  lea     rcx, [rsp+508h+var_4E8]; void *
0x18000262f  sub     rbp, rax
0x180002632  mov     r8, r12; Size
0x180002635  xor     edx, edx; Val
0x180002637  sar     rbp, 1
0x18000263a  mov     r15d, 7
0x180002640  call    memset_0
0x180002645  mov     r8, r12; Size
0x180002648  lea     rcx, [rsp+508h+FindFileData]; void *
0x180002650  xor     edx, edx; Val
0x180002652  call    memset_0
0x180002657  mov     r12d, 104h
0x18000265d  sub     r12, rdi
0x180002660  jz      short loc_1800026B5
0x180002662  cmp     r12, 7FFFFFFFh
0x180002669  ja      loc_1800027F8
0x18000266f  mov     edx, 7FFFFFFEh
0x180002674  lea     r9, asc_18003BDF8; ".*"
0x18000267b  mov     r8, r12
0x18000267e  mov     rax, rsi
0x180002681  xor     r10d, r10d
0x180002684  test    rdx, rdx
0x180002687  jz      short loc_1800026A6
0x180002689  movzx   ecx, word ptr [r9]
0x18000268d  test    cx, cx
0x180002690  jz      short loc_1800026A6
0x180002692  mov     [rax], cx
0x180002695  add     r9, 2
0x180002699  add     rax, 2
0x18000269d  dec     rdx
0x1800026a0  sub     r8, 1
0x1800026a4  jnz     short loc_180002684
0x1800026a6  test    r8, r8
0x1800026a9  lea     rdx, [rax-2]
0x1800026ad  cmovnz  rdx, rax
0x1800026b1  mov     [rdx], r10w
0x1800026b5  lea     rdx, [rsp+508h+FindFileData]; lpFindFileData
0x1800026bd  mov     rcx, r14; lpFileName
0x1800026c0  call    cs:__imp_FindFirstFileW
0x1800026c6  mov     rdi, rax
0x1800026c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800026cd  jnz     loc_180002802
0x1800026d3  xor     eax, eax
0x1800026d5  mov     [rsi], ax
0x1800026d8  xor     eax, eax
0x1800026da  mov     rcx, [rsp+508h+var_48]
0x1800026e2  xor     rcx, rsp; StackCookie
0x1800026e5  call    __security_check_cookie
0x1800026ea  mov     rbx, [rsp+508h+arg_8]
0x1800026f2  add     rsp, 4D0h
0x1800026f9  pop     r15
0x1800026fb  pop     r14
0x1800026fd  pop     r13
0x1800026ff  pop     r12
0x180002701  pop     rdi
0x180002702  pop     rsi
0x180002703  pop     rbp
0x180002704  retn
0x180002705  mov     edx, r13d
0x180002708  mov     rcx, r14; psz1
0x18000270b  call    _FindInDefExts
0x180002710  cmp     eax, r15d
0x180002713  jb      loc_18000281A
0x180002719  lea     rdx, [rsp+508h+FindFileData]; lpFindFileData
0x180002721  mov     rcx, rdi; hFindFile
0x180002724  call    cs:__imp_FindNextFileW
0x18000272a  test    eax, eax
0x18000272c  jnz     short loc_180002705
0x18000272e  mov     rcx, rdi; hFindFile
0x180002731  call    cs:__imp_FindClose
0x180002737  cmp     r15d, 7
0x18000273b  jnb     short loc_1800026D3
0x18000273d  lea     rax, ?c_aDefExtList@@3QBQEBGB; ushort const * const near * const c_aDefExtList
0x180002744  mov     r8d, r15d
0x180002747  mov     rdx, r12; unsigned __int64
0x18000274a  mov     rcx, rsi; unsigned __int16 *
0x18000274d  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180002751  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002756  test    rbx, rbx
0x180002759  jnz     short loc_180002765
0x18000275b  mov     eax, 1
0x180002760  jmp     loc_1800026DA
0x180002765  lea     rcx, [rsp+508h+var_4E8]
0x18000276a  mov     eax, 80h
0x18000276f  movups  xmm0, xmmword ptr [rcx]
0x180002772  movups  xmm1, xmmword ptr [rcx+10h]
0x180002776  movups  xmmword ptr [rbx], xmm0
0x180002779  movups  xmm0, xmmword ptr [rcx+20h]
0x18000277d  movups  xmmword ptr [rbx+10h], xmm1
0x180002781  movups  xmm1, xmmword ptr [rcx+30h]
0x180002785  movups  xmmword ptr [rbx+20h], xmm0
0x180002789  movups  xmm0, xmmword ptr [rcx+40h]
0x18000278d  movups  xmmword ptr [rbx+30h], xmm1
0x180002791  movups  xmm1, xmmword ptr [rcx+50h]
0x180002795  movups  xmmword ptr [rbx+40h], xmm0
0x180002799  movups  xmm0, xmmword ptr [rcx+60h]
0x18000279d  movups  xmmword ptr [rbx+50h], xmm1
0x1800027a1  movups  xmm1, xmmword ptr [rcx+70h]
0x1800027a5  add     rcx, rax
0x1800027a8  movups  xmmword ptr [rbx+60h], xmm0
0x1800027ac  movups  xmmword ptr [rbx+70h], xmm1
0x1800027b0  add     rbx, rax
0x1800027b3  sub     rbp, 1
0x1800027b7  jnz     short loc_18000276F
0x1800027b9  movups  xmm0, xmmword ptr [rcx]
0x1800027bc  movups  xmm1, xmmword ptr [rcx+10h]
0x1800027c0  movups  xmmword ptr [rbx], xmm0
0x1800027c3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800027c7  movups  xmmword ptr [rbx+10h], xmm1
0x1800027cb  movups  xmm1, xmmword ptr [rcx+30h]
0x1800027cf  movups  xmmword ptr [rbx+20h], xmm0
0x1800027d3  movups  xmm0, xmmword ptr [rcx+40h]
0x1800027d7  movups  xmmword ptr [rbx+30h], xmm1
0x1800027db  movups  xmmword ptr [rbx+40h], xmm0
0x1800027df  jmp     loc_18000275B
0x1800027e4  mov     r8, r12; Size
0x1800027e7  xor     edx, edx; Val
0x1800027e9  mov     rcx, rbx; void *
0x1800027ec  call    memset_0
0x1800027f1  xor     eax, eax
0x1800027f3  jmp     loc_1800025FF
0x1800027f8  xor     eax, eax
0x1800027fa  mov     [rsi], ax
0x1800027fd  jmp     loc_1800026B5
0x180002802  mov     ecx, ebp
0x180002804  lea     r14, [rsp+508h+FindFileData.cFileName]
0x18000280c  mov     ebp, 4
0x180002811  lea     r14, [r14+rcx*2]
0x180002815  jmp     loc_180002705
0x18000281a  mov     r15d, eax
0x18000281d  lea     rcx, [rsp+508h+FindFileData]
0x180002825  lea     rax, [rsp+508h+var_4E8]
0x18000282a  mov     rdx, rbp
0x18000282d  mov     r8d, 80h
0x180002833  movups  xmm0, xmmword ptr [rcx]
0x180002836  movups  xmm1, xmmword ptr [rcx+10h]
0x18000283a  movups  xmmword ptr [rax], xmm0
0x18000283d  movups  xmm0, xmmword ptr [rcx+20h]
0x180002841  movups  xmmword ptr [rax+10h], xmm1
0x180002845  movups  xmm1, xmmword ptr [rcx+30h]
0x180002849  movups  xmmword ptr [rax+20h], xmm0
0x18000284d  movups  xmm0, xmmword ptr [rcx+40h]
0x180002851  movups  xmmword ptr [rax+30h], xmm1
0x180002855  movups  xmm1, xmmword ptr [rcx+50h]
0x180002859  movups  xmmword ptr [rax+40h], xmm0
0x18000285d  movups  xmm0, xmmword ptr [rcx+60h]
0x180002861  movups  xmmword ptr [rax+50h], xmm1
0x180002865  movups  xmm1, xmmword ptr [rcx+70h]
0x180002869  add     rcx, r8
0x18000286c  movups  xmmword ptr [rax+60h], xmm0
0x180002870  movups  xmmword ptr [rax+70h], xmm1
0x180002874  add     rax, r8
0x180002877  sub     rdx, 1
0x18000287b  jnz     short loc_180002833
0x18000287d  movups  xmm0, xmmword ptr [rcx]
0x180002880  movups  xmm1, xmmword ptr [rcx+10h]
0x180002884  movups  xmmword ptr [rax], xmm0
0x180002887  movups  xmm0, xmmword ptr [rcx+20h]
0x18000288b  movups  xmmword ptr [rax+10h], xmm1
0x18000288f  movups  xmm1, xmmword ptr [rcx+30h]
0x180002893  movups  xmmword ptr [rax+20h], xmm0
0x180002897  movups  xmm0, xmmword ptr [rcx+40h]
0x18000289b  movups  xmmword ptr [rax+30h], xmm1
0x18000289f  movups  xmmword ptr [rax+40h], xmm0
0x1800028a3  jmp     loc_180002719
```
