# VerifyImage(ushort *)

- ea: `0x18002d888`
- end: `0x18002dd8c`
- name: `?VerifyImage@@YAJPEAG@Z`
- size: `1284`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a05fc`

## callees

- `0x180009940`
- `0x18002d888`
- `0x180033f60`
- `0x180034e64`
- `0x1800a0528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dd32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dd32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da4c`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002dc48`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002dc48`
- `WINTRUST!WinVerifyTrust` at `0x18002d9ac`
- `WINTRUST!WinVerifyTrust` at `0x18002d9f8`
- `WINTRUST!WinVerifyTrust` at `0x18002dc8d`
- `WINTRUST!WinVerifyTrust` at `0x18002dcd9`
- `WINTRUST!WinVerifyTrust` at `0x18002d9ac`
- `WINTRUST!WinVerifyTrust` at `0x18002d9f8`
- `WINTRUST!WinVerifyTrust` at `0x18002dc8d`
- `WINTRUST!WinVerifyTrust` at `0x18002dcd9`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002dc6a`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002dc6a`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002daed`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002db47`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002dba0`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002daed`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002db47`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002dba0`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18002da9f`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18002da9f`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002dcf0`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002dcf0`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002dd1e`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002dd1e`

## string_xrefs

- `0x18002da7c`: `VerifyImage - CreateFileW FAILED with error 0x%x`

## pseudocode

```c
__int64 __fastcall VerifyImage(LPCWSTR lpFileName)
{
  __int64 FileW; // rsi
  BYTE *v3; // rdi
  unsigned int v4; // ebx
  LONG v5; // r14d
  int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  BYTE *v10; // rax
  signed int v11; // eax
  DWORD v12; // r8d
  HCATINFO v13; // rax
  void *v14; // r14
  int v15; // eax
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD pWVTData[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  int *v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+90h] [rbp-70h]
  void *v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A8h] [rbp-58h]
  _OWORD v27[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v28; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR *wszCatalogFile; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  BYTE *v31; // [rsp+108h] [rbp+8h]
  DWORD v32; // [rsp+110h] [rbp+10h]
  GUID pgActionID; // [rsp+130h] [rbp+30h] BYREF
  GUID pgSubsystem; // [rsp+140h] [rbp+40h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+150h] [rbp+50h] BYREF
  BYTE pbHash[40]; // [rsp+360h] [rbp+260h] BYREF

  memset_0(pWVTData, 0, 0x58u);
  memset(v27, 0, sizeof(v27));
  memset_0(&v28, 0, 0x48u);
  phCatAdmin = 0;
  pgSubsystem.Data1 = -145692989;
  *(_DWORD *)&pgSubsystem.Data2 = 298924270;
  *(_DWORD *)pgSubsystem.Data4 = -1073683067;
  *(_DWORD *)&pgSubsystem.Data4[4] = -292175281;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  phPrevCatInfo = 0;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  FileW = -1;
  pcbHash = 0;
  v3 = pbHash;
  if ( !lpFileName )
  {
    v4 = -2147024809;
LABEL_41:
    CloseHandle((HANDLE)FileW);
    goto LABEL_42;
  }
  pWVTData[0] = 88;
  v24 = 1;
  v22 = 1;
  v21 = 2;
  v23 = (int *)v27;
  v4 = -2147467263;
  v26 = 16;
  LODWORD(v27[0]) = 32;
  *((_QWORD *)&v27[0] + 1) = lpFileName;
  v5 = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( !v5 )
  {
    v6 = CheckCallerIdentity(v25);
    v4 = v6;
    if ( v6 < 0 )
      _DbgPrintMessage(8, "VerifyImage - The provider that validated the file could not be trusted, error = 0x%x", v6);
  }
  v24 = 2;
  WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( v5 )
  {
    _DbgPrintMessage(1, "VerifyImage - The binary could not be verified as a stand-alone file", v4);
    FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "VerifyImage - CreateFileW FAILED with error 0x%x", v4);
      goto LABEL_38;
    }
    if ( !CryptCATAdminAcquireContext(&phCatAdmin, &pgSubsystem, 0) )
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      _DbgPrintMessage(8, "VerifyImage - CryptCATAdminAcquireContext FAILED with error 0x%x", v4);
      goto LABEL_38;
    }
    pcbHash = 40;
    if ( CryptCATAdminCalcHashFromFileHandle((HANDLE)FileW, &pcbHash, pbHash, 0) )
      goto LABEL_29;
    v9 = GetLastError();
    v4 = v9;
    if ( v9 != 122 )
    {
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      _DbgPrintMessage(8, "VerifyImage - CryptCATAdminCalcHashFromFileHandle FAILED with error 0x%x\n", v4);
      goto LABEL_38;
    }
    pcbHash = 0;
    CryptCATAdminCalcHashFromFileHandle((HANDLE)FileW, &pcbHash, pbHash, 0);
    if ( !pcbHash )
    {
      v4 = -2147024774;
      _DbgPrintMessage(
        8,
        "VerifyImage - CryptCATAdminCalcHashFromFileHandle FAILED to get hash size, error 0x%x",
        2147942522LL);
      goto LABEL_38;
    }
    v10 = (BYTE *)LocalAlloc(0x40u, pcbHash);
    v3 = v10;
    if ( !v10 )
    {
      v4 = -2147024882;
      goto LABEL_38;
    }
    if ( CryptCATAdminCalcHashFromFileHandle((HANDLE)FileW, &pcbHash, v10, 0) )
    {
LABEL_29:
      memset_0(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
      psCatInfo.cbStruct = 524;
      memset_0(&v28, 0, 0x48u);
      v12 = pcbHash;
      v23 = &v28;
      v22 = 2;
      v24 = 1;
      v28 = 72;
      v30 = FileW;
      v31 = v3;
      v32 = pcbHash;
      for ( phPrevCatInfo = 0; ; phPrevCatInfo = v14 )
      {
        v13 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, v3, v12, 0, &phPrevCatInfo);
        v14 = v13;
        if ( !v13 )
        {
          v4 = -2147024891;
          _DbgPrintMessage(8, "VerifyImage - The system catalog that contains file hash was not found");
          goto LABEL_38;
        }
        if ( CryptCATCatalogInfoFromContext(v13, &psCatInfo, 0) )
        {
          wszCatalogFile = psCatInfo.wszCatalogFile;
          if ( !WinVerifyTrust(0, &pgActionID, pWVTData) )
            break;
        }
        v12 = pcbHash;
      }
      v15 = CheckCallerIdentity(v25);
      v4 = v15;
      if ( v15 < 0 )
        _DbgPrintMessage(
          8,
          "VerifyImage - The provider that validated the system catalog could not be trusted, error = 0x%x",
          v15);
      v24 = 2;
      WinVerifyTrust(0, &pgActionID, pWVTData);
      CryptCATAdminReleaseCatalogContext(phCatAdmin, v14, 0);
    }
    else
    {
      v11 = GetLastError();
      v4 = v11;
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      _DbgPrintMessage(8, "VerifyImage - CryptCATAdminCalcHashFromFileHandle FAILED with error 0x%x", v4);
    }
  }
