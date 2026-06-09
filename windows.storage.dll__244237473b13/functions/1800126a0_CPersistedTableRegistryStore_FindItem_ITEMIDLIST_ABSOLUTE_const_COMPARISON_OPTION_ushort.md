# CPersistedTableRegistryStore::FindItem(_ITEMIDLIST_ABSOLUTE const *,COMPARISON_OPTION,ushort * *)

- ea: `0x1800126a0`
- end: `0x180012d1c`
- name: `?FindItem@CPersistedTableRegistryStore@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@W4COMPARISON_OPTION@@PEAPEAG@Z`
- size: `1660`
- prototype: `int __high(const struct _ITEMIDLIST_ABSOLUTE *, enum COMPARISON_OPTION, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x180011f80`
- `0x1800126a0`
- `0x180012d30`
- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x1800899a4`
- `0x1800b03d0`
- `0x1800d2374`
- `0x1800f8b50`
- `0x1800fd500`
- `0x1800fd8e0`
- `0x180103290`
- `0x180171934`
- `0x1801bca10`
- `0x1801bd2a8`
- `0x1801bdab8`
- `0x1801bdff4`
- `0x180243eb0`
- `0x180296470`
- `0x18036a5b8`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001280d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001280d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128a7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012bbd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012c7e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012bbd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001299c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001299c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cac`

## string_xrefs

- `0x180012944`: `FilePath`
- `0x180012865`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180012882`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1800128cc`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180012add`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180012c41`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180012c5a`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180012cfd`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CPersistedTableRegistryStore::FindItem(
        CPersistedTableRegistryStore *a1,
        const ITEMIDLIST *a2,
        int a3,
        _QWORD *a4)
{
  int v8; // edi
  int Items; // eax
  unsigned int v10; // ebx
  int TableRegKey; // eax
  void *v12; // rax
  int v13; // eax
  int v14; // r9d
  unsigned __int16 *v15; // rsi
  unsigned __int16 *v16; // r15
  ITEMIDLIST *v17; // rcx
  HKEY v18; // rcx
  HKEY v20; // rcx
  __int64 v21; // rcx
  WCHAR *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int Link; // eax
  int v26; // eax
  int UnaliasedIDList; // eax
  ITEMIDLIST *v28; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v29; // rcx
  int v30; // eax
  ITEMIDLIST *v31; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v32; // rcx
  __int64 v33; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  unsigned int *v35; // [rsp+28h] [rbp-D8h]
  LPCWCH lpString2; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  _QWORD *v39; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v47; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  _BYTE v52[192]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v39 = a4;
  WinRTStorageTelemetry::WatchCurrentThread(v52, "FindItem", 0);
  v8 = 0;
  *a4 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  Items = CPersistedTableRegistryStore::GetItems(a1);
  v10 = Items;
  if ( Items < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)Items,
      v34);
    goto LABEL_12;
  }
  hKey = 0;
  TableRegKey = CPersistedTableRegistryStore::_GetTableRegKey(a1, 0x20019u, &hKey);
  v10 = TableRegKey;
  if ( TableRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)TableRegKey,
      v34);
    goto LABEL_15;
  }
  v12 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)a1 + 3) + 120LL))(*((_QWORD **)a1 + 3));
  v13 = wil::impersonate_token_nothrow(v12);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v13,
      v34);
