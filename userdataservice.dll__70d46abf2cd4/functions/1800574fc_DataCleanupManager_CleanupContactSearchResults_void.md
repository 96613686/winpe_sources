# DataCleanupManager::CleanupContactSearchResults(void)

- ea: `0x1800574fc`
- end: `0x180057c5d`
- name: `?CleanupContactSearchResults@DataCleanupManager@@QEAAJXZ`
- size: `1889`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004038c`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180012988`
- `0x1800234d4`
- `0x1800574fc`
- `0x180057c64`
- `0x180057cb0`
- `0x1800688fc`
- `0x18007e770`
- `0x18012c776`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x180057536`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x180057536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057a19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800575dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800575dc`
- `unistore!CreateStoreManager` at `0x1800575aa`
- `unistore!CreateStoreManager` at `0x1800575aa`

## string_xrefs

- `0x180057548`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057586`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800575bc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800579a0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057a51`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057aab`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057ac9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057ae9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057b2d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057b48`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057b63`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057b86`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180057ba3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall DataCleanupManager::CleanupContactSearchResults(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // r9
  unsigned __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r9
  int i; // eax
  int v11; // eax
  int v12; // eax
  _WORD *v13; // rbx
  char v14; // r14
  int v15; // eax
  int v16; // eax
  int v17; // eax
  char v18; // bl
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v42[16]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v43[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v44[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v45; // [rsp+E0h] [rbp-20h] BYREF
  int v46; // [rsp+E8h] [rbp-18h]
  __int64 v47; // [rsp+F0h] [rbp-10h] BYREF
  int v48; // [rsp+F8h] [rbp-8h]
  _DWORD v49[4]; // [rsp+100h] [rbp+0h] BYREF

  v40 = 0;
  v2 = POutlookAppManager_CreateInstance(&v40);
  v3 = v2;
  if ( v2 < 0 )
  {
    Log_HREvent(
      (unsigned int)v2,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      762);
LABEL_87:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
    return v3;
  }
  v28 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 32LL))(v40, &v28);
  v3 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      765);
LABEL_86:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
    goto LABEL_87;
  }
  v31 = 0;
  v5 = CreateStoreManager(0, &v31);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 768;
