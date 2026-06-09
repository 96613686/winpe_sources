# CRecentDocsHelper::AddToRecentDocs(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,uint,MFU_FOLDER_ACTION,RecentDocsFlags)

- ea: `0x1802253a8`
- end: `0x1802259c8`
- name: `?AddToRecentDocs@CRecentDocsHelper@@QEAA_NPEBU_ITEMIDLIST_ABSOLUTE@@PEBG111111HKIW4MFU_FOLDER_ACTION@@W4RecentDocsFlags@@@Z`
- size: `1568`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180224bf0`
- `0x180224df0`
- `0x180449380`

## callees

- `0x180009fc0`
- `0x18001e9a0`
- `0x180045230`
- `0x1800544f0`
- `0x18007dcf0`
- `0x1800899a4`
- `0x1800fa660`
- `0x180133f50`
- `0x180144260`
- `0x1801638c8`
- `0x180183160`
- `0x1801ad290`
- `0x1801c5a50`
- `0x180225294`
- `0x1802253a8`
- `0x180239010`
- `0x180268860`
- `0x18027f46c`
- `0x1802d7970`
- `0x1802d7af0`
- `0x1802db6a0`
- `0x1802ef5a4`
- `0x18033163c`
- `0x180331698`
- `0x180331900`
- `0x180331b0c`
- `0x18033295c`
- `0x18034b788`
- `0x18035e740`
- `0x18036ff94`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x180649650`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802256ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1802256ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18022567b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18022567b`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180225734`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180225734`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1802256fe`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x1802256fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022568e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18022568e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1802256da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1802256da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180225449`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18022589c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180225449`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18022589c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802257c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180225988`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802257c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180225988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802258ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802258ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180225504`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180225504`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall CRecentDocsHelper::AddToRecentDocs(
        unsigned int *a1,
        const ITEMIDLIST *a2,
        WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        int a13,
        int a14)
{
  LPWSTR FileNameW; // rax
  WCHAR *v19; // r12
  char v20; // bl
  unsigned int v21; // ebx
  __int64 v22; // r15
  LPVOID v23; // rdi
  __int64 (__fastcall *v24)(LPVOID, _QWORD, unsigned __int16 **, _QWORD); // rbx
  int v25; // eax
  int v26; // eax
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v30; // rbx
  unsigned __int16 *v31; // rbx
  LPWSTR ExtensionW; // rax
  int v33; // eax
  ITEMIDLIST *v34; // rax
  ITEMIDLIST *v35; // rbx
  const unsigned __int16 *v36; // rax
  char v37; // bl
  unsigned __int16 *v38; // rbx
  LPWSTR v39; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+28h] [rbp-D8h]
  char v43[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h]
  LPVOID v49; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h]
  __int64 v52; // [rsp+88h] [rbp-78h]
  _QWORD v53[42]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszUrl[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v55[524]; // [rsp+1E4h] [rbp+E4h] BYREF
  unsigned __int16 v56[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR pszPath[2088]; // [rsp+600h] [rbp+500h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+16A8h] [rbp+15A8h]

  v48 = a5;
  v47 = a6;
  v46 = a7;
  v45 = a8;
  v44 = a9;
  v43[0] = 0;
  *(_DWORD *)pszUrl = 0;
  memset_0(v55, 0, 0x204u);
  FileNameW = PathFindFileNameW(a3);
  v19 = FileNameW;
  if ( !FileNameW || (v20 = 1, !*FileNameW) )
    v20 = 0;
  if ( !IsRecentDocsEnabled() || (unsigned int)PathIsTemporaryW(a3) || !v20 )
    return v43[0];
  wil::ActivityBase<FileExplorerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v53);
  v53[0] = &FileExplorerTelemetry::AddToRecentDocs::`vftable';
  v21 = a12;
  FileExplorerTelemetry::AddToRecentDocs::StartActivity((FileExplorerTelemetry::AddToRecentDocs *)v53, a12, a11);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  if ( a4 )
  {
    v22 = -1;
    v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&v50, a4, -1);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56B,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\recdocs.cpp",
        (const char *)(unsigned int)v26,
        ppv);
  }
  else
  {
    v49 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v22 = -1;
    if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_de25675a_72de_44b4_9373_05170450c140, &v49) >= 0 )
    {
      v23 = v49;
      v24 = *(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)v49 + 48LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
      v51 = -1;
      v52 = -1;
      HIDWORD(v42) = 0;
      v25 = v24(v23, a11, &v50, 0);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x566,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\recdocs.cpp",
          (const char *)(unsigned int)v25,
          0);
      v21 = a12;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  }
  if ( (a14 & 2) != 0 )
  {
    v27 = v50;
    if ( v50 )
      AddTaskLinkToAutoDestList(v50, a3, v47, v46, v50, v45, v44, a10);
    goto LABEL_44;
  }
  LODWORD(v49) = 0;
  LODWORD(v42) = v21;
  if ( (unsigned int)AddToAutoDestList(a11, a2, v50, v48, &v49, v42, a13, a14) == -2147217660
    || (unsigned int)CheckIfFileIsCached(a3, v21) )
  {
    goto LABEL_44;
  }
  AcquireSRWLockExclusive(&g_srwLastFileLock);
  LocalFree(g_pszLastFile);
  g_pszLastFile = 0;
  do
    ++v22;
  while ( a3[v22] );
  if ( (int)_AllocStringWorker<CTLocalAllocPolicy>(v29, v28, a3, v22, 1, &g_pszLastFile) >= 0 )
    GetSystemTimeAsFileTime(&g_ftLastFileCacheUpdate);
  ReleaseSRWLockExclusive(&g_srwLastFileLock);
  if ( UrlIsW(a3, URLIS_URL) )
  {
    StringCchCopyW(pszUrl, 0x104u, v19);
    UrlUnescapeW(pszUrl, 0, 0, 0x140000u);
    v19 = pszUrl;
  }
  v30 = (struct _ITEMIDLIST_ABSOLUTE *)SHCloneSpecialIDList(0, 8, 1);
  if ( (int)CRecentDocsHelper::_SetTarget((CRecentDocsHelper *)a1, v30) < 0 || !v30 )
    goto LABEL_44;
  if ( CreateSharedRecentMRUList(*((struct CRecentDocumentsFolder **)a1 + 3), 0, a1 + 2, 0, (struct IMruDataList **)a1) >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51721485>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51721485>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)ShouldAddToRecentDocs(a2, v50) )
      {
        v31 = v50;
        ExtensionW = PathFindExtensionW(v19);
        v33 = CRecentDocsHelper::_AddDocToRecentAndExtRecent(a1, a2, v19, ExtensionW, a3, v31, a14, a12);
        goto LABEL_32;
      }
    }
    else if ( (unsigned int)ShouldAddToRecentDocs(a2, v50) )
    {
      v38 = v50;
      v39 = PathFindExtensionW(v19);
      v33 = CRecentDocsHelper::_AddDocToRecentAndExtRecent(a1, a2, v19, v39, a3, v38, a14, 0);
LABEL_32:
      if ( v33 )
      {
        v43[0] = 1;
        _AddToUrlHistory(a3);
      }
    }
    if ( (_DWORD)v49 )
    {
      v34 = ILClone(a2);
      v35 = v34;
      if ( v34 )
      {
        ILRemoveLastID(v34);
        if ( (int)SHGetNameAndFlagsW(v35, 0x8000u, pszPath, 0x824u, 0) >= 0
          && !(unsigned int)PathIsOneOf(pszPath, &off_1806BC408, 5) )
        {
          if ( (int)SHGetNameAndFlagsW(v35, 0, v56, 0x104u, 0) < 0 )
          {
            v36 = PathFindFileNameW(pszPath);
            StringCchCopyW(v56, 0x104u, v36);
          }
          CRecentDocsHelper::_AddDocToRecentAndExtRecent(a1, v35, v56, L"Folder", a3, v50, a14, 0);
        }
        CoTaskMemFree(v35);
      }
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 16LL))(*(_QWORD *)a1);
    *(_QWORD *)a1 = 0;
  }
  CRecentDocsHelper::_SetTarget((CRecentDocsHelper *)a1, 0);
