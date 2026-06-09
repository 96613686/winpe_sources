# CBrokeredLauncher::CLaunchHelper::_DoLaunchOrFallback(bool,IShellItem *,ushort const *)

- ea: `0x180053f18`
- end: `0x18005444e`
- name: `?_DoLaunchOrFallback@CLaunchHelper@CBrokeredLauncher@@AEAAJ_NPEAUIShellItem@@PEBG@Z`
- size: `1334`
- prototype: `__int64 __fastcall(CBrokeredLauncher::CLaunchHelper *__hidden this, bool, struct IShellItem *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800570b4`
- `0x1800ec29c`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800210f8`
- `0x18003f59c`
- `0x180053884`
- `0x180053f18`
- `0x180054454`
- `0x1800544c8`
- `0x180055194`
- `0x180055298`
- `0x180055490`
- `0x18005552c`
- `0x18005591c`
- `0x180055d2c`
- `0x180055e20`
- `0x180055f1c`
- `0x180055ffc`
- `0x18005609c`
- `0x1800561e0`
- `0x180056f44`
- `0x18005886c`
- `0x180059708`
- `0x18006cbdc`
- `0x18006cdb0`
- `0x1800719a0`
- `0x18008a030`
- `0x1800e1fb8`
- `0x1800e4518`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053fa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18005400e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18005400e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005403a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005428b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005403a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005428b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054264`

## string_xrefs

