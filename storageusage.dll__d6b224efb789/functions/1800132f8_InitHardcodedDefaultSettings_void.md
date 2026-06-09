# InitHardcodedDefaultSettings(void)

- ea: `0x1800132f8`
- end: `0x1800139fe`
- name: `?InitHardcodedDefaultSettings@@YAXXZ`
- size: `1798`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180012340`

## callees

- `0x1800132f8`
- `0x180013b30`
- `0x180013b48`
- `0x180016954`

## string_xrefs

- `0x1800135c1`: `ProgramData`
- `0x18001360c`: `Installers`
- `0x180013721`: `CleanupPlugins`
- `0x18001376c`: `BackupConfig`
- `0x180013862`: `StorsvcServiceStatus`
- `0x1800138b2`: `TempPaths`

## pseudocode

```c
void InitHardcodedDefaultSettings(void)
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 v2; // rcx
  char v3; // bl
  bool v4; // al
  __int64 v5; // rcx
  char v6; // bl
  bool v7; // al
  __int64 v8; // rcx
  _BOOL8 v9; // rcx
  bool v10; // al
  _BOOL8 v11; // rcx
  bool v12; // al
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  _BOOL8 v16; // rcx
  bool v17; // al
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  _BYTE v26[12]; // [rsp+20h] [rbp-49h]
  int v27; // [rsp+30h] [rbp-39h] BYREF
  const wchar_t *v28; // [rsp+38h] [rbp-31h]
  _BYTE v29[12]; // [rsp+40h] [rbp-29h]
  _BYTE v30[12]; // [rsp+4Ch] [rbp-1Dh]
  int v31; // [rsp+58h] [rbp-11h]
  bool v32; // [rsp+5Ch] [rbp-Dh]
  void *v33; // [rsp+60h] [rbp-9h]
  __int64 (__fastcall *v34)(); // [rsp+68h] [rbp-1h]
  int v35; // [rsp+70h] [rbp+7h]
  char v36; // [rsp+74h] [rbp+Bh]

  if ( *((_QWORD *)&STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 1) == (_QWORD)STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings )
  {
    v31 = 8;
    v27 = 0;
    v28 = L"StorageUsage";
    *(_DWORD *)v29 = 0;
    *(_DWORD *)&v30[8] = 1;
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_QWORD *)v30 = 0x100000000LL;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = StorageUsageScan;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v0, &v27);
    v27 = 1;
    v28 = L"StoragePolicy";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000000LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &GetStoragePolicyInfo;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v1, &v27);
    *(_DWORD *)v29 = 0;
    v28 = L"SyncRoot";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v27 = 2;
    *(_QWORD *)v30 = 0x100000000LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = AnalyzeSyncRoots;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v2, &v27);
    if ( IsClassicDesktop() || (v3 = 0, IsContainer()) )
      v3 = 1;
    v28 = L"Windir";
    v26[8] = 0;
    *(_DWORD *)&v26[4] = 504;
    *(_DWORD *)&v29[8] = *(_DWORD *)&v26[8];
    v27 = 3;
    *(_QWORD *)v29 = 0x1F800000002LL;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v4 = IsClassicDesktop();
    v32 = v3;
    v31 = v4 + 2;
    v35 = 168;
    v33 = &ScanWinDir;
    v34 = ReadWindirSettings;
    v36 = 0;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v5, &v27);
    if ( IsClassicDesktop() || (v6 = 0, IsContainer()) )
      v6 = 1;
    v28 = L"ProgramFiles";
    *(_DWORD *)v26 = 0;
    *(_DWORD *)&v29[8] = *(_DWORD *)&v26[8];
    v27 = 4;
    *(_QWORD *)v29 = *(_QWORD *)v26;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v7 = IsClassicDesktop();
    v32 = v6;
    v31 = v7 + 2;
    v33 = &ScanProgramFiles;
    v34 = 0;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v8, &v27);
    if ( IsClassicDesktop() || (v10 = IsContainer(), LOBYTE(v9) = 0, v10) )
      LOBYTE(v9) = 1;
    v27 = 5;
    v28 = L"AppData";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v33 = &ScanAppData;
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000001LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = 2;
    v32 = v9;
    v34 = 0;
    v35 = 168;
    v36 = 0;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v9, &v27);
    if ( IsClassicDesktop() || (v12 = IsContainer(), LOBYTE(v11) = 0, v12) )
      LOBYTE(v11) = 1;
    v27 = 6;
    v28 = L"ProgramData";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v33 = &ScanProgramData;
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v31 = 2;
    v32 = v11;
    v34 = 0;
    v35 = 168;
    v36 = 0;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v11, &v27);
    v27 = 7;
    v28 = L"Installers";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v31 = 4;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &InstallersHashScan;
    v35 = 336;
    v36 = 0;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v13, &v27);
    v27 = 8;
    v28 = L"WindowsOld";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000001LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &ScanWindowsOldDir;
    v35 = 0x7FFFFFFF;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v14, &v27);
    v27 = 9;
    v28 = L"FilesMetadata";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000001LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &ScanFilesMetadata;
    v35 = 168;
    v36 = 0;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v15, &v27);
    if ( IsClassicDesktop() || (v17 = IsContainer(), LOBYTE(v16) = 0, v17) )
      LOBYTE(v16) = 1;
    v27 = 10;
    v28 = L"CleanupPlugins";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v33 = &ScanCleanupPlugins;
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v31 = -1;
    v32 = v16;
    v34 = 0;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v16, &v27);
    v27 = 11;
    v28 = L"BackupConfig";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000001LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &GetBackupConfigInfo;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v18, &v27);
    v27 = 12;
    v28 = L"KnownFoldersDriveInfo";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000000LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &ScanKFDriveInfo;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v19, &v27);
    v27 = 13;
    v28 = L"StorageToastRegKeys";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0x100000001LL;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = &ScanStorageToastRegKeys;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v20, &v27);
    v27 = 14;
    v28 = L"StorsvcServiceStatus";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 1;
    *(_QWORD *)&v30[4] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = GetStorSvcStatus;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v21, &v27);
    v27 = 15;
    v28 = L"TempPaths";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 0;
    *(_QWORD *)&v30[4] = 1;
    v31 = 2;
    v32 = IsContainer();
    v34 = 0;
    v33 = &ScanTempPaths;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v22, &v27);
    v27 = 16;
    v28 = L"TagKnownFolders";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    *(_DWORD *)v29 = 0;
    *(_QWORD *)v30 = 0;
    *(_DWORD *)&v30[8] = 1;
    v31 = -1;
    v32 = IsClassicDesktop();
    v34 = 0;
    v33 = TagKnownFolders;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v23, &v27);
    v27 = 17;
    v28 = L"EnumerateVolumes";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v33 = &EnumerateVolumes;
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 0;
    *(_QWORD *)&v30[4] = 1;
    v31 = -1;
    v32 = 0;
    v34 = 0;
    v35 = 24;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v24, &v27);
    v27 = 18;
    v28 = L"FragAnalysis";
    *(_QWORD *)&v29[4] = *(_QWORD *)&v26[4];
    v33 = TriggerDefragAnalysis;
    *(_DWORD *)v29 = 0;
    *(_DWORD *)v30 = 0;
    *(_QWORD *)&v30[4] = 1;
    v31 = -1;
    v32 = 0;
    v34 = 0;
    v35 = 168;
    v36 = 1;
    std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(v25, &v27);
  }
}

