# RecycleBinPolicy::UpdateCleanupList(ushort const *,std::list<std::shared_ptr<CCleanupPolicy>,std::allocator<std::shared_ptr<CCleanupPolicy>>> &)

- ea: `0x18003376c`
- end: `0x180033b70`
- name: `?UpdateCleanupList@RecycleBinPolicy@@SAJPEBGAEAV?$list@V?$shared_ptr@VCCleanupPolicy@@@std@@V?$allocator@V?$shared_ptr@VCCleanupPolicy@@@std@@@2@@std@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003253c`

## callees

- `0x180012734`
- `0x180014a00`
- `0x180018d54`
- `0x18001fcac`
- `0x18002dcf4`
- `0x18002e584`
- `0x18002ebe8`
- `0x18003037c`
- `0x18003376c`
- `0x180034018`
- `0x18003aef8`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800337aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800339f4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800337aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800339f4`
- `RPCRT4!RpcRevertToSelf` at `0x18003385f`
- `RPCRT4!RpcRevertToSelf` at `0x1800338ff`
- `RPCRT4!RpcRevertToSelf` at `0x180033afe`
- `RPCRT4!RpcRevertToSelf` at `0x18003385f`
- `RPCRT4!RpcRevertToSelf` at `0x1800338ff`
- `RPCRT4!RpcRevertToSelf` at `0x180033afe`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003388a`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003388a`

## string_xrefs

- `0x18003380f`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x1800338e3`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RecycleBinPolicy::UpdateCleanupList(const WCHAR *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  int DriveNumberW; // esi
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  int StoragePolicySettings; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  char v11; // al
  HRESULT v12; // eax
  __int64 v13; // rdx
  void *v14; // rdi
  __int64 (__fastcall *v15)(void *, _QWORD, const GUID *, GUID *); // rbx
  bool v16; // zf
  __int64 v18; // rdi
  unsigned int (__fastcall *v19)(__int64, __int64, _QWORD); // rbx
  int (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v21)(_QWORD, GUID *, int *); // rdi
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, __int64 *, LPCWSTR *); // rbx
  unsigned int v24; // r8d
  __int64 v25; // rax
  std::_Ref_count_base *v26; // rbx
  int (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  char v28; // al
  int ppv; // [rsp+20h] [rbp-69h]
  int *ppva; // [rsp+20h] [rbp-69h]
  _BYTE v31[4]; // [rsp+30h] [rbp-59h] BYREF
  int v32[3]; // [rsp+34h] [rbp-55h] BYREF
  int (__fastcall ***v33)(_QWORD, GUID *, int *); // [rsp+40h] [rbp-49h] BYREF
  int v34[2]; // [rsp+48h] [rbp-41h] BYREF
  void *v35; // [rsp+50h] [rbp-39h] BYREF
  int v36; // [rsp+58h] [rbp-31h] BYREF
  FILETIME FileTime1; // [rsp+60h] [rbp-29h] BYREF
  LPCWSTR pszPath; // [rsp+68h] [rbp-21h] BYREF
  __int64 v39; // [rsp+70h] [rbp-19h]
  __int64 v40; // [rsp+78h] [rbp-11h]
  __int64 v41; // [rsp+80h] [rbp-9h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v43[8]; // [rsp+98h] [rbp+Fh] BYREF
  std::_Ref_count_base *v44; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  char v46; // [rsp+100h] [rbp+77h] BYREF

  v35 = 0;
  *(_QWORD *)v34 = 0;
  v33 = 0;
  *(_QWORD *)&v32[1] = 0;
  v41 = 0;
  FileTime1 = 0;
  v36 = 0;
  v32[0] = 720;
  DriveNumberW = PathGetDriveNumberW(a1);
  v31[0] = 0;
  if ( DriveNumberW == -1 )
  {
    v5 = -2147024809;
    v6 = 2147942487LL;
    v7 = 1035;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)v6,
      ppv);
    v31[0] = 0;
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32[1]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    return v5;
  }
  StoragePolicySettings = StorageService::GetStoragePolicySettings(v3, 3u, 0, &v36);
  v5 = StoragePolicySettings;
  if ( StoragePolicySettings < 0 )
  {
    v7 = 1037;
LABEL_8:
    v6 = (unsigned int)StoragePolicySettings;
    goto LABEL_9;
  }
  if ( !v36 )
    goto LABEL_38;
  StoragePolicySettings = StorageService::GetStoragePolicySettings(v9, 8u, 0, v32);
  v5 = StoragePolicySettings;
  if ( StoragePolicySettings < 0 )
  {
    v7 = 1039;
    goto LABEL_8;
  }
  if ( v32[0] )
  {
    v32[0] *= 24;
    v10 = AutoRpcImpersonateClient(&v46);
    wil::unique_call<long (*)(void),&long RpcRevertToSelf(void),1>::operator=(v31, v10);
    v11 = v46;
    v46 = 0;
    if ( v11 )
      RpcRevertToSelf();
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    v12 = SHGetKnownFolderItem(
            &FOLDERID_RecycleBinFolder,
            KF_FLAG_DEFAULT,
            0,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            &v35);
    v5 = v12;
    if ( v12 < 0 )
    {
      v13 = 1046;
      goto LABEL_17;
    }
    v14 = v35;
    v15 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v35 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    ppva = v34;
    v12 = v15(v14, 0, &BHID_EnumItems, &GUID_70629033_e363_4a28_a567_0db78006e6d7);
    v5 = v12;
    if ( v12 < 0 )
    {
      v13 = 1047;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v12,
        (int)ppva);
      v16 = v31[0] == 0;
      v31[0] = 0;
      if ( !v16 )
        RpcRevertToSelf();
      goto LABEL_19;
    }
    while ( 1 )
    {
      v18 = *(_QWORD *)v34;
      v19 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(**(_QWORD **)v34 + 24LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
      if ( v19(v18, 1, &v33) )
        break;
      pszPath = 0;
      v39 = 0;
      v40 = 0;
      v20 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
      if ( v33 )
      {
        v21 = **v33;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32[1]);
        if ( v21(v20, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v32[1]) >= 0 )
        {
          v22 = *(_QWORD *)&v32[1];
          v23 = *(int (__fastcall **)(__int64, __int64 *, LPCWSTR *))(**(_QWORD **)&v32[1] + 136LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
          v39 = -1;
          v40 = -1;
          if ( v23(v22, PKEY_Recycle_DeletedFrom, &pszPath) >= 0
            && DriveNumberW == PathGetDriveNumberW(pszPath)
            && (*(int (__fastcall **)(_QWORD, __int64 *, FILETIME *))(**(_QWORD **)&v32[1] + 120LL))(
                 *(_QWORD *)&v32[1],
                 PKEY_Recycle_DateDeleted,
                 &FileTime1) >= 0
            && (unsigned int)RecursiveUtil::CompareTimeThreshold(
                               &FileTime1,
                               (struct _FILETIME *)(unsigned int)v32[0],
                               v24) == -1
            && (*(int (__fastcall **)(_QWORD, const PROPERTYKEY *, __int64 *))(**(_QWORD **)&v32[1] + 152LL))(
                 *(_QWORD *)&v32[1],
                 &PKEY_Size,
                 &v41) >= 0 )
          {
            v25 = std::make_shared<RecycleBinPolicy,>(v43);
            *(_OWORD *)v42 = 0;
            v26 = *(std::_Ref_count_base **)v25;
            v42[0] = *(std::_Ref_count_base **)v25;
            v42[1] = *(std::_Ref_count_base **)(v25 + 8);
            *(_QWORD *)v25 = 0;
            *(_QWORD *)(v25 + 8) = 0;
            if ( v44 )
              std::_Ref_count_base::_Decref(v44);
            *((_QWORD *)v26 + 6) = v41;
            *((FILETIME *)v26 + 7) = FileTime1;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)v26 + 64);
            v27 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
            if ( v33 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, int *)))(*v33)[1])(v33);
              v27 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
            }
            *((_QWORD *)v26 + 8) = v27;
            std::list<std::shared_ptr<CCleanupPolicy>>::_Emplace<std::shared_ptr<CCleanupPolicy> const &>(a2, *a2, v42);
            if ( v42[1] )
              std::_Ref_count_base::_Decref(v42[1]);
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    }
    v28 = v31[0];
    v31[0] = 0;
    if ( v28 )
      RpcRevertToSelf();
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32[1]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    return 0;
  }
  else
  {
LABEL_38:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32[1]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x18003376c  push    rbp
0x18003376e  push    rbx
0x18003376f  push    rsi
0x180033770  push    rdi
0x180033771  push    r14
0x180033773  push    r15
0x180033775  lea     rbp, [rsp-2Fh]
0x18003377a  sub     rsp, 0B8h
0x180033781  mov     r14, rdx
0x180033784  xor     r15d, r15d
0x180033787  mov     [rbp+57h+var_90], r15
0x18003378b  mov     qword ptr [rbp+57h+var_98], r15
0x18003378f  mov     [rbp+57h+var_A0], r15
0x180033793  mov     qword ptr [rbp+57h+var_AC+4], r15
0x180033797  mov     [rbp+57h+var_60], r15
0x18003379b  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r15
0x18003379f  mov     [rbp+57h+var_88], r15d
0x1800337a3  mov     dword ptr [rbp+57h+var_AC], 2D0h
0x1800337aa  call    cs:__imp_PathGetDriveNumberW
0x1800337b0  mov     esi, eax
0x1800337b2  mov     [rbp+57h+var_B0], r15b
0x1800337b6  cmp     eax, 0FFFFFFFFh
0x1800337b9  jnz     short loc_1800337CA
0x1800337bb  mov     ebx, 80070057h
0x1800337c0  mov     r9d, ebx
0x1800337c3  mov     edx, 40Bh
0x1800337c8  jmp     short loc_18003380F
0x1800337ca  lea     r9, [rbp+57h+var_88]
0x1800337ce  xor     r8d, r8d
0x1800337d1  lea     edx, [r8+3]
0x1800337d5  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x1800337da  mov     ebx, eax
0x1800337dc  test    eax, eax
0x1800337de  jns     short loc_1800337E7
0x1800337e0  mov     edx, 40Dh
0x1800337e5  jmp     short loc_18003380C
0x1800337e7  cmp     [rbp+57h+var_88], r15d
0x1800337eb  jz      loc_180033B30
0x1800337f1  lea     r9, [rbp+57h+var_AC]
0x1800337f5  xor     r8d, r8d
0x1800337f8  lea     edx, [r8+8]
0x1800337fc  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x180033801  mov     ebx, eax
0x180033803  test    eax, eax
0x180033805  jns     short loc_180033829
0x180033807  mov     edx, 40Fh; void *
0x18003380c  mov     r9d, eax; char *
0x18003380f  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180033816  mov     rcx, [rbp+5Fh]; this
0x18003381a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003381f  nop
0x180033820  mov     [rbp+57h+var_B0], r15b
0x180033824  jmp     loc_180033906
0x180033829  mov     eax, dword ptr [rbp+57h+var_AC]
0x18003382c  test    eax, eax
0x18003382e  jz      loc_180033B30
0x180033834  lea     eax, [rax+rax*2]
0x180033837  shl     eax, 3
0x18003383a  mov     dword ptr [rbp+57h+var_AC], eax
0x18003383d  lea     rcx, [rbp+57h+arg_10]
0x180033841  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180033846  nop
0x180033847  mov     rdx, rax
0x18003384a  lea     rcx, [rbp+57h+var_B0]
0x18003384e  call    ??4?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1>::operator=(wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1> &&)
0x180033853  nop
0x180033854  mov     al, [rbp+57h+arg_10]
0x180033857  mov     [rbp+57h+arg_10], r15b
0x18003385b  test    al, al
0x18003385d  jz      short loc_180033865
0x18003385f  call    cs:__imp_RpcRevertToSelf
0x180033865  lea     rcx, [rbp+57h+var_90]
0x180033869  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003386e  lea     rax, [rbp+57h+var_90]
0x180033872  mov     [rsp+0E0h+ppv], rax; ppv
0x180033877  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003387e  xor     r8d, r8d; hToken
0x180033881  xor     edx, edx; flags
0x180033883  lea     rcx, FOLDERID_RecycleBinFolder; rfid
0x18003388a  call    cs:__imp_SHGetKnownFolderItem
0x180033890  mov     ebx, eax
0x180033892  test    eax, eax
0x180033894  jns     short loc_18003389D
0x180033896  mov     edx, 416h
0x18003389b  jmp     short loc_1800338E0
0x18003389d  mov     rdi, [rbp+57h+var_90]
0x1800338a1  mov     rax, [rdi]
0x1800338a4  mov     rbx, [rax+18h]
0x1800338a8  lea     rcx, [rbp+57h+var_98]
0x1800338ac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800338b1  lea     rax, [rbp+57h+var_98]
0x1800338b5  mov     [rsp+0E0h+ppv], rax; int
0x1800338ba  lea     r9, _GUID_70629033_e363_4a28_a567_0db78006e6d7
0x1800338c1  lea     r8, BHID_EnumItems
0x1800338c8  xor     edx, edx
0x1800338ca  mov     rcx, rdi
0x1800338cd  mov     rax, rbx
0x1800338d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338d5  mov     ebx, eax
0x1800338d7  test    eax, eax
0x1800338d9  jns     short loc_180033934
0x1800338db  mov     edx, 417h; void *
0x1800338e0  mov     r9d, eax; char *
0x1800338e3  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800338ea  mov     rcx, [rbp+5Fh]; this
0x1800338ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338f3  nop
0x1800338f4  mov     al, [rbp+57h+var_B0]
0x1800338f7  test    al, al
0x1800338f9  mov     [rbp+57h+var_B0], r15b
0x1800338fd  jz      short loc_180033906
0x1800338ff  call    cs:__imp_RpcRevertToSelf
0x180033905  nop
0x180033906  lea     rcx, [rbp+57h+var_AC+4]
0x18003390a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003390f  nop
0x180033910  lea     rcx, [rbp+57h+var_A0]
0x180033914  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033919  nop
0x18003391a  lea     rcx, [rbp+57h+var_98]
0x18003391e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033923  nop
0x180033924  lea     rcx, [rbp+57h+var_90]
0x180033928  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003392d  mov     eax, ebx
0x18003392f  jmp     loc_180033B60
0x180033934  mov     rdi, qword ptr [rbp+57h+var_98]
0x180033938  mov     rax, [rdi]
0x18003393b  mov     rbx, [rax+18h]
0x18003393f  lea     rcx, [rbp+57h+var_A0]
0x180033943  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033948  xor     r9d, r9d
0x18003394b  lea     r8, [rbp+57h+var_A0]
0x18003394f  lea     edx, [r9+1]
0x180033953  mov     rcx, rdi
0x180033956  mov     rax, rbx
0x180033959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003395e  test    eax, eax
0x180033960  jnz     loc_180033AF3
0x180033966  mov     [rbp+57h+pszPath], r15
0x18003396a  mov     [rbp+57h+var_70], r15
0x18003396e  mov     [rbp+57h+var_68], r15
0x180033972  mov     rbx, [rbp+57h+var_A0]
0x180033976  test    rbx, rbx
0x180033979  jnz     short loc_180033986
0x18003397b  lea     rcx, [rbp+57h+pszPath]
0x18003397f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180033984  jmp     short loc_180033934
0x180033986  mov     rax, [rbx]
0x180033989  mov     rdi, [rax]
0x18003398c  lea     rcx, [rbp+57h+var_AC+4]
0x180033990  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033995  lea     r8, [rbp+57h+var_AC+4]
0x180033999  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1800339a0  mov     rcx, rbx
0x1800339a3  mov     rax, rdi
0x1800339a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ab  test    eax, eax
0x1800339ad  js      short loc_18003397B
0x1800339af  mov     rdi, qword ptr [rbp+57h+var_AC+4]
0x1800339b3  mov     rax, [rdi]
0x1800339b6  mov     rbx, [rax+88h]
0x1800339bd  lea     rcx, [rbp+57h+pszPath]
0x1800339c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800339c6  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x1800339ce  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x1800339d6  lea     r8, [rbp+57h+pszPath]
0x1800339da  lea     rdx, PKEY_Recycle_DeletedFrom
0x1800339e1  mov     rcx, rdi
0x1800339e4  mov     rax, rbx
0x1800339e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ec  test    eax, eax
0x1800339ee  js      short loc_18003397B
0x1800339f0  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1800339f4  call    cs:__imp_PathGetDriveNumberW
0x1800339fa  cmp     esi, eax
0x1800339fc  jnz     loc_18003397B
0x180033a02  mov     rcx, qword ptr [rbp+57h+var_AC+4]
0x180033a06  mov     rax, [rcx]
0x180033a09  lea     r8, [rbp+57h+FileTime1]
0x180033a0d  lea     rdx, PKEY_Recycle_DateDeleted
0x180033a14  mov     rax, [rax+78h]
0x180033a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a1d  test    eax, eax
0x180033a1f  js      loc_18003397B
0x180033a25  mov     edx, dword ptr [rbp+57h+var_AC]; this
0x180033a28  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180033a2c  call    ?CompareTimeThreshold@RecursiveUtil@@YAJPEAU_FILETIME@@K@Z; RecursiveUtil::CompareTimeThreshold(_FILETIME *,ulong)
0x180033a31  cmp     eax, 0FFFFFFFFh
0x180033a34  jnz     loc_18003397B
0x180033a3a  mov     rcx, qword ptr [rbp+57h+var_AC+4]
0x180033a3e  mov     rax, [rcx]
0x180033a41  lea     r8, [rbp+57h+var_60]
0x180033a45  lea     rdx, PKEY_Size
0x180033a4c  mov     rax, [rax+98h]
0x180033a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a58  test    eax, eax
0x180033a5a  js      loc_18003397B
0x180033a60  lea     rcx, [rbp+57h+var_48]
0x180033a64  call    ??$make_shared@VRecycleBinPolicy@@$$V@std@@YA?AV?$shared_ptr@VRecycleBinPolicy@@@0@XZ; std::make_shared<RecycleBinPolicy,>(void)
0x180033a69  nop
0x180033a6a  xorps   xmm0, xmm0
0x180033a6d  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x180033a72  mov     rbx, [rax]
0x180033a75  mov     [rbp+57h+var_58], rbx
0x180033a79  mov     rcx, [rax+8]
0x180033a7d  mov     [rbp+57h+var_58+8], rcx
0x180033a81  mov     [rax], r15
0x180033a84  mov     [rax+8], r15
0x180033a88  mov     rcx, [rbp+57h+var_40]; this
0x180033a8c  test    rcx, rcx
0x180033a8f  jz      short loc_180033A96
0x180033a91  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180033a96  mov     rax, [rbp+57h+var_60]
0x180033a9a  mov     [rbx+30h], rax
0x180033a9e  mov     rax, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x180033aa2  mov     [rbx+38h], rax
0x180033aa6  lea     rcx, [rbx+40h]
0x180033aaa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033aaf  mov     rcx, [rbp+57h+var_A0]
0x180033ab3  test    rcx, rcx
0x180033ab6  jz      short loc_180033AC8
0x180033ab8  mov     rax, [rcx]
0x180033abb  mov     rax, [rax+8]
0x180033abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ac4  mov     rcx, [rbp+57h+var_A0]
0x180033ac8  mov     [rbx+40h], rcx
0x180033acc  lea     r8, [rbp+57h+var_58]
0x180033ad0  mov     rdx, [r14]
0x180033ad3  mov     rcx, r14
0x180033ad6  call    ??$_Emplace@AEBV?$shared_ptr@VCCleanupPolicy@@@std@@@?$list@V?$shared_ptr@VCCleanupPolicy@@@std@@V?$allocator@V?$shared_ptr@VCCleanupPolicy@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$shared_ptr@VCCleanupPolicy@@@std@@PEAX@1@QEAU21@AEBV?$shared_ptr@VCCleanupPolicy@@@1@@Z; std::list<std::shared_ptr<CCleanupPolicy>>::_Emplace<std::shared_ptr<CCleanupPolicy> const &>(std::_List_node<std::shared_ptr<CCleanupPolicy>,void *> * const,std::shared_ptr<CCleanupPolicy> const &)
0x180033adb  nop
0x180033adc  mov     rcx, [rbp+57h+var_58+8]; this
0x180033ae0  test    rcx, rcx
0x180033ae3  jz      loc_18003397B
0x180033ae9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180033aee  jmp     loc_18003397B
0x180033af3  mov     al, [rbp+57h+var_B0]
0x180033af6  mov     [rbp+57h+var_B0], r15b
0x180033afa  test    al, al
0x180033afc  jz      short loc_180033B05
0x180033afe  call    cs:__imp_RpcRevertToSelf
0x180033b04  nop
0x180033b05  lea     rcx, [rbp+57h+var_AC+4]
0x180033b09  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b0e  nop
0x180033b0f  lea     rcx, [rbp+57h+var_A0]
0x180033b13  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b18  nop
0x180033b19  lea     rcx, [rbp+57h+var_98]
0x180033b1d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b22  nop
0x180033b23  lea     rcx, [rbp+57h+var_90]
0x180033b27  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b2c  xor     eax, eax
0x180033b2e  jmp     short loc_180033B60
0x180033b30  mov     [rbp+57h+var_B0], r15b
0x180033b34  lea     rcx, [rbp+57h+var_AC+4]
0x180033b38  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b3d  nop
0x180033b3e  lea     rcx, [rbp+57h+var_A0]
0x180033b42  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b47  nop
0x180033b48  lea     rcx, [rbp+57h+var_98]
0x180033b4c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b51  nop
0x180033b52  lea     rcx, [rbp+57h+var_90]
0x180033b56  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033b5b  mov     eax, 80070005h
0x180033b60  add     rsp, 0B8h
0x180033b67  pop     r15
0x180033b69  pop     r14
0x180033b6b  pop     rdi
0x180033b6c  pop     rsi
0x180033b6d  pop     rbx
0x180033b6e  pop     rbp
0x180033b6f  retn
```
