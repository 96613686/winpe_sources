# VerifyImage(ushort *)

- ea: `0x18002c044`
- end: `0x18002c4cf`
- name: `?VerifyImage@@YAJPEAG@Z`
- size: `1163`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18009c398`

## callees

- `0x18000a210`
- `0x18002c044`
- `0x1800321f0`
- `0x1800330c4`
- `0x18009c2d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c20b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c20b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c482`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c2fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c49c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c49c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c1fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c1fc`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002c3bc`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002c3bc`
- `WINTRUST!WinVerifyTrust` at `0x18002c168`
- `WINTRUST!WinVerifyTrust` at `0x18002c1ae`
- `WINTRUST!WinVerifyTrust` at `0x18002c3f5`
- `WINTRUST!WinVerifyTrust` at `0x18002c43b`
- `WINTRUST!WinVerifyTrust` at `0x18002c168`
- `WINTRUST!WinVerifyTrust` at `0x18002c1ae`
- `WINTRUST!WinVerifyTrust` at `0x18002c3f5`
- `WINTRUST!WinVerifyTrust` at `0x18002c43b`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002c3d8`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002c3d8`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c285`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c2d3`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c320`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c285`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c2d3`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002c320`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18002c243`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18002c243`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002c44c`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002c44c`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002c474`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002c474`

## string_xrefs

