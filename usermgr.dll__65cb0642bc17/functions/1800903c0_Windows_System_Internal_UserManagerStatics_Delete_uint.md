# Windows::System::Internal::UserManagerStatics::Delete(uint)

- ea: `0x1800903c0`
- end: `0x180090846`
- name: `?Delete@UserManagerStatics@Internal@System@Windows@@UEAAJI@Z`
- size: `1158`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005a6c`
- `0x180005c60`
- `0x180005d80`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000ed00`
- `0x180012890`
- `0x1800179c0`
- `0x18002618c`
- `0x18002799c`
- `0x1800332e8`
- `0x1800397c4`
- `0x18003e290`
- `0x1800641b8`
- `0x1800872d8`
- `0x1800903c0`
- `0x1800916f0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090488`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800905ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800905ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800905bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800905bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090701`
- `ntdll!RtlIsMultiSessionSku` at `0x18009041d`
- `ntdll!RtlIsMultiSessionSku` at `0x18009041d`

## string_xrefs

- `0x18009078b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800907a2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800907c8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800907df`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800907f3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009080a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009081f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180090833`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::System::Internal::UserManagerStatics::Delete(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rcx
  int v6; // r9d
  int v7; // r8d
  __int64 v8; // rdi
  char IsMultiSessionSku; // al
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // r10
  int v11; // eax
  HSTRING *v12; // r11
  bool v13; // bl
  int v14; // eax
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, _QWORD, char **); // rbx
  char *v17; // rdi
  int (__fastcall *v18)(char *, HSTRING *); // rbx
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int v22; // eax
  int v23; // eax
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v28; // rax
  int v29; // ebx
  wil *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  int v33; // [rsp+20h] [rbp-68h]
  __int64 v34; // [rsp+30h] [rbp-58h] BYREF
  char *v35; // [rsp+38h] [rbp-50h] BYREF
  int v36[2]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v37[7]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v39; // [rsp+98h] [rbp+10h] BYREF
  __int64 v40; // [rsp+A0h] [rbp+18h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+20h] BYREF

  v39 = a2;
  v4 = UserMgrUserModelTelemetry::Provider();
  v7 = *(_DWORD *)v4;
  if ( *(_DWORD *)v4 > 4u )
  {
    LODWORD(v40) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v4,
      (unsigned int)&dword_180126C1C,
      v7,
      v6,
      (__int64)&v40);
  }
  *(_QWORD *)v36 = 0;
  v8 = 0;
  v37[0] = 0;
  IsMultiSessionSku = RtlIsMultiSessionSku(v5);
  try
  {
    if ( IsMultiSessionSku )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070032LL,
        v33);
    UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)((char *)this - 40));
    v11 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)UserStaticsInternal + 136LL))(
            UserStaticsInternal,
            a2,
            0,
            0);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4EC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v11,
        (int)v36);
    LODWORD(v40) = a2;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    v35 = (char *)this + 224;
    std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
      (char *)this + 264,
      &string,
      &v40);
    v13 = string == *v12;
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v35);
    if ( !v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80A20306LL,
        (int)v36);
    if ( a2 - 1 > 0xE )
    {
      if ( a2 - 16 > 0xFFFEF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4FD,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x80070490LL,
          (int)v36);
      string = 0;
      v35 = 0;
      v34 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 64) + 8LL))((char *)this + 512) )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        if ( (int)Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
                    (char *)this + 512,
                    &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
                    &v34) >= 0 )
        {
          v15 = *((_QWORD *)this + 62);
          v16 = *(int (__fastcall **)(__int64, _QWORD, char **))(*(_QWORD *)v15 + 96LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
          if ( v16(v15, a2, &v35) >= 0 )
          {
            v17 = v35;
            v18 = *(int (__fastcall **)(char *, HSTRING *))(*(_QWORD *)v35 + 64LL);
            WindowsDeleteString(string);
            string = 0;
            if ( v18(v17, &string) >= 0 && !WindowsIsStringEmpty(string) )
            {
              v19 = v34;
              v20 = *(void (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v34 + 680LL);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              v20(v19, StringRawBuffer);
            }
          }
        }
      }
      v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 62) + 88LL))(*((_QWORD *)this + 62), a2);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v22,
          (int)v36);
      v23 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserDeletedEventArgs,Windows::System::Internal::UserDeletedEventArgs,unsigned int &>(
              v37,
              &v39);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v23,
          (int)v36);
      v8 = v37[0];
      v37[0] = 0;
      v37[1] = v8;
      Windows::Internal::Events::HeapEventStore::GetTargets((char *)this + 688, &v40);
      if ( Windows::Internal::Events::HeapEventStore::GetSize((Windows::Internal::Events::HeapEventStore *)&v40) )
        Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_94891d06eed33533d74872aa05742a67_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(
          (__int64)v37,
          (Windows::Internal::Events::HeapEventStore *)&v40,
          (__int64)this + 680,
          (__int64)this + 680,
          (int)v36);
      if ( v40 )
      {
        v40 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      WindowsDeleteString(string);
    }
    else
    {
      v14 = Windows::System::Internal::UserManagerStatics::FreeSponsoredUserId(
              (Windows::System::Internal::UserManagerStatics *)((char *)this - 40),
              a2);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F8,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v14,
          (int)v36);
    }
    v24 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v24 > 4u )
    {
      LODWORD(v40) = 0;
      LODWORD(string) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v24,
        (unsigned int)byte_180126BE9,
        v25,
        v26,
        (__int64)&string,
        (__int64)&v40);
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
    result = 0;
  }
  catch ( ... )
  {
    v28 = UserMgrUserModelTelemetry::Provider();
    v29 = (int)v28;
    v30 = (wil *)*(unsigned int *)v28;
    if ( (unsigned int)v30 > 4 )
    {
      LODWORD(v40) = wil::ResultFromCaughtException(v30);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)byte_180126BAB,
        v31,
        v32,
        (__int64)&v40);
    }
    LODWORD(v40) = wil::ResultFromCaughtException(v30);
    return (unsigned int)v40;
  }
  return result;
}

