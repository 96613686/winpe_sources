# _dynamic_initializer_for__DirScanConfigTable__

- ea: `0x180004500`
- end: `0x180004c63`
- name: `_dynamic_initializer_for__DirScanConfigTable__`
- size: `1891`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800055d8`
- `0x180017af4`
- `0x1800202a0`
- `0x1800202f4`

## string_xrefs

- `0x180004bfb`: `TempPaths`
- `0x18000495e`: `%systemdrive%\windows.old`
- `0x1800048d9`: `Installer`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
int dynamic_initializer_for__DirScanConfigTable__()
{
  __int64 v0; // rax
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v21; // [rsp+28h] [rbp-51h]
  __int64 v22; // [rsp+28h] [rbp-51h]
  __int64 v23; // [rsp+28h] [rbp-51h]
  __int64 v24; // [rsp+28h] [rbp-51h]
  __int64 v25; // [rsp+28h] [rbp-51h]
  __int64 v26; // [rsp+28h] [rbp-51h]
  __int64 v27; // [rsp+28h] [rbp-51h]
  __int64 v28; // [rsp+28h] [rbp-51h]
  __int64 v29; // [rsp+28h] [rbp-51h]
  __int64 v30; // [rsp+28h] [rbp-51h]
  const wchar_t *v31; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v32[24]; // [rsp+38h] [rbp-41h]
  _BYTE v33[20]; // [rsp+5Ch] [rbp-1Dh]
  _BYTE v34[32]; // [rsp+70h] [rbp-9h] BYREF
  const wchar_t *v35; // [rsp+90h] [rbp+17h] BYREF
  int v36; // [rsp+98h] [rbp+1Fh]
  __int128 v37; // [rsp+9Ch] [rbp+23h]
  int v38; // [rsp+ACh] [rbp+33h]
  _QWORD v39[2]; // [rsp+B0h] [rbp+37h] BYREF
  char v40; // [rsp+C0h] [rbp+47h] BYREF
  const wchar_t *v41; // [rsp+E0h] [rbp+67h] BYREF
  char v42; // [rsp+E8h] [rbp+6Fh] BYREF

  v39[0] = L"Microsoft\\OneNote";
  v39[1] = L"Packages\\Microsoft.SkypeApp_kzf8qxf38zg5c";
  v31 = (const wchar_t *)v39;
  *(_QWORD *)v32 = &v40;
  v0 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34, &v31);
  *(GUID *)&v32[8] = FOLDERID_LocalAppData;
  v35 = L"LocAppData";
  v36 = 0;
  v37 = *(_OWORD *)&v32[4];
  v38 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_LocalAppData, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)DirScanConfigTable,
    5,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v35,
    v0,
    0);
  v41 = L"Skype";
  v31 = (const wchar_t *)&v41;
  *(_QWORD *)v32 = &v42;
  v1 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35, &v31);
  *(GUID *)&v33[4] = FOLDERID_RoamingAppData;
  v31 = L"LocRomData";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_RoamingAppData, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040680,
    5,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v1,
    0);
  v2 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_LocalAppDataLow;
  v31 = L"LocAppDataLow";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_LocalAppDataLow, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_1800406D0,
    5,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v2,
    0);
  v3 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(_OWORD *)&v33[4] = 0;
  v31 = L"ONReg";
  *(_DWORD *)v32 = 2;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040720,
    5,
    (unsigned int)GetONBackupFolderFromRegistry,
    (unsigned int)&v31,
    v3,
    1);
  v4 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(_OWORD *)&v33[4] = 0;
  v31 = L"ONDef";
  *(_DWORD *)v32 = 2;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040770,
    5,
    (unsigned int)GenerateONBackupFolder,
    (unsigned int)&v31,
    v4,
    1);
  v5 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_ProgramData;
  v31 = L"ProgData";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_ProgramData, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_1800407C0,
    6,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v5,
    0);
  v6 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_ProgramFiles;
  v31 = L"ProgFiles";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_ProgramFiles, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040810,
    4,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v6,
    0);
  v7 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_ProgramFilesX64;
  v31 = L"ProgFiles64";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_ProgramFilesX64, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040860,
    4,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v7,
    0);
  v8 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_ProgramFilesX86;
  v31 = L"ProgFiles86";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_ProgramFilesX86, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_1800408B0,
    4,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v8,
    0);
  v9 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_Windows;
  v31 = L"Windows";
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Windows, 12));
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040900,
    3,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v9,
    0);
  v10 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(_OWORD *)&v33[4] = 0;
  *(_DWORD *)v32 = 2;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  LOBYTE(v21) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040950,
    7,
    (unsigned int)GenerateInstallersFolder,
    (unsigned int)&v31,
    v10,
    v21,
    L"Installer",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v41 = L"Users";
  v31 = (const wchar_t *)&v41;
  *(_QWORD *)v32 = &v42;
  v11 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35, &v31);
  *(_DWORD *)v32 = 1;
  *(_DWORD *)&v32[4] = *(_DWORD *)v33;
  LOBYTE(v22) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_1800409A0,
    8,
    (unsigned int)ExpandEnvironmentVarString,
    (unsigned int)&v31,
    v11,
    v22,
    L"Winold",
    *(_QWORD *)v32,
    L"%systemdrive%\\windows.old",
    *(_QWORD *)&v33[12]);
  v12 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_Downloads;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Downloads, 12));
  LOBYTE(v23) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_1800409F0,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v12,
    v23,
    L"Downloads",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v13 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_Documents;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Documents, 12));
  LOBYTE(v24) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040A40,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v13,
    v24,
    L"Docs",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v14 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_Music;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Music, 12));
  LOBYTE(v25) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040A90,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v14,
    v25,
    L"Music",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v15 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_Pictures;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Pictures, 12));
  LOBYTE(v26) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040AE0,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v15,
    v26,
    L"Pics",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v16 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(GUID *)&v33[4] = FOLDERID_Videos;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Videos, 12));
  LOBYTE(v27) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040B30,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v16,
    v27,
    L"Videos",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v17 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(GUID *)&v33[4] = FOLDERID_Desktop;
  *(_DWORD *)v32 = 0;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)FOLDERID_Desktop, 12));
  LOBYTE(v28) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040B80,
    9,
    (unsigned int)GenerateKnownFolder,
    (unsigned int)&v31,
    v17,
    v28,
    L"Desktop",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v18 = std::vector<unsigned short const *>::vector<unsigned short const *>(v34);
  *(_OWORD *)&v33[4] = 0;
  *(_DWORD *)v32 = 2;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  LOBYTE(v29) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040BD0,
    9,
    (unsigned int)GetChkdskRecoveryPath,
    (unsigned int)&v31,
    v18,
    v29,
    L"CHKDSK",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  v19 = std::vector<unsigned short const *>::vector<unsigned short const *>(&v35);
  *(_OWORD *)&v33[4] = 0;
  *(_DWORD *)v32 = 2;
  *(_OWORD *)&v32[4] = *(_OWORD *)v33;
  *(_DWORD *)&v32[20] = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  LOBYTE(v30) = 0;
  DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(
    (unsigned int)qword_180040C20,
    15,
    (unsigned int)GetTempPaths,
    (unsigned int)&v31,
    v19,
    v30,
    L"TempPaths",
    *(_QWORD *)v32,
    (unsigned __int64)(*(_OWORD *)v33 >> 32),
    *(_QWORD *)&v32[16]);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__DirScanConfigTable__);
}

```

