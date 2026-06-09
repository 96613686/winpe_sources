# WscServiceUtils::GetWscIniConfiguration(ushort const *,ushort * *)

- ea: `0x1800062d0`
- end: `0x180006a62`
- name: `?GetWscIniConfiguration@WscServiceUtils@@YAJPEBGPEAPEAG@Z`
- size: `1938`
- prototype: `__int64 __fastcall(WscServiceUtils *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x180005220`
- `0x1800062d0`
- `0x180006a70`
- `0x180006e9c`
- `0x180008e48`
- `0x1800186e0`
- `0x18001f97c`
- `0x180029e74`
- `0x18002ab38`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000638d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000638d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180006451`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180006451`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800064b8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000650d`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006568`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800065bd`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006616`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006670`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800066ca`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800064b8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000650d`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006568`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800065bd`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006616`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180006670`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800066ca`

## string_xrefs

- `0x180006341`: `\SecurityProductInformation.ini`
- `0x180006536`: `Company : %ls`
- `0x1800064ff`: `Company`
- `0x18000655a`: `PathToSignedReportingExe`
- `0x18000658b`: `PathToSignedReportingExe : %ls`

## pseudocode

```c
__int64 __fastcall WscServiceUtils::GetWscIniConfiguration(
        WscServiceUtils *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r15
  WCHAR *v6; // rdi
  HANDLE v7; // r14
  int LastFailure; // eax
  int v9; // ebx
  CThirdPartyManager *v10; // rcx
  const unsigned __int16 *v11; // r8
  DWORD PrivateProfileStringW; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  void *QuadPart; // r13
  void *v20; // r12
  void *v21; // r15
  void *v22; // r14
  void *v23; // rdi
  unsigned __int16 *v24; // rbx
  void *v25; // rsi
  unsigned __int64 v26; // rax
  unsigned __int16 v27; // dx
  unsigned __int16 v28; // ax
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r8
  int v31; // edx
  unsigned int v32; // eax
  CThirdPartyManager *v33; // rcx
  unsigned int v34; // [rsp+50h] [rbp-B0h]
  _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  void *v39; // [rsp+78h] [rbp-88h] BYREF
  void *v40; // [rsp+80h] [rbp-80h] BYREF
  void *v41; // [rsp+88h] [rbp-78h] BYREF
  void *v42; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v43; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v44; // [rsp+A0h] [rbp-60h]
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  WCHAR ReturnedString[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v47[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = a2;
  v44 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  if ( !v3 || !this )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, 2147942487LL);
    }
    return 2147942487LL;
  }
  v36 = 0;
  v29 = 0;
  *(_QWORD *)v3 = 0;
  v30 = 0;
  do
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)this + v26) );
    if ( v29 >= v26 )
      break;
    v27 = *((_WORD *)this + v29);
    if ( v27 == 92 || v27 == 47 )
      v30 = v29;
    v47[v29] = v27;
    if ( v29 + 1 >= v26 )
      break;
    v28 = *((_WORD *)this + v29 + 1);
    if ( v28 == 92 || v28 == 47 )
      v30 = v29 + 1;
    v47[v29 + 1] = v28;
    v29 += 2LL;
  }
  while ( v29 < 0x104 );
  if ( 2 * v30 >= 0x208 )
    goto LABEL_20;
  v47[v30] = 0;
  lpFileName = 0;
  CommonUtil::NewSprintfW(
    (CommonUtil *)&lpFileName,
    (unsigned __int16 **)L"%ls%ls",
    v47,
    L"\\SecurityProductInformation.ini");
  v6 = (WCHAR *)lpFileName;
  hObject = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v7 = hObject;
  if ( hObject == (HANDLE)-1LL )
  {
    LastFailure = HrGetLastFailure();
    v9 = LastFailure;
    if ( LastFailure == -2147024894 || LastFailure == -2147024893 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_9:
        if ( v9 < 0 )
        {
          if ( v10 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)v10 + 2), 21, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v9);
LABEL_13:
          if ( v6 )
            operator delete(v6);
          return (unsigned int)v9;
        }
        goto LABEL_16;
      }
      v31 = 34;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_9;
      }
      v31 = 35;
    }
    WPP_SF_Sd(
      *((_QWORD *)v10 + 2),
      v31,
      (unsigned int)WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids,
      (_DWORD)v6,
      LastFailure);
    v10 = WPP_GLOBAL_Control;
    goto LABEL_9;
  }
LABEL_16:
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v7, &FileSize) )
  {
    v32 = HrGetLastFailure();
    v9 = v32;
    v34 = v32;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids, v32);
      v33 = WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
    {
      if ( v33 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v33 + 2), 22, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, (unsigned int)v9);
      if ( v7 != (HANDLE)-1LL )
        CloseHandle(v7);
      goto LABEL_13;
    }
LABEL_18:
    v43 = 0;
    v42 = 0;
    v41 = 0;
    v40 = 0;
    v39 = 0;
    Block = 0;
    FileSize.QuadPart = 0;
    PrivateProfileStringW = GetPrivateProfileStringW(L"Products", L"Name", L"n/a", ReturnedString, 0x104u, v6);
    if ( 2 * (unsigned __int64)PrivateProfileStringW < 0x20A )
    {
      ReturnedString[PrivateProfileStringW] = 0;
      CommonUtil::NewSprintfW((CommonUtil *)&v43, (unsigned __int16 **)L" , Name : %ls", ReturnedString);
      v13 = GetPrivateProfileStringW(L"Products", L"Company", L"n/a", ReturnedString, 0x104u, v6);
      if ( 2 * (unsigned __int64)v13 < 0x20A )
      {
        ReturnedString[v13] = 0;
        CommonUtil::NewSprintfW((CommonUtil *)&v42, (unsigned __int16 **)L"Company : %ls", ReturnedString);
        v14 = GetPrivateProfileStringW(L"Products", L"PathToSignedReportingExe", L"n/a", ReturnedString, 0x104u, v6);
        if ( 2 * (unsigned __int64)v14 < 0x20A )
        {
          ReturnedString[v14] = 0;
          CommonUtil::NewSprintfW(
            (CommonUtil *)&v41,
            (unsigned __int16 **)L"PathToSignedReportingExe : %ls",
            ReturnedString);
          v15 = GetPrivateProfileStringW(L"Products", L"Version", L"n/a", ReturnedString, 0x104u, v6);
          if ( 2 * (unsigned __int64)v15 < 0x20A )
          {
            ReturnedString[v15] = 0;
            CommonUtil::NewSprintfW((CommonUtil *)&v40, (unsigned __int16 **)L"Version : %ls", ReturnedString);
            v16 = GetPrivateProfileStringW(L"Products", L"Environment", L"n/a", ReturnedString, 0x104u, v6);
            if ( 2 * (unsigned __int64)v16 < 0x20A )
            {
              ReturnedString[v16] = 0;
              CommonUtil::NewSprintfW((CommonUtil *)&v39, (unsigned __int16 **)L"Environment : %ls", ReturnedString);
              v17 = GetPrivateProfileStringW(L"Products", L"Runtime_platform", L"n/a", ReturnedString, 0x104u, v6);
              if ( 2 * (unsigned __int64)v17 < 0x20A )
              {
                ReturnedString[v17] = 0;
                CommonUtil::NewSprintfW(
                  (CommonUtil *)&Block,
                  (unsigned __int16 **)L"Runtime_platform : %ls",
                  ReturnedString);
                v18 = GetPrivateProfileStringW(L"Products", L"Upgrade", L"n/a", ReturnedString, 0x104u, v6);
                if ( 2 * (unsigned __int64)v18 < 0x20A )
                {
                  ReturnedString[v18] = 0;
                  CommonUtil::NewSprintfW(
                    (CommonUtil *)&FileSize,
                    (unsigned __int16 **)L"Upgrade : %ls",
                    ReturnedString);
                  QuadPart = (void *)FileSize.QuadPart;
                  v20 = Block;
                  v21 = v39;
                  v22 = v40;
                  v23 = v42;
                  v24 = v43;
                  v25 = v41;
                  CommonUtil::NewSprintfW(
                    (CommonUtil *)&v36,
                    (unsigned __int16 **)L"%ls , %ls , %ls , %ls , %ls , %ls , %ls",
                    v43,
                    v42,
                    v41,
                    v40,
                    v39,
                    Block,
                    FileSize.QuadPart);
                  *(_QWORD *)v44 = v36;
                  if ( QuadPart )
                    operator delete(QuadPart);
                  if ( v20 )
                    operator delete(v20);
                  if ( v21 )
                    operator delete(v21);
                  if ( v22 )
                    operator delete(v22);
                  if ( v25 )
                    operator delete(v25);
                  if ( v23 )
                    operator delete(v23);
                  if ( v24 )
                    operator delete(v24);
                  if ( hObject != (HANDLE)-1LL )
                    CloseHandle(hObject);
                  if ( lpFileName )
                    operator delete((void *)lpFileName);
                  return v34;
                }
              }
            }
          }
        }
      }
    }
LABEL_20:
    _report_rangecheckfailure();
  }
  v34 = 0;
  if ( FileSize.QuadPart <= 0xA00000uLL )
    goto LABEL_18;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids,
      (_DWORD)v6,
      0);
  CommonUtil::HrDuplicateStringW((CommonUtil *)&v36, (unsigned __int16 **)L"INI file too big", v11);
  *(_QWORD *)v3 = v36;
  if ( v7 != (HANDLE)-1LL )
    CloseHandle(v7);
  if ( v6 )
    operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x1800062d0  push    rbp
0x1800062d2  push    rbx
0x1800062d3  push    rsi
0x1800062d4  push    r15
0x1800062d6  lea     rbp, [rsp-3E8h]
0x1800062de  sub     rsp, 4E8h
0x1800062e5  mov     rax, cs:__security_cookie
0x1800062ec  xor     rax, rsp
0x1800062ef  mov     [rbp+400h+var_30], rax
0x1800062f6  mov     r15, rdx
0x1800062f9  mov     [rbp+400h+var_460], rdx
0x1800062fd  mov     rbx, rcx
0x180006300  mov     dl, 1
0x180006302  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x180006309  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000630e  test    r15, r15
0x180006311  jnz     loc_1800068D5
0x180006317  mov     rcx, cs:WPP_GLOBAL_Control
0x18000631e  lea     rsi, WPP_GLOBAL_Control
0x180006325  cmp     rcx, rsi
0x180006328  jnz     loc_180006A38
0x18000632e  mov     eax, 80070057h
0x180006333  jmp     loc_180006428
0x180006338  mov     [rbp+rcx+400h+var_240], r12w
0x180006341  lea     r9, aSecurityproduc; "\\SecurityProductInformation.ini"
0x180006348  lea     rcx, [rsp+500h+lpFileName]; this
0x18000634d  mov     [rsp+500h+lpFileName], r12
0x180006352  lea     r8, [rbp+400h+var_240]; unsigned __int16 *
0x180006359  lea     rdx, aLsLs_0; "%ls%ls"
0x180006360  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180006365  mov     rdi, [rsp+500h+lpFileName]
0x18000636a  xor     r9d, r9d; lpSecurityAttributes
0x18000636d  mov     [rsp+500h+hTemplateFile], r12; hTemplateFile
0x180006372  mov     rcx, rdi; lpFileName
0x180006375  mov     [rsp+500h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000637a  mov     edx, 80000000h; dwDesiredAccess
0x18000637f  mov     r8d, 1; dwShareMode
0x180006385  mov     [rsp+500h+dwCreationDisposition], 3; dwCreationDisposition
0x18000638d  call    cs:__imp_CreateFileW
0x180006393  mov     [rbp+400h+hObject], rax
0x180006397  mov     r14, rax
0x18000639a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000639e  jnz     loc_18000694C
0x1800063a4  call    HrGetLastFailure
0x1800063a9  mov     ebx, eax
0x1800063ab  cmp     eax, 80070002h
0x1800063b0  jz      loc_180006903
0x1800063b6  cmp     eax, 80070003h
0x1800063bb  jz      loc_180006903
0x1800063c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063c8  lea     rsi, WPP_GLOBAL_Control
0x1800063cf  cmp     rcx, rsi
0x1800063d2  jz      short loc_1800063DE
0x1800063d4  test    byte ptr [rcx+1Ch], 1
0x1800063d8  jnz     loc_1800068FC
0x1800063de  test    ebx, ebx
0x1800063e0  jns     short loc_180006444
0x1800063e2  cmp     rcx, rsi
0x1800063e5  jz      short loc_180006405
0x1800063e7  test    byte ptr [rcx+1Ch], 1
0x1800063eb  jz      short loc_180006405
0x1800063ed  mov     rcx, [rcx+10h]
0x1800063f1  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800063f8  mov     edx, 15h
0x1800063fd  mov     r9d, ebx
0x180006400  call    WPP_SF_d
0x180006405  test    rdi, rdi
0x180006408  jnz     loc_1800069CC
0x18000640e  mov     eax, ebx
0x180006410  mov     rdi, [rsp+500h+arg_0]
0x180006418  mov     r14, [rsp+500h+var_20]
0x180006420  mov     r12, [rsp+500h+arg_10]
0x180006428  mov     rcx, [rbp+400h+var_30]
0x18000642f  xor     rcx, rsp; StackCookie
0x180006432  call    __security_check_cookie
0x180006437  add     rsp, 4E8h
0x18000643e  pop     r15
0x180006440  pop     rsi
0x180006441  pop     rbx
0x180006442  pop     rbp
0x180006443  retn
0x180006444  lea     rdx, [rsp+500h+FileSize]; lpFileSize
0x180006449  mov     qword ptr [rsp+500h+FileSize], r12
0x18000644e  mov     rcx, r14; hFile
0x180006451  call    cs:__imp_GetFileSizeEx
0x180006457  test    eax, eax
0x180006459  jz      loc_180006958
0x18000645f  cmp     qword ptr [rsp+500h+FileSize], 0A00000h
0x180006468  mov     [rsp+500h+var_4B0], r12d
0x18000646d  ja      loc_1800069D9
0x180006473  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x180006478  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x18000647c  lea     r8, Default; "n/a"
0x180006483  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x18000648b  lea     rdx, KeyName; "Name"
0x180006492  mov     [rbp+400h+var_468], r12
0x180006496  lea     rcx, AppName; "Products"
0x18000649d  mov     [rbp+400h+var_470], r12
0x1800064a1  mov     [rbp+400h+var_478], r12
0x1800064a5  mov     [rbp+400h+var_480], r12
0x1800064a9  mov     [rsp+500h+var_488], r12
0x1800064ae  mov     [rsp+500h+Block], r12
0x1800064b3  mov     qword ptr [rsp+500h+FileSize], r12
0x1800064b8  call    cs:__imp_GetPrivateProfileStringW
0x1800064be  mov     eax, eax
0x1800064c0  lea     rcx, [rax+rax]
0x1800064c4  cmp     rcx, 20Ah
0x1800064cb  jnb     short loc_180006522
0x1800064cd  mov     [rbp+rcx+400h+ReturnedString], r12w
0x1800064d3  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x1800064d7  lea     rcx, [rbp+400h+var_468]; this
0x1800064db  lea     rdx, aNameLs; " , Name : %ls"
0x1800064e2  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800064e7  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x1800064eb  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x1800064f0  lea     r8, Default; "n/a"
0x1800064f7  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x1800064ff  lea     rdx, aCompany; "Company"
0x180006506  lea     rcx, AppName; "Products"
0x18000650d  call    cs:__imp_GetPrivateProfileStringW
0x180006513  mov     eax, eax
0x180006515  lea     rcx, [rax+rax]
0x180006519  cmp     rcx, 20Ah
0x180006520  jb      short loc_180006528
0x180006522  call    __report_rangecheckfailure
0x180006528  mov     [rbp+rcx+400h+ReturnedString], r12w
0x18000652e  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x180006532  lea     rcx, [rbp+400h+var_470]; this
0x180006536  lea     rdx, aCompanyLs; "Company : %ls"
0x18000653d  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180006542  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x180006546  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x18000654b  lea     r8, Default; "n/a"
0x180006552  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x18000655a  lea     rdx, aPathtosignedre; "PathToSignedReportingExe"
0x180006561  lea     rcx, AppName; "Products"
0x180006568  call    cs:__imp_GetPrivateProfileStringW
0x18000656e  mov     eax, eax
0x180006570  lea     rcx, [rax+rax]
0x180006574  cmp     rcx, 20Ah
0x18000657b  jnb     short loc_180006522
0x18000657d  mov     [rbp+rcx+400h+ReturnedString], r12w
0x180006583  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x180006587  lea     rcx, [rbp+400h+var_478]; this
0x18000658b  lea     rdx, aPathtosignedre_1; "PathToSignedReportingExe : %ls"
0x180006592  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180006597  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x18000659b  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x1800065a0  lea     r8, Default; "n/a"
0x1800065a7  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x1800065af  lea     rdx, aVersion; "Version"
0x1800065b6  lea     rcx, AppName; "Products"
0x1800065bd  call    cs:__imp_GetPrivateProfileStringW
0x1800065c3  mov     eax, eax
0x1800065c5  lea     rcx, [rax+rax]
0x1800065c9  cmp     rcx, 20Ah
0x1800065d0  jnb     loc_180006522
0x1800065d6  mov     [rbp+rcx+400h+ReturnedString], r12w
0x1800065dc  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x1800065e0  lea     rcx, [rbp+400h+var_480]; this
0x1800065e4  lea     rdx, aVersionLs; "Version : %ls"
0x1800065eb  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800065f0  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x1800065f4  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x1800065f9  lea     r8, Default; "n/a"
0x180006600  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x180006608  lea     rdx, aEnvironment; "Environment"
0x18000660f  lea     rcx, AppName; "Products"
0x180006616  call    cs:__imp_GetPrivateProfileStringW
0x18000661c  mov     eax, eax
0x18000661e  lea     rcx, [rax+rax]
0x180006622  cmp     rcx, 20Ah
0x180006629  jnb     loc_180006522
0x18000662f  mov     [rbp+rcx+400h+ReturnedString], r12w
0x180006635  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x180006639  lea     rcx, [rsp+500h+var_488]; this
0x18000663e  lea     rdx, aEnvironmentLs; "Environment : %ls"
0x180006645  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18000664a  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x18000664e  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x180006653  lea     r8, Default; "n/a"
0x18000665a  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x180006662  lea     rdx, aRuntimePlatfor; "Runtime_platform"
0x180006669  lea     rcx, AppName; "Products"
0x180006670  call    cs:__imp_GetPrivateProfileStringW
0x180006676  mov     eax, eax
0x180006678  lea     rdx, [rax+rax]
0x18000667c  cmp     rdx, 20Ah
0x180006683  jnb     loc_180006522
0x180006689  mov     [rbp+rdx+400h+ReturnedString], r12w
0x18000668f  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x180006693  lea     rdx, aRuntimePlatfor_0; "Runtime_platform : %ls"
0x18000669a  lea     rcx, [rsp+500h+Block]; this
0x18000669f  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800066a4  lea     r9, [rbp+400h+ReturnedString]; lpReturnedString
0x1800066a8  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rdi; lpFileName
0x1800066ad  lea     r8, Default; "n/a"
0x1800066b4  mov     [rsp+500h+dwCreationDisposition], 104h; nSize
0x1800066bc  lea     rdx, aUpgrade; "Upgrade"
0x1800066c3  lea     rcx, AppName; "Products"
0x1800066ca  call    cs:__imp_GetPrivateProfileStringW
0x1800066d0  mov     eax, eax
0x1800066d2  lea     rcx, [rax+rax]
0x1800066d6  cmp     rcx, 20Ah
0x1800066dd  jnb     loc_180006522
0x1800066e3  mov     [rbp+rcx+400h+ReturnedString], r12w
0x1800066e9  lea     r8, [rbp+400h+ReturnedString]; unsigned __int16 *
0x1800066ed  lea     rcx, [rsp+500h+FileSize]; this
0x1800066f2  mov     [rsp+500h+arg_18], r13
0x1800066fa  lea     rdx, aUpgradeLs; "Upgrade : %ls"
0x180006701  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180006706  mov     r13, qword ptr [rsp+500h+FileSize]
0x18000670b  lea     rdx, aLsLsLsLsLsLsLs; "%ls , %ls , %ls , %ls , %ls , %ls , %ls"
0x180006712  mov     r12, [rsp+500h+Block]
0x180006717  lea     rcx, [rsp+500h+var_4A0]; this
0x18000671c  mov     r15, [rsp+500h+var_488]
0x180006721  mov     r14, [rbp+400h+var_480]
0x180006725  mov     rdi, [rbp+400h+var_470]
0x180006729  mov     rbx, [rbp+400h+var_468]
0x18000672d  mov     r9, rdi
0x180006730  mov     rsi, [rbp+400h+var_478]
0x180006734  mov     r8, rbx; unsigned __int16 *
0x180006737  mov     [rsp+500h+var_4C0], r13
0x18000673c  mov     [rsp+500h+var_4C8], r12
0x180006741  mov     [rsp+500h+hTemplateFile], r15
0x180006746  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], r14
0x18000674b  mov     qword ptr [rsp+500h+dwCreationDisposition], rsi
0x180006750  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180006755  mov     rcx, [rbp+400h+var_460]
0x180006759  mov     rax, [rsp+500h+var_4A0]
0x18000675e  mov     [rcx], rax
0x180006761  test    r13, r13
0x180006764  jz      short loc_18000676E
0x180006766  mov     rcx, r13; Block
0x180006769  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000676e  mov     r13, [rsp+500h+arg_18]
0x180006776  test    r12, r12
0x180006779  jz      short loc_180006783
0x18000677b  mov     rcx, r12; Block
0x18000677e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006783  test    r15, r15
0x180006786  jz      short loc_180006790
0x180006788  mov     rcx, r15; Block
0x18000678b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006790  test    r14, r14
0x180006793  jz      short loc_18000679D
0x180006795  mov     rcx, r14; Block
0x180006798  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000679d  test    rsi, rsi
0x1800067a0  jz      short loc_1800067AA
0x1800067a2  mov     rcx, rsi; Block
0x1800067a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800067aa  test    rdi, rdi
0x1800067ad  jz      short loc_1800067B7
0x1800067af  mov     rcx, rdi; Block
0x1800067b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800067b7  test    rbx, rbx
0x1800067ba  jz      short loc_1800067C4
0x1800067bc  mov     rcx, rbx; Block
0x1800067bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800067c4  mov     rcx, [rbp+400h+hObject]; hObject
0x1800067c8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800067cc  jnz     loc_180006A23
0x1800067d2  mov     rcx, [rsp+500h+lpFileName]; Block
0x1800067d7  test    rcx, rcx
0x1800067da  jnz     loc_180006A2E
0x1800067e0  mov     eax, [rsp+500h+var_4B0]
0x1800067e4  jmp     loc_180006410
0x1800067f0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800067f7  nop     word ptr [rax+rax+00000000h]
0x180006800  inc     rax
0x180006803  cmp     [rbx+rax*2], r12w
0x180006808  jnz     short loc_180006800
0x18000680a  cmp     rcx, rax
0x18000680d  jnb     short loc_180006856
0x18000680f  movzx   edx, word ptr [rbx+rcx*2]
0x180006813  cmp     dx, 5Ch ; '\'
0x180006817  jz      short loc_18000687C
0x180006819  cmp     dx, 2Fh ; '/'
0x18000681d  jz      short loc_18000687C
0x18000681f  mov     [rbp+rcx*2+400h+var_240], dx
0x180006827  lea     rdx, [rcx+1]
0x18000682b  cmp     rdx, rax
0x18000682e  jnb     short loc_180006856
0x180006830  movzx   eax, word ptr [rbx+rcx*2+2]
0x180006835  cmp     ax, 5Ch ; '\'
0x180006839  jz      short loc_180006881
0x18000683b  cmp     ax, 2Fh ; '/'
0x18000683f  jz      short loc_180006881
0x180006841  mov     [rbp+rcx*2+400h+var_23E], ax
0x180006849  add     rcx, 2
0x18000684d  cmp     rcx, 104h
0x180006854  jb      short loc_1800067F0
0x180006856  lea     rcx, [r8+r8]
0x18000685a  mov     [rsp+500h+arg_0], rdi
0x180006862  mov     [rsp+500h+var_20], r14
0x18000686a  cmp     rcx, 208h
0x180006871  jnb     loc_180006522
0x180006877  jmp     loc_180006338
0x18000687c  mov     r8, rcx
  ... truncated ...
```
