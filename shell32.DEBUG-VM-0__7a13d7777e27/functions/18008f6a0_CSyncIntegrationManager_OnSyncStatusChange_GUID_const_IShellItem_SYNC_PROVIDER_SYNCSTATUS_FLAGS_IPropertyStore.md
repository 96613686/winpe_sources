# CSyncIntegrationManager::OnSyncStatusChange(_GUID const &,IShellItem *,SYNC_PROVIDER_SYNCSTATUS_FLAGS,IPropertyStore *)

- ea: `0x18008f6a0`
- end: `0x18008fbc9`
- name: `?OnSyncStatusChange@CSyncIntegrationManager@@UEAAJAEBU_GUID@@PEAUIShellItem@@W4SYNC_PROVIDER_SYNCSTATUS_FLAGS@@PEAUIPropertyStore@@@Z`
- size: `1321`
- prototype: `int __high(const struct _GUID *, struct IShellItem *, enum SYNC_PROVIDER_SYNCSTATUS_FLAGS, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f05c`
- `0x180015e10`
- `0x180047d00`
- `0x18004a500`
- `0x18008c8d8`
- `0x18008e3cc`
- `0x18008e4d4`
- `0x18008eae8`
- `0x18008f6a0`
- `0x18008fbd0`
- `0x180125da4`
- `0x1801c9738`
- `0x180523bb0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fb3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fb59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fb59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18008fb31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18008fb31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f87b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f896`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f8b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f8c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f87b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f896`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f8b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f8c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008fb18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008fb18`
- `Windows.Storage!ILFree` at `0x18008fb91`
- `Windows.Storage!ILFree` at `0x18008fb91`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008f8f5`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008f8f5`

## pseudocode

