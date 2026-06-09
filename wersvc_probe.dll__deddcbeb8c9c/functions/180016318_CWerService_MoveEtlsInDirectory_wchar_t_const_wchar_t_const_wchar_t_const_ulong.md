# CWerService::MoveEtlsInDirectory(wchar_t const *,wchar_t const *,wchar_t const *,ulong *)

- ea: `0x180016318`
- end: `0x180016723`
- name: `?MoveEtlsInDirectory@CWerService@@AEAAJPEB_W00PEAK@Z`
- size: `1035`
- prototype: `int(CWerService *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017f88`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x180011ef8`
- `0x180012004`
- `0x180013f54`
- `0x180014200`
- `0x180016318`
- `0x18001e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001660a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001660a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016628`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001648a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001648a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800165dc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800165dc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800166f1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800166f1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001657c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001657c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001669a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001669a`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180016410`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180016410`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001651c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001651c`

## pseudocode

```c
__int64 __fastcall CWerService::MoveEtlsInDirectory(
        CWerService *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int *a5)
{
  __int64 FirstFileW; // rbx
  const wchar_t *v9; // rdx
  CWerService *v10; // rcx
  const wchar_t *v11; // rdx
  CWerService *v12; // rcx
  signed int i; // edi
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // rax
  signed int NamedSecurityInfoW; // eax
  DWORD v16; // eax
  char v17; // al
  int v18; // edx
  int v19; // r8d
  signed int v20; // eax
  signed int LastError; // eax
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR pObjectName[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  PACL pSacl; // [rsp+68h] [rbp-98h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v30[8]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v32[8]; // [rsp+B0h] [rbp-50h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  pObjectName[0] = v25;
  v25[0] = 0;
  pObjectName[1] = v25;
  v30[0] = 0;
  lpNewFileName[0] = v30;
  lpNewFileName[1] = v30;
  lpFileName[0] = v32;
  lpFileName[1] = v32;
  v32[0] = 0;
  v23 = 0;
  hMem = 0;
  pDacl = 0;
  pSacl = 0;
  i = CWerService::AdjustTokenPrivilege(v10, v9, 1, &v23);
  if ( i >= 0 )
  {
    ppSecurityDescriptor = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
    NamedSecurityInfoW = GetNamedSecurityInfoW(a3, SE_FILE_OBJECT, 0xCu, 0, 0, &pDacl, &pSacl, ppSecurityDescriptor);
    i = NamedSecurityInfoW;
    if ( NamedSecurityInfoW )
    {
      if ( NamedSecurityInfoW > 0 )
        i = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      v12 = (CWerService *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
          (unsigned int)i);
    }
    else
    {
      i = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName, L"%s\\*etl", a2);
      if ( i >= 0 )
      {
        FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
        if ( FirstFileW == -1 )
        {
          LastError = GetLastError();
          i = LastError;
          if ( LastError > 0 )
            i = (unsigned __int16)LastError | 0x80070000;
          if ( i >= 0 )
            i = -2147467259;
        }
        else
        {
          for ( i = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      pObjectName,
                      L"%s\\%s",
                      a2,
                      FindFileData.cFileName);
                i >= 0;
                i = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      pObjectName,
                      L"%s\\%s",
                      a2,
                      FindFileData.cFileName) )
          {
            i = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  lpNewFileName,
                  L"%s\\%s%s",
                  a3,
                  a4,
                  FindFileData.cFileName);
            if ( i < 0 )
              break;
            v16 = SetNamedSecurityInfoW(pObjectName[0], SE_FILE_OBJECT, 0xCu, 0, 0, pDacl, pSacl);
            if ( v16 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  120,
                  (unsigned int)&WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
                  pObjectName[0],
                  v16);
            }
            else if ( MoveFileExW(pObjectName[0], lpNewFileName[0], 0) )
            {
              ++*a5;
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v17 = GetLastError();
              WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, pObjectName[0], (__int64)lpNewFileName[0], v17);
            }
            if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
            {
              v20 = GetLastError();
              i = v20;
              if ( v20 > 0 )
                i = (unsigned __int16)v20 | 0x80070000;
              if ( i == -2147024878 )
                i = 0;
              break;
            }
          }
        }
      }
    }
  }
  if ( v23 )
    CWerService::AdjustTokenPrivilege(v12, v11, 0, &v23);
  if ( i < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      (unsigned int)i);
  if ( hMem )
    LocalFree(hMem);
  if ( lpFileName[0] != v32 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpNewFileName[0] != v30 )
    operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( pObjectName[0] != v25 )
    operator delete(pObjectName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180016318  mov     [rsp-8+arg_0], rbx
0x18001631d  push    rbp
0x18001631e  push    rsi
0x18001631f  push    rdi
0x180016320  push    r12
0x180016322  push    r13
0x180016324  push    r14
0x180016326  push    r15
0x180016328  lea     rbp, [rsp-220h]
0x180016330  sub     rsp, 320h
0x180016337  mov     rax, cs:__security_cookie
0x18001633e  xor     rax, rsp
0x180016341  mov     [rbp+250h+var_40], rax
0x180016348  mov     r15, [rbp+250h+arg_20]
0x18001634f  lea     rcx, [rbp+250h+FindFileData]; void *
0x180016353  mov     r12, r8
0x180016356  mov     r14, rdx
0x180016359  xor     edx, edx; Val
0x18001635b  mov     r8d, 250h; Size
0x180016361  mov     r13, r9
0x180016364  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016368  call    memset_0
0x18001636d  xor     esi, esi
0x18001636f  lea     rax, [rsp+350h+var_2F8]
0x180016374  mov     [rsp+350h+pObjectName], rax
0x180016379  lea     r9, [rsp+350h+var_310]; int *
0x18001637e  lea     rax, [rsp+350h+var_2F8]
0x180016383  mov     [rsp+350h+var_2F8], si
0x180016388  mov     [rsp+350h+var_300], rax
0x18001638d  lea     r8d, [rbx+2]; int
0x180016391  lea     rax, [rbp+250h+var_2C0]
0x180016395  mov     [rbp+250h+var_2C0], si
0x180016399  mov     [rbp+250h+lpNewFileName], rax
0x18001639d  lea     rax, [rbp+250h+var_2C0]
0x1800163a1  mov     [rbp+250h+var_2C8], rax
0x1800163a5  lea     rax, [rbp+250h+var_2A0]
0x1800163a9  mov     [rbp+250h+lpFileName], rax
0x1800163ad  lea     rax, [rbp+250h+var_2A0]
0x1800163b1  mov     [rbp+250h+var_2A8], rax
0x1800163b5  mov     [rbp+250h+var_2A0], si
0x1800163b9  mov     [rsp+350h+var_310], esi
0x1800163bd  mov     [rsp+350h+hMem], rsi
0x1800163c2  mov     [rsp+350h+pDacl], rsi
0x1800163c7  mov     [rsp+350h+pSacl], rsi
0x1800163cc  call    ?AdjustTokenPrivilege@CWerService@@AEAAJPEB_WHPEAH@Z; CWerService::AdjustTokenPrivilege(wchar_t const *,int,int *)
0x1800163d1  mov     edi, eax
0x1800163d3  test    eax, eax
0x1800163d5  js      loc_180016647
0x1800163db  lea     rcx, [rsp+350h+hMem]
0x1800163e0  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1800163e5  mov     [rsp+350h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800163ea  lea     edx, [rbx+2]; ObjectType
0x1800163ed  lea     rax, [rsp+350h+pSacl]
0x1800163f2  xor     r9d, r9d; ppsidOwner
0x1800163f5  mov     [rsp+350h+ppSacl], rax; ppSacl
0x1800163fa  lea     r8d, [rbx+0Dh]; SecurityInfo
0x1800163fe  lea     rax, [rsp+350h+pDacl]
0x180016403  mov     rcx, r12; pObjectName
0x180016406  mov     [rsp+350h+ppDacl], rax; ppDacl
0x18001640b  mov     [rsp+350h+ppsidGroup], rsi; ppsidGroup
0x180016410  call    cs:__imp_GetNamedSecurityInfoW
0x180016416  mov     edi, eax
0x180016418  test    eax, eax
0x18001641a  jz      short loc_180016465
0x18001641c  jle     short loc_180016427
0x18001641e  movzx   edi, ax
0x180016421  or      edi, 80070000h
0x180016427  mov     rcx, cs:WPP_GLOBAL_Control
0x18001642e  lea     rsi, WPP_GLOBAL_Control
0x180016435  cmp     rcx, rsi
0x180016438  jz      loc_18001664E
0x18001643e  test    byte ptr [rcx+1Ch], 1
0x180016442  jz      loc_18001664E
0x180016448  mov     rcx, [rcx+10h]
0x18001644c  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180016453  mov     edx, 77h ; 'w'
0x180016458  mov     r9d, edi
0x18001645b  call    WPP_SF_d
0x180016460  jmp     loc_18001664E
0x180016465  mov     r8, r14
0x180016468  lea     rdx, aSEtl_0; "%s\\*etl"
0x18001646f  lea     rcx, [rbp+250h+lpFileName]
0x180016473  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180016478  mov     edi, eax
0x18001647a  test    eax, eax
0x18001647c  js      loc_180016647
0x180016482  mov     rcx, [rbp+250h+lpFileName]; lpFileName
0x180016486  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18001648a  call    cs:__imp_FindFirstFileW
0x180016490  mov     rbx, rax
0x180016493  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016497  jz      loc_180016628
0x18001649d  lea     r9, [rbp+250h+FindFileData.cFileName]
0x1800164a1  mov     r8, r14
0x1800164a4  lea     rdx, aSS; "%s\\%s"
0x1800164ab  lea     rcx, [rsp+350h+pObjectName]
0x1800164b0  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800164b5  mov     edi, eax
0x1800164b7  test    eax, eax
0x1800164b9  js      loc_180016647
0x1800164bf  mov     esi, 80070000h
0x1800164c4  lea     rax, [rbp+250h+FindFileData.cFileName]
0x1800164c8  mov     r9, r13
0x1800164cb  mov     r8, r12
0x1800164ce  mov     [rsp+350h+ppsidGroup], rax
0x1800164d3  lea     rdx, aSSS_0; "%s\\%s%s"
0x1800164da  lea     rcx, [rbp+250h+lpNewFileName]
0x1800164de  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800164e3  mov     edi, eax
0x1800164e5  test    eax, eax
0x1800164e7  js      loc_180016647
0x1800164ed  mov     rcx, [rsp+350h+pDacl]
0x1800164f2  xor     r9d, r9d; psidOwner
0x1800164f5  mov     rax, [rsp+350h+pSacl]
0x1800164fa  mov     [rsp+350h+ppSacl], rax; pSacl
0x1800164ff  mov     [rsp+350h+ppDacl], rcx; pDacl
0x180016504  mov     rcx, [rsp+350h+pObjectName]; pObjectName
0x180016509  lea     edi, [r9+1]
0x18001650d  mov     edx, edi; ObjectType
0x18001650f  mov     [rsp+350h+ppsidGroup], 0; psidGroup
0x180016518  lea     r8d, [r9+0Ch]; SecurityInfo
0x18001651c  call    cs:__imp_SetNamedSecurityInfoW
0x180016522  test    eax, eax
0x180016524  jz      short loc_180016570
0x180016526  mov     rcx, cs:WPP_GLOBAL_Control
0x18001652d  lea     rdx, WPP_GLOBAL_Control
0x180016534  cmp     rcx, rdx
0x180016537  jz      loc_1800165D5
0x18001653d  test    [rcx+1Ch], dil
0x180016541  jz      loc_1800165D5
0x180016547  test    eax, eax
0x180016549  jle     short loc_180016550
0x18001654b  movzx   eax, ax
0x18001654e  or      eax, esi
0x180016550  mov     r9, [rsp+350h+pObjectName]
0x180016555  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001655c  mov     rcx, [rcx+10h]
0x180016560  mov     edx, 78h ; 'x'
0x180016565  mov     dword ptr [rsp+350h+ppsidGroup], eax
0x180016569  call    WPP_SF_Sd
0x18001656e  jmp     short loc_1800165D5
0x180016570  mov     rdx, [rbp+250h+lpNewFileName]; lpNewFileName
0x180016574  xor     r8d, r8d; dwFlags
0x180016577  mov     rcx, [rsp+350h+pObjectName]; lpExistingFileName
0x18001657c  call    cs:__imp_MoveFileExW
0x180016582  test    eax, eax
0x180016584  jz      short loc_18001658B
0x180016586  add     [r15], edi
0x180016589  jmp     short loc_1800165D5
0x18001658b  mov     rax, cs:WPP_GLOBAL_Control
0x180016592  lea     rcx, WPP_GLOBAL_Control
0x180016599  cmp     rax, rcx
0x18001659c  jz      short loc_1800165D5
0x18001659e  test    [rax+1Ch], dil
0x1800165a2  jz      short loc_1800165D5
0x1800165a4  call    cs:__imp_GetLastError
0x1800165aa  test    eax, eax
0x1800165ac  jle     short loc_1800165B3
0x1800165ae  movzx   eax, ax
0x1800165b1  or      eax, esi
0x1800165b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165ba  mov     r9, [rsp+350h+pObjectName]
0x1800165bf  mov     dword ptr [rsp+350h+ppDacl], eax
0x1800165c3  mov     rax, [rbp+250h+lpNewFileName]
0x1800165c7  mov     rcx, [rcx+10h]
0x1800165cb  mov     [rsp+350h+ppsidGroup], rax
0x1800165d0  call    WPP_SF_SSd
0x1800165d5  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1800165d9  mov     rcx, rbx; hFindFile
0x1800165dc  call    cs:__imp_FindNextFileW
0x1800165e2  test    eax, eax
0x1800165e4  jz      short loc_18001660A
0x1800165e6  lea     r9, [rbp+250h+FindFileData.cFileName]
0x1800165ea  mov     r8, r14
0x1800165ed  lea     rdx, aSS; "%s\\%s"
0x1800165f4  lea     rcx, [rsp+350h+pObjectName]
0x1800165f9  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800165fe  mov     edi, eax
0x180016600  test    eax, eax
0x180016602  jns     loc_1800164C4
0x180016608  jmp     short loc_180016647
0x18001660a  call    cs:__imp_GetLastError
0x180016610  mov     edi, eax
0x180016612  test    eax, eax
0x180016614  jle     short loc_18001661B
0x180016616  movzx   edi, ax
0x180016619  or      edi, esi
0x18001661b  xor     eax, eax
0x18001661d  cmp     edi, 80070012h
0x180016623  cmovz   edi, eax
0x180016626  jmp     short loc_180016647
0x180016628  call    cs:__imp_GetLastError
0x18001662e  mov     edi, eax
0x180016630  test    eax, eax
0x180016632  jle     short loc_18001663D
0x180016634  movzx   edi, ax
0x180016637  or      edi, 80070000h
0x18001663d  test    edi, edi
0x18001663f  mov     eax, 80004005h
0x180016644  cmovns  edi, eax
0x180016647  lea     rsi, WPP_GLOBAL_Control
0x18001664e  cmp     [rsp+350h+var_310], 0
0x180016653  jz      short loc_180016662
0x180016655  lea     r9, [rsp+350h+var_310]; int *
0x18001665a  xor     r8d, r8d; int
0x18001665d  call    ?AdjustTokenPrivilege@CWerService@@AEAAJPEB_WHPEAH@Z; CWerService::AdjustTokenPrivilege(wchar_t const *,int,int *)
0x180016662  test    edi, edi
0x180016664  jns     short loc_180016690
0x180016666  mov     rcx, cs:WPP_GLOBAL_Control
0x18001666d  cmp     rcx, rsi
0x180016670  jz      short loc_180016690
0x180016672  test    byte ptr [rcx+1Ch], 1
0x180016676  jz      short loc_180016690
0x180016678  mov     rcx, [rcx+10h]
0x18001667c  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180016683  mov     edx, 7Ah ; 'z'
0x180016688  mov     r9d, edi
0x18001668b  call    WPP_SF_d
0x180016690  mov     rcx, [rsp+350h+hMem]; hMem
0x180016695  test    rcx, rcx
0x180016698  jz      short loc_1800166A0
0x18001669a  call    cs:__imp_LocalFree
0x1800166a0  mov     rcx, [rbp+250h+lpFileName]; void *
0x1800166a4  lea     rax, [rbp+250h+var_2A0]
0x1800166a8  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800166af  cmp     rcx, rax
0x1800166b2  jz      short loc_1800166BC
0x1800166b4  mov     rdx, rsi; struct std::nothrow_t *
0x1800166b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800166bc  mov     rcx, [rbp+250h+lpNewFileName]; void *
0x1800166c0  lea     rax, [rbp+250h+var_2C0]
0x1800166c4  cmp     rcx, rax
0x1800166c7  jz      short loc_1800166D1
0x1800166c9  mov     rdx, rsi; struct std::nothrow_t *
0x1800166cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800166d1  mov     rcx, [rsp+350h+pObjectName]; void *
0x1800166d6  lea     rax, [rsp+350h+var_2F8]
0x1800166db  cmp     rcx, rax
0x1800166de  jz      short loc_1800166E8
0x1800166e0  mov     rdx, rsi; struct std::nothrow_t *
0x1800166e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800166e8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800166ec  jz      short loc_1800166F7
0x1800166ee  mov     rcx, rbx; hFindFile
0x1800166f1  call    cs:__imp_FindClose
0x1800166f7  mov     eax, edi
0x1800166f9  mov     rcx, [rbp+250h+var_40]
0x180016700  xor     rcx, rsp; StackCookie
0x180016703  call    __security_check_cookie
0x180016708  mov     rbx, [rsp+350h+arg_0]
0x180016710  add     rsp, 320h
0x180016717  pop     r15
0x180016719  pop     r14
0x18001671b  pop     r13
0x18001671d  pop     r12
0x18001671f  pop     rdi
0x180016720  pop     rsi
0x180016721  pop     rbp
0x180016722  retn
```
