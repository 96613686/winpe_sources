# Windows::UI::Core::CompositionHelper::SetCompositionRoot_Classic_Impl(IDCompositionVisual *,bool)

- ea: `0x180059c90`
- end: `0x18005a0ca`
- name: `?SetCompositionRoot_Classic_Impl@CompositionHelper@Core@UI@Windows@@UEAAJPEAUIDCompositionVisual@@_N@Z`
- size: `1082`
- prototype: `__int64 __fastcall(Windows::UI::Core::CompositionHelper *__hidden this, struct IDCompositionVisual *, bool)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180026820`
- `0x18002b770`
- `0x180051568`
- `0x180051750`
- `0x180059c90`
- `0x18005a0d0`
- `0x18005a11c`
- `0x18006dc64`
- `0x180091978`
- `0x180096cb4`
- `0x180096d54`
- `0x180096de8`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a05b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a09f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a05b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a09f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059ceb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005a078`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180059ceb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18005a078`
- `dcomp!DCompositionCreateDevice` at `0x180059d4e`
- `dcomp!DCompositionCreateDevice` at `0x180059d4e`

## string_xrefs

- `0x180059d63`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`
- `0x180059f3d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`
- `0x18005a087`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CompositionHelper::SetCompositionRoot_Classic_Impl(
        Windows::UI::Core::CompositionHelper *this,
        struct IDCompositionVisual *a2,
        char a3)
{
  const unsigned __int16 *v6; // rdx
  _QWORD *v7; // rax
  int CoreApplicationViewOfCurrentThread; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, struct IDCompositionVisual **); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v15; // rdx
  _QWORD *v17; // rax
  int v18; // [rsp+20h] [rbp-49h]
  struct IDCompositionVisual *v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+38h] [rbp-31h] BYREF
  __int64 v21; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::Foundation::Private::ICompositionVisual *v24; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v25; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string[4]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 104);
  if ( a2 && *((_QWORD *)this + 12) )
  {
    v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[103])v6);
    CoreApplicationViewOfCurrentThread = -2003302400;
    RoOriginateError(2291664896LL, *v7);
    v9 = 245;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
      (const char *)0x88980800LL,
      v18);
    goto LABEL_47;
  }
  if ( *((_QWORD *)this + 6) )
  {
    v17 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[125])v6);
    CoreApplicationViewOfCurrentThread = -2003302400;
    RoOriginateError(2291664896LL, *v17);
    v9 = 247;
    goto LABEL_46;
  }
  v20 = 0;
  v21 = 0;
  v19 = 0;
  v22 = 0;
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
    CoreApplicationViewOfCurrentThread = DCompositionCreateDevice(0, &GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3, &v20);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 262;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
        (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
        v18);
LABEL_10:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
LABEL_47:
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      return (unsigned int)CoreApplicationViewOfCurrentThread;
    }
    v11 = v20;
    v12 = *(__int64 (__fastcall **)(__int64, struct IDCompositionVisual **))(*(_QWORD *)v20 + 56LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
    CoreApplicationViewOfCurrentThread = v12(v11, &v19);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 263;
      goto LABEL_9;
    }
    CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(struct IDCompositionVisual *, struct IDCompositionVisual *, __int64))(*(_QWORD *)v19 + 128LL))(
                                           v19,
                                           a2,
                                           1);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 264;
      goto LABEL_9;
    }
    CoreApplicationViewOfCurrentThread = Microsoft::WRL::ComPtr<IDCompositionVisual>::As<IDCompositionVisualPartner>(
                                           &v19,
                                           &v22);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 267;
      goto LABEL_9;
    }
    CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 320LL))(v22);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 268;
      goto LABEL_9;
    }
    CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 328LL))(v22);
    if ( CoreApplicationViewOfCurrentThread < 0 )
    {
      v10 = 269;
      goto LABEL_9;
    }
    if ( !a3 )
    {
      v13 = v20;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
      CoreApplicationViewOfCurrentThread = v14(v13, *((_QWORD *)this + 14), 0, &v21);
      if ( CoreApplicationViewOfCurrentThread < 0 )
      {
        v10 = 274;
        goto LABEL_9;
      }
      CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64, struct IDCompositionVisual *))(*(_QWORD *)v21 + 24LL))(
                                             v21,
                                             v19);
      if ( CoreApplicationViewOfCurrentThread < 0 )
      {
        v10 = 275;
        goto LABEL_9;
      }
      CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
      if ( CoreApplicationViewOfCurrentThread < 0 )
      {
        v10 = 277;
        goto LABEL_9;
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::operator=((char *)this + 80, &v21);
LABEL_41:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::operator=((char *)this + 72, &v20);
      Microsoft::WRL::ComPtr<IDCompositionVisual>::operator=((char *)this + 88, &v19);
      Microsoft::WRL::ComPtr<IInspectable>::operator=((char *)this + 96, a2);
      goto LABEL_42;
    }
    v25 = 0;
    v26 = 0;
    v24 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    CoreApplicationViewOfCurrentThread = GetCoreApplicationViewOfCurrentThread(&v25);
    if ( CoreApplicationViewOfCurrentThread >= 0 )
    {
      CoreApplicationViewOfCurrentThread = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(
                                             &v25,
                                             &v26);
      if ( CoreApplicationViewOfCurrentThread >= 0 )
      {
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
        CoreApplicationViewOfCurrentThread = CreateAndAttachToCompositionVisualInterop(v19, &v24);
        if ( CoreApplicationViewOfCurrentThread >= 0 )
        {
          CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64, struct Windows::Foundation::Private::ICompositionVisual *))(*(_QWORD *)v26 + 56LL))(
                                                 v26,
                                                 v24);
          if ( CoreApplicationViewOfCurrentThread >= 0 )
          {
            CoreApplicationViewOfCurrentThread = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
            if ( CoreApplicationViewOfCurrentThread >= 0 )
            {
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
              goto LABEL_41;
            }
            v15 = 289;
          }
          else
          {
            v15 = 288;
          }
        }
        else
        {
          v15 = 287;
        }
      }
      else
      {
        v15 = 286;
      }
    }
    else
    {
      v15 = 285;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
      (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
      v18);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    goto LABEL_10;
  }
  Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(this);
LABEL_42:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x180059c90  mov     [rsp-8+arg_10], rbx
0x180059c95  push    rbp
0x180059c96  push    rsi
0x180059c97  push    rdi
0x180059c98  push    r14
0x180059c9a  push    r15
0x180059c9c  lea     rbp, [rsp-37h]
0x180059ca1  sub     rsp, 0A0h
0x180059ca8  mov     rax, cs:__security_cookie
0x180059caf  xor     rax, rsp
0x180059cb2  mov     [rbp+57h+var_30], rax
0x180059cb6  mov     r14, rdx
0x180059cb9  mov     rsi, rcx
0x180059cbc  lea     rdx, [rcx+68h]
0x180059cc0  mov     r15b, r8b
0x180059cc3  lea     rcx, [rbp+57h+SRWLock]
0x180059cc7  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180059ccc  test    r14, r14
0x180059ccf  jz      short loc_180059CFB
0x180059cd1  cmp     qword ptr [rsi+60h], 0
0x180059cd6  jz      short loc_180059CFB
0x180059cd8  lea     rcx, [rbp+57h+string]; string
0x180059cdc  call    ??$?0$0GH@@StringReference@Internal@Windows@@QEAA@AEAY0GH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[103])
0x180059ce1  mov     ebx, 88980800h
0x180059ce6  mov     ecx, ebx
0x180059ce8  mov     rdx, [rax]
0x180059ceb  call    cs:__imp_RoOriginateError
0x180059cf1  mov     edx, 0F5h
0x180059cf6  jmp     loc_18005A083
0x180059cfb  cmp     qword ptr [rsi+30h], 0
0x180059d00  jnz     loc_18005A065
0x180059d06  mov     [rbp+57h+var_88], 0
0x180059d0e  mov     [rbp+57h+var_80], 0
0x180059d16  mov     [rbp+57h+var_90], 0
0x180059d1e  mov     [rbp+57h+var_78], 0
0x180059d26  test    r14, r14
0x180059d29  jnz     short loc_180059D38
0x180059d2b  mov     rcx, rsi; this
0x180059d2e  call    ?DisconnectCompositionInternal@CompositionHelper@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::CompositionHelper::DisconnectCompositionInternal(void)
0x180059d33  jmp     loc_18005A02E
0x180059d38  lea     rcx, [rbp+57h+var_88]
0x180059d3c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059d41  lea     r8, [rbp+57h+var_88]
0x180059d45  xor     ecx, ecx
0x180059d47  lea     rdx, _GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3
0x180059d4e  call    cs:__imp_DCompositionCreateDevice
0x180059d54  mov     ebx, eax
0x180059d56  test    eax, eax
0x180059d58  jns     short loc_180059D9B
0x180059d5a  mov     edx, 106h; void *
0x180059d5f  mov     rcx, [rbp+5Fh]; this
0x180059d63  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180059d6a  mov     r9d, ebx; char *
0x180059d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059d72  lea     rcx, [rbp+57h+var_78]
0x180059d76  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059d7b  lea     rcx, [rbp+57h+var_90]
0x180059d7f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059d84  lea     rcx, [rbp+57h+var_80]
0x180059d88  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059d8d  lea     rcx, [rbp+57h+var_88]
0x180059d91  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059d96  jmp     loc_18005A096
0x180059d9b  mov     rdi, [rbp+57h+var_88]
0x180059d9f  lea     rcx, [rbp+57h+var_90]
0x180059da3  mov     rax, [rdi]
0x180059da6  mov     rbx, [rax+38h]
0x180059daa  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059daf  lea     rdx, [rbp+57h+var_90]
0x180059db3  mov     rcx, rdi
0x180059db6  mov     rax, rbx
0x180059db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059dbe  mov     ebx, eax
0x180059dc0  test    eax, eax
0x180059dc2  jns     short loc_180059DCB
0x180059dc4  mov     edx, 107h
0x180059dc9  jmp     short loc_180059D5F
0x180059dcb  mov     rcx, [rbp+57h+var_90]
0x180059dcf  xor     r9d, r9d
0x180059dd2  mov     rdx, r14
0x180059dd5  mov     rax, [rcx]
0x180059dd8  lea     r8d, [r9+1]
0x180059ddc  mov     rax, [rax+80h]
0x180059de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059de8  mov     ebx, eax
0x180059dea  test    eax, eax
0x180059dec  jns     short loc_180059DF8
0x180059dee  mov     edx, 108h
0x180059df3  jmp     loc_180059D5F
0x180059df8  lea     rdx, [rbp+57h+var_78]
0x180059dfc  lea     rcx, [rbp+57h+var_90]
0x180059e00  call    ??$As@UIDCompositionVisualPartner@@@?$ComPtr@UIDCompositionVisual@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionVisualPartner@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IDCompositionVisual>::As<IDCompositionVisualPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionVisualPartner>>)
0x180059e05  mov     ebx, eax
0x180059e07  test    eax, eax
0x180059e09  jns     short loc_180059E15
0x180059e0b  mov     edx, 10Bh
0x180059e10  jmp     loc_180059D5F
0x180059e15  mov     rcx, [rbp+57h+var_78]
0x180059e19  movss   xmm1, cs:__real@3f800000
0x180059e21  mov     rax, [rcx]
0x180059e24  mov     rax, [rax+140h]
0x180059e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e30  mov     ebx, eax
0x180059e32  test    eax, eax
0x180059e34  jns     short loc_180059E40
0x180059e36  mov     edx, 10Ch
0x180059e3b  jmp     loc_180059D5F
0x180059e40  mov     rcx, [rbp+57h+var_78]
0x180059e44  movss   xmm1, cs:__real@3f800000
0x180059e4c  mov     rax, [rcx]
0x180059e4f  mov     rax, [rax+148h]
0x180059e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e5b  mov     ebx, eax
0x180059e5d  test    eax, eax
0x180059e5f  jns     short loc_180059E6B
0x180059e61  mov     edx, 10Dh
0x180059e66  jmp     loc_180059D5F
0x180059e6b  test    r15b, r15b
0x180059e6e  jnz     loc_180059F04
0x180059e74  mov     rdi, [rbp+57h+var_88]
0x180059e78  lea     rcx, [rbp+57h+var_80]
0x180059e7c  mov     rax, [rdi]
0x180059e7f  mov     rbx, [rax+30h]
0x180059e83  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059e88  mov     rdx, [rsi+70h]
0x180059e8c  lea     r9, [rbp+57h+var_80]
0x180059e90  xor     r8d, r8d
0x180059e93  mov     rcx, rdi
0x180059e96  mov     rax, rbx
0x180059e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e9e  mov     ebx, eax
0x180059ea0  test    eax, eax
0x180059ea2  jns     short loc_180059EAE
0x180059ea4  mov     edx, 112h
0x180059ea9  jmp     loc_180059D5F
0x180059eae  mov     rcx, [rbp+57h+var_80]
0x180059eb2  mov     rdx, [rbp+57h+var_90]
0x180059eb6  mov     rax, [rcx]
0x180059eb9  mov     rax, [rax+18h]
0x180059ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ec2  mov     ebx, eax
0x180059ec4  test    eax, eax
0x180059ec6  jns     short loc_180059ED2
0x180059ec8  mov     edx, 113h
0x180059ecd  jmp     loc_180059D5F
0x180059ed2  mov     rcx, [rbp+57h+var_88]
0x180059ed6  mov     rax, [rcx]
0x180059ed9  mov     rax, [rax+18h]
0x180059edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ee2  mov     ebx, eax
0x180059ee4  test    eax, eax
0x180059ee6  jns     short loc_180059EF2
0x180059ee8  mov     edx, 115h
0x180059eed  jmp     loc_180059D5F
0x180059ef2  lea     rcx, [rsi+50h]
0x180059ef6  lea     rdx, [rbp+57h+var_80]
0x180059efa  call    ??4?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IDCompositionTarget>::operator=(Microsoft::WRL::ComPtr<IDCompositionTarget> const &)
0x180059eff  jmp     loc_18005A008
0x180059f04  lea     rcx, [rbp+57h+var_60]
0x180059f08  mov     [rbp+57h+var_60], 0
0x180059f10  mov     [rbp+57h+var_58], 0
0x180059f18  mov     [rbp+57h+var_68], 0
0x180059f20  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059f25  lea     rcx, [rbp+57h+var_60]; struct Windows::ApplicationModel::Core::ICoreApplicationView **
0x180059f29  call    ?GetCoreApplicationViewOfCurrentThread@@YAJPEAPEAUICoreApplicationView@Core@ApplicationModel@Windows@@@Z; GetCoreApplicationViewOfCurrentThread(Windows::ApplicationModel::Core::ICoreApplicationView * *)
0x180059f2e  mov     ebx, eax
0x180059f30  test    eax, eax
0x180059f32  jns     short loc_180059F6C
0x180059f34  mov     edx, 11Dh; void *
0x180059f39  mov     rcx, [rbp+5Fh]; this
0x180059f3d  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180059f44  mov     r9d, ebx; char *
0x180059f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059f4c  lea     rcx, [rbp+57h+var_68]
0x180059f50  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059f55  lea     rcx, [rbp+57h+var_58]
0x180059f59  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059f5e  lea     rcx, [rbp+57h+var_60]
0x180059f62  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059f67  jmp     loc_180059D72
0x180059f6c  lea     rdx, [rbp+57h+var_58]
0x180059f70  lea     rcx, [rbp+57h+var_60]
0x180059f74  call    ??$As@UICoreApplicationView4@Private@Foundation@Windows@@@?$ComPtr@UICoreApplicationView@Core@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreApplicationView4@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICoreApplicationView4>>)
0x180059f79  mov     ebx, eax
0x180059f7b  test    eax, eax
0x180059f7d  jns     short loc_180059F86
0x180059f7f  mov     edx, 11Eh
0x180059f84  jmp     short loc_180059F39
0x180059f86  lea     rcx, [rbp+57h+var_68]
0x180059f8a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059f8f  mov     rcx, [rbp+57h+var_90]; struct IDCompositionVisual *
0x180059f93  lea     rdx, [rbp+57h+var_68]; struct Windows::Foundation::Private::ICompositionVisual **
0x180059f97  call    ?CreateAndAttachToCompositionVisualInterop@@YAJPEAUIDCompositionVisual@@PEAPEAUICompositionVisual@Private@Foundation@Windows@@@Z; CreateAndAttachToCompositionVisualInterop(IDCompositionVisual *,Windows::Foundation::Private::ICompositionVisual * *)
0x180059f9c  mov     ebx, eax
0x180059f9e  test    eax, eax
0x180059fa0  jns     short loc_180059FA9
0x180059fa2  mov     edx, 11Fh
0x180059fa7  jmp     short loc_180059F39
0x180059fa9  mov     rcx, [rbp+57h+var_58]
0x180059fad  mov     rdx, [rbp+57h+var_68]
0x180059fb1  mov     rax, [rcx]
0x180059fb4  mov     rax, [rax+38h]
0x180059fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fbd  mov     ebx, eax
0x180059fbf  test    eax, eax
0x180059fc1  jns     short loc_180059FCD
0x180059fc3  mov     edx, 120h
0x180059fc8  jmp     loc_180059F39
0x180059fcd  mov     rcx, [rbp+57h+var_88]
0x180059fd1  mov     rax, [rcx]
0x180059fd4  mov     rax, [rax+18h]
0x180059fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fdd  mov     ebx, eax
0x180059fdf  test    eax, eax
0x180059fe1  jns     short loc_180059FED
0x180059fe3  mov     edx, 121h
0x180059fe8  jmp     loc_180059F39
0x180059fed  lea     rcx, [rbp+57h+var_68]
0x180059ff1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059ff6  lea     rcx, [rbp+57h+var_58]
0x180059ffa  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180059fff  lea     rcx, [rbp+57h+var_60]
0x18005a003  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005a008  lea     rcx, [rsi+48h]
0x18005a00c  lea     rdx, [rbp+57h+var_88]
0x18005a010  call    ??4?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IDCompositionTarget>::operator=(Microsoft::WRL::ComPtr<IDCompositionTarget> const &)
0x18005a015  lea     rcx, [rsi+58h]
0x18005a019  lea     rdx, [rbp+57h+var_90]
0x18005a01d  call    ??4?$ComPtr@UIDCompositionVisual@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IDCompositionVisual>::operator=(Microsoft::WRL::ComPtr<IDCompositionVisual> const &)
0x18005a022  lea     rcx, [rsi+60h]
0x18005a026  mov     rdx, r14
0x18005a029  call    ??4?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@PEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=(IInspectable *)
0x18005a02e  lea     rcx, [rbp+57h+var_78]
0x18005a032  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005a037  lea     rcx, [rbp+57h+var_90]
0x18005a03b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005a040  lea     rcx, [rbp+57h+var_80]
0x18005a044  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005a049  lea     rcx, [rbp+57h+var_88]
0x18005a04d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005a052  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005a056  test    rcx, rcx
0x18005a059  jz      short loc_18005A061
0x18005a05b  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a061  xor     eax, eax
0x18005a063  jmp     short loc_18005A0A7
0x18005a065  lea     rcx, [rbp+57h+string]; string
0x18005a069  call    ??$?0$0HN@@StringReference@Internal@Windows@@QEAA@AEAY0HN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[125])
0x18005a06e  mov     ebx, 88980800h
0x18005a073  mov     ecx, ebx
0x18005a075  mov     rdx, [rax]
0x18005a078  call    cs:__imp_RoOriginateError
0x18005a07e  mov     edx, 0F7h; void *
0x18005a083  mov     rcx, [rbp+5Fh]; this
0x18005a087  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005a08e  mov     r9d, ebx; char *
0x18005a091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a096  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005a09a  test    rcx, rcx
0x18005a09d  jz      short loc_18005A0A5
0x18005a09f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a0a5  mov     eax, ebx
0x18005a0a7  mov     rcx, [rbp+57h+var_30]
0x18005a0ab  xor     rcx, rsp; StackCookie
0x18005a0ae  call    __security_check_cookie
0x18005a0b3  mov     rbx, [rsp+0C0h+arg_10]
0x18005a0bb  add     rsp, 0A0h
0x18005a0c2  pop     r15
0x18005a0c4  pop     r14
0x18005a0c6  pop     rdi
0x18005a0c7  pop     rsi
0x18005a0c8  pop     rbp
0x18005a0c9  retn
```
