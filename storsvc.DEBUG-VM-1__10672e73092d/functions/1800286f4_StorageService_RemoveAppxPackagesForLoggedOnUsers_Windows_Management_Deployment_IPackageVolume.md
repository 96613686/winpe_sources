# StorageService::RemoveAppxPackagesForLoggedOnUsers(Windows::Management::Deployment::IPackageVolume *)

- ea: `0x1800286f4`
- end: `0x180028a12`
- name: `?RemoveAppxPackagesForLoggedOnUsers@StorageService@@IEAAJPEAUIPackageVolume@Deployment@Management@Windows@@@Z`
- size: `798`
- prototype: `int(StorageService *__hidden this, struct Windows::Management::Deployment::IPackageVolume *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800282b8`

## callees

- `0x180001cf0`
- `0x18000d030`
- `0x180012734`
- `0x180014a00`
- `0x18001c4d0`
- `0x18001c5ec`
- `0x18001c62c`
- `0x18002839c`
- `0x1800286f4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002876a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002884a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002876a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002884a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002894f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002894f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028947`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028947`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002892e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002892e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028834`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002891e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002891e`

## string_xrefs

- `0x1800287bf`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x18002886a`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StorageService::RemoveAppxPackagesForLoggedOnUsers(
        StorageService *this,
        struct Windows::Management::Deployment::IPackageVolume *a2)
{
  int v3; // eax
  signed int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // r9
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  signed int v12; // edi
  int v13; // esi
  unsigned int i; // r14d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  StorageService *v17; // rcx
  signed int v18; // eax
  signed int LastError; // eax
  int v21; // [rsp+20h] [rbp-69h]
  unsigned int v22; // [rsp+40h] [rbp-49h] BYREF
  int v23; // [rsp+44h] [rbp-45h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  __int64 v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h] BYREF
  int v27; // [rsp+60h] [rbp-29h] BYREF
  signed int v28; // [rsp+64h] [rbp-25h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-21h] BYREF
  __int64 v30; // [rsp+70h] [rbp-19h] BYREF
  __int64 v31; // [rsp+78h] [rbp-11h] BYREF
  __int64 v32; // [rsp+80h] [rbp-9h] BYREF
  HANDLE hToken; // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+90h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v22 = 0;
  v31 = 0;
  v30 = 0;
  v26 = 0;
  v25 = 0;
  if ( WindowsCreateStringReference(L"Windows.System.User", 0x13u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::IUserStatics>>(string, &v30);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 5152;
LABEL_7:
    v8 = (unsigned int)v3;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)v8,
      v21);
    goto LABEL_35;
  }
  v6 = v30;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  v3 = v7(v6, &v26);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 5154;
    goto LABEL_7;
  }
  v3 = BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Windows::Foundation::Collections::IVectorView<Windows::System::User *>>(
         v26,
         &v25);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 5155;
    goto LABEL_7;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v22);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 5156;
    goto LABEL_7;
  }
  if ( !v22 )
  {
    v4 = -2147023728;
    v8 = 2147943568LL;
    v5 = 5157;
    goto LABEL_8;
  }
  if ( WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
         string,
         &v31);
  v12 = v9;
  if ( v9 >= 0 )
  {
    v13 = -2147467259;
    for ( i = 0; i < v22; ++i )
    {
      v24 = 0;
      v15 = v25;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      v4 = v16(v15, i, &v24);
      if ( v4 >= 0 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 56LL))(v24, &v23);
        if ( v23 )
        {
          v32 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v31 + 136LL))(v31, v24, &v32);
          if ( v4 >= 0 )
          {
            hToken = 0;
            v4 = UMgrQueryUserToken(v32, &hToken);
            if ( v4 >= 0 )
            {
              if ( ImpersonateLoggedOnUser(hToken) )
              {
                v18 = StorageService::RemoveAppxPackagesForCurrentUser(v17, a2);
                v4 = v18;
                if ( v13 < 0 )
                  v13 = v18;
                RevertToSelf();
              }
              else
              {
                LastError = GetLastError();
                v4 = LastError;
                if ( LastError > 0 )
                  v4 = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
        else
        {
          v4 = -2147023652;
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    }
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      v27 = v13;
      v28 = v4;
      v29 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)byte_1800A5DC9,
        v10,
        v11,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
    v4 = v13;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1429,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v9,
      v21);
    v4 = v12;
  }
