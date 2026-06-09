# Windows::System::Internal::Launch::LauncherQueryInfo::QueryFileSupport(Windows::Storage::IStorageFile *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x180020800`
- end: `0x180020d62`
- name: `?QueryFileSupport@LauncherQueryInfo@Launch@Internal@System@Windows@@EEAAJPEAUIStorageFile@Storage@5@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@45@@Z`
- size: `1378`
- prototype: `__int64 __fastcall(Windows::System::Internal::Launch::LauncherQueryInfo *__hidden this, struct Windows::Storage::IStorageFile *, HSTRING, enum Windows::System::LaunchQuerySupportStatus *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180020800`
- `0x180020d68`
- `0x180020e64`
- `0x180020e98`
- `0x180020f34`
- `0x180020fe0`
- `0x1800210a0`
- `0x1800210f8`
- `0x180021114`
- `0x1800211fc`
- `0x180021290`
- `0x180021494`
- `0x18002174c`
- `0x180041748`
- `0x1800596d8`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x180020c1b`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x180020c1b`
- `Windows.Storage!STORAGE_CStorageItem_GetValidatedStorageItem` at `0x18002093b`
- `Windows.Storage!STORAGE_CStorageItem_GetValidatedStorageItem` at `0x18002093b`
- `Windows.Storage!__imp_GetShellItemFromStorageItem` at `0x180020b71`
- `Windows.Storage!__imp_GetShellItemFromStorageItem` at `0x180020b71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800208ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800208ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020bcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ccb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020bcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ccb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020d48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Launch::LauncherQueryInfo::QueryFileSupport(
        Windows::System::Internal::Launch::LauncherQueryInfo *this,
        struct Windows::Storage::IStorageFile *a2,
        HSTRING a3,
        enum Windows::System::LaunchQuerySupportStatus *a4)
{
  __int64 (__fastcall *v7)(struct Windows::Storage::IStorageFile *, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  void *v11; // rdi
  int (__fastcall *v12)(void *, _QWORD, const GUID *, GUID *, PCWSTR *); // rbx
  PCWSTR v13; // rdi
  int v14; // ebx
  struct IAssocHandler *v15; // rcx
  int (__fastcall *v16)(PCWSTR, __int64, struct IAssocHandler **, HSTRING *); // r14
  struct IAssocHandler *v17; // rcx
  PCWSTR v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int ShellItemFromStorageItem; // eax
  const WCHAR *v23; // rax
  HRESULT v24; // eax
  __int64 v25; // rdx
  __int64 (__fastcall *v26)(struct Windows::Storage::IStorageFile *, GUID *, struct IAssocHandler **); // rbx
  int v27; // eax
  struct IAssocHandler *v28; // rdi
  ULONG (__stdcall *Release)(IAssocHandler *); // rbx
  int v30; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IAssocHandler *v33; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v34; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  void **v40; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[272]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v42[8]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v43[48]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  *(_DWORD *)a4 = 4;
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v40,
    "QueryFileSupport");
  v40 = &LauncherClientProvider::QueryFileSupport::`vftable';
  LauncherClientProvider::QueryFileSupport::StartActivity((LauncherClientProvider::QueryFileSupport *)&v40);
  string = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::Storage::IStorageFile *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(a2, &string);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v39 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v10 = QueryStateRepositoryForFileSupport(string, a3, &v39);
    v9 = v10;
    if ( v10 < 0 )
    {
      v25 = 1288;
    }
    else
    {
      v10 = EvaluateHandlersForSupport<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo>(v39, a3, a4);
      v9 = v10;
      if ( v10 >= 0 )
      {
        v32[0] = *(_DWORD *)a4 == 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        LauncherClientProvider::QueryFileSupport::QueryStateRepositoryForFile<unsigned short const *,bool>(
          &v40,
          &StringRawBuffer,
          v32);
        if ( !*(_DWORD *)a4 || a3 )
        {
LABEL_29:
          wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v40);
          v20 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v9 = 0;
          goto LABEL_32;
        }
        ppv = 0;
        v37 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        if ( (int)STORAGE_CStorageItem_GetValidatedStorageItem(a2, 0, &v37) >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          ShellItemFromStorageItem = GetShellItemFromStorageItem(v37, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
          if ( ShellItemFromStorageItem < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x515,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
              (const char *)(unsigned int)ShellItemFromStorageItem,
              v31);
        }
        v11 = ppv;
        if ( ppv )
          goto LABEL_8;
        v33 = 0;
        v26 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFile *, GUID *, struct IAssocHandler **))a2;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        v27 = v26(a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v33);
        v9 = v27;
        if ( v27 >= 0 )
        {
          v34 = 0;
          v28 = v33;
          Release = v33->lpVtbl[1].Release;
          WindowsDeleteString(0);
          v34 = 0;
          v30 = ((__int64 (__fastcall *)(struct IAssocHandler *, HSTRING *))Release)(v28, &v34);
          v9 = v30;
          if ( v30 >= 0 )
          {
            if ( v34 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
              v23 = WindowsGetStringRawBuffer(v34, 0);
              v24 = SHCreateItemFromParsingName(v23, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
              if ( v24 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x522,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
                  (const char *)(unsigned int)v24,
                  v31);
            }
            WindowsDeleteString(v34);
            v34 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            v11 = ppv;
            if ( !ppv )
            {
LABEL_25:
              v19 = v37;
              if ( v37 )
              {
                v37 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                v11 = ppv;
              }
              if ( v11 )
              {
                ppv = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
              }
              goto LABEL_29;
            }
LABEL_8:
            StringRawBuffer = 0;
            v12 = *(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, PCWSTR *))(*(_QWORD *)v11 + 24LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
            if ( v12(v11, 0, &BHID_EnumAssocHandlers, &GUID_973810ae_9599_4b88_9e4d_6ee98c9552da, &StringRawBuffer) >= 0 )
            {
              v13 = StringRawBuffer;
              v14 = 3;
              v15 = 0;
              v33 = 0;
              LODWORD(v34) = 0;
              while ( 1 )
              {
                v16 = *(int (__fastcall **)(PCWSTR, __int64, struct IAssocHandler **, HSTRING *))(*(_QWORD *)v13 + 24LL);
                if ( v15 )
                {
                  v33 = 0;
                  ((void (__fastcall *)(struct IAssocHandler *))v15->lpVtbl->Release)(v15);
                }
                if ( v16(v13, 1, &v33, &v34) < 0 || !(_DWORD)v34 )
                  break;
                v32[0] = 0;
                if ( IsTargetAppxPackaged(v33, v32) >= 0 && !v32[0] )
                {
                  v14 = 0;
                  break;
                }
                v15 = v33;
              }
              v17 = v33;
              if ( v33 )
              {
                v33 = 0;
                ((void (__fastcall *)(struct IAssocHandler *))v17->lpVtbl->Release)(v17);
              }
              v32[0] = v14 == 0;
              v33 = (struct IAssocHandler *)WindowsGetStringRawBuffer(string, 0);
              LauncherClientProvider::QueryFileSupport::QueryNonUWPSupportForFile<unsigned short const *,bool>(
                &v40,
                &v33,
                v32);
              if ( !v14 )
                *(_DWORD *)a4 = 0;
            }
            v18 = StringRawBuffer;
            if ( StringRawBuffer )
            {
              StringRawBuffer = 0;
              (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v18 + 16LL))(v18);
            }
            v11 = ppv;
            goto LABEL_25;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x51F,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
            (const char *)(unsigned int)v30,
            v31);
          WindowsDeleteString(v34);
          v34 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x51C,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
            (const char *)(unsigned int)v27,
            v31);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        WindowsDeleteString(string);
        string = 0;
        LauncherClientProvider::QueryFileSupport::~QueryFileSupport((LauncherClientProvider::QueryFileSupport *)&v40);
        return v9;
      }
      v25 = 1289;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      v31);
    goto LABEL_50;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x505,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
    (const char *)(unsigned int)v8,
    v31);