- `0x18002c220`: `VerifyImage - CreateFileW FAILED with error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18002c044  mov     [rsp-8+arg_8], rbx
0x18002c049  mov     [rsp-8+arg_10], rsi
0x18002c04e  push    rbp
0x18002c04f  push    rdi
0x18002c050  push    r13
0x18002c052  push    r14
0x18002c054  push    r15
0x18002c056  lea     rbp, [rsp-290h]
0x18002c05e  sub     rsp, 390h
0x18002c065  mov     rax, cs:__security_cookie
0x18002c06c  xor     rax, rsp
0x18002c06f  mov     [rbp+2B0h+var_28], rax
0x18002c076  mov     r15, rcx
0x18002c079  mov     r14d, 58h ; 'X'
0x18002c07f  mov     r8d, r14d; Size
0x18002c082  lea     rcx, [rsp+3B0h+pWVTData]; void *
0x18002c087  xor     edx, edx; Val
0x18002c089  call    memset_0
0x18002c08e  xorps   xmm0, xmm0
0x18002c091  lea     r8d, [r14-10h]; Size
0x18002c095  xor     edx, edx; Val
0x18002c097  lea     rcx, [rbp+2B0h+var_2D0]; void *
0x18002c09b  movups  [rbp+2B0h+var_2F0], xmm0
0x18002c09f  movups  [rbp+2B0h+var_2E0], xmm0
0x18002c0a3  call    memset_0
0x18002c0a8  xor     edx, edx; Val
0x18002c0aa  mov     [rsp+3B0h+phCatAdmin], 0
0x18002c0b3  mov     r8d, 20Ch; Size
0x18002c0b9  mov     [rbp+2B0h+pgSubsystem.Data1], 0F750E6C3h
0x18002c0c0  lea     rcx, [rbp+2B0h+psCatInfo]; void *
0x18002c0c4  mov     dword ptr [rbp+2B0h+pgSubsystem.Data2], 11D138EEh
0x18002c0cb  mov     dword ptr [rbp+2B0h+pgSubsystem.Data4], 0C000E585h
0x18002c0d2  mov     dword ptr [rbp+2B0h+pgSubsystem.Data4+4], 0EE95C24Fh
0x18002c0d9  mov     [rbp+2B0h+pgActionID.Data1], 0AAC56Bh
0x18002c0e0  mov     dword ptr [rbp+2B0h+pgActionID.Data2], 11D0CD44h
0x18002c0e7  mov     dword ptr [rbp+2B0h+pgActionID.Data4], 0C000C28Ch
0x18002c0ee  mov     dword ptr [rbp+2B0h+pgActionID.Data4+4], 0EE95C24Fh
0x18002c0f5  mov     [rsp+3B0h+phPrevCatInfo], 0
0x18002c0fe  call    memset_0
0x18002c103  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c107  mov     [rsp+3B0h+pcbHash], 0
0x18002c10f  lea     rdi, [rbp+2B0h+pbHash]
0x18002c116  test    r15, r15
0x18002c119  jnz     short loc_18002C125
0x18002c11b  mov     ebx, 80070057h
0x18002c120  jmp     loc_18002C47F
0x18002c125  mov     eax, 1
0x18002c12a  mov     [rsp+3B0h+pWVTData], r14d
0x18002c12f  mov     [rbp+2B0h+var_320], eax
0x18002c132  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002c137  mov     [rbp+2B0h+var_330], eax
0x18002c13a  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002c13e  lea     rax, [rbp+2B0h+var_2F0]
0x18002c142  mov     [rsp+3B0h+var_338], 2
0x18002c14b  xor     ecx, ecx; hwnd
0x18002c14d  mov     [rbp+2B0h+var_328], rax
0x18002c151  mov     ebx, 80004001h
0x18002c156  mov     [rbp+2B0h+var_308], 10h
0x18002c15d  mov     dword ptr [rbp+2B0h+var_2F0], 20h ; ' '
0x18002c164  mov     qword ptr [rbp+2B0h+var_2F0+8], r15
0x18002c168  call    cs:__imp_WinVerifyTrust
0x18002c16e  mov     r14d, eax
0x18002c171  mov     r13d, 8
0x18002c177  test    eax, eax
0x18002c179  jnz     short loc_18002C19C
0x18002c17b  mov     rcx, [rbp+2B0h+var_318]; void *
0x18002c17f  call    ?CheckCallerIdentity@@YAJPEAX@Z; CheckCallerIdentity(void *)
0x18002c184  mov     ebx, eax
0x18002c186  test    eax, eax
0x18002c188  jns     short loc_18002C19C
0x18002c18a  mov     r8d, eax
0x18002c18d  lea     rdx, aVerifyimageThe; "VerifyImage - The provider that validat"...
0x18002c194  mov     ecx, r13d; int
0x18002c197  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c19c  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002c1a1  mov     [rbp+2B0h+var_320], 2
0x18002c1a8  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002c1ac  xor     ecx, ecx; hwnd
0x18002c1ae  call    cs:__imp_WinVerifyTrust
0x18002c1b4  test    r14d, r14d
0x18002c1b7  jz      loc_18002C468
0x18002c1bd  mov     r14d, 1
0x18002c1c3  lea     rdx, aVerifyimageThe_2; "VerifyImage - The binary could not be v"...
0x18002c1ca  mov     ecx, r14d; int
0x18002c1cd  mov     r8d, ebx
0x18002c1d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c1d5  mov     [rsp+3B0h+hTemplateFile], 0; hTemplateFile
0x18002c1de  xor     r9d, r9d; lpSecurityAttributes
0x18002c1e1  mov     [rsp+3B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002c1e9  mov     r8d, r14d; dwShareMode
0x18002c1ec  mov     edx, 80000000h; dwDesiredAccess
0x18002c1f1  mov     [rsp+3B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c1f9  mov     rcx, r15; lpFileName
0x18002c1fc  call    cs:__imp_CreateFileW
0x18002c202  mov     rsi, rax
0x18002c205  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c209  jnz     short loc_18002C237
0x18002c20b  call    cs:__imp_GetLastError
0x18002c211  mov     ebx, eax
0x18002c213  test    eax, eax
0x18002c215  jle     short loc_18002C220
0x18002c217  movzx   ebx, ax
0x18002c21a  or      ebx, 80070000h
0x18002c220  lea     rdx, aVerifyimageCre; "VerifyImage - CreateFileW FAILED with e"...
0x18002c227  mov     r8d, ebx
0x18002c22a  mov     ecx, r13d; int
0x18002c22d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c232  jmp     loc_18002C468
0x18002c237  xor     r8d, r8d; dwFlags
0x18002c23a  lea     rdx, [rbp+2B0h+pgSubsystem]; pgSubsystem
0x18002c23e  lea     rcx, [rsp+3B0h+phCatAdmin]; phCatAdmin
0x18002c243  call    cs:__imp_CryptCATAdminAcquireContext
0x18002c249  test    eax, eax
0x18002c24b  jnz     short loc_18002C26B
0x18002c24d  call    cs:__imp_GetLastError
0x18002c253  mov     ebx, eax
0x18002c255  test    eax, eax
0x18002c257  jle     short loc_18002C262
0x18002c259  movzx   ebx, ax
0x18002c25c  or      ebx, 80070000h
0x18002c262  lea     rdx, aVerifyimageCry_2; "VerifyImage - CryptCATAdminAcquireConte"...
0x18002c269  jmp     short loc_18002C227
0x18002c26b  xor     r9d, r9d; dwFlags
0x18002c26e  mov     [rsp+3B0h+pcbHash], 28h ; '('
0x18002c276  lea     r8, [rbp+2B0h+pbHash]; pbHash
0x18002c27d  mov     rcx, rsi; hFile
0x18002c280  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002c285  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002c28b  test    eax, eax
0x18002c28d  jnz     loc_18002C34B
0x18002c293  call    cs:__imp_GetLastError
0x18002c299  mov     ebx, eax
0x18002c29b  cmp     eax, 7Ah ; 'z'
0x18002c29e  jz      short loc_18002C2B9
0x18002c2a0  test    eax, eax
0x18002c2a2  jle     short loc_18002C2AD
0x18002c2a4  movzx   ebx, ax
0x18002c2a7  or      ebx, 80070000h
0x18002c2ad  lea     rdx, aVerifyimageCry_0; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002c2b4  jmp     loc_18002C227
0x18002c2b9  xor     r9d, r9d; dwFlags
0x18002c2bc  mov     [rsp+3B0h+pcbHash], 0
0x18002c2c4  lea     r8, [rbp+2B0h+pbHash]; pbHash
0x18002c2cb  mov     rcx, rsi; hFile
0x18002c2ce  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002c2d3  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002c2d9  mov     eax, [rsp+3B0h+pcbHash]
0x18002c2dd  test    eax, eax
0x18002c2df  jnz     short loc_18002C2F2
0x18002c2e1  mov     ebx, 8007007Ah
0x18002c2e6  lea     rdx, aVerifyimageCry_1; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002c2ed  jmp     loc_18002C227
0x18002c2f2  mov     rdx, rax; uBytes
0x18002c2f5  mov     ecx, 40h ; '@'; uFlags
0x18002c2fa  call    cs:__imp_LocalAlloc
0x18002c300  mov     rdi, rax
0x18002c303  test    rax, rax
0x18002c306  jnz     short loc_18002C312
0x18002c308  mov     ebx, 8007000Eh
0x18002c30d  jmp     loc_18002C468
0x18002c312  xor     r9d, r9d; dwFlags
0x18002c315  lea     rdx, [rsp+3B0h+pcbHash]; pcbHash
0x18002c31a  mov     r8, rax; pbHash
0x18002c31d  mov     rcx, rsi; hFile
0x18002c320  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002c326  test    eax, eax
0x18002c328  jnz     short loc_18002C34B
0x18002c32a  call    cs:__imp_GetLastError
0x18002c330  mov     ebx, eax
0x18002c332  test    eax, eax
0x18002c334  jle     short loc_18002C33F
0x18002c336  movzx   ebx, ax
0x18002c339  or      ebx, 80070000h
0x18002c33f  lea     rdx, aVerifyimageCry; "VerifyImage - CryptCATAdminCalcHashFrom"...
0x18002c346  jmp     loc_18002C227
0x18002c34b  xor     edx, edx; Val
0x18002c34d  lea     rcx, [rbp+2B0h+psCatInfo.wszCatalogFile]; void *
0x18002c351  mov     r8d, 208h; Size
0x18002c357  call    memset_0
0x18002c35c  mov     ebx, 48h ; 'H'
0x18002c361  mov     [rbp+2B0h+psCatInfo.cbStruct], 20Ch
0x18002c368  mov     r8d, ebx; Size
0x18002c36b  lea     rcx, [rbp+2B0h+var_2D0]; void *
0x18002c36f  xor     edx, edx; Val
0x18002c371  call    memset_0
0x18002c376  mov     r8d, [rsp+3B0h+pcbHash]; cbHash
0x18002c37b  lea     rax, [rbp+2B0h+var_2D0]
0x18002c37f  lea     r15d, [rbx-46h]
0x18002c383  mov     [rbp+2B0h+var_328], rax
0x18002c387  mov     [rbp+2B0h+var_330], r15d
0x18002c38b  mov     [rbp+2B0h+var_320], r14d
0x18002c38f  mov     [rbp+2B0h+var_2D0], ebx
0x18002c392  mov     [rbp+2B0h+var_2B0], rsi
0x18002c396  mov     [rbp+2B0h+var_2A8], rdi
0x18002c39a  mov     [rbp+2B0h+var_2A0], r8d
0x18002c39e  mov     [rsp+3B0h+phPrevCatInfo], 0
0x18002c3a7  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002c3ac  lea     rax, [rsp+3B0h+phPrevCatInfo]
0x18002c3b1  xor     r9d, r9d; dwFlags
0x18002c3b4  mov     qword ptr [rsp+3B0h+dwCreationDisposition], rax; phPrevCatInfo
0x18002c3b9  mov     rdx, rdi; pbHash
0x18002c3bc  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18002c3c2  mov     r14, rax
0x18002c3c5  test    rax, rax
0x18002c3c8  jz      loc_18002C454
0x18002c3ce  xor     r8d, r8d; dwFlags
0x18002c3d1  lea     rdx, [rbp+2B0h+psCatInfo]; psCatInfo
0x18002c3d5  mov     rcx, rax; hCatInfo
0x18002c3d8  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18002c3de  test    eax, eax
0x18002c3e0  jz      short loc_18002C3FF
0x18002c3e2  lea     rax, [rbp+2B0h+psCatInfo.wszCatalogFile]
0x18002c3e6  xor     ecx, ecx; hwnd
0x18002c3e8  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002c3ed  mov     [rbp+2B0h+var_2C8], rax
0x18002c3f1  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002c3f5  call    cs:__imp_WinVerifyTrust
0x18002c3fb  test    eax, eax
0x18002c3fd  jz      short loc_18002C40B
0x18002c3ff  mov     r8d, [rsp+3B0h+pcbHash]
0x18002c404  mov     [rsp+3B0h+phPrevCatInfo], r14
0x18002c409  jmp     short loc_18002C3A7
0x18002c40b  mov     rcx, [rbp+2B0h+var_318]; void *
0x18002c40f  call    ?CheckCallerIdentity@@YAJPEAX@Z; CheckCallerIdentity(void *)
0x18002c414  mov     ebx, eax
0x18002c416  test    eax, eax
0x18002c418  jns     short loc_18002C42C
0x18002c41a  mov     r8d, eax
0x18002c41d  lea     rdx, aVerifyimageThe_1; "VerifyImage - The provider that validat"...
0x18002c424  mov     ecx, r13d; int
0x18002c427  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c42c  lea     r8, [rsp+3B0h+pWVTData]; pWVTData
0x18002c431  mov     [rbp+2B0h+var_320], r15d
0x18002c435  lea     rdx, [rbp+2B0h+pgActionID]; pgActionID
0x18002c439  xor     ecx, ecx; hwnd
0x18002c43b  call    cs:__imp_WinVerifyTrust
0x18002c441  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002c446  xor     r8d, r8d; dwFlags
0x18002c449  mov     rdx, r14; hCatInfo
0x18002c44c  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18002c452  jmp     short loc_18002C468
0x18002c454  lea     rdx, aVerifyimageThe_0; "VerifyImage - The system catalog that c"...
0x18002c45b  mov     ecx, r13d; int
0x18002c45e  mov     ebx, 80070005h
0x18002c463  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c468  mov     rcx, [rsp+3B0h+phCatAdmin]; hCatAdmin
0x18002c46d  test    rcx, rcx
0x18002c470  jz      short loc_18002C47A
0x18002c472  xor     edx, edx; dwFlags
0x18002c474  call    cs:__imp_CryptCATAdminReleaseContext
0x18002c47a  test    rsi, rsi
0x18002c47d  jz      short loc_18002C488
0x18002c47f  mov     rcx, rsi; hObject
0x18002c482  call    cs:__imp_CloseHandle
0x18002c488  test    rdi, rdi
0x18002c48b  jz      short loc_18002C4A2
0x18002c48d  lea     rax, [rbp+2B0h+pbHash]
0x18002c494  cmp     rdi, rax
0x18002c497  jz      short loc_18002C4A2
0x18002c499  mov     rcx, rdi; hMem
0x18002c49c  call    cs:__imp_LocalFree
0x18002c4a2  mov     eax, ebx
0x18002c4a4  mov     rcx, [rbp+2B0h+var_28]
0x18002c4ab  xor     rcx, rsp; StackCookie
0x18002c4ae  call    __security_check_cookie
0x18002c4b3  lea     r11, [rsp+3B0h+var_20]
0x18002c4bb  mov     rbx, [r11+38h]
0x18002c4bf  mov     rsi, [r11+40h]
0x18002c4c3  mov     rsp, r11
0x18002c4c6  pop     r15
0x18002c4c8  pop     r14
0x18002c4ca  pop     r13
0x18002c4cc  pop     rdi
0x18002c4cd  pop     rbp
0x18002c4ce  retn
```