```

## disassembly

```asm
0x1800132f8  push    rbp
0x1800132fa  push    rbx
0x1800132fb  push    rsi
0x1800132fc  push    rdi
0x1800132fd  push    r12
0x1800132ff  push    r13
0x180013301  push    r14
0x180013303  push    r15
0x180013305  lea     rbp, [rsp-1Fh]
0x18001330a  sub     rsp, 88h
0x180013311  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A+8; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x180013318  cmp     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18001331f  jnz     loc_1800139EA
0x180013325  xor     edi, edi
0x180013327  mov     [rbp+57h+var_68], 8
0x18001332e  lea     rax, aStorageusage; "StorageUsage"
0x180013335  mov     [rbp+57h+var_90], edi
0x180013338  mov     [rbp+57h+var_88], rax
0x18001333c  mov     rax, [rbp+57h+var_A0+4]
0x180013340  lea     esi, [rdi+1]
0x180013343  mov     dword ptr [rbp+57h+var_80], edi
0x180013346  mov     dword ptr [rbp+57h+var_74+4], esi
0x180013349  mov     [rbp+57h+var_6C], esi
0x18001334c  mov     [rbp+57h+var_80+4], rax
0x180013350  mov     dword ptr [rbp+57h+var_74], edi
0x180013353  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013358  mov     [rbp+57h+var_64], al
0x18001335b  lea     r13d, [rdi+18h]
0x18001335f  lea     rax, ?StorageUsageScan@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; StorageUsageScan(void *,SCAN_FUNCTION_ARGS,bool &)
0x180013366  mov     [rbp+57h+var_58], rdi
0x18001336a  lea     rdx, [rbp+57h+var_90]
0x18001336e  mov     [rbp+57h+var_60], rax
0x180013372  mov     [rbp+57h+var_50], r13d
0x180013376  mov     [rbp+57h+var_4C], sil
0x18001337a  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x18001337f  lea     rax, aStoragepolicy; "StoragePolicy"
0x180013386  mov     [rbp+57h+var_90], esi
0x180013389  mov     [rbp+57h+var_88], rax
0x18001338d  or      r12d, 0FFFFFFFFh
0x180013391  mov     rax, [rbp+57h+var_A0+4]
0x180013395  mov     [rbp+57h+var_80+4], rax
0x180013399  mov     dword ptr [rbp+57h+var_80], edi
0x18001339c  mov     dword ptr [rbp+57h+var_74], edi
0x18001339f  mov     dword ptr [rbp+57h+var_74+4], esi
0x1800133a2  mov     [rbp+57h+var_6C], esi
0x1800133a5  mov     [rbp+57h+var_68], r12d
0x1800133a9  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x1800133ae  mov     [rbp+57h+var_64], al
0x1800133b1  lea     rdx, [rbp+57h+var_90]
0x1800133b5  lea     rax, ?GetStoragePolicyInfo@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; GetStoragePolicyInfo(void *,SCAN_FUNCTION_ARGS,bool &)
0x1800133bc  mov     [rbp+57h+var_58], rdi
0x1800133c0  mov     [rbp+57h+var_60], rax
0x1800133c4  mov     [rbp+57h+var_50], r13d
0x1800133c8  mov     [rbp+57h+var_4C], sil
0x1800133cc  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x1800133d1  lea     rax, aSyncroot; "SyncRoot"
0x1800133d8  mov     dword ptr [rbp+57h+var_80], edi
0x1800133db  mov     [rbp+57h+var_88], rax
0x1800133df  lea     r14d, [rdi+2]
0x1800133e3  mov     rax, [rbp+57h+var_A0+4]
0x1800133e7  mov     [rbp+57h+var_80+4], rax
0x1800133eb  mov     [rbp+57h+var_90], r14d
0x1800133ef  mov     dword ptr [rbp+57h+var_74], edi
0x1800133f2  mov     dword ptr [rbp+57h+var_74+4], esi
0x1800133f5  mov     [rbp+57h+var_6C], esi
0x1800133f8  mov     [rbp+57h+var_68], r12d
0x1800133fc  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013401  mov     [rbp+57h+var_64], al
0x180013404  lea     rdx, [rbp+57h+var_90]
0x180013408  lea     rax, ?AnalyzeSyncRoots@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; AnalyzeSyncRoots(void *,SCAN_FUNCTION_ARGS,bool &)
0x18001340f  mov     [rbp+57h+var_58], rdi
0x180013413  mov     [rbp+57h+var_60], rax
0x180013417  mov     [rbp+57h+var_50], r13d
0x18001341b  mov     [rbp+57h+var_4C], sil
0x18001341f  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x180013424  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013429  test    al, al
0x18001342b  jnz     short loc_180013439
0x18001342d  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x180013432  mov     bl, dil
0x180013435  test    al, al
0x180013437  jz      short loc_18001343C
0x180013439  mov     bl, sil
0x18001343c  mov     eax, cs:dword_1800350E0
0x180013442  mov     cl, cs:byte_1800350E4
0x180013448  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18001344b  movzx   eax, word ptr [rbp+57h+var_98+1]
0x18001344f  mov     word ptr [rbp+57h+var_98+1], ax
0x180013453  mov     al, byte ptr [rbp+57h+var_98+3]
0x180013456  mov     byte ptr [rbp+57h+var_98+3], al
0x180013459  lea     rax, aWindir; "Windir"
0x180013460  mov     [rbp+57h+var_88], rax
0x180013464  mov     byte ptr [rbp+57h+var_98], cl
0x180013467  mov     eax, [rbp+57h+var_98]
0x18001346a  mov     dword ptr [rbp+57h+var_A0], r14d
0x18001346e  movsd   xmm0, [rbp+57h+var_A0]
0x180013473  mov     [rbp+57h+var_78], eax
0x180013476  mov     [rbp+57h+var_90], 3
0x18001347d  movsd   [rbp+57h+var_80], xmm0
0x180013482  mov     dword ptr [rbp+57h+var_74], esi
0x180013485  mov     [rbp+57h+var_74+4], rsi
0x180013489  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x18001348e  movzx   eax, al
0x180013491  lea     rdx, [rbp+57h+var_90]
0x180013495  add     eax, r14d
0x180013498  mov     [rbp+57h+var_64], bl
0x18001349b  mov     [rbp+57h+var_68], eax
0x18001349e  mov     r15d, 0A8h
0x1800134a4  lea     rax, ?ScanWinDir@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanWinDir(void *,SCAN_FUNCTION_ARGS,bool &)
0x1800134ab  mov     [rbp+57h+var_50], r15d
0x1800134af  mov     [rbp+57h+var_60], rax
0x1800134b3  lea     rax, ?ReadWindirSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z; ReadWindirSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &)
0x1800134ba  mov     [rbp+57h+var_58], rax
0x1800134be  mov     [rbp+57h+var_4C], dil
0x1800134c2  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x1800134c7  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x1800134cc  test    al, al
0x1800134ce  jnz     short loc_1800134DC
0x1800134d0  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x1800134d5  mov     bl, dil
0x1800134d8  test    al, al
0x1800134da  jz      short loc_1800134DF
0x1800134dc  mov     bl, sil
0x1800134df  mov     rax, [rbp+57h+var_A0+4]
0x1800134e3  mov     [rbp+57h+var_A0+4], rax
0x1800134e7  lea     rax, aProgramfiles; "ProgramFiles"
0x1800134ee  mov     [rbp+57h+var_88], rax
0x1800134f2  mov     eax, [rbp+57h+var_98]
0x1800134f5  mov     dword ptr [rbp+57h+var_A0], edi
0x1800134f8  movsd   xmm0, [rbp+57h+var_A0]
0x1800134fd  mov     [rbp+57h+var_78], eax
0x180013500  mov     [rbp+57h+var_90], 4
0x180013507  movsd   [rbp+57h+var_80], xmm0
0x18001350c  mov     dword ptr [rbp+57h+var_74], esi
0x18001350f  mov     [rbp+57h+var_74+4], rsi
0x180013513  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013518  movzx   eax, al
0x18001351b  lea     rdx, [rbp+57h+var_90]
0x18001351f  add     eax, r14d
0x180013522  mov     [rbp+57h+var_64], bl
0x180013525  mov     [rbp+57h+var_68], eax
0x180013528  lea     rax, ?ScanProgramFiles@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanProgramFiles(void *,SCAN_FUNCTION_ARGS,bool &)
0x18001352f  mov     [rbp+57h+var_60], rax
0x180013533  mov     [rbp+57h+var_58], rdi
0x180013537  mov     [rbp+57h+var_50], r15d
0x18001353b  mov     [rbp+57h+var_4C], sil
0x18001353f  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x180013544  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013549  test    al, al
0x18001354b  jnz     short loc_180013559
0x18001354d  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x180013552  mov     cl, dil
0x180013555  test    al, al
0x180013557  jz      short loc_18001355C
0x180013559  mov     cl, sil
0x18001355c  lea     rax, aAppdata; "AppData"
0x180013563  mov     [rbp+57h+var_90], 5
0x18001356a  mov     [rbp+57h+var_88], rax
0x18001356e  lea     rdx, [rbp+57h+var_90]
0x180013572  mov     rax, [rbp+57h+var_A0+4]
0x180013576  mov     [rbp+57h+var_80+4], rax
0x18001357a  lea     rax, ?ScanAppData@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanAppData(void *,SCAN_FUNCTION_ARGS,bool &)
0x180013581  mov     [rbp+57h+var_60], rax
0x180013585  mov     dword ptr [rbp+57h+var_80], edi
0x180013588  mov     dword ptr [rbp+57h+var_74], esi
0x18001358b  mov     dword ptr [rbp+57h+var_74+4], esi
0x18001358e  mov     [rbp+57h+var_6C], esi
0x180013591  mov     [rbp+57h+var_68], r14d
0x180013595  mov     [rbp+57h+var_64], cl
0x180013598  mov     [rbp+57h+var_58], rdi
0x18001359c  mov     [rbp+57h+var_50], r15d
0x1800135a0  mov     [rbp+57h+var_4C], dil
0x1800135a4  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x1800135a9  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x1800135ae  test    al, al
0x1800135b0  jnz     short loc_1800135BE
0x1800135b2  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x1800135b7  mov     cl, dil
0x1800135ba  test    al, al
0x1800135bc  jz      short loc_1800135C1
0x1800135be  mov     cl, sil
0x1800135c1  lea     rax, aProgramdata; "ProgramData"
0x1800135c8  mov     [rbp+57h+var_90], 6
0x1800135cf  mov     [rbp+57h+var_88], rax
0x1800135d3  lea     rdx, [rbp+57h+var_90]
0x1800135d7  mov     rax, [rbp+57h+var_A0+4]
0x1800135db  mov     [rbp+57h+var_80+4], rax
0x1800135df  lea     rax, ?ScanProgramData@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanProgramData(void *,SCAN_FUNCTION_ARGS,bool &)
0x1800135e6  mov     [rbp+57h+var_60], rax
0x1800135ea  mov     dword ptr [rbp+57h+var_80], edi
0x1800135ed  mov     dword ptr [rbp+57h+var_74], esi
0x1800135f0  mov     [rbp+57h+var_74+4], rsi
0x1800135f4  mov     [rbp+57h+var_68], r14d
0x1800135f8  mov     [rbp+57h+var_64], cl
0x1800135fb  mov     [rbp+57h+var_58], rdi
0x1800135ff  mov     [rbp+57h+var_50], r15d
0x180013603  mov     [rbp+57h+var_4C], dil
0x180013607  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x18001360c  lea     rax, aInstallers; "Installers"
0x180013613  mov     [rbp+57h+var_90], 7
0x18001361a  mov     [rbp+57h+var_88], rax
0x18001361e  mov     rax, [rbp+57h+var_A0+4]
0x180013622  mov     [rbp+57h+var_80+4], rax
0x180013626  mov     dword ptr [rbp+57h+var_80], edi
0x180013629  mov     dword ptr [rbp+57h+var_74], esi
0x18001362c  mov     [rbp+57h+var_74+4], rsi
0x180013630  mov     [rbp+57h+var_68], 4
0x180013637  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x18001363c  mov     [rbp+57h+var_64], al
0x18001363f  lea     rdx, [rbp+57h+var_90]
0x180013643  lea     rax, ?InstallersHashScan@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; InstallersHashScan(void *,SCAN_FUNCTION_ARGS,bool &)
0x18001364a  mov     [rbp+57h+var_58], rdi
0x18001364e  mov     [rbp+57h+var_60], rax
0x180013652  mov     [rbp+57h+var_50], 150h
0x180013659  mov     [rbp+57h+var_4C], dil
0x18001365d  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x180013662  lea     rax, aWindowsold; "WindowsOld"
0x180013669  mov     [rbp+57h+var_90], 8
0x180013670  mov     [rbp+57h+var_88], rax
0x180013674  mov     rax, [rbp+57h+var_A0+4]
0x180013678  mov     [rbp+57h+var_80+4], rax
0x18001367c  mov     dword ptr [rbp+57h+var_80], edi
0x18001367f  mov     dword ptr [rbp+57h+var_74], esi
0x180013682  mov     dword ptr [rbp+57h+var_74+4], esi
0x180013685  mov     [rbp+57h+var_6C], esi
0x180013688  mov     [rbp+57h+var_68], r12d
0x18001368c  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x180013691  mov     [rbp+57h+var_64], al
0x180013694  lea     rdx, [rbp+57h+var_90]
0x180013698  lea     rax, ?ScanWindowsOldDir@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanWindowsOldDir(void *,SCAN_FUNCTION_ARGS,bool &)
0x18001369f  mov     [rbp+57h+var_58], rdi
0x1800136a3  mov     [rbp+57h+var_60], rax
0x1800136a7  mov     [rbp+57h+var_50], 7FFFFFFFh
0x1800136ae  mov     [rbp+57h+var_4C], sil
0x1800136b2  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x1800136b7  lea     rax, aFilesmetadata; "FilesMetadata"
0x1800136be  mov     [rbp+57h+var_90], 9
0x1800136c5  mov     [rbp+57h+var_88], rax
0x1800136c9  mov     rax, [rbp+57h+var_A0+4]
0x1800136cd  mov     [rbp+57h+var_80+4], rax
0x1800136d1  mov     dword ptr [rbp+57h+var_80], edi
0x1800136d4  mov     dword ptr [rbp+57h+var_74], esi
0x1800136d7  mov     dword ptr [rbp+57h+var_74+4], esi
0x1800136da  mov     [rbp+57h+var_6C], esi
0x1800136dd  mov     [rbp+57h+var_68], r12d
0x1800136e1  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x1800136e6  mov     [rbp+57h+var_64], al
0x1800136e9  lea     rdx, [rbp+57h+var_90]
0x1800136ed  lea     rax, ?ScanFilesMetadata@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanFilesMetadata(void *,SCAN_FUNCTION_ARGS,bool &)
0x1800136f4  mov     [rbp+57h+var_58], rdi
0x1800136f8  mov     [rbp+57h+var_60], rax
0x1800136fc  mov     [rbp+57h+var_50], r15d
0x180013700  mov     [rbp+57h+var_4C], dil
0x180013704  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x180013709  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x18001370e  test    al, al
0x180013710  jnz     short loc_18001371E
0x180013712  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x180013717  mov     cl, dil
0x18001371a  test    al, al
0x18001371c  jz      short loc_180013721
0x18001371e  mov     cl, sil
0x180013721  lea     rax, aCleanupplugins; "CleanupPlugins"
0x180013728  mov     [rbp+57h+var_90], 0Ah
0x18001372f  mov     [rbp+57h+var_88], rax
0x180013733  lea     rdx, [rbp+57h+var_90]
0x180013737  mov     rax, [rbp+57h+var_A0+4]
0x18001373b  mov     [rbp+57h+var_80+4], rax
0x18001373f  lea     rax, ?ScanCleanupPlugins@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; ScanCleanupPlugins(void *,SCAN_FUNCTION_ARGS,bool &)
0x180013746  mov     [rbp+57h+var_60], rax
0x18001374a  mov     dword ptr [rbp+57h+var_80], edi
0x18001374d  mov     dword ptr [rbp+57h+var_74], esi
0x180013750  mov     [rbp+57h+var_74+4], rsi
0x180013754  mov     [rbp+57h+var_68], r12d
0x180013758  mov     [rbp+57h+var_64], cl
0x18001375b  mov     [rbp+57h+var_58], rdi
0x18001375f  mov     [rbp+57h+var_50], r15d
0x180013763  mov     [rbp+57h+var_4C], sil
0x180013767  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x18001376c  lea     rax, aBackupconfig; "BackupConfig"
0x180013773  mov     [rbp+57h+var_90], 0Bh
0x18001377a  mov     [rbp+57h+var_88], rax
0x18001377e  mov     rax, [rbp+57h+var_A0+4]
0x180013782  mov     [rbp+57h+var_80+4], rax
0x180013786  mov     dword ptr [rbp+57h+var_80], edi
0x180013789  mov     dword ptr [rbp+57h+var_74], esi
0x18001378c  mov     dword ptr [rbp+57h+var_74+4], esi
0x18001378f  mov     [rbp+57h+var_6C], esi
0x180013792  mov     [rbp+57h+var_68], r12d
0x180013796  call    ?IsClassicDesktop@@YA_NXZ; IsClassicDesktop(void)
0x18001379b  mov     [rbp+57h+var_64], al
0x18001379e  lea     rdx, [rbp+57h+var_90]
0x1800137a2  lea     rax, ?GetBackupConfigInfo@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z; GetBackupConfigInfo(void *,SCAN_FUNCTION_ARGS,bool &)
0x1800137a9  mov     [rbp+57h+var_58], rdi
0x1800137ad  mov     [rbp+57h+var_60], rax
0x1800137b1  mov     [rbp+57h+var_50], r15d
0x1800137b5  mov     [rbp+57h+var_4C], sil
0x1800137b9  call    ?push_back@?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@QEAAX$$QEAVSTORAGE_USAGE_SCAN_CONFIG@@@Z; std::vector<STORAGE_USAGE_SCAN_CONFIG>::push_back(STORAGE_USAGE_SCAN_CONFIG &&)
0x1800137be  lea     rax, aKnownfoldersdr; "KnownFoldersDriveInfo"
0x1800137c5  mov     [rbp+57h+var_90], 0Ch
  ... truncated ...
```
