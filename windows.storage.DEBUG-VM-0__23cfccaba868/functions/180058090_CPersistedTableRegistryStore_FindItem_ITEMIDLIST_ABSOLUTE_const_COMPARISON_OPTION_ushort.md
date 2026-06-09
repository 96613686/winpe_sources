# CPersistedTableRegistryStore::FindItem(_ITEMIDLIST_ABSOLUTE const *,COMPARISON_OPTION,ushort * *)

- ea: `0x180058090`
- end: `0x18005869f`
- name: `?FindItem@CPersistedTableRegistryStore@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@W4COMPARISON_OPTION@@PEAPEAG@Z`
- size: `1551`
- prototype: `int __high(const struct _ITEMIDLIST_ABSOLUTE *, enum COMPARISON_OPTION, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x180010110`
- `0x180010220`
- `0x180015ee0`
- `0x180018280`
- `0x180018f50`
- `0x1800432f0`
- `0x180057970`
- `0x180058090`
- `0x1800586b0`
- `0x180058950`
- `0x18006c2e4`
- `0x18006d038`
- `0x18006e168`
- `0x1800dd190`
- `0x18012a358`
- `0x18012a9a0`
- `0x180148460`
- `0x1801e72d0`
- `0x1802321c0`
- `0x18028b5c0`
- `0x1803596f0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058284`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005856a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180058613`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005856a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180058613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800582d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005836d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005843e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005857d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005858e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800581cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800582d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005836d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005843e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005857d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005858e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058635`

## string_xrefs

