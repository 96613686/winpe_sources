# Windows::System::Internal::Launch::LauncherQueryInfo::QueryUriSupport(Windows::Foundation::IUriRuntimeClass *,Windows::System::LaunchQuerySupportType,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x18002a700`
- end: `0x18002ab37`
- name: `?QueryUriSupport@LauncherQueryInfo@Launch@Internal@System@Windows@@EEAAJPEAUIUriRuntimeClass@Foundation@5@W4LaunchQuerySupportType@45@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@45@@Z`
- size: `1079`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18002073c`
- `0x180020e64`
- `0x180020e98`
- `0x180020fe0`
- `0x1800210a0`
- `0x1800210f8`
- `0x180021114`
- `0x18002a700`
- `0x18002ab40`
- `0x18002be8c`
- `0x18002c738`
- `0x180041d2c`
- `0x1800596d8`
- `0x18008a030`
- `0x1800d07c0`
- `0x1800d09d4`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x18002a9c5`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18002a9c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a8fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aaf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a8fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aaf6`

## string_xrefs

- `0x18002a746`: `QueryUriSupport`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Launch::LauncherQueryInfo::QueryUriSupport(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5)
{
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  const WCHAR *v18; // rax
  HRESULT v19; // eax
  void *v20; // rbx
  int (__fastcall *v21)(void *, _QWORD, const GUID *, GUID *); // rdi
  int NonUWPAppAvailability; // eax
  int v23; // ebx
  int v25; // [rsp+20h] [rbp-E0h]
  bool v26[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v27; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IEnumAssocHandlers *StringRawBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  void **v33; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[272]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v35[8]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v36[48]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  *a5 = 4;
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v33,
    "QueryUriSupport");
  v33 = &LauncherClientProvider::QueryUriSupport::`vftable';
  LauncherClientProvider::QueryUriSupport::StartActivity((LauncherClientProvider::QueryUriSupport *)&v33);
  string = 0;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(a2, &string);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v31 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v11 = QueryStateRepositoryForUriSupport(string, a4, a3, &v31);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CE,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v11,
        v25);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      WindowsDeleteString(string);
      string = 0;
      LauncherClientProvider::QueryUriSupport::~QueryUriSupport((LauncherClientProvider::QueryUriSupport *)&v33);
      return v10;
    }
    v12 = EvaluateHandlersForSupport<Windows::Internal::StateRepository::ProtocolLauncherInfo>(v31, a4, a5);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CF,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v12,
        v25);
      v13 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      goto LABEL_8;
    }
    v26[0] = *a5 == 0;
    StringRawBuffer = (struct IEnumAssocHandlers *)WindowsGetStringRawBuffer(string, 0);
    LauncherClientProvider::QueryUriSupport::QueryStateRepositoryForUri<unsigned short const *,bool>(
      &v33,
      &StringRawBuffer,
      v26);
    if ( *a5 && !a3 && !a4 )
    {
      ppv = 0;
      v27 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
      WindowsDeleteString(0);
      v27 = 0;
      v15 = v14(a2, &v27);
      v10 = v15;
      if ( v15 < 0 )
      {
        v16 = 1241;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v15,
          v25);
LABEL_15:
        WindowsDeleteString(v27);
        v27 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        goto LABEL_31;
      }
      if ( v27 )
        goto LABEL_20;
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 128LL);
      WindowsDeleteString(0);
      v27 = 0;
      v15 = v17(a2, &v27);
      v10 = v15;
      if ( v15 < 0 )
      {
        v16 = 1247;
        goto LABEL_14;
      }
      if ( v27 )
      {
LABEL_20:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v18 = WindowsGetStringRawBuffer(v27, 0);
        v19 = SHCreateItemFromParsingName(v18, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4E4,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
            (const char *)(unsigned int)v19,
            v25);
        v20 = ppv;
        if ( ppv )
        {
          StringRawBuffer = 0;
          v21 = *(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
          if ( v21(v20, 0, &BHID_EnumAssocHandlers, &GUID_973810ae_9599_4b88_9e4d_6ee98c9552da) >= 0 )
          {
            LODWORD(v32[0]) = 3;
            NonUWPAppAvailability = GetNonUWPAppAvailability(
                                      StringRawBuffer,
                                      (enum Windows::System::LaunchQuerySupportStatus *)v32);
            v10 = NonUWPAppAvailability;
            if ( NonUWPAppAvailability < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4EB,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
                (const char *)(unsigned int)NonUWPAppAvailability,
                (int)&StringRawBuffer);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
              goto LABEL_15;
            }
            v23 = v32[0];
            v26[0] = LODWORD(v32[0]) == 0;
            v32[0] = WindowsGetStringRawBuffer(string, 0);
            LauncherClientProvider::QueryUriSupport::QueryNonUWPSupportForUri<unsigned short const *,bool>(
              &v33,
              v32,
              v26);
            if ( !v23 )
              *a5 = 0;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
        }
      }
      WindowsDeleteString(v27);
      v27 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v33);
    v10 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4CB,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
    (const char *)(unsigned int)v9,
    v25);
