# Windows::System::Internal::FindAllAsyncOperation::DoWork(void)

- ea: `0x180048230`
- end: `0x180048937`
- name: `?DoWork@FindAllAsyncOperation@Internal@System@Windows@@UEAAJXZ`
- size: `1799`
- prototype: `__int64 __fastcall(Windows::System::Internal::FindAllAsyncOperation *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006130`
- `0x18000707c`
- `0x180007920`
- `0x18000acdc`
- `0x18000cd30`
- `0x18000ce48`
- `0x180011490`
- `0x180012890`
- `0x180018458`
- `0x180034454`
- `0x1800344b8`
- `0x18003b2c0`
- `0x18003d588`
- `0x180048230`
- `0x18004e58c`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180048604`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180048604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800485a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800485a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048681`
- `ntdll!RtlEqualSid` at `0x180048663`
- `ntdll!RtlEqualSid` at `0x180048663`
- `ntdll!RtlIsMultiSessionSku` at `0x18004846f`
- `ntdll!RtlIsMultiSessionSku` at `0x18004846f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180048462`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180048462`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800486af`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800486af`

## string_xrefs

- `0x180048834`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x180048848`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x18004885c`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x180048870`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x180048885`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x180048897`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x1800488ab`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x1800488c0`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x1800488d4`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x1800488e9`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x1800488fa`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x18004890f`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`
- `0x180048924`: `onecore\ds\security\umstartup\usermgr\lib\findallasyncoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::FindAllAsyncOperation::DoWork(PSID *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // eax
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // r13d
  __int64 v10; // rbx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD, struct Windows::System::IUser **); // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int8 v16; // r15
  bool v17; // zf
  char v18; // al
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  int v22; // eax
  void (__fastcall *v23)(void *, __int64 *); // rdi
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rdi
  int v26; // eax
  __int64 v27; // rsi
  PSID v28; // rdi
  PCWSTR StringRawBuffer; // rax
  const char *v30; // r9
  int v31; // eax
  unsigned __int8 v32; // dl
  int CurrentServiceSessionId; // eax
  int v34; // ecx
  int v35; // eax
  __int64 (__fastcall *v36)(__int64, PSID *); // rdi
  _QWORD *v37; // rsi
  int v38; // eax
  const struct _tlgProvider_t *v39; // rax
  int v40; // r8d
  int v41; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v43; // rax
  int v44; // ebx
  wil *v45; // rcx
  int v46; // r8d
  int v47; // r9d
  int v48; // [rsp+20h] [rbp-118h]
  char v49; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v50[3]; // [rsp+41h] [rbp-F7h] BYREF
  int v51; // [rsp+44h] [rbp-F4h] BYREF
  int v52; // [rsp+48h] [rbp-F0h] BYREF
  PSID pSid; // [rsp+50h] [rbp-E8h] BYREF
  int v54; // [rsp+58h] [rbp-E0h] BYREF
  struct Windows::System::IUser *v55; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v56; // [rsp+68h] [rbp-D0h] BYREF
  int v57; // [rsp+6Ch] [rbp-CCh] BYREF
  HSTRING string; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+78h] [rbp-C0h] BYREF
  __int64 v60; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v61; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+98h] [rbp-A0h] BYREF
  _BYTE v64[8]; // [rsp+A0h] [rbp-98h] BYREF
  unsigned int (__fastcall *v65)(__int64, PCWSTR, PSID *); // [rsp+A8h] [rbp-90h]
  Windows::System::Internal::FindAllAsyncOperation *v66; // [rsp+B0h] [rbp-88h]
  _BYTE *v67; // [rsp+E0h] [rbp-58h]
  __int64 v68; // [rsp+E8h] [rbp-50h]
  char *v69; // [rsp+F0h] [rbp-48h]
  __int64 v70; // [rsp+F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v66 = (Windows::System::Internal::FindAllAsyncOperation *)this;
  v62 = 0;
  v63 = 0;
  v59 = 0;
  v56 = 0;
  v51 = 0;
  v57 = 0;
  v61 = 0;
  v2 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v49 = *((_BYTE *)this + 640);
    v50[0] = *((_BYTE *)this + 648);
    v69 = &v49;
    v70 = 1;
    v67 = v50;
    v68 = 1;
    v48 = 4;
    tlgWriteTransfer_EventWriteTransfer(v2, &word_18012B7EE, 0, 0);
  }
  try
  {
    v3 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(&v62);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
        (const char *)(unsigned int)v3,
        v48);
    v4 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0>>(
           (__int64)retaddr,
           &v63);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
        (const char *)(unsigned int)v4,
        v48);
    v5 = v62;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    v7 = v6(v5, &v59);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
        (const char *)(unsigned int)v7,
        v48);
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v59 + 56LL))(v59, &v56);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
        (const char *)(unsigned int)v8,
        v48);
    v9 = 0;
    v10 = v63;
    while ( v9 < v56 )
    {
      v55 = 0;
      v54 = 0;
      v52 = 0;
      v11 = v59;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::System::IUser **))(*(_QWORD *)v59 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      v13 = v12(v11, v9, &v55);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
          (const char *)(unsigned int)v13,
          v48);
      v14 = (*(__int64 (__fastcall **)(struct Windows::System::IUser *, int *))(*(_QWORD *)v55 + 56LL))(v55, &v52);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
          (const char *)(unsigned int)v14,
          v48);
      v15 = (*(__int64 (__fastcall **)(struct Windows::System::IUser *, int *))(*(_QWORD *)v55 + 64LL))(v55, &v54);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
          (const char *)(unsigned int)v15,
          v48);
      v16 = 1;
      LODWORD(pSid) = 0;
      RtlGetDeviceFamilyInfoEnum(0, &pSid, 0);
      if ( (_DWORD)pSid == 5 || (v17 = (unsigned __int8)RtlIsMultiSessionSku() == 0, v18 = 1, !v17) )
        v18 = 0;
      if ( *((_BYTE *)this + 648) )
      {
        v19 = *((_DWORD *)this + 163);
        if ( v19 != v52 && (!v18 || v19 != 1 || v52 != 2) )
          v16 = 0;
      }
      if ( !*((_BYTE *)this + 640) || (v20 = *((_DWORD *)this + 161), v20 == v54) || v18 && !v20 && v54 == 1 )
      {
        if ( v16 )
        {
          v60 = 0;
          v21 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
                  (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v55,
                  &v60);
          if ( v21 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x94,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
              (const char *)(unsigned int)v21,
              v48);
          v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 96LL))(v60, &v57);
          if ( v22 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x95,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
              (const char *)(unsigned int)v22,
              v48);
          if ( !*((_BYTE *)this + 236) )
          {
            if ( (unsigned int)(v54 - 2) <= 1 )
            {
              v16 = 0;
            }
            else
            {
              string = 0;
              pSid = 0;
              v23 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection
                                                             + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
              v23(&Windows::System::Internal::Adapters::g_AdapterCollection, &v61);
              v24 = v60;
              v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v60 + 72LL);
              WindowsDeleteString(string);
              string = 0;
              v26 = v25(v24, &string);
              if ( v26 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xA2,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
                  (const char *)(unsigned int)v26,
                  v48);
              v27 = v61;
              v65 = *(unsigned int (__fastcall **)(__int64, PCWSTR, PSID *))(*(_QWORD *)v61 + 40LL);
              v28 = pSid;
              if ( pSid )
              {
                wil::last_error_context::last_error_context((wil::last_error_context *)v64);
                FreeSid(v28);
                wil::last_error_context::~last_error_context((wil::last_error_context *)v64);
              }
              pSid = 0;
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( !v65(v27, StringRawBuffer, &pSid) )
                wil::details::in1diag3::_Throw_GetLastError(
                  retaddr,
                  (void *)0xA3,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
                  v30);
              v16 &= -(RtlEqualSid(this[43], pSid) != 0);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
              WindowsDeleteString(string);
            }
          }
          v31 = Windows::System::Internal::UserPackageRegistration::RegisterPackageIfNeeded(
                  (Windows::System::Internal::UserPackageRegistration *)(this + 83),
                  (struct _BASIC_CALLER_INFORMATION *)(this + 28),
                  v55);
          v32 = 0;
          if ( v31 >= 0 )
            v32 = v16;
          if ( v32 )
          {
            CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v16);
            v34 = *((_DWORD *)this + 58);
            if ( v34 == CurrentServiceSessionId || v34 == v57 )
            {
              v35 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *))(*(_QWORD *)v10 + 104LL))(
                      v10,
                      v55);
              if ( v35 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xBB,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
                  (const char *)(unsigned int)v35,
                  v48);
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      ++v9;
    }
    v36 = *(__int64 (__fastcall **)(__int64, PSID *))(*(_QWORD *)v10 + 64LL);
    v37 = this + 82;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 82);
    v38 = v36(v10, this + 82);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\findallasyncoperation.cpp",
        (const char *)(unsigned int)v38,
        v48);
    if ( *v37 )
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v37 + 56LL))(*v37, &v51);
    v39 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v39 > 5u )
    {
      LODWORD(pSid) = 0;
      v52 = v51;
      v50[0] = *((_BYTE *)this + 640);
      v49 = *((_BYTE *)this + 648);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v39,
        (unsigned int)word_18012B702,
        v40,
        v41,
        (__int64)&v49,
        (__int64)v50,
        (__int64)&v52,
        (__int64)&pSid);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    result = 0;
  }
  catch ( ... )
  {
    v43 = UserMgrUserModelTelemetry::Provider();
    v44 = (int)v43;
    v45 = (wil *)*(unsigned int *)v43;
    if ( (unsigned int)v45 > 5 )
    {
      v51 = wil::ResultFromCaughtException(v45);
      v50[0] = *((_BYTE *)v66 + 640);
      v49 = *((_BYTE *)v66 + 648);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v44,
        (unsigned int)byte_18012B775,
        v46,
        v47,
        (__int64)&v49,
        (__int64)v50,
        (__int64)&v51);
    }
    return (unsigned int)wil::ResultFromCaughtException(v45);
  }
  return result;
}

