# CTemplateDownloader::_CleanupDownloadedTemplates(void)

- ea: `0x1801adddc`
- end: `0x1801ae0bb`
- name: `?_CleanupDownloadedTemplates@CTemplateDownloader@@AEAAXXZ`
- size: `735`
- prototype: `void __fastcall(CTemplateDownloader *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801aafa4`

## callees

- `0x18000b7e8`
- `0x18001f3c0`
- `0x180027ee4`
- `0x180038274`
- `0x180074b74`
- `0x1800887f8`
- `0x18013d330`
- `0x18013df8c`
- `0x1801aa954`
- `0x1801aaa28`
- `0x1801ad614`
- `0x1801ad6a8`
- `0x1801adddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1801ade1b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1801ade1b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801adec1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801adfd7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801adec1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801adfd7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801adfa4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801adfa4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801adf91`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801adf91`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801adeff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801adeff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801ae002`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801ae002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae076`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801ade92`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801ade92`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801adf23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801adf23`

## string_xrefs

- `0x1801adeaa`: `*.dll`

## pseudocode

```c
void __fastcall CTemplateDownloader::_CleanupDownloadedTemplates(RTL_SRWLOCK *this)
{
  _QWORD *v2; // rbx
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rsi
  HANDLE FirstFile; // rax
  int v6; // ebx
  __int64 v7; // rdx
  bool v8; // sf
  unsigned __int64 v9; // r14
  const unsigned __int16 *v10; // r8
  unsigned __int64 i; // rsi
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v18 = (unsigned __int64)&this[20] & -(__int64)(TryAcquireSRWLockExclusive(this + 20) != 0);
  if ( v18 )
  {
    v2 = 0;
    ppszPath = 0;
    v3 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v16 = 0;
    v17 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    v16 = -1;
    v17 = -1;
    v4 = 1000;
    if ( SHGetKnownFolderPath(&FOLDERID_SearchTemplates, 0x8000u, 0, &ppszPath) >= 0
      && PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.dll") >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      hFindFile = 0;
      FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
      if ( (int)ResultFromWin32Handle(FirstFile, &hFindFile) >= 0 )
      {
        do
        {
          v13 = 0;
          PathRemoveExtensionW(FindFileData.cFileName);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v13);
          v6 = Microsoft::WRL::Details::MakeAndInitialize<CTemplateFile,CTemplateFile,unsigned short (&)[260],_FILETIME &>(
                 &v13,
                 FindFileData.cFileName,
                 &FindFileData.ftLastWriteTime);
          if ( v6 >= 0 )
          {
            v14 = v13;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v14);
            v6 = CTSimpleArray<Microsoft::WRL::ComPtr<CTemplateFile>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CTemplateFile>>>::_AddSortedEx<CCompareTemplatesByTime,Microsoft::WRL::ComPtr<CTemplateFile> &&>(
                   &v19,
                   v7,
                   &v14);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v14);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v13);
        }
        while ( v6 >= 0 && FindNextFileW(hFindFile, &FindFileData) );
        FindClose(hFindFile);
        v3 = v20;
        v8 = v6 < 0;
        v2 = v19;
        if ( !v8 )
        {
          v9 = 1000;
          if ( v20 > 0x3E8 )
          {
            do
            {
              if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, *(PCWSTR *)(v2[v9] + 16LL)) >= 0
                && StringCchCatW(pszPathOut, 0x104u, L".dll") >= 0 )
              {
                DeleteFileW(pszPathOut);
              }
              ++v9;
            }
            while ( v9 < v3 );
          }
        }
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v18);
    wil::AcquireSRWLockExclusive(&hFindFile, &this[21]);
    if ( v3 > 0x3E8 )
    {
      do
        TemplateDownloadHelpers::RemoveTemplateFromArray(
          (TemplateDownloadHelpers *)&this[22],
          *(struct CSimpleCaseInsensitiveOrdinalStringArray **)(v2[v4++] + 16LL),
          v10);
      while ( v4 < v3 );
    }
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&hFindFile);
    if ( v2 )
    {
      for ( i = 0; i < v3; ++i )
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v2[i]);
      CoTaskMemFree(v2);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v18);
}

```

## disassembly