LABEL_8:
  WindowsDeleteString(string);
  string = 0;
  v33 = &LauncherClientProvider::QueryUriSupport::`vftable';
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v33);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v36);
  wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v35);
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(v34);
  return v10;
}

```

## disassembly

```asm
0x18002a700  mov     [rsp-8+arg_0], rbx
0x18002a705  push    rbp
0x18002a706  push    rsi
0x18002a707  push    rdi
0x18002a708  push    r12
0x18002a70a  push    r13
0x18002a70c  push    r14
0x18002a70e  push    r15
0x18002a710  lea     rbp, [rsp-0D0h]
0x18002a718  sub     rsp, 1D0h
0x18002a71f  mov     rax, cs:__security_cookie
0x18002a726  xor     rax, rsp
0x18002a729  mov     [rbp+100h+var_40], rax
0x18002a730  mov     r14, r9
0x18002a733  mov     r15d, r8d
0x18002a736  mov     rdi, rdx
0x18002a739  mov     rsi, [rbp+100h+arg_20]
0x18002a740  mov     dword ptr [rsi], 4
0x18002a746  lea     rdx, aQueryurisuppor; "QueryUriSupport"
0x18002a74d  lea     rcx, [rsp+200h+var_190]
0x18002a752  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002a757  lea     r13, ??_7QueryUriSupport@LauncherClientProvider@@6B@; const LauncherClientProvider::QueryUriSupport::`vftable'
0x18002a75e  mov     [rsp+200h+var_190], r13
0x18002a763  lea     rcx, [rsp+200h+var_190]; this
0x18002a768  call    ?StartActivity@QueryUriSupport@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::QueryUriSupport::StartActivity(void)
0x18002a76d  xor     r12d, r12d
0x18002a770  mov     [rsp+200h+string], r12
0x18002a775  mov     rax, [rdi]
0x18002a778  mov     rbx, [rax+88h]
0x18002a77f  xor     ecx, ecx; string
0x18002a781  call    cs:__imp_WindowsDeleteString
0x18002a787  mov     [rsp+200h+string], r12
0x18002a78c  lea     rdx, [rsp+200h+string]
0x18002a791  mov     rcx, rdi
0x18002a794  mov     rax, rbx
0x18002a797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a79c  mov     ebx, eax
0x18002a79e  test    eax, eax
0x18002a7a0  jns     short loc_18002A7C2
0x18002a7a2  mov     rcx, [rbp+108h]; this
0x18002a7a9  mov     r9d, eax; char *
0x18002a7ac  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002a7b3  mov     edx, 4CBh; void *
0x18002a7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7bd  jmp     loc_18002A85A
0x18002a7c2  mov     [rsp+200h+var_1A8], r12
0x18002a7c7  lea     rcx, [rsp+200h+var_1A8]
0x18002a7cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a7d1  lea     r9, [rsp+200h+var_1A8]
0x18002a7d6  mov     r8d, r15d
0x18002a7d9  mov     rdx, r14
0x18002a7dc  mov     rcx, [rsp+200h+string]
0x18002a7e1  call    ?QueryStateRepositoryForUriSupport@@YAJPEAUHSTRING__@@0W4LaunchQuerySupportType@System@Windows@@PEAPEAU?$IVectorView@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@4@@Z; QueryStateRepositoryForUriSupport(HSTRING__ *,HSTRING__ *,Windows::System::LaunchQuerySupportType,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ProtocolLauncherInfo *> * *)
0x18002a7e6  mov     ebx, eax
0x18002a7e8  test    eax, eax
0x18002a7ea  jns     short loc_18002A80C
0x18002a7ec  mov     rcx, [rbp+108h]; this
0x18002a7f3  mov     r9d, eax; char *
0x18002a7f6  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002a7fd  mov     edx, 4CEh; void *
0x18002a802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a807  jmp     loc_18002AAE7
0x18002a80c  mov     r8, rsi
0x18002a80f  mov     rdx, r14
0x18002a812  mov     rcx, [rsp+200h+var_1A8]
0x18002a817  call    ??$EvaluateHandlersForSupport@VProtocolLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z; EvaluateHandlersForSupport<Windows::Internal::StateRepository::ProtocolLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ProtocolLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)
0x18002a81c  mov     ebx, eax
0x18002a81e  test    eax, eax
0x18002a820  jns     short loc_18002A8A0
0x18002a822  mov     rcx, [rbp+108h]; this
0x18002a829  mov     r9d, eax; char *
0x18002a82c  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002a833  mov     edx, 4CFh; void *
0x18002a838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a83d  nop
0x18002a83e  mov     rcx, [rsp+200h+var_1A8]
0x18002a843  test    rcx, rcx
0x18002a846  jz      short loc_18002A85A
0x18002a848  mov     [rsp+200h+var_1A8], r12
0x18002a84d  mov     rax, [rcx]
0x18002a850  mov     rax, [rax+10h]
0x18002a854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a859  nop
0x18002a85a  mov     rcx, [rsp+200h+string]; string
0x18002a85f  call    cs:__imp_WindowsDeleteString
0x18002a865  mov     [rsp+200h+string], r12
0x18002a86a  mov     [rsp+200h+var_190], r13
0x18002a86f  lea     rcx, [rsp+200h+var_190]
0x18002a874  call    ?Destroy@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002a879  lea     rcx, [rbp+100h+var_70]; this
0x18002a880  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18002a885  lea     rcx, [rbp+100h+var_78]
0x18002a88c  call    ?reset@?$shared_object@V?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18002a891  lea     rcx, [rsp+200h+var_188]
0x18002a896  call    ??1?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002a89b  jmp     loc_18002AB0B
0x18002a8a0  cmp     [rsi], r12d
0x18002a8a3  setz    [rsp+200h+var_1D0]
0x18002a8a8  xor     edx, edx; length
0x18002a8aa  mov     rcx, [rsp+200h+string]; string
0x18002a8af  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a8b5  mov     [rsp+200h+var_1B0], rax
0x18002a8ba  lea     r8, [rsp+200h+var_1D0]
0x18002a8bf  lea     rdx, [rsp+200h+var_1B0]
0x18002a8c4  lea     rcx, [rsp+200h+var_190]
0x18002a8c9  call    ??$QueryStateRepositoryForUri@PEBG_N@QueryUriSupport@LauncherClientProvider@@QEAAX$$QEAPEBG$$QEA_N@Z; LauncherClientProvider::QueryUriSupport::QueryStateRepositoryForUri<ushort const *,bool>(ushort const * &&,bool &&)
0x18002a8ce  cmp     [rsi], r12d
0x18002a8d1  jz      loc_18002AADA
0x18002a8d7  test    r15d, r15d
0x18002a8da  jnz     loc_18002AADA
0x18002a8e0  test    r14, r14
0x18002a8e3  jnz     loc_18002AADA
0x18002a8e9  mov     [rsp+200h+ppv], r12
0x18002a8ee  mov     [rsp+200h+var_1C8], r12
0x18002a8f3  mov     rax, [rdi]
0x18002a8f6  mov     rbx, [rax+30h]
0x18002a8fa  xor     ecx, ecx; string
0x18002a8fc  call    cs:__imp_WindowsDeleteString
0x18002a902  mov     [rsp+200h+var_1C8], r12
0x18002a907  lea     rdx, [rsp+200h+var_1C8]
0x18002a90c  mov     rcx, rdi
0x18002a90f  mov     rax, rbx
0x18002a912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a917  mov     ebx, eax
0x18002a919  test    eax, eax
0x18002a91b  jns     short loc_18002A957
0x18002a91d  mov     edx, 4D9h; void *
0x18002a922  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002a929  mov     r9d, eax; char *
0x18002a92c  mov     rcx, [rbp+108h]; this
0x18002a933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a938  mov     rcx, [rsp+200h+var_1C8]; string
0x18002a93d  call    cs:__imp_WindowsDeleteString
0x18002a943  mov     [rsp+200h+var_1C8], r12
0x18002a948  lea     rcx, [rsp+200h+ppv]
0x18002a94d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a952  jmp     loc_18002AAE7
0x18002a957  cmp     [rsp+200h+var_1C8], r12
0x18002a95c  jnz     short loc_18002A99D
0x18002a95e  mov     rax, [rdi]
0x18002a961  mov     rbx, [rax+80h]
0x18002a968  xor     ecx, ecx; string
0x18002a96a  call    cs:__imp_WindowsDeleteString
0x18002a970  mov     [rsp+200h+var_1C8], r12
0x18002a975  lea     rdx, [rsp+200h+var_1C8]
0x18002a97a  mov     rcx, rdi
0x18002a97d  mov     rax, rbx
0x18002a980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a985  mov     ebx, eax
0x18002a987  test    eax, eax
0x18002a989  jns     short loc_18002A992
0x18002a98b  mov     edx, 4DFh
0x18002a990  jmp     short loc_18002A922
0x18002a992  cmp     [rsp+200h+var_1C8], r12
0x18002a997  jz      loc_18002AAC0
0x18002a99d  lea     rcx, [rsp+200h+ppv]
0x18002a9a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a9a7  xor     edx, edx; length
0x18002a9a9  mov     rcx, [rsp+200h+var_1C8]; string
0x18002a9ae  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a9b4  lea     r9, [rsp+200h+ppv]; ppv
0x18002a9b9  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18002a9c0  xor     edx, edx; pbc
0x18002a9c2  mov     rcx, rax; pszPath
0x18002a9c5  call    cs:__imp_SHCreateItemFromParsingName
0x18002a9cb  test    eax, eax
0x18002a9cd  jns     short loc_18002A9EA
0x18002a9cf  mov     rcx, [rbp+108h]; this
0x18002a9d6  mov     r9d, eax; char *
0x18002a9d9  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002a9e0  mov     edx, 4E4h; void *
0x18002a9e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a9ea  mov     rbx, [rsp+200h+ppv]
0x18002a9ef  test    rbx, rbx
0x18002a9f2  jz      loc_18002AAC0
0x18002a9f8  mov     [rsp+200h+var_1B0], r12
0x18002a9fd  mov     rax, [rbx]
0x18002aa00  mov     rdi, [rax+18h]
0x18002aa04  lea     rcx, [rsp+200h+var_1B0]
0x18002aa09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aa0e  lea     rax, [rsp+200h+var_1B0]
0x18002aa13  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x18002aa18  lea     r9, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da
0x18002aa1f  lea     r8, BHID_EnumAssocHandlers
0x18002aa26  xor     edx, edx
0x18002aa28  mov     rcx, rbx
0x18002aa2b  mov     rax, rdi
0x18002aa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa33  test    eax, eax
0x18002aa35  js      short loc_18002AAB6
0x18002aa37  mov     dword ptr [rsp+200h+var_1A0], 3
0x18002aa3f  lea     rdx, [rsp+200h+var_1A0]; enum Windows::System::LaunchQuerySupportStatus *
0x18002aa44  mov     rcx, [rsp+200h+var_1B0]; struct IEnumAssocHandlers *
0x18002aa49  call    ?GetNonUWPAppAvailability@@YAJPEAUIEnumAssocHandlers@@PEAW4LaunchQuerySupportStatus@System@Windows@@@Z; GetNonUWPAppAvailability(IEnumAssocHandlers *,Windows::System::LaunchQuerySupportStatus *)
0x18002aa4e  mov     ebx, eax
0x18002aa50  test    eax, eax
0x18002aa52  jns     short loc_18002AA7E
0x18002aa54  mov     rcx, [rbp+108h]; this
0x18002aa5b  mov     r9d, eax; char *
0x18002aa5e  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002aa65  mov     edx, 4EBh; void *
0x18002aa6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa6f  lea     rcx, [rsp+200h+var_1B0]
0x18002aa74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aa79  jmp     loc_18002A938
0x18002aa7e  mov     ebx, dword ptr [rsp+200h+var_1A0]
0x18002aa82  test    ebx, ebx
0x18002aa84  setz    [rsp+200h+var_1D0]
0x18002aa89  xor     edx, edx; length
0x18002aa8b  mov     rcx, [rsp+200h+string]; string
0x18002aa90  call    cs:__imp_WindowsGetStringRawBuffer
0x18002aa96  mov     [rsp+200h+var_1A0], rax
0x18002aa9b  lea     r8, [rsp+200h+var_1D0]
0x18002aaa0  lea     rdx, [rsp+200h+var_1A0]
0x18002aaa5  lea     rcx, [rsp+200h+var_190]
0x18002aaaa  call    ??$QueryNonUWPSupportForUri@PEBG_N@QueryUriSupport@LauncherClientProvider@@QEAAX$$QEAPEBG$$QEA_N@Z; LauncherClientProvider::QueryUriSupport::QueryNonUWPSupportForUri<ushort const *,bool>(ushort const * &&,bool &&)
0x18002aaaf  test    ebx, ebx
0x18002aab1  jnz     short loc_18002AAB6
0x18002aab3  mov     [rsi], r12d
0x18002aab6  lea     rcx, [rsp+200h+var_1B0]
0x18002aabb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aac0  mov     rcx, [rsp+200h+var_1C8]; string
0x18002aac5  call    cs:__imp_WindowsDeleteString
0x18002aacb  mov     [rsp+200h+var_1C8], r12
0x18002aad0  lea     rcx, [rsp+200h+ppv]
0x18002aad5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aada  lea     rcx, [rsp+200h+var_190]
0x18002aadf  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002aae4  mov     ebx, r12d
0x18002aae7  lea     rcx, [rsp+200h+var_1A8]
0x18002aaec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aaf1  mov     rcx, [rsp+200h+string]; string
0x18002aaf6  call    cs:__imp_WindowsDeleteString
0x18002aafc  mov     [rsp+200h+string], r12
0x18002ab01  lea     rcx, [rsp+200h+var_190]; this
0x18002ab06  call    ??1QueryUriSupport@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::QueryUriSupport::~QueryUriSupport(void)
0x18002ab0b  mov     eax, ebx
0x18002ab0d  mov     rcx, [rbp+100h+var_40]
0x18002ab14  xor     rcx, rsp; StackCookie
0x18002ab17  call    __security_check_cookie
0x18002ab1c  mov     rbx, [rsp+200h+arg_0]
0x18002ab24  add     rsp, 1D0h
0x18002ab2b  pop     r15
0x18002ab2d  pop     r14
0x18002ab2f  pop     r13
0x18002ab31  pop     r12
0x18002ab33  pop     rdi
0x18002ab34  pop     rsi
0x18002ab35  pop     rbp
0x18002ab36  retn
```
