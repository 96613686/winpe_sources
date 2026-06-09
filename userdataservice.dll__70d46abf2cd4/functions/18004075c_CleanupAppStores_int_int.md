# CleanupAppStores(int,int)

- ea: `0x18004075c`
- end: `0x180040d91`
- name: `?CleanupAppStores@@YAJHH@Z`
- size: `1589`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004038c`
- `0x1800ae8a0`

## callees

- `0x180004658`
- `0x180005c2c`
- `0x180008ee8`
- `0x180008f0c`
- `0x180011838`
- `0x180012988`
- `0x180032a4c`
- `0x180039678`
- `0x18003ffb0`
- `0x18004075c`
- `0x180040d98`
- `0x180041ff8`
- `0x180084a84`
- `0x1800977c4`
- `0x1800ac25c`
- `0x1800ac3c8`
- `0x180118444`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x1800407e7`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x1800407e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b92`
- `unistore!RemoveStaleChangeTrackingDataOnStore` at `0x180040ba8`
- `unistore!RemoveStaleChangeTrackingDataOnStore` at `0x180040ba8`

## string_xrefs

- `0x1800407c3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800407f9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040839`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040879`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040bbe`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040c25`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040c6a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040c94`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040ce6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180040d59`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall CleanupAppStores(int a1)
{
  AppInstanceCache *v2; // rax
  struct AppInstanceCache *v3; // rax
  struct AppInstanceCache *v4; // r12
  int v5; // eax
  unsigned int AsyncName__lambda_c768481704f013017fa2cab7299eb2aa; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64, _DWORD *, __int16, __int64); // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r9
  __int64 i; // r15
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdi
  unsigned int ShouldCleanupAppData; // ebx
  __int64 v20; // rdx
  int v21; // edi
  __int64 v22; // rdx
  bool v23; // sf
  HLOCAL v24; // rcx
  unsigned __int16 *v25; // r8
  int v26; // edx
  int v27; // r9d
  int v28; // eax
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v33; // [rsp+40h] [rbp-79h] BYREF
  __int64 v34; // [rsp+48h] [rbp-71h] BYREF
  __int64 v35; // [rsp+50h] [rbp-69h] BYREF
  __int64 v36; // [rsp+58h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-59h] BYREF
  __int64 v38; // [rsp+68h] [rbp-51h] BYREF
  __int64 v39; // [rsp+70h] [rbp-49h] BYREF
  __int64 v40; // [rsp+78h] [rbp-41h] BYREF
  __int64 v41; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v42; // [rsp+88h] [rbp-31h]
  _QWORD v43[3]; // [rsp+90h] [rbp-29h] BYREF
  _DWORD v44[6]; // [rsp+A8h] [rbp-11h] BYREF

  v2 = (AppInstanceCache *)operator new(0x28u);
  if ( !v2 || (v3 = AppInstanceCache::AppInstanceCache(v2), (v4 = v3) == 0) )
  {
    AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      382);
    return AsyncName__lambda_c768481704f013017fa2cab7299eb2aa;
  }
  v5 = CleanupStoreGroupings(v3, 0);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v5;
  if ( v5 < 0 )
  {
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      385);
    goto LABEL_77;
  }
  v35 = 0;
  v7 = POutlookAppManager_CreateInstance(&v35);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v7;
  if ( v7 < 0 )
  {
    Log_HREvent(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      388);
LABEL_76:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
    goto LABEL_77;
  }
  v34 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 32LL))(v35, &v34);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v8;
  if ( v8 < 0 )
  {
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      391);
LABEL_75:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
    goto LABEL_76;
  }
  v36 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 88LL))(v34, &v36);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v9;
  if ( v9 < 0 )
  {
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      394);
LABEL_74:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
    goto LABEL_75;
  }
  v10 = v36;
  v44[0] = 280035359;
  v44[1] = 280100928;
  v44[2] = 280166431;
  v44[3] = 280559647;
  v44[4] = 805371935;
  v44[5] = 939524107;
  v33 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _DWORD *, __int16, __int64))(*(_QWORD *)v36 + 120LL);
  v12 = tlx::replace<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v33);
  v13 = v11(v10, 1, 0xFFFFFFFFLL, v44, 6, v12);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v13;
  if ( v13 < 0 )
  {
    v14 = 406;
LABEL_72:
    Log_HREvent(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v14);
LABEL_73:
    tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v33);
    goto LABEL_74;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v16 = v33;
    if ( (unsigned int)i >= *(_DWORD *)v33 )
    {
      v13 = CleanupEmptyGroupings();
      AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v13;
      if ( v13 >= 0 )
      {
        tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v33);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
        tlx::_delete<AppInstanceCache>(v4);
        return 0;
      }
      v14 = 530;
      goto LABEL_72;
    }
    v17 = *(_QWORD *)(*(_QWORD *)(v33 + 24) + 8 * i);
    if ( (*(_WORD *)(v17 + 6) & 0x300) != 0 )
    {
      if ( (*(_WORD *)(v17 + 54) & 0x300) != 0 )
      {
        v18 = 0;
        ShouldCleanupAppData = 0;
      }
      else
      {
        v18 = *(_QWORD *)(v17 + 56);
        ShouldCleanupAppData = 5;
      }
    }
    else
    {
      v18 = *(_QWORD *)(v17 + 8);
      if ( (*(_WORD *)(v17 + 30) & 0x300) != 0 )
      {
        ShouldCleanupAppData = 6;
      }
      else
      {
        ShouldCleanupAppData = AppInstanceCache::ShouldCleanupAppData(v4, *(_QWORD *)(v17 + 8), v17 + 32);
        v16 = v33;
      }
    }
    v20 = *(_QWORD *)(*(_QWORD *)(v16 + 24) + 8 * i);
    if ( (*(_WORD *)(v20 + 126) & 0x300) == 0 )
    {
      if ( *(_DWORD *)(v20 + 128) )
        break;
    }
    if ( ShouldCleanupAppData )
      goto LABEL_26;
    if ( a1 && v18 && (*(_WORD *)(v20 + 102) & 0x300) == 0 )
    {
      hMem = 0;
      if ( (*(_WORD *)(v20 + 78) & 0x300) != 0 )
        v22 = 0;
      else
        v22 = *(_QWORD *)(v20 + 80);
      v23 = (int)GetDisplayNameFromPackageFamilyNameAndPraid(v18, v22, &hMem) < 0;
      v16 = v33;
      if ( v23 )
        goto LABEL_52;
      v24 = hMem;
      v25 = (unsigned __int16 *)hMem;
      do
      {
        v26 = *(unsigned __int16 *)((char *)v25
                                  + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v33 + 24) + 8 * i) + 104LL)
                                  - (_QWORD)hMem);
        v27 = *v25 - v26;
        if ( v27 )
          break;
        ++v25;
      }
      while ( v26 );
      if ( v27 )
      {
        v38 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v34 + 112LL))(
                v34,
                *(_QWORD *)(v33 + 8) + 12 * i,
                &v38);
        AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v28;
        if ( v28 < 0 )
        {
          v30 = 475;
          goto LABEL_63;
        }
        v43[1] = hMem;
        v43[0] = 805371935;
        v43[2] = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *))(*(_QWORD *)v38 + 88LL))(v38, 0, 1, v43);
        AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v28;
        if ( v28 < 0 )
        {
          v30 = 481;
          goto LABEL_63;
        }
        v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 176LL))(v38);
        AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v28;
        if ( v28 < 0 )
        {
          v30 = 482;
LABEL_63:
          Log_HREvent(
            (unsigned int)v28,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            v30);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&hMem);
          goto LABEL_73;
        }
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
        v16 = v33;