LABEL_7:
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v6);
LABEL_85:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v31);
    goto LABEL_86;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = FileTime64::Retreat((FileTime64 *)&SystemTimeAsFileTime, v7);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 773;
    goto LABEL_7;
  }
  v30 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v31 + 184LL))(
         v31,
         0x20000,
         0,
         0,
         0,
         0,
         &v30);
  v3 = v8;
  if ( v8 < 0 )
  {
    v9 = 776;
LABEL_83:
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v9);
LABEL_84:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
    goto LABEL_85;
  }
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 120LL))(v30);
        !i;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30) )
  {
    v8 = DataCleanupManager::FailIfShutdownOrDc(lpCriticalSection);
    v3 = v8;
    if ( v8 < 0 )
    {
      v9 = 781;
      goto LABEL_83;
    }
    v29 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v29);
    v3 = v11;
    if ( v11 < 0 )
    {
      Log_HREvent(
        (unsigned int)v11,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        784);
      goto LABEL_65;
    }
    v49[0] = 805765184;
    v49[1] = 906035219;
    v49[2] = 805371935;
    hMem = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v29 + 48LL))(v29, 3, v49);
    v3 = v12;
    if ( v12 < 0 )
    {
      v26 = 792;
      goto LABEL_79;
    }
    v13 = hMem;
    if ( (*((_WORD *)hMem + 3) & 0x300) != 0
      || *(unsigned __int64 *)&SystemTimeAsFileTime <= *((_QWORD *)hMem + 1)
      || (*((_WORD *)hMem + 15) & 0x300) != 0
      || (v14 = 1, *((_DWORD *)hMem + 8) != 655361) )
    {
      v14 = 0;
    }
    if ( (*((_WORD *)hMem + 27) & 0x300) == 0
      && !wcscmp_0(*((const wchar_t **)hMem + 7), L"IPM.GRRoot")
      && (v13[15] & 0x300) == 0
      && *((_DWORD *)v13 + 8) == 1 )
    {
      v36 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 112LL))(v29, &v36);
      v3 = v15;
      if ( v15 < 0 )
      {
        Log_HREvent(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          804);
        goto LABEL_63;
      }
      v37 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 168LL))(v36, &v37);
      v3 = v16;
      if ( v16 < 0 )
      {
        v25 = 807;
        goto LABEL_69;
      }
      v44[0] = 0;
      LODWORD(v44[1]) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v37 + 24LL))(v37, v44);
      v3 = v16;
      if ( v16 < 0 )
      {
        v25 = 810;
LABEL_69:
        Log_HREvent(
          (unsigned int)v16,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          v25);
        goto LABEL_62;
      }
      ATL::CComQIPtr<IUSFolder,&__s_GUID const _GUID_ad206d2b_7e48_4f09_a3c2_e9455cbc8243>::CComQIPtr<IUSFolder,&__s_GUID const _GUID_ad206d2b_7e48_4f09_a3c2_e9455cbc8243>(
        &v39,
        v29);
      if ( !v39 )
      {
        v3 = -2147467262;
        Log_HREvent(
          2147500034LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          813);
        goto LABEL_61;
      }
      v38 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 216LL))(v39, &v38);
      v3 = v17;
      if ( v17 < 0 )
      {
        v24 = 816;
LABEL_60:
        Log_HREvent(
          (unsigned int)v17,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          v24);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
LABEL_61:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
LABEL_62:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v37);
LABEL_63:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
        goto LABEL_64;
      }
      v43[0] = 0;
      LODWORD(v43[1]) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v38 + 24LL))(v38, v43);
      v3 = v17;
      if ( v17 < 0 )
      {
        v24 = 819;
        goto LABEL_60;
      }
      if ( *(_QWORD *)((char *)v44 + 4) != *(_QWORD *)((char *)v43 + 4) || (v18 = 1, LODWORD(v44[0]) != LODWORD(v43[0])) )
        v18 = 0;
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v37);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
      if ( v18 )
      {
LABEL_38:
        v45 = 0;
        v46 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 24LL))(v29, &v45);
        v3 = v12;
        if ( v12 >= 0 )
        {
          v19 = USOIDToOLITEMID(v42, &v45);
          v47 = *(_QWORD *)v19;
          v48 = *(_DWORD *)(v19 + 8);
          v35 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v28 + 200LL))(
                  v28,
                  &v47,
                  &GUID_3382bed9_e18f_4e32_b3e6_503192c8a58e,
                  &v35);
          v3 = v20;
          if ( v20 < 0 )
          {
            Log_HREvent(
              (unsigned int)v20,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
              831);
          }
          else
          {
            v34 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 32LL))(v35, &v34);
            v3 = v21;
            if ( v21 < 0 )
            {
              Log_HREvent(
                (unsigned int)v21,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
                835);
            }
            else
            {
              v33 = 0;
              v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v34 + 56LL))(
                      v34,
                      0,
                      &v33);
              v3 = v22;
              if ( v22 < 0 )
              {
                v23 = 838;
              }
              else
              {
                while ( v33 )
                {
                  v22 = DataCleanupManager::FailIfShutdownOrDc(lpCriticalSection);
                  v3 = v22;
                  if ( v22 < 0 )
                  {
                    v23 = 841;
                    goto LABEL_49;
                  }
                  v22 = ((__int64 (__fastcall *)(struct IUnknown *))v33->lpVtbl[2].AddRef)(v33);
                  v3 = v22;
                  if ( v22 < 0 )
                  {
                    v23 = 843;
                    goto LABEL_49;
                  }
                  if ( v33 )
                    ATL::AtlComPtrAssign(&v33, 0);
                  v22 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v34 + 64LL))(v34, &v33);
                  v3 = v22;
                  if ( v22 < 0 )
                  {
                    v23 = 846;
                    goto LABEL_49;
                  }
                }
                v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 40LL))(v29);
                v3 = v22;
                if ( v22 >= 0 )
                {
                  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v33);
                  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
                  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
                  v13 = hMem;
                  goto LABEL_54;
                }
                v23 = 849;
              }
