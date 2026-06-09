# CScopeList::ApplyFolderDisplayNarrowAlias(TLMString<64,64,32767> &,wchar_t *,uint *)

- ea: `0x1801595b0`
- end: `0x180159ad9`
- name: `?ApplyFolderDisplayNarrowAlias@CScopeList@@QEAAJAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@PEA_WPEAI@Z`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800d7f50`

## callees

- `0x18003b678`
- `0x18008efd8`
- `0x18008f4a4`
- `0x18008fa8c`
- `0x18008fb4c`
- `0x1800f3e64`
- `0x1800fe3b4`
- `0x1801050c8`
- `0x18012bee4`
- `0x1801590dc`
- `0x1801595b0`
- `0x18016b4d0`
- `0x18017a674`
- `0x180188d90`
- `0x180273cbc`
- `0x180273edc`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18015980b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18015980b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180159679`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801597c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801597f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180159679`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801597c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1801597f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CScopeList::ApplyFolderDisplayNarrowAlias(__int64 a1, __int64 a2, wchar_t *a3, unsigned int *a4)
{
  unsigned int v7; // r12d
  const WCHAR *v8; // rax
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rsi
  int v12; // r15d
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rax
  unsigned int *v16; // rax
  int *v17; // rbx
  const wchar_t *Buffer; // rdi
  const wchar_t *v19; // r15
  int v20; // esi
  unsigned int v21; // eax
  wchar_t v23; // dx
  __int64 v24; // rbx
  wchar_t *v25; // rax
  unsigned int *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  char *v30; // rcx
  const wchar_t *v31; // rax
  unsigned int v32[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v35; // [rsp+38h] [rbp-C8h]
  void **v36; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszPath; // [rsp+58h] [rbp-A8h]
  int v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+64h] [rbp-9Ch]
  wchar_t v40[68]; // [rsp+68h] [rbp-98h] BYREF
  void **v41; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *v42; // [rsp+F8h] [rbp-8h]
  __int64 v43; // [rsp+100h] [rbp+0h]
  wchar_t v44[68]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v45[2]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v46; // [rsp+1A0h] [rbp+A0h]
  __int16 v47; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v48[3]; // [rsp+230h] [rbp+130h] BYREF
  __int16 v49; // [rsp+248h] [rbp+148h] BYREF
  char v50[8]; // [rsp+2D0h] [rbp+1D0h] BYREF
  LPCWSTR pszPath2; // [rsp+2D8h] [rbp+1D8h]

  *(_QWORD *)v32 = a1;
  v7 = *a4;
  v42 = v44;
  v43 = 65;
  v44[0] = 0;
  v41 = &CCICommonPathString::`vftable';
  v36 = &CLMString::`vftable';
  pszPath = v40;
  v38 = 65;
  CLMString::AssignInConstructor((CLMString *)&v36, *(const wchar_t **)(a2 + 8), 0xFFFFFFFF);
  v36 = &CCICommonPathString::`vftable';
  if ( !v39 || (v8 = pszPath, pszPath[v39 - 1] != 92) )
  {
    CLMString::Append((CLMString *)&v36, L"\\", 0xFFFFFFFF);
    v8 = pszPath;
  }
  if ( !PathIsRootW(v8) )
  {
    v9 = CLMString::Find((CLMString *)a2, 0x3Au, 0);
    v10 = v9;
    if ( v9 < 3
      || (v11 = (unsigned int)(*(_DWORD *)(a2 + 20) - 1), *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v11) != 41)
      || (v12 = v9 + 1, (unsigned int)CLMString::Find((CLMString *)a2, 0x3Au, v9 + 1) != -1)
      || (int)v11 < v12
      || (v13 = *(_QWORD *)(a2 + 8), *(_WORD *)(v13 + 2LL * (unsigned int)(v10 - 2)) != 40)
      || *(_WORD *)(v13 + 2LL * (unsigned int)(v10 - 3)) != 32 )
    {
      v21 = 2 * *(_DWORD *)(a2 + 20) + 2;
      *a4 = v21;
      if ( v7 >= v21 )
      {
        v36 = &CCICommonPathString::`vftable';
        CLMString::DeleteBuf((CLMString *)&v36, v40);
        v36 = &CLMString::`vftable';
        v41 = &CCICommonPathString::`vftable';
        CLMString::DeleteBuf((CLMString *)&v41, v44);
        return 2147500037LL;
      }
      else
      {
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v36);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v41);
        return 2147942522LL;
      }
    }
    v14 = v10 - 1;
    v15 = CLMString::Mid(a2, &v34, v14, (unsigned int)v11 - v14);
    CLMString::operator=(&v41, v15);
    AppendBackSlashIf((struct CLMString *)&v41);
    v16 = (unsigned int *)CLMString::Mid(a2, &v34, 0, v14 - 2);
    CLMString::Append(
      (CLMString *)&v41,
      (const wchar_t *)(*(_QWORD *)(*((_QWORD *)v16 + 1) + 8LL) + 2LL * *v16),
      v16[1]);
  }
  v34 = *(_QWORD *)v32 + 8LL;
  v35 = 0;
  while ( (unsigned int)CScopeListEnumerator::operator++(&v34) )
  {
    v17 = (int *)v35;
    if ( (_QWORD)v35 )
      v17 = *(int **)(v35 + 8);
    Buffer = CLMString::GetBuffer((CLMString *)(v17 + 88), 0);
    v32[0] = v17[93];
    v19 = CLMString::GetBuffer((CLMString *)(v17 + 128), 0);
    v20 = v17[133];
    if ( PathIsRootW(pszPath) )
    {
      TLMString<64,64,32767>::TLMString<64,64,32767>(v50, Buffer);
      AppendBackSlashIf((struct CLMString *)v50);
      if ( PathIsRootW(pszPath2) && PathIsSameRootW(pszPath, pszPath2) )
      {
        v29 = 2 * v20 + 2;
        *a4 = v29;
        if ( v7 >= v29 )
          v28 = StringCbCopyW(a3, v29, v19);
        else
          v28 = -2147024774;
        v30 = v50;
LABEL_31:
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v30);
        goto LABEL_33;
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v50);
    }
    else if ( (unsigned int)CompareScopes(Buffer, v17[86], v42) )
    {
      v48[1] = &v49;
      v48[2] = 65;
      v49 = 0;
      v48[0] = &CCICommonPathString::`vftable';
      CLMString::Append((CLMString *)v48, v19, 0xFFFFFFFF);
      CLMString::Mid(&v41, v32, v32[0], HIDWORD(v43) - v32[0]);
      CLMString::Append((CLMString *)v48, (const wchar_t *)(*(_QWORD *)(v33 + 8) + 2LL * v32[0]), v32[1]);
      v24 = (int)CLMString::ReverseFindT((CLMString *)v48, v23);
      v45[1] = &v47;
      v46 = 65;
      v47 = 0;
      v45[0] = &CCICommonPathString::`vftable';
      v25 = CLMString::GetBuffer((CLMString *)v48, 0);
      CLMString::Append((CLMString *)v45, &v25[v24 + 1], 0xFFFFFFFF);
      CLMString::Append((CLMString *)v45, L" (", 0xFFFFFFFF);
      v26 = (unsigned int *)CLMString::Mid(v48, &v34, 0, (unsigned int)v24);
      CLMString::Append(
        (CLMString *)v45,
        (const wchar_t *)(*(_QWORD *)(*((_QWORD *)v26 + 1) + 8LL) + 2LL * *v26),
        v26[1]);
      CLMString::Append((CLMString *)v45, L")", 0xFFFFFFFF);
      v27 = 2 * HIDWORD(v46) + 2;
      *a4 = v27;
      if ( v7 < v27 )
      {
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v45);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v48);
        v28 = -2147024774;
        goto LABEL_33;
      }
      v31 = CLMString::GetBuffer((CLMString *)v45, 0);
      v28 = StringCbCopyW(a3, *a4, v31);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v45);
      v30 = (char *)v48;
      goto LABEL_31;
    }
  }
  v28 = -2147467259;
LABEL_33:
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v36);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v41);
  return v28;
}

```

## disassembly

```asm
0x1801595b0  mov     [rsp-8+arg_0], rbx
0x1801595b5  push    rbp
0x1801595b6  push    rsi
0x1801595b7  push    rdi
0x1801595b8  push    r12
0x1801595ba  push    r13
0x1801595bc  push    r14
0x1801595be  push    r15
0x1801595c0  lea     rbp, [rsp-280h]
0x1801595c8  sub     rsp, 380h
0x1801595cf  mov     rax, cs:__security_cookie
0x1801595d6  xor     rax, rsp
0x1801595d9  mov     [rbp+2B0h+var_40], rax
0x1801595e0  mov     r14, r9
0x1801595e3  mov     r13, r8
0x1801595e6  mov     rdi, rdx
0x1801595e9  mov     qword ptr [rsp+3B0h+var_390], rcx
0x1801595ee  mov     r12d, [r9]
0x1801595f1  lea     rax, [rbp+2B0h+var_2A8]
0x1801595f5  mov     [rbp+2B0h+var_2B8], rax
0x1801595f9  mov     ecx, 41h ; 'A'
0x1801595fe  mov     [rbp+2B0h+var_2B0], rcx
0x180159602  xor     eax, eax
0x180159604  mov     [rbp+2B0h+var_2A8], ax
0x180159608  lea     rsi, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x18015960f  mov     [rbp+2B0h+var_2C0], rsi
0x180159613  lea     r15, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18015961a  mov     [rsp+3B0h+var_360], r15
0x18015961f  lea     rax, [rsp+3B0h+var_348]
0x180159624  mov     [rsp+3B0h+pszPath], rax
0x180159629  mov     [rsp+3B0h+var_350], ecx
0x18015962d  or      ebx, 0FFFFFFFFh
0x180159630  mov     r8d, ebx; unsigned int
0x180159633  mov     rdx, [rdx+8]; wchar_t *
0x180159637  lea     rcx, [rsp+3B0h+var_360]; this
0x18015963c  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180159641  mov     [rsp+3B0h+var_360], rsi
0x180159646  mov     eax, [rsp+3B0h+var_34C]
0x18015964a  test    eax, eax
0x18015964c  jz      short loc_18015965D
0x18015964e  lea     ecx, [rax-1]
0x180159651  mov     rax, [rsp+3B0h+pszPath]
0x180159656  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18015965b  jz      short loc_180159676
0x18015965d  mov     r8d, ebx; unsigned int
0x180159660  lea     rdx, S; "\\"
0x180159667  lea     rcx, [rsp+3B0h+var_360]; this
0x18015966c  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180159671  mov     rax, [rsp+3B0h+pszPath]
0x180159676  mov     rcx, rax; pszPath
0x180159679  call    cs:__imp_PathIsRootW
0x18015967f  test    eax, eax
0x180159681  jnz     loc_180159756
0x180159687  lea     edx, [rax+3Ah]; wchar_t
0x18015968a  xor     r8d, r8d; unsigned int
0x18015968d  mov     rcx, rdi; this
0x180159690  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x180159695  mov     ebx, eax
0x180159697  cmp     eax, 3
0x18015969a  jl      loc_180159838
0x1801596a0  mov     esi, [rdi+14h]
0x1801596a3  dec     esi
0x1801596a5  mov     rcx, [rdi+8]
0x1801596a9  cmp     word ptr [rcx+rsi*2], 29h ; ')'
0x1801596ae  jnz     loc_180159831
0x1801596b4  lea     r15d, [rax+1]
0x1801596b8  mov     edx, 3Ah ; ':'; wchar_t
0x1801596bd  mov     r8d, r15d; unsigned int
0x1801596c0  mov     rcx, rdi; this
0x1801596c3  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x1801596c8  cmp     eax, 0FFFFFFFFh
0x1801596cb  jnz     loc_18015982A
0x1801596d1  cmp     esi, r15d
0x1801596d4  jl      loc_18015982A
0x1801596da  mov     rdx, [rdi+8]
0x1801596de  lea     eax, [rbx-2]
0x1801596e1  cmp     word ptr [rdx+rax*2], 28h ; '('
0x1801596e6  jnz     loc_18015982A
0x1801596ec  lea     eax, [rbx-3]
0x1801596ef  cmp     word ptr [rdx+rax*2], 20h ; ' '
0x1801596f4  jnz     loc_18015982A
0x1801596fa  dec     ebx
0x1801596fc  sub     esi, ebx
0x1801596fe  mov     r9d, esi
0x180159701  mov     r8d, ebx
0x180159704  lea     rdx, [rsp+3B0h+var_380]
0x180159709  mov     rcx, rdi
0x18015970c  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180159711  mov     rdx, rax
0x180159714  lea     rcx, [rbp+2B0h+var_2C0]
0x180159718  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x18015971d  lea     rcx, [rbp+2B0h+var_2C0]; struct CLMString *
0x180159721  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x180159726  lea     r9d, [rbx-2]
0x18015972a  xor     r8d, r8d
0x18015972d  lea     rdx, [rsp+3B0h+var_380]
0x180159732  mov     rcx, rdi
0x180159735  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x18015973a  mov     r8d, [rax]
0x18015973d  mov     rcx, [rax+8]
0x180159741  mov     rdx, [rcx+8]
0x180159745  lea     rdx, [rdx+r8*2]; wchar_t *
0x180159749  mov     r8d, [rax+4]; unsigned int
0x18015974d  lea     rcx, [rbp+2B0h+var_2C0]; this
0x180159751  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180159756  mov     rax, qword ptr [rsp+3B0h+var_390]
0x18015975b  add     rax, 8
0x18015975f  mov     [rsp+3B0h+var_380], rax
0x180159764  xorps   xmm0, xmm0
0x180159767  movdqu  [rsp+3B0h+var_378], xmm0
0x18015976d  lea     rcx, [rsp+3B0h+var_380]
0x180159772  call    ??ECScopeListEnumerator@@QEAAHXZ; CScopeListEnumerator::operator++(void)
0x180159777  test    eax, eax
0x180159779  jz      loc_180159A94
0x18015977f  mov     rbx, qword ptr [rsp+3B0h+var_378]
0x180159784  test    rbx, rbx
0x180159787  jz      short loc_18015978D
0x180159789  mov     rbx, [rbx+8]
0x18015978d  lea     rcx, [rbx+160h]; this
0x180159794  xor     edx, edx; int
0x180159796  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18015979b  mov     rdi, rax
0x18015979e  mov     eax, [rbx+174h]
0x1801597a4  mov     [rsp+3B0h+var_390], eax
0x1801597a8  lea     rcx, [rbx+200h]; this
0x1801597af  xor     edx, edx; int
0x1801597b1  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1801597b6  mov     r15, rax
0x1801597b9  mov     esi, [rbx+214h]
0x1801597bf  mov     rcx, [rsp+3B0h+pszPath]; pszPath
0x1801597c4  call    cs:__imp_PathIsRootW
0x1801597ca  test    eax, eax
0x1801597cc  jz      loc_18015989D
0x1801597d2  mov     rdx, rdi
0x1801597d5  lea     rcx, [rbp+2B0h+var_E0]
0x1801597dc  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x1801597e1  nop
0x1801597e2  lea     rcx, [rbp+2B0h+var_E0]; struct CLMString *
0x1801597e9  call    ?AppendBackSlashIf@@YAXAEAVCLMString@@@Z; AppendBackSlashIf(CLMString &)
0x1801597ee  mov     rcx, [rbp+2B0h+pszPath2]; pszPath
0x1801597f5  call    cs:__imp_PathIsRootW
0x1801597fb  test    eax, eax
0x1801597fd  jz      short loc_180159819
0x1801597ff  mov     rdx, [rbp+2B0h+pszPath2]; pszPath2
0x180159806  mov     rcx, [rsp+3B0h+pszPath]; pszPath1
0x18015980b  call    cs:__imp_PathIsSameRootW
0x180159811  test    eax, eax
0x180159813  jnz     loc_180159A2D
0x180159819  lea     rcx, [rbp+2B0h+var_E0]
0x180159820  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159825  jmp     loc_18015976D
0x18015982a  lea     r15, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180159831  lea     rsi, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x180159838  mov     eax, [rdi+14h]
0x18015983b  lea     eax, ds:2[rax*2]
0x180159842  mov     [r14], eax
0x180159845  cmp     r12d, eax
0x180159848  jnb     short loc_180159868
0x18015984a  lea     rcx, [rsp+3B0h+var_360]
0x18015984f  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159854  nop
0x180159855  lea     rcx, [rbp+2B0h+var_2C0]
0x180159859  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18015985e  mov     eax, 8007007Ah
0x180159863  jmp     loc_180159AAF
0x180159868  mov     [rsp+3B0h+var_360], rsi
0x18015986d  lea     rdx, [rsp+3B0h+var_348]; wchar_t *
0x180159872  lea     rcx, [rsp+3B0h+var_360]; this
0x180159877  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18015987c  mov     [rsp+3B0h+var_360], r15
0x180159881  mov     [rbp+2B0h+var_2C0], rsi
0x180159885  lea     rdx, [rbp+2B0h+var_2A8]; wchar_t *
0x180159889  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18015988d  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180159892  nop
0x180159893  mov     eax, 80004005h
0x180159898  jmp     loc_180159AAF
0x18015989d  mov     r8, [rbp+2B0h+var_2B8]; wchar_t *
0x1801598a1  mov     edx, [rbx+158h]; int
0x1801598a7  mov     rcx, rdi; wchar_t *
0x1801598aa  call    ?CompareScopes@@YAHPEB_WJ0@Z; CompareScopes(wchar_t const *,long,wchar_t const *)
0x1801598af  test    eax, eax
0x1801598b1  jz      loc_18015976D
0x1801598b7  lea     rax, [rbp+2B0h+var_168]
0x1801598be  mov     [rbp+2B0h+var_178], rax
0x1801598c5  mov     [rbp+2B0h+var_170], 41h ; 'A'
0x1801598d0  xor     eax, eax
0x1801598d2  mov     [rbp+2B0h+var_168], ax
0x1801598d9  lea     rdi, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1801598e0  mov     [rbp+2B0h+var_180], rdi
0x1801598e7  or      esi, 0FFFFFFFFh
0x1801598ea  mov     r8d, esi; unsigned int
0x1801598ed  mov     rdx, r15; wchar_t *
0x1801598f0  lea     rcx, [rbp+2B0h+var_180]; this
0x1801598f7  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801598fc  mov     r9d, dword ptr [rbp+2B0h+var_2B0+4]
0x180159900  sub     r9d, [rsp+3B0h+var_390]
0x180159905  mov     r8d, [rsp+3B0h+var_390]
0x18015990a  lea     rdx, [rsp+3B0h+var_390]
0x18015990f  lea     rcx, [rbp+2B0h+var_2C0]
0x180159913  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180159918  mov     edx, [rsp+3B0h+var_390]
0x18015991c  mov     rax, [rsp+3B0h+var_388]
0x180159921  mov     rcx, [rax+8]
0x180159925  lea     rdx, [rcx+rdx*2]; wchar_t *
0x180159929  mov     r8d, [rsp+3B0h+var_390+4]; unsigned int
0x18015992e  lea     rcx, [rbp+2B0h+var_180]; this
0x180159935  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18015993a  lea     rcx, [rbp+2B0h+var_180]; this
0x180159941  call    ?ReverseFindT@CLMString@@QEBAH_W@Z; CLMString::ReverseFindT(wchar_t)
0x180159946  movsxd  rbx, eax
0x180159949  lea     rax, [rbp+2B0h+var_208]
0x180159950  mov     [rbp+2B0h+var_218], rax
0x180159957  mov     [rbp+2B0h+var_210], 41h ; 'A'
0x180159962  xor     ecx, ecx
0x180159964  mov     [rbp+2B0h+var_208], cx
0x18015996b  mov     [rbp+2B0h+var_220], rdi
0x180159972  xor     edx, edx; int
0x180159974  lea     rcx, [rbp+2B0h+var_180]; this
0x18015997b  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180159980  lea     rcx, [rax+2]
0x180159984  lea     rdx, [rcx+rbx*2]; wchar_t *
0x180159988  mov     r8d, esi; unsigned int
0x18015998b  lea     rcx, [rbp+2B0h+var_220]; this
0x180159992  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180159997  mov     r8d, esi; unsigned int
0x18015999a  lea     rdx, asc_180319BF8; " ("
0x1801599a1  lea     rcx, [rbp+2B0h+var_220]; this
0x1801599a8  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801599ad  mov     r9d, ebx
0x1801599b0  xor     r8d, r8d
0x1801599b3  lea     rdx, [rsp+3B0h+var_380]
0x1801599b8  lea     rcx, [rbp+2B0h+var_180]
0x1801599bf  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x1801599c4  mov     rcx, [rax+8]
0x1801599c8  mov     edx, [rax]
0x1801599ca  mov     rcx, [rcx+8]
0x1801599ce  lea     rdx, [rcx+rdx*2]; wchar_t *
0x1801599d2  mov     r8d, [rax+4]; unsigned int
0x1801599d6  lea     rcx, [rbp+2B0h+var_220]; this
0x1801599dd  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801599e2  mov     r8d, esi; unsigned int
0x1801599e5  lea     rdx, asc_1802EC478; ")"
0x1801599ec  lea     rcx, [rbp+2B0h+var_220]; this
0x1801599f3  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801599f8  mov     eax, dword ptr [rbp+2B0h+var_210+4]
0x1801599fe  lea     eax, ds:2[rax*2]
0x180159a05  mov     [r14], eax
0x180159a08  cmp     r12d, eax
0x180159a0b  jnb     short loc_180159A5B
0x180159a0d  lea     rcx, [rbp+2B0h+var_220]
0x180159a14  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159a19  nop
0x180159a1a  lea     rcx, [rbp+2B0h+var_180]
0x180159a21  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159a26  mov     ebx, 8007007Ah
0x180159a2b  jmp     short loc_180159A99
0x180159a2d  lea     eax, ds:2[rsi*2]
0x180159a34  mov     [r14], eax
0x180159a37  cmp     r12d, eax
0x180159a3a  jnb     short loc_180159A43
0x180159a3c  mov     ebx, 8007007Ah
0x180159a41  jmp     short loc_180159A52
0x180159a43  mov     edx, eax; unsigned __int64
0x180159a45  mov     r8, r15; wchar_t *
0x180159a48  mov     rcx, r13; wchar_t *
0x180159a4b  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180159a50  mov     ebx, eax
0x180159a52  lea     rcx, [rbp+2B0h+var_E0]
0x180159a59  jmp     short loc_180159A8D
0x180159a5b  xor     edx, edx; int
0x180159a5d  lea     rcx, [rbp+2B0h+var_220]; this
0x180159a64  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180159a69  mov     edx, [r14]; unsigned __int64
0x180159a6c  mov     r8, rax; wchar_t *
0x180159a6f  mov     rcx, r13; wchar_t *
0x180159a72  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180159a77  mov     ebx, eax
0x180159a79  lea     rcx, [rbp+2B0h+var_220]
0x180159a80  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159a85  nop
0x180159a86  lea     rcx, [rbp+2B0h+var_180]
0x180159a8d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159a92  jmp     short loc_180159A99
0x180159a94  mov     ebx, 80004005h
0x180159a99  lea     rcx, [rsp+3B0h+var_360]
0x180159a9e  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159aa3  nop
0x180159aa4  lea     rcx, [rbp+2B0h+var_2C0]
0x180159aa8  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159aad  mov     eax, ebx
0x180159aaf  mov     rcx, [rbp+2B0h+var_40]
0x180159ab6  xor     rcx, rsp; StackCookie
0x180159ab9  call    __security_check_cookie
0x180159abe  mov     rbx, [rsp+3B0h+arg_0]
0x180159ac6  add     rsp, 380h
0x180159acd  pop     r15
0x180159acf  pop     r14
0x180159ad1  pop     r13
0x180159ad3  pop     r12
  ... truncated ...
```
