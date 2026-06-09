# WamObjectStoreImplementation::GetEntry(IUnknown *,HSTRING__ *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180009f40`
- end: `0x18000a5c5`
- name: `?GetEntry@WamObjectStoreImplementation@@QEAAJPEAUIUnknown@@PEAUHSTRING__@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `1669`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, struct IUnknown *, HSTRING, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008f40`

## callees

- `0x180007350`
- `0x180009e80`
- `0x180009f40`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001ffdc`
- `0x18007ad10`
- `0x18008e690`
- `0x180091969`
- `0x18009a6fc`
- `0x18009a8a0`
- `0x1800d7190`
- `0x1800d81d8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a109`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a109`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a01c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a01c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a2a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a431`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a2a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a431`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a581`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a4e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a30a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a30a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180009fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180009fad`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000a18f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000a18f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a148`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a148`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a4ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a4ba`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a3b4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a3b4`

## string_xrefs

- `0x18000a167`: `Windows.Storage.Streams.DataWriter`
- `0x18000a3e4`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000a450`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000a4fe`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000a535`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000a56c`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WamObjectStoreImplementation::GetEntry(
        PSRWLOCK SRWLock,
        struct IUnknown *a2,
        HSTRING a3,
        struct Windows::Storage::Streams::IBuffer **a4)
{
  _lambda_570d6c12d7f446ca7443779868589c96_ *v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // r8
  struct Windows::Storage::Streams::IBuffer *v13; // rbx
  void *v14; // r15
  char v15; // r14
  signed int v16; // edi
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  struct Windows::Storage::Streams::IBuffer *v22; // rcx
  __int64 v23; // rcx
  HRESULT v25; // eax
  struct Windows::Storage::Streams::IBuffer *v26; // rcx
  __int64 v27; // rcx
  struct Windows::Storage::Streams::IBuffer *v28; // rcx
  __int64 v29; // rcx
  signed int LastError; // eax
  int PrivilegeSet; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Storage::Streams::IBuffer *v34; // [rsp+50h] [rbp-B0h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL AccessStatus; // [rsp+60h] [rbp-A0h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v38[16]; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK v39; // [rsp+78h] [rbp-88h]
  _BYTE v40[32]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B8h] [rbp-48h]
  HSTRING v45[2]; // [rsp+C0h] [rbp-40h]
  HSTRING v46[2]; // [rsp+D0h] [rbp-30h]
  HSTRING string[28]; // [rsp+E0h] [rbp-20h]
  HANDLE v48[2]; // [rsp+1C0h] [rbp+C0h]
  HANDLE hObject[2]; // [rsp+1D0h] [rbp+D0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v32 = 0;
  v8 = _lambda_570d6c12d7f446ca7443779868589c96_::_lambda_570d6c12d7f446ca7443779868589c96_(
         (_lambda_570d6c12d7f446ca7443779868589c96_ *)&v34,
         &v32);
  wil::ScopeExit<_lambda_3876c2633569fbadd92ad93bfc26ac25_>(v38, v8);
  if ( !a2 || WindowsIsStringEmpty(a3) || !a4 )
  {
    wil::details::ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___::_ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___(v38);
    return 2147942487LL;
  }
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  *(_OWORD *)v45 = 0;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)string = 0;
  *(_OWORD *)v48 = 0;
  *(_OWORD *)hObject = 0;
  v9 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
         (Windows::Internal::Security::Authentication::Web::CallerContext *)&v41,
         a2,
         0,
         0);
  v10 = v9;
  v32 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v9,
      PrivilegeSet);
    Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v41);
    wil::details::ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___::_ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___(v38);
    return v10;
  }
  AcquireSRWLockShared(SRWLock);
  v39 = SRWLock;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  memset(v40, 0, sizeof(v40));
  v12 = -1;
  do
    ++v12;
  while ( StringRawBuffer[v12] );
  std::wstring::_Construct<1,unsigned short const *>(v40, StringRawBuffer);
  std::_Hash<std::_Umap_traits<std::wstring,WamObjectEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,WamObjectEntry>>,0>>::find(
    &SRWLock[1],
    &v34,
    v40);
  if ( *(_QWORD *)&v40[24] > 7u )
    std::_Deallocate<16>(*(_QWORD *)v40, 2LL * *(_QWORD *)&v40[24] + 2);
  v13 = v34;
  if ( v34 == SRWLock[2].Ptr )
  {
    v32 = -2147023728;
LABEL_34:
    ReleaseSRWLockShared(SRWLock);
    v20 = v32;
    if ( (unsigned __int64)hObject[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[1]);
    if ( hObject[0] )
      CloseHandle(hObject[0]);
    if ( (unsigned __int64)v48[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v48[1]);
    if ( (unsigned __int64)v48[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v48[0]);
    if ( string[1] )
      WindowsDeleteString(string[1]);
    if ( string[0] )
      WindowsDeleteString(string[0]);
    if ( v46[1] )
      WindowsDeleteString(v46[1]);
    if ( v46[0] )
      WindowsDeleteString(v46[0]);
    if ( v45[1] )
      WindowsDeleteString(v45[1]);
    if ( v45[0] )
      WindowsDeleteString(v45[0]);
    goto LABEL_54;
  }
  v14 = (void *)*((_QWORD *)v34 + 8);
  GrantedAccess = 0;
  AccessStatus = 0;
  memset(v40, 0, 20);
  PrivilegeSetLength[0] = 20;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    v15 = 0;
  }
  else
  {
    v25 = CoImpersonateClient();
    v16 = v25;
    if ( v25 < 0 )
    {
      v32 = v25;
      goto LABEL_76;
    }
    v15 = 1;
  }
  if ( AccessCheck(
         v14,
         (HANDLE)0xFFFFFFFFFFFFFFFALL,
         1u,
         &gWAMStoreGenericMapping,
         (PPRIVILEGE_SET)v40,
         PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    v16 = -2147024891;
    if ( AccessStatus )
      v16 = 0;
    if ( !v15 )
      goto LABEL_16;
LABEL_71:
    CoRevertToSelf();
    goto LABEL_16;
  }
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
  if ( v15 )
    goto LABEL_71;
LABEL_16:
  v32 = v16;
  if ( v16 >= 0 )
  {
    v33 = 0;
    v34 = 0;
    _InterlockedCompareExchange64((volatile signed __int64 *)v13 + 9, GetTickCount64(), *((_QWORD *)v13 + 9));
    if ( WindowsCreateStringReference(
           L"Windows.Storage.Streams.DataWriter",
           0x22u,
           (HSTRING_HEADER *)&v40[8],
           (HSTRING *)v40) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v33 = 0;
    *(_QWORD *)PrivilegeSetLength = 0;
    v16 = RoActivateInstance(*(_QWORD *)v40, PrivilegeSetLength);
    if ( v16 >= 0 )
    {
      v17 = memcmp_0(&GUID_64b89265_d341_4922_b38a_dd4af8808c4e, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
      v18 = *(_QWORD *)PrivilegeSetLength;
      if ( !v17 )
      {
        v33 = *(_QWORD *)PrivilegeSetLength;
        v32 = v16;
LABEL_24:
        v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 96LL))(
                v18,
                *((unsigned int *)v13 + 14),
                *((_QWORD *)v13 + 6));
        v20 = v19;
        v32 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x310,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
            (const char *)(unsigned int)v19,
            PrivilegeSet);
          v28 = v34;
          if ( v34 )
          {
            v34 = 0;
            (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v28 + 16LL))(v28);
          }
          v29 = v33;
          if ( v33 )
          {
            v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
        }
        else
        {
          v21 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v33 + 248LL))(
                  v33,
                  &v34);
          v20 = v21;
          v32 = v21;
          if ( v21 >= 0 )
          {
            v22 = v34;
            if ( v34 )
            {
              (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v34 + 8LL))(v34);
              v22 = v34;
            }
            *a4 = v22;
            v32 = 0;
            if ( v22 )
            {
              v34 = 0;
              (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v22 + 16LL))(v22);
            }
            v23 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            goto LABEL_34;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
            (const char *)(unsigned int)v21,
            PrivilegeSet);
          v26 = v34;
          if ( v34 )
          {
            v34 = 0;
            (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v26 + 16LL))(v26);
          }
          v27 = v33;
          if ( v33 )
          {
            v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
        }
        ReleaseSRWLockShared(SRWLock);
        Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v41);