```asm
0x1801adddc  mov     [rsp-8+arg_8], rbx
0x1801adde1  mov     [rsp-8+arg_10], rsi
0x1801adde6  push    rbp
0x1801adde7  push    rdi
0x1801adde8  push    r13
0x1801addea  push    r14
0x1801addec  push    r15
0x1801addee  lea     rbp, [rsp-400h]
0x1801addf6  sub     rsp, 500h
0x1801addfd  mov     rax, cs:__security_cookie
0x1801ade04  xor     rax, rsp
0x1801ade07  mov     [rbp+420h+var_30], rax
0x1801ade0e  lea     rbx, [rcx+0A0h]
0x1801ade15  mov     r15, rcx
0x1801ade18  mov     rcx, rbx; SRWLock
0x1801ade1b  call    cs:__imp_TryAcquireSRWLockExclusive
0x1801ade21  neg     al
0x1801ade23  sbb     rdx, rdx
0x1801ade26  and     rdx, rbx
0x1801ade29  mov     [rsp+520h+var_4C0], rdx
0x1801ade2e  jz      loc_1801AE086
0x1801ade34  xor     ebx, ebx
0x1801ade36  mov     [rsp+520h+ppszPath], 0
0x1801ade3f  xor     edi, edi
0x1801ade41  mov     [rsp+520h+var_4B8], rbx
0x1801ade46  lea     rcx, [rsp+520h+ppszPath]
0x1801ade4b  mov     [rsp+520h+var_4B0], rdi
0x1801ade50  mov     [rsp+520h+var_4A8], rbx
0x1801ade55  mov     [rbp+420h+var_4A0], rbx
0x1801ade59  mov     [rsp+520h+var_4D0], 0
0x1801ade62  mov     [rsp+520h+var_4C8], 0
0x1801ade6b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ade70  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ade74  lea     r9, [rsp+520h+ppszPath]; ppszPath
0x1801ade79  xor     r8d, r8d; hToken
0x1801ade7c  mov     [rsp+520h+var_4D0], rax
0x1801ade81  mov     edx, 8000h; dwFlags
0x1801ade86  mov     [rsp+520h+var_4C8], rax
0x1801ade8b  lea     rcx, FOLDERID_SearchTemplates; rfid
0x1801ade92  call    cs:__imp_SHGetKnownFolderPath
0x1801ade98  mov     esi, 3E8h
0x1801ade9d  test    eax, eax
0x1801ade9f  js      loc_1801AE010
0x1801adea5  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1801adeaa  lea     r9, aDll; "*.dll"
0x1801adeb1  mov     r13d, 104h
0x1801adeb7  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1801adebe  mov     edx, r13d; cchPathOut
0x1801adec1  call    cs:__imp_PathCchCombine
0x1801adec7  test    eax, eax
0x1801adec9  js      loc_1801AE010
0x1801adecf  xor     edx, edx; Val
0x1801aded1  lea     rcx, [rbp+420h+FindFileData]; void *
0x1801aded5  mov     r8d, 250h; Size
0x1801adedb  call    memset_0
0x1801adee0  xor     r9d, r9d; fSearchOp
0x1801adee3  mov     [rsp+520h+dwAdditionalFlags], ebx; dwAdditionalFlags
0x1801adee7  lea     r8, [rbp+420h+FindFileData]; lpFindFileData
0x1801adeeb  mov     [rsp+520h+hFindFile], rbx
0x1801adef0  lea     edx, [rbx+1]; fInfoLevelId
0x1801adef3  mov     [rsp+520h+lpSearchFilter], rbx; lpSearchFilter
0x1801adef8  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x1801adeff  call    cs:__imp_FindFirstFileExW
0x1801adf05  mov     rcx, rax; void *
0x1801adf08  lea     rdx, [rsp+520h+hFindFile]; void **
0x1801adf0d  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801adf12  test    eax, eax
0x1801adf14  js      loc_1801AE010
0x1801adf1a  lea     rcx, [rbp+420h+pszPath]; pszPath
0x1801adf1e  mov     [rsp+520h+var_4E8], rdi
0x1801adf23  call    cs:__imp_PathRemoveExtensionW
0x1801adf29  lea     rcx, [rsp+520h+var_4E8]
0x1801adf2e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801adf33  lea     r8, [rbp+420h+var_47C]
0x1801adf37  lea     rdx, [rbp+420h+pszPath]
0x1801adf3b  lea     rcx, [rsp+520h+var_4E8]
0x1801adf40  call    ??$MakeAndInitialize@VCTemplateFile@@V1@AEAY0BAE@GAEAU_FILETIME@@@Details@WRL@Microsoft@@YAJPEAPEAVCTemplateFile@@AEAY0BAE@GAEAU_FILETIME@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CTemplateFile,CTemplateFile,ushort (&)[260],_FILETIME &>(CTemplateFile * *,ushort (&)[260],_FILETIME &)
0x1801adf45  mov     ebx, eax
0x1801adf47  test    eax, eax
0x1801adf49  js      short loc_1801ADF7A
0x1801adf4b  mov     rax, [rsp+520h+var_4E8]
0x1801adf50  lea     rcx, [rsp+520h+var_4E0]
0x1801adf55  mov     [rsp+520h+var_4E0], rax
0x1801adf5a  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1801adf5f  lea     r8, [rsp+520h+var_4E0]
0x1801adf64  lea     rcx, [rsp+520h+var_4B8]
0x1801adf69  call    ??$_AddSortedEx@VCCompareTemplatesByTime@@$$QEAV?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@@@QEAAJAEBVCCompareTemplatesByTime@@$$QEAV?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CTemplateFile>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CTemplateFile>>>::_AddSortedEx<CCompareTemplatesByTime,Microsoft::WRL::ComPtr<CTemplateFile> &&>(CCompareTemplatesByTime const &,Microsoft::WRL::ComPtr<CTemplateFile> &&,unsigned __int64 *)
0x1801adf6e  lea     rcx, [rsp+520h+var_4E0]
0x1801adf73  mov     ebx, eax
0x1801adf75  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801adf7a  lea     rcx, [rsp+520h+var_4E8]
0x1801adf7f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801adf84  test    ebx, ebx
0x1801adf86  js      short loc_1801ADF9F
0x1801adf88  mov     rcx, [rsp+520h+hFindFile]; hFindFile
0x1801adf8d  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x1801adf91  call    cs:__imp_FindNextFileW
0x1801adf97  test    eax, eax
0x1801adf99  jnz     loc_1801ADF1A
0x1801adf9f  mov     rcx, [rsp+520h+hFindFile]; hFindFile
0x1801adfa4  call    cs:__imp_FindClose
0x1801adfaa  mov     rdi, [rsp+520h+var_4B0]
0x1801adfaf  test    ebx, ebx
0x1801adfb1  mov     rbx, [rsp+520h+var_4B8]
0x1801adfb6  js      short loc_1801AE010
0x1801adfb8  mov     r14, rsi
0x1801adfbb  cmp     rdi, rsi
0x1801adfbe  jbe     short loc_1801AE010
0x1801adfc0  mov     r9, [rbx+r14*8]
0x1801adfc4  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1801adfcb  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1801adfd0  mov     rdx, r13; cchPathOut
0x1801adfd3  mov     r9, [r9+10h]; pszMore
0x1801adfd7  call    cs:__imp_PathCchCombine
0x1801adfdd  test    eax, eax
0x1801adfdf  js      short loc_1801AE008
0x1801adfe1  lea     r8, aDll_0; ".dll"
0x1801adfe8  mov     rdx, r13; unsigned __int64
0x1801adfeb  lea     rcx, [rbp+420h+pszPathOut]; unsigned __int16 *
0x1801adff2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801adff7  test    eax, eax
0x1801adff9  js      short loc_1801AE008
0x1801adffb  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x1801ae002  call    cs:__imp_DeleteFileW
0x1801ae008  inc     r14
0x1801ae00b  cmp     r14, rdi
0x1801ae00e  jb      short loc_1801ADFC0
0x1801ae010  lea     rcx, [rsp+520h+var_4C0]; this
0x1801ae015  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801ae01a  lea     rdx, [r15+0A8h]
0x1801ae021  lea     rcx, [rsp+520h+hFindFile]
0x1801ae026  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801ae02b  cmp     rdi, rsi
0x1801ae02e  jbe     short loc_1801AE04C
0x1801ae030  mov     rdx, [rbx+rsi*8]
0x1801ae034  lea     rcx, [r15+0B0h]; this
0x1801ae03b  mov     rdx, [rdx+10h]; struct CSimpleCaseInsensitiveOrdinalStringArray *
0x1801ae03f  call    ?RemoveTemplateFromArray@TemplateDownloadHelpers@@YAJAEAVCSimpleCaseInsensitiveOrdinalStringArray@@PEBG@Z; TemplateDownloadHelpers::RemoveTemplateFromArray(CSimpleCaseInsensitiveOrdinalStringArray &,ushort const *)
0x1801ae044  inc     rsi
0x1801ae047  cmp     rsi, rdi
0x1801ae04a  jb      short loc_1801AE030
0x1801ae04c  lea     rcx, [rsp+520h+hFindFile]; this
0x1801ae051  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801ae056  test    rbx, rbx
0x1801ae059  jz      short loc_1801AE07C
0x1801ae05b  xor     esi, esi
0x1801ae05d  test    rdi, rdi
0x1801ae060  jz      short loc_1801AE073
0x1801ae062  lea     rcx, [rbx+rsi*8]
0x1801ae066  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801ae06b  inc     rsi
0x1801ae06e  cmp     rsi, rdi
0x1801ae071  jb      short loc_1801AE062
0x1801ae073  mov     rcx, rbx; pv
0x1801ae076  call    cs:__imp_CoTaskMemFree
0x1801ae07c  lea     rcx, [rsp+520h+ppszPath]
0x1801ae081  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ae086  lea     rcx, [rsp+520h+var_4C0]; this
0x1801ae08b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801ae090  mov     rcx, [rbp+420h+var_30]
0x1801ae097  xor     rcx, rsp; StackCookie
0x1801ae09a  call    __security_check_cookie
0x1801ae09f  lea     r11, [rsp+520h+var_20]
0x1801ae0a7  mov     rbx, [r11+38h]
0x1801ae0ab  mov     rsi, [r11+40h]
0x1801ae0af  mov     rsp, r11
0x1801ae0b2  pop     r15
0x1801ae0b4  pop     r14
0x1801ae0b6  pop     r13
0x1801ae0b8  pop     rdi
0x1801ae0b9  pop     rbp
0x1801ae0ba  retn
```