```

## disassembly

```asm
0x180048230  mov     r11, rsp
0x180048233  mov     [r11+10h], rbx
0x180048237  mov     [r11+18h], rsi
0x18004823b  push    rdi
0x18004823c  push    r12
0x18004823e  push    r13
0x180048240  push    r14
0x180048242  push    r15
0x180048244  sub     rsp, 110h
0x18004824b  mov     rax, cs:__security_cookie
0x180048252  xor     rax, rsp
0x180048255  mov     [rsp+138h+var_38], rax
0x18004825d  mov     r14, rcx
0x180048260  mov     [rsp+138h+var_88], rcx
0x180048268  xor     esi, esi
0x18004826a  mov     [r11-0A8h], rsi
0x180048271  mov     [r11-0A0h], rsi
0x180048278  mov     [rsp+138h+var_C0], rsi
0x18004827d  mov     [rsp+138h+var_D0], esi
0x180048281  mov     [rsp+138h+var_F4], esi
0x180048285  mov     [rsp+138h+var_CC], esi
0x180048289  mov     [r11-0B0h], rsi
0x180048290  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180048295  mov     ecx, [rax]
0x180048297  cmp     ecx, 5
0x18004829a  jbe     short loc_18004830E
0x18004829c  mov     cl, [r14+280h]
0x1800482a3  mov     [rsp+138h+var_F8], cl
0x1800482a7  mov     cl, [r14+288h]
0x1800482ae  mov     [rsp+138h+var_F7], cl
0x1800482b2  lea     rcx, [rsp+138h+var_F8]
0x1800482b7  mov     [rsp+138h+var_48], rcx
0x1800482bf  mov     [rsp+138h+var_40], 1
0x1800482cb  lea     rcx, [rsp+138h+var_F7]
0x1800482d0  mov     [rsp+138h+var_58], rcx
0x1800482d8  mov     [rsp+138h+var_50], 1
0x1800482e4  lea     rcx, [rsp+138h+var_78]
0x1800482ec  mov     [rsp+138h+var_110], rcx
0x1800482f1  mov     [rsp+138h+var_118], 4; int
0x1800482f9  xor     r9d, r9d
0x1800482fc  xor     r8d, r8d
0x1800482ff  lea     rdx, word_18012B7EE
0x180048306  mov     rcx, rax
0x180048309  call    _tlgWriteTransfer_EventWriteTransfer
0x18004830e  lea     rcx, [rsp+138h+var_A8]
0x180048316  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x18004831b  mov     rcx, [rsp+138h]; this
0x180048323  test    eax, eax
0x180048325  js      loc_180048831
0x18004832b  lea     rdx, [rsp+138h+var_A0]
0x180048333  call    ??$CreateExternalObjectVector@VUser@System@Windows@@V?$AgileVector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0> * *)
0x180048338  mov     rcx, [rsp+138h]; this
0x180048340  test    eax, eax
0x180048342  js      loc_180048845
0x180048348  mov     rdi, [rsp+138h+var_A8]
0x180048350  mov     rax, [rdi]
0x180048353  mov     rbx, [rax+30h]
0x180048357  lea     rcx, [rsp+138h+var_C0]
0x18004835c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048361  lea     rdx, [rsp+138h+var_C0]
0x180048366  mov     rcx, rdi
0x180048369  mov     rax, rbx
0x18004836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048371  mov     rcx, [rsp+138h]; this
0x180048379  test    eax, eax
0x18004837b  js      loc_180048859
0x180048381  mov     rcx, [rsp+138h+var_C0]
0x180048386  mov     rax, [rcx]
0x180048389  lea     rdx, [rsp+138h+var_D0]
0x18004838e  mov     rax, [rax+38h]
0x180048392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048397  mov     rcx, [rsp+138h]; this
0x18004839f  test    eax, eax
0x1800483a1  js      loc_18004886D
0x1800483a7  mov     r13d, esi
0x1800483aa  mov     rbx, [rsp+138h+var_A0]
0x1800483b2  cmp     r13d, [rsp+138h+var_D0]
0x1800483b7  jnb     loc_18004870A
0x1800483bd  mov     [rsp+138h+var_D8], rsi
0x1800483c2  mov     [rsp+138h+var_E0], esi
0x1800483c6  mov     [rsp+138h+var_F0], esi
0x1800483ca  mov     rsi, [rsp+138h+var_C0]
0x1800483cf  mov     rax, [rsi]
0x1800483d2  mov     rdi, [rax+30h]
0x1800483d6  lea     rcx, [rsp+138h+var_D8]
0x1800483db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800483e0  lea     r8, [rsp+138h+var_D8]
0x1800483e5  mov     edx, r13d
0x1800483e8  mov     rcx, rsi
0x1800483eb  mov     rax, rdi
0x1800483ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483f3  mov     rcx, [rsp+138h]; this
0x1800483fb  xor     esi, esi
0x1800483fd  test    eax, eax
0x1800483ff  js      loc_180048882
0x180048405  mov     rcx, [rsp+138h+var_D8]
0x18004840a  mov     rax, [rcx]
0x18004840d  lea     rdx, [rsp+138h+var_F0]
0x180048412  mov     rax, [rax+38h]
0x180048416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004841b  mov     rcx, [rsp+138h]; this
0x180048423  test    eax, eax
0x180048425  js      loc_180048894
0x18004842b  mov     rcx, [rsp+138h+var_D8]
0x180048430  mov     rax, [rcx]
0x180048433  lea     rdx, [rsp+138h+var_E0]
0x180048438  mov     rax, [rax+40h]
0x18004843c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048441  mov     rcx, [rsp+138h]; this
0x180048449  test    eax, eax
0x18004844b  js      loc_1800488A8
0x180048451  mov     r15b, 1
0x180048454  mov     dword ptr [rsp+138h+pSid], esi
0x180048458  xor     r8d, r8d
0x18004845b  lea     rdx, [rsp+138h+pSid]
0x180048460  xor     ecx, ecx
0x180048462  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180048468  cmp     dword ptr [rsp+138h+pSid], 5
0x18004846d  jz      short loc_18004847C
0x18004846f  call    cs:__imp_RtlIsMultiSessionSku
0x180048475  test    al, al
0x180048477  mov     al, r15b
0x18004847a  jz      short loc_18004847F
0x18004847c  mov     al, sil
0x18004847f  cmp     [r14+288h], sil
0x180048486  jz      short loc_1800484A8
0x180048488  mov     ecx, [r14+28Ch]
0x18004848f  cmp     ecx, [rsp+138h+var_F0]
0x180048493  jz      short loc_1800484A8
0x180048495  test    al, al
0x180048497  jz      short loc_1800484A5
0x180048499  cmp     ecx, 1
0x18004849c  jnz     short loc_1800484A5
0x18004849e  cmp     [rsp+138h+var_F0], 2
0x1800484a3  jz      short loc_1800484A8
0x1800484a5  mov     r15b, sil
0x1800484a8  cmp     [r14+280h], sil
0x1800484af  jz      short loc_1800484D9
0x1800484b1  mov     ecx, [r14+284h]
0x1800484b8  cmp     ecx, [rsp+138h+var_E0]
0x1800484bc  jz      short loc_1800484D9
0x1800484be  test    al, al
0x1800484c0  jz      loc_1800486F8
0x1800484c6  test    ecx, ecx
0x1800484c8  jnz     loc_1800486F8
0x1800484ce  cmp     [rsp+138h+var_E0], 1
0x1800484d3  jnz     loc_1800486F8
0x1800484d9  test    r15b, r15b
0x1800484dc  jz      loc_1800486F8
0x1800484e2  mov     [rsp+138h+var_B8], rsi
0x1800484ea  lea     rdx, [rsp+138h+var_B8]
0x1800484f2  lea     rcx, [rsp+138h+var_D8]
0x1800484f7  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x1800484fc  mov     rcx, [rsp+138h]; this
0x180048504  test    eax, eax
0x180048506  js      loc_1800488BD
0x18004850c  mov     rcx, [rsp+138h+var_B8]
0x180048514  mov     rax, [rcx]
0x180048517  lea     rdx, [rsp+138h+var_CC]
0x18004851c  mov     rax, [rax+60h]
0x180048520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048525  mov     rcx, [rsp+138h]; this
0x18004852d  test    eax, eax
0x18004852f  js      loc_1800488D1
0x180048535  lea     r12, [r14+0E0h]
0x18004853c  cmp     [r12+0Ch], sil
0x180048541  jnz     loc_18004868C
0x180048547  mov     eax, [rsp+138h+var_E0]
0x18004854b  add     eax, 0FFFFFFFEh
0x18004854e  cmp     eax, 1
0x180048551  jbe     loc_180048689
0x180048557  mov     [rsp+138h+string], rsi
0x18004855c  mov     [rsp+138h+pSid], rsi
0x180048561  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180048568  mov     rdi, [rax+38h]
0x18004856c  lea     rcx, [rsp+138h+var_B0]
0x180048574  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048579  lea     rdx, [rsp+138h+var_B0]
0x180048581  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180048588  mov     rax, rdi
0x18004858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048590  mov     rsi, [rsp+138h+var_B8]
0x180048598  mov     rax, [rsi]
0x18004859b  mov     rdi, [rax+48h]
0x18004859f  mov     rcx, [rsp+138h+string]; string
0x1800485a4  call    cs:__imp_WindowsDeleteString
0x1800485aa  mov     [rsp+138h+string], 0
0x1800485b3  lea     rdx, [rsp+138h+string]
0x1800485b8  mov     rcx, rsi
0x1800485bb  mov     rax, rdi
0x1800485be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485c3  mov     rcx, [rsp+138h]; this
0x1800485cb  test    eax, eax
0x1800485cd  js      loc_1800488E6
0x1800485d3  mov     rsi, [rsp+138h+var_B0]
0x1800485db  mov     rax, [rsi]
0x1800485de  mov     rax, [rax+28h]
0x1800485e2  mov     [rsp+138h+var_90], rax
0x1800485ea  mov     rdi, [rsp+138h+pSid]
0x1800485ef  test    rdi, rdi
0x1800485f2  jz      short loc_180048617
0x1800485f4  lea     rcx, [rsp+138h+var_98]; this
0x1800485fc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180048601  mov     rcx, rdi; pSid
0x180048604  call    cs:__imp_FreeSid
0x18004860a  lea     rcx, [rsp+138h+var_98]; this
0x180048612  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180048617  mov     [rsp+138h+pSid], 0
0x180048620  xor     edx, edx; length
0x180048622  mov     rcx, [rsp+138h+string]; string
0x180048627  call    cs:__imp_WindowsGetStringRawBuffer
0x18004862d  lea     r8, [rsp+138h+pSid]
0x180048632  mov     rdx, rax
0x180048635  mov     rcx, rsi
0x180048638  mov     rax, [rsp+138h+var_90]
0x180048640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048645  mov     rcx, [rsp+138h]; this
0x18004864d  xor     esi, esi
0x18004864f  test    eax, eax
0x180048651  jz      loc_1800488FA
0x180048657  mov     rdx, [rsp+138h+pSid]; Sid2
0x18004865c  mov     rcx, [r14+158h]; Sid1
0x180048663  call    cs:__imp_RtlEqualSid
0x180048669  nop
0x18004866a  neg     al
0x18004866c  sbb     al, al
0x18004866e  and     r15b, al
0x180048671  lea     rcx, [rsp+138h+pSid]
0x180048676  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004867b  nop
0x18004867c  mov     rcx, [rsp+138h+string]; string
0x180048681  call    cs:__imp_WindowsDeleteString
0x180048687  jmp     short loc_18004868C
0x180048689  mov     r15b, sil
0x18004868c  lea     rcx, [r14+298h]; this
0x180048693  mov     r8, [rsp+138h+var_D8]; struct Windows::System::IUser *
0x180048698  mov     rdx, r12; struct _BASIC_CALLER_INFORMATION *
0x18004869b  call    ?RegisterPackageIfNeeded@UserPackageRegistration@Internal@System@Windows@@QEAAJPEAU_BASIC_CALLER_INFORMATION@@PEAUIUser@34@@Z; Windows::System::Internal::UserPackageRegistration::RegisterPackageIfNeeded(_BASIC_CALLER_INFORMATION *,Windows::System::IUser *)
0x1800486a0  mov     edx, esi
0x1800486a2  movzx   ecx, r15b
0x1800486a6  test    eax, eax
0x1800486a8  cmovns  edx, ecx
0x1800486ab  test    dl, dl
0x1800486ad  jz      short loc_1800486EA
0x1800486af  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800486b5  mov     ecx, [r14+0E8h]
0x1800486bc  cmp     ecx, eax
0x1800486be  jz      short loc_1800486C6
0x1800486c0  cmp     ecx, [rsp+138h+var_CC]
0x1800486c4  jnz     short loc_1800486EA
0x1800486c6  mov     rax, [rbx]
0x1800486c9  mov     rdx, [rsp+138h+var_D8]
0x1800486ce  mov     rcx, rbx
0x1800486d1  mov     rax, [rax+68h]
0x1800486d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486da  mov     rcx, [rsp+138h]; this
0x1800486e2  test    eax, eax
0x1800486e4  js      loc_18004890C
0x1800486ea  lea     rcx, [rsp+138h+var_B8]
0x1800486f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800486f7  nop
0x1800486f8  lea     rcx, [rsp+138h+var_D8]
0x1800486fd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048702  inc     r13d
0x180048705  jmp     loc_1800483B2
0x18004870a  mov     rax, [rbx]
0x18004870d  mov     rdi, [rax+40h]
0x180048711  lea     rsi, [r14+290h]
0x180048718  mov     rcx, rsi
0x18004871b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048720  mov     rdx, rsi
0x180048723  mov     rcx, rbx
0x180048726  mov     rax, rdi
0x180048729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004872e  mov     rcx, [rsp+138h]; this
0x180048736  test    eax, eax
0x180048738  js      loc_180048921
0x18004873e  mov     rcx, [rsi]
0x180048741  test    rcx, rcx
0x180048744  jz      short loc_180048757
0x180048746  mov     rax, [rcx]
0x180048749  lea     rdx, [rsp+138h+var_F4]
0x18004874e  mov     rax, [rax+38h]
0x180048752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048757  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18004875c  mov     ecx, [rax]
0x18004875e  cmp     ecx, 5
0x180048761  jbe     short loc_1800487C1
0x180048763  mov     dword ptr [rsp+138h+pSid], 0
0x18004876b  mov     ecx, [rsp+138h+var_F4]
0x18004876f  mov     [rsp+138h+var_F0], ecx
0x180048773  mov     cl, [r14+280h]
0x18004877a  mov     [rsp+138h+var_F7], cl
0x18004877e  mov     cl, [r14+288h]
0x180048785  mov     [rsp+138h+var_F8], cl
0x180048789  lea     rcx, [rsp+138h+pSid]
0x18004878e  mov     [rsp+138h+var_100], rcx
0x180048793  lea     rcx, [rsp+138h+var_F0]
0x180048798  mov     [rsp+138h+var_108], rcx
0x18004879d  lea     rcx, [rsp+138h+var_F7]
  ... truncated ...
```