LABEL_54:
        wil::details::ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___::_ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___(v38);
        return v20;
      }
      v16 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))PrivilegeSetLength)(
              *(_QWORD *)PrivilegeSetLength,
              &GUID_64b89265_d341_4922_b38a_dd4af8808c4e,
              &v33);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)PrivilegeSetLength + 16LL))(*(_QWORD *)PrivilegeSetLength);
    }
    v32 = v16;
    if ( v16 >= 0 )
    {
      v18 = v33;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
      (const char *)(unsigned int)v16,
      PrivilegeSet);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    goto LABEL_77;
  }
LABEL_76:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x304,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamobjectstore.cpp",
    (const char *)(unsigned int)v16,
    PrivilegeSet);
LABEL_77:
  ReleaseSRWLockShared(SRWLock);
  Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext((Windows::Internal::Security::Authentication::Web::CallerContext *)&v41);
  wil::details::ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___::_ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___(v38);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180009f40  mov     [rsp-8+arg_10], rbx
0x180009f45  push    rbp
0x180009f46  push    rsi
0x180009f47  push    rdi
0x180009f48  push    r12
0x180009f4a  push    r13
0x180009f4c  push    r14
0x180009f4e  push    r15
0x180009f50  lea     rbp, [rsp-0F0h]
0x180009f58  sub     rsp, 1F0h
0x180009f5f  mov     rax, cs:__security_cookie
0x180009f66  xor     rax, rsp
0x180009f69  mov     [rbp+120h+var_40], rax
0x180009f70  mov     r12, r9
0x180009f73  mov     rbx, r8
0x180009f76  mov     rdi, rdx
0x180009f79  mov     rsi, rcx
0x180009f7c  xor     r13d, r13d
0x180009f7f  mov     [rsp+220h+var_1E0], r13d
0x180009f84  lea     rdx, [rsp+220h+var_1E0]; int *
0x180009f89  lea     rcx, [rsp+220h+var_1D0]; this
0x180009f8e  call    ??0_lambda_570d6c12d7f446ca7443779868589c96_@@QEAA@AEAJ@Z; _lambda_570d6c12d7f446ca7443779868589c96_::_lambda_570d6c12d7f446ca7443779868589c96_(long &)
0x180009f93  mov     rdx, rax
0x180009f96  lea     rcx, [rsp+220h+var_1B8]
0x180009f9b  call    ??$ScopeExit@V_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@details@0@$$QEAV_lambda_3876c2633569fbadd92ad93bfc26ac25_@@@Z; wil::ScopeExit<_lambda_3876c2633569fbadd92ad93bfc26ac25_>(_lambda_3876c2633569fbadd92ad93bfc26ac25_ &&)
0x180009fa0  nop
0x180009fa1  test    rdi, rdi
0x180009fa4  jz      loc_18000A4C5
0x180009faa  mov     rcx, rbx; string
0x180009fad  call    cs:__imp_WindowsIsStringEmpty
0x180009fb3  test    eax, eax
0x180009fb5  jnz     loc_18000A4C5
0x180009fbb  test    r12, r12
0x180009fbe  jz      loc_18000A4C5
0x180009fc4  mov     [rbp+120h+var_180], ax
0x180009fc8  mov     [rbp+120h+var_178], r13
0x180009fcc  mov     [rbp+120h+var_170], r13
0x180009fd0  mov     [rbp+120h+var_168], r13d
0x180009fd4  xorps   xmm0, xmm0
0x180009fd7  movdqa  xmmword ptr [rbp+120h+var_160], xmm0
0x180009fdc  xorps   xmm1, xmm1
0x180009fdf  movdqa  xmmword ptr [rbp+120h+var_150], xmm1
0x180009fe4  movdqa  xmmword ptr [rbp+120h+string], xmm0
0x180009fe9  movdqa  xmmword ptr [rbp+120h+var_60], xmm1
0x180009ff1  movdqa  xmmword ptr [rbp+120h+hObject], xmm0
0x180009ff9  xor     r9d, r9d; bool
0x180009ffc  xor     r8d, r8d; unsigned __int64
0x180009fff  mov     rdx, rdi; struct IUnknown *
0x18000a002  lea     rcx, [rbp+120h+var_180]; this
0x18000a006  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18000a00b  mov     edi, eax
0x18000a00d  mov     [rsp+220h+var_1E0], eax
0x18000a011  test    eax, eax
0x18000a013  js      loc_18000A4F4
0x18000a019  mov     rcx, rsi; SRWLock
0x18000a01c  call    cs:__imp_AcquireSRWLockShared
0x18000a022  mov     [rsp+220h+var_1A8], rsi
0x18000a027  xor     edx, edx; length
0x18000a029  mov     rcx, rbx; string
0x18000a02c  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a032  xorps   xmm0, xmm0
0x18000a035  movups  xmmword ptr [rbp+120h+var_1A0], xmm0
0x18000a039  xorps   xmm1, xmm1
0x18000a03c  movdqu  xmmword ptr [rbp+120h+var_1A0+10h], xmm1
0x18000a041  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000a048  nop     dword ptr [rax+rax+00000000h]
0x18000a050  inc     r8
0x18000a053  cmp     word ptr [rax+r8*2], 0
0x18000a059  jnz     short loc_18000A050
0x18000a05b  mov     rdx, rax
0x18000a05e  lea     rcx, [rbp+120h+var_1A0]
0x18000a062  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a067  lea     rcx, [rsi+8]
0x18000a06b  lea     r8, [rbp+120h+var_1A0]
0x18000a06f  lea     rdx, [rsp+220h+var_1D0]
0x18000a074  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectEntry@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWamObjectEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,WamObjectEntry,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,WamObjectEntry>>,0>>::find(std::wstring const &)
0x18000a079  mov     rdx, qword ptr [rbp+120h+var_1A0+18h]
0x18000a07d  cmp     rdx, 7
0x18000a081  ja      loc_18000A39E
0x18000a087  mov     rbx, [rsp+220h+var_1D0]
0x18000a08c  cmp     rbx, [rsi+10h]
0x18000a090  jz      loc_18000A29D
0x18000a096  mov     r15, [rbx+40h]
0x18000a09a  mov     [rsp+220h+var_1BC], r13d
0x18000a09f  mov     [rsp+220h+var_1C0], r13d
0x18000a0a4  xorps   xmm0, xmm0
0x18000a0a7  xor     eax, eax
0x18000a0a9  movups  xmmword ptr [rbp+120h+var_1A0], xmm0
0x18000a0ad  mov     dword ptr [rbp+120h+var_1A0+10h], eax
0x18000a0b0  mov     [rsp+220h+var_1C8], 14h
0x18000a0b8  mov     eax, gs:179Ch
0x18000a0c0  test    eax, eax
0x18000a0c2  jz      loc_18000A3B4
0x18000a0c8  xor     r14b, r14b
0x18000a0cb  lea     rax, [rsp+220h+var_1C0]
0x18000a0d0  mov     [rsp+220h+AccessStatus], rax; AccessStatus
0x18000a0d5  lea     rax, [rsp+220h+var_1BC]
0x18000a0da  mov     [rsp+220h+GrantedAccess], rax; GrantedAccess
0x18000a0df  lea     rax, [rsp+220h+var_1C8]
0x18000a0e4  mov     [rsp+220h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000a0e9  lea     rax, [rbp+120h+var_1A0]
0x18000a0ed  mov     [rsp+220h+PrivilegeSet], rax; int
0x18000a0f2  lea     r9, ?gWAMStoreGenericMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000a0f9  mov     rdx, 0FFFFFFFFFFFFFFFAh; ClientToken
0x18000a100  mov     r8d, 1; DesiredAccess
0x18000a106  mov     rcx, r15; pSecurityDescriptor
0x18000a109  call    cs:__imp_AccessCheck
0x18000a10f  test    eax, eax
0x18000a111  jz      loc_18000A49C
0x18000a117  mov     edi, 80070005h
0x18000a11c  cmp     [rsp+220h+var_1C0], 0
0x18000a121  cmovnz  edi, r13d
0x18000a125  test    r14b, r14b
0x18000a128  jnz     loc_18000A4BA
0x18000a12e  mov     [rsp+220h+var_1E0], edi
0x18000a132  test    edi, edi
0x18000a134  js      loc_18000A562
0x18000a13a  mov     [rsp+220h+var_1D8], r13
0x18000a13f  mov     [rsp+220h+var_1D0], r13
0x18000a144  mov     rdi, [rbx+48h]
0x18000a148  call    cs:__imp_GetTickCount64
0x18000a14e  mov     rcx, rax
0x18000a151  mov     rax, rdi
0x18000a154  lock cmpxchg [rbx+48h], rcx
0x18000a15a  lea     r9, [rbp+120h+var_1A0]; string
0x18000a15e  lea     r8, [rbp+120h+var_1A0+8]; hstringHeader
0x18000a162  mov     edx, 22h ; '"'; length
0x18000a167  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x18000a16e  call    cs:__imp_WindowsCreateStringReference
0x18000a174  test    eax, eax
0x18000a176  js      loc_18000A4D9
0x18000a17c  mov     [rsp+220h+var_1D8], r13
0x18000a181  mov     qword ptr [rsp+220h+var_1C8], r13
0x18000a186  lea     rdx, [rsp+220h+var_1C8]
0x18000a18b  mov     rcx, qword ptr [rbp+120h+var_1A0]
0x18000a18f  call    cs:__imp_RoActivateInstance
0x18000a195  mov     edi, eax
0x18000a197  test    eax, eax
0x18000a199  js      short loc_18000A1EB
0x18000a19b  mov     r8d, 10h; Size
0x18000a1a1  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000a1a8  lea     rcx, _GUID_64b89265_d341_4922_b38a_dd4af8808c4e; Buf1
0x18000a1af  call    memcmp_0
0x18000a1b4  mov     rcx, qword ptr [rsp+220h+var_1C8]
0x18000a1b9  test    eax, eax
0x18000a1bb  jz      loc_18000A3CC
0x18000a1c1  mov     rax, [rcx]
0x18000a1c4  lea     r8, [rsp+220h+var_1D8]
0x18000a1c9  lea     rdx, _GUID_64b89265_d341_4922_b38a_dd4af8808c4e
0x18000a1d0  mov     rax, [rax]
0x18000a1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d8  mov     edi, eax
0x18000a1da  mov     rcx, qword ptr [rsp+220h+var_1C8]
0x18000a1df  mov     rax, [rcx]
0x18000a1e2  mov     rax, [rax+10h]
0x18000a1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1eb  mov     [rsp+220h+var_1E0], edi
0x18000a1ef  test    edi, edi
0x18000a1f1  js      loc_18000A52B
0x18000a1f7  mov     rcx, [rsp+220h+var_1D8]
0x18000a1fc  mov     rax, [rcx]
0x18000a1ff  mov     r8, [rbx+30h]
0x18000a203  mov     edx, [rbx+38h]
0x18000a206  mov     rax, [rax+60h]
0x18000a20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20f  mov     ebx, eax
0x18000a211  mov     [rsp+220h+var_1E0], eax
0x18000a215  test    eax, eax
0x18000a217  js      loc_18000A446
0x18000a21d  mov     rcx, [rsp+220h+var_1D8]
0x18000a222  mov     rax, [rcx]
0x18000a225  lea     rdx, [rsp+220h+var_1D0]
0x18000a22a  mov     rax, [rax+0F8h]
0x18000a231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a236  mov     ebx, eax
0x18000a238  mov     [rsp+220h+var_1E0], eax
0x18000a23c  test    eax, eax
0x18000a23e  js      loc_18000A3DA
0x18000a244  mov     rcx, [rsp+220h+var_1D0]
0x18000a249  test    rcx, rcx
0x18000a24c  jz      short loc_18000A25F
0x18000a24e  mov     rax, [rcx]
0x18000a251  mov     rax, [rax+8]
0x18000a255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25a  mov     rcx, [rsp+220h+var_1D0]
0x18000a25f  mov     [r12], rcx
0x18000a263  mov     [rsp+220h+var_1E0], r13d
0x18000a268  test    rcx, rcx
0x18000a26b  jz      short loc_18000A27F
0x18000a26d  mov     [rsp+220h+var_1D0], r13
0x18000a272  mov     rax, [rcx]
0x18000a275  mov     rax, [rax+10h]
0x18000a279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a27e  nop
0x18000a27f  mov     rcx, [rsp+220h+var_1D8]
0x18000a284  test    rcx, rcx
0x18000a287  jz      short loc_18000A29B
0x18000a289  mov     [rsp+220h+var_1D8], r13
0x18000a28e  mov     rax, [rcx]
0x18000a291  mov     rax, [rax+10h]
0x18000a295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29a  nop
0x18000a29b  jmp     short loc_18000A2A5
0x18000a29d  mov     [rsp+220h+var_1E0], 80070490h
0x18000a2a5  mov     rcx, rsi; SRWLock
0x18000a2a8  call    cs:__imp_ReleaseSRWLockShared
0x18000a2ae  mov     ebx, [rsp+220h+var_1E0]
0x18000a2b2  mov     rcx, [rbp+120h+hObject+8]; hObject
0x18000a2b9  lea     rax, [rcx-1]
0x18000a2bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a2c1  jbe     loc_18000A5A3
0x18000a2c7  mov     rcx, [rbp+120h+hObject]; hObject
0x18000a2ce  test    rcx, rcx
0x18000a2d1  jnz     loc_18000A392
0x18000a2d7  mov     rcx, [rbp+120h+var_60+8]; hObject
0x18000a2de  lea     rax, [rcx-1]
0x18000a2e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a2e6  jbe     loc_18000A5AE
0x18000a2ec  mov     rcx, [rbp+120h+var_60]; hObject
0x18000a2f3  lea     rax, [rcx-1]
0x18000a2f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a2fb  jbe     loc_18000A5B9
0x18000a301  mov     rcx, [rbp+120h+string+8]; string
0x18000a305  test    rcx, rcx
0x18000a308  jz      short loc_18000A310
0x18000a30a  call    cs:__imp_WindowsDeleteString
0x18000a310  mov     rcx, [rbp+120h+string]; string
0x18000a314  test    rcx, rcx
0x18000a317  jz      short loc_18000A31F
0x18000a319  call    cs:__imp_WindowsDeleteString
0x18000a31f  mov     rcx, [rbp+120h+var_150+8]; string
0x18000a323  test    rcx, rcx
0x18000a326  jz      short loc_18000A32E
0x18000a328  call    cs:__imp_WindowsDeleteString
0x18000a32e  mov     rcx, [rbp+120h+var_150]; string
0x18000a332  test    rcx, rcx
0x18000a335  jz      short loc_18000A33D
0x18000a337  call    cs:__imp_WindowsDeleteString
0x18000a33d  mov     rcx, [rbp+120h+var_160+8]; string
0x18000a341  test    rcx, rcx
0x18000a344  jz      short loc_18000A34C
0x18000a346  call    cs:__imp_WindowsDeleteString
0x18000a34c  mov     rcx, [rbp+120h+var_160]; string
0x18000a350  test    rcx, rcx
0x18000a353  jz      short loc_18000A35C
0x18000a355  call    cs:__imp_WindowsDeleteString
0x18000a35b  nop
0x18000a35c  lea     rcx, [rsp+220h+var_1B8]
0x18000a361  call    wil__details__ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f______ScopeExitFn__lambda_6d2f907367a244b21804e887d940ba7f___
0x18000a366  mov     eax, ebx
0x18000a368  mov     rcx, [rbp+120h+var_40]
0x18000a36f  xor     rcx, rsp; StackCookie
0x18000a372  call    __security_check_cookie
0x18000a377  mov     rbx, [rsp+220h+arg_10]
0x18000a37f  add     rsp, 1F0h
0x18000a386  pop     r15
0x18000a388  pop     r14
0x18000a38a  pop     r13
0x18000a38c  pop     r12
0x18000a38e  pop     rdi
0x18000a38f  pop     rsi
0x18000a390  pop     rbp
0x18000a391  retn
0x18000a392  call    cs:__imp_CloseHandle
0x18000a398  nop
0x18000a399  jmp     loc_18000A2D7
0x18000a39e  lea     rdx, ds:2[rdx*2]
0x18000a3a6  mov     rcx, qword ptr [rbp+120h+var_1A0]
0x18000a3aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a3af  jmp     loc_18000A087
0x18000a3b4  call    cs:__imp_CoImpersonateClient
0x18000a3ba  mov     edi, eax
0x18000a3bc  test    eax, eax
0x18000a3be  js      loc_18000A55E
0x18000a3c4  mov     r14b, 1
0x18000a3c7  jmp     loc_18000A0CB
0x18000a3cc  mov     [rsp+220h+var_1D8], rcx
0x18000a3d1  mov     [rsp+220h+var_1E0], edi
0x18000a3d5  jmp     loc_18000A1FC
0x18000a3da  mov     rcx, [rbp+128h]; this
0x18000a3e1  mov     r9d, ebx; char *
0x18000a3e4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18000a3eb  mov     edx, 311h; void *
0x18000a3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3f5  nop
0x18000a3f6  mov     rcx, [rsp+220h+var_1D0]
0x18000a3fb  test    rcx, rcx
0x18000a3fe  jz      short loc_18000A412
0x18000a400  mov     [rsp+220h+var_1D0], r13
0x18000a405  mov     rax, [rcx]
0x18000a408  mov     rax, [rax+10h]
0x18000a40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a411  nop
0x18000a412  mov     rcx, [rsp+220h+var_1D8]
0x18000a417  test    rcx, rcx
0x18000a41a  jz      short loc_18000A42E
0x18000a41c  mov     [rsp+220h+var_1D8], r13
0x18000a421  mov     rax, [rcx]
0x18000a424  mov     rax, [rax+10h]
0x18000a428  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
