# CSharingSourceProxy::Initialize(HWND__ *,ISharePlatformHost *)

- ea: `0x18006fbbc`
- end: `0x18006fd62`
- name: `?Initialize@CSharingSourceProxy@@QEAAJPEAUHWND__@@PEAUISharePlatformHost@@@Z`
- size: `422`
- prototype: `int(CSharingSourceProxy *__hidden this, HWND, struct ISharePlatformHost *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006d208`

## callees

- `0x180003d24`
- `0x1800177a4`
- `0x180019534`
- `0x180019b14`
- `0x180024a00`
- `0x1800299c8`
- `0x18002d43c`
- `0x180062420`
- `0x180062c48`
- `0x18006b3dc`
- `0x18006f9a4`
- `0x18006fbbc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006fc5c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006fc5c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fc84`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fc84`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006fcf9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006fcf9`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18006fccb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18006fccb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006fce1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006fce1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18006fd28`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18006fd28`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18006fc24`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18006fc7c`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18006fc24`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18006fc7c`

## pseudocode

```c
__int64 __fastcall CSharingSourceProxy::Initialize(CSharingSourceProxy *this, HWND a2, struct ISharePlatformHost *a3)
{
  int ConstrainedImpersonationTokenForHwnd; // ebx
  void **v7; // r8
  int AgileReference; // ebx
  DWORD *v9; // rdi
  HANDLE v10; // rax
  _BYTE v12[32]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp+28h] BYREF

  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v12, 0x157Cu);
  v13 = 0;
  *(_QWORD *)this = a2;
  Microsoft::WRL::ComPtr<ISharePlatformHost>::operator=((char *)this + 24, a3);
  *((_BYTE *)this + 56) = IsCurrentThreadSTA();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  ConstrainedImpersonationTokenForHwnd = CoreQueryWindowService(
                                           a2,
                                           &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60,
                                           &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60,
                                           &v13);
  if ( ConstrainedImpersonationTokenForHwnd == -2147024891 )
  {
    hToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    ConstrainedImpersonationTokenForHwnd = UserAwareWindowIdentity::GetConstrainedImpersonationTokenForHwnd(
                                             a2,
                                             (HWND)&hToken,
                                             v7);
    if ( ConstrainedImpersonationTokenForHwnd >= 0 )
    {
      if ( ImpersonateLoggedOnUser(hToken) )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
        ConstrainedImpersonationTokenForHwnd = CoreQueryWindowService(
                                                 a2,
                                                 &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60,
                                                 &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60,
                                                 &v13);
        RevertToSelf();
      }
      else
      {
        ConstrainedImpersonationTokenForHwnd = ResultFromKnownLastError();
      }
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  }
  if ( !v13 )
    goto LABEL_8;
  if ( ConstrainedImpersonationTokenForHwnd < 0 )
  {
    AgileReference = -2144927163;
    goto LABEL_18;
  }
  wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset((char *)this + 32);
  AgileReference = RoGetAgileReference(0, &GUID_252e6571_8157_4809_8e2a_94aaa9e5de60, v13, (char *)this + 32);
  if ( AgileReference >= 0 )
  {
    v9 = (DWORD *)((char *)this + 12);
    if ( !GetWindowThreadProcessId(a2, (LPDWORD)this + 3) )
    {
LABEL_8:
      AgileReference = -2147024809;
      goto LABEL_18;
    }
    v10 = OpenProcess(0x100000u, 0, *v9);
    *((_QWORD *)this + 6) = v10;
    if ( v10 )
    {
      AgileReference = 0;
    }
    else
    {
      AgileReference = ResultFromKnownLastError();
      if ( AgileReference == -2147024891 && (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
        AgileReference = UMgrOpenProcessHandleForAccess(0x100000, *v9, (char *)this + 48);
    }
  }
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v12);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x18006fbbc  mov     [rsp-18h+arg_10], rbx
0x18006fbc1  mov     [rsp-18h+arg_18], rsi
0x18006fbc6  push    rbp
0x18006fbc7  push    rdi
0x18006fbc8  push    r14
0x18006fbca  mov     rbp, rsp
0x18006fbcd  sub     rsp, 40h
0x18006fbd1  mov     r14, rdx
0x18006fbd4  mov     rsi, rcx
0x18006fbd7  mov     edx, 157Ch; DueTime
0x18006fbdc  lea     rcx, [rbp+var_20]; this
0x18006fbe0  mov     rbx, r8
0x18006fbe3  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18006fbe8  lea     rcx, [rsi+18h]
0x18006fbec  mov     [rbp+arg_0], 0
0x18006fbf4  mov     rdx, rbx
0x18006fbf7  mov     [rsi], r14
0x18006fbfa  call    ??4?$ComPtr@UISharePlatformHost@@@WRL@Microsoft@@QEAAAEAV012@PEAUISharePlatformHost@@@Z; Microsoft::WRL::ComPtr<ISharePlatformHost>::operator=(ISharePlatformHost *)
0x18006fbff  call    ?IsCurrentThreadSTA@@YA_NXZ; IsCurrentThreadSTA(void)
0x18006fc04  lea     rcx, [rbp+arg_0]
0x18006fc08  mov     [rsi+38h], al
0x18006fc0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fc10  lea     rdi, _GUID_252e6571_8157_4809_8e2a_94aaa9e5de60
0x18006fc17  mov     rcx, r14
0x18006fc1a  mov     r8, rdi
0x18006fc1d  lea     r9, [rbp+arg_0]
0x18006fc21  mov     rdx, rdi
0x18006fc24  call    cs:__imp_CoreQueryWindowService
0x18006fc2a  mov     ebx, eax
0x18006fc2c  cmp     eax, 80070005h
0x18006fc31  jnz     short loc_18006FC9C
0x18006fc33  xor     edx, edx
0x18006fc35  mov     [rbp+hToken], 0
0x18006fc3d  lea     rcx, [rbp+hToken]
0x18006fc41  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006fc46  lea     rdx, [rbp+hToken]; HWND
0x18006fc4a  mov     rcx, r14; hWnd
0x18006fc4d  call    ?GetConstrainedImpersonationTokenForHwnd@UserAwareWindowIdentity@@YAJPEAUHWND__@@PEAPEAX@Z; UserAwareWindowIdentity::GetConstrainedImpersonationTokenForHwnd(HWND__ *,void * *)
0x18006fc52  mov     ebx, eax
0x18006fc54  test    eax, eax
0x18006fc56  js      short loc_18006FC93
0x18006fc58  mov     rcx, [rbp+hToken]; hToken
0x18006fc5c  call    cs:__imp_ImpersonateLoggedOnUser
0x18006fc62  test    eax, eax
0x18006fc64  jz      short loc_18006FC8C
0x18006fc66  lea     rcx, [rbp+arg_0]
0x18006fc6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fc6f  lea     r9, [rbp+arg_0]
0x18006fc73  mov     r8, rdi
0x18006fc76  mov     rdx, rdi
0x18006fc79  mov     rcx, r14
0x18006fc7c  call    cs:__imp_CoreQueryWindowService
0x18006fc82  mov     ebx, eax
0x18006fc84  call    cs:__imp_RevertToSelf
0x18006fc8a  jmp     short loc_18006FC93
0x18006fc8c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006fc91  mov     ebx, eax
0x18006fc93  lea     rcx, [rbp+hToken]
0x18006fc97  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006fc9c  cmp     [rbp+arg_0], 0
0x18006fca1  jnz     short loc_18006FCAD
0x18006fca3  mov     ebx, 80070057h
0x18006fca8  jmp     loc_18006FD3B
0x18006fcad  test    ebx, ebx
0x18006fcaf  js      loc_18006FD36
0x18006fcb5  lea     rcx, [rsi+20h]
0x18006fcb9  call    ?reset@?$com_ptr_t@UIAgileReference@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAgileReference,wil::err_returncode_policy>::reset(void)
0x18006fcbe  mov     r8, [rbp+arg_0]
0x18006fcc2  lea     r9, [rsi+20h]
0x18006fcc6  mov     rdx, rdi
0x18006fcc9  xor     ecx, ecx
0x18006fccb  call    cs:__imp_RoGetAgileReference
0x18006fcd1  mov     ebx, eax
0x18006fcd3  test    eax, eax
0x18006fcd5  js      short loc_18006FD3B
0x18006fcd7  lea     rdi, [rsi+0Ch]
0x18006fcdb  mov     rcx, r14; hWnd
0x18006fcde  mov     rdx, rdi; lpdwProcessId
0x18006fce1  call    cs:__imp_GetWindowThreadProcessId
0x18006fce7  test    eax, eax
0x18006fce9  jz      short loc_18006FCA3
0x18006fceb  mov     r8d, [rdi]; dwProcessId
0x18006fcee  mov     r14d, 100000h
0x18006fcf4  mov     ecx, r14d; dwDesiredAccess
0x18006fcf7  xor     edx, edx; bInheritHandle
0x18006fcf9  call    cs:__imp_OpenProcess
0x18006fcff  mov     [rsi+30h], rax
0x18006fd03  test    rax, rax
0x18006fd06  jnz     short loc_18006FD32
0x18006fd08  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006fd0d  mov     ebx, eax
0x18006fd0f  cmp     eax, 80070005h
0x18006fd14  jnz     short loc_18006FD3B
0x18006fd16  call    IsUMgrOpenProcessHandleForAccessPresent
0x18006fd1b  test    al, al
0x18006fd1d  jz      short loc_18006FD3B
0x18006fd1f  mov     edx, [rdi]
0x18006fd21  lea     r8, [rsi+30h]
0x18006fd25  mov     ecx, r14d
0x18006fd28  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x18006fd2e  mov     ebx, eax
0x18006fd30  jmp     short loc_18006FD3B
0x18006fd32  xor     ebx, ebx
0x18006fd34  jmp     short loc_18006FD3B
0x18006fd36  mov     ebx, 80270245h
0x18006fd3b  lea     rcx, [rbp+arg_0]
0x18006fd3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fd44  lea     rcx, [rbp+var_20]; this
0x18006fd48  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18006fd4d  mov     rsi, [rsp+40h+arg_18]
0x18006fd52  mov     eax, ebx
0x18006fd54  mov     rbx, [rsp+40h+arg_10]
0x18006fd59  add     rsp, 40h
0x18006fd5d  pop     r14
0x18006fd5f  pop     rdi
0x18006fd60  pop     rbp
0x18006fd61  retn
```