LABEL_15:
    v20 = hKey;
    hKey = 0;
    if ( v20 )
      RegCloseKey(v20);
    goto LABEL_12;
  }
  pidl = 0;
  pv = 0;
  v44 = 0;
  v45 = 0;
  if ( (int)RebaseOnVolumeID(a2, (LPITEMIDLIST *)&pidl) >= 0 )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v44 = -1;
    v45 = -1;
    SHGetNameFromIDList(pidl, SIGDN_FILESYSPATH, (PWSTR *)&pv);
  }
  v15 = v48;
  v16 = &v48[268 * v49];
  while ( 1 )
  {
    if ( v15 == v16 )
    {
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_9;
    }
    v22 = 0;
    lpString2 = 0;
    v37 = 0;
    v38 = 0;
    if ( !pv )
      goto LABEL_30;
    v37 = -1;
    v38 = -1;
    if ( SHRegAllocData(hKey, v15, L"FilePath", v14, (void **)&lpString2, v35) < 0 )
    {
      v22 = (WCHAR *)lpString2;
LABEL_30:
      v46 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Link = CPersistedTableRegistryStore::GetLink(a1, v15, 8, &v46);
      if ( Link < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x201,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
          (const char *)(unsigned int)Link,
          v34);
      }
      else
      {
        v47 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, struct _ITEMIDLIST_ABSOLUTE **))(*(_QWORD *)v46 + 32LL))(v46, &v47);
        if ( v26 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x204,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
            (const char *)(unsigned int)v26,
            v34);
        }
        else
        {
          pidl2 = 0;
          UnaliasedIDList = GetUnaliasedIDList(v47, (struct _ITEMIDLIST_ABSOLUTE **)&pidl2);
          if ( UnaliasedIDList < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x209,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
              (const char *)(unsigned int)UnaliasedIDList,
              v34);
          }
          else if ( a3 )
          {
            if ( a3 != 1 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
              v8 = -2147024809;
              RoOriginateError(2147942487LL, 0);
              v31 = (ITEMIDLIST *)pidl2;
              pidl2 = 0;
              CoTaskMemFree(v31);
              v32 = v47;
              v47 = 0;
              CoTaskMemFree(v32);
              v33 = v46;
              if ( v46 )
              {
                v46 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              goto LABEL_43;
            }
            LOBYTE(v8) = ILIsEqual(a2, pidl2);
          }
          else
          {
            LOBYTE(v8) = ILIsEqual(a2, pidl2) || ILIsParent(pidl2, a2, 0);
          }
          v28 = (ITEMIDLIST *)pidl2;
          pidl2 = 0;
          CoTaskMemFree(v28);
        }
        v29 = v47;
        v47 = 0;
        CoTaskMemFree(v29);
      }
      v24 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
LABEL_25:
      if ( !(_BYTE)v8 )
        goto LABEL_26;
      goto LABEL_41;
    }
    if ( !a3 )
    {
      v22 = (WCHAR *)lpString2;
      LOBYTE(v8) = (unsigned int)PathIsEqualOrSubFolder(lpString2, (LPCWCH)pv) != 0;
      goto LABEL_25;
    }
    if ( a3 != 1 )
      break;
    v22 = (WCHAR *)lpString2;
    if ( (PathComparePaths(lpString2, (LPCWCH)pv) & 2) == 0 )
      goto LABEL_25;
LABEL_41:
    v30 = _AllocString<CTCoAllocPolicy>(v24, v23, v15, v39);
    v8 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)v30,
        v34);
LABEL_43:
      if ( v22 )
        CoTaskMemFree(v22);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_9;
    }
LABEL_26:
    v8 = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    v15 += 268;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v21);
  v8 = -2147024809;
  RoOriginateError(2147942487LL, 0);
  if ( lpString2 )
    CoTaskMemFree((LPVOID)lpString2);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
LABEL_9:
  v44 = 0;
  v45 = 0;
  v17 = (ITEMIDLIST *)pidl;
  pidl = 0;
  CoTaskMemFree(v17);
  v18 = hKey;
  hKey = 0;
  if ( v18 )
    RegCloseKey(v18);
  v10 = v8;
LABEL_12:
  CTSimpleArray<PERSISTED_ITEM,4294967294,CTPolicyCoTaskMem<PERSISTED_ITEM>,CSimpleArrayStandardCompareHelper<PERSISTED_ITEM>,CSimpleArrayStandardMergeHelper<PERSISTED_ITEM>>::RemoveAll(&v48);
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v52);
  return v10;
}