- `0x180058315`: `FilePath`
- `0x180058242`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x18005825f`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1800582a3`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x18005849c`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1800585d6`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1800585ef`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180058680`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

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
0x180058090  mov     [rsp-8+arg_10], rbx
0x180058095  push    rbp
0x180058096  push    rsi
0x180058097  push    rdi
0x180058098  push    r12
0x18005809a  push    r13
0x18005809c  push    r14
0x18005809e  push    r15
0x1800580a0  lea     rbp, [rsp-90h]
0x1800580a8  sub     rsp, 190h
0x1800580af  mov     rax, cs:__security_cookie
0x1800580b6  xor     rax, rsp
0x1800580b9  mov     [rbp+0C0h+var_40], rax
0x1800580c0  mov     rbx, r9
0x1800580c3  mov     [rsp+1C0h+var_170], rbx
0x1800580c8  mov     r14d, r8d
0x1800580cb  mov     r12, rdx
0x1800580ce  mov     r13, rcx
0x1800580d1  xor     r8d, r8d
0x1800580d4  lea     rdx, aFinditem; "FindItem"
0x1800580db  lea     rcx, [rbp+0C0h+var_100]
0x1800580df  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1800580e4  nop
0x1800580e5  xor     edi, edi
0x1800580e7  mov     [rbx], rdi
0x1800580ea  mov     [rbp+0C0h+var_128], rdi
0x1800580ee  mov     [rbp+0C0h+var_120], rdi
0x1800580f2  mov     [rbp+0C0h+var_118], rdi
0x1800580f6  mov     [rbp+0C0h+var_110], rdi
0x1800580fa  xor     r8d, r8d
0x1800580fd  lea     rdx, [rbp+0C0h+var_128]
0x180058101  mov     rcx, r13
0x180058104  call    ?GetItems@CPersistedTableRegistryStore@@UEAAJPEAV?$CCoSimpleArray@UPERSISTED_ITEM@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UPERSISTED_ITEM@@@@@@W4PERSISTED_ITEM_LIST_FLAGS@@@Z; CPersistedTableRegistryStore::GetItems(CCoSimpleArray<PERSISTED_ITEM,4294967294,CSimpleArrayStandardCompareHelper<PERSISTED_ITEM>> *,PERSISTED_ITEM_LIST_FLAGS)
0x180058109  mov     ebx, eax
0x18005810b  test    eax, eax
0x18005810d  js      loc_180058238
0x180058113  mov     [rsp+1C0h+hKey], rdi
0x180058118  lea     r8, [rsp+1C0h+hKey]; HKEY *
0x18005811d  mov     edx, 20019h; unsigned int
0x180058122  mov     rcx, r13; this
0x180058125  call    ?_GetTableRegKey@CPersistedTableRegistryStore@@AEAAJKPEAPEAUHKEY__@@@Z; CPersistedTableRegistryStore::_GetTableRegKey(ulong,HKEY__ * *)
0x18005812a  mov     ebx, eax
0x18005812c  test    eax, eax
0x18005812e  js      loc_180058255
0x180058134  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180058138  mov     [rsp+1C0h+Token], rsi
0x18005813d  mov     rcx, [r13+18h]
0x180058141  mov     rax, [rcx]
0x180058144  mov     rax, [rax+78h]
0x180058148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005814d  mov     rcx, rax; Token
0x180058150  lea     rdx, [rsp+1C0h+Token]
0x180058155  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18005815a  mov     ebx, eax
0x18005815c  test    eax, eax
0x18005815e  js      loc_180058299
0x180058164  mov     [rsp+1C0h+pidl], rdi
0x180058169  mov     [rsp+1C0h+pv], rdi
0x18005816e  mov     [rsp+1C0h+var_148], rdi
0x180058173  mov     [rbp+0C0h+var_140], rdi
0x180058177  lea     rdx, [rsp+1C0h+pidl]; ppidl
0x18005817c  mov     rcx, r12; pidl
0x18005817f  call    RebaseOnVolumeID
0x180058184  test    eax, eax
0x180058186  jns     loc_1800582C6
0x18005818c  mov     rsi, [rbp+0C0h+var_128]
0x180058190  imul    r15, [rbp+0C0h+var_120], 218h
0x180058198  add     r15, rsi
0x18005819b  cmp     rsi, r15
0x18005819e  jnz     loc_18005865B
0x1800581a4  mov     rcx, [rsp+1C0h+pv]; pv
0x1800581a9  test    rcx, rcx
0x1800581ac  jz      short loc_1800581B9
0x1800581ae  call    cs:__imp_CoTaskMemFree
0x1800581b4  mov     [rsp+1C0h+pv], rdi
0x1800581b9  mov     [rsp+1C0h+var_148], rdi
0x1800581be  mov     [rbp+0C0h+var_140], rdi
0x1800581c2  mov     rcx, [rsp+1C0h+pidl]; pv
0x1800581c7  mov     [rsp+1C0h+pidl], rdi
0x1800581cc  call    cs:__imp_CoTaskMemFree
0x1800581d2  nop
0x1800581d3  mov     rcx, [rsp+1C0h+Token]; Token
0x1800581d8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800581dc  jnz     loc_18005828F
0x1800581e2  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800581e7  mov     [rsp+1C0h+hKey], rdi
0x1800581ec  test    rcx, rcx
0x1800581ef  jz      short loc_1800581F7
0x1800581f1  call    cs:__imp_RegCloseKey
0x1800581f7  mov     ebx, edi
0x1800581f9  lea     rcx, [rbp+0C0h+var_128]
0x1800581fd  call    ?RemoveAll@?$CTSimpleArray@UPERSISTED_ITEM@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UPERSISTED_ITEM@@@@V?$CSimpleArrayStandardCompareHelper@UPERSISTED_ITEM@@@@V?$CSimpleArrayStandardMergeHelper@UPERSISTED_ITEM@@@@@@QEAAXXZ; CTSimpleArray<PERSISTED_ITEM,4294967294,CTPolicyCoTaskMem<PERSISTED_ITEM>,CSimpleArrayStandardCompareHelper<PERSISTED_ITEM>,CSimpleArrayStandardMergeHelper<PERSISTED_ITEM>>::RemoveAll(void)
0x180058202  nop
0x180058203  lea     rcx, [rbp+0C0h+var_100]; this
0x180058207  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18005820c  mov     eax, ebx
0x18005820e  mov     rcx, [rbp+0C0h+var_40]
0x180058215  xor     rcx, rsp; StackCookie
0x180058218  call    __security_check_cookie
0x18005821d  mov     rbx, [rsp+1C0h+arg_10]
0x180058225  add     rsp, 190h
0x18005822c  pop     r15
0x18005822e  pop     r14
0x180058230  pop     r13
0x180058232  pop     r12
0x180058234  pop     rdi
0x180058235  pop     rsi
0x180058236  pop     rbp
0x180058237  retn
0x180058238  mov     rcx, [rbp+0C8h]; this
0x18005823f  mov     r9d, eax; char *
0x180058242  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x180058249  mov     edx, 1D2h; void *
0x18005824e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058253  jmp     short loc_1800581F9
0x180058255  mov     rcx, [rbp+0C8h]; this
0x18005825c  mov     r9d, eax; char *
0x18005825f  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x180058266  mov     edx, 1D5h; void *
0x18005826b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058270  nop
0x180058271  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180058276  mov     [rsp+1C0h+hKey], rdi
0x18005827b  test    rcx, rcx
0x18005827e  jz      loc_1800581F9
0x180058284  call    cs:__imp_RegCloseKey
0x18005828a  jmp     loc_1800581F9
0x18005828f  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180058294  jmp     loc_1800581E2
0x180058299  mov     rcx, [rbp+0C8h]; this
0x1800582a0  mov     r9d, eax; char *
0x1800582a3  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1800582aa  mov     edx, 1D8h; void *
0x1800582af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800582b4  nop
0x1800582b5  mov     rcx, [rsp+1C0h+Token]; Token
0x1800582ba  cmp     rcx, rsi
0x1800582bd  jz      short loc_180058271
0x1800582bf  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800582c4  jmp     short loc_180058271
0x1800582c6  mov     rcx, [rsp+1C0h+pv]; pv
0x1800582cb  test    rcx, rcx
0x1800582ce  jz      short loc_1800582DB
0x1800582d0  call    cs:__imp_CoTaskMemFree
0x1800582d6  mov     [rsp+1C0h+pv], rdi
0x1800582db  mov     [rsp+1C0h+var_148], rsi
0x1800582e0  mov     [rbp+0C0h+var_140], rsi
0x1800582e4  lea     r8, [rsp+1C0h+pv]; ppszName
0x1800582e9  mov     edx, 80058000h; sigdnName
0x1800582ee  mov     rcx, [rsp+1C0h+pidl]; pidl
0x1800582f3  call    SHGetNameFromIDList
0x1800582f8  jmp     loc_18005818C
0x1800582fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058301  mov     [rsp+1C0h+var_180], rax
0x180058306  mov     [rsp+1C0h+var_178], rax
0x18005830b  lea     rax, [rsp+1C0h+lpString2]
0x180058310  mov     [rsp+1C0h+var_1A0], rax; int
0x180058315  lea     r8, aFilepath; "FilePath"
0x18005831c  mov     rdx, rsi; unsigned __int16 *
0x18005831f  mov     rcx, [rsp+1C0h+hKey]; HKEY
0x180058324  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180058329  test    eax, eax
0x18005832b  js      short loc_18005837F
0x18005832d  test    r14d, r14d
0x180058330  jz      loc_18005850E
0x180058336  cmp     r14d, 1
0x18005833a  jnz     loc_18005855C
0x180058340  mov     rdx, [rsp+1C0h+pv]; lpString1
0x180058345  mov     rbx, [rsp+1C0h+lpString2]
0x18005834a  mov     rcx, rbx; lpString2
0x18005834d  call    PathComparePaths
0x180058352  test    al, 2
0x180058354  jnz     loc_18005847B
0x18005835a  test    dil, dil
0x18005835d  jnz     loc_18005847B
0x180058363  xor     edi, edi
0x180058365  test    rbx, rbx
0x180058368  jz      short loc_180058373
0x18005836a  mov     rcx, rbx; pv
0x18005836d  call    cs:__imp_CoTaskMemFree
0x180058373  add     rsi, 218h
0x18005837a  jmp     loc_18005819B
0x18005837f  mov     rbx, [rsp+1C0h+lpString2]
0x180058384  mov     [rbp+0C0h+var_138], 0
0x18005838c  lea     rcx, [rbp+0C0h+var_138]
0x180058390  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058395  lea     r9, [rbp+0C0h+var_138]
0x180058399  mov     r8d, 8
0x18005839f  mov     rdx, rsi
0x1800583a2  mov     rcx, r13
0x1800583a5  call    ?GetLink@CPersistedTableRegistryStore@@UEAAJPEBGW4AccessCacheOptions@AccessCache@Storage@Windows@@PEAPEAUIShellLinkW@@@Z; CPersistedTableRegistryStore::GetLink(ushort const *,Windows::Storage::AccessCache::AccessCacheOptions,IShellLinkW * *)
0x1800583aa  mov     rcx, [rbp+0C8h]; this
0x1800583b1  test    eax, eax
0x1800583b3  js      loc_18005867D
0x1800583b9  mov     [rbp+0C0h+var_130], 0
0x1800583c1  mov     rcx, [rbp+0C0h+var_138]
0x1800583c5  mov     rax, [rcx]
0x1800583c8  lea     rdx, [rbp+0C0h+var_130]
0x1800583cc  mov     rax, [rax+20h]
0x1800583d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583d5  mov     rcx, [rbp+0C8h]; this
0x1800583dc  test    eax, eax
0x1800583de  js      loc_1800585D3
0x1800583e4  mov     [rsp+1C0h+pidl2], 0
0x1800583ed  lea     rdx, [rsp+1C0h+pidl2]; struct _ITEMIDLIST_ABSOLUTE **
0x1800583f2  mov     rcx, [rbp+0C0h+var_130]; struct _ITEMIDLIST_ABSOLUTE *
0x1800583f6  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800583fb  mov     rcx, [rbp+0C8h]; this
0x180058402  test    eax, eax
0x180058404  js      loc_1800585EC
0x18005840a  test    r14d, r14d
0x18005840d  jz      loc_18005852B
0x180058413  cmp     r14d, 1
0x180058417  jnz     loc_180058605
0x18005841d  mov     rdx, [rsp+1C0h+pidl2]; pidl2
0x180058422  mov     rcx, r12; pidl1
0x180058425  call    ILIsEqual
0x18005842a  test    eax, eax
0x18005842c  setnz   dil
0x180058430  mov     rcx, [rsp+1C0h+pidl2]; pv
0x180058435  mov     [rsp+1C0h+pidl2], 0
0x18005843e  call    cs:__imp_CoTaskMemFree
0x180058444  nop
0x180058445  mov     rcx, [rbp+0C0h+var_130]; pv
0x180058449  mov     [rbp+0C0h+var_130], 0
0x180058451  call    cs:__imp_CoTaskMemFree
0x180058457  nop
0x180058458  mov     rcx, [rbp+0C0h+var_138]
0x18005845c  test    rcx, rcx
0x18005845f  jz      short loc_180058476
0x180058461  mov     [rbp+0C0h+var_138], 0
0x180058469  mov     rax, [rcx]
0x18005846c  mov     rax, [rax+10h]
0x180058470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058475  nop
0x180058476  jmp     loc_18005835A
0x18005847b  mov     r9, [rsp+1C0h+var_170]
0x180058480  mov     r8, rsi
0x180058483  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180058488  mov     edi, eax
0x18005848a  test    eax, eax
0x18005848c  jns     loc_180058363
0x180058492  mov     rcx, [rbp+0C8h]; this
0x180058499  mov     r9d, eax; char *
0x18005849c  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1800584a3  mov     edx, 21Fh; void *
0x1800584a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800584ad  nop
0x1800584ae  xor     esi, esi
0x1800584b0  test    rbx, rbx
0x1800584b3  jz      short loc_1800584BF
0x1800584b5  mov     rcx, rbx; pv
0x1800584b8  call    cs:__imp_CoTaskMemFree
0x1800584be  nop
0x1800584bf  mov     rcx, [rsp+1C0h+pv]; pv
0x1800584c4  test    rcx, rcx
0x1800584c7  jz      short loc_1800584D4
0x1800584c9  call    cs:__imp_CoTaskMemFree
0x1800584cf  mov     [rsp+1C0h+pv], rsi
0x1800584d4  mov     [rsp+1C0h+var_148], rsi
0x1800584d9  mov     [rbp+0C0h+var_140], rsi
0x1800584dd  mov     rcx, [rsp+1C0h+pidl]; pv
0x1800584e2  mov     [rsp+1C0h+pidl], rsi
0x1800584e7  call    cs:__imp_CoTaskMemFree
0x1800584ed  nop
0x1800584ee  mov     rcx, [rsp+1C0h+Token]; Token
0x1800584f3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800584f7  jz      short loc_1800584FF
0x1800584f9  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800584fe  nop
0x1800584ff  mov     rcx, [rsp+1C0h+hKey]
0x180058504  mov     [rsp+1C0h+hKey], rsi
0x180058509  jmp     loc_1800581EC
0x18005850e  mov     rdx, [rsp+1C0h+pv]; lpString1
0x180058513  mov     rbx, [rsp+1C0h+lpString2]
0x180058518  mov     rcx, rbx; lpString2
0x18005851b  call    PathIsEqualOrSubFolder
0x180058520  test    eax, eax
0x180058522  setnz   dil
0x180058526  jmp     loc_18005835A
0x18005852b  mov     rdx, [rsp+1C0h+pidl2]; pidl2
0x180058530  mov     rcx, r12; pidl1
0x180058533  call    ILIsEqual
0x180058538  test    eax, eax
0x18005853a  jnz     short loc_180058554
0x18005853c  xor     r8d, r8d; fImmediate
0x18005853f  mov     rdx, r12; pidl2
0x180058542  mov     rcx, [rsp+1C0h+pidl2]; pidl1
0x180058547  call    ILIsParent
0x18005854c  test    eax, eax
0x18005854e  jz      loc_180058696
0x180058554  mov     dil, 1
0x180058557  jmp     loc_180058430
0x18005855c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180058561  xor     edx, edx
0x180058563  mov     edi, 80070057h
0x180058568  mov     ecx, edi
0x18005856a  call    cs:__imp_RoOriginateError
0x180058570  nop
0x180058571  mov     rcx, [rsp+1C0h+lpString2]; pv
  ... truncated ...
```