## disassembly

```asm
0x180004500  mov     [rsp-8+arg_10], rbx
0x180004505  mov     [rsp-8+arg_18], rsi
0x18000450a  push    rbp
0x18000450b  push    rdi
0x18000450c  push    r14
0x18000450e  lea     rbp, [rsp-47h]
0x180004513  sub     rsp, 0C0h
0x18000451a  lea     rax, aMicrosoftOneno; "Microsoft\\OneNote"
0x180004521  mov     [rbp+57h+var_20], rax
0x180004525  lea     rax, aPackagesMicros; "Packages\\Microsoft.SkypeApp_kzf8qxf38z"...
0x18000452c  mov     [rbp+57h+var_18], rax
0x180004530  lea     rax, [rbp+57h+var_20]
0x180004534  mov     [rbp+57h+var_A0], rax
0x180004538  lea     rax, [rbp+57h+var_10]
0x18000453c  mov     qword ptr [rbp+57h+var_98], rax
0x180004540  lea     rdx, [rbp+57h+var_A0]
0x180004544  lea     rcx, [rbp+57h+var_60]
0x180004548  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@V?$initializer_list@PEBG@1@AEBV?$allocator@PEBG@1@@Z; std::vector<ushort const *>::vector<ushort const *>(std::initializer_list<ushort const *>,std::allocator<ushort const *> const &)
0x18000454d  movups  xmm1, xmmword ptr cs:FOLDERID_LocalAppData.Data1
0x180004554  movups  [rbp+57h+var_98+8], xmm1
0x180004558  lea     rcx, aLocappdata; "LocAppData"
0x18000455f  mov     [rbp+57h+var_40], rcx
0x180004563  xor     r14d, r14d
0x180004566  mov     [rbp+57h+var_38], r14d
0x18000456a  movups  xmm0, [rbp+57h+var_98+4]
0x18000456e  movups  [rbp+57h+var_34], xmm0
0x180004572  psrldq  xmm1, 0Ch
0x180004577  movd    [rbp+57h+var_24], xmm1
0x18000457c  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004581  mov     [rsp+0D0h+var_B0], rax
0x180004586  lea     r9, [rbp+57h+var_40]
0x18000458a  lea     rsi, ?GenerateKnownFolder@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; GenerateKnownFolder(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x180004591  mov     r8, rsi
0x180004594  lea     ebx, [r14+5]
0x180004598  mov     edx, ebx
0x18000459a  lea     rcx, ?DirScanConfigTable@@3V?$array@UDIR_SCAN_CONFIG@@$0BE@@std@@A; std::array<DIR_SCAN_CONFIG,20> DirScanConfigTable
0x1800045a1  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x1800045a6  nop
0x1800045a7  lea     rax, aSkype; "Skype"
0x1800045ae  mov     [rbp+57h+arg_0], rax
0x1800045b2  lea     rax, [rbp+57h+arg_0]
0x1800045b6  mov     [rbp+57h+var_A0], rax
0x1800045ba  lea     rax, [rbp+57h+arg_8]
0x1800045be  mov     qword ptr [rbp+57h+var_98], rax
0x1800045c2  lea     rdx, [rbp+57h+var_A0]
0x1800045c6  lea     rcx, [rbp+57h+var_40]
0x1800045ca  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@V?$initializer_list@PEBG@1@AEBV?$allocator@PEBG@1@@Z; std::vector<ushort const *>::vector<ushort const *>(std::initializer_list<ushort const *>,std::allocator<ushort const *> const &)
0x1800045cf  movups  xmm1, xmmword ptr cs:FOLDERID_RoamingAppData.Data1
0x1800045d6  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x1800045da  lea     rcx, aLocromdata; "LocRomData"
0x1800045e1  mov     [rbp+57h+var_A0], rcx
0x1800045e5  mov     dword ptr [rbp+57h+var_98], r14d
0x1800045e9  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x1800045ed  movups  [rbp+57h+var_98+4], xmm0
0x1800045f1  psrldq  xmm1, 0Ch
0x1800045f6  movd    [rbp+57h+var_84], xmm1
0x1800045fb  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004600  mov     [rsp+0D0h+var_B0], rax
0x180004605  lea     r9, [rbp+57h+var_A0]
0x180004609  mov     r8, rsi
0x18000460c  mov     edx, ebx
0x18000460e  lea     rcx, qword_180040680
0x180004615  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x18000461a  nop
0x18000461b  lea     rcx, [rbp+57h+var_60]
0x18000461f  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x180004624  movups  xmm1, xmmword ptr cs:FOLDERID_LocalAppDataLow.Data1
0x18000462b  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x18000462f  lea     rcx, aLocappdatalow; "LocAppDataLow"
0x180004636  mov     [rbp+57h+var_A0], rcx
0x18000463a  mov     dword ptr [rbp+57h+var_98], r14d
0x18000463e  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004642  movups  [rbp+57h+var_98+4], xmm0
0x180004646  psrldq  xmm1, 0Ch
0x18000464b  movd    [rbp+57h+var_84], xmm1
0x180004650  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004655  mov     [rsp+0D0h+var_B0], rax
0x18000465a  lea     r9, [rbp+57h+var_A0]
0x18000465e  mov     r8, rsi
0x180004661  mov     edx, ebx
0x180004663  lea     rcx, qword_1800406D0
0x18000466a  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x18000466f  nop
0x180004670  lea     rcx, [rbp+57h+var_40]
0x180004674  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x180004679  xorps   xmm1, xmm1
0x18000467c  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x180004680  lea     rcx, aOnreg; "ONReg"
0x180004687  mov     [rbp+57h+var_A0], rcx
0x18000468b  lea     edi, [rbx-3]
0x18000468e  mov     dword ptr [rbp+57h+var_98], edi
0x180004691  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004695  movups  [rbp+57h+var_98+4], xmm0
0x180004699  psrldq  xmm1, 0Ch
0x18000469e  movd    [rbp+57h+var_84], xmm1
0x1800046a3  mov     byte ptr [rsp+0D0h+var_A8], 1
0x1800046a8  mov     [rsp+0D0h+var_B0], rax
0x1800046ad  lea     r9, [rbp+57h+var_A0]
0x1800046b1  lea     r8, ?GetONBackupFolderFromRegistry@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; GetONBackupFolderFromRegistry(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x1800046b8  mov     edx, ebx
0x1800046ba  lea     rcx, qword_180040720
0x1800046c1  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x1800046c6  nop
0x1800046c7  lea     rcx, [rbp+57h+var_60]
0x1800046cb  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800046d0  xorps   xmm1, xmm1
0x1800046d3  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x1800046d7  lea     rcx, aOndef; "ONDef"
0x1800046de  mov     [rbp+57h+var_A0], rcx
0x1800046e2  mov     dword ptr [rbp+57h+var_98], edi
0x1800046e5  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x1800046e9  movups  [rbp+57h+var_98+4], xmm0
0x1800046ed  psrldq  xmm1, 0Ch
0x1800046f2  movd    [rbp+57h+var_84], xmm1
0x1800046f7  mov     byte ptr [rsp+0D0h+var_A8], 1
0x1800046fc  mov     [rsp+0D0h+var_B0], rax
0x180004701  lea     r9, [rbp+57h+var_A0]
0x180004705  lea     r8, ?GenerateONBackupFolder@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; GenerateONBackupFolder(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x18000470c  mov     edx, ebx
0x18000470e  lea     rcx, qword_180040770
0x180004715  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x18000471a  nop
0x18000471b  lea     rcx, [rbp+57h+var_40]
0x18000471f  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x180004724  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramData.Data1
0x18000472b  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x18000472f  lea     rcx, aProgdata; "ProgData"
0x180004736  mov     [rbp+57h+var_A0], rcx
0x18000473a  mov     dword ptr [rbp+57h+var_98], r14d
0x18000473e  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004742  movups  [rbp+57h+var_98+4], xmm0
0x180004746  psrldq  xmm1, 0Ch
0x18000474b  movd    [rbp+57h+var_84], xmm1
0x180004750  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004755  mov     [rsp+0D0h+var_B0], rax
0x18000475a  lea     r9, [rbp+57h+var_A0]
0x18000475e  mov     r8, rsi
0x180004761  lea     edx, [rbx+1]
0x180004764  lea     rcx, qword_1800407C0
0x18000476b  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x180004770  nop
0x180004771  lea     rcx, [rbp+57h+var_60]
0x180004775  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x18000477a  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x180004781  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x180004785  lea     rcx, aProgfiles; "ProgFiles"
0x18000478c  mov     [rbp+57h+var_A0], rcx
0x180004790  mov     dword ptr [rbp+57h+var_98], r14d
0x180004794  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004798  movups  [rbp+57h+var_98+4], xmm0
0x18000479c  psrldq  xmm1, 0Ch
0x1800047a1  movd    [rbp+57h+var_84], xmm1
0x1800047a6  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x1800047ab  mov     [rsp+0D0h+var_B0], rax
0x1800047b0  lea     r9, [rbp+57h+var_A0]
0x1800047b4  mov     r8, rsi
0x1800047b7  lea     ebx, [rdi+2]
0x1800047ba  mov     edx, ebx
0x1800047bc  lea     rcx, qword_180040810
0x1800047c3  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x1800047c8  nop
0x1800047c9  lea     rcx, [rbp+57h+var_40]
0x1800047cd  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800047d2  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x1800047d9  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x1800047dd  lea     rcx, aProgfiles64; "ProgFiles64"
0x1800047e4  mov     [rbp+57h+var_A0], rcx
0x1800047e8  mov     dword ptr [rbp+57h+var_98], r14d
0x1800047ec  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x1800047f0  movups  [rbp+57h+var_98+4], xmm0
0x1800047f4  psrldq  xmm1, 0Ch
0x1800047f9  movd    [rbp+57h+var_84], xmm1
0x1800047fe  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004803  mov     [rsp+0D0h+var_B0], rax
0x180004808  lea     r9, [rbp+57h+var_A0]
0x18000480c  mov     r8, rsi
0x18000480f  mov     edx, ebx
0x180004811  lea     rcx, qword_180040860
0x180004818  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x18000481d  nop
0x18000481e  lea     rcx, [rbp+57h+var_60]
0x180004822  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x180004827  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x18000482e  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x180004832  lea     rcx, aProgfiles86; "ProgFiles86"
0x180004839  mov     [rbp+57h+var_A0], rcx
0x18000483d  mov     dword ptr [rbp+57h+var_98], r14d
0x180004841  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004845  movups  [rbp+57h+var_98+4], xmm0
0x180004849  psrldq  xmm1, 0Ch
0x18000484e  movd    [rbp+57h+var_84], xmm1
0x180004853  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004858  mov     [rsp+0D0h+var_B0], rax
0x18000485d  lea     r9, [rbp+57h+var_A0]
0x180004861  mov     r8, rsi
0x180004864  mov     edx, ebx
0x180004866  lea     rcx, qword_1800408B0
0x18000486d  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x180004872  nop
0x180004873  lea     rcx, [rbp+57h+var_40]
0x180004877  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x18000487c  movups  xmm1, xmmword ptr cs:FOLDERID_Windows.Data1
0x180004883  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x180004887  lea     rcx, aWindows; "Windows"
0x18000488e  mov     [rbp+57h+var_A0], rcx
0x180004892  mov     dword ptr [rbp+57h+var_98], r14d
0x180004896  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x18000489a  movups  [rbp+57h+var_98+4], xmm0
0x18000489e  psrldq  xmm1, 0Ch
0x1800048a3  movd    [rbp+57h+var_84], xmm1
0x1800048a8  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x1800048ad  mov     [rsp+0D0h+var_B0], rax
0x1800048b2  lea     r9, [rbp+57h+var_A0]
0x1800048b6  mov     r8, rsi
0x1800048b9  lea     edx, [rdi+1]
0x1800048bc  lea     rcx, qword_180040900
0x1800048c3  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x1800048c8  nop
0x1800048c9  lea     rcx, [rbp+57h+var_60]
0x1800048cd  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800048d2  xorps   xmm1, xmm1
0x1800048d5  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x1800048d9  lea     rcx, aInstaller; "Installer"
0x1800048e0  mov     [rbp+57h+var_A0], rcx
0x1800048e4  mov     dword ptr [rbp+57h+var_98], edi
0x1800048e7  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x1800048eb  movups  [rbp+57h+var_98+4], xmm0
0x1800048ef  psrldq  xmm1, 0Ch
0x1800048f4  movd    [rbp+57h+var_84], xmm1
0x1800048f9  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x1800048fe  mov     [rsp+0D0h+var_B0], rax
0x180004903  lea     r9, [rbp+57h+var_A0]
0x180004907  lea     r8, ?GenerateInstallersFolder@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; GenerateInstallersFolder(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x18000490e  lea     edx, [rdi+5]
0x180004911  lea     rcx, qword_180040950
0x180004918  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x18000491d  nop
0x18000491e  lea     rax, aUsers; "Users"
0x180004925  mov     [rbp+57h+arg_0], rax
0x180004929  lea     rax, [rbp+57h+arg_0]
0x18000492d  mov     [rbp+57h+var_A0], rax
0x180004931  lea     rax, [rbp+57h+arg_8]
0x180004935  mov     qword ptr [rbp+57h+var_98], rax
0x180004939  lea     rdx, [rbp+57h+var_A0]
0x18000493d  lea     rcx, [rbp+57h+var_40]
0x180004941  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@V?$initializer_list@PEBG@1@AEBV?$allocator@PEBG@1@@Z; std::vector<ushort const *>::vector<ushort const *>(std::initializer_list<ushort const *>,std::allocator<ushort const *> const &)
0x180004946  lea     rcx, aWinold_0; "Winold"
0x18000494d  mov     [rbp+57h+var_A0], rcx
0x180004951  mov     dword ptr [rbp+57h+var_98], 1
0x180004958  mov     ecx, dword ptr [rbp+57h+var_74]
0x18000495b  mov     dword ptr [rbp+57h+var_98+4], ecx
0x18000495e  lea     rcx, Src; "%systemdrive%\\windows.old"
0x180004965  mov     qword ptr [rbp+57h+var_98+8], rcx
0x180004969  mov     rcx, qword ptr [rbp+57h+var_74+0Ch]
0x18000496d  mov     [rbp-31h], rcx
0x180004971  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004976  mov     [rsp+0D0h+var_B0], rax
0x18000497b  lea     r9, [rbp+57h+var_A0]
0x18000497f  lea     r8, ?ExpandEnvironmentVarString@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; ExpandEnvironmentVarString(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x180004986  lea     edx, [rdi+6]
0x180004989  lea     rcx, qword_1800409A0
0x180004990  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x180004995  nop
0x180004996  lea     rcx, [rbp+57h+var_60]
0x18000499a  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x18000499f  movups  xmm1, xmmword ptr cs:FOLDERID_Downloads.Data1
0x1800049a6  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x1800049aa  lea     rcx, aDownloads; "Downloads"
0x1800049b1  mov     [rbp+57h+var_A0], rcx
0x1800049b5  mov     dword ptr [rbp+57h+var_98], r14d
0x1800049b9  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x1800049bd  movups  [rbp+57h+var_98+4], xmm0
0x1800049c1  psrldq  xmm1, 0Ch
0x1800049c6  movd    [rbp+57h+var_84], xmm1
0x1800049cb  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x1800049d0  mov     [rsp+0D0h+var_B0], rax
0x1800049d5  lea     r9, [rbp+57h+var_A0]
0x1800049d9  mov     r8, rsi
0x1800049dc  lea     ebx, [rdi+7]
0x1800049df  mov     edx, ebx
0x1800049e1  lea     rcx, qword_1800409F0
0x1800049e8  call    ??0DIR_SCAN_CONFIG@@QEAA@JP6AJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z0V?$vector@PEBGV?$allocator@PEBG@std@@@3@_N@Z; DIR_SCAN_CONFIG::DIR_SCAN_CONFIG(long,long (*)(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &),FOLDER_NAME_GENERATOR_ARGS,std::vector<ushort const *>,bool)
0x1800049ed  nop
0x1800049ee  lea     rcx, [rbp+57h+var_40]
0x1800049f2  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800049f7  movups  xmm1, xmmword ptr cs:FOLDERID_Documents.Data1
0x1800049fe  movups  xmmword ptr [rbp+57h+var_74+4], xmm1
0x180004a02  lea     rcx, aDocs; "Docs"
0x180004a09  mov     [rbp+57h+var_A0], rcx
0x180004a0d  mov     dword ptr [rbp+57h+var_98], r14d
0x180004a11  movups  xmm0, xmmword ptr [rbp+57h+var_74]
0x180004a15  movups  [rbp+57h+var_98+4], xmm0
0x180004a19  psrldq  xmm1, 0Ch
0x180004a1e  movd    [rbp+57h+var_84], xmm1
0x180004a23  mov     byte ptr [rsp+0D0h+var_A8], r14b
0x180004a28  mov     [rsp+0D0h+var_B0], rax
0x180004a2d  lea     r9, [rbp+57h+var_A0]
0x180004a31  mov     r8, rsi
0x180004a34  mov     edx, ebx
0x180004a36  lea     rcx, qword_180040A40
  ... truncated ...
```
