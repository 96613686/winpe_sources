# CryptCATAdminAddCatalog

- ea: `0x180001510`
- end: `0x180001802`
- name: `CryptCATAdminAddCatalog`
- size: `754`
- prototype: `HCATINFO __stdcall(HCATADMIN hCatAdmin, PWSTR pwszCatalogFile, PWSTR pwszSelectBaseName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001510`
- `0x180001808`
- `0x1800018dc`
- `0x180001a70`
- `0x180002ce0`
- `0x180005d00`
- `0x180007700`
- `0x1800077b0`
- `0x1800263f0`
- `0x18003a890`

## import_xrefs

- `msvcrt!wcschr` at `0x1800015ea`
- `msvcrt!wcschr` at `0x1800015ff`
- `msvcrt!wcschr` at `0x1800015ea`
- `msvcrt!wcschr` at `0x1800015ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800015b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000173e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000177f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800015b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000173e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000177f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800017ae`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180001619`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180001684`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180001619`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180001684`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000156b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800017c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000156b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800017c3`

## pseudocode

```c
HCATINFO __stdcall CryptCATAdminAddCatalog(
        HCATADMIN hCatAdmin,
        PWSTR pwszCatalogFile,
        PWSTR pwszSelectBaseName,
        DWORD dwFlags)
{
  PWSTR v5; // rbp
  WCHAR *v6; // rdi
  int v8; // r14d
  void *v9; // rsi
  unsigned __int16 *v10; // rbx
  __int64 v11; // rbp
  int TickCount64; // r13d
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // r14d
  WCHAR *v17; // rax
  unsigned __int16 *v18; // rcx
  unsigned int v19; // r8d
  DWORD CurrentDirectoryW; // eax
  DWORD v21; // eax
  unsigned __int16 *v22; // rcx
  unsigned int v23; // r8d
  void *v24; // rdi
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  int v27; // eax
  int v29; // [rsp+20h] [rbp-58h]
  int v30; // [rsp+28h] [rbp-50h]
  void *Src; // [rsp+38h] [rbp-40h] BYREF
  WCHAR Buffer; // [rsp+80h] [rbp+8h] BYREF
  PWSTR v33; // [rsp+90h] [rbp+18h]

  v33 = pwszSelectBaseName;
  Src = 0;
  v5 = pwszSelectBaseName;
  v6 = pwszCatalogFile;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !hCatAdmin || *(_DWORD *)hCatAdmin != 184 || !pwszCatalogFile || dwFlags > 1 )
  {
    TickCount64 = 0;
    SetLastError(0x57u);
    v23 = 613;
    goto LABEL_34;
  }
  v11 = -1;
  TickCount64 = GetTickCount64();
  if ( !IsCatalogFile((HANDLE)0xFFFFFFFFFFFFFFFFLL, v6) )
  {
    if ( GetLastError() == 2 )
    {
      v14 = 625;
    }
    else
    {
      SetLastError(0xBu);
      v14 = 629;
    }
    goto LABEL_8;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)hCatAdmin + 64));
  v8 = 1;
  _CatAdminFreeCachedCatalogs((struct CRYPT_CAT_ADMIN_ *)hCatAdmin, 0);
  if ( !wcschr(v6, 0x5Cu) && !wcschr(v6, 0x3Au) )
  {
    v13 = (unsigned __int16 *)(2 * GetCurrentDirectoryW(1u, &Buffer));
    if ( !(_DWORD)v13 )
    {
      v14 = 650;
LABEL_8:
      ErrLog_LogError(v13, 2u, v14, 0, v29, v30);
LABEL_9:
      v5 = v33;
      goto LABEL_35;
    }
    v15 = -1;
    do
      ++v15;
    while ( v6[v15] );
    v16 = (_DWORD)v13 + 2 * (v15 + 1);
    v17 = (WCHAR *)CatalogNew(v16);
    v10 = v17;
    if ( !v17 )
    {
      SetLastError(8u);
      v19 = 657;
LABEL_19:
      ErrLog_LogError(v18, 2u, v19, 0, v29, v30);
      v8 = 1;
      goto LABEL_9;
    }
    CurrentDirectoryW = GetCurrentDirectoryW(v16 >> 1, v17);
    v18 = 0;
    if ( !CurrentDirectoryW )
    {
      v19 = 664;
      goto LABEL_19;
    }
    do
      ++v11;
    while ( v10[v11] );
    if ( v10[v11 - 1] != 92 )
      StringCbCatW(v10, v16, L"\\");
    StringCbCatW(v10, v16, v6);
    v8 = 1;
    LODWORD(v6) = (_DWORD)v10;
  }
  v5 = v33;
  v21 = Client_SSCatDBAddCatalog(dwFlags, (int)hCatAdmin + 104, (_DWORD)v6, (_DWORD)v33, (__int64)&Src);
  if ( v21 )
  {
    SetLastError(v21);
    v23 = 688;
LABEL_34:
    ErrLog_LogError(v22, 2u, v23, 0, v29, v30);
    goto LABEL_35;
  }
  v24 = (void *)CatalogDupeString(Src);
  if ( !v24 )
  {
    v23 = 698;
    goto LABEL_34;
  }
  v25 = CatalogNew(0x18u);
  v9 = (void *)v25;
  if ( v25 )
  {
    *(_QWORD *)(v25 + 4) = 0;
    *(_DWORD *)(v25 + 12) = 0;
    *(_DWORD *)v25 = 1;
    *(_QWORD *)(v25 + 16) = v24;
  }
  else
  {
    SetLastError(8u);
    ErrLog_LogError(v26, 2u, 0x2C1u, 0, v29, v30);
    LocalFree(v24);
    v8 = 1;
  }