LABEL_49:
              Log_HREvent(
                (unsigned int)v22,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
                v23);
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v33);
            }
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v34);
          }
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
LABEL_64:
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&hMem);
LABEL_65:
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
          goto LABEL_84;
        }
        v26 = 827;
LABEL_79:
        Log_HREvent(
          (unsigned int)v12,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          v26);
        goto LABEL_64;
      }
      v13 = hMem;
    }
    if ( v14 )
      goto LABEL_38;
LABEL_54:
    if ( v13 )
      LocalFree(v13);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  return 0;
}

```

## disassembly

```asm
0x1800574fc  mov     [rsp-8+arg_8], rbx
0x180057501  mov     [rsp-8+arg_10], rsi
0x180057506  push    rbp
0x180057507  push    rdi
0x180057508  push    r12
0x18005750a  push    r14
0x18005750c  push    r15
0x18005750e  lea     rbp, [rsp-20h]
0x180057513  sub     rsp, 120h
0x18005751a  mov     rax, cs:__security_cookie
0x180057521  xor     rax, rsp
0x180057524  mov     [rbp+40h+var_30], rax
0x180057528  mov     r15, rcx
0x18005752b  xor     r12d, r12d
0x18005752e  lea     rcx, [rbp+40h+var_A0]
0x180057532  mov     [rbp+40h+var_A0], r12
0x180057536  call    cs:__imp_POutlookAppManager_CreateInstance
0x18005753c  mov     ebx, eax
0x18005753e  test    eax, eax
0x180057540  jns     short loc_180057560
0x180057542  mov     r9d, 2FAh
0x180057548  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005754f  lea     edx, [r12+1]
0x180057554  mov     ecx, eax
0x180057556  call    Log_HREvent
0x18005755b  jmp     loc_180057BCF
0x180057560  mov     rcx, [rbp+40h+var_A0]
0x180057564  lea     rdx, [rsp+140h+var_100]
0x180057569  mov     [rsp+140h+var_100], r12
0x18005756e  mov     rax, [rcx]
0x180057571  mov     rax, [rax+20h]
0x180057575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005757a  mov     ebx, eax
0x18005757c  test    eax, eax
0x18005757e  jns     short loc_18005759E
0x180057580  mov     r9d, 2FDh
0x180057586  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005758d  mov     edx, 1
0x180057592  mov     ecx, eax
0x180057594  call    Log_HREvent
0x180057599  jmp     loc_180057BC5
0x18005759e  lea     rdx, [rsp+140h+var_E8]
0x1800575a3  mov     [rsp+140h+var_E8], r12
0x1800575a8  xor     ecx, ecx
0x1800575aa  call    cs:__imp_CreateStoreManager
0x1800575b0  mov     ebx, eax
0x1800575b2  test    eax, eax
0x1800575b4  jns     short loc_1800575D4
0x1800575b6  mov     r9d, 300h
0x1800575bc  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800575c3  mov     edx, 1
0x1800575c8  mov     ecx, eax
0x1800575ca  call    Log_HREvent
0x1800575cf  jmp     loc_180057BBB
0x1800575d4  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800575d8  mov     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800575dc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800575e2  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; this
0x1800575e6  call    ?Retreat@FileTime64@@QEAAJ_K@Z; FileTime64::Retreat(unsigned __int64)
0x1800575eb  mov     ebx, eax
0x1800575ed  test    eax, eax
0x1800575ef  jns     short loc_1800575F9
0x1800575f1  mov     r9d, 305h
0x1800575f7  jmp     short loc_1800575BC
0x1800575f9  mov     rcx, [rsp+140h+var_E8]
0x1800575fe  lea     rdx, [rsp+140h+var_F0]
0x180057603  mov     [rsp+140h+var_110], rdx
0x180057608  xor     r9d, r9d
0x18005760b  mov     [rsp+140h+var_F0], r12
0x180057610  xor     r8d, r8d
0x180057613  mov     [rsp+140h+var_118], r12
0x180057618  mov     edx, 20000h
0x18005761d  mov     rax, [rcx]
0x180057620  mov     [rsp+140h+var_120], r12
0x180057625  mov     rax, [rax+0B8h]
0x18005762c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057631  mov     ebx, eax
0x180057633  test    eax, eax
0x180057635  jns     short loc_180057647
0x180057637  mov     r9d, 308h
0x18005763d  mov     edx, 1
0x180057642  jmp     loc_180057BA3
0x180057647  mov     rcx, [rsp+140h+var_F0]
0x18005764c  mov     rax, [rcx]
0x18005764f  mov     rax, [rax+78h]
0x180057653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057658  mov     edi, 1
0x18005765d  mov     esi, 300h
0x180057662  test    eax, eax
0x180057664  jnz     loc_180057BDC
0x18005766a  mov     rcx, r15; lpCriticalSection
0x18005766d  call    ?FailIfShutdownOrDc@DataCleanupManager@@AEAAJXZ; DataCleanupManager::FailIfShutdownOrDc(void)
0x180057672  mov     ebx, eax
0x180057674  test    eax, eax
0x180057676  js      loc_180057B9B
0x18005767c  mov     rcx, [rsp+140h+var_F0]
0x180057681  lea     rdx, [rsp+140h+var_F8]
0x180057686  mov     [rsp+140h+var_F8], r12
0x18005768b  mov     rax, [rcx]
0x18005768e  mov     rax, [rax+28h]
0x180057692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057697  mov     ebx, eax
0x180057699  test    eax, eax
0x18005769b  js      loc_180057B80
0x1800576a1  mov     rcx, [rsp+140h+var_F8]
0x1800576a6  lea     rdx, [rsp+140h+hMem]
0x1800576ab  mov     [rbp+40h+var_40], 30070040h
0x1800576b2  lea     r8, [rbp+40h+var_40]
0x1800576b6  mov     [rbp+40h+var_3C], 36010013h
0x1800576bd  xor     r9d, r9d
0x1800576c0  mov     [rbp+40h+var_38], 3001001Fh
0x1800576c7  mov     [rsp+140h+hMem], r12
0x1800576cc  mov     rax, [rcx]
0x1800576cf  mov     [rsp+140h+var_120], rdx
0x1800576d4  lea     edx, [r9+3]
0x1800576d8  mov     rax, [rax+30h]
0x1800576dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576e1  mov     ebx, eax
0x1800576e3  test    eax, eax
0x1800576e5  js      loc_180057B78
0x1800576eb  mov     rbx, [rsp+140h+hMem]
0x1800576f0  test    [rbx+6], si
0x1800576f4  jnz     short loc_180057712
0x1800576f6  mov     rax, [rbx+8]
0x1800576fa  cmp     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800576fe  jbe     short loc_180057712
0x180057700  test    [rbx+1Eh], si
0x180057704  jnz     short loc_180057712
0x180057706  cmp     dword ptr [rbx+20h], 0A0001h
0x18005770d  mov     r14b, dil
0x180057710  jz      short loc_180057715
0x180057712  mov     r14b, r12b
0x180057715  test    [rbx+36h], si
0x180057719  jnz     loc_180057867
0x18005771f  mov     rcx, [rbx+38h]; String1
0x180057723  lea     rdx, aIpmGrroot; "IPM.GRRoot"
0x18005772a  call    wcscmp_0
0x18005772f  test    eax, eax
0x180057731  jnz     loc_180057867
0x180057737  test    [rbx+1Eh], si
0x18005773b  jnz     loc_180057867
0x180057741  cmp     [rbx+20h], edi
0x180057744  jnz     loc_180057867
0x18005774a  mov     rcx, [rsp+140h+var_F8]
0x18005774f  lea     rdx, [rbp+40h+var_C0]
0x180057753  mov     [rbp+40h+var_C0], r12
0x180057757  mov     rax, [rcx]
0x18005775a  mov     rax, [rax+70h]
0x18005775e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057763  mov     ebx, eax
0x180057765  test    eax, eax
0x180057767  js      loc_180057AE3
0x18005776d  mov     rcx, [rbp+40h+var_C0]
0x180057771  lea     rdx, [rbp+40h+var_B8]
0x180057775  mov     [rbp+40h+var_B8], r12
0x180057779  mov     rax, [rcx]
0x18005777c  mov     rax, [rax+0A8h]
0x180057783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057788  mov     ebx, eax
0x18005778a  test    eax, eax
0x18005778c  js      loc_180057ADB
0x180057792  mov     rcx, [rbp+40h+var_B8]
0x180057796  lea     rdx, [rbp+40h+var_70]
0x18005779a  xor     eax, eax
0x18005779c  mov     qword ptr [rbp+40h+var_70], rax
0x1800577a0  mov     dword ptr [rbp+40h+var_70+8], eax
0x1800577a3  mov     rax, [rcx]
0x1800577a6  mov     rax, [rax+18h]
0x1800577aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577af  mov     ebx, eax
0x1800577b1  test    eax, eax
0x1800577b3  js      loc_180057AC3
0x1800577b9  mov     rdx, [rsp+140h+var_F8]
0x1800577be  lea     rcx, [rbp+40h+var_A8]
0x1800577c2  call    ??0?$CComQIPtr@UIUSFolder@@$1?_GUID_ad206d2b_7e48_4f09_a3c2_e9455cbc8243@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSFolder,&__s_GUID const _GUID_ad206d2b_7e48_4f09_a3c2_e9455cbc8243>::CComQIPtr<IUSFolder,&__s_GUID const _GUID_ad206d2b_7e48_4f09_a3c2_e9455cbc8243>(IUnknown *)
0x1800577c7  mov     rcx, [rbp+40h+var_A8]
0x1800577cb  test    rcx, rcx
0x1800577ce  jz      loc_180057AA6
0x1800577d4  mov     [rbp+40h+var_B0], r12
0x1800577d8  lea     rdx, [rbp+40h+var_B0]
0x1800577dc  mov     rax, [rcx]
0x1800577df  mov     rax, [rax+0D8h]
0x1800577e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577eb  mov     ebx, eax
0x1800577ed  test    eax, eax
0x1800577ef  js      loc_180057A9E
0x1800577f5  mov     rcx, [rbp+40h+var_B0]
0x1800577f9  lea     rdx, [rbp+40h+var_80]
0x1800577fd  xor     eax, eax
0x1800577ff  mov     qword ptr [rbp+40h+var_80], rax
0x180057803  mov     dword ptr [rbp+40h+var_80+8], eax
0x180057806  mov     rax, [rcx]
0x180057809  mov     rax, [rax+18h]
0x18005780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057812  mov     ebx, eax
0x180057814  test    eax, eax
0x180057816  js      loc_180057A4B
0x18005781c  mov     eax, dword ptr [rbp+40h+var_80+8]
0x18005781f  cmp     dword ptr [rbp+40h+var_70+8], eax
0x180057822  jnz     short loc_180057837
0x180057824  mov     eax, dword ptr [rbp+40h+var_80+4]
0x180057827  cmp     dword ptr [rbp+40h+var_70+4], eax
0x18005782a  jnz     short loc_180057837
0x18005782c  mov     eax, dword ptr [rbp+40h+var_80]
0x18005782f  mov     bl, dil
0x180057832  cmp     dword ptr [rbp+40h+var_70], eax
0x180057835  jz      short loc_18005783A
0x180057837  mov     bl, r12b
0x18005783a  lea     rcx, [rbp+40h+var_B0]
0x18005783e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180057843  lea     rcx, [rbp+40h+var_A8]
0x180057847  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005784c  lea     rcx, [rbp+40h+var_B8]
0x180057850  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180057855  lea     rcx, [rbp+40h+var_C0]
0x180057859  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005785e  test    bl, bl
0x180057860  jnz     short loc_180057870
0x180057862  mov     rbx, [rsp+140h+hMem]
0x180057867  test    r14b, r14b
0x18005786a  jz      loc_180057A11
0x180057870  mov     rcx, [rsp+140h+var_F8]
0x180057875  lea     rdx, [rbp+40h+var_60]
0x180057879  xor     eax, eax
0x18005787b  mov     [rbp+40h+var_60], rax
0x18005787f  mov     [rbp+40h+var_58], eax
0x180057882  mov     rax, [rcx]
0x180057885  mov     rax, [rax+18h]
0x180057889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005788e  mov     ebx, eax
0x180057890  test    eax, eax
0x180057892  js      loc_180057B5D
0x180057898  lea     rdx, [rbp+40h+var_60]
0x18005789c  lea     rcx, [rbp+40h+var_90]
0x1800578a0  call    ?USOIDToOLITEMID@@YA?AUOLITEMID@@AEBUUSOID@@@Z; USOIDToOLITEMID(USOID const &)
0x1800578a5  mov     rcx, [rsp+140h+var_100]
0x1800578aa  lea     r9, [rsp+140h+var_C8]
0x1800578af  lea     r8, _GUID_3382bed9_e18f_4e32_b3e6_503192c8a58e
0x1800578b6  lea     rdx, [rbp+40h+var_50]
0x1800578ba  movsd   xmm0, qword ptr [rax]
0x1800578be  movsd   [rbp+40h+var_50], xmm0
0x1800578c3  mov     eax, [rax+8]
0x1800578c6  mov     [rbp+40h+var_48], eax
0x1800578c9  mov     [rsp+140h+var_C8], r12
0x1800578ce  mov     rax, [rcx]
0x1800578d1  mov     rax, [rax+0C8h]
0x1800578d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578dd  mov     ebx, eax
0x1800578df  test    eax, eax
0x1800578e1  js      loc_180057B42
0x1800578e7  mov     rcx, [rsp+140h+var_C8]
0x1800578ec  lea     rdx, [rsp+140h+var_D0]
0x1800578f1  mov     [rsp+140h+var_D0], r12
0x1800578f6  mov     rax, [rcx]
0x1800578f9  mov     rax, [rax+20h]
0x1800578fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057902  mov     ebx, eax
0x180057904  test    eax, eax
0x180057906  js      loc_180057B27
0x18005790c  mov     rcx, [rsp+140h+var_D0]
0x180057911  lea     r8, [rsp+140h+var_D8]
0x180057916  mov     [rsp+140h+var_D8], r12
0x18005791b  xor     edx, edx
0x18005791d  mov     rax, [rcx]
0x180057920  mov     rax, [rax+38h]
0x180057924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057929  mov     ebx, eax
0x18005792b  test    eax, eax
0x18005792d  js      loc_180057B1C
0x180057933  cmp     [rsp+140h+var_D8], r12
0x180057938  jz      loc_1800579D3
0x18005793e  mov     rcx, r15; lpCriticalSection
0x180057941  call    ?FailIfShutdownOrDc@DataCleanupManager@@AEAAJXZ; DataCleanupManager::FailIfShutdownOrDc(void)
0x180057946  mov     ebx, eax
0x180057948  test    eax, eax
0x18005794a  js      loc_180057B06
0x180057950  mov     rcx, [rsp+140h+var_D8]
0x180057955  mov     rax, [rcx]
0x180057958  mov     rax, [rax+38h]
0x18005795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057961  mov     ebx, eax
0x180057963  test    eax, eax
0x180057965  js      loc_180057AFB
0x18005796b  cmp     [rsp+140h+var_D8], r12
0x180057970  jz      short loc_18005797E
0x180057972  xor     edx, edx; struct IUnknown *
0x180057974  lea     rcx, [rsp+140h+var_D8]; struct IUnknown **
0x180057979  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18005797e  mov     rcx, [rsp+140h+var_D0]
0x180057983  lea     rdx, [rsp+140h+var_D8]
0x180057988  mov     rax, [rcx]
0x18005798b  mov     rax, [rax+40h]
0x18005798f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057994  mov     ebx, eax
0x180057996  test    eax, eax
0x180057998  jns     short loc_180057933
0x18005799a  mov     r9d, 34Eh
0x1800579a0  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800579a7  mov     edx, edi
0x1800579a9  mov     ecx, eax
  ... truncated ...
```