LABEL_38:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  if ( FileW )
    goto LABEL_41;
LABEL_42:
  if ( v3 && v3 != pbHash )
    LocalFree(v3);
  return v4;
}

```

## disassembly

```asm
0x18002d888  mov     [rsp-8+arg_8], rbx
0x18002d88d  mov     [rsp-8+arg_10], rsi
0x18002d892  push    rbp
0x18002d893  push    rdi
0x18002d894  push    r13
0x18002d896  push    r14
0x18002d898  push    r15
0x18002d89a  lea     rbp, [rsp-290h]
0x18002d8a2  sub     rsp, 390h
0x18002d8a9  mov     rax, cs:__security_cookie
0x18002d8b0  xor     rax, rsp
0x18002d8b3  mov     [rbp+2B0h+var_28], rax
0x18002d8ba  mov     r15, rcx
0x18002d8bd  mov     r14d, 58h ; 'X'
0x18002d8c3  mov     r8d, r14d; Size
0x18002d8c6  lea     rcx, [rsp+3B0h+pWVTData]; void *
0x18002d8cb  xor     edx, edx; Val
0x18002d8cd  call    memset_0
0x18002d8d2  xorps   xmm0, xmm0
0x18002d8d5  lea     r8d, [r14-10h]; Size
0x18002d8d9  xor     edx, edx; Val
0x18002d8db  lea     rcx, [rbp+2B0h+var_2D0]; void *
0x18002d8df  movups  [rbp+2B0h+var_2F0], xmm0
0x18002d8e3  movups  [rbp+2B0h+var_2E0], xmm0
0x18002d8e7  call    memset_0
0x18002d8ec  xor     edx, edx; Val
0x18002d8ee  mov     [rsp+3B0h+phCatAdmin], 0
0x18002d8f7  mov     r8d, 20Ch; Size
0x18002d8fd  mov     [rbp+2B0h+pgSubsystem.Data1], 0F750E6C3h
0x18002d904  lea     rcx, [rbp+2B0h+psCatInfo]; void *
0x18002d908  mov     dword ptr [rbp+2B0h+pgSubsystem.Data2], 11D138EEh
0x18002d90f  mov     dword ptr [rbp+2B0h+pgSubsystem.Data4], 0C000E585h
0x18002d916  mov     dword ptr [rbp+2B0h+pgSubsystem.Data4+4], 0EE95C24Fh
0x18002d91d  mov     [rbp+2B0h+pgActionID.Data1], 0AAC56Bh
0x18002d924  mov     dword ptr [rbp+2B0h+pgActionID.Data2], 11D0CD44h
0x18002d92b  mov     dword ptr [rbp+2B0h+pgActionID.Data4], 0C000C28Ch
0x18002d932  mov     dword ptr [rbp+2B0h+pgActionID.Data4+4], 0EE95C24Fh
0x18002d939  mov     [rsp+3B0h+phPrevCatInfo], 0
0x18002d942  call    memset_0
0x18002d947  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002d94b  mov     [rsp+3B0h+pcbHash], 0
0x18002d953  lea     rdi, [rbp+2B0h+pbHash]
0x18002d95a  test    r15, r15
0x18002d95d  jnz     short loc_18002D969
0x18002d95f  mov     ebx, 80070057h
0x18002d964  jmp     loc_18002DD2F
0x18002d969  mov     eax, 1
0x18002d96e  mov     [rsp+3B0h+pWVTData], r14d
0x18002d973  mov     [rbp+2B0h+var_320], eax
0x18002d976  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002d97b  mov     [rbp+2B0h+var_330], eax
0x18002d97e  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002d982  lea     rax, [rbp+2B0h+var_2F0]
0x18002d986  mov     [rsp+3B0h+var_338], 2
0x18002d98f  xor     ecx, ecx; hwnd
0x18002d991  mov     [rbp+2B0h+var_328], rax
0x18002d995  mov     ebx, 80004001h
0x18002d99a  mov     [rbp+2B0h+var_308], 10h
0x18002d9a1  mov     dword ptr [rbp+2B0h+var_2F0], 20h ; ' '
0x18002d9a8  mov     qword ptr [rbp+2B0h+var_2F0+8], r15
0x18002d9ac  call    cs:__imp_WinVerifyTrust
0x18002d9b3  nop     dword ptr [rax+rax+00h]
0x18002d9b8  mov     r14d, eax
0x18002d9bb  mov     r13d, 8
0x18002d9c1  test    eax, eax
0x18002d9c3  jnz     short loc_18002D9E6
0x18002d9c5  mov     rcx, [rbp+2B0h+var_318]; void *
0x18002d9c9  call    ?CheckCallerIdentity@@YAJPEAX@Z; CheckCallerIdentity(void *)
0x18002d9ce  mov     ebx, eax
0x18002d9d0  test    eax, eax
0x18002d9d2  jns     short loc_18002D9E6
0x18002d9d4  mov     r8d, eax
0x18002d9d7  lea     rdx, aVerifyimageThe; "VerifyImage - The provider that validat"...
0x18002d9de  mov     ecx, r13d; int
0x18002d9e1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d9e6  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002d9eb  mov     [rbp+2B0h+var_320], 2
0x18002d9f2  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002d9f6  xor     ecx, ecx; hwnd
0x18002d9f8  call    cs:__imp_WinVerifyTrust
0x18002d9ff  nop     dword ptr [rax+rax+00h]
0x18002da04  test    r14d, r14d
0x18002da07  jz      loc_18002DD12
0x18002da0d  mov     r14d, 1
0x18002da13  lea     rdx, aVerifyimageThe_2; "VerifyImage - The binary could not be v"...
0x18002da1a  mov     ecx, r14d; int
0x18002da1d  mov     r8d, ebx
0x18002da20  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002da25  mov     [rsp+3B0h+hTemplateFile], 0; hTemplateFile
0x18002da2e  xor     r9d, r9d; lpSecurityAttributes
0x18002da31  mov     [rsp+3B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002da39  mov     r8d, r14d; dwShareMode
0x18002da3c  mov     edx, 80000000h; dwDesiredAccess
0x18002da41  mov     [rsp+3B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002da49  mov     rcx, r15; lpFileName
0x18002da4c  call    cs:__imp_CreateFileW
0x18002da53  nop     dword ptr [rax+rax+00h]
0x18002da58  mov     rsi, rax
0x18002da5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002da5f  jnz     short loc_18002DA93
0x18002da61  call    cs:__imp_GetLastError
0x18002da68  nop     dword ptr [rax+rax+00h]
0x18002da6d  mov     ebx, eax
0x18002da6f  test    eax, eax
0x18002da71  jle     short loc_18002DA7C
0x18002da73  movzx   ebx, ax
0x18002da76  or      ebx, 80070000h
0x18002da7c  lea     rdx, aVerifyimageCre; "VerifyImage - CreateFileW FAILED with e"...
0x18002da83  mov     r8d, ebx
0x18002da86  mov     ecx, r13d; int
0x18002da89  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002da8e  jmp     loc_18002DD12
0x18002da93  xor     r8d, r8d; dwFlags
0x18002da96  lea     rdx, [rbp+2B0h+pgSubsystem]; pgSubsystem
0x18002da9a  lea     rcx, [rsp+3B0h+phCatAdmin]; phCatAdmin
0x18002da9f  call    cs:__imp_CryptCATAdminAcquireContext
0x18002daa6  nop     dword ptr [rax+rax+00h]
0x18002daab  test    eax, eax
0x18002daad  jnz     short loc_18002DAD3
0x18002daaf  call    cs:__imp_GetLastError
0x18002dab6  nop     dword ptr [rax+rax+00h]
0x18002dabb  mov     ebx, eax
0x18002dabd  test    eax, eax
0x18002dabf  jle     short loc_18002DACA
0x18002dac1  movzx   ebx, ax
0x18002dac4  or      ebx, 80070000h
0x18002daca  lea     rdx, aVerifyimageCry_2; "VerifyImage - CryptCATAdminAcquireConte"...
0x18002dad1  jmp     short loc_18002DA83
0x18002dad3  xor     r9d, r9d; dwFlags
0x18002dad6  mov     [rsp+3B0h+pcbHash], 28h ; '('
0x18002dade  lea     r8, [rbp+2B0h+pbHash]; pbHash
0x18002dae5  mov     rcx, rsi; hFile
0x18002dae8  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002daed  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002daf4  nop     dword ptr [rax+rax+00h]
0x18002daf9  test    eax, eax
0x18002dafb  jnz     loc_18002DBD7
0x18002db01  call    cs:__imp_GetLastError
0x18002db08  nop     dword ptr [rax+rax+00h]
0x18002db0d  mov     ebx, eax
0x18002db0f  cmp     eax, 7Ah ; 'z'
0x18002db12  jz      short loc_18002DB2D
0x18002db14  test    eax, eax
0x18002db16  jle     short loc_18002DB21
0x18002db18  movzx   ebx, ax
0x18002db1b  or      ebx, 80070000h
0x18002db21  lea     rdx, aVerifyimageCry_0; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002db28  jmp     loc_18002DA83
0x18002db2d  xor     r9d, r9d; dwFlags
0x18002db30  mov     [rsp+3B0h+pcbHash], 0
0x18002db38  lea     r8, [rbp+2B0h+pbHash]; pbHash
0x18002db3f  mov     rcx, rsi; hFile
0x18002db42  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002db47  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002db4e  nop     dword ptr [rax+rax+00h]
0x18002db53  mov     eax, [rsp+3B0h+pcbHash]
0x18002db57  test    eax, eax
0x18002db59  jnz     short loc_18002DB6C
0x18002db5b  mov     ebx, 8007007Ah
0x18002db60  lea     rdx, aVerifyimageCry_1; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002db67  jmp     loc_18002DA83
0x18002db6c  mov     rdx, rax; uBytes
0x18002db6f  mov     ecx, 40h ; '@'; uFlags
0x18002db74  call    cs:__imp_LocalAlloc
0x18002db7b  nop     dword ptr [rax+rax+00h]
0x18002db80  mov     rdi, rax
0x18002db83  test    rax, rax
0x18002db86  jnz     short loc_18002DB92
0x18002db88  mov     ebx, 8007000Eh
0x18002db8d  jmp     loc_18002DD12
0x18002db92  xor     r9d, r9d; dwFlags
0x18002db95  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002db9a  mov     r8, rax; pbHash
0x18002db9d  mov     rcx, rsi; hFile
0x18002dba0  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002dba7  nop     dword ptr [rax+rax+00h]
0x18002dbac  test    eax, eax
0x18002dbae  jnz     short loc_18002DBD7
0x18002dbb0  call    cs:__imp_GetLastError
0x18002dbb7  nop     dword ptr [rax+rax+00h]
0x18002dbbc  mov     ebx, eax
0x18002dbbe  test    eax, eax
0x18002dbc0  jle     short loc_18002DBCB
0x18002dbc2  movzx   ebx, ax
0x18002dbc5  or      ebx, 80070000h
0x18002dbcb  lea     rdx, aVerifyimageCry; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002dbd2  jmp     loc_18002DA83
0x18002dbd7  xor     edx, edx; Val
0x18002dbd9  lea     rcx, [rbp+2B0h+psCatInfo.wszCatalogFile]; void *
0x18002dbdd  mov     r8d, 208h; Size
0x18002dbe3  call    memset_0
0x18002dbe8  mov     ebx, 48h ; 'H'
0x18002dbed  mov     [rbp+2B0h+psCatInfo.cbStruct], 20Ch
0x18002dbf4  mov     r8d, ebx; Size
0x18002dbf7  lea     rcx, [rbp+2B0h+var_2D0]; void *
0x18002dbfb  xor     edx, edx; Val
0x18002dbfd  call    memset_0
0x18002dc02  mov     r8d, [rsp+3B0h+pcbHash]; cbHash
0x18002dc07  lea     rax, [rbp+2B0h+var_2D0]
0x18002dc0b  lea     r15d, [rbx-46h]
0x18002dc0f  mov     [rbp+2B0h+var_328], rax
0x18002dc13  mov     [rbp+2B0h+var_330], r15d
0x18002dc17  mov     [rbp+2B0h+var_320], r14d
0x18002dc1b  mov     [rbp+2B0h+var_2D0], ebx
0x18002dc1e  mov     [rbp+2B0h+var_2B0], rsi
0x18002dc22  mov     [rbp+2B0h+var_2A8], rdi
0x18002dc26  mov     [rbp+2B0h+var_2A0], r8d
0x18002dc2a  mov     [rsp+3B0h+phPrevCatInfo], 0
0x18002dc33  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002dc38  lea     rax, [rsp+3B0h+phPrevCatInfo]
0x18002dc3d  xor     r9d, r9d; dwFlags
0x18002dc40  mov     qword ptr [rsp+3B0h+dwCreationDisposition], rax; phPrevCatInfo
0x18002dc45  mov     rdx, rdi; pbHash
0x18002dc48  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18002dc4f  nop     dword ptr [rax+rax+00h]
0x18002dc54  mov     r14, rax
0x18002dc57  test    rax, rax
0x18002dc5a  jz      loc_18002DCFE
0x18002dc60  xor     r8d, r8d; dwFlags
0x18002dc63  lea     rdx, [rbp+2B0h+psCatInfo]; psCatInfo
0x18002dc67  mov     rcx, rax; hCatInfo
0x18002dc6a  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18002dc71  nop     dword ptr [rax+rax+00h]
0x18002dc76  test    eax, eax
0x18002dc78  jz      short loc_18002DC9D
0x18002dc7a  lea     rax, [rbp+2B0h+psCatInfo.wszCatalogFile]
0x18002dc7e  xor     ecx, ecx; hwnd
0x18002dc80  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002dc85  mov     [rbp+2B0h+var_2C8], rax
0x18002dc89  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002dc8d  call    cs:__imp_WinVerifyTrust
0x18002dc94  nop     dword ptr [rax+rax+00h]
0x18002dc99  test    eax, eax
0x18002dc9b  jz      short loc_18002DCA9
0x18002dc9d  mov     r8d, [rsp+3B0h+pcbHash]
0x18002dca2  mov     [rsp+3B0h+phPrevCatInfo], r14
0x18002dca7  jmp     short loc_18002DC33
0x18002dca9  mov     rcx, [rbp+2B0h+var_318]; void *
0x18002dcad  call    ?CheckCallerIdentity@@YAJPEAX@Z; CheckCallerIdentity(void *)
0x18002dcb2  mov     ebx, eax
0x18002dcb4  test    eax, eax
0x18002dcb6  jns     short loc_18002DCCA
0x18002dcb8  mov     r8d, eax
0x18002dcbb  lea     rdx, aVerifyimageThe_1; "VerifyImage - The provider that validat"...
0x18002dcc2  mov     ecx, r13d; int
0x18002dcc5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dcca  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002dccf  mov     [rbp+2B0h+var_320], r15d
0x18002dcd3  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002dcd7  xor     ecx, ecx; hwnd
0x18002dcd9  call    cs:__imp_WinVerifyTrust
0x18002dce0  nop     dword ptr [rax+rax+00h]
0x18002dce5  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002dcea  xor     r8d, r8d; dwFlags
0x18002dced  mov     rdx, r14; hCatInfo
0x18002dcf0  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18002dcf7  nop     dword ptr [rax+rax+00h]
0x18002dcfc  jmp     short loc_18002DD12
0x18002dcfe  lea     rdx, aVerifyimageThe_0; "VerifyImage - The system catalog that c"...
0x18002dd05  mov     ecx, r13d; int
0x18002dd08  mov     ebx, 80070005h
0x18002dd0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002dd12  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002dd17  test    rcx, rcx
0x18002dd1a  jz      short loc_18002DD2A
0x18002dd1c  xor     edx, edx; dwFlags
0x18002dd1e  call    cs:__imp_CryptCATAdminReleaseContext
0x18002dd25  nop     dword ptr [rax+rax+00h]
0x18002dd2a  test    rsi, rsi
0x18002dd2d  jz      short loc_18002DD3E
0x18002dd2f  mov     rcx, rsi; hObject
0x18002dd32  call    cs:__imp_CloseHandle
0x18002dd39  nop     dword ptr [rax+rax+00h]
0x18002dd3e  test    rdi, rdi
0x18002dd41  jz      short loc_18002DD5E
0x18002dd43  lea     rax, [rbp+2B0h+pbHash]
0x18002dd4a  cmp     rdi, rax
0x18002dd4d  jz      short loc_18002DD5E
0x18002dd4f  mov     rcx, rdi; hMem
0x18002dd52  call    cs:__imp_LocalFree
0x18002dd59  nop     dword ptr [rax+rax+00h]
0x18002dd5e  mov     eax, ebx
0x18002dd60  mov     rcx, [rbp+2B0h+var_28]
0x18002dd67  xor     rcx, rsp; StackCookie
0x18002dd6a  call    __security_check_cookie
0x18002dd6f  lea     r11, [rsp+3B0h+var_20]
0x18002dd77  mov     rbx, [r11+38h]
0x18002dd7b  mov     rsi, [r11+40h]
0x18002dd7f  mov     rsp, r11
0x18002dd82  pop     r15
0x18002dd84  pop     r14
0x18002dd86  pop     r13
0x18002dd88  pop     rdi
0x18002dd89  pop     rbp
0x18002dd8a  retn
```