```c
__int64 __fastcall CSyncIntegrationManager::OnSyncStatusChange(
        __int64 a1,
        __int64 a2,
        struct IShellItem *a3,
        int a4,
        __int64 a5)
{
  char v5; // si
  __int64 v8; // r13
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  const size_t *v11; // r8
  const size_t *v12; // rdx
  const size_t *v13; // rcx
  bool v14; // bl
  struct IBindCtx *v15; // rdx
  const struct _GUID *v16; // r8
  HRESULT UnaliasedItem; // r15d
  int CacheEntry; // eax
  IUnknown *v19; // rdi
  unsigned __int64 v20; // rsi
  _QWORD *v21; // rbx
  _QWORD *v22; // r12
  __int64 v23; // r13
  const ITEMIDLIST *v24; // rax
  const ITEMIDLIST *v25; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // r14
  int LastError; // eax
  unsigned __int64 i; // rbx
  IUnknown *punk; // [rsp+50h] [rbp-71h] BYREF
  int v32; // [rsp+58h] [rbp-69h] BYREF
  int v33; // [rsp+5Ch] [rbp-65h]
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp-61h] BYREF
  LPVOID v35; // [rsp+68h] [rbp-59h] BYREF
  HANDLE hMutex; // [rsp+70h] [rbp-51h]
  __int64 v37; // [rsp+78h] [rbp-49h]
  LPVOID pv; // [rsp+80h] [rbp-41h] BYREF
  __int64 v39; // [rsp+88h] [rbp-39h]
  __int64 v40; // [rsp+90h] [rbp-31h]
  __int64 v41; // [rsp+98h] [rbp-29h]
  PROPVARIANT pvar; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-19h]
  __int64 v44; // [rsp+B0h] [rbp-11h]
  LPVOID v45; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-1h]
  __int64 v47; // [rsp+C8h] [rbp+7h]
  __int64 v48; // [rsp+D0h] [rbp+Fh]
  __int64 v49; // [rsp+D8h] [rbp+17h]

  v5 = a4;
  v33 = a4;
  v48 = a2;
  v8 = a1;
  v49 = a1;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    lpVtbl = a3->lpVtbl;
    pvar = 0;
    v43 = -1;
    v44 = -1;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, PROPVARIANT *))lpVtbl->GetDisplayName)(
           a3,
           2147844096LL,
           &pvar) >= 0
      || (GetDisplayName = a3->lpVtbl->GetDisplayName,
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pvar),
          v43 = -1,
          v44 = -1,
          ((int (__fastcall *)(struct IShellItem *, __int64, PROPVARIANT *))GetDisplayName)(a3, 2147647488LL, &pvar) >= 0) )
    {
      v32 = 0;
      pv = 0;
      v39 = 0;
      v40 = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      v35 = 0;
      hMutex = 0;
      v37 = 0;
      IPropertyStore_GetUInt32(a5, &PKEY_Sync_ItemState, &v32);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = -1;
      v40 = -1;
      IPropertyStore_GetString(a5, &PKEY_Sync_ItemStatusText, &pv);
      if ( v45 )
      {
        CoTaskMemFree(v45);
        v45 = 0;
      }
      v46 = -1;
      v47 = -1;
      IPropertyStore_GetString(a5, &PKEY_Sync_ItemStatusDescription, &v45);
      if ( v35 )
      {
        CoTaskMemFree(v35);
        v35 = 0;
      }
      hMutex = (HANDLE)-1LL;
      v37 = -1;
      IPropertyStore_GetString(a5, &PKEY_Sync_ItemStatusAction, &v35);
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      {
        v11 = &pszStart;
        v12 = &pszStart;
        v13 = &pszStart;
        if ( v35 )
          v12 = (const size_t *)v35;
        if ( v45 )
          v13 = (const size_t *)v45;
        if ( pv )
          v11 = (const size_t *)pv;
        McTemplateU0jzqqzzz_EventWriteTransfer(
          (_DWORD)v13,
          (_DWORD)v12,
          a2,
          (_DWORD)pvar,
          v5,
          v32,
          (__int64)v11,
          (__int64)v13,
          (__int64)v12);
      }
      if ( v35 )
      {
        CoTaskMemFree(v35);
        v35 = 0;
      }
      hMutex = 0;
      v37 = 0;
      if ( v45 )
      {
        CoTaskMemFree(v45);
        v45 = 0;
      }
      v46 = 0;
      v47 = 0;
      if ( pv )
        CoTaskMemFree(pv);
    }
    if ( pvar )
      CoTaskMemFree(pvar);
  }
  ppidl = 0;
  v14 = 0;
  punk = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punk);
  UnaliasedItem = GetUnaliasedItem(a3, v15, v16, (void **)&punk);
  if ( UnaliasedItem >= 0 )
  {
    UnaliasedItem = SHGetIDListFromObject(punk, &ppidl);
    if ( UnaliasedItem >= 0 )
    {
      v32 = 0;
      v14 = ((unsigned int (__fastcall *)(IUnknown *, __int64, int *))punk->lpVtbl[2].QueryInterface)(
              punk,
              0x40000000,
              &v32) == 0;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punk);
  if ( UnaliasedItem >= 0 )
  {
    punk = 0;
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&punk);
    CacheEntry = CSyncIntegrationManager::_GetCacheEntry(
                   (CSyncIntegrationManager *)(v8 - 8),
                   (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
                   (struct ISyncStatusCacheEntry **)&punk);
    v19 = punk;
    if ( !CacheEntry )
      ((void (__fastcall *)(IUnknown *, __int64, __int64))punk->lpVtbl[4].QueryInterface)(punk, a2, a5);
    if ( v14 && (v5 & 3) != 0 )
    {
      pv = 0;
      v39 = 0;
      v40 = 0;
      v20 = 0;
      v41 = 0;
      Microsoft::WRL::Wrappers::Mutex::Lock(v8 + 160, &v35, 500);
      if ( hMutex )
      {
        if ( ((unsigned int)v35 & 0xFFFFFF7F) == 0 )
        {
          v21 = *(_QWORD **)(v8 + 88);
          v22 = &v21[*(_QWORD *)(v8 + 96)];
          if ( v21 != v22 )
          {
            if ( (v33 & 4) != 0 )
            {
              v23 = v48;
              do
              {
                v24 = (const ITEMIDLIST *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 152LL))(*v21);
                if ( (unsigned __int8)DoesChangeAffectItem(ppidl, v24) )
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v21 + 96LL))(*v21, v23, a5);
                ++v21;
              }
              while ( v21 != v22 );
              v8 = v49;
            }
            else
            {
              do
              {
                v25 = (const ITEMIDLIST *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 152LL))(*v21);
                if ( (unsigned __int8)DoesChangeAffectItem(ppidl, v25) )
                  AddEntryToArray(&pv, v21);
                ++v21;
              }
              while ( v21 != v22 );
              v20 = v39;
            }
            v19 = punk;
          }
          LOWORD(pvar) = 0;
          if ( v19 )
          {
            if ( ((int (__fastcall *)(IUnknown *, __int128 *, PROPVARIANT *))v19->lpVtbl[1].Release)(
                   v19,
                   &PKEY_Sync_ItemState,
                   &pvar) >= 0
              && (_WORD)pvar == 19
              && (_DWORD)v43 == 3 )
            {
              v26 = *(_QWORD **)(v8 + 88);
              v27 = &v26[*(_QWORD *)(v8 + 96)];
              if ( v26 != v27 )
              {
                do
                {
                  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, LPITEMIDLIST))(*(_QWORD *)*v26 + 136LL))(*v26, ppidl)
                    && (*(unsigned __int8 (__fastcall **)(_QWORD, LPITEMIDLIST))(*(_QWORD *)*v26 + 160LL))(*v26, ppidl) )
                  {
                    AddEntryToArray(&pv, v26);
                  }
                  ++v26;
                }
                while ( v26 != v27 );
                v20 = v39;
              }
            }
          }
          PropVariantClear(&pvar);
        }
        if ( hMutex && ((unsigned int)v35 & 0xFFFFFF7F) == 0 && !ReleaseMutex(hMutex) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RaiseException(LastError, 1u, 0, 0);
          __debugbreak();
        }
      }
      for ( i = 0; i < v20; ++i )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + i) + 104LL))(*((_QWORD *)pv + i));
      CTSimpleArray<Microsoft::WRL::ComPtr<ISyncStatusProviderInfo>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ISyncStatusProviderInfo>>,CISyncStatusProviderInfoComparer,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ISyncStatusProviderInfo>>>::RemoveAll(&pv);
    }
    ILFree(ppidl);
    if ( v19 )
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
  }
  return (unsigned int)UnaliasedItem;
}

```

