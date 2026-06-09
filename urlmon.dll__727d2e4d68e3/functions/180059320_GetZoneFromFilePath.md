# _GetZoneFromFilePath

- ea: `0x180059320`
- end: `0x180059738`
- name: `_GetZoneFromFilePath`
- size: `1048`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800a07e0`
- `0x18010a120`

## callees

- `0x18001db50`
- `0x180033980`
- `0x180058fe4`
- `0x180059150`
- `0x1800592a8`
- `0x180059320`
- `0x180059a0c`
- `0x180059cc0`
- `0x18007fec4`
- `0x180091ce8`
- `0x180127d28`
- `0x180127e28`
- `0x180128660`

## import_xrefs

- `iertutil!__imp_?IEIsLowIntegrityFile@@YAJPEBG@Z` at `0x180059534`
- `iertutil!__imp_?IEIsLowIntegrityFile@@YAJPEBG@Z` at `0x180059534`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800594c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800594c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059469`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059469`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18005938a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059510`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18005938a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059510`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1800595bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1800595bd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800593c1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800593c1`

## pseudocode

```c
__int64 __fastcall GetZoneFromFilePath(_DWORD *a1, _BYTE *a2, const WCHAR *a3)
{
  CMapPathToSpecialDirHelper *v3; // rdi
  int v4; // ebx
  int v6; // r14d
  _BYTE *v7; // rsi
  unsigned int v8; // r8d
  DWORD FullPathNameW; // r15d
  int LocalDirType; // esi
  CMapPathToSpecialDirHelper *v12; // rax
  CMapPathToSpecialDirHelper *v13; // rdi
  unsigned int v14; // edx
  BOOL IsUNCW; // eax
  int v16; // r12d
  struct CMapPathToSpecialDirHelper::CMappedPathEntry *v17; // rax
  struct CMapPathToSpecialDirHelper::CMappedPathEntry *v18; // r15
  unsigned int v19; // ecx
  PWSTR v20; // rax
  unsigned int v21; // edx
  bool v22; // r15
  unsigned int v23; // r8d
  wchar_t *v24; // rdx
  bool v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+44h] [rbp-BCh] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-A8h]
  _BYTE *v31; // [rsp+60h] [rbp-A0h]
  _BYTE *v32; // [rsp+68h] [rbp-98h]
  wchar_t pszDest[260]; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+278h] [rbp+178h]
  __int64 v35; // [rsp+27Ch] [rbp+17Ch]
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszSrch[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR pszPath[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v3 = g_pMapPathToSpecialDirHelper;
  v4 = 0;
  v32 = a2;
  v30 = a1;
  if ( g_pMapPathToSpecialDirHelper )
  {
LABEL_2:
    v6 = 0;
    v26 = 0;
    if ( (int)CMapPathToSpecialDirHelper::Init(v3) >= 0 )
    {
      v7 = (char *)v3 + 25;
      v31 = (char *)v3 + 25;
      if ( PathIsUNCW(a3) != *((_BYTE *)v3 + 25) )
        goto LABEL_18;
      FullPathNameW = GetFullPathNameW(a3, 0x104u, Buffer, 0);
      if ( FullPathNameW - 1 > 0x102 )
        goto LABEL_6;
      v28 = 260;
      v27 = 0;
      LocalDirType = CMapPathToSpecialDirHelper::GetLocalDirType(
                       v3,
                       Buffer,
                       v8,
                       (enum CMapPathToSpecialDirHelper::DirectoryType *)&v26,
                       pszSrch,
                       &v28,
                       (enum CMapPathToSpecialDirHelper::StatusGetLocalDirType *)&v27);
      if ( LocalDirType < 0 )
        goto LABEL_6;
      v16 = v27;
      v6 = v26;
      if ( v27 == 1 )
      {
LABEL_17:
        v7 = v31;
LABEL_18:
        if ( v6 == 1 )
        {
          if ( (unsigned int)CMapPathToSpecialDirHelper::IsFileInSpecialDirs(v3, a3, 1) != 1 )
          {
            *v30 = 4;
            *v32 = 0;
          }
        }
        else
        {
          IsUNCW = PathIsUNCW(a3);
          if ( v6 == 2 && IsUNCW == *v7 || !IsUNCW && !IEIsLowIntegrityFile(a3) )
            *v30 = 3;
        }
        return (unsigned int)v4;
      }
      if ( v26
        || !CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u)
        || !CReparsePointsHelper::ContainsReparsePoint(Buffer, FullPathNameW) )
      {
LABEL_28:
        if ( v16 == 2 )
        {
          LocalDirType = 0;
          if ( *((_DWORD *)v3 + 5) )
          {
            v17 = (struct CMapPathToSpecialDirHelper::CMappedPathEntry *)operator new(0x10u);
            v18 = v17;
            if ( v17 )
            {
              v19 = v28;
              *(_QWORD *)v17 = 0;
              *((_DWORD *)v17 + 2) = v19;
              *((_DWORD *)v17 + 3) = v6;
              v20 = StrDupW(pszSrch);
              *(_QWORD *)v18 = v20;
              if ( v20 )
              {
                LocalDirType = 0;
                CMapPathToSpecialDirHelper::AddToCache(v3, v18);
              }
              else
              {
                CMapPathToSpecialDirHelper::CMappedPathEntry::`scalar deleting destructor'(v18, v21);
                LocalDirType = -2147024882;
              }
            }
            else
            {
              LocalDirType = -2147024882;
            }
          }
        }
        if ( LocalDirType < 0 )
          goto LABEL_6;
        goto LABEL_17;
      }
      v35 = 2;
      pszDest[0] = 0;
      v34 = 0;
      LocalDirType = CReparsePointsHelper::Init((CReparsePointsHelper *)pszDest, Buffer, FullPathNameW);
      if ( LocalDirType >= 0 )
      {
        v22 = 1;
        v25 = 1;
        while ( v22 && !v6 )
        {
          LocalDirType = CReparsePointsHelper::FindNextReparsePoint(pszDest, &v25);
          if ( LocalDirType < 0 )
            goto LABEL_6;
          v22 = v25;
          if ( !v25 )
            break;
          v27 = 0;
          v24 = pszDest;
          v29 = 260;
          if ( (_DWORD)v35 != 1 )
            v24 = 0;
          LocalDirType = CMapPathToSpecialDirHelper::GetLocalDirType(
                           v3,
                           v24,
                           v23,
                           (enum CMapPathToSpecialDirHelper::DirectoryType *)&v26,
                           pszPath,
                           &v29,
                           (enum CMapPathToSpecialDirHelper::StatusGetLocalDirType *)&v27);
          if ( LocalDirType < 0 )
            goto LABEL_6;
          if ( v16 == 3 )
            v16 = 2;
          v6 = v26;
        }
        goto LABEL_28;
      }
    }