LABEL_52:
        v24 = hMem;
      }
      if ( v24 )
      {
        LocalFree(v24);
        v16 = v33;
      }
    }
    v29 = RemoveStaleChangeTrackingDataOnStore(*(_QWORD *)(v16 + 8) + 12 * i);
    AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v29;
    if ( v29 < 0 )
    {
      Log_HREvent(
        (unsigned int)v29,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        487);
      tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v33);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      goto LABEL_77;
    }
LABEL_35:
    ;
  }
  if ( !ShouldCleanupAppData )
    ShouldCleanupAppData = 7;
LABEL_26:
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x100000) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      AppStoreDeleted,
      v18,
      ShouldCleanupAppData);
    v16 = v33;
  }
  v39 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v34 + 112LL))(
          v34,
          *(_QWORD *)(v16 + 8) + 12 * i,
          &v39);
  if ( v21 >= 0 )
  {
    if ( ShouldCleanupAppData != 7 )
    {
      v21 = ResetAppStoreData(v39);
      if ( v21 < 0 )
      {
        v31 = 499;
        goto LABEL_69;
      }
    }
    v40 = 0;
    v41 = v39;
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    v42 = ShouldCleanupAppData;
    AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = MakeAsync__GenericMakeAsyncName__lambda_c768481704f013017fa2cab7299eb2aa___(
                                                           &v40,
                                                           &v41);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v41);
    if ( (AsyncName__lambda_c768481704f013017fa2cab7299eb2aa & 0x80000000) != 0 )
    {
      Log_HREvent(
        AsyncName__lambda_c768481704f013017fa2cab7299eb2aa,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        515);
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v40);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
      goto LABEL_73;
    }
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v40);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
    goto LABEL_35;
  }
  v31 = 495;