```

## disassembly

```asm
0x1800903c0  mov     [rsp+arg_8], edx
0x1800903c4  push    rbx
0x1800903c5  push    rsi
0x1800903c6  push    rdi
0x1800903c7  push    r14
0x1800903c9  push    r15
0x1800903cb  sub     rsp, 60h
0x1800903cf  mov     esi, edx
0x1800903d1  mov     r14, rcx
0x1800903d4  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800903d9  mov     r8d, [rax]
0x1800903dc  cmp     r8d, 4
0x1800903e0  jbe     short loc_180090405
0x1800903e2  mov     dword ptr [rsp+88h+arg_10], esi
0x1800903e9  lea     rcx, [rsp+88h+arg_10]
0x1800903f1  mov     qword ptr [rsp+88h+var_68], rcx; int
0x1800903f6  lea     rdx, dword_180126C1C
0x1800903fd  mov     rcx, rax
0x180090400  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180090405  mov     qword ptr [rsp+88h+var_48], 0
0x18009040e  xor     edi, edi
0x180090410  mov     [rsp+88h+var_38], rdi
0x180090415  mov     rbx, [rsp+88h]
0x18009041d  call    cs:__imp_RtlIsMultiSessionSku
0x180090423  test    al, al
0x180090425  jnz     loc_180090785
0x18009042b  lea     rcx, [r14-28h]; this
0x18009042f  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180090434  mov     r10, rax
0x180090437  mov     rcx, [rax]
0x18009043a  mov     rax, [rcx+88h]
0x180090441  lea     rcx, [rsp+88h+var_48]
0x180090446  mov     qword ptr [rsp+88h+var_68], rcx; int
0x18009044b  xor     r9d, r9d
0x18009044e  xor     r8d, r8d
0x180090451  mov     edx, esi
0x180090453  mov     rcx, r10
0x180090456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009045b  mov     rcx, [rsp+88h]; this
0x180090463  test    eax, eax
0x180090465  js      loc_18009079F
0x18009046b  cmp     qword ptr [rsp+88h+var_48], 0
0x180090471  jnz     loc_1800907B3
0x180090477  mov     dword ptr [rsp+88h+arg_10], esi
0x18009047e  lea     rbx, [r14+0E0h]
0x180090485  mov     rcx, rbx; lpCriticalSection
0x180090488  call    cs:__imp_EnterCriticalSection
0x18009048e  mov     [rsp+88h+var_50], rbx
0x180090493  lea     r11, [r14+108h]
0x18009049a  lea     r8, [rsp+88h+arg_10]
0x1800904a2  lea     rdx, [rsp+88h+string]
0x1800904aa  mov     rcx, r11
0x1800904ad  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x1800904b2  mov     rdx, [r11]
0x1800904b5  cmp     [rsp+88h+string], rdx
0x1800904bd  setz    bl
0x1800904c0  lea     rcx, [rsp+88h+var_50]; this
0x1800904c5  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800904ca  mov     rcx, [rsp+88h]; this
0x1800904d2  test    bl, bl
0x1800904d4  jz      loc_1800907D9
0x1800904da  lea     eax, [rsi-1]
0x1800904dd  cmp     eax, 0Eh
0x1800904e0  ja      short loc_180090502
0x1800904e2  mov     edx, esi; unsigned int
0x1800904e4  lea     rcx, [r14-28h]; this
0x1800904e8  call    ?FreeSponsoredUserId@UserManagerStatics@Internal@System@Windows@@AEAAJI@Z; Windows::System::Internal::UserManagerStatics::FreeSponsoredUserId(uint)
0x1800904ed  mov     rcx, [rsp+88h]; this
0x1800904f5  test    eax, eax
0x1800904f7  js      loc_1800907F0
0x1800904fd  jmp     loc_180090707
0x180090502  mov     rcx, [rsp+88h]; this
0x18009050a  lea     eax, [rsi-10h]
0x18009050d  cmp     eax, 0FFFEFh
0x180090512  ja      loc_180090804
0x180090518  mov     [rsp+88h+string], 0
0x180090524  mov     [rsp+88h+var_50], 0
0x18009052d  mov     [rsp+88h+var_58], 0
0x180090536  lea     rbx, [r14+200h]
0x18009053d  mov     rax, [rbx]
0x180090540  mov     rcx, rbx
0x180090543  mov     rax, [rax+8]
0x180090547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009054c  test    al, al
0x18009054e  jz      loc_180090624
0x180090554  lea     rcx, [rsp+88h+var_58]
0x180090559  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009055e  lea     r8, [rsp+88h+var_58]
0x180090563  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18009056a  mov     rcx, rbx
0x18009056d  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x180090572  test    eax, eax
0x180090574  js      loc_180090624
0x18009057a  mov     rdi, [r14+1F0h]
0x180090581  mov     rax, [rdi]
0x180090584  mov     rbx, [rax+60h]
0x180090588  lea     rcx, [rsp+88h+var_50]
0x18009058d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090592  lea     r8, [rsp+88h+var_50]
0x180090597  mov     edx, esi
0x180090599  mov     rcx, rdi
0x18009059c  mov     rax, rbx
0x18009059f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905a4  test    eax, eax
0x1800905a6  js      short loc_180090624
0x1800905a8  mov     rdi, [rsp+88h+var_50]
0x1800905ad  mov     rax, [rdi]
0x1800905b0  mov     rbx, [rax+40h]
0x1800905b4  mov     rcx, [rsp+88h+string]; string
0x1800905bc  call    cs:__imp_WindowsDeleteString
0x1800905c2  mov     [rsp+88h+string], 0
0x1800905ce  lea     rdx, [rsp+88h+string]
0x1800905d6  mov     rcx, rdi
0x1800905d9  mov     rax, rbx
0x1800905dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905e1  test    eax, eax
0x1800905e3  js      short loc_180090624
0x1800905e5  mov     rcx, [rsp+88h+string]; string
0x1800905ed  call    cs:__imp_WindowsIsStringEmpty
0x1800905f3  test    eax, eax
0x1800905f5  jnz     short loc_180090624
0x1800905f7  mov     rdi, [rsp+88h+var_58]
0x1800905fc  mov     rax, [rdi]
0x1800905ff  mov     rbx, [rax+2A8h]
0x180090606  xor     edx, edx; length
0x180090608  mov     rcx, [rsp+88h+string]; string
0x180090610  call    cs:__imp_WindowsGetStringRawBuffer
0x180090616  mov     rdx, rax
0x180090619  mov     rcx, rdi
0x18009061c  mov     rax, rbx
0x18009061f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090624  mov     rcx, [r14+1F0h]
0x18009062b  mov     rax, [rcx]
0x18009062e  mov     edx, esi
0x180090630  mov     rax, [rax+58h]
0x180090634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090639  mov     rcx, [rsp+88h]; this
0x180090641  test    eax, eax
0x180090643  js      loc_18009081C
0x180090649  lea     rdx, [rsp+88h+arg_8]
0x180090651  lea     rcx, [rsp+88h+var_38]
0x180090656  call    ??$MakeAndInitialize@VUserDeletedEventArgs@Internal@System@Windows@@V1234@AEAI@Details@WRL@Microsoft@@YAJPEAPEAVUserDeletedEventArgs@Internal@System@Windows@@AEAI@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserDeletedEventArgs,Windows::System::Internal::UserDeletedEventArgs,uint &>(Windows::System::Internal::UserDeletedEventArgs * *,uint &)
0x18009065b  mov     rcx, [rsp+88h]; this
0x180090663  test    eax, eax
0x180090665  js      loc_180090830
0x18009066b  mov     rdi, [rsp+88h+var_38]
0x180090670  mov     [rsp+88h+var_38], 0
0x180090679  mov     [rsp+88h+var_30], rdi
0x18009067e  lea     rcx, [r14+2B0h]
0x180090685  lea     rdx, [rsp+88h+arg_10]
0x18009068d  call    ?GetTargets@HeapEventStore@Events@Internal@Windows@@QEAA?AVHeapEventStoreTargets@1234@XZ; Windows::Internal::Events::HeapEventStore::GetTargets(void)
0x180090692  lea     rcx, [rsp+88h+arg_10]; this
0x18009069a  call    ?GetSize@HeapEventStore@Events@Internal@Windows@@QEBA_KXZ; Windows::Internal::Events::HeapEventStore::GetSize(void)
0x18009069f  test    rax, rax
0x1800906a2  jz      short loc_1800906C4
0x1800906a4  lea     r9, [r14+2A8h]
0x1800906ab  lea     r8, [r14+2A8h]
0x1800906b2  lea     rdx, [rsp+88h+arg_10]
0x1800906ba  lea     rcx, [rsp+88h+var_38]
0x1800906bf  call    ??$Invoke@V_lambda_94891d06eed33533d74872aa05742a67_@@V?$HardenedEventSource@U?$IEventHandler@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@Internal@Windows@@@?$ParallelInvokeTraits@$07@Events@Internal@Windows@@SAXAEAV_lambda_94891d06eed33533d74872aa05742a67_@@AEAVHeapEventStoreTargets@HeapEventStore@123@AEAV?$HardenedEventSource@U?$IEventHandler@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@23@AEAVWatchdogEventCallMonitor@123@_K@Z; Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_94891d06eed33533d74872aa05742a67_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(_lambda_94891d06eed33533d74872aa05742a67_ &,Windows::Internal::Events::HeapEventStore::HeapEventStoreTargets &,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>> &,Windows::Internal::Events::WatchdogEventCallMonitor &,unsigned __int64)
0x1800906c4  mov     rcx, [rsp+88h+arg_10]
0x1800906cc  test    rcx, rcx
0x1800906cf  jz      short loc_1800906E3
0x1800906d1  mov     [rsp+88h+arg_10], 0
0x1800906dd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800906e2  nop
0x1800906e3  lea     rcx, [rsp+88h+var_58]
0x1800906e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800906ed  nop
0x1800906ee  lea     rcx, [rsp+88h+var_50]
0x1800906f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800906f8  nop
0x1800906f9  mov     rcx, [rsp+88h+string]; string
0x180090701  call    cs:__imp_WindowsDeleteString
0x180090707  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18009070c  mov     ecx, [rax]
0x18009070e  cmp     ecx, 4
0x180090711  jbe     short loc_18009074F
0x180090713  mov     dword ptr [rsp+88h+arg_10], 0
0x18009071e  mov     dword ptr [rsp+88h+string], esi
0x180090725  lea     rcx, [rsp+88h+arg_10]
0x18009072d  mov     [rsp+88h+var_60], rcx
0x180090732  lea     rcx, [rsp+88h+string]
0x18009073a  mov     qword ptr [rsp+88h+var_68], rcx
0x18009073f  lea     rdx, byte_180126BE9
0x180090746  mov     rcx, rax
0x180090749  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009074e  nop
0x18009074f  test    rdi, rdi
0x180090752  jz      short loc_180090764
0x180090754  mov     rax, [rdi]
0x180090757  mov     rcx, rdi
0x18009075a  mov     rax, [rax+10h]
0x18009075e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090763  nop
0x180090764  lea     rcx, [rsp+88h+var_48]
0x180090769  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009076e  xor     eax, eax
0x180090770  jmp     short loc_180090779
0x180090772  mov     eax, dword ptr [rsp+88h+arg_10]
0x180090779  add     rsp, 60h
0x18009077d  pop     r15
0x18009077f  pop     r14
0x180090781  pop     rdi
0x180090782  pop     rsi
0x180090783  pop     rbx
0x180090784  retn
0x180090785  mov     r9d, 80070032h; char *
0x18009078b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180090792  mov     edx, 4EBh; void *
0x180090797  mov     rcx, rbx; this
0x18009079a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009079f  mov     r9d, eax; char *
0x1800907a2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800907a9  mov     edx, 4ECh; void *
0x1800907ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800907b3  mov     ecx, 80A20302h
0x1800907b8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800907bd  mov     r9d, eax; char *
0x1800907c0  mov     rcx, [rsp+88h]; this
0x1800907c8  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800907cf  mov     edx, 4F1h; void *
0x1800907d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800907d9  mov     r9d, 80A20306h; char *
0x1800907df  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800907e6  mov     edx, 4F4h; void *
0x1800907eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800907f0  mov     r9d, eax; char *
0x1800907f3  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800907fa  mov     edx, 4F8h; void *
0x1800907ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090804  mov     r9d, 80070490h; char *
0x18009080a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180090811  mov     edx, 4FDh; void *
0x180090816  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009081c  mov     r9d, eax; char *
0x18009081f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180090826  mov     edx, 50Dh; void *
0x18009082b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090830  mov     r9d, eax; char *
0x180090833  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18009083a  mov     edx, 50Eh; void *
0x18009083f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