LABEL_6:
    *v32 = 0;
    *v30 = 4;
    return (unsigned int)v4;
  }
  EnterCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
  if ( !g_pMapPathToSpecialDirHelper )
  {
    v12 = (CMapPathToSpecialDirHelper *)operator new(0x28u);
    v13 = v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = 0;
      *((_QWORD *)v12 + 1) = 0;
      *((_QWORD *)v12 + 2) = 0;
      *((_BYTE *)v12 + 24) = 0;
      *((_QWORD *)v12 + 4) = 0;
      v4 = CMapPathToSpecialDirHelper::Init(v12);
      if ( v4 < 0 )
        CMapPathToSpecialDirHelper::`scalar deleting destructor'(v13, v14);
      else
        g_pMapPathToSpecialDirHelper = v13;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  LeaveCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
  if ( v4 >= 0 )
  {
    v3 = g_pMapPathToSpecialDirHelper;
    goto LABEL_2;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180059320  mov     [rsp-8+arg_18], rbx
0x180059325  push    rbp
0x180059326  push    rsi
0x180059327  push    rdi
0x180059328  push    r12
0x18005932a  push    r13
0x18005932c  push    r14
0x18005932e  push    r15
0x180059330  lea     rbp, [rsp-7D0h]
0x180059338  sub     rsp, 8D0h
0x18005933f  mov     rax, cs:__security_cookie
0x180059346  xor     rax, rsp
0x180059349  mov     [rbp+800h+var_40], rax
0x180059350  mov     rdi, cs:?g_pMapPathToSpecialDirHelper@@3PEAVCMapPathToSpecialDirHelper@@EA; CMapPathToSpecialDirHelper * g_pMapPathToSpecialDirHelper
0x180059357  xor     ebx, ebx
0x180059359  mov     [rsp+900h+var_898], rdx
0x18005935e  mov     r13, r8
0x180059361  mov     [rsp+900h+var_8A8], rcx
0x180059366  test    rdi, rdi
0x180059369  jz      loc_180059462
0x18005936f  xor     r14d, r14d
0x180059372  mov     rcx, rdi; this
0x180059375  mov     [rsp+900h+var_8BC], r14d
0x18005937a  call    ?Init@CMapPathToSpecialDirHelper@@QEAAJXZ; CMapPathToSpecialDirHelper::Init(void)
0x18005937f  test    eax, eax
0x180059381  js      loc_180059422
0x180059387  mov     rcx, r13; pszPath
0x18005938a  call    cs:__imp_PathIsUNCW
0x180059391  nop     dword ptr [rax+rax+00h]
0x180059396  cmp     eax, 1
0x180059399  lea     rsi, [rdi+19h]
0x18005939d  mov     [rsp+900h+var_8A0], rsi
0x1800593a2  setz    al
0x1800593a5  cmp     al, [rsi]
0x1800593a7  jnz     loc_180059503
0x1800593ad  mov     esi, 104h
0x1800593b2  lea     r8, [rbp+800h+Buffer]; lpBuffer
0x1800593b9  mov     edx, esi; nBufferLength
0x1800593bb  xor     r9d, r9d; lpFilePart
0x1800593be  mov     rcx, r13; lpFileName
0x1800593c1  call    cs:__imp_GetFullPathNameW
0x1800593c8  nop     dword ptr [rax+rax+00h]
0x1800593cd  mov     r15d, eax
0x1800593d0  lea     ecx, [rax-1]
0x1800593d3  cmp     ecx, 102h
0x1800593d9  ja      short loc_180059422
0x1800593db  lea     rax, [rsp+900h+var_8B8]
0x1800593e0  mov     [rsp+900h+var_8B4], esi
0x1800593e4  mov     [rsp+900h+var_8D0], rax; enum CMapPathToSpecialDirHelper::StatusGetLocalDirType *
0x1800593e9  lea     r9, [rsp+900h+var_8BC]; enum CMapPathToSpecialDirHelper::DirectoryType *
0x1800593ee  lea     rax, [rsp+900h+var_8B4]
0x1800593f3  mov     [rsp+900h+var_8B8], r14d
0x1800593f8  mov     [rsp+900h+var_8D8], rax; unsigned int *
0x1800593fd  lea     rdx, [rbp+800h+Buffer]; unsigned __int16 *
0x180059404  lea     rax, [rbp+800h+pszSrch]
0x18005940b  mov     rcx, rdi; this
0x18005940e  mov     [rsp+900h+pszPath], rax; pszPath
0x180059413  call    ?GetLocalDirType@CMapPathToSpecialDirHelper@@AEAAJPEBGKPEAW4DirectoryType@1@PEAGPEAKPEAW4StatusGetLocalDirType@1@@Z; CMapPathToSpecialDirHelper::GetLocalDirType(ushort const *,ulong,CMapPathToSpecialDirHelper::DirectoryType *,ushort *,ulong *,CMapPathToSpecialDirHelper::StatusGetLocalDirType *)
0x180059418  mov     esi, eax
0x18005941a  test    eax, eax
0x18005941c  jns     loc_18005955E
0x180059422  mov     rax, [rsp+900h+var_898]
0x180059427  mov     byte ptr [rax], 0
0x18005942a  mov     rax, [rsp+900h+var_8A8]
0x18005942f  mov     dword ptr [rax], 4
0x180059435  mov     eax, ebx
0x180059437  mov     rcx, [rbp+800h+var_40]
0x18005943e  xor     rcx, rsp; StackCookie
0x180059441  call    __security_check_cookie
0x180059446  mov     rbx, [rsp+900h+arg_18]
0x18005944e  add     rsp, 8D0h
0x180059455  pop     r15
0x180059457  pop     r14
0x180059459  pop     r13
0x18005945b  pop     r12
0x18005945d  pop     rdi
0x18005945e  pop     rsi
0x18005945f  pop     rbp
0x180059460  retn
0x180059462  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059469  call    cs:__imp_EnterCriticalSection
0x180059470  nop     dword ptr [rax+rax+00h]
0x180059475  cmp     cs:?g_pMapPathToSpecialDirHelper@@3PEAVCMapPathToSpecialDirHelper@@EA, rbx; CMapPathToSpecialDirHelper * g_pMapPathToSpecialDirHelper
0x18005947c  jnz     short loc_1800594BB
0x18005947e  mov     ecx, 28h ; '('; Size
0x180059483  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059488  mov     rdi, rax
0x18005948b  test    rax, rax
0x18005948e  jz      short loc_1800594E2
0x180059490  mov     rcx, rax; this
0x180059493  mov     [rax], rbx
0x180059496  mov     [rax+8], rbx
0x18005949a  mov     [rax+10h], rbx
0x18005949e  mov     [rax+18h], bl
0x1800594a1  mov     [rax+20h], rbx
0x1800594a5  call    ?Init@CMapPathToSpecialDirHelper@@QEAAJXZ; CMapPathToSpecialDirHelper::Init(void)
0x1800594aa  mov     ebx, eax
0x1800594ac  test    eax, eax
0x1800594ae  js      loc_1800596F4
0x1800594b4  mov     cs:?g_pMapPathToSpecialDirHelper@@3PEAVCMapPathToSpecialDirHelper@@EA, rdi; CMapPathToSpecialDirHelper * g_pMapPathToSpecialDirHelper
0x1800594bb  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800594c2  call    cs:__imp_LeaveCriticalSection
0x1800594c9  nop     dword ptr [rax+rax+00h]
0x1800594ce  test    ebx, ebx
0x1800594d0  js      loc_180059435
0x1800594d6  mov     rdi, cs:?g_pMapPathToSpecialDirHelper@@3PEAVCMapPathToSpecialDirHelper@@EA; CMapPathToSpecialDirHelper * g_pMapPathToSpecialDirHelper
0x1800594dd  jmp     loc_18005936F
0x1800594e2  mov     ebx, 8007000Eh
0x1800594e7  jmp     short loc_1800594BB
0x1800594e9  xor     esi, esi
0x1800594eb  mov     rdx, r15; struct CMapPathToSpecialDirHelper::CMappedPathEntry *
0x1800594ee  mov     rcx, rdi; this
0x1800594f1  call    ?AddToCache@CMapPathToSpecialDirHelper@@AEAAXPEAVCMappedPathEntry@1@@Z; CMapPathToSpecialDirHelper::AddToCache(CMapPathToSpecialDirHelper::CMappedPathEntry *)
0x1800594f6  test    esi, esi
0x1800594f8  js      loc_180059422
0x1800594fe  mov     rsi, [rsp+900h+var_8A0]
0x180059503  cmp     r14d, 1
0x180059507  jz      loc_180059701
0x18005950d  mov     rcx, r13; pszPath
0x180059510  call    cs:__imp_PathIsUNCW
0x180059517  nop     dword ptr [rax+rax+00h]
0x18005951c  cmp     eax, 1
0x18005951f  setz    cl
0x180059522  cmp     r14d, 2
0x180059526  jz      short loc_180059558
0x180059528  cmp     eax, 1
0x18005952b  jz      loc_180059435
0x180059531  mov     rcx, r13
0x180059534  call    cs:__imp_?IEIsLowIntegrityFile@@YAJPEBG@Z; IEIsLowIntegrityFile(ushort const *)
0x18005953b  nop     dword ptr [rax+rax+00h]
0x180059540  test    eax, eax
0x180059542  jnz     loc_180059435
0x180059548  mov     rax, [rsp+900h+var_8A8]
0x18005954d  mov     dword ptr [rax], 3
0x180059553  jmp     loc_180059435
0x180059558  cmp     cl, [rsi]
0x18005955a  jnz     short loc_180059528
0x18005955c  jmp     short loc_180059548
0x18005955e  mov     r12d, [rsp+900h+var_8B8]
0x180059563  mov     r14d, [rsp+900h+var_8BC]
0x180059568  cmp     r12d, 1
0x18005956c  jz      short loc_1800594FE
0x18005956e  test    r14d, r14d
0x180059571  jnz     short loc_180059583
0x180059573  lea     edx, [r14+2]; dwFlags
0x180059577  lea     ecx, [rdx+6]; FeatureEntry
0x18005957a  call    CoInternetIsFeatureEnabled
0x18005957f  test    eax, eax
0x180059581  jnz     short loc_1800595FC
0x180059583  cmp     r12d, 2
0x180059587  jnz     loc_1800594F6
0x18005958d  xor     esi, esi
0x18005958f  cmp     [rdi+14h], esi
0x180059592  jz      loc_1800594F6
0x180059598  lea     ecx, [rsi+10h]; Size
0x18005959b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800595a0  mov     r15, rax
0x1800595a3  test    rax, rax
0x1800595a6  jz      short loc_1800595F2
0x1800595a8  mov     ecx, [rsp+900h+var_8B4]
0x1800595ac  mov     [rax], rsi
0x1800595af  mov     [rax+8], ecx
0x1800595b2  lea     rcx, [rbp+800h+pszSrch]; pszSrch
0x1800595b9  mov     [rax+0Ch], r14d
0x1800595bd  call    cs:__imp_StrDupW
0x1800595c4  nop     dword ptr [rax+rax+00h]
0x1800595c9  mov     [r15], rax
0x1800595cc  mov     rsi, rax
0x1800595cf  test    rax, rax
0x1800595d2  jnz     loc_1800594E9
0x1800595d8  mov     rcx, r15; this
0x1800595db  call    ??_GCMappedPathEntry@CMapPathToSpecialDirHelper@@QEAAPEAXI@Z; CMapPathToSpecialDirHelper::CMappedPathEntry::`scalar deleting destructor'(uint)
0x1800595e0  neg     rsi
0x1800595e3  sbb     esi, esi
0x1800595e5  not     esi
0x1800595e7  and     esi, 8007000Eh
0x1800595ed  jmp     loc_1800594F6
0x1800595f2  mov     esi, 8007000Eh
0x1800595f7  jmp     loc_1800594F6
0x1800595fc  mov     edx, r15d; unsigned int
0x1800595ff  lea     rcx, [rbp+800h+Buffer]; lpFileName
0x180059606  call    ?ContainsReparsePoint@CReparsePointsHelper@@SA_NPEAGK@Z; CReparsePointsHelper::ContainsReparsePoint(ushort *,ulong)
0x18005960b  test    al, al
0x18005960d  jz      loc_180059583
0x180059613  xor     eax, eax
0x180059615  mov     [rbp+800h+var_684], 2
0x180059620  mov     r8d, r15d; unsigned int
0x180059623  mov     [rsp+900h+pszDest], ax
0x180059628  lea     rdx, [rbp+800h+Buffer]; unsigned __int16 *
0x18005962f  mov     [rbp+800h+var_688], eax
0x180059635  lea     rcx, [rsp+900h+pszDest]; this
0x18005963a  call    ?Init@CReparsePointsHelper@@QEAAJPEBGK@Z; CReparsePointsHelper::Init(ushort const *,ulong)
0x18005963f  mov     esi, eax
0x180059641  test    eax, eax
0x180059643  js      loc_180059422
0x180059649  mov     r15b, 1
0x18005964c  mov     [rsp+900h+var_8C0], r15b
0x180059651  test    r15b, r15b
0x180059654  jz      loc_180059583
0x18005965a  test    r14d, r14d
0x18005965d  jnz     loc_180059583
0x180059663  lea     rdx, [rsp+900h+var_8C0]; bool *
0x180059668  lea     rcx, [rsp+900h+pszDest]; pszDest
0x18005966d  call    ?FindNextReparsePoint@CReparsePointsHelper@@QEAAJPEA_N@Z; CReparsePointsHelper::FindNextReparsePoint(bool *)
0x180059672  mov     esi, eax
0x180059674  test    eax, eax
0x180059676  js      loc_180059422
0x18005967c  mov     r15b, [rsp+900h+var_8C0]
0x180059681  test    r15b, r15b
0x180059684  jz      loc_180059583
0x18005968a  xor     eax, eax
0x18005968c  mov     [rsp+900h+var_8B8], r14d
0x180059691  cmp     dword ptr [rbp+800h+var_684], 1
0x180059698  lea     rdx, [rsp+900h+pszDest]
0x18005969d  lea     r9, [rsp+900h+var_8BC]; enum CMapPathToSpecialDirHelper::DirectoryType *
0x1800596a2  mov     [rsp+900h+var_8B0], 104h
0x1800596aa  cmovnz  rdx, rax; unsigned __int16 *
0x1800596ae  mov     rcx, rdi; this
0x1800596b1  lea     rax, [rsp+900h+var_8B8]
0x1800596b6  mov     [rsp+900h+var_8D0], rax; enum CMapPathToSpecialDirHelper::StatusGetLocalDirType *
0x1800596bb  lea     rax, [rsp+900h+var_8B0]
0x1800596c0  mov     [rsp+900h+var_8D8], rax; unsigned int *
0x1800596c5  lea     rax, [rbp+800h+var_250]
0x1800596cc  mov     [rsp+900h+pszPath], rax; pszPath
0x1800596d1  call    ?GetLocalDirType@CMapPathToSpecialDirHelper@@AEAAJPEBGKPEAW4DirectoryType@1@PEAGPEAKPEAW4StatusGetLocalDirType@1@@Z; CMapPathToSpecialDirHelper::GetLocalDirType(ushort const *,ulong,CMapPathToSpecialDirHelper::DirectoryType *,ushort *,ulong *,CMapPathToSpecialDirHelper::StatusGetLocalDirType *)
0x1800596d6  mov     esi, eax
0x1800596d8  test    eax, eax
0x1800596da  js      loc_180059422
0x1800596e0  cmp     r12d, 3
0x1800596e4  jnz     short loc_1800596EA
0x1800596e6  lea     r12d, [r14+2]
0x1800596ea  mov     r14d, [rsp+900h+var_8BC]
0x1800596ef  jmp     loc_180059651
0x1800596f4  mov     rcx, rdi; this
0x1800596f7  call    ??_GCMapPathToSpecialDirHelper@@QEAAPEAXI@Z; CMapPathToSpecialDirHelper::`scalar deleting destructor'(uint)
0x1800596fc  jmp     loc_1800594BB
0x180059701  xor     r9d, r9d
0x180059704  mov     rdx, r13
0x180059707  mov     rcx, rdi
0x18005970a  lea     r8d, [r9+1]
0x18005970e  call    ?IsFileInSpecialDirs@CMapPathToSpecialDirHelper@@QEAAJPEBGW4DirectoryType@1@H@Z; CMapPathToSpecialDirHelper::IsFileInSpecialDirs(ushort const *,CMapPathToSpecialDirHelper::DirectoryType,int)
0x180059713  test    eax, eax
0x180059715  jz      short loc_180059720
0x180059717  cmp     eax, 1
0x18005971a  jz      loc_180059435
0x180059720  mov     rax, [rsp+900h+var_8A8]
0x180059725  mov     dword ptr [rax], 4
0x18005972b  mov     rax, [rsp+900h+var_898]
0x180059730  mov     byte ptr [rax], 0
0x180059733  jmp     loc_180059435
```