- `0x180053ffa`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180054118`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180054163`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800541da`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005421e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180054350`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005438d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800543d2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180054407`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x18005443b`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CBrokeredLauncher::CLaunchHelper::_DoLaunchOrFallback(
        CBrokeredLauncher::CLaunchHelper *this,
        bool a2,
        struct IShellItem *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  HSTRING v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  unsigned __int16 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 ProgIdForPackageFamilyName; // rax
  enum IMMERSIVE_OPENWITH_FLAGS *v16; // r8
  unsigned int lpVtbl; // esi
  struct Windows::Foundation::IUriRuntimeClass *v18; // rdx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  PSRWLOCK v23; // rcx
  const char *v24; // r9
  __int64 result; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int Lpcwstr; // eax
  int v30; // eax
  unsigned __int16 *v31; // [rsp+20h] [rbp-208h]
  int v32; // [rsp+20h] [rbp-208h]
  int v33; // [rsp+20h] [rbp-208h]
  int v34; // [rsp+20h] [rbp-208h]
  int v35; // [rsp+20h] [rbp-208h]
  struct IShellItem v36; // [rsp+30h] [rbp-1F8h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-1F0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1E8h] BYREF
  HSTRING v39; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-1D8h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-1D0h] BYREF
  _BYTE v42[32]; // [rsp+70h] [rbp-1B8h] BYREF
  void **v43; // [rsp+90h] [rbp-198h] BYREF
  _BYTE v44[264]; // [rsp+98h] [rbp-190h] BYREF
  __int64 v45; // [rsp+1A0h] [rbp-88h]
  _BYTE v46[8]; // [rsp+1A8h] [rbp-80h] BYREF
  _BYTE v47[48]; // [rsp+1B0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v43);
  v43 = &LauncherDesktopProvider::DoLaunchOrFallback::`vftable';
  wil::ActivityBase<LauncherServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v43,
    &SRWLock);
  v8 = v45;
  *(_OWORD *)(v45 + 24) = *(_OWORD *)((char *)this + 100);
  *(_BYTE *)(v8 + 4) = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  try
  {
    LauncherDesktopProvider::DoLaunchOrFallback::StartActivity(
      (LauncherDesktopProvider::DoLaunchOrFallback *)&v43,
      a2,
      a4);
    v9 = 0;
    v39 = 0;
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v10 + 136LL))(*((_QWORD *)this + 4), &v39);
      v9 = v39;
    }
    else
    {
      v11 = 0;
    }
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xABF,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v11,
        (int)v31);
    if ( !WindowsIsStringEmpty(v9) )
    {
      SRWLock = 0;
      Lpcwstr = Windows::Internal::String::GetLpcwstr(
                  (Windows::Internal::String *)&v39,
                  (const unsigned __int16 **)&SRWLock);
      if ( Lpcwstr < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAFD,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)Lpcwstr,
          (int)v31);
      v30 = CBrokeredLauncher::CLaunchHelper::_DoDirectInvokeLaunch(this, a3, (const unsigned __int16 *)SRWLock);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAFF,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v30,
          (int)v31);
      goto LABEL_32;
    }
    LODWORD(v36.lpVtbl) = 0;
    v12 = 0;
    memset(pv, 0, sizeof(pv));
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    if ( CBrokeredLauncher::CLaunchHelper::_GetTargetPackageFamilyName(this, &string) >= 0 && string )
    {
      v31 = (unsigned __int16 *)&v36;
      ProgIdForPackageFamilyName = CBrokeredLauncher::CLaunchHelper::_FindProgIdForPackageFamilyName(v14, v42, a3);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::operator=(
        pv,
        ProgIdForPackageFamilyName);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v42);
      SRWLock = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
      LauncherDesktopProvider::DoLaunchOrFallback::TargetPackageFamilyNameProvided<unsigned short const *,enum CBrokeredLauncher::CLaunchHelper::AssocStatus &>(
        &v43,
        &SRWLock,
        &v36);
      lpVtbl = (unsigned int)v36.lpVtbl;
      v12 = (unsigned __int16 *)pv[0];
    }
    else
    {
      LOBYTE(v13) = a2;
      lpVtbl = CBrokeredLauncher::CLaunchHelper::_ValidateAndGetAssocStatus(this, v13, a3, a4);
      LODWORD(v36.lpVtbl) = lpVtbl;
      LauncherDesktopProvider::DoLaunchOrFallback::AssocStatus<enum CBrokeredLauncher::CLaunchHelper::AssocStatus &>(
        &v43,
        &v36);
    }
    LODWORD(v36.lpVtbl) = 0;
    v18 = (struct Windows::Foundation::IUriRuntimeClass *)*((_QWORD *)this + 9);
    if ( !v18 || lpVtbl )
    {
      if ( !v12 || !*v12 )
      {
        if ( lpVtbl == 1 )
        {
          if ( EdpHelpers::ShouldUseOpenWithForEdpItem(a3, &v36, v16) )
          {
            SRWLock = 0;
            v40 = *((_QWORD *)this + 4);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
            v21 = Microsoft::WRL::Details::MakeAndInitialize<OpenWithOptionsServiceProvider,IServiceProvider,enum IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions *,unsigned short const * &,unsigned long &>(
                    (unsigned int)&SRWLock,
                    (unsigned int)&v36,
                    (unsigned int)&v40,
                    (int)this + 16,
                    (__int64)this + 8);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xAE5,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)(unsigned int)v21,
                v33);
            v22 = CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(
                    this,
                    a3,
                    (struct IUnknown *)SRWLock,
                    0,
                    L"Unknown",
                    a4);
            if ( v22 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xAEA,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                (const char *)(unsigned int)v22,
                v34);
            v23 = SRWLock;
            if ( SRWLock )
            {
              SRWLock = 0;
              (*((void (__fastcall **)(PSRWLOCK))v23->Ptr + 2))(v23);
            }
            goto LABEL_30;
          }
        }
        else if ( lpVtbl == 2 && CBrokeredLauncher::CLaunchHelper::LimitPickerToCurrentAppAndAppUriHandlers(this) )
        {
          SRWLock = 0;
          v40 = *((_QWORD *)this + 4);
          v26 = Microsoft::WRL::Details::MakeAndInitialize<OpenWithOptionsServiceProvider,IServiceProvider,enum IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions *,unsigned short const * &,unsigned long &>(
                  &SRWLock,
                  &v36,
                  &v40,
                  (char *)this + 16);
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAEF,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
              (const char *)(unsigned int)v26,
              (_DWORD)this + 8);
          v27 = CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(
                  this,
                  a3,
                  (struct IUnknown *)SRWLock,
                  0,
                  0,
                  a4);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAF1,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
              (const char *)(unsigned int)v27,
              v35);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SRWLock);
          goto LABEL_30;
        }
        LOBYTE(v18) = a2;
        v28 = CBrokeredLauncher::CLaunchHelper::_DoLaunch(this, v18, a3, lpVtbl);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAF6,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v28,
            (int)v31);
        goto LABEL_30;
      }
      v20 = CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(
              this,
              a3,
              *((struct IUnknown **)this + 4),
              0,
              v12,
              a4);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xADE,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v20,
          v32);
    }
    else
    {
      v19 = CBrokeredLauncher::CLaunchHelper::_DoFallbackLaunch(this, v18);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAD8,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
          (const char *)(unsigned int)v19,
          (int)v31);
    }
LABEL_30:
    WindowsDeleteString(string);
    string = 0;
    if ( v12 )
      CoTaskMemFree(v12);
LABEL_32:
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v43, 0);
    if ( v39 )
      WindowsDeleteString(v39);
    v43 = &LauncherDesktopProvider::DoLaunchOrFallback::`vftable';
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v43);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v47);
    wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v46);
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB04,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x180053f18  push    rbx
0x180053f1a  push    rsi
0x180053f1b  push    rdi
0x180053f1c  push    r12
0x180053f1e  push    r13
0x180053f20  push    r14
0x180053f22  push    r15
0x180053f24  sub     rsp, 1F0h
0x180053f2b  mov     rax, cs:__security_cookie
0x180053f32  xor     rax, rsp
0x180053f35  mov     [rsp+228h+var_48], rax
0x180053f3d  mov     r15, r9
0x180053f40  mov     r14, r8
0x180053f43  mov     r12b, dl
0x180053f46  mov     rbx, rcx
0x180053f49  lea     rdx, aDolaunchorfall; "DoLaunchOrFallback"
0x180053f50  lea     rcx, [rsp+228h+var_198]; struct wil::details::IFailureCallback *
0x180053f58  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180053f5d  lea     rdi, ??_7DoLaunchOrFallback@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::DoLaunchOrFallback::`vftable'
0x180053f64  mov     [rsp+228h+var_198], rdi
0x180053f6c  lea     rdx, [rsp+228h+SRWLock]
0x180053f71  lea     rcx, [rsp+228h+var_198]
0x180053f79  call    ?LockExclusive@?$ActivityBase@VLauncherServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LauncherServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180053f7e  mov     rax, [rsp+228h+var_88]
0x180053f86  movups  xmm0, xmmword ptr [rbx+64h]
0x180053f8a  movdqu  xmmword ptr [rax+18h], xmm0
0x180053f8f  mov     byte ptr [rax+4], 1
0x180053f93  mov     rcx, [rsp+228h+SRWLock]; SRWLock
0x180053f98  xor     r13d, r13d
0x180053f9b  test    rcx, rcx
0x180053f9e  jz      short loc_180053FA6
0x180053fa0  call    cs:__imp_ReleaseSRWLockExclusive
0x180053fa6  mov     r8, r15; unsigned __int16 *
0x180053fa9  mov     dl, r12b; bool
0x180053fac  lea     rcx, [rsp+228h+var_198]; this
0x180053fb4  call    ?StartActivity@DoLaunchOrFallback@LauncherDesktopProvider@@QEAAX_NPEBG@Z; LauncherDesktopProvider::DoLaunchOrFallback::StartActivity(bool,ushort const *)
0x180053fb9  mov     rcx, r13; string
0x180053fbc  mov     [rsp+228h+var_1E0], rcx
0x180053fc1  mov     r8, [rbx+20h]
0x180053fc5  test    r8, r8
0x180053fc8  jz      short loc_180053FE8
0x180053fca  mov     rax, [r8]
0x180053fcd  lea     rdx, [rsp+228h+var_1E0]
0x180053fd2  mov     rcx, r8
0x180053fd5  mov     rax, [rax+88h]
0x180053fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fe1  mov     rcx, [rsp+228h+var_1E0]
0x180053fe6  jmp     short loc_180053FEB
0x180053fe8  mov     eax, r13d
0x180053feb  mov     r10, [rsp+228h]
0x180053ff3  test    eax, eax
0x180053ff5  jns     short loc_18005400E
0x180053ff7  mov     r9d, eax; char *
0x180053ffa  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180054001  mov     edx, 0ABFh; void *
0x180054006  mov     rcx, r10; this
0x180054009  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005400e  call    cs:__imp_WindowsIsStringEmpty
0x180054014  test    eax, eax
0x180054016  jz      loc_1800543E4
0x18005401c  mov     dword ptr [rsp+228h+var_1F8.lpVtbl], r13d
0x180054021  mov     rdi, r13
0x180054024  mov     [rsp+228h+pv], r13
0x180054029  mov     [rsp+228h+var_1C8], r13
0x18005402e  mov     [rsp+228h+var_1C0], r13
0x180054033  mov     [rsp+228h+string], r13
0x180054038  xor     ecx, ecx; string
0x18005403a  call    cs:__imp_WindowsDeleteString
0x180054040  mov     [rsp+228h+string], r13
0x180054045  lea     rdx, [rsp+228h+string]; HSTRING *
0x18005404a  mov     rcx, rbx; this
0x18005404d  call    ?_GetTargetPackageFamilyName@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAPEAUHSTRING__@@@Z; CBrokeredLauncher::CLaunchHelper::_GetTargetPackageFamilyName(HSTRING__ * *)
0x180054052  test    eax, eax
0x180054054  js      short loc_1800540C2
0x180054056  mov     r9, [rsp+228h+string]
0x18005405b  test    r9, r9
0x18005405e  jz      short loc_1800540C2
0x180054060  lea     rax, [rsp+228h+var_1F8]
0x180054065  mov     [rsp+228h+var_208], rax
0x18005406a  mov     r8, r14
0x18005406d  lea     rdx, [rsp+228h+var_1B8]
0x180054072  call    ?_FindProgIdForPackageFamilyName@CLaunchHelper@CBrokeredLauncher@@AEAA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEAUIShellItem@@PEAUHSTRING__@@PEAW4AssocStatus@12@@Z; CBrokeredLauncher::CLaunchHelper::_FindProgIdForPackageFamilyName(IShellItem *,HSTRING__ *,CBrokeredLauncher::CLaunchHelper::AssocStatus *)
0x180054077  mov     rdx, rax
0x18005407a  lea     rcx, [rsp+228h+pv]
0x18005407f  call    ??4?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAAEAV012@$$QEAV012@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::operator=(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &&)
0x180054084  lea     rcx, [rsp+228h+var_1B8]
0x180054089  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005408e  xor     edx, edx; length
0x180054090  mov     rcx, [rsp+228h+string]; string
0x180054095  call    cs:__imp_WindowsGetStringRawBuffer
0x18005409b  mov     [rsp+228h+SRWLock], rax
0x1800540a0  lea     r8, [rsp+228h+var_1F8]
0x1800540a5  lea     rdx, [rsp+228h+SRWLock]
0x1800540aa  lea     rcx, [rsp+228h+var_198]
0x1800540b2  call    ??$TargetPackageFamilyNameProvided@PEBGAEAW4AssocStatus@CLaunchHelper@CBrokeredLauncher@@@DoLaunchOrFallback@LauncherDesktopProvider@@QEAAX$$QEAPEBGAEAW4AssocStatus@CLaunchHelper@CBrokeredLauncher@@@Z; LauncherDesktopProvider::DoLaunchOrFallback::TargetPackageFamilyNameProvided<ushort const *,CBrokeredLauncher::CLaunchHelper::AssocStatus &>(ushort const * &&,CBrokeredLauncher::CLaunchHelper::AssocStatus &)
0x1800540b7  mov     esi, dword ptr [rsp+228h+var_1F8.lpVtbl]
0x1800540bb  mov     rdi, [rsp+228h+pv]
0x1800540c0  jmp     short loc_1800540EB
0x1800540c2  mov     r9, r15
0x1800540c5  mov     r8, r14
0x1800540c8  mov     dl, r12b
0x1800540cb  mov     rcx, rbx
0x1800540ce  call    ?_ValidateAndGetAssocStatus@CLaunchHelper@CBrokeredLauncher@@AEAA?AW4AssocStatus@12@_NPEAUIShellItem@@PEBG@Z; CBrokeredLauncher::CLaunchHelper::_ValidateAndGetAssocStatus(bool,IShellItem *,ushort const *)
0x1800540d3  mov     esi, eax
0x1800540d5  mov     dword ptr [rsp+228h+var_1F8.lpVtbl], eax
0x1800540d9  lea     rdx, [rsp+228h+var_1F8]
0x1800540de  lea     rcx, [rsp+228h+var_198]
0x1800540e6  call    ??$AssocStatus@AEAW40CLaunchHelper@CBrokeredLauncher@@@DoLaunchOrFallback@LauncherDesktopProvider@@QEAAXAEAW4AssocStatus@CLaunchHelper@CBrokeredLauncher@@@Z; LauncherDesktopProvider::DoLaunchOrFallback::AssocStatus<CBrokeredLauncher::CLaunchHelper::AssocStatus &>(CBrokeredLauncher::CLaunchHelper::AssocStatus &)
0x1800540eb  mov     dword ptr [rsp+228h+var_1F8.lpVtbl], r13d
0x1800540f0  mov     rdx, [rbx+48h]; struct Windows::Foundation::IUriRuntimeClass *
0x1800540f4  test    rdx, rdx
0x1800540f7  jz      short loc_180054129
0x1800540f9  test    esi, esi
0x1800540fb  jnz     short loc_180054129
0x1800540fd  mov     rcx, rbx; this
0x180054100  call    ?_DoFallbackLaunch@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z; CBrokeredLauncher::CLaunchHelper::_DoFallbackLaunch(Windows::Foundation::IUriRuntimeClass *)
0x180054105  mov     rcx, [rsp+228h]; this
0x18005410d  test    eax, eax
0x18005410f  jns     loc_18005424C
0x180054115  mov     r9d, eax; char *
0x180054118  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005411f  mov     edx, 0AD8h; void *
0x180054124  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054129  test    rdi, rdi
0x18005412c  jz      short loc_180054174
0x18005412e  cmp     [rdi], r13w
0x180054132  jz      short loc_180054174
0x180054134  mov     [rsp+228h+var_200], r15; unsigned __int16 *
0x180054139  mov     [rsp+228h+var_208], rdi; int
0x18005413e  xor     r9d, r9d; unsigned __int16 *
0x180054141  mov     r8, [rbx+20h]; struct IUnknown *
0x180054145  mov     rdx, r14; struct IShellItem *
0x180054148  mov     rcx, rbx; this
0x18005414b  call    ?_LaunchShellItemWithOptionsAndVerb@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEAUIUnknown@@PEBG22@Z; CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(IShellItem *,IUnknown *,ushort const *,ushort const *,ushort const *)
0x180054150  mov     rcx, [rsp+228h]; this
0x180054158  test    eax, eax
0x18005415a  jns     loc_18005424C
0x180054160  mov     r9d, eax; char *
0x180054163  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005416a  mov     edx, 0ADEh; void *
0x18005416f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054174  cmp     esi, 1
0x180054177  jnz     loc_1800542F9
0x18005417d  lea     rdx, [rsp+228h+var_1F8]; struct IShellItem *
0x180054182  mov     rcx, r14; this
0x180054185  call    ?ShouldUseOpenWithForEdpItem@EdpHelpers@@YA_NPEAUIShellItem@@PEAW4IMMERSIVE_OPENWITH_FLAGS@@@Z; EdpHelpers::ShouldUseOpenWithForEdpItem(IShellItem *,IMMERSIVE_OPENWITH_FLAGS *)
0x18005418a  test    al, al
0x18005418c  jz      loc_1800543AE
0x180054192  mov     [rsp+228h+SRWLock], r13
0x180054197  mov     rax, [rbx+20h]
0x18005419b  mov     [rsp+228h+var_1D8], rax
0x1800541a0  lea     rcx, [rsp+228h+SRWLock]
0x1800541a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800541aa  lea     rax, [rbx+8]
0x1800541ae  lea     r9, [rbx+10h]
0x1800541b2  mov     [rsp+228h+var_208], rax; int
0x1800541b7  lea     r8, [rsp+228h+var_1D8]
0x1800541bc  lea     rdx, [rsp+228h+var_1F8]
0x1800541c1  lea     rcx, [rsp+228h+SRWLock]
0x1800541c6  call    ??$MakeAndInitialize@VOpenWithOptionsServiceProvider@@UIServiceProvider@@AEAW4IMMERSIVE_OPENWITH_FLAGS@@PEAUILauncherOptions@System@Windows@@AEAPEBGAEAK@Details@WRL@Microsoft@@YAJPEAPEAUIServiceProvider@@AEAW4IMMERSIVE_OPENWITH_FLAGS@@$$QEAPEAUILauncherOptions@System@Windows@@AEAPEBGAEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<OpenWithOptionsServiceProvider,IServiceProvider,IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions *,ushort const * &,ulong &>(IServiceProvider * *,IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions * &&,ushort const * &,ulong &)
0x1800541cb  mov     rcx, [rsp+228h]; this
0x1800541d3  test    eax, eax
0x1800541d5  jns     short loc_1800541EB
0x1800541d7  mov     r9d, eax; char *
0x1800541da  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800541e1  mov     edx, 0AE5h; void *
0x1800541e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800541eb  mov     [rsp+228h+var_200], r15; unsigned __int16 *
0x1800541f0  lea     rax, String1; "Unknown"
0x1800541f7  mov     [rsp+228h+var_208], rax; int
0x1800541fc  xor     r9d, r9d; unsigned __int16 *
0x1800541ff  mov     r8, [rsp+228h+SRWLock]; struct IUnknown *
0x180054204  mov     rdx, r14; struct IShellItem *
0x180054207  mov     rcx, rbx; this
0x18005420a  call    ?_LaunchShellItemWithOptionsAndVerb@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEAUIUnknown@@PEBG22@Z; CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(IShellItem *,IUnknown *,ushort const *,ushort const *,ushort const *)
0x18005420f  mov     rcx, [rsp+228h]; this
0x180054217  test    eax, eax
0x180054219  jns     short loc_180054230
0x18005421b  mov     r9d, eax; char *
0x18005421e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180054225  mov     edx, 0AEAh; void *
0x18005422a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054230  mov     rcx, [rsp+228h+SRWLock]
0x180054235  test    rcx, rcx
0x180054238  jz      short loc_18005424C
0x18005423a  mov     [rsp+228h+SRWLock], r13
0x18005423f  mov     rax, [rcx]
0x180054242  mov     rax, [rax+10h]
0x180054246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005424b  nop
0x18005424c  mov     rcx, [rsp+228h+string]; string
0x180054251  call    cs:__imp_WindowsDeleteString
0x180054257  mov     [rsp+228h+string], r13
0x18005425c  test    rdi, rdi
0x18005425f  jz      short loc_18005426A
0x180054261  mov     rcx, rdi; pv
0x180054264  call    cs:__imp_CoTaskMemFree
0x18005426a  lea     rdi, ??_7DoLaunchOrFallback@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::DoLaunchOrFallback::`vftable'
0x180054271  xor     edx, edx
0x180054273  lea     rcx, [rsp+228h+var_198]
0x18005427b  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180054280  nop
0x180054281  mov     rcx, [rsp+228h+var_1E0]; string
0x180054286  test    rcx, rcx
0x180054289  jz      short loc_180054292
0x18005428b  call    cs:__imp_WindowsDeleteString
0x180054291  nop
0x180054292  mov     [rsp+228h+var_198], rdi
0x18005429a  lea     rcx, [rsp+228h+var_198]
0x1800542a2  call    ?Destroy@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800542a7  lea     rcx, [rsp+228h+var_78]; this
0x1800542af  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800542b4  lea     rcx, [rsp+228h+var_80]
0x1800542bc  call    ?reset@?$shared_object@V?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800542c1  lea     rcx, [rsp+228h+var_190]
0x1800542c9  call    ??1?$ActivityData@VLauncherDesktopProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherDesktopProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800542ce  xor     eax, eax
0x1800542d0  jmp     short loc_1800542D6
0x1800542d2  mov     eax, dword ptr [rsp+228h+var_1F8.lpVtbl]
0x1800542d6  mov     rcx, [rsp+228h+var_48]
0x1800542de  xor     rcx, rsp; StackCookie
0x1800542e1  call    __security_check_cookie
0x1800542e6  add     rsp, 1F0h
0x1800542ed  pop     r15
0x1800542ef  pop     r14
0x1800542f1  pop     r13
0x1800542f3  pop     r12
0x1800542f5  pop     rdi
0x1800542f6  pop     rsi
0x1800542f7  pop     rbx
0x1800542f8  retn
0x1800542f9  cmp     esi, 2
0x1800542fc  jnz     loc_1800543AE
0x180054302  mov     rcx, rbx; this
0x180054305  call    ?LimitPickerToCurrentAppAndAppUriHandlers@CLaunchHelper@CBrokeredLauncher@@AEAA_NXZ; CBrokeredLauncher::CLaunchHelper::LimitPickerToCurrentAppAndAppUriHandlers(void)
0x18005430a  test    al, al
0x18005430c  jz      loc_1800543AE
0x180054312  mov     [rsp+228h+SRWLock], r13
0x180054317  mov     rax, [rbx+20h]
0x18005431b  mov     [rsp+228h+var_1D8], rax
0x180054320  lea     rax, [rbx+8]
0x180054324  lea     r9, [rbx+10h]
0x180054328  mov     [rsp+228h+var_208], rax; int
0x18005432d  lea     r8, [rsp+228h+var_1D8]
0x180054332  lea     rdx, [rsp+228h+var_1F8]
0x180054337  lea     rcx, [rsp+228h+SRWLock]
0x18005433c  call    ??$MakeAndInitialize@VOpenWithOptionsServiceProvider@@UIServiceProvider@@AEAW4IMMERSIVE_OPENWITH_FLAGS@@PEAUILauncherOptions@System@Windows@@AEAPEBGAEAK@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@012@AEAW4IMMERSIVE_OPENWITH_FLAGS@@$$QEAPEAUILauncherOptions@System@Windows@@AEAPEBGAEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<OpenWithOptionsServiceProvider,IServiceProvider,IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions *,ushort const * &,ulong &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>,IMMERSIVE_OPENWITH_FLAGS &,Windows::System::ILauncherOptions * &&,ushort const * &,ulong &)
0x180054341  mov     rcx, [rsp+228h]; this
0x180054349  test    eax, eax
0x18005434b  jns     short loc_180054361
0x18005434d  mov     r9d, eax; char *
0x180054350  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180054357  mov     edx, 0AEFh; void *
0x18005435c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054361  mov     [rsp+228h+var_200], r15; unsigned __int16 *
0x180054366  mov     [rsp+228h+var_208], r13; int
0x18005436b  xor     r9d, r9d; unsigned __int16 *
0x18005436e  mov     r8, [rsp+228h+SRWLock]; struct IUnknown *
0x180054373  mov     rdx, r14; struct IShellItem *
0x180054376  mov     rcx, rbx; this
0x180054379  call    ?_LaunchShellItemWithOptionsAndVerb@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEAUIUnknown@@PEBG22@Z; CBrokeredLauncher::CLaunchHelper::_LaunchShellItemWithOptionsAndVerb(IShellItem *,IUnknown *,ushort const *,ushort const *,ushort const *)
0x18005437e  mov     rcx, [rsp+228h]; this
0x180054386  test    eax, eax
0x180054388  jns     short loc_18005439F
0x18005438a  mov     r9d, eax; char *
0x18005438d  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180054394  mov     edx, 0AF1h; void *
0x180054399  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005439f  lea     rcx, [rsp+228h+SRWLock]
0x1800543a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800543a9  jmp     loc_18005424C
0x1800543ae  mov     r9d, esi
0x1800543b1  mov     r8, r14
0x1800543b4  mov     dl, r12b
0x1800543b7  mov     rcx, rbx
0x1800543ba  call    ?_DoLaunch@CLaunchHelper@CBrokeredLauncher@@AEAAJ_NPEAUIShellItem@@W4AssocStatus@12@@Z; CBrokeredLauncher::CLaunchHelper::_DoLaunch(bool,IShellItem *,CBrokeredLauncher::CLaunchHelper::AssocStatus)
0x1800543bf  mov     rcx, [rsp+228h]; this
0x1800543c7  test    eax, eax
0x1800543c9  jns     loc_18005424C
0x1800543cf  mov     r9d, eax; char *
0x1800543d2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800543d9  mov     edx, 0AF6h; void *
0x1800543de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800543e4  mov     [rsp+228h+SRWLock], r13
0x1800543e9  lea     rdx, [rsp+228h+SRWLock]; unsigned __int16 **
0x1800543ee  lea     rcx, [rsp+228h+var_1E0]; this
0x1800543f3  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x1800543f8  mov     rcx, [rsp+228h]; this
0x180054400  test    eax, eax
0x180054402  jns     short loc_180054418
0x180054404  mov     r9d, eax; char *
0x180054407  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18005440e  mov     edx, 0AFDh; void *
0x180054413  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054418  mov     r8, [rsp+228h+SRWLock]; unsigned __int16 *
0x18005441d  mov     rdx, r14; struct IShellItem *
0x180054420  mov     rcx, rbx; this
0x180054423  call    ?_DoDirectInvokeLaunch@CLaunchHelper@CBrokeredLauncher@@AEAAJPEAUIShellItem@@PEBG@Z; CBrokeredLauncher::CLaunchHelper::_DoDirectInvokeLaunch(IShellItem *,ushort const *)
0x180054428  mov     rcx, [rsp+228h]; this
0x180054430  test    eax, eax
  ... truncated ...
```