LABEL_44:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v27, Shell32_RecentDoc_Processed_Info, a3);
  v37 = v43[0];
  if ( v43[0] )
    FileExplorerTelemetry::AddToRecentDocs::NewlyAdded<bool &>(v53, a1 + 8);
  FileExplorerTelemetry::AddToRecentDocs::DocumentAdded<bool &>(v53, v43);
  wil::ActivityBase<FileExplorerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
  FileExplorerTelemetry::AddToRecentDocs::~AddToRecentDocs((FileExplorerTelemetry::AddToRecentDocs *)v53);
  return v37;
}

```

## disassembly

```asm
0x1802253a8  push    rbp
0x1802253aa  push    rbx
0x1802253ab  push    rsi
0x1802253ac  push    rdi
0x1802253ad  push    r12
0x1802253af  push    r13
0x1802253b1  push    r14
0x1802253b3  push    r15
0x1802253b5  lea     rbp, [rsp-1568h]
0x1802253bd  mov     eax, 1668h
0x1802253c2  call    _alloca_probe
0x1802253c7  sub     rsp, rax
0x1802253ca  mov     rax, cs:__security_cookie
0x1802253d1  xor     rax, rsp
0x1802253d4  mov     [rbp+15A0h+var_50], rax
0x1802253db  mov     rdi, r9
0x1802253de  mov     rsi, r8
0x1802253e1  mov     r13, rdx
0x1802253e4  mov     r14, rcx
0x1802253e7  mov     rax, [rbp+15A0h+arg_20]
0x1802253ee  mov     [rsp+16A0h+var_1638], rax
0x1802253f3  mov     rax, [rbp+15A0h+arg_28]
0x1802253fa  mov     [rsp+16A0h+var_1640], rax
0x1802253ff  mov     rax, [rbp+15A0h+arg_30]
0x180225406  mov     [rsp+16A0h+var_1648], rax
0x18022540b  mov     rax, [rbp+15A0h+arg_38]
0x180225412  mov     [rsp+16A0h+var_1650], rax
0x180225417  mov     rax, [rbp+15A0h+arg_40]
0x18022541e  mov     [rsp+16A0h+var_1658], rax
0x180225423  xor     r15d, r15d
0x180225426  mov     [rsp+16A0h+var_1660], r15b
0x18022542b  mov     dword ptr [rbp+15A0h+pszUrl], r15d
0x180225432  xor     edx, edx; Val
0x180225434  mov     r8d, 204h; Size
0x18022543a  lea     rcx, [rbp+15A0h+var_14BC]; void *
0x180225441  call    memset_0
0x180225446  mov     rcx, rsi; pszPath
0x180225449  call    cs:__imp_PathFindFileNameW
0x180225450  nop     dword ptr [rax+rax+00h]
0x180225455  mov     r12, rax
0x180225458  test    rax, rax
0x18022545b  jz      short loc_180225465
0x18022545d  cmp     r15w, [rax]
0x180225461  mov     bl, 1
0x180225463  jnz     short loc_180225468
0x180225465  mov     bl, r15b
0x180225468  call    ?IsRecentDocsEnabled@@YA_NXZ; IsRecentDocsEnabled(void)
0x18022546d  test    al, al
0x18022546f  jz      loc_18022599E
0x180225475  mov     rcx, rsi; unsigned __int16 *
0x180225478  call    PathIsTemporaryW
0x18022547d  test    eax, eax
0x18022547f  jnz     loc_18022599E
0x180225485  test    bl, bl
0x180225487  jz      loc_18022599E
0x18022548d  lea     rdx, aAddtorecentdoc; "AddToRecentDocs"
0x180225494  lea     rcx, [rbp+15A0h+var_1610]; struct wil::details::IFailureCallback *
0x180225498  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18022549d  lea     rax, ??_7AddToRecentDocs@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::AddToRecentDocs::`vftable'
0x1802254a4  mov     [rbp+15A0h+var_1610], rax
0x1802254a8  mov     r8d, [rbp+15A0h+arg_50]; unsigned int
0x1802254af  mov     ebx, [rbp+15A0h+arg_58]
0x1802254b5  mov     edx, ebx; unsigned int
0x1802254b7  lea     rcx, [rbp+15A0h+var_1610]; this
0x1802254bb  call    ?StartActivity@AddToRecentDocs@FileExplorerTelemetry@@QEAAXIK@Z; FileExplorerTelemetry::AddToRecentDocs::StartActivity(uint,ulong)
0x1802254c0  nop
0x1802254c1  mov     [rsp+16A0h+var_1628], r15
0x1802254c6  mov     [rbp+15A0h+var_1620], r15
0x1802254ca  mov     [rbp+15A0h+var_1618], r15
0x1802254ce  test    rdi, rdi
0x1802254d1  jnz     loc_180225592
0x1802254d7  mov     [rsp+16A0h+var_1630], r15
0x1802254dc  lea     rcx, [rsp+16A0h+var_1630]
0x1802254e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802254e6  lea     rax, [rsp+16A0h+var_1630]
0x1802254eb  mov     [rsp+16A0h+ppv], rax; ppv
0x1802254f0  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x1802254f7  xor     edx, edx; pUnkOuter
0x1802254f9  lea     r8d, [rdi+3]; dwClsContext
0x1802254fd  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180225504  call    cs:__imp_CoCreateInstance
0x18022550b  nop     dword ptr [rax+rax+00h]
0x180225510  or      r15, 0FFFFFFFFFFFFFFFFh
0x180225514  test    eax, eax
0x180225516  js      short loc_180225586
0x180225518  mov     rdi, [rsp+16A0h+var_1630]
0x18022551d  mov     rax, [rdi]
0x180225520  mov     rbx, [rax+30h]
0x180225524  lea     rcx, [rsp+16A0h+var_1628]; void *
0x180225529  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18022552e  mov     [rbp+15A0h+var_1620], r15
0x180225532  mov     [rbp+15A0h+var_1618], r15
0x180225536  mov     [rsp+16A0h+var_1678], 0
0x18022553f  mov     [rsp+16A0h+ppv], 0; int
0x180225548  xor     r9d, r9d
0x18022554b  lea     r8, [rsp+16A0h+var_1628]
0x180225550  mov     edx, [rbp+15A0h+arg_50]
0x180225556  mov     rcx, rdi
0x180225559  mov     rax, rbx
0x18022555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225561  mov     rcx, [rbp+15A8h]; this
0x180225568  test    eax, eax
0x18022556a  jns     short loc_180225580
0x18022556c  mov     r9d, eax; char *
0x18022556f  lea     r8, aOnecoreuapShel_106; "onecoreuap\\shell\\windows.storage\\rec"...
0x180225576  mov     edx, 566h; void *
0x18022557b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180225580  mov     ebx, [rbp+15A0h+arg_58]
0x180225586  lea     rcx, [rsp+16A0h+var_1630]
0x18022558b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180225590  jmp     short loc_1802255C5
0x180225592  or      r15, 0FFFFFFFFFFFFFFFFh
0x180225596  mov     r8, r15
0x180225599  mov     rdx, rdi
0x18022559c  lea     rcx, [rsp+16A0h+var_1628]
0x1802255a1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1802255a6  mov     rcx, [rbp+15A8h]; this
0x1802255ad  test    eax, eax
0x1802255af  jns     short loc_1802255C5
0x1802255b1  mov     r9d, eax; char *
0x1802255b4  lea     r8, aOnecoreuapShel_106; "onecoreuap\\shell\\windows.storage\\rec"...
0x1802255bb  mov     edx, 56Bh; void *
0x1802255c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802255c5  mov     edi, [rbp+15A0h+arg_68]
0x1802255cb  test    dil, 2
0x1802255cf  jz      short loc_180225619
0x1802255d1  mov     rcx, [rsp+16A0h+var_1628]
0x1802255d6  test    rcx, rcx
0x1802255d9  jz      loc_180225916
0x1802255df  mov     eax, [rbp+15A0h+arg_48]
0x1802255e5  mov     [rsp+16A0h+var_1668], eax
0x1802255e9  mov     rax, [rsp+16A0h+var_1658]
0x1802255ee  mov     [rsp+16A0h+var_1670], rax
0x1802255f3  mov     rax, [rsp+16A0h+var_1650]
0x1802255f8  mov     [rsp+16A0h+var_1678], rax
0x1802255fd  mov     [rsp+16A0h+ppv], rcx
0x180225602  mov     r9, [rsp+16A0h+var_1648]
0x180225607  mov     r8, [rsp+16A0h+var_1640]
0x18022560c  mov     rdx, rsi
0x18022560f  call    AddTaskLinkToAutoDestList
0x180225614  jmp     loc_180225916
0x180225619  mov     dword ptr [rsp+16A0h+var_1630], 0
0x180225621  mov     [rsp+16A0h+var_1668], edi
0x180225625  mov     eax, [rbp+15A0h+arg_60]
0x18022562b  mov     dword ptr [rsp+16A0h+var_1670], eax
0x18022562f  mov     dword ptr [rsp+16A0h+var_1678], ebx
0x180225633  lea     rax, [rsp+16A0h+var_1630]
0x180225638  mov     [rsp+16A0h+ppv], rax
0x18022563d  mov     r9, [rsp+16A0h+var_1638]
0x180225642  mov     r8, [rsp+16A0h+var_1628]
0x180225647  mov     rdx, r13
0x18022564a  mov     ecx, [rbp+15A0h+arg_50]
0x180225650  call    ?AddToAutoDestList@@YAJKPEBU_ITEMIDLIST_ABSOLUTE@@PEBG1PEAHIW4MFU_FOLDER_ACTION@@W4RecentDocsFlags@@@Z; AddToAutoDestList(ulong,_ITEMIDLIST_ABSOLUTE const *,ushort const *,ushort const *,int *,uint,MFU_FOLDER_ACTION,RecentDocsFlags)
0x180225655  cmp     eax, 80040F04h
0x18022565a  jz      loc_180225916
0x180225660  mov     edx, ebx
0x180225662  mov     rcx, rsi
0x180225665  call    ?CheckIfFileIsCached@@YAHPEBGW4SHARD_ACTION@@@Z; CheckIfFileIsCached(ushort const *,SHARD_ACTION)
0x18022566a  xor     ebx, ebx
0x18022566c  test    eax, eax
0x18022566e  jnz     loc_180225916
0x180225674  lea     rcx, ?g_srwLastFileLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18022567b  call    cs:__imp_AcquireSRWLockExclusive
0x180225682  nop     dword ptr [rax+rax+00h]
0x180225687  mov     rcx, cs:?g_pszLastFile@@3PEAGEA; hMem
0x18022568e  call    cs:__imp_LocalFree
0x180225695  nop     dword ptr [rax+rax+00h]
0x18022569a  mov     cs:?g_pszLastFile@@3PEAGEA, rbx; ushort * g_pszLastFile
0x1802256a1  inc     r15
0x1802256a4  cmp     [rsi+r15*2], bx
0x1802256a9  jnz     short loc_1802256A1
0x1802256ab  lea     rax, ?g_pszLastFile@@3PEAGEA; ushort * g_pszLastFile
0x1802256b2  mov     [rsp+16A0h+var_1678], rax
0x1802256b7  mov     ebx, 1
0x1802256bc  mov     [rsp+16A0h+ppv], rbx
0x1802256c1  mov     r9, r15
0x1802256c4  mov     r8, rsi
0x1802256c7  call    ??$_AllocStringWorker@VCTLocalAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTLocalAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1802256cc  xor     r15d, r15d
0x1802256cf  test    eax, eax
0x1802256d1  js      short loc_1802256E6
0x1802256d3  lea     rcx, ?g_ftLastFileCacheUpdate@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x1802256da  call    cs:__imp_GetSystemTimeAsFileTime
0x1802256e1  nop     dword ptr [rax+rax+00h]
0x1802256e6  lea     rcx, ?g_srwLastFileLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1802256ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1802256f4  nop     dword ptr [rax+rax+00h]
0x1802256f9  xor     edx, edx; UrlIs
0x1802256fb  mov     rcx, rsi; pszUrl
0x1802256fe  call    cs:__imp_UrlIsW
0x180225705  nop     dword ptr [rax+rax+00h]
0x18022570a  test    eax, eax
0x18022570c  jz      short loc_180225747
0x18022570e  mov     r8, r12; unsigned __int16 *
0x180225711  mov     edx, 104h; unsigned __int64
0x180225716  lea     rcx, [rbp+15A0h+pszUrl]; unsigned __int16 *
0x18022571d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180225722  mov     r9d, 140000h; dwFlags
0x180225728  xor     r8d, r8d; pcchUnescaped
0x18022572b  xor     edx, edx; pszUnescaped
0x18022572d  lea     rcx, [rbp+15A0h+pszUrl]; pszUrl
0x180225734  call    cs:__imp_UrlUnescapeW
0x18022573b  nop     dword ptr [rax+rax+00h]
0x180225740  lea     r12, [rbp+15A0h+pszUrl]
0x180225747  mov     r8d, ebx; fCreate
0x18022574a  mov     edx, 8; csidl
0x18022574f  xor     ecx, ecx; hwnd
0x180225751  call    SHCloneSpecialIDList
0x180225756  mov     rbx, rax
0x180225759  mov     rdx, rax; struct _ITEMIDLIST_ABSOLUTE *
0x18022575c  mov     rcx, r14; this
0x18022575f  call    ?_SetTarget@CRecentDocsHelper@@AEAAJPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CRecentDocsHelper::_SetTarget(_ITEMIDLIST_ABSOLUTE *)
0x180225764  test    eax, eax
0x180225766  js      loc_180225916
0x18022576c  test    rbx, rbx
0x18022576f  jz      loc_180225916
0x180225775  lea     r8, [r14+8]; unsigned int *
0x180225779  mov     [rsp+16A0h+ppv], r14; struct IMruDataList **
0x18022577e  xor     r9d, r9d; unsigned int
0x180225781  xor     edx, edx; unsigned __int16 *
0x180225783  mov     rcx, [r14+18h]; struct CRecentDocumentsFolder *
0x180225787  call    ?CreateSharedRecentMRUList@@YAJPEAVCRecentDocumentsFolder@@PEBGPEAKKPEAPEAUIMruDataList@@@Z; CreateSharedRecentMRUList(CRecentDocumentsFolder *,ushort const *,ulong *,ulong,IMruDataList * *)
0x18022578c  test    eax, eax
0x18022578e  js      loc_18022590C
0x180225794  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51721485@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51721485@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51721485> `wil::Feature<__WilFeatureTraits_Feature_51721485>::GetImpl(void)'::`2'::impl
0x18022579b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51721485@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51721485>::__private_IsEnabled(void)
0x1802257a0  mov     rdx, [rsp+16A0h+var_1628]; unsigned __int16 *
0x1802257a5  mov     rcx, r13; pidl
0x1802257a8  test    al, al
0x1802257aa  jz      loc_180225973
0x1802257b0  call    ?ShouldAddToRecentDocs@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@PEBG@Z; ShouldAddToRecentDocs(_ITEMIDLIST_ABSOLUTE const *,ushort const *)
0x1802257b5  test    eax, eax
0x1802257b7  jz      short loc_180225807
0x1802257b9  mov     rbx, [rsp+16A0h+var_1628]
0x1802257be  mov     rcx, r12; pszPath
0x1802257c1  call    cs:__imp_PathFindExtensionW
0x1802257c8  nop     dword ptr [rax+rax+00h]
0x1802257cd  mov     ecx, [rbp+15A0h+arg_58]
0x1802257d3  mov     [rsp+16A0h+var_1668], ecx
0x1802257d7  mov     dword ptr [rsp+16A0h+var_1670], edi
0x1802257db  mov     [rsp+16A0h+var_1678], rbx
0x1802257e0  mov     [rsp+16A0h+ppv], rsi
0x1802257e5  mov     r9, rax
0x1802257e8  mov     r8, r12
0x1802257eb  mov     rdx, r13
0x1802257ee  mov     rcx, r14
0x1802257f1  call    ?_AddDocToRecentAndExtRecent@CRecentDocsHelper@@AEAAHPEBU_ITEMIDLIST_ABSOLUTE@@PEBG111W4RecentDocsFlags@@W4SHARD_ACTION@@@Z; CRecentDocsHelper::_AddDocToRecentAndExtRecent(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ushort const *,ushort const *,ushort const *,RecentDocsFlags,SHARD_ACTION)
0x1802257f6  test    eax, eax
0x1802257f8  jz      short loc_180225807
0x1802257fa  mov     [rsp+16A0h+var_1660], 1
0x1802257ff  mov     rcx, rsi; unsigned __int16 *
0x180225802  call    ?_AddToUrlHistory@@YAXPEBG@Z; _AddToUrlHistory(ushort const *)
0x180225807  cmp     dword ptr [rsp+16A0h+var_1630], r15d
0x18022580c  jz      loc_1802258FA
0x180225812  mov     rcx, r13; pidl
0x180225815  call    ILClone
0x18022581a  mov     rbx, rax
0x18022581d  test    rax, rax
0x180225820  jz      loc_1802258FA
0x180225826  mov     rcx, rax; pidl
0x180225829  call    ILRemoveLastID
0x18022582e  mov     [rsp+16A0h+ppv], r15; unsigned int *
0x180225833  mov     r9d, 824h; unsigned int
0x180225839  lea     r8, [rbp+15A0h+pszPath]; unsigned __int16 *
0x180225840  mov     edx, 8000h; unsigned int
0x180225845  mov     rcx, rbx; pidl
0x180225848  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x18022584d  test    eax, eax
0x18022584f  js      loc_1802258EB
0x180225855  mov     r8d, 5
0x18022585b  lea     rdx, off_1806BC408
0x180225862  lea     rcx, [rbp+15A0h+pszPath]
0x180225869  call    PathIsOneOf
0x18022586e  test    eax, eax
0x180225870  jnz     short loc_1802258EB
0x180225872  mov     [rsp+16A0h+ppv], r15; unsigned int *
0x180225877  mov     r12d, 104h
0x18022587d  mov     r9d, r12d; unsigned int
0x180225880  lea     r8, [rbp+15A0h+var_12B0]; unsigned __int16 *
0x180225887  xor     edx, edx; unsigned int
0x180225889  mov     rcx, rbx; pidl
0x18022588c  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x180225891  test    eax, eax
0x180225893  jns     short loc_1802258BA
0x180225895  lea     rcx, [rbp+15A0h+pszPath]; pszPath
0x18022589c  call    cs:__imp_PathFindFileNameW
0x1802258a3  nop     dword ptr [rax+rax+00h]
0x1802258a8  mov     r8, rax; unsigned __int16 *
0x1802258ab  mov     edx, r12d; unsigned __int64
0x1802258ae  lea     rcx, [rbp+15A0h+var_12B0]; unsigned __int16 *
0x1802258b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802258ba  mov     [rsp+16A0h+var_1668], r15d
0x1802258bf  mov     dword ptr [rsp+16A0h+var_1670], edi
0x1802258c3  mov     rax, [rsp+16A0h+var_1628]
0x1802258c8  mov     [rsp+16A0h+var_1678], rax
0x1802258cd  mov     [rsp+16A0h+ppv], rsi
0x1802258d2  lea     r9, aFolder; "Folder"
0x1802258d9  lea     r8, [rbp+15A0h+var_12B0]
0x1802258e0  mov     rdx, rbx
0x1802258e3  mov     rcx, r14
  ... truncated ...
```