```

## disassembly

```asm
0x1800126a0  mov     [rsp-8+arg_10], rbx
0x1800126a5  push    rbp
0x1800126a6  push    rsi
0x1800126a7  push    rdi
0x1800126a8  push    r12
0x1800126aa  push    r13
0x1800126ac  push    r14
0x1800126ae  push    r15
0x1800126b0  lea     rbp, [rsp-90h]
0x1800126b8  sub     rsp, 190h
0x1800126bf  mov     rax, cs:__security_cookie
0x1800126c6  xor     rax, rsp
0x1800126c9  mov     [rbp+0C0h+var_40], rax
0x1800126d0  mov     rbx, r9
0x1800126d3  mov     [rsp+1C0h+var_170], rbx
0x1800126d8  mov     r14d, r8d
0x1800126db  mov     r12, rdx
0x1800126de  mov     r13, rcx
0x1800126e1  xor     r8d, r8d
0x1800126e4  lea     rdx, aFinditem; "FindItem"
0x1800126eb  lea     rcx, [rbp+0C0h+var_100]
0x1800126ef  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1800126f4  nop
0x1800126f5  xor     edi, edi
0x1800126f7  mov     [rbx], rdi
0x1800126fa  mov     [rbp+0C0h+var_128], rdi
0x1800126fe  mov     [rbp+0C0h+var_120], rdi
0x180012702  mov     [rbp+0C0h+var_118], rdi
0x180012706  mov     [rbp+0C0h+var_110], rdi
0x18001270a  xor     r8d, r8d
0x18001270d  lea     rdx, [rbp+0C0h+var_128]
0x180012711  mov     rcx, r13
0x180012714  call    ?GetItems@CPersistedTableRegistryStore@@UEAAJPEAV?$CCoSimpleArray@UPERSISTED_ITEM@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UPERSISTED_ITEM@@@@@@W4PERSISTED_ITEM_LIST_FLAGS@@@Z; CPersistedTableRegistryStore::GetItems(CCoSimpleArray<PERSISTED_ITEM,4294967294,CSimpleArrayStandardCompareHelper<PERSISTED_ITEM>> *,PERSISTED_ITEM_LIST_FLAGS)
0x180012719  mov     ebx, eax
0x18001271b  test    eax, eax
0x18001271d  js      loc_18001285B
0x180012723  mov     [rsp+1C0h+hKey], rdi
0x180012728  lea     r8, [rsp+1C0h+hKey]; HKEY *
0x18001272d  mov     edx, 20019h; unsigned int
0x180012732  mov     rcx, r13; this
0x180012735  call    ?_GetTableRegKey@CPersistedTableRegistryStore@@AEAAJKPEAPEAUHKEY__@@@Z; CPersistedTableRegistryStore::_GetTableRegKey(ulong,HKEY__ * *)
0x18001273a  mov     ebx, eax
0x18001273c  test    eax, eax
0x18001273e  js      loc_180012878
0x180012744  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012748  mov     [rsp+1C0h+Token], rsi
0x18001274d  mov     rcx, [r13+18h]
0x180012751  mov     rax, [rcx]
0x180012754  mov     rax, [rax+78h]
0x180012758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275d  mov     rcx, rax; Token
0x180012760  lea     rdx, [rsp+1C0h+Token]
0x180012765  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18001276a  mov     ebx, eax
0x18001276c  test    eax, eax
0x18001276e  js      loc_1800128C2
0x180012774  mov     [rsp+1C0h+pidl], rdi
0x180012779  mov     [rsp+1C0h+pv], rdi
0x18001277e  mov     [rsp+1C0h+var_148], rdi
0x180012783  mov     [rbp+0C0h+var_140], rdi
0x180012787  lea     rdx, [rsp+1C0h+pidl]; ppidl
0x18001278c  mov     rcx, r12; pidl
0x18001278f  call    RebaseOnVolumeID
0x180012794  test    eax, eax
0x180012796  jns     loc_1800128EF
0x18001279c  mov     rsi, [rbp+0C0h+var_128]
0x1800127a0  imul    r15, [rbp+0C0h+var_120], 218h
0x1800127a8  add     r15, rsi
0x1800127ab  cmp     rsi, r15
0x1800127ae  jnz     loc_180012CD8
0x1800127b4  mov     rcx, [rsp+1C0h+pv]; pv
0x1800127b9  test    rcx, rcx
0x1800127bc  jz      short loc_1800127CF
0x1800127be  call    cs:__imp_CoTaskMemFree
0x1800127c5  nop     dword ptr [rax+rax+00h]
0x1800127ca  mov     [rsp+1C0h+pv], rdi
0x1800127cf  mov     [rsp+1C0h+var_148], rdi
0x1800127d4  mov     [rbp+0C0h+var_140], rdi
0x1800127d8  mov     rcx, [rsp+1C0h+pidl]; pv
0x1800127dd  mov     [rsp+1C0h+pidl], rdi
0x1800127e2  call    cs:__imp_CoTaskMemFree
0x1800127e9  nop     dword ptr [rax+rax+00h]
0x1800127ee  nop
0x1800127ef  mov     rcx, [rsp+1C0h+Token]; Token
0x1800127f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800127f8  jnz     loc_1800128B8
0x1800127fe  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180012803  mov     [rsp+1C0h+hKey], rdi
0x180012808  test    rcx, rcx
0x18001280b  jz      short loc_180012819
0x18001280d  call    cs:__imp_RegCloseKey
0x180012814  nop     dword ptr [rax+rax+00h]
0x180012819  mov     ebx, edi
0x18001281b  lea     rcx, [rbp+0C0h+var_128]
0x18001281f  call    ?RemoveAll@?$CTSimpleArray@UPERSISTED_ITEM@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UPERSISTED_ITEM@@@@V?$CSimpleArrayStandardCompareHelper@UPERSISTED_ITEM@@@@V?$CSimpleArrayStandardMergeHelper@UPERSISTED_ITEM@@@@@@QEAAXXZ; CTSimpleArray<PERSISTED_ITEM,4294967294,CTPolicyCoTaskMem<PERSISTED_ITEM>,CSimpleArrayStandardCompareHelper<PERSISTED_ITEM>,CSimpleArrayStandardMergeHelper<PERSISTED_ITEM>>::RemoveAll(void)
0x180012824  nop
0x180012825  lea     rcx, [rbp+0C0h+var_100]; this
0x180012829  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18001282e  mov     eax, ebx
0x180012830  mov     rcx, [rbp+0C0h+var_40]
0x180012837  xor     rcx, rsp; StackCookie
0x18001283a  call    __security_check_cookie
0x18001283f  mov     rbx, [rsp+1C0h+arg_10]
0x180012847  add     rsp, 190h
0x18001284e  pop     r15
0x180012850  pop     r14
0x180012852  pop     r13
0x180012854  pop     r12
0x180012856  pop     rdi
0x180012857  pop     rsi
0x180012858  pop     rbp
0x180012859  retn
0x18001285b  mov     rcx, [rbp+0C8h]; this
0x180012862  mov     r9d, eax; char *
0x180012865  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x18001286c  mov     edx, 1D2h; void *
0x180012871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012876  jmp     short loc_18001281B
0x180012878  mov     rcx, [rbp+0C8h]; this
0x18001287f  mov     r9d, eax; char *
0x180012882  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x180012889  mov     edx, 1D5h; void *
0x18001288e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012893  nop
0x180012894  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180012899  mov     [rsp+1C0h+hKey], rdi
0x18001289e  test    rcx, rcx
0x1800128a1  jz      loc_18001281B
0x1800128a7  call    cs:__imp_RegCloseKey
0x1800128ae  nop     dword ptr [rax+rax+00h]
0x1800128b3  jmp     loc_18001281B
0x1800128b8  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800128bd  jmp     loc_1800127FE
0x1800128c2  mov     rcx, [rbp+0C8h]; this
0x1800128c9  mov     r9d, eax; char *
0x1800128cc  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1800128d3  mov     edx, 1D8h; void *
0x1800128d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128dd  nop
0x1800128de  mov     rcx, [rsp+1C0h+Token]; Token
0x1800128e3  cmp     rcx, rsi
0x1800128e6  jz      short loc_180012894
0x1800128e8  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800128ed  jmp     short loc_180012894
0x1800128ef  mov     rcx, [rsp+1C0h+pv]; pv
0x1800128f4  test    rcx, rcx
0x1800128f7  jz      short loc_18001290A
0x1800128f9  call    cs:__imp_CoTaskMemFree
0x180012900  nop     dword ptr [rax+rax+00h]
0x180012905  mov     [rsp+1C0h+pv], rdi
0x18001290a  mov     [rsp+1C0h+var_148], rsi
0x18001290f  mov     [rbp+0C0h+var_140], rsi
0x180012913  lea     r8, [rsp+1C0h+pv]; ppszName
0x180012918  mov     edx, 80058000h; sigdnName
0x18001291d  mov     rcx, [rsp+1C0h+pidl]; pidl
0x180012922  call    SHGetNameFromIDList
0x180012927  jmp     loc_18001279C
0x18001292c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012930  mov     [rsp+1C0h+var_180], rax
0x180012935  mov     [rsp+1C0h+var_178], rax
0x18001293a  lea     rax, [rsp+1C0h+lpString2]
0x18001293f  mov     [rsp+1C0h+var_1A0], rax; int
0x180012944  lea     r8, aFilepath; "FilePath"
0x18001294b  mov     rdx, rsi; unsigned __int16 *
0x18001294e  mov     rcx, [rsp+1C0h+hKey]; HKEY
0x180012953  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180012958  test    eax, eax
0x18001295a  js      short loc_1800129B4
0x18001295c  test    r14d, r14d
0x18001295f  jz      loc_180012B61
0x180012965  cmp     r14d, 1
0x180012969  jnz     loc_180012BAF
0x18001296f  mov     rdx, [rsp+1C0h+pv]; lpString1
0x180012974  mov     rbx, [rsp+1C0h+lpString2]
0x180012979  mov     rcx, rbx; lpString2
0x18001297c  call    PathComparePaths
0x180012981  test    al, 2
0x180012983  jnz     loc_180012ABC
0x180012989  test    dil, dil
0x18001298c  jnz     loc_180012ABC
0x180012992  xor     edi, edi
0x180012994  test    rbx, rbx
0x180012997  jz      short loc_1800129A8
0x180012999  mov     rcx, rbx; pv
0x18001299c  call    cs:__imp_CoTaskMemFree
0x1800129a3  nop     dword ptr [rax+rax+00h]
0x1800129a8  add     rsi, 218h
0x1800129af  jmp     loc_1800127AB
0x1800129b4  mov     rbx, [rsp+1C0h+lpString2]
0x1800129b9  mov     [rbp+0C0h+var_138], 0
0x1800129c1  lea     rcx, [rbp+0C0h+var_138]
0x1800129c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800129ca  lea     r9, [rbp+0C0h+var_138]
0x1800129ce  mov     r8d, 8
0x1800129d4  mov     rdx, rsi
0x1800129d7  mov     rcx, r13
0x1800129da  call    ?GetLink@CPersistedTableRegistryStore@@UEAAJPEBGW4AccessCacheOptions@AccessCache@Storage@Windows@@PEAPEAUIShellLinkW@@@Z; CPersistedTableRegistryStore::GetLink(ushort const *,Windows::Storage::AccessCache::AccessCacheOptions,IShellLinkW * *)
0x1800129df  mov     rcx, [rbp+0C8h]; this
0x1800129e6  test    eax, eax
0x1800129e8  js      loc_180012CFA
0x1800129ee  mov     [rbp+0C0h+var_130], 0
0x1800129f6  mov     rcx, [rbp+0C0h+var_138]
0x1800129fa  mov     rax, [rcx]
0x1800129fd  lea     rdx, [rbp+0C0h+var_130]
0x180012a01  mov     rax, [rax+20h]
0x180012a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a0a  mov     rcx, [rbp+0C8h]; this
0x180012a11  test    eax, eax
0x180012a13  js      loc_180012C3E
0x180012a19  mov     [rsp+1C0h+pidl2], 0
0x180012a22  lea     rdx, [rsp+1C0h+pidl2]; struct _ITEMIDLIST_ABSOLUTE **
0x180012a27  mov     rcx, [rbp+0C0h+var_130]; struct _ITEMIDLIST_ABSOLUTE *
0x180012a2b  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180012a30  mov     rcx, [rbp+0C8h]; this
0x180012a37  test    eax, eax
0x180012a39  js      loc_180012C57
0x180012a3f  test    r14d, r14d
0x180012a42  jz      loc_180012B7E
0x180012a48  cmp     r14d, 1
0x180012a4c  jnz     loc_180012C70
0x180012a52  mov     rdx, [rsp+1C0h+pidl2]; pidl2
0x180012a57  mov     rcx, r12; pidl1
0x180012a5a  call    ILIsEqual
0x180012a5f  test    eax, eax
0x180012a61  setnz   dil
0x180012a65  mov     rcx, [rsp+1C0h+pidl2]; pv
0x180012a6a  mov     [rsp+1C0h+pidl2], 0
0x180012a73  call    cs:__imp_CoTaskMemFree
0x180012a7a  nop     dword ptr [rax+rax+00h]
0x180012a7f  nop
0x180012a80  mov     rcx, [rbp+0C0h+var_130]; pv
0x180012a84  mov     [rbp+0C0h+var_130], 0
0x180012a8c  call    cs:__imp_CoTaskMemFree
0x180012a93  nop     dword ptr [rax+rax+00h]
0x180012a98  nop
0x180012a99  mov     rcx, [rbp+0C0h+var_138]
0x180012a9d  test    rcx, rcx
0x180012aa0  jz      short loc_180012AB7
0x180012aa2  mov     [rbp+0C0h+var_138], 0
0x180012aaa  mov     rax, [rcx]
0x180012aad  mov     rax, [rax+10h]
0x180012ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ab6  nop
0x180012ab7  jmp     loc_180012989
0x180012abc  mov     r9, [rsp+1C0h+var_170]
0x180012ac1  mov     r8, rsi
0x180012ac4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180012ac9  mov     edi, eax
0x180012acb  test    eax, eax
0x180012acd  jns     loc_180012992
0x180012ad3  mov     rcx, [rbp+0C8h]; this
0x180012ada  mov     r9d, eax; char *
0x180012add  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x180012ae4  mov     edx, 21Fh; void *
0x180012ae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012aee  nop
0x180012aef  xor     esi, esi
0x180012af1  test    rbx, rbx
0x180012af4  jz      short loc_180012B06
0x180012af6  mov     rcx, rbx; pv
0x180012af9  call    cs:__imp_CoTaskMemFree
0x180012b00  nop     dword ptr [rax+rax+00h]
0x180012b05  nop
0x180012b06  mov     rcx, [rsp+1C0h+pv]; pv
0x180012b0b  test    rcx, rcx
0x180012b0e  jz      short loc_180012B21
0x180012b10  call    cs:__imp_CoTaskMemFree
0x180012b17  nop     dword ptr [rax+rax+00h]
0x180012b1c  mov     [rsp+1C0h+pv], rsi
0x180012b21  mov     [rsp+1C0h+var_148], rsi
0x180012b26  mov     [rbp+0C0h+var_140], rsi
0x180012b2a  mov     rcx, [rsp+1C0h+pidl]; pv
0x180012b2f  mov     [rsp+1C0h+pidl], rsi
0x180012b34  call    cs:__imp_CoTaskMemFree
0x180012b3b  nop     dword ptr [rax+rax+00h]
0x180012b40  nop
0x180012b41  mov     rcx, [rsp+1C0h+Token]; Token
0x180012b46  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012b4a  jz      short loc_180012B52
0x180012b4c  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180012b51  nop
0x180012b52  mov     rcx, [rsp+1C0h+hKey]
0x180012b57  mov     [rsp+1C0h+hKey], rsi
0x180012b5c  jmp     loc_180012808
0x180012b61  mov     rdx, [rsp+1C0h+pv]; lpString1
0x180012b66  mov     rbx, [rsp+1C0h+lpString2]
0x180012b6b  mov     rcx, rbx; lpString2
0x180012b6e  call    PathIsEqualOrSubFolder
0x180012b73  test    eax, eax
0x180012b75  setnz   dil
0x180012b79  jmp     loc_180012989
0x180012b7e  mov     rdx, [rsp+1C0h+pidl2]; pidl2
0x180012b83  mov     rcx, r12; pidl1
0x180012b86  call    ILIsEqual
0x180012b8b  test    eax, eax
0x180012b8d  jnz     short loc_180012BA7
0x180012b8f  xor     r8d, r8d; fImmediate
0x180012b92  mov     rdx, r12; pidl2
0x180012b95  mov     rcx, [rsp+1C0h+pidl2]; pidl1
0x180012b9a  call    ILIsParent
  ... truncated ...
```
