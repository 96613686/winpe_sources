# CUserTileStore::SetImageForUser(ushort const *,IStream *)

- ea: `0x1800cc550`
- end: `0x1800cc7c6`
- name: `?SetImageForUser@CUserTileStore@@UEAAJPEBGPEAUIStream@@@Z`
- size: `630`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, struct IStream *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000c1b8`
- `0x18000c410`
- `0x180014e10`
- `0x1800343ec`
- `0x180036c2c`
- `0x18003729c`
- `0x18003c554`
- `0x180054130`
- `0x180084440`
- `0x1800cc550`
- `0x1800db3e8`
- `0x1800dcb08`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800cc60a`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800cc60a`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800cc5ab`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800cc5ab`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800cc735`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800cc735`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cc65c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cc65c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CUserTileStore::SetImageForUser(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        struct IStream *a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, const unsigned __int16 *, struct IStream *, _QWORD); // rbx
  unsigned int ScaleFactorForDevice; // eax
  const char *v12; // r9
  int v13; // eax
  HRESULT TilePath; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int *v17; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  int v21[2]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v17 = v21;
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      UserTile_Store_Commit_Start,
      a3,
      1);
  }
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) )
    return 2147943660LL;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v6 = CoCreateInstanceAsSystem(&CLSID_UserTileBroker, &GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76, &v20);
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = 1498;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    goto LABEL_24;
  }
  v9 = v20;
  v10 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IStream *, _QWORD))(*(_QWORD *)v20 + 32LL);
  ScaleFactorForDevice = GetScaleFactorForDevice(1);
  v6 = v10(v9, a2, a3, ScaleFactorForDevice);
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = 1499;
    goto LABEL_9;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    *(_QWORD *)v21 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v21,
      0);
    v13 = SHTranslateSIDToName(Sid, (wchar_t **)v21);
    LastError = v13;
    if ( v13 >= 0 )
    {
      v19 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      TilePath = _GetTilePath(1u, a2, 0, &v19);
      LastError = TilePath;
      if ( TilePath >= 0 )
      {
        TilePath = SHSetUserPicturePath(*(_QWORD *)v21, 0, v19);
        LastError = TilePath;
        if ( TilePath >= 0 )
        {
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              Microsoft_Windows_Shell_Core_Provider_Context,
              UserTile_Store_Commit_Stop,
              v16,
              1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v19);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          LastError = 0;
          goto LABEL_24;
        }
        v15 = 1508;
      }
      else
      {
        v15 = 1507;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)TilePath,
        (int)v17);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E1,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v13,
        (int)v17);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5DF,
                  (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
                  v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return LastError;
}

```

## disassembly

