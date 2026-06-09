# UninstallWorker(void *)

- ea: `0x14000afc0`
- end: `0x14000b845`
- name: `?UninstallWorker@@YAKPEAX@Z`
- size: `2181`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x1400044e0`
- `0x140005794`
- `0x14000ab54`
- `0x14000afc0`
- `0x14000e280`
- `0x14000ec58`
- `0x14000ee88`
- `0x14000f240`
- `0x140010aa0`
- `0x140010c28`
- `0x140010c94`
- `0x140010e88`
- `0x140011004`
- `0x140011190`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000b723`
- `ADVAPI32!EventWrite` at `0x14000b723`
- `KERNEL32!GetCommandLineW` at `0x14000b6a6`
- `KERNEL32!GetCommandLineW` at `0x14000b6a6`
- `KERNEL32!LocalFree` at `0x14000b81a`
- `KERNEL32!LocalFree` at `0x14000b81a`
- `KERNEL32!FindFirstFileW` at `0x14000b166`
- `KERNEL32!FindFirstFileW` at `0x14000b166`
- `KERNEL32!lstrcmpiW` at `0x14000b1cf`
- `KERNEL32!lstrcmpiW` at `0x14000b24c`
- `KERNEL32!lstrcmpiW` at `0x14000b1cf`
- `KERNEL32!lstrcmpiW` at `0x14000b24c`
- `KERNEL32!FindClose` at `0x14000b79e`
- `KERNEL32!FindClose` at `0x14000b79e`
- `KERNEL32!GetLastError` at `0x14000b175`
- `KERNEL32!GetLastError` at `0x14000b2bb`
- `KERNEL32!GetLastError` at `0x14000b175`
- `KERNEL32!GetLastError` at `0x14000b2bb`
- `KERNEL32!FindNextFileW` at `0x14000b299`
- `KERNEL32!FindNextFileW` at `0x14000b299`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000b031`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000b031`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b7d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b7d6`

## string_xrefs

- `0x14000b03b`: `Failed to initialize COM`
- `0x14000b047`: `UninstallWorker`
- `0x14000b0db`: `UninstallWorker`
- `0x14000b124`: `UninstallWorker`
- `0x14000b37f`: `UninstallWorker`
- `0x14000b7b6`: `UninstallWorker`
- `0x14000b7c5`: `Failed to create a new CBS client`
- `0x14000b13b`: `Failed to build a wildcard file name under the directory %S`
- `0x14000b320`: `Failed to copy filename prefix`
- `0x14000b2f1`: `Failed to build a file name under the directory %S`
- `0x14000b369`: `Failed: CreatePackage() for %S`
- `0x14000b3b9`: `Failed: OpenPackageByKB() for %S`
- `0x14000b3e3`: `Update is not installed`
- `0x14000b47c`: `Update is not installed`
- `0x14000b426`: `Failed to display update-not-installed message box`
- `0x14000b4bb`: `Failed to display update-not-installed message box`
- `0x14000b73d`: `Update does not support uninstall`
- `0x14000b77c`: `Failed to display update-permanent message box`
- `0x14000b501`: `Failed to set update title`
- `0x14000b549`: `Failed to display welcome`
- `0x14000b569`: `Failed; user cancelled the uninstall`
- `0x14000b5d9`: `Failed; user cancelled the uninstall`
- `0x14000b57f`: `Start of uninstall`
- `0x14000b5f4`: `Failed to uninstall package`
- `0x14000b665`: `End of uninstall`
- `0x14000b68b`: `Reboot was required for update %S`
- `0x14000b614`: `Package type is not supported for uninstall`
- `0x14000b657`: `Failed to display uninstall-not-supported message box`

## pseudocode

```c
__int64 __fastcall UninstallWorker(PVOID Parameter)
{
  signed int Package; // ebx
  LPVOID *v2; // rax
  const wchar_t **v3; // rsi
  __int64 v4; // r8
  __int64 FirstFileW; // r15
  __int64 v6; // r8
  WCHAR *v7; // r9
  const char *v8; // r8
  __int64 v9; // rdx
  signed int LastError; // eax
  int v11; // r14d
  __int64 v12; // rcx
  WCHAR *cFileName; // r8
  __int64 v14; // rdx
  WCHAR *v15; // rax
  WCHAR *v16; // rcx
  signed int v17; // eax
  const char *v18; // r8
  __int64 v19; // rdx
  int *v20; // r9
  AppModule *v21; // rcx
  const char *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  LPWSTR CommandLineW; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  HLOCAL v30; // rsi
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+34h] [rbp-CCh] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v36[3]; // [rsp+44h] [rbp-BCh] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+2A0h] [rbp+1A0h] BYREF
  LPWSTR v39; // [rsp+2B0h] [rbp+1B0h]
  int v40; // [rsp+2B8h] [rbp+1B8h]
  int v41; // [rsp+2BCh] [rbp+1BCh]
  WCHAR FileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR String1[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  LODWORD(hMem) = 0;
  v36[0] = 0;
  v32 = 0;
  v33 = 0;
  if ( CoInitializeEx(0, 2u) < 0 )
  {
    Package = 0;
    WusaLogDebugEventA(L"UninstallWorker", 593, "Failed to initialize COM");
    return (unsigned int)Package;
  }
  v2 = (LPVOID *)operator new(0x228u);
  if ( !v2 || (v3 = (const wchar_t **)CbsClient::CbsClient(v2, TargetPath)) == 0 )
  {
    WusaLogDebugEventA(L"UninstallWorker", 597, "Failed to create a new CBS client");
    Package = -2147024882;
    goto LABEL_89;
  }
  FirstFileW = -1;
  if ( pszPath )
  {
    WusaPostMessage(0x404u, 0, v4);
    Package = WusaMountOrExtractAllFilesFromCabinet(TargetPath, pszPath, &v33);
    if ( Package < 0 )
    {
      v7 = (WCHAR *)pszPath;
      v8 = "Failed to extract the MSU %S";
      v9 = 608;
LABEL_8:
      WusaLogDebugEventA(L"UninstallWorker", v9, v8, v7);
LABEL_71:
      if ( Package == -2145124297 )
      {
        WusaLogDebugEventA(L"UninstallWorker", 794, "Package type is not supported for uninstall");
        if ( (int)WusaMessageBox(0xEA7Du, 0xEA60u, 1, (PCWSTR)0xFFFE, 0, qword_1400201F0) < 0 )
        {
          v22 = "Failed to display uninstall-not-supported message box";
          v23 = 798;
LABEL_63:
          WusaLogDebugEventA(L"UninstallWorker", v23, v22);
          goto LABEL_85;
        }
      }
      goto LABEL_85;
    }
    dword_140020180 = v33;
    WusaPostMessage(0x400u, 0, v6);
    Package = StringCchPrintfW(FileName, 0x104u, L"%s\\*.cab", TargetPath);
    if ( Package < 0 )
    {
      WusaLogDebugEventA(
        L"UninstallWorker",
        619,
        "Failed to build a wildcard file name under the directory %S",
        TargetPath);
      goto LABEL_71;
    }
    WusaLogDebugEventA(L"UninstallWorker", 621, "Start of search");
    FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      Package = LastError;
      if ( LastError > 0 )
        Package = (unsigned __int16)LastError | 0x80070000;
      v7 = FileName;
      v8 = "Failed: FindFirstFile() for %S";
      if ( Package >= 0 )
        Package = -2147467259;
      v9 = 624;
      goto LABEL_8;
    }
    v11 = 0;
    do
    {
      memset_0(String1, 0, 0x208u);
      if ( lstrcmpiW(FindFileData.cFileName, L"wsusscan.cab") )
      {
        v12 = 3;
        cFileName = FindFileData.cFileName;
        v14 = 260;
        v15 = String1;
        do
        {
          if ( !v12 )
            break;
          if ( !*cFileName )
            break;
          *v15++ = *cFileName++;
          --v12;
          --v14;
        }
        while ( v14 );
        v16 = v15 - 1;
        if ( v14 )
          v16 = v15;
        *v16 = 0;
        Package = v14 == 0 ? 0x8007007A : 0;
        if ( !v14 )
        {
          WusaLogDebugEventA(L"UninstallWorker", 636, "Failed to copy filename prefix");
          goto LABEL_71;
        }
        if ( lstrcmpiW(String1, L"SSU") )
        {
          if ( v11 )
          {
            v18 = "Failed. More than one packages found in the sandbox";
            v19 = 646;
LABEL_38:
            Package = -2147418113;
            WusaLogDebugEventA(L"UninstallWorker", v19, v18);
            goto LABEL_86;
          }
          Package = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", TargetPath, FindFileData.cFileName);
          if ( Package < 0 )
          {
            v7 = (WCHAR *)TargetPath;
            v8 = "Failed to build a file name under the directory %S";
            v9 = 650;
            goto LABEL_8;
          }
          v11 = 1;
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    WusaLogDebugEventA(L"UninstallWorker", 656, "End of search");
    v17 = GetLastError();
    Package = v17;
    if ( v17 != 18 )
    {
      if ( v17 > 0 )
        Package = (unsigned __int16)v17 | 0x80070000;
      if ( Package < 0 )
      {
        WusaLogDebugEventA(L"UninstallWorker", 662, "Failed: FindNextFile()");
        goto LABEL_71;
      }
    }
    if ( !v11 )
    {
      v18 = "Failed. No packages found in the sandbox";
      v19 = 668;
      goto LABEL_38;
    }
    Package = CbsClient::CreatePackage((CbsClient *)v3, FileName);
    if ( Package < 0 )
    {
      v7 = FileName;
      v9 = 676;
      v8 = "Failed: CreatePackage() for %S";
      goto LABEL_8;
    }
LABEL_49:
    Package = CbsClient::GetState((CbsClient *)v3, (enum _CbsInstallState *)&v32, (int *)&hMem, v20);
    if ( Package >= 0 )
    {
      if ( v32 >= 6 )
      {
        if ( v32 <= 7 && !(_DWORD)hMem )
        {
          Package = AppModule::SetUpdateTitle(v21, v3[68]);
          if ( Package < 0 )
          {
            WusaLogDebugEventA(L"UninstallWorker", 739, "Failed to set update title");
            goto LABEL_71;
          }
          v35 = 6;
          Package = WusaMessageBox(0xEA71u, 0xEA60u, 6, (PCWSTR)0xFFFF, &v35, v3[68]);
          if ( Package < 0 )
          {
            WusaLogDebugEventA(L"UninstallWorker", 744, "Failed to display welcome");
            goto LABEL_71;
          }
          if ( v35 == 7 )
          {
            Package = -2147023673;
            v22 = "Failed; user cancelled the uninstall";
            v23 = 749;
          }
          else
          {
            WusaLogDebugEventA(L"UninstallWorker", 758, "Start of uninstall");
            WusaPostMessage(0x405u, 0, v24);
            Package = BlockShutDown();
            if ( Package < 0 )
            {
              WusaLogDebugEventA(L"UninstallWorker", 763, "Failed to block Operation System shutdown");
              goto LABEL_71;
            }
            v26 = CbsClient::ChangeState(v3, v25, v36);
            Package = v26;
            if ( v26 != -2146498528 || !dword_1400201AC )
            {
              dword_14002024C = v26;
              if ( v26 < 0 )
              {
                WusaLogDebugEventA(L"UninstallWorker", 774, "Failed to uninstall package");
                goto LABEL_71;
              }
              WusaLogDebugEventA(L"UninstallWorker", 777, "End of uninstall");
              if ( v36[0] == 1 )
              {
                dword_140020250 = 1;
                WusaLogDebugEventA(L"UninstallWorker", 782, "Reboot was required for update %S", v3[67]);
                CommandLineW = GetCommandLineW();
                UserData.Ptr = (ULONGLONG)off_1400201D8;
                v28 = -1;
                do
                  ++v28;
                while ( *((_WORD *)off_1400201D8 + v28) );
                UserData.Reserved = 0;
                UserData.Size = 2 * v28 + 2;
                v29 = -1;
                v39 = CommandLineW;
                do
                  ++v29;
                while ( CommandLineW[v29] );
                v40 = 2 * v29 + 2;
                v41 = 0;
                EventWrite(RegHandle, &WUSA_EVENT_UNINSTALLREBOOTREQUIRED, 2u, &UserData);
              }
              else if ( dword_140020194 == 2 )
              {
                dword_140020250 = 1;
              }
              goto LABEL_85;
            }
            Package = -2147023673;
            v22 = "Failed; user cancelled the uninstall";
            v23 = 769;
          }
          goto LABEL_63;
        }
        WusaLogDebugEventA(L"UninstallWorker", 723, "Update does not support uninstall");
        if ( (int)WusaMessageBox(0xEA70u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0, v3[68]) < 0 )
          WusaLogDebugEventA(L"UninstallWorker", 727, "Failed to display update-permanent message box");
        Package = -2145116156;
      }
      else
      {
        WusaLogDebugEventA(L"UninstallWorker", 711, "Update is not installed");
        if ( (int)WusaMessageBox(0xEA6Fu, 0xEA60u, 1, (PCWSTR)0xFFFF, 0, v3[68]) < 0 )
          WusaLogDebugEventA(L"UninstallWorker", 715, "Failed to display update-not-installed message box");
        Package = 2359303;
      }
LABEL_85:
      if ( FirstFileW != -1 )
LABEL_86:
        FindClose((HANDLE)FirstFileW);
      goto LABEL_87;
    }
    v7 = FileName;
    v9 = 707;
    v8 = "Failed: GetState() for %S";
    goto LABEL_8;
  }
  WusaPostMessage(0x400u, 0, v4);
  WusaLogDebugEventA(L"UninstallWorker", 682, "Start of search");
  Package = CbsClient::OpenPackageByKB((CbsClient *)v3, qword_1400201F0);
  if ( Package < 0 )
  {
    WusaLogDebugEventA(L"UninstallWorker", 685, "Failed: OpenPackageByKB() for %S", qword_1400201F0);
    goto LABEL_71;
  }
  WusaLogDebugEventA(L"UninstallWorker", 687, "End of search");
  if ( Package != 2359303 )
    goto LABEL_49;
  WusaLogDebugEventA(L"UninstallWorker", 691, "Update is not installed");
  if ( (int)WusaMessageBox(0xEA68u, 0xEA60u, 1, (PCWSTR)0xFFFF, 0, qword_1400201F0) < 0 )
    WusaLogDebugEventA(L"UninstallWorker", 695, "Failed to display update-not-installed message box");
LABEL_87:
  CbsClient::~CbsClient((CbsClient *)v3);
  operator delete(v3);
LABEL_89:
  CoUninitialize();
  if ( Package < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(Package, (unsigned __int16 **)&hMem);
    v30 = hMem;
    WusaLogDebugEventA(L"UninstallWorker", 817, "Exit with error code 0X%x (%ls)", Package, (const wchar_t *)hMem);
    if ( v30 )
      LocalFree(v30);
  }
  return (unsigned int)Package;
}

```

## disassembly

```asm
0x14000afc0  push    rbp
0x14000afc2  push    rbx
0x14000afc3  push    rsi
0x14000afc4  push    rdi
0x14000afc5  push    r12
0x14000afc7  push    r13
0x14000afc9  push    r14
0x14000afcb  push    r15
0x14000afcd  lea     rbp, [rsp-5F8h]
0x14000afd5  sub     rsp, 6F8h
0x14000afdc  mov     rax, cs:__security_cookie
0x14000afe3  xor     rax, rsp
0x14000afe6  mov     [rbp+630h+var_50], rax
0x14000afed  xor     edx, edx; Val
0x14000afef  lea     rcx, [rbp+630h+FileName]; void *
0x14000aff6  mov     r8d, 208h; Size
0x14000affc  call    memset_0
0x14000b001  xor     edx, edx; Val
0x14000b003  lea     rcx, [rsp+730h+FindFileData]; void *
0x14000b008  mov     r8d, 250h; Size
0x14000b00e  call    memset_0
0x14000b013  xor     r12d, r12d
0x14000b016  xor     ecx, ecx; pvReserved
0x14000b018  mov     dword ptr [rsp+730h+hMem], r12d
0x14000b01d  mov     [rsp+730h+var_6EC], r12d
0x14000b022  mov     [rsp+730h+var_700], r12d
0x14000b027  lea     edx, [r12+2]; dwCoInit
0x14000b02c  mov     [rsp+730h+var_6FC], r12d
0x14000b031  call    cs:__imp_CoInitializeEx
0x14000b037  test    eax, eax
0x14000b039  jns     short loc_14000B05B
0x14000b03b  lea     r8, aFailedToInitia_2; "Failed to initialize COM"
0x14000b042  mov     edx, 251h
0x14000b047  lea     rcx, aUninstallworke; "UninstallWorker"
0x14000b04e  mov     ebx, r12d
0x14000b051  call    WusaLogDebugEventA
0x14000b056  jmp     loc_14000B820
0x14000b05b  mov     ecx, 228h; Size
0x14000b060  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b065  test    rax, rax
0x14000b068  jz      loc_14000B7B6
0x14000b06e  mov     rdx, cs:TargetPath; unsigned __int16 *
0x14000b075  mov     rcx, rax; ppv
0x14000b078  call    ??0CbsClient@@QEAA@PEBG@Z; CbsClient::CbsClient(ushort const *)
0x14000b07d  mov     rsi, rax
0x14000b080  test    rax, rax
0x14000b083  jz      loc_14000B7B6
0x14000b089  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000b08d  xor     edx, edx; wParam
0x14000b08f  cmp     cs:pszPath, r12
0x14000b096  lea     r13d, [r15+2]
0x14000b09a  jz      loc_14000B375
0x14000b0a0  mov     ecx, 404h; Msg
0x14000b0a5  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x14000b0aa  mov     rdx, cs:pszPath; pszPath
0x14000b0b1  lea     r8, [rsp+730h+var_6FC]; int *
0x14000b0b6  mov     rcx, cs:TargetPath; TargetPath
0x14000b0bd  call    ?WusaMountOrExtractAllFilesFromCabinet@@YAJPEBG0PEAH@Z; WusaMountOrExtractAllFilesFromCabinet(ushort const *,ushort const *,int *)
0x14000b0c2  mov     ebx, eax
0x14000b0c4  test    eax, eax
0x14000b0c6  jns     short loc_14000B0EF
0x14000b0c8  mov     r9, cs:pszPath
0x14000b0cf  lea     r8, aFailedToExtrac_0; "Failed to extract the MSU %S"
0x14000b0d6  mov     edx, 260h
0x14000b0db  lea     rdi, aUninstallworke; "UninstallWorker"
0x14000b0e2  mov     rcx, rdi
0x14000b0e5  call    WusaLogDebugEventA
0x14000b0ea  jmp     loc_14000B608
0x14000b0ef  mov     eax, [rsp+730h+var_6FC]
0x14000b0f3  xor     edx, edx; wParam
0x14000b0f5  mov     ecx, 400h; Msg
0x14000b0fa  mov     cs:dword_140020180, eax
0x14000b100  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x14000b105  mov     r9, cs:TargetPath
0x14000b10c  lea     r8, aSCab; "%s\\*.cab"
0x14000b113  mov     edx, 104h; unsigned __int64
0x14000b118  lea     rcx, [rbp+630h+FileName]; unsigned __int16 *
0x14000b11f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b124  lea     rdi, aUninstallworke; "UninstallWorker"
0x14000b12b  mov     ebx, eax
0x14000b12d  mov     rcx, rdi
0x14000b130  test    eax, eax
0x14000b132  jns     short loc_14000B149
0x14000b134  mov     r9, cs:TargetPath
0x14000b13b  lea     r8, aFailedToBuildA_0; "Failed to build a wildcard file name un"...
0x14000b142  mov     edx, 26Bh
0x14000b147  jmp     short loc_14000B0E5
0x14000b149  lea     r8, aStartOfSearch; "Start of search"
0x14000b150  mov     edx, 26Dh
0x14000b155  call    WusaLogDebugEventA
0x14000b15a  lea     rdx, [rsp+730h+FindFileData]; lpFindFileData
0x14000b15f  lea     rcx, [rbp+630h+FileName]; lpFileName
0x14000b166  call    cs:__imp_FindFirstFileW
0x14000b16c  mov     r15, rax
0x14000b16f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b173  jnz     short loc_14000B1AC
0x14000b175  call    cs:__imp_GetLastError
0x14000b17b  mov     ebx, eax
0x14000b17d  test    eax, eax
0x14000b17f  jle     short loc_14000B18A
0x14000b181  movzx   ebx, ax
0x14000b184  or      ebx, 80070000h
0x14000b18a  test    ebx, ebx
0x14000b18c  lea     r9, [rbp+630h+FileName]
0x14000b193  mov     eax, 80004005h
0x14000b198  lea     r8, aFailedFindfirs; "Failed: FindFirstFile() for %S"
0x14000b19f  cmovns  ebx, eax
0x14000b1a2  mov     edx, 270h
0x14000b1a7  jmp     loc_14000B0E2
0x14000b1ac  mov     r14d, r12d
0x14000b1af  xor     edx, edx; Val
0x14000b1b1  lea     rcx, [rbp+630h+String1]; void *
0x14000b1b8  mov     r8d, 208h; Size
0x14000b1be  call    memset_0
0x14000b1c3  lea     rdx, aWsusscanCab; "wsusscan.cab"
0x14000b1ca  lea     rcx, [rsp+730h+FindFileData.cFileName]; lpString1
0x14000b1cf  call    cs:__imp_lstrcmpiW
0x14000b1d5  test    eax, eax
0x14000b1d7  jz      loc_14000B291
0x14000b1dd  mov     ecx, 3
0x14000b1e2  lea     r8, [rsp+730h+FindFileData.cFileName]
0x14000b1e7  mov     edx, 104h
0x14000b1ec  lea     rax, [rbp+630h+String1]
0x14000b1f3  test    rcx, rcx
0x14000b1f6  jz      short loc_14000B216
0x14000b1f8  movzx   r9d, word ptr [r8]
0x14000b1fc  test    r9w, r9w
0x14000b200  jz      short loc_14000B216
0x14000b202  mov     [rax], r9w
0x14000b206  add     r8, 2
0x14000b20a  add     rax, 2
0x14000b20e  sub     rcx, r13
0x14000b211  sub     rdx, r13
0x14000b214  jnz     short loc_14000B1F3
0x14000b216  test    rdx, rdx
0x14000b219  lea     rcx, [rax-2]
0x14000b21d  cmovnz  rcx, rax
0x14000b221  mov     rax, rdx
0x14000b224  neg     rax
0x14000b227  sbb     ebx, ebx
0x14000b229  not     ebx
0x14000b22b  mov     [rcx], r12w
0x14000b22f  and     ebx, 8007007Ah
0x14000b235  test    rdx, rdx
0x14000b238  jz      loc_14000B320
0x14000b23e  lea     rdx, aSsu; "SSU"
0x14000b245  lea     rcx, [rbp+630h+String1]; lpString1
0x14000b24c  call    cs:__imp_lstrcmpiW
0x14000b252  test    eax, eax
0x14000b254  jz      short loc_14000B291
0x14000b256  test    r14d, r14d
0x14000b259  jnz     loc_14000B302
0x14000b25f  mov     r9, cs:TargetPath
0x14000b266  lea     rax, [rsp+730h+FindFileData.cFileName]
0x14000b26b  lea     r8, aSS; "%s\\%s"
0x14000b272  mov     [rsp+730h+var_710], rax
0x14000b277  mov     edx, 104h; unsigned __int64
0x14000b27c  lea     rcx, [rbp+630h+FileName]; unsigned __int16 *
0x14000b283  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b288  mov     ebx, eax
0x14000b28a  test    eax, eax
0x14000b28c  js      short loc_14000B2EA
0x14000b28e  mov     r14d, r13d
0x14000b291  lea     rdx, [rsp+730h+FindFileData]; lpFindFileData
0x14000b296  mov     rcx, r15; hFindFile
0x14000b299  call    cs:__imp_FindNextFileW
0x14000b29f  test    eax, eax
0x14000b2a1  jnz     loc_14000B1AF
0x14000b2a7  lea     r8, aEndOfSearch; "End of search"
0x14000b2ae  mov     edx, 290h
0x14000b2b3  mov     rcx, rdi
0x14000b2b6  call    WusaLogDebugEventA
0x14000b2bb  call    cs:__imp_GetLastError
0x14000b2c1  mov     ebx, eax
0x14000b2c3  cmp     eax, 12h
0x14000b2c6  jz      short loc_14000B331
0x14000b2c8  test    eax, eax
0x14000b2ca  jle     short loc_14000B2D5
0x14000b2cc  movzx   ebx, ax
0x14000b2cf  or      ebx, 80070000h
0x14000b2d5  test    ebx, ebx
0x14000b2d7  jns     short loc_14000B331
0x14000b2d9  lea     r8, aFailedFindnext; "Failed: FindNextFile()"
0x14000b2e0  mov     edx, 296h
0x14000b2e5  jmp     loc_14000B600
0x14000b2ea  mov     r9, cs:TargetPath
0x14000b2f1  lea     r8, aFailedToBuildA; "Failed to build a file name under the d"...
0x14000b2f8  mov     edx, 28Ah
0x14000b2fd  jmp     loc_14000B0E2
0x14000b302  lea     r8, aFailedMoreThan; "Failed. More than one packages found in"...
0x14000b309  mov     edx, 286h
0x14000b30e  mov     rcx, rdi
0x14000b311  mov     ebx, 8000FFFFh
0x14000b316  call    WusaLogDebugEventA
0x14000b31b  jmp     loc_14000B79B
0x14000b320  lea     r8, aFailedToCopyFi; "Failed to copy filename prefix"
0x14000b327  mov     edx, 27Ch
0x14000b32c  jmp     loc_14000B600
0x14000b331  test    r14d, r14d
0x14000b334  jnz     short loc_14000B344
0x14000b336  lea     r8, aFailedNoPackag; "Failed. No packages found in the sandbo"...
0x14000b33d  mov     edx, 29Ch
0x14000b342  jmp     short loc_14000B30E
0x14000b344  lea     rdx, [rbp+630h+FileName]; unsigned __int16 *
0x14000b34b  mov     rcx, rsi; this
0x14000b34e  call    ?CreatePackage@CbsClient@@QEAAJPEBG@Z; CbsClient::CreatePackage(ushort const *)
0x14000b353  mov     ebx, eax
0x14000b355  test    eax, eax
0x14000b357  jns     loc_14000B43F
0x14000b35d  lea     r9, [rbp+630h+FileName]
0x14000b364  mov     edx, 2A4h
0x14000b369  lea     r8, aFailedCreatepa; "Failed: CreatePackage() for %S"
0x14000b370  jmp     loc_14000B0E2
0x14000b375  mov     ecx, 400h; Msg
0x14000b37a  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x14000b37f  lea     rdi, aUninstallworke; "UninstallWorker"
0x14000b386  mov     edx, 2AAh
0x14000b38b  mov     rcx, rdi
0x14000b38e  lea     r8, aStartOfSearch; "Start of search"
0x14000b395  call    WusaLogDebugEventA
0x14000b39a  mov     rdx, cs:qword_1400201F0; unsigned __int16 *
0x14000b3a1  mov     rcx, rsi; this
0x14000b3a4  call    ?OpenPackageByKB@CbsClient@@QEAAJPEBG@Z; CbsClient::OpenPackageByKB(ushort const *)
0x14000b3a9  mov     ebx, eax
0x14000b3ab  mov     rcx, rdi
0x14000b3ae  test    eax, eax
0x14000b3b0  jns     short loc_14000B3CA
0x14000b3b2  mov     r9, cs:qword_1400201F0
0x14000b3b9  lea     r8, aFailedOpenpack; "Failed: OpenPackageByKB() for %S"
0x14000b3c0  mov     edx, 2ADh
0x14000b3c5  jmp     loc_14000B0E5
0x14000b3ca  lea     r8, aEndOfSearch; "End of search"
0x14000b3d1  mov     edx, 2AFh
0x14000b3d6  call    WusaLogDebugEventA
0x14000b3db  cmp     ebx, 240007h
0x14000b3e1  jnz     short loc_14000B43F
0x14000b3e3  lea     r8, aUpdateIsNotIns; "Update is not installed"
0x14000b3ea  mov     edx, 2B3h
0x14000b3ef  mov     rcx, rdi
0x14000b3f2  call    WusaLogDebugEventA
0x14000b3f7  mov     rax, cs:qword_1400201F0
0x14000b3fe  mov     edx, 0EA60h; DWORD
0x14000b403  mov     [rsp+730h+var_708], rax
0x14000b408  mov     r9d, 0FFFFh; pszIcon
0x14000b40e  mov     r8d, r13d; dwCommonButtons
0x14000b411  mov     [rsp+730h+var_710], r12; int *
0x14000b416  lea     ecx, [rdx+8]; dwMessageId
0x14000b419  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000b41e  test    eax, eax
0x14000b420  jns     loc_14000B7A4
0x14000b426  lea     r8, aFailedToDispla_3; "Failed to display update-not-installed "...
0x14000b42d  mov     edx, 2B7h
0x14000b432  mov     rcx, rdi
0x14000b435  call    WusaLogDebugEventA
0x14000b43a  jmp     loc_14000B7A4
0x14000b43f  lea     r8, [rsp+730h+hMem]; int *
0x14000b444  mov     rcx, rsi; this
0x14000b447  lea     rdx, [rsp+730h+var_700]; enum _CbsInstallState *
0x14000b44c  call    ?GetState@CbsClient@@QEAAJPEAW4_CbsInstallState@@PEAHPEAJ@Z; CbsClient::GetState(_CbsInstallState *,int *,long *)
0x14000b451  mov     ebx, eax
0x14000b453  test    eax, eax
0x14000b455  jns     short loc_14000B46F
0x14000b457  lea     r9, [rbp+630h+FileName]
0x14000b45e  mov     edx, 2C3h
0x14000b463  lea     r8, aFailedGetstate; "Failed: GetState() for %S"
0x14000b46a  jmp     loc_14000B0E2
0x14000b46f  mov     r14d, 6
0x14000b475  cmp     [rsp+730h+var_700], r14d
0x14000b47a  jge     short loc_14000B4D9
0x14000b47c  lea     r8, aUpdateIsNotIns; "Update is not installed"
0x14000b483  mov     edx, 2C7h
0x14000b488  mov     rcx, rdi
0x14000b48b  call    WusaLogDebugEventA
0x14000b490  mov     rax, [rsi+220h]
0x14000b497  mov     edx, 0EA60h; DWORD
0x14000b49c  mov     [rsp+730h+var_708], rax
0x14000b4a1  mov     r9d, 0FFFFh; pszIcon
0x14000b4a7  mov     r8d, r13d; dwCommonButtons
0x14000b4aa  mov     [rsp+730h+var_710], r12; int *
0x14000b4af  lea     ecx, [rdx+0Fh]; dwMessageId
0x14000b4b2  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000b4b7  test    eax, eax
0x14000b4b9  jns     short loc_14000B4CF
0x14000b4bb  lea     r8, aFailedToDispla_3; "Failed to display update-not-installed "...
0x14000b4c2  mov     edx, 2CBh
0x14000b4c7  mov     rcx, rdi
0x14000b4ca  call    WusaLogDebugEventA
0x14000b4cf  mov     ebx, 240007h
0x14000b4d4  jmp     loc_14000B795
0x14000b4d9  cmp     [rsp+730h+var_700], 7
0x14000b4de  jg      loc_14000B73D
0x14000b4e4  cmp     dword ptr [rsp+730h+hMem], r12d
0x14000b4e9  jnz     loc_14000B73D
0x14000b4ef  mov     rdx, [rsi+220h]; unsigned __int16 *
0x14000b4f6  call    ?SetUpdateTitle@AppModule@@QEAAJPEBG@Z; AppModule::SetUpdateTitle(ushort const *)
0x14000b4fb  mov     ebx, eax
0x14000b4fd  test    eax, eax
0x14000b4ff  jns     short loc_14000B512
0x14000b501  lea     r8, aFailedToSetUpd; "Failed to set update title"
0x14000b508  mov     edx, 2E3h
  ... truncated ...
```