LABEL_32:
  WindowsDeleteString(string);
  string = 0;
  v40 = &LauncherClientProvider::QueryFileSupport::`vftable';
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v40);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v43);
  wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v42);
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(v41);
  return v9;
}

```

## disassembly

```asm
0x180020800  push    rbp
0x180020802  push    rbx
0x180020803  push    rsi
0x180020804  push    rdi
0x180020805  push    r12
0x180020807  push    r14
0x180020809  push    r15
0x18002080b  lea     rbp, [rsp-0D0h]
0x180020813  sub     rsp, 1D0h
0x18002081a  mov     rax, cs:__security_cookie
0x180020821  xor     rax, rsp
0x180020824  mov     [rbp+100h+var_40], rax
0x18002082b  mov     rsi, r9
0x18002082e  mov     rdi, r8
0x180020831  mov     r14, rdx
0x180020834  mov     dword ptr [r9], 4
0x18002083b  lea     rdx, aQueryfilesuppo; "QueryFileSupport"
0x180020842  lea     rcx, [rsp+200h+var_190]
0x180020847  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002084c  lea     r12, ??_7QueryFileSupport@LauncherClientProvider@@6B@; const LauncherClientProvider::QueryFileSupport::`vftable'
0x180020853  mov     [rsp+200h+var_190], r12
0x180020858  lea     rcx, [rsp+200h+var_190]; this
0x18002085d  call    ?StartActivity@QueryFileSupport@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::QueryFileSupport::StartActivity(void)
0x180020862  xor     r15d, r15d
0x180020865  mov     [rsp+200h+string], r15
0x18002086a  mov     rax, [r14]
0x18002086d  mov     rbx, [rax+30h]
0x180020871  xor     ecx, ecx; string
0x180020873  call    cs:__imp_WindowsDeleteString
0x180020879  mov     [rsp+200h+string], r15
0x18002087e  lea     rdx, [rsp+200h+string]
0x180020883  mov     rcx, r14
0x180020886  mov     rax, rbx
0x180020889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002088e  mov     ebx, eax
0x180020890  test    eax, eax
0x180020892  js      loc_180020B9F
0x180020898  mov     [rsp+200h+var_198], r15
0x18002089d  lea     rcx, [rsp+200h+var_198]
0x1800208a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800208a7  lea     r8, [rsp+200h+var_198]
0x1800208ac  mov     rdx, rdi
0x1800208af  mov     rcx, [rsp+200h+string]
0x1800208b4  call    ?QueryStateRepositoryForFileSupport@@YAJPEAUHSTRING__@@0PEAPEAU?$IVectorView@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@Z; QueryStateRepositoryForFileSupport(HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *> * *)
0x1800208b9  mov     ebx, eax
0x1800208bb  test    eax, eax
0x1800208bd  js      loc_180020C42
0x1800208c3  mov     r8, rsi
0x1800208c6  mov     rdx, rdi
0x1800208c9  mov     rcx, [rsp+200h+var_198]
0x1800208ce  call    ??$EvaluateHandlersForSupport@VFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z; EvaluateHandlersForSupport<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::FileTypeAssociationLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)
0x1800208d3  mov     ebx, eax
0x1800208d5  test    eax, eax
0x1800208d7  js      loc_180020C49
0x1800208dd  cmp     [rsi], r15d
0x1800208e0  setz    [rsp+200h+var_1D0]
0x1800208e5  xor     edx, edx; length
0x1800208e7  mov     rcx, [rsp+200h+string]; string
0x1800208ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1800208f2  mov     [rsp+200h+var_1A0], rax
0x1800208f7  lea     r8, [rsp+200h+var_1D0]
0x1800208fc  lea     rdx, [rsp+200h+var_1A0]
0x180020901  lea     rcx, [rsp+200h+var_190]
0x180020906  call    ??$QueryStateRepositoryForFile@PEBG_N@QueryFileSupport@LauncherClientProvider@@QEAAX$$QEAPEBG$$QEA_N@Z; LauncherClientProvider::QueryFileSupport::QueryStateRepositoryForFile<ushort const *,bool>(ushort const * &&,bool &&)
0x18002090b  cmp     [rsi], r15d
0x18002090e  jz      loc_180020AC8
0x180020914  test    rdi, rdi
0x180020917  jnz     loc_180020AC8
0x18002091d  mov     [rsp+200h+ppv], r15
0x180020922  mov     [rsp+200h+var_1A8], r15
0x180020927  lea     rcx, [rsp+200h+var_1A8]
0x18002092c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020931  lea     r8, [rsp+200h+var_1A8]
0x180020936  xor     edx, edx
0x180020938  mov     rcx, r14
0x18002093b  call    cs:__imp_STORAGE_CStorageItem_GetValidatedStorageItem
0x180020941  test    eax, eax
0x180020943  jns     loc_180020B56
0x180020949  mov     rdi, [rsp+200h+ppv]
0x18002094e  test    rdi, rdi
0x180020951  jz      loc_180020C69
0x180020957  mov     [rsp+200h+var_1A0], r15
0x18002095c  mov     rax, [rdi]
0x18002095f  mov     rbx, [rax+18h]
0x180020963  lea     rcx, [rsp+200h+var_1A0]
0x180020968  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002096d  lea     rax, [rsp+200h+var_1A0]
0x180020972  mov     qword ptr [rsp+200h+var_1E0], rax
0x180020977  lea     r9, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da
0x18002097e  lea     r8, BHID_EnumAssocHandlers
0x180020985  xor     edx, edx
0x180020987  mov     rcx, rdi
0x18002098a  mov     rax, rbx
0x18002098d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020992  test    eax, eax
0x180020994  js      loc_180020A6D
0x18002099a  mov     rdi, [rsp+200h+var_1A0]
0x18002099f  mov     ebx, 3
0x1800209a4  mov     rcx, r15
0x1800209a7  mov     [rsp+200h+var_1C8], rcx
0x1800209ac  mov     dword ptr [rsp+200h+var_1C0], r15d
0x1800209b1  mov     rax, [rdi]
0x1800209b4  mov     r14, [rax+18h]
0x1800209b8  test    rcx, rcx
0x1800209bb  jz      short loc_1800209CF
0x1800209bd  mov     [rsp+200h+var_1C8], r15
0x1800209c2  mov     rdx, [rcx]
0x1800209c5  mov     rax, [rdx+10h]
0x1800209c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ce  nop
0x1800209cf  lea     r9, [rsp+200h+var_1C0]
0x1800209d4  lea     r8, [rsp+200h+var_1C8]
0x1800209d9  mov     edx, 1
0x1800209de  mov     rcx, rdi
0x1800209e1  mov     rax, r14
0x1800209e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209e9  test    eax, eax
0x1800209eb  js      short loc_180020A1D
0x1800209ed  cmp     dword ptr [rsp+200h+var_1C0], r15d
0x1800209f2  jbe     short loc_180020A1D
0x1800209f4  mov     [rsp+200h+var_1D0], r15b
0x1800209f9  lea     rdx, [rsp+200h+var_1D0]; bool *
0x1800209fe  mov     rcx, [rsp+200h+var_1C8]; struct IAssocHandler *
0x180020a03  call    ?IsTargetAppxPackaged@@YAJPEAUIAssocHandler@@PEA_N@Z; IsTargetAppxPackaged(IAssocHandler *,bool *)
0x180020a08  test    eax, eax
0x180020a0a  js      short loc_180020A13
0x180020a0c  cmp     [rsp+200h+var_1D0], r15b
0x180020a11  jz      short loc_180020A1A
0x180020a13  mov     rcx, [rsp+200h+var_1C8]
0x180020a18  jmp     short loc_1800209B1
0x180020a1a  mov     ebx, r15d
0x180020a1d  mov     rcx, [rsp+200h+var_1C8]
0x180020a22  test    rcx, rcx
0x180020a25  jz      short loc_180020A39
0x180020a27  mov     [rsp+200h+var_1C8], r15
0x180020a2c  mov     rax, [rcx]
0x180020a2f  mov     rax, [rax+10h]
0x180020a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a38  nop
0x180020a39  test    ebx, ebx
0x180020a3b  setz    [rsp+200h+var_1D0]
0x180020a40  xor     edx, edx; length
0x180020a42  mov     rcx, [rsp+200h+string]; string
0x180020a47  call    cs:__imp_WindowsGetStringRawBuffer
0x180020a4d  mov     [rsp+200h+var_1C8], rax
0x180020a52  lea     r8, [rsp+200h+var_1D0]
0x180020a57  lea     rdx, [rsp+200h+var_1C8]
0x180020a5c  lea     rcx, [rsp+200h+var_190]
0x180020a61  call    ??$QueryNonUWPSupportForFile@PEBG_N@QueryFileSupport@LauncherClientProvider@@QEAAX$$QEAPEBG$$QEA_N@Z; LauncherClientProvider::QueryFileSupport::QueryNonUWPSupportForFile<ushort const *,bool>(ushort const * &&,bool &&)
0x180020a66  test    ebx, ebx
0x180020a68  jnz     short loc_180020A6D
0x180020a6a  mov     [rsi], r15d
0x180020a6d  mov     rcx, [rsp+200h+var_1A0]
0x180020a72  test    rcx, rcx
0x180020a75  jz      short loc_180020A89
0x180020a77  mov     [rsp+200h+var_1A0], r15
0x180020a7c  mov     rax, [rcx]
0x180020a7f  mov     rax, [rax+10h]
0x180020a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a88  nop
0x180020a89  mov     rdi, [rsp+200h+ppv]
0x180020a8e  mov     rcx, [rsp+200h+var_1A8]
0x180020a93  test    rcx, rcx
0x180020a96  jz      short loc_180020AAE
0x180020a98  mov     [rsp+200h+var_1A8], r15
0x180020a9d  mov     rax, [rcx]
0x180020aa0  mov     rax, [rax+10h]
0x180020aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aa9  mov     rdi, [rsp+200h+ppv]
0x180020aae  test    rdi, rdi
0x180020ab1  jz      short loc_180020AC8
0x180020ab3  mov     [rsp+200h+ppv], r15
0x180020ab8  mov     rax, [rdi]
0x180020abb  mov     rcx, rdi
0x180020abe  mov     rax, [rax+10h]
0x180020ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac7  nop
0x180020ac8  lea     rcx, [rsp+200h+var_190]
0x180020acd  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180020ad2  nop
0x180020ad3  mov     rcx, [rsp+200h+var_198]
0x180020ad8  test    rcx, rcx
0x180020adb  jz      short loc_180020AEF
0x180020add  mov     [rsp+200h+var_198], r15
0x180020ae2  mov     rax, [rcx]
0x180020ae5  mov     rax, [rax+10h]
0x180020ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aee  nop
0x180020aef  mov     ebx, r15d
0x180020af2  mov     rcx, [rsp+200h+string]; string
0x180020af7  call    cs:__imp_WindowsDeleteString
0x180020afd  mov     [rsp+200h+string], r15
0x180020b02  mov     [rsp+200h+var_190], r12
0x180020b07  lea     rcx, [rsp+200h+var_190]
0x180020b0c  call    ?Destroy@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180020b11  lea     rcx, [rbp+100h+var_70]; this
0x180020b18  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180020b1d  lea     rcx, [rbp+100h+var_78]
0x180020b24  call    ?reset@?$shared_object@V?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180020b29  lea     rcx, [rsp+200h+var_188]
0x180020b2e  call    ??1?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180020b33  mov     eax, ebx
0x180020b35  mov     rcx, [rbp+100h+var_40]
0x180020b3c  xor     rcx, rsp; StackCookie
0x180020b3f  call    __security_check_cookie
0x180020b44  add     rsp, 1D0h
0x180020b4b  pop     r15
0x180020b4d  pop     r14
0x180020b4f  pop     r12
0x180020b51  pop     rdi
0x180020b52  pop     rsi
0x180020b53  pop     rbx
0x180020b54  pop     rbp
0x180020b55  retn
0x180020b56  lea     rcx, [rsp+200h+ppv]
0x180020b5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b60  lea     r8, [rsp+200h+ppv]
0x180020b65  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180020b6c  mov     rcx, [rsp+200h+var_1A8]
0x180020b71  call    cs:__imp_GetShellItemFromStorageItem
0x180020b77  mov     rcx, [rbp+108h]; this
0x180020b7e  test    eax, eax
0x180020b80  jns     loc_180020949
0x180020b86  mov     r9d, eax; char *
0x180020b89  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180020b90  mov     edx, 515h; void *
0x180020b95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020b9a  jmp     loc_180020949
0x180020b9f  mov     rcx, [rbp+108h]; this
0x180020ba6  mov     r9d, eax; char *
0x180020ba9  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180020bb0  mov     edx, 505h; void *
0x180020bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bba  jmp     loc_180020AF2
0x180020bbf  cmp     [rsp+200h+var_1C0], r15
0x180020bc4  jnz     short loc_180020BF3
0x180020bc6  mov     rcx, [rsp+200h+var_1C0]; string
0x180020bcb  call    cs:__imp_WindowsDeleteString
0x180020bd1  mov     [rsp+200h+var_1C0], r15
0x180020bd6  lea     rcx, [rsp+200h+var_1C8]
0x180020bdb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020be0  mov     rdi, [rsp+200h+ppv]
0x180020be5  test    rdi, rdi
0x180020be8  jz      loc_180020A8E
0x180020bee  jmp     loc_180020957
0x180020bf3  lea     rcx, [rsp+200h+ppv]
0x180020bf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020bfd  xor     edx, edx; length
0x180020bff  mov     rcx, [rsp+200h+var_1C0]; string
0x180020c04  call    cs:__imp_WindowsGetStringRawBuffer
0x180020c0a  lea     r9, [rsp+200h+ppv]; ppv
0x180020c0f  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180020c16  xor     edx, edx; pbc
0x180020c18  mov     rcx, rax; pszPath
0x180020c1b  call    cs:__imp_SHCreateItemFromParsingName
0x180020c21  mov     rcx, [rbp+108h]; this
0x180020c28  test    eax, eax
0x180020c2a  jns     short loc_180020BC6
0x180020c2c  mov     r9d, eax; char *
0x180020c2f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180020c36  mov     edx, 522h; void *
0x180020c3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020c40  jmp     short loc_180020BC6
0x180020c42  mov     edx, 508h
0x180020c47  jmp     short loc_180020C4E
0x180020c49  mov     edx, 509h; void *
0x180020c4e  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180020c55  mov     r9d, eax; char *
0x180020c58  mov     rcx, [rbp+108h]; this
0x180020c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c64  jmp     loc_180020D39
0x180020c69  mov     [rsp+200h+var_1C8], r15
0x180020c6e  mov     rax, [r14]
0x180020c71  mov     rbx, [rax]
0x180020c74  lea     rcx, [rsp+200h+var_1C8]
0x180020c79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020c7e  lea     r8, [rsp+200h+var_1C8]
0x180020c83  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180020c8a  mov     rcx, r14
0x180020c8d  mov     rax, rbx
0x180020c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c95  mov     ebx, eax
0x180020c97  test    eax, eax
0x180020c99  jns     short loc_180020CB8
0x180020c9b  mov     rcx, [rbp+108h]; this
0x180020ca2  mov     r9d, eax; char *
0x180020ca5  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180020cac  mov     edx, 51Ch; void *
0x180020cb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cb6  jmp     short loc_180020D1B
0x180020cb8  mov     [rsp+200h+var_1C0], r15
0x180020cbd  mov     rdi, [rsp+200h+var_1C8]
0x180020cc2  mov     rax, [rdi]
0x180020cc5  mov     rbx, [rax+60h]
0x180020cc9  xor     ecx, ecx; string
0x180020ccb  call    cs:__imp_WindowsDeleteString
0x180020cd1  mov     [rsp+200h+var_1C0], r15
0x180020cd6  lea     rdx, [rsp+200h+var_1C0]
0x180020cdb  mov     rcx, rdi
0x180020cde  mov     rax, rbx
  ... truncated ...
```