LABEL_35:
  if ( Src )
    MIDL_user_free(Src);
  if ( v10 )
    LocalFree(v10);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)hCatAdmin + 64));
  v27 = GetTickCount64();
  ErrLog_LogPrintfW(0, 1, L"DONE Adding Catalog File (%ums): %s", (unsigned int)(v27 - TickCount64), v5);
  return v9;
}

```

## disassembly

```asm
0x180001510  mov     [rsp+arg_8], rbx
0x180001515  mov     [rsp+arg_10], r8
0x18000151a  push    rbp
0x18000151b  push    rsi
0x18000151c  push    rdi
0x18000151d  push    r12
0x18000151f  push    r13
0x180001521  push    r14
0x180001523  push    r15
0x180001525  sub     rsp, 40h
0x180001529  xor     eax, eax
0x18000152b  mov     r12d, r9d
0x18000152e  mov     [rsp+78h+Src], rax
0x180001533  mov     rbp, r8
0x180001536  mov     rdi, rdx
0x180001539  mov     r15, rcx
0x18000153c  mov     r14d, eax
0x18000153f  mov     esi, eax
0x180001541  mov     ebx, eax
0x180001543  test    rcx, rcx
0x180001546  jz      loc_180001777
0x18000154c  cmp     dword ptr [rcx], 0B8h
0x180001552  jnz     loc_180001777
0x180001558  test    rdx, rdx
0x18000155b  jz      loc_180001777
0x180001561  cmp     r9d, 1
0x180001565  ja      loc_180001777
0x18000156b  call    cs:__imp_GetTickCount64
0x180001571  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180001575  mov     rdx, rdi; pwszFileName
0x180001578  mov     rcx, rbp; hFile
0x18000157b  mov     r13, rax
0x18000157e  call    IsCatalogFile
0x180001583  test    eax, eax
0x180001585  jnz     short loc_1800015C4
0x180001587  call    cs:__imp_GetLastError
0x18000158d  cmp     eax, 2
0x180001590  jnz     short loc_1800015B1
0x180001592  mov     r8d, 271h; unsigned int
0x180001598  xor     r9d, r9d; unsigned int
0x18000159b  lea     edx, [r9+2]; unsigned int
0x18000159f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800015a4  mov     rbp, [rsp+78h+arg_10]
0x1800015ac  jmp     loc_180001797
0x1800015b1  mov     ecx, 0Bh; dwErrCode
0x1800015b6  call    cs:__imp_SetLastError
0x1800015bc  mov     r8d, 275h
0x1800015c2  jmp     short loc_180001598
0x1800015c4  lea     rcx, [r15+40h]; lpCriticalSection
0x1800015c8  call    cs:__imp_EnterCriticalSection
0x1800015ce  mov     r14d, 1
0x1800015d4  xor     edx, edx; int
0x1800015d6  mov     rcx, r15; struct CRYPT_CAT_ADMIN_ *
0x1800015d9  mov     [rsp+78h+var_48], r14d
0x1800015de  call    ?_CatAdminFreeCachedCatalogs@@YAHPEAUCRYPT_CAT_ADMIN_@@H@Z; _CatAdminFreeCachedCatalogs(CRYPT_CAT_ADMIN_ *,int)
0x1800015e3  lea     edx, [r14+5Bh]; Ch
0x1800015e7  mov     rcx, rdi; Str
0x1800015ea  call    cs:__imp_wcschr
0x1800015f0  test    rax, rax
0x1800015f3  jnz     loc_1800016D5
0x1800015f9  lea     edx, [rax+3Ah]; Ch
0x1800015fc  mov     rcx, rdi; Str
0x1800015ff  call    cs:__imp_wcschr
0x180001605  test    rax, rax
0x180001608  jnz     loc_1800016D5
0x18000160e  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180001616  mov     ecx, r14d; nBufferLength
0x180001619  call    cs:__imp_GetCurrentDirectoryW
0x18000161f  xor     edx, edx
0x180001621  lea     ecx, [rax+rax]
0x180001624  test    ecx, ecx
0x180001626  jnz     short loc_180001633
0x180001628  mov     r8d, 28Ah
0x18000162e  jmp     loc_180001598
0x180001633  mov     rax, rbp
0x180001636  inc     rax
0x180001639  cmp     [rdi+rax*2], dx
0x18000163d  jnz     short loc_180001636
0x18000163f  lea     eax, [rax+1]
0x180001642  lea     r14d, [rcx+rax*2]
0x180001646  mov     ecx, r14d; uBytes
0x180001649  call    CatalogNew
0x18000164e  mov     rbx, rax
0x180001651  test    rax, rax
0x180001654  jnz     short loc_18000167C
0x180001656  lea     ecx, [rax+8]; dwErrCode
0x180001659  call    cs:__imp_SetLastError
0x18000165f  mov     r8d, 291h; unsigned int
0x180001665  mov     edx, 2; unsigned int
0x18000166a  xor     r9d, r9d; unsigned int
0x18000166d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001672  mov     r14d, [rsp+78h+var_48]
0x180001677  jmp     loc_1800015A4
0x18000167c  mov     ecx, r14d
0x18000167f  mov     rdx, rbx; lpBuffer
0x180001682  shr     ecx, 1; nBufferLength
0x180001684  call    cs:__imp_GetCurrentDirectoryW
0x18000168a  xor     ecx, ecx
0x18000168c  test    eax, eax
0x18000168e  jnz     short loc_180001698
0x180001690  mov     r8d, 298h
0x180001696  jmp     short loc_180001665
0x180001698  inc     rbp
0x18000169b  cmp     [rbx+rbp*2], cx
0x18000169f  jnz     short loc_180001698
0x1800016a1  mov     eax, 5Ch ; '\'
0x1800016a6  cmp     [rbx+rbp*2-2], ax
0x1800016ab  jz      short loc_1800016BF
0x1800016ad  mov     edx, r14d; unsigned __int64
0x1800016b0  lea     r8, asc_1800557E4; "\\"
0x1800016b7  mov     rcx, rbx; unsigned __int16 *
0x1800016ba  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800016bf  mov     edx, r14d; unsigned __int64
0x1800016c2  mov     r8, rdi; unsigned __int16 *
0x1800016c5  mov     rcx, rbx; unsigned __int16 *
0x1800016c8  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800016cd  mov     r14d, [rsp+78h+var_48]
0x1800016d2  mov     rdi, rbx
0x1800016d5  mov     rbp, [rsp+78h+arg_10]
0x1800016dd  lea     rax, [rsp+78h+Src]
0x1800016e2  mov     r9, rbp
0x1800016e5  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800016ea  lea     rdx, [r15+68h]
0x1800016ee  mov     r8, rdi
0x1800016f1  mov     ecx, r12d
0x1800016f4  call    Client_SSCatDBAddCatalog
0x1800016f9  test    eax, eax
0x1800016fb  jz      short loc_18000170D
0x1800016fd  mov     ecx, eax; dwErrCode
0x1800016ff  call    cs:__imp_SetLastError
0x180001705  mov     r8d, 2B0h
0x18000170b  jmp     short loc_18000178B
0x18000170d  mov     rcx, [rsp+78h+Src]; Src
0x180001712  call    CatalogDupeString
0x180001717  mov     rdi, rax
0x18000171a  test    rax, rax
0x18000171d  jnz     short loc_180001727
0x18000171f  mov     r8d, 2BAh
0x180001725  jmp     short loc_18000178B
0x180001727  mov     ecx, 18h; uBytes
0x18000172c  call    CatalogNew
0x180001731  xor     ecx, ecx
0x180001733  mov     rsi, rax
0x180001736  test    rax, rax
0x180001739  jnz     short loc_180001764
0x18000173b  lea     ecx, [rax+8]; dwErrCode
0x18000173e  call    cs:__imp_SetLastError
0x180001744  xor     r9d, r9d; unsigned int
0x180001747  lea     edx, [rsi+2]; unsigned int
0x18000174a  mov     r8d, 2C1h; unsigned int
0x180001750  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001755  mov     rcx, rdi; hMem
0x180001758  call    cs:__imp_LocalFree
0x18000175e  lea     r14d, [rsi+1]
0x180001762  jmp     short loc_180001797
0x180001764  mov     [rax+4], rcx
0x180001768  mov     [rax+0Ch], ecx
0x18000176b  mov     dword ptr [rax], 1
0x180001771  mov     [rax+10h], rdi
0x180001775  jmp     short loc_180001797
0x180001777  mov     ecx, 57h ; 'W'; dwErrCode
0x18000177c  mov     r13, rax
0x18000177f  call    cs:__imp_SetLastError
0x180001785  mov     r8d, 265h; unsigned int
0x18000178b  xor     r9d, r9d; unsigned int
0x18000178e  lea     edx, [r9+2]; unsigned int
0x180001792  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001797  mov     rcx, [rsp+78h+Src]; void *
0x18000179c  test    rcx, rcx
0x18000179f  jz      short loc_1800017A6
0x1800017a1  call    MIDL_user_free
0x1800017a6  test    rbx, rbx
0x1800017a9  jz      short loc_1800017B4
0x1800017ab  mov     rcx, rbx; hMem
0x1800017ae  call    cs:__imp_LocalFree
0x1800017b4  test    r14d, r14d
0x1800017b7  jz      short loc_1800017C3
0x1800017b9  lea     rcx, [r15+40h]; lpCriticalSection
0x1800017bd  call    cs:__imp_LeaveCriticalSection
0x1800017c3  call    cs:__imp_GetTickCount64
0x1800017c9  lea     r8, aDoneAddingCata; "DONE Adding Catalog File (%ums): %s"
0x1800017d0  mov     qword ptr [rsp+78h+var_58], rbp
0x1800017d5  sub     eax, r13d
0x1800017d8  mov     edx, 1; int
0x1800017dd  mov     r9d, eax
0x1800017e0  xor     ecx, ecx; lpSrc
0x1800017e2  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x1800017e7  mov     rbx, [rsp+78h+arg_8]
0x1800017ef  mov     rax, rsi
0x1800017f2  add     rsp, 40h
0x1800017f6  pop     r15
0x1800017f8  pop     r14
0x1800017fa  pop     r13
0x1800017fc  pop     r12
0x1800017fe  pop     rdi
0x1800017ff  pop     rsi
0x180001800  pop     rbp
0x180001801  retn
```