LABEL_35:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800286f4  mov     [rsp-8+arg_0], rbx
0x1800286f9  mov     [rsp-8+arg_10], rsi
0x1800286fe  push    rbp
0x1800286ff  push    rdi
0x180028700  push    r12
0x180028702  push    r14
0x180028704  push    r15
0x180028706  lea     rbp, [rsp-37h]
0x18002870b  sub     rsp, 0C0h
0x180028712  mov     rax, cs:__security_cookie
0x180028719  xor     rax, rsp
0x18002871c  mov     [rbp+57h+var_30], rax
0x180028720  mov     r15, rdx
0x180028723  xor     r12d, r12d
0x180028726  mov     [rbp+57h+var_A0], r12d
0x18002872a  mov     [rbp+57h+var_68], r12
0x18002872e  mov     [rbp+57h+var_70], r12
0x180028732  mov     [rbp+57h+var_88], r12
0x180028736  mov     [rbp+57h+var_90], r12
0x18002873a  lea     r9, [rbp+57h+string]; string
0x18002873e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180028742  lea     edx, [r12+13h]; length
0x180028747  lea     rcx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18002874e  call    cs:__imp_WindowsCreateStringReference
0x180028754  mov     esi, 0C000000Dh
0x180028759  test    eax, eax
0x18002875b  jns     short loc_180028770
0x18002875d  xor     r9d, r9d; lpArguments
0x180028760  xor     r8d, r8d; nNumberOfArguments
0x180028763  lea     edx, [r12+1]; dwExceptionFlags
0x180028768  mov     ecx, esi; dwExceptionCode
0x18002876a  call    cs:__imp_RaiseException
0x180028770  lea     rdx, [rbp+57h+var_70]
0x180028774  mov     rcx, [rbp+57h+string]
0x180028778  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::IUserStatics>>)
0x18002877d  mov     ebx, eax
0x18002877f  test    eax, eax
0x180028781  jns     short loc_18002878A
0x180028783  mov     edx, 1420h
0x180028788  jmp     short loc_1800287B8
0x18002878a  mov     rdi, [rbp+57h+var_70]
0x18002878e  mov     rax, [rdi]
0x180028791  mov     rbx, [rax+38h]
0x180028795  lea     rcx, [rbp+57h+var_88]
0x180028799  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002879e  lea     rdx, [rbp+57h+var_88]
0x1800287a2  mov     rcx, rdi
0x1800287a5  mov     rax, rbx
0x1800287a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287ad  mov     ebx, eax
0x1800287af  test    eax, eax
0x1800287b1  jns     short loc_1800287D0
0x1800287b3  mov     edx, 1422h; void *
0x1800287b8  mov     r9d, eax; char *
0x1800287bb  mov     rcx, [rbp+5Fh]; this
0x1800287bf  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800287c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800287cb  jmp     loc_1800289C1
0x1800287d0  lea     rdx, [rbp+57h+var_90]
0x1800287d4  mov     rcx, [rbp+57h+var_88]
0x1800287d8  call    ??$BlockOnCompletionAndGetResults@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Windows::Foundation::Collections::IVectorView<Windows::System::User *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>,tagCOWAIT_FLAGS,void *)
0x1800287dd  mov     ebx, eax
0x1800287df  test    eax, eax
0x1800287e1  jns     short loc_1800287EA
0x1800287e3  mov     edx, 1423h
0x1800287e8  jmp     short loc_1800287B8
0x1800287ea  mov     rcx, [rbp+57h+var_90]
0x1800287ee  mov     rax, [rcx]
0x1800287f1  lea     rdx, [rbp+57h+var_A0]
0x1800287f5  mov     rax, [rax+38h]
0x1800287f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287fe  mov     ebx, eax
0x180028800  test    eax, eax
0x180028802  jns     short loc_18002880B
0x180028804  mov     edx, 1424h
0x180028809  jmp     short loc_1800287B8
0x18002880b  cmp     [rbp+57h+var_A0], r12d
0x18002880f  jnz     short loc_180028820
0x180028811  mov     ebx, 80070490h
0x180028816  mov     r9d, ebx
0x180028819  mov     edx, 1425h
0x18002881e  jmp     short loc_1800287BB
0x180028820  lea     r9, [rbp+57h+string]; string
0x180028824  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180028828  mov     edx, 23h ; '#'; length
0x18002882d  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180028834  call    cs:__imp_WindowsCreateStringReference
0x18002883a  test    eax, eax
0x18002883c  jns     short loc_180028850
0x18002883e  xor     r9d, r9d; lpArguments
0x180028841  xor     r8d, r8d; nNumberOfArguments
0x180028844  lea     edx, [r9+1]; dwExceptionFlags
0x180028848  mov     ecx, esi; dwExceptionCode
0x18002884a  call    cs:__imp_RaiseException
0x180028850  lea     rdx, [rbp+57h+var_68]
0x180028854  mov     rcx, [rbp+57h+string]
0x180028858  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18002885d  mov     edi, eax
0x18002885f  test    eax, eax
0x180028861  jns     short loc_180028882
0x180028863  mov     rcx, [rbp+5Fh]; this
0x180028867  mov     r9d, eax; char *
0x18002886a  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180028871  mov     edx, 1429h; void *
0x180028876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002887b  mov     ebx, edi
0x18002887d  jmp     loc_1800289C1
0x180028882  mov     esi, 80004005h
0x180028887  mov     r14d, r12d
0x18002888a  cmp     [rbp+57h+var_A0], r12d
0x18002888e  jbe     loc_18002897A
0x180028894  mov     [rbp+57h+var_98], r12
0x180028898  mov     rdi, [rbp+57h+var_90]
0x18002889c  mov     rax, [rdi]
0x18002889f  mov     rbx, [rax+30h]
0x1800288a3  lea     rcx, [rbp+57h+var_98]
0x1800288a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800288ac  lea     r8, [rbp+57h+var_98]
0x1800288b0  mov     edx, r14d
0x1800288b3  mov     rcx, rdi
0x1800288b6  mov     rax, rbx
0x1800288b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288be  mov     ebx, eax
0x1800288c0  test    eax, eax
0x1800288c2  js      loc_180028964
0x1800288c8  mov     [rbp+57h+var_9C], r12d
0x1800288cc  mov     rcx, [rbp+57h+var_98]
0x1800288d0  mov     rax, [rcx]
0x1800288d3  lea     rdx, [rbp+57h+var_9C]
0x1800288d7  mov     rax, [rax+38h]
0x1800288db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288e0  cmp     [rbp+57h+var_9C], r12d
0x1800288e4  jnz     short loc_1800288ED
0x1800288e6  mov     ebx, 800704DCh
0x1800288eb  jmp     short loc_180028964
0x1800288ed  mov     [rbp+57h+var_60], r12
0x1800288f1  mov     rcx, [rbp+57h+var_68]
0x1800288f5  mov     rax, [rcx]
0x1800288f8  lea     r8, [rbp+57h+var_60]
0x1800288fc  mov     rdx, [rbp+57h+var_98]
0x180028900  mov     rax, [rax+88h]
0x180028907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002890c  mov     ebx, eax
0x18002890e  test    eax, eax
0x180028910  js      short loc_180028964
0x180028912  mov     [rbp+57h+hToken], r12
0x180028916  lea     rdx, [rbp+57h+hToken]
0x18002891a  mov     rcx, [rbp+57h+var_60]
0x18002891e  call    cs:__imp_UMgrQueryUserToken
0x180028924  mov     ebx, eax
0x180028926  test    eax, eax
0x180028928  js      short loc_180028964
0x18002892a  mov     rcx, [rbp+57h+hToken]; hToken
0x18002892e  call    cs:__imp_ImpersonateLoggedOnUser
0x180028934  test    eax, eax
0x180028936  jz      short loc_18002894F
0x180028938  mov     rdx, r15; struct Windows::Management::Deployment::IPackageVolume *
0x18002893b  call    ?RemoveAppxPackagesForCurrentUser@StorageService@@IEAAJPEAUIPackageVolume@Deployment@Management@Windows@@@Z; StorageService::RemoveAppxPackagesForCurrentUser(Windows::Management::Deployment::IPackageVolume *)
0x180028940  mov     ebx, eax
0x180028942  test    esi, esi
0x180028944  cmovs   esi, eax
0x180028947  call    cs:__imp_RevertToSelf
0x18002894d  jmp     short loc_180028964
0x18002894f  call    cs:__imp_GetLastError
0x180028955  mov     ebx, eax
0x180028957  test    eax, eax
0x180028959  jle     short loc_180028964
0x18002895b  movzx   ebx, ax
0x18002895e  or      ebx, 80070000h
0x180028964  lea     rcx, [rbp+57h+var_98]
0x180028968  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002896d  inc     r14d
0x180028970  cmp     r14d, [rbp+57h+var_A0]
0x180028974  jb      loc_180028894
0x18002897a  mov     eax, cs:dword_1800BF000
0x180028980  cmp     eax, 5
0x180028983  jbe     short loc_1800289BF
0x180028985  mov     [rbp+57h+var_80], esi
0x180028988  mov     [rbp+57h+var_7C], ebx
0x18002898b  mov     eax, [rbp+57h+var_A0]
0x18002898e  mov     [rbp+57h+var_78], eax
0x180028991  lea     rax, [rbp+57h+var_80]
0x180028995  mov     [rsp+0E0h+var_B0], rax
0x18002899a  lea     rax, [rbp+57h+var_7C]
0x18002899e  mov     [rsp+0E0h+var_B8], rax
0x1800289a3  lea     rax, [rbp+57h+var_78]
0x1800289a7  mov     [rsp+0E0h+var_C0], rax
0x1800289ac  lea     rdx, byte_1800A5DC9
0x1800289b3  lea     rcx, dword_1800BF000
0x1800289ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800289bf  mov     ebx, esi
0x1800289c1  lea     rcx, [rbp+57h+var_90]
0x1800289c5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800289ca  nop
0x1800289cb  lea     rcx, [rbp+57h+var_88]
0x1800289cf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800289d4  nop
0x1800289d5  lea     rcx, [rbp+57h+var_70]
0x1800289d9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800289de  nop
0x1800289df  lea     rcx, [rbp+57h+var_68]
0x1800289e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800289e8  mov     eax, ebx
0x1800289ea  mov     rcx, [rbp+57h+var_30]
0x1800289ee  xor     rcx, rsp; StackCookie
0x1800289f1  call    __security_check_cookie
0x1800289f6  lea     r11, [rsp+0E0h+var_20]
0x1800289fe  mov     rbx, [r11+30h]
0x180028a02  mov     rsi, [r11+40h]
0x180028a06  mov     rsp, r11
0x180028a09  pop     r15
0x180028a0b  pop     r14
0x180028a0d  pop     r12
0x180028a0f  pop     rdi
0x180028a10  pop     rbp
0x180028a11  retn
```
