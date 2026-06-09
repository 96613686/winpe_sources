# GetODSyncRootPaths(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180019674`
- end: `0x180019a69`
- name: `?GetODSyncRootPaths@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019288`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180013ae4`
- `0x1800152d4`
- `0x180017130`
- `0x180017384`
- `0x1800179cc`
- `0x180019674`
- `0x18001ebf4`
- `0x18001f108`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001999e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001999e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001970e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001970e`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001997a`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001997a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetODSyncRootPaths(_QWORD *a1)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, GUID *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  unsigned int i; // r14d
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, __int64 *); // rbx
  LPVOID v16; // rdi
  int (__fastcall *v17)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  int SyncRootInfoByPath; // eax
  __int64 v19; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  _BYTE v35[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v36[3]; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+C8h] [rbp-38h]
  wchar_t Str[256]; // [rsp+CCh] [rbp-34h] BYREF
  _BYTE v39[512]; // [rsp+2CCh] [rbp+1CCh] BYREF
  int v40; // [rsp+4CCh] [rbp+3CCh]
  char v41; // [rsp+4D0h] [rbp+3D0h]
  int v42; // [rsp+4D1h] [rbp+3D1h]
  __int16 v43; // [rsp+4D5h] [rbp+3D5h]
  char v44; // [rsp+4D7h] [rbp+3D7h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  if ( !((__int64)(a1[1] - *a1) >> 5) )
  {
    v26 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    v3 = CoCreateInstance(
           &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
           0,
           1u,
           &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
           &v26);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v25 = 0;
      v4 = v26;
      v5 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v26;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      v6 = v5(v4, &GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad, &v25);
      v2 = v6;
      if ( v6 >= 0 )
      {
        v24 = 0;
        v7 = v25;
        v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
        v9 = v8(v7, &v24);
        v2 = v9;
        if ( v9 >= 0 )
        {
          v23 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v23);
          v2 = v9;
          if ( v9 >= 0 )
          {
            for ( i = 0; i < v23; ++i )
            {
              v27 = 0;
              v12 = v24;
              v13 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v24 + 32LL);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
              if ( v13(v12, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v27) >= 0 )
              {
                v32 = 0;
                v33 = 0;
                v34 = 0;
                v14 = v27;
                v15 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
                v33 = -1;
                v34 = -1;
                if ( v15(v14, &v32) >= 0 )
                {
                  v29 = 0;
                  v30 = 0;
                  v31 = 0;
                  v16 = v26;
                  v17 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 136LL);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
                  v30 = -1;
                  v31 = -1;
                  if ( v17(v16, v32, 0, &v29) >= 0 )
                  {
                    memset(v36, 0, sizeof(v36));
                    v37 = 0;
                    memset_0(Str, 0, sizeof(Str));
                    memset_0(v39, 0, sizeof(v39));
                    v40 = 0;
                    v41 = 0;
                    v42 = 0;
                    v43 = 0;
                    v44 = 0;
                    v28 = 0;
                    SyncRootInfoByPath = CfGetSyncRootInfoByPath(v29, 1, v36, 1064, &v28);
                    if ( (int)(SyncRootInfoByPath + 0x80000000) < 0 || SyncRootInfoByPath == -2147024662 )
                    {
                      if ( wcsstr(Str, L"OneDrive") )
                      {
                        std::wstring::wstring(v35, v29);
                        v19 = a1[1];
                        if ( v19 == a1[2] )
                        {
                          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, a1[1], v35);
                        }
                        else
                        {
                          std::_Construct_in_place<std::wstring,std::wstring>(v19, v35);
                          a1[1] += 32LL;
                        }
                        std::wstring::_Tidy_deallocate(v35);
                      }
                    }
                  }
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
              }
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
            v2 = 0;
            goto LABEL_28;
          }
          v10 = 2309;
        }
        else
        {
          v10 = 2306;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
          (const char *)(unsigned int)v9,
          ppva);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8FF,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
          (const char *)(unsigned int)v6,
          ppva);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8FC,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
        (const char *)(unsigned int)v3,
        ppva);
    }
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    return v2;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F9,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
    (const char *)0x80070057LL,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x180019674  mov     [rsp-8+arg_8], rbx
0x180019679  mov     [rsp-8+arg_10], rsi
0x18001967e  push    rbp
0x18001967f  push    rdi
0x180019680  push    r12
0x180019682  push    r14
0x180019684  push    r15
0x180019686  lea     rbp, [rsp-3F0h]
0x18001968e  sub     rsp, 4F0h
0x180019695  mov     rax, cs:__security_cookie
0x18001969c  xor     rax, rsp
0x18001969f  mov     [rbp+410h+var_30], rax
0x1800196a6  mov     rsi, rcx
0x1800196a9  mov     rax, [rcx+8]
0x1800196ad  sub     rax, [rcx]
0x1800196b0  sar     rax, 5
0x1800196b4  xor     r15d, r15d
0x1800196b7  test    rax, rax
0x1800196ba  jz      short loc_1800196E1
0x1800196bc  mov     rcx, [rbp+418h]; this
0x1800196c3  mov     ebx, 80070057h
0x1800196c8  mov     r9d, ebx; char *
0x1800196cb  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800196d2  mov     edx, 8F9h; void *
0x1800196d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196dc  jmp     loc_180019A3C
0x1800196e1  mov     [rsp+510h+var_4C8], r15
0x1800196e6  lea     rcx, [rsp+510h+var_4C8]
0x1800196eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800196f0  lea     rax, [rsp+510h+var_4C8]
0x1800196f5  mov     qword ptr [rsp+510h+ppv], rax; int
0x1800196fa  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180019701  xor     edx, edx; pUnkOuter
0x180019703  lea     r8d, [rdx+1]; dwClsContext
0x180019707  lea     rcx, _GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe; rclsid
0x18001970e  call    cs:__imp_CoCreateInstance
0x180019714  mov     ebx, eax
0x180019716  test    eax, eax
0x180019718  jns     short loc_18001973A
0x18001971a  mov     rcx, [rbp+418h]; this
0x180019721  mov     r9d, eax; char *
0x180019724  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001972b  mov     edx, 8FCh; void *
0x180019730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019735  jmp     loc_180019A32
0x18001973a  mov     [rsp+510h+var_4D0], r15
0x18001973f  mov     rdi, [rsp+510h+var_4C8]
0x180019744  mov     rax, [rdi]
0x180019747  mov     rbx, [rax]
0x18001974a  lea     rcx, [rsp+510h+var_4D0]
0x18001974f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019754  lea     r8, [rsp+510h+var_4D0]
0x180019759  lea     rdx, _GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad
0x180019760  mov     rcx, rdi
0x180019763  mov     rax, rbx
0x180019766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001976b  mov     ebx, eax
0x18001976d  test    eax, eax
0x18001976f  jns     short loc_18001979C
0x180019771  mov     rcx, [rbp+418h]; this
0x180019778  mov     r9d, eax; char *
0x18001977b  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180019782  mov     edx, 8FFh; void *
0x180019787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001978c  nop
0x18001978d  lea     rcx, [rsp+510h+var_4D0]
0x180019792  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019797  jmp     loc_180019A32
0x18001979c  mov     [rsp+510h+var_4D8], r15
0x1800197a1  mov     rdi, [rsp+510h+var_4D0]
0x1800197a6  mov     rax, [rdi]
0x1800197a9  mov     rbx, [rax+18h]
0x1800197ad  lea     rcx, [rsp+510h+var_4D8]
0x1800197b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800197b7  lea     rdx, [rsp+510h+var_4D8]
0x1800197bc  mov     rcx, rdi
0x1800197bf  mov     rax, rbx
0x1800197c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197c7  mov     ebx, eax
0x1800197c9  test    eax, eax
0x1800197cb  jns     short loc_1800197F5
0x1800197cd  mov     edx, 902h; void *
0x1800197d2  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800197d9  mov     r9d, eax; char *
0x1800197dc  mov     rcx, [rbp+418h]; this
0x1800197e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800197e8  nop
0x1800197e9  lea     rcx, [rsp+510h+var_4D8]
0x1800197ee  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800197f3  jmp     short loc_18001978D
0x1800197f5  mov     [rsp+510h+var_4E0], r15d
0x1800197fa  mov     rcx, [rsp+510h+var_4D8]
0x1800197ff  mov     rax, [rcx]
0x180019802  lea     rdx, [rsp+510h+var_4E0]
0x180019807  mov     rax, [rax+18h]
0x18001980b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019810  mov     ebx, eax
0x180019812  test    eax, eax
0x180019814  jns     short loc_18001981D
0x180019816  mov     edx, 905h
0x18001981b  jmp     short loc_1800197D2
0x18001981d  mov     r14d, r15d
0x180019820  cmp     [rsp+510h+var_4E0], r15d
0x180019825  jbe     loc_180019A1A
0x18001982b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001982f  mov     [rsp+510h+var_4C0], r15
0x180019834  mov     rdi, [rsp+510h+var_4D8]
0x180019839  mov     rax, [rdi]
0x18001983c  mov     rbx, [rax+20h]
0x180019840  lea     rcx, [rsp+510h+var_4C0]
0x180019845  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001984a  lea     r9, [rsp+510h+var_4C0]
0x18001984f  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x180019856  mov     edx, r14d
0x180019859  mov     rcx, rdi
0x18001985c  mov     rax, rbx
0x18001985f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019864  test    eax, eax
0x180019866  js      loc_180019A02
0x18001986c  mov     [rsp+510h+var_498], r15
0x180019871  mov     [rbp+410h+var_490], r15
0x180019875  mov     [rbp+410h+var_488], r15
0x180019879  mov     rdi, [rsp+510h+var_4C0]
0x18001987e  mov     rax, [rdi]
0x180019881  mov     rbx, [rax+18h]
0x180019885  lea     rcx, [rsp+510h+var_498]
0x18001988a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001988f  mov     [rbp+410h+var_490], r12
0x180019893  mov     [rbp+410h+var_488], r12
0x180019897  lea     rdx, [rsp+510h+var_498]
0x18001989c  mov     rcx, rdi
0x18001989f  mov     rax, rbx
0x1800198a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198a7  test    eax, eax
0x1800198a9  js      loc_1800199F7
0x1800198af  mov     [rsp+510h+var_4B0], r15
0x1800198b4  mov     [rsp+510h+var_4A8], r15
0x1800198b9  mov     [rsp+510h+var_4A0], r15
0x1800198be  mov     rdi, [rsp+510h+var_4C8]
0x1800198c3  mov     rax, [rdi]
0x1800198c6  mov     rbx, [rax+88h]
0x1800198cd  lea     rcx, [rsp+510h+var_4B0]
0x1800198d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800198d7  mov     [rsp+510h+var_4A8], r12
0x1800198dc  mov     [rsp+510h+var_4A0], r12
0x1800198e1  lea     r9, [rsp+510h+var_4B0]
0x1800198e6  xor     r8d, r8d
0x1800198e9  mov     rdx, [rsp+510h+var_498]
0x1800198ee  mov     rcx, rdi
0x1800198f1  mov     rax, rbx
0x1800198f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198f9  test    eax, eax
0x1800198fb  js      loc_1800199EC
0x180019901  mov     [rbp+410h+var_460], r15
0x180019905  mov     [rbp+410h+var_458], r15
0x180019909  xor     eax, eax
0x18001990b  mov     [rbp+410h+var_450], rax
0x18001990f  mov     [rbp+410h+var_448], eax
0x180019912  mov     ebx, 200h
0x180019917  mov     r8d, ebx; Size
0x18001991a  xor     edx, edx; Val
0x18001991c  lea     rcx, [rbp+410h+Str]; void *
0x180019920  call    memset_0
0x180019925  mov     r8d, ebx; Size
0x180019928  xor     edx, edx; Val
0x18001992a  lea     rcx, [rbp+410h+var_244]; void *
0x180019931  call    memset_0
0x180019936  xor     eax, eax
0x180019938  mov     [rbp+410h+var_44], eax
0x18001993e  mov     [rbp+410h+var_40], al
0x180019944  mov     [rbp+410h+var_3F], eax
0x18001994a  mov     [rbp+410h+var_3B], ax
0x180019951  mov     [rbp+410h+var_39], al
0x180019957  mov     [rsp+510h+var_4B8], r15d
0x18001995c  lea     rax, [rsp+510h+var_4B8]
0x180019961  mov     qword ptr [rsp+510h+ppv], rax
0x180019966  mov     r9d, 428h
0x18001996c  lea     r8, [rbp+410h+var_460]
0x180019970  mov     edx, 1
0x180019975  mov     rcx, [rsp+510h+var_4B0]
0x18001997a  call    cs:__imp_CfGetSyncRootInfoByPath
0x180019980  mov     edx, 80000000h
0x180019985  lea     ecx, [rax+rdx]
0x180019988  test    edx, ecx
0x18001998a  jnz     short loc_180019993
0x18001998c  cmp     eax, 800700EAh
0x180019991  jnz     short loc_1800199EC
0x180019993  lea     rdx, aOnedrive; "OneDrive"
0x18001999a  lea     rcx, [rbp+410h+Str]; Str
0x18001999e  call    cs:__imp_wcsstr
0x1800199a4  test    rax, rax
0x1800199a7  jz      short loc_1800199EC
0x1800199a9  mov     rdx, [rsp+510h+var_4B0]
0x1800199ae  lea     rcx, [rbp+410h+var_480]
0x1800199b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800199b7  nop
0x1800199b8  mov     rcx, [rsi+8]
0x1800199bc  cmp     rcx, [rsi+10h]
0x1800199c0  jz      short loc_1800199D2
0x1800199c2  lea     rdx, [rbp+410h+var_480]
0x1800199c6  call    ??$_Construct_in_place@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@@Z; std::_Construct_in_place<std::wstring,std::wstring>(std::wstring &,std::wstring &&)
0x1800199cb  add     qword ptr [rsi+8], 20h ; ' '
0x1800199d0  jmp     short loc_1800199E2
0x1800199d2  lea     r8, [rbp+410h+var_480]
0x1800199d6  mov     rdx, rcx
0x1800199d9  mov     rcx, rsi
0x1800199dc  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800199e1  nop
0x1800199e2  lea     rcx, [rbp+410h+var_480]
0x1800199e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800199eb  nop
0x1800199ec  lea     rcx, [rsp+510h+var_4B0]
0x1800199f1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800199f6  nop
0x1800199f7  lea     rcx, [rsp+510h+var_498]
0x1800199fc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180019a01  nop
0x180019a02  lea     rcx, [rsp+510h+var_4C0]
0x180019a07  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019a0c  inc     r14d
0x180019a0f  cmp     r14d, [rsp+510h+var_4E0]
0x180019a14  jb      loc_18001982F
0x180019a1a  lea     rcx, [rsp+510h+var_4D8]
0x180019a1f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019a24  nop
0x180019a25  lea     rcx, [rsp+510h+var_4D0]
0x180019a2a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019a2f  mov     ebx, r15d
0x180019a32  lea     rcx, [rsp+510h+var_4C8]
0x180019a37  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019a3c  mov     eax, ebx
0x180019a3e  mov     rcx, [rbp+410h+var_30]
0x180019a45  xor     rcx, rsp; StackCookie
0x180019a48  call    __security_check_cookie
0x180019a4d  lea     r11, [rsp+510h+var_20]
0x180019a55  mov     rbx, [r11+38h]
0x180019a59  mov     rsi, [r11+40h]
0x180019a5d  mov     rsp, r11
0x180019a60  pop     r15
0x180019a62  pop     r14
0x180019a64  pop     r12
0x180019a66  pop     rdi
0x180019a67  pop     rbp
0x180019a68  retn
```