LABEL_69:
  Log_HREvent(
    (unsigned int)v21,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
    v31);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
  tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v33);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
  AsyncName__lambda_c768481704f013017fa2cab7299eb2aa = v21;
LABEL_77:
  tlx::_delete<AppInstanceCache>(v4);
  return AsyncName__lambda_c768481704f013017fa2cab7299eb2aa;
}

```

## disassembly

```asm
0x18004075c  push    rbp
0x18004075e  push    rbx
0x18004075f  push    rsi
0x180040760  push    rdi
0x180040761  push    r12
0x180040763  push    r13
0x180040765  push    r14
0x180040767  push    r15
0x180040769  lea     rbp, [rsp-1Fh]
0x18004076e  sub     rsp, 0D8h
0x180040775  mov     rax, cs:__security_cookie
0x18004077c  xor     rax, rsp
0x18004077f  mov     [rbp+57h+var_50], rax
0x180040783  mov     r13d, ecx
0x180040786  mov     ecx, 28h ; '('; Size
0x18004078b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040790  test    rax, rax
0x180040793  jz      loc_180040D54
0x180040799  mov     rcx, rax; this
0x18004079c  call    ??0AppInstanceCache@@QEAA@XZ; AppInstanceCache::AppInstanceCache(void)
0x1800407a1  mov     r12, rax
0x1800407a4  test    rax, rax
0x1800407a7  jz      loc_180040D54
0x1800407ad  xor     edx, edx; unsigned __int16 *
0x1800407af  mov     rcx, rax; struct AppInstanceCache *
0x1800407b2  call    ?CleanupStoreGroupings@@YAJPEAVAppInstanceCache@@PEBG@Z; CleanupStoreGroupings(AppInstanceCache *,ushort const *)
0x1800407b7  mov     ebx, eax
0x1800407b9  test    eax, eax
0x1800407bb  jns     short loc_1800407DB
0x1800407bd  mov     r9d, 181h
0x1800407c3  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800407ca  mov     edx, 1
0x1800407cf  mov     ecx, eax
0x1800407d1  call    Log_HREvent
0x1800407d6  jmp     loc_180040D1A
0x1800407db  lea     rcx, [rbp+57h+var_C0]
0x1800407df  mov     [rbp+57h+var_C0], 0
0x1800407e7  call    cs:__imp_POutlookAppManager_CreateInstance
0x1800407ed  mov     ebx, eax
0x1800407ef  test    eax, eax
0x1800407f1  jns     short loc_180040811
0x1800407f3  mov     r9d, 184h
0x1800407f9  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040800  mov     edx, 1
0x180040805  mov     ecx, eax
0x180040807  call    Log_HREvent
0x18004080c  jmp     loc_180040D11
0x180040811  mov     rcx, [rbp+57h+var_C0]
0x180040815  lea     rdx, [rbp+57h+var_C8]
0x180040819  mov     [rbp+57h+var_C8], 0
0x180040821  mov     rax, [rcx]
0x180040824  mov     rax, [rax+20h]
0x180040828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004082d  mov     ebx, eax
0x18004082f  test    eax, eax
0x180040831  jns     short loc_180040851
0x180040833  mov     r9d, 187h
0x180040839  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040840  mov     edx, 1
0x180040845  mov     ecx, eax
0x180040847  call    Log_HREvent
0x18004084c  jmp     loc_180040D08
0x180040851  mov     rcx, [rbp+57h+var_C8]
0x180040855  lea     rdx, [rbp+57h+var_B8]
0x180040859  mov     [rbp+57h+var_B8], 0
0x180040861  mov     rax, [rcx]
0x180040864  mov     rax, [rax+58h]
0x180040868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004086d  mov     ebx, eax
0x18004086f  test    eax, eax
0x180040871  jns     short loc_180040891
0x180040873  mov     r9d, 18Ah
0x180040879  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040880  mov     edx, 1
0x180040885  mov     ecx, eax
0x180040887  call    Log_HREvent
0x18004088c  jmp     loc_180040CFF
0x180040891  mov     rdi, [rbp+57h+var_B8]
0x180040895  lea     rcx, [rbp+57h+var_D0]
0x180040899  mov     [rbp+57h+var_68], 10B1001Fh
0x1800408a0  mov     [rbp+57h+var_64], 10B20040h
0x1800408a7  mov     [rbp+57h+var_60], 10B3001Fh
0x1800408ae  mov     [rbp+57h+var_5C], 10B9001Fh
0x1800408b5  mov     [rbp+57h+var_58], 3001001Fh
0x1800408bc  mov     [rbp+57h+var_54], 3800000Bh
0x1800408c3  mov     [rbp+57h+var_D0], 0
0x1800408cb  mov     rax, [rdi]
0x1800408ce  mov     rbx, [rax+78h]
0x1800408d2  call    ??$replace@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@YAPEAPEAU_USPROPVALBATCH@@AEAV?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@0@@Z; tlx::replace<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0> &)
0x1800408d7  mov     [rsp+110h+var_E8], rax
0x1800408dc  lea     r9, [rbp+57h+var_68]
0x1800408e0  mov     esi, 1
0x1800408e5  mov     [rsp+110h+var_F0], 6
0x1800408ec  mov     edx, esi
0x1800408ee  mov     rax, rbx
0x1800408f1  or      r8d, 0FFFFFFFFh
0x1800408f5  mov     rcx, rdi
0x1800408f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408fd  mov     ebx, eax
0x1800408ff  test    eax, eax
0x180040901  jns     short loc_18004090E
0x180040903  mov     r9d, 196h
0x180040909  jmp     loc_180040CE6
0x18004090e  xor     r15d, r15d
0x180040911  mov     rax, [rbp+57h+var_D0]
0x180040915  mov     r8d, 300h
0x18004091b  cmp     r15d, [rax]
0x18004091e  jnb     loc_180040CD5
0x180040924  mov     rcx, [rax+18h]
0x180040928  mov     rdx, [rcx+r15*8]
0x18004092c  test    [rdx+6], r8w
0x180040931  jnz     short loc_180040962
0x180040933  mov     rdi, [rdx+8]
0x180040937  test    [rdx+1Eh], r8w
0x18004093c  jnz     short loc_18004095B
0x18004093e  lea     r8, [rdx+20h]
0x180040942  mov     rcx, r12
0x180040945  mov     rdx, rdi
0x180040948  call    ?ShouldCleanupAppData@AppInstanceCache@@QEAA?AW4AppDataCleanupReason@@PEBGAEBU_FILETIME@@@Z; AppInstanceCache::ShouldCleanupAppData(ushort const *,_FILETIME const &)
0x18004094d  mov     ebx, eax
0x18004094f  mov     r8d, 300h
0x180040955  mov     rax, [rbp+57h+var_D0]
0x180040959  jmp     short loc_180040978
0x18004095b  mov     ebx, 6
0x180040960  jmp     short loc_180040978
0x180040962  test    [rdx+36h], r8w
0x180040967  jnz     short loc_180040974
0x180040969  mov     rdi, [rdx+38h]
0x18004096d  mov     ebx, 5
0x180040972  jmp     short loc_180040978
0x180040974  xor     edi, edi
0x180040976  xor     ebx, ebx
0x180040978  mov     rcx, [rax+18h]
0x18004097c  mov     rdx, [rcx+r15*8]
0x180040980  test    [rdx+7Eh], r8w
0x180040985  jnz     loc_180040A6F
0x18004098b  cmp     dword ptr [rdx+80h], 0
0x180040992  jz      loc_180040A6F
0x180040998  test    ebx, ebx
0x18004099a  jnz     short loc_1800409A1
0x18004099c  mov     ebx, 7
0x1800409a1  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 10h
0x1800409a8  jz      short loc_1800409C7
0x1800409aa  mov     r9d, ebx
0x1800409ad  lea     rdx, AppStoreDeleted
0x1800409b4  mov     r8, rdi
0x1800409b7  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x1800409be  call    McTemplateU0zq_EventWriteTransfer
0x1800409c3  mov     rax, [rbp+57h+var_D0]
0x1800409c7  mov     rcx, [rbp+57h+var_C8]
0x1800409cb  lea     r8, [r15+r15*2]
0x1800409cf  mov     [rbp+57h+var_A0], 0
0x1800409d7  mov     rdx, [rax+8]
0x1800409db  mov     r9, [rcx]
0x1800409de  lea     rdx, [rdx+r8*4]
0x1800409e2  lea     r8, [rbp+57h+var_A0]
0x1800409e6  mov     rax, [r9+70h]
0x1800409ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409ef  mov     edi, eax
0x1800409f1  test    eax, eax
0x1800409f3  js      loc_180040C8E
0x1800409f9  cmp     ebx, 7
0x1800409fc  jz      short loc_180040A11
0x1800409fe  mov     rcx, [rbp+57h+var_A0]
0x180040a02  call    ResetAppStoreData
0x180040a07  mov     edi, eax
0x180040a09  test    eax, eax
0x180040a0b  js      loc_180040C5C
0x180040a11  mov     rcx, [rbp+57h+var_A0]
0x180040a15  mov     [rbp+57h+var_98], 0
0x180040a1d  mov     [rbp+57h+var_90], rcx
0x180040a21  test    rcx, rcx
0x180040a24  jz      short loc_180040A32
0x180040a26  mov     rax, [rcx]
0x180040a29  mov     rax, [rax+8]
0x180040a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a32  lea     rdx, [rbp+57h+var_90]
0x180040a36  mov     [rbp+57h+var_88], ebx
0x180040a39  lea     rcx, [rbp+57h+var_98]
0x180040a3d  call    MakeAsync__GenericMakeAsyncName__lambda_c768481704f013017fa2cab7299eb2aa___
0x180040a42  lea     rcx, [rbp+57h+var_90]
0x180040a46  mov     ebx, eax
0x180040a48  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180040a4d  test    ebx, ebx
0x180040a4f  js      loc_180040C64
0x180040a55  lea     rcx, [rbp+57h+var_98]
0x180040a59  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040a5e  lea     rcx, [rbp+57h+var_A0]
0x180040a62  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180040a67  add     r15d, esi
0x180040a6a  jmp     loc_180040911
0x180040a6f  test    ebx, ebx
0x180040a71  jnz     loc_1800409A1
0x180040a77  test    r13d, r13d
0x180040a7a  jz      loc_180040B9C
0x180040a80  test    rdi, rdi
0x180040a83  jz      loc_180040B9C
0x180040a89  test    [rdx+66h], r8w
0x180040a8e  jnz     loc_180040B9C
0x180040a94  mov     [rbp+57h+hMem], 0
0x180040a9c  test    [rdx+4Eh], r8w
0x180040aa1  jnz     short loc_180040AA9
0x180040aa3  mov     rdx, [rdx+50h]
0x180040aa7  jmp     short loc_180040AAB
0x180040aa9  xor     edx, edx
0x180040aab  lea     r8, [rbp+57h+hMem]
0x180040aaf  mov     rcx, rdi
0x180040ab2  call    GetDisplayNameFromPackageFamilyNameAndPraid
0x180040ab7  xor     edi, edi
0x180040ab9  test    eax, eax
0x180040abb  mov     rax, [rbp+57h+var_D0]
0x180040abf  js      loc_180040B89
0x180040ac5  mov     rcx, [rax+18h]
0x180040ac9  mov     rdx, [rcx+r15*8]
0x180040acd  mov     rcx, [rbp+57h+hMem]
0x180040ad1  mov     r8, rcx
0x180040ad4  mov     r10, [rdx+68h]
0x180040ad8  sub     r10, rcx
0x180040adb  movzx   r9d, word ptr [r8]
0x180040adf  movzx   edx, word ptr [r8+r10]
0x180040ae4  sub     r9d, edx
0x180040ae7  jnz     short loc_180040AF1
0x180040ae9  add     r8, 2
0x180040aed  test    edx, edx
0x180040aef  jnz     short loc_180040ADB
0x180040af1  test    r9d, r9d
0x180040af4  jz      loc_180040B8D
0x180040afa  mov     rcx, [rbp+57h+var_C8]
0x180040afe  lea     r8, [r15+r15*2]
0x180040b02  mov     [rbp+57h+var_A8], rdi
0x180040b06  mov     rdx, [rax+8]
0x180040b0a  mov     r9, [rcx]
0x180040b0d  lea     rdx, [rdx+r8*4]
0x180040b11  lea     r8, [rbp+57h+var_A8]
0x180040b15  mov     rax, [r9+70h]
0x180040b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b1e  mov     ebx, eax
0x180040b20  test    eax, eax
0x180040b22  js      loc_180040C54
0x180040b28  mov     rax, [rbp+57h+hMem]
0x180040b2c  lea     r9, [rbp+57h+var_80]
0x180040b30  mov     rcx, [rbp+57h+var_A8]
0x180040b34  mov     r8d, esi
0x180040b37  mov     [rbp+57h+var_78], rax
0x180040b3b  xor     edx, edx
0x180040b3d  mov     [rbp+57h+var_80], 3001001Fh
0x180040b45  mov     [rbp+57h+var_70], rdi
0x180040b49  mov     rax, [rcx]
0x180040b4c  mov     rax, [rax+58h]
0x180040b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b55  mov     ebx, eax
0x180040b57  test    eax, eax
0x180040b59  js      loc_180040C4C
0x180040b5f  mov     rcx, [rbp+57h+var_A8]
0x180040b63  mov     rax, [rcx]
0x180040b66  mov     rax, [rax+0B0h]
0x180040b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b72  mov     ebx, eax
0x180040b74  test    eax, eax
0x180040b76  js      loc_180040C1F
0x180040b7c  lea     rcx, [rbp+57h+var_A8]
0x180040b80  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180040b85  mov     rax, [rbp+57h+var_D0]
0x180040b89  mov     rcx, [rbp+57h+hMem]; hMem
0x180040b8d  test    rcx, rcx
0x180040b90  jz      short loc_180040B9C
0x180040b92  call    cs:__imp_LocalFree
0x180040b98  mov     rax, [rbp+57h+var_D0]
0x180040b9c  mov     rcx, [rax+8]
0x180040ba0  lea     rdx, [r15+r15*2]
0x180040ba4  lea     rcx, [rcx+rdx*4]
0x180040ba8  call    cs:__imp_RemoveStaleChangeTrackingDataOnStore
0x180040bae  mov     ebx, eax
0x180040bb0  test    eax, eax
0x180040bb2  jns     loc_180040A67
0x180040bb8  mov     r9d, 1E7h
0x180040bbe  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040bc5  mov     edx, esi
0x180040bc7  mov     ecx, eax
0x180040bc9  call    Log_HREvent
0x180040bce  lea     rcx, [rbp+57h+var_D0]
0x180040bd2  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x180040bd7  mov     rcx, [rbp+57h+var_B8]
0x180040bdb  test    rcx, rcx
0x180040bde  jz      short loc_180040BEC
0x180040be0  mov     rax, [rcx]
0x180040be3  mov     rax, [rax+10h]
0x180040be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bec  mov     rcx, [rbp+57h+var_C8]
0x180040bf0  test    rcx, rcx
0x180040bf3  jz      short loc_180040C01
0x180040bf5  mov     rax, [rcx]
0x180040bf8  mov     rax, [rax+10h]
0x180040bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c01  mov     rcx, [rbp+57h+var_C0]
0x180040c05  test    rcx, rcx
0x180040c08  jz      loc_180040D1A
0x180040c0e  mov     rax, [rcx]
0x180040c11  mov     rax, [rax+10h]
0x180040c15  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