## disassembly

```asm
0x18008f6a0  mov     [rsp-8+arg_18], rbx
0x18008f6a5  push    rbp
0x18008f6a6  push    rsi
0x18008f6a7  push    rdi
0x18008f6a8  push    r12
0x18008f6aa  push    r13
0x18008f6ac  push    r14
0x18008f6ae  push    r15
0x18008f6b0  lea     rbp, [rsp-1Fh]
0x18008f6b5  sub     rsp, 0E0h
0x18008f6bc  mov     r14, [rbp+4Fh+arg_20]
0x18008f6c0  xor     r15d, r15d
0x18008f6c3  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18008f6ca  mov     esi, r9d
0x18008f6cd  mov     [rbp+4Fh+var_B4], r9d
0x18008f6d1  mov     rdi, r8
0x18008f6d4  mov     r12, rdx
0x18008f6d7  mov     [rbp+4Fh+var_40], rdx
0x18008f6db  mov     r13, rcx
0x18008f6de  mov     [rbp+4Fh+var_38], rcx
0x18008f6e2  jz      loc_18008F8C6
0x18008f6e8  mov     rax, [r8]
0x18008f6eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008f6ef  lea     r8, [rbp+4Fh+pvar]
0x18008f6f3  mov     [rbp+4Fh+pvar], r15
0x18008f6f7  mov     edx, 80058000h
0x18008f6fc  mov     [rbp+4Fh+var_68], rbx
0x18008f700  mov     rcx, rdi
0x18008f703  mov     [rbp+4Fh+var_60], rbx
0x18008f707  mov     rax, [rax+28h]
0x18008f70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f710  test    eax, eax
0x18008f712  jns     short loc_18008F750
0x18008f714  mov     rax, [rdi]
0x18008f717  lea     rcx, [rbp+4Fh+pvar]; void *
0x18008f71b  mov     rbx, [rax+28h]
0x18008f71f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008f724  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008f728  lea     r8, [rbp+4Fh+pvar]
0x18008f72c  mov     [rbp+4Fh+var_68], rax
0x18008f730  mov     edx, 80028000h
0x18008f735  mov     [rbp+4Fh+var_60], rax
0x18008f739  mov     rcx, rdi
0x18008f73c  mov     rax, rbx
0x18008f73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f744  test    eax, eax
0x18008f746  js      loc_18008F8B7
0x18008f74c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008f750  lea     r8, [rbp+4Fh+var_B8]
0x18008f754  mov     [rbp+4Fh+var_B8], r15d
0x18008f758  lea     rdx, PKEY_Sync_ItemState
0x18008f75f  mov     [rbp+4Fh+pv], r15
0x18008f763  mov     rcx, r14
0x18008f766  mov     [rbp+4Fh+var_88], r15
0x18008f76a  mov     [rbp+4Fh+var_80], r15
0x18008f76e  mov     [rbp+4Fh+var_58], r15
0x18008f772  mov     [rbp+4Fh+var_50], r15
0x18008f776  mov     [rbp+4Fh+var_48], r15
0x18008f77a  mov     [rbp+4Fh+var_A8], r15
0x18008f77e  mov     [rbp+4Fh+hMutex], r15
0x18008f782  mov     [rbp+4Fh+var_98], r15
0x18008f786  call    IPropertyStore_GetUInt32
0x18008f78b  mov     rcx, [rbp+4Fh+pv]; pv
0x18008f78f  test    rcx, rcx
0x18008f792  jz      short loc_18008F79E
0x18008f794  call    cs:__imp_CoTaskMemFree
0x18008f79a  mov     [rbp+4Fh+pv], r15
0x18008f79e  lea     r8, [rbp+4Fh+pv]
0x18008f7a2  mov     [rbp+4Fh+var_88], rbx
0x18008f7a6  lea     rdx, PKEY_Sync_ItemStatusText
0x18008f7ad  mov     [rbp+4Fh+var_80], rbx
0x18008f7b1  mov     rcx, r14
0x18008f7b4  call    IPropertyStore_GetString
0x18008f7b9  mov     rcx, [rbp+4Fh+var_58]; pv
0x18008f7bd  test    rcx, rcx
0x18008f7c0  jz      short loc_18008F7CC
0x18008f7c2  call    cs:__imp_CoTaskMemFree
0x18008f7c8  mov     [rbp+4Fh+var_58], r15
0x18008f7cc  lea     r8, [rbp+4Fh+var_58]
0x18008f7d0  mov     [rbp+4Fh+var_50], rbx
0x18008f7d4  lea     rdx, PKEY_Sync_ItemStatusDescription
0x18008f7db  mov     [rbp+4Fh+var_48], rbx
0x18008f7df  mov     rcx, r14
0x18008f7e2  call    IPropertyStore_GetString
0x18008f7e7  mov     rcx, [rbp+4Fh+var_A8]; pv
0x18008f7eb  test    rcx, rcx
0x18008f7ee  jz      short loc_18008F7FA
0x18008f7f0  call    cs:__imp_CoTaskMemFree
0x18008f7f6  mov     [rbp+4Fh+var_A8], r15
0x18008f7fa  lea     r8, [rbp+4Fh+var_A8]
0x18008f7fe  mov     [rbp+4Fh+hMutex], rbx
0x18008f802  lea     rdx, PKEY_Sync_ItemStatusAction
0x18008f809  mov     [rbp+4Fh+var_98], rbx
0x18008f80d  mov     rcx, r14
0x18008f810  call    IPropertyStore_GetString
0x18008f815  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18008f81c  jz      short loc_18008F872
0x18008f81e  mov     rax, [rbp+4Fh+var_A8]
0x18008f822  lea     r8, pszStart
0x18008f829  mov     r9, [rbp+4Fh+pvar]
0x18008f82d  test    rax, rax
0x18008f830  mov     rdx, r8
0x18008f833  mov     rcx, r8
0x18008f836  cmovnz  rdx, rax
0x18008f83a  mov     rax, [rbp+4Fh+var_58]
0x18008f83e  test    rax, rax
0x18008f841  mov     [rsp+110h+var_D0], rdx
0x18008f846  cmovnz  rcx, rax
0x18008f84a  mov     rax, [rbp+4Fh+pv]
0x18008f84e  mov     [rsp+110h+var_D8], rcx
0x18008f853  test    rax, rax
0x18008f856  cmovnz  r8, rax
0x18008f85a  mov     eax, [rbp+4Fh+var_B8]
0x18008f85d  mov     [rsp+110h+var_E0], r8
0x18008f862  mov     r8, r12
0x18008f865  mov     [rsp+110h+var_E8], eax
0x18008f869  mov     [rsp+110h+var_F0], esi
0x18008f86d  call    McTemplateU0jzqqzzz_EventWriteTransfer
0x18008f872  mov     rcx, [rbp+4Fh+var_A8]; pv
0x18008f876  test    rcx, rcx
0x18008f879  jz      short loc_18008F885
0x18008f87b  call    cs:__imp_CoTaskMemFree
0x18008f881  mov     [rbp+4Fh+var_A8], r15
0x18008f885  mov     rcx, [rbp+4Fh+var_58]; pv
0x18008f889  mov     [rbp+4Fh+hMutex], r15
0x18008f88d  mov     [rbp+4Fh+var_98], r15
0x18008f891  test    rcx, rcx
0x18008f894  jz      short loc_18008F8A0
0x18008f896  call    cs:__imp_CoTaskMemFree
0x18008f89c  mov     [rbp+4Fh+var_58], r15
0x18008f8a0  mov     rcx, [rbp+4Fh+pv]; pv
0x18008f8a4  mov     [rbp+4Fh+var_50], r15
0x18008f8a8  mov     [rbp+4Fh+var_48], r15
0x18008f8ac  test    rcx, rcx
0x18008f8af  jz      short loc_18008F8B7
0x18008f8b1  call    cs:__imp_CoTaskMemFree
0x18008f8b7  mov     rcx, [rbp+4Fh+pvar]; pv
0x18008f8bb  test    rcx, rcx
0x18008f8be  jz      short loc_18008F8C6
0x18008f8c0  call    cs:__imp_CoTaskMemFree
0x18008f8c6  lea     rcx, [rbp+4Fh+punk]
0x18008f8ca  mov     [rbp+4Fh+ppidl], r15
0x18008f8ce  mov     bl, r15b
0x18008f8d1  mov     [rbp+4Fh+punk], r15
0x18008f8d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f8da  lea     r9, [rbp+4Fh+punk]; void **
0x18008f8de  mov     rcx, rdi; struct IShellItem *
0x18008f8e1  call    ?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)
0x18008f8e6  mov     r15d, eax
0x18008f8e9  test    eax, eax
0x18008f8eb  js      short loc_18008F927
0x18008f8ed  mov     rcx, [rbp+4Fh+punk]; punk
0x18008f8f1  lea     rdx, [rbp+4Fh+ppidl]; ppidl
0x18008f8f5  call    cs:__imp_SHGetIDListFromObject
0x18008f8fb  mov     r15d, eax
0x18008f8fe  test    eax, eax
0x18008f900  js      short loc_18008F927
0x18008f902  mov     rcx, [rbp+4Fh+punk]
0x18008f906  lea     r8, [rbp+4Fh+var_B8]
0x18008f90a  mov     [rbp+4Fh+var_B8], 0
0x18008f911  mov     edx, 40000000h
0x18008f916  mov     rax, [rcx]
0x18008f919  mov     rax, [rax+30h]
0x18008f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f922  test    eax, eax
0x18008f924  setz    bl
0x18008f927  lea     rcx, [rbp+4Fh+punk]
0x18008f92b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f930  test    r15d, r15d
0x18008f933  js      loc_18008FBAB
0x18008f939  lea     rcx, [rbp+4Fh+punk]
0x18008f93d  mov     [rbp+4Fh+punk], 0
0x18008f945  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18008f94a  mov     rdx, [rbp+4Fh+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x18008f94e  lea     rcx, [r13-8]; this
0x18008f952  lea     r8, [rbp+4Fh+punk]; struct ISyncStatusCacheEntry **
0x18008f956  call    ?_GetCacheEntry@CSyncIntegrationManager@@AEBAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUISyncStatusCacheEntry@@@Z; CSyncIntegrationManager::_GetCacheEntry(_ITEMIDLIST_ABSOLUTE const *,ISyncStatusCacheEntry * *)
0x18008f95b  mov     rdi, [rbp+4Fh+punk]
0x18008f95f  test    eax, eax
0x18008f961  jnz     short loc_18008F978
0x18008f963  mov     rax, [rdi]
0x18008f966  mov     r8, r14
0x18008f969  mov     rdx, r12
0x18008f96c  mov     rcx, rdi
0x18008f96f  mov     rax, [rax+60h]
0x18008f973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f978  xor     r12d, r12d
0x18008f97b  test    bl, bl
0x18008f97d  jz      loc_18008FB8D
0x18008f983  test    sil, 3
0x18008f987  jz      loc_18008FB8D
0x18008f98d  lea     rcx, [r13+0A0h]
0x18008f994  mov     [rbp+4Fh+pv], r12
0x18008f998  mov     r8d, 1F4h
0x18008f99e  mov     [rbp+4Fh+var_88], r12
0x18008f9a2  lea     rdx, [rbp+4Fh+var_A8]
0x18008f9a6  mov     [rbp+4Fh+var_80], r12
0x18008f9aa  mov     esi, r12d
0x18008f9ad  mov     [rbp+4Fh+var_78], r12
0x18008f9b1  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Mutex::Lock(ulong)
0x18008f9b6  cmp     [rbp+4Fh+hMutex], r12
0x18008f9ba  jz      loc_18008FB60
0x18008f9c0  test    dword ptr [rbp+4Fh+var_A8], 0FFFFFF7Fh
0x18008f9c7  jnz     loc_18008FB1E
0x18008f9cd  mov     rbx, [r13+58h]
0x18008f9d1  mov     rax, [r13+60h]
0x18008f9d5  lea     r12, [rbx+rax*8]
0x18008f9d9  cmp     rbx, r12
0x18008f9dc  jz      loc_18008FA7A
0x18008f9e2  mov     edi, [rbp+4Fh+var_B4]
0x18008f9e5  test    dil, 4
0x18008f9e9  jz      short loc_18008FA38
0x18008f9eb  mov     r13, [rbp+4Fh+var_40]
0x18008f9ef  mov     rcx, [rbx]
0x18008f9f2  mov     rax, [rcx]
0x18008f9f5  mov     rax, [rax+98h]
0x18008f9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa01  mov     rcx, [rbp+4Fh+ppidl]; pidl2
0x18008fa05  mov     r8d, edi
0x18008fa08  mov     rdx, rax; pidl1
0x18008fa0b  call    _DoesChangeAffectItem
0x18008fa10  test    al, al
0x18008fa12  jz      short loc_18008FA29
0x18008fa14  mov     rcx, [rbx]
0x18008fa17  mov     r8, r14
0x18008fa1a  mov     rdx, r13
0x18008fa1d  mov     rax, [rcx]
0x18008fa20  mov     rax, [rax+60h]
0x18008fa24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa29  add     rbx, 8
0x18008fa2d  cmp     rbx, r12
0x18008fa30  jnz     short loc_18008F9EF
0x18008fa32  mov     r13, [rbp+4Fh+var_38]
0x18008fa36  jmp     short loc_18008FA76
0x18008fa38  mov     rcx, [rbx]
0x18008fa3b  mov     rax, [rcx]
0x18008fa3e  mov     rax, [rax+98h]
0x18008fa45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa4a  mov     rcx, [rbp+4Fh+ppidl]; pidl2
0x18008fa4e  mov     r8d, edi
0x18008fa51  mov     rdx, rax; pidl1
0x18008fa54  call    _DoesChangeAffectItem
0x18008fa59  test    al, al
0x18008fa5b  jz      short loc_18008FA69
0x18008fa5d  mov     rdx, rbx
0x18008fa60  lea     rcx, [rbp+4Fh+pv]
0x18008fa64  call    _AddEntryToArray
0x18008fa69  add     rbx, 8
0x18008fa6d  cmp     rbx, r12
0x18008fa70  jnz     short loc_18008FA38
0x18008fa72  mov     rsi, [rbp+4Fh+var_88]
0x18008fa76  mov     rdi, [rbp+4Fh+punk]
0x18008fa7a  xor     r12d, r12d
0x18008fa7d  mov     word ptr [rbp+4Fh+pvar], r12w
0x18008fa82  test    rdi, rdi
0x18008fa85  jz      loc_18008FB14
0x18008fa8b  mov     rax, [rdi]
0x18008fa8e  lea     r8, [rbp+4Fh+pvar]
0x18008fa92  lea     rdx, PKEY_Sync_ItemState
0x18008fa99  mov     rcx, rdi
0x18008fa9c  mov     rax, [rax+28h]
0x18008faa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008faa5  test    eax, eax
0x18008faa7  js      short loc_18008FB14
0x18008faa9  cmp     word ptr [rbp+4Fh+pvar], 13h
0x18008faae  jnz     short loc_18008FB14
0x18008fab0  cmp     dword ptr [rbp+4Fh+var_68], 3
0x18008fab4  jnz     short loc_18008FB14
0x18008fab6  mov     rbx, [r13+58h]
0x18008faba  mov     rax, [r13+60h]
0x18008fabe  lea     r14, [rbx+rax*8]
0x18008fac2  cmp     rbx, r14
0x18008fac5  jz      short loc_18008FB14
0x18008fac7  mov     rcx, [rbx]
0x18008faca  mov     rdx, [rbp+4Fh+ppidl]
0x18008face  mov     rax, [rcx]
0x18008fad1  mov     rax, [rax+88h]
0x18008fad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fadd  test    al, al
0x18008fadf  jnz     short loc_18008FB07
0x18008fae1  mov     rcx, [rbx]
0x18008fae4  mov     rdx, [rbp+4Fh+ppidl]
0x18008fae8  mov     rax, [rcx]
0x18008faeb  mov     rax, [rax+0A0h]
0x18008faf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008faf7  test    al, al
0x18008faf9  jz      short loc_18008FB07
0x18008fafb  mov     rdx, rbx
0x18008fafe  lea     rcx, [rbp+4Fh+pv]
0x18008fb02  call    _AddEntryToArray
0x18008fb07  add     rbx, 8
0x18008fb0b  cmp     rbx, r14
0x18008fb0e  jnz     short loc_18008FAC7
0x18008fb10  mov     rsi, [rbp+4Fh+var_88]
0x18008fb14  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18008fb18  call    cs:__imp_PropVariantClear
0x18008fb1e  cmp     [rbp+4Fh+hMutex], r12
0x18008fb22  jz      short loc_18008FB60
0x18008fb24  test    dword ptr [rbp+4Fh+var_A8], 0FFFFFF7Fh
0x18008fb2b  jnz     short loc_18008FB60
  ... truncated ...
```