```asm
0x1800cc550  mov     [rsp-18h+arg_0], rbx
0x1800cc555  mov     [rsp-18h+arg_18], rsi
0x1800cc55a  push    rbp
0x1800cc55b  push    rdi
0x1800cc55c  push    r14
0x1800cc55e  mov     rbp, rsp
0x1800cc561  sub     rsp, 70h
0x1800cc565  mov     rax, cs:__security_cookie
0x1800cc56c  xor     rax, rsp
0x1800cc56f  mov     [rbp+var_8], rax
0x1800cc573  mov     r14, r8
0x1800cc576  mov     rsi, rdx
0x1800cc579  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800cc580  jz      short loc_1800CC5A4
0x1800cc582  lea     rax, [rbp+var_28]
0x1800cc586  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800cc58b  mov     r9d, 1
0x1800cc591  lea     rdx, UserTile_Store_Commit_Start
0x1800cc598  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1800cc59f  call    McGenEventWrite_EventWriteTransfer
0x1800cc5a4  lea     rcx, POLID_UseDefaultTile
0x1800cc5ab  call    cs:__imp_SHWindowsPolicy
0x1800cc5b2  nop     dword ptr [rax+rax+00h]
0x1800cc5b7  test    eax, eax
0x1800cc5b9  jz      short loc_1800CC5C5
0x1800cc5bb  mov     eax, 800704ECh
0x1800cc5c0  jmp     loc_1800CC7A4
0x1800cc5c5  mov     [rbp+var_30], 0
0x1800cc5cd  lea     rcx, [rbp+var_30]
0x1800cc5d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cc5d6  lea     r8, [rbp+var_30]
0x1800cc5da  lea     rdx, _GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76
0x1800cc5e1  lea     rcx, CLSID_UserTileBroker
0x1800cc5e8  call    CoCreateInstanceAsSystem
0x1800cc5ed  mov     ebx, eax
0x1800cc5ef  test    eax, eax
0x1800cc5f1  jns     short loc_1800CC5FA
0x1800cc5f3  mov     edx, 5DAh
0x1800cc5f8  jmp     short loc_1800CC635
0x1800cc5fa  mov     rdi, [rbp+var_30]
0x1800cc5fe  mov     rax, [rdi]
0x1800cc601  mov     rbx, [rax+20h]
0x1800cc605  mov     ecx, 1
0x1800cc60a  call    cs:__imp_GetScaleFactorForDevice
0x1800cc611  nop     dword ptr [rax+rax+00h]
0x1800cc616  mov     r9d, eax
0x1800cc619  mov     r8, r14
0x1800cc61c  mov     rdx, rsi
0x1800cc61f  mov     rcx, rdi
0x1800cc622  mov     rax, rbx
0x1800cc625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc62a  mov     ebx, eax
0x1800cc62c  test    eax, eax
0x1800cc62e  jns     short loc_1800CC64D
0x1800cc630  mov     edx, 5DBh; void *
0x1800cc635  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800cc63c  mov     r9d, eax; char *
0x1800cc63f  mov     rcx, [rbp+18h]; this
0x1800cc643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc648  jmp     loc_1800CC799
0x1800cc64d  mov     [rbp+Sid], 0
0x1800cc655  lea     rdx, [rbp+Sid]; Sid
0x1800cc659  mov     rcx, rsi; StringSid
0x1800cc65c  call    cs:__imp_ConvertStringSidToSidW
0x1800cc663  nop     dword ptr [rax+rax+00h]
0x1800cc668  test    eax, eax
0x1800cc66a  jnz     short loc_1800CC691
0x1800cc66c  mov     rcx, [rbp+18h]; this
0x1800cc670  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800cc677  mov     edx, 5DFh; void *
0x1800cc67c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc681  mov     ebx, eax
0x1800cc683  lea     rcx, [rbp+Sid]
0x1800cc687  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cc68c  jmp     loc_1800CC799
0x1800cc691  mov     qword ptr [rbp+var_28], 0
0x1800cc699  xor     edx, edx
0x1800cc69b  lea     rcx, [rbp+var_28]
0x1800cc69f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800cc6a4  lea     rdx, [rbp+var_28]
0x1800cc6a8  mov     rcx, [rbp+Sid]
0x1800cc6ac  call    SHTranslateSIDToName
0x1800cc6b1  mov     ebx, eax
0x1800cc6b3  test    eax, eax
0x1800cc6b5  jns     short loc_1800CC6DB
0x1800cc6b7  mov     rcx, [rbp+18h]; this
0x1800cc6bb  mov     r9d, eax; char *
0x1800cc6be  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800cc6c5  mov     edx, 5E1h; void *
0x1800cc6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc6cf  nop
0x1800cc6d0  lea     rcx, [rbp+var_28]
0x1800cc6d4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800cc6d9  jmp     short loc_1800CC683
0x1800cc6db  mov     [rbp+var_38], 0
0x1800cc6e3  xor     edx, edx
0x1800cc6e5  lea     rcx, [rbp+var_38]
0x1800cc6e9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800cc6ee  lea     r9, [rbp+var_38]
0x1800cc6f2  xor     r8d, r8d
0x1800cc6f5  mov     rdx, rsi
0x1800cc6f8  lea     ecx, [r8+1]
0x1800cc6fc  call    ?_GetTilePath@@YAJW4USER_TILE_TYPE@@PEBG_NPEAPEAG@Z; _GetTilePath(USER_TILE_TYPE,ushort const *,bool,ushort * *)
0x1800cc701  mov     ebx, eax
0x1800cc703  test    eax, eax
0x1800cc705  jns     short loc_1800CC72B
0x1800cc707  mov     edx, 5E3h; void *
0x1800cc70c  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800cc713  mov     r9d, eax; char *
0x1800cc716  mov     rcx, [rbp+18h]; this
0x1800cc71a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc71f  nop
0x1800cc720  lea     rcx, [rbp+var_38]
0x1800cc724  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800cc729  jmp     short loc_1800CC6D0
0x1800cc72b  mov     r8, [rbp+var_38]
0x1800cc72f  xor     edx, edx
0x1800cc731  mov     rcx, qword ptr [rbp+var_28]
0x1800cc735  call    cs:__imp_SHSetUserPicturePath
0x1800cc73c  nop     dword ptr [rax+rax+00h]
0x1800cc741  mov     ebx, eax
0x1800cc743  test    eax, eax
0x1800cc745  jns     short loc_1800CC74E
0x1800cc747  mov     edx, 5E4h
0x1800cc74c  jmp     short loc_1800CC70C
0x1800cc74e  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800cc755  jz      short loc_1800CC77A
0x1800cc757  lea     rax, [rbp+var_18]
0x1800cc75b  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc760  mov     r9d, 1
0x1800cc766  lea     rdx, UserTile_Store_Commit_Stop
0x1800cc76d  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1800cc774  call    McGenEventWrite_EventWriteTransfer
0x1800cc779  nop
0x1800cc77a  lea     rcx, [rbp+var_38]
0x1800cc77e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800cc783  nop
0x1800cc784  lea     rcx, [rbp+var_28]
0x1800cc788  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800cc78d  nop
0x1800cc78e  lea     rcx, [rbp+Sid]
0x1800cc792  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cc797  xor     ebx, ebx
0x1800cc799  lea     rcx, [rbp+var_30]
0x1800cc79d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cc7a2  mov     eax, ebx
0x1800cc7a4  mov     rcx, [rbp+var_8]
0x1800cc7a8  xor     rcx, rsp; StackCookie
0x1800cc7ab  call    __security_check_cookie
0x1800cc7b0  lea     r11, [rsp+70h+var_s0]
0x1800cc7b5  mov     rbx, [r11+20h]
0x1800cc7b9  mov     rsi, [r11+38h]
0x1800cc7bd  mov     rsp, r11
0x1800cc7c0  pop     r14
0x1800cc7c2  pop     rdi
0x1800cc7c3  pop     rbp
0x1800cc7c4  retn
```
