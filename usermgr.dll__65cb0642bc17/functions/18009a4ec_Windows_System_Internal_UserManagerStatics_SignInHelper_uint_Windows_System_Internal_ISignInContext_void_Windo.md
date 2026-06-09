# Windows::System::Internal::UserManagerStatics::SignInHelper(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)

- ea: `0x18009a4ec`
- end: `0x18009ac93`
- name: `?SignInHelper@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z`
- size: `1959`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int, struct Windows::System::Internal::ISignInContext *, void *, struct Windows::System::Internal::ISignInResult **)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008bcd0`
- `0x1800c4070`

## callees

- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x180024828`
- `0x18002618c`
- `0x180037ee4`
- `0x18003b578`
- `0x18004e4e8`
- `0x1800545f4`
- `0x1800643dc`
- `0x180068d54`
- `0x180084fac`
- `0x180087564`
- `0x18008798c`
- `0x180087c74`
- `0x18009a4ec`
- `0x18009ac9c`
- `0x18009e47c`
- `0x1800a0128`
- `0x1800bf0cc`
- `0x1800bf468`
- `0x1800bfbc0`
- `0x1800ec010`

## string_xrefs

- `0x18009aaf7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab0f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab23`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab38`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab4c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab60`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab74`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab89`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ab9d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009abb2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009abc7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009abdc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009abf0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac07`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac1c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac31`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac46`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac5a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac6b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ac80`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::System::Internal::UserManagerStatics::SignInHelper(
        __int64 **this,
        unsigned int a2,
        struct Windows::System::Internal::ISignInContext *a3,
        void *a4,
        struct Windows::System::Internal::ISignInResult **a5)
{
  int v8; // eax
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  int started; // eax
  unsigned int v13; // r8d
  char v14; // si
  unsigned int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  struct Windows::System::Internal::ISignInResult *v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  const struct _tlgProvider_t *v24; // rax
  unsigned int v25; // r8d
  int v26; // r9d
  int v27; // eax
  __int64 (__fastcall **v28)(_QWORD, GUID *, __int64); // rax
  int v29; // eax
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rbx
  int v37; // eax
  int v38; // eax
  int SignInResult; // eax
  __int64 result; // rax
  wil *v41; // rcx
  int v42; // r8d
  int v43; // r9d
  int v44; // [rsp+20h] [rbp-D8h]
  int v45; // [rsp+20h] [rbp-D8h]
  bool v46; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v47[3]; // [rsp+41h] [rbp-B7h] BYREF
  _DWORD v48[3]; // [rsp+44h] [rbp-B4h] BYREF
  int v49; // [rsp+50h] [rbp-A8h] BYREF
  int v50[2]; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+60h] [rbp-98h] BYREF
  struct Windows::System::Internal::ISignInResult *v52; // [rsp+68h] [rbp-90h] BYREF
  struct Windows::System::IUser *v53; // [rsp+70h] [rbp-88h] BYREF
  __int64 v54; // [rsp+78h] [rbp-80h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp-78h] BYREF
  Windows::System::Internal::UserManagerStatics *v56; // [rsp+88h] [rbp-70h] BYREF
  int v57; // [rsp+90h] [rbp-68h]
  __int64 v58; // [rsp+98h] [rbp-60h] BYREF
  _QWORD v59[5]; // [rsp+A0h] [rbp-58h] BYREF
  char v60; // [rsp+C8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  unsigned int v62; // [rsp+108h] [rbp+10h] BYREF
  struct Windows::System::Internal::ISignInContext *v63; // [rsp+110h] [rbp+18h] BYREF

  v63 = a3;
  v62 = a2;
  v55 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v55);
  v54 = 0;
  v8 = Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::Implementation::ISignInContextPrivate>(
         &v55,
         (__int64)&v54);
  try
  {
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA79,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v8,
        v44);
    v53 = 0;
    v49 = 0;
    (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, int *))(*(_QWORD *)a3 + 64LL))(a3, &v49);
    v9 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v9 > 4u )
    {
      v48[0] = v49;
      v50[0] = v62;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&word_1801263F6,
        v10,
        v11,
        (__int64)v50,
        (__int64)v48);
    }
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA87,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v44);
    *a5 = 0;
    v46 = 0;
    started = Windows::System::Internal::Implementation::SignInTracker::StartTrackingSignIn(
                (Windows::System::Internal::Implementation::SignInTracker *)(this + 32),
                v62,
                &v46);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)started,
        v44);
    v59[0] = &v46;
    v59[1] = this;
    v59[2] = &v62;
    v59[3] = &a5;
    v59[4] = &v53;
    v14 = 1;
    v60 = 1;
    if ( v46 )
    {
      v15 = Windows::System::Internal::Implementation::SignOutTracker::WaitForSignOutToComplete(
              (Windows::System::Internal::Implementation::SignOutTracker *)(this + 40),
              v62,
              v13);
      if ( (int)(v15 + 0x80000000) < 0 || v15 == -2136866039 )
        v14 = 0;
      if ( v14 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAA9,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)v15,
          v44);
      if ( v62 - 1 > 0xE )
      {
        if ( v62 == 0x200000 )
        {
          v17 = Windows::System::Internal::UserManagerStatics::SignInUnknownUser(
                  (Windows::System::Internal::UserManagerStatics *)this,
                  0x200000u,
                  a3,
                  a4,
                  a5);
          if ( v17 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAB4,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
              (const char *)(unsigned int)v17,
              v45);
        }
        else
        {
          v18 = Windows::System::Internal::UserManagerStatics::SignInLSAUser(
                  (Windows::System::Internal::UserManagerStatics *)this,
                  v62,
                  a3,
                  a4,
                  &v53,
                  a5);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xABC,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
              (const char *)(unsigned int)v18,
              v45);
        }
      }
      else
      {
        v16 = Windows::System::Internal::UserManagerStatics::SignInSponsoredUser(
                (struct _RTL_CRITICAL_SECTION *)this,
                v62,
                a3,
                a4,
                a5);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAAD,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v16,
            v45);
      }
      v52 = *a5;
      v19 = v52;
      if ( v52 )
        (*(void (__fastcall **)(struct Windows::System::Internal::ISignInResult *))(*(_QWORD *)v52 + 8LL))(v52);
      v48[0] = 0;
      v20 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInResult *, _DWORD *))(*(_QWORD *)v19 + 80LL))(
              v19,
              v48);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAC1,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v20,
          v45);
      v56 = (Windows::System::Internal::UserManagerStatics *)this;
      v57 = v48[0];
      v21 = Windows::Internal::ComTaskPool::QueueTask__lambda_02434b6cd590c78b6080bfcdf6187612___(retaddr, &v56);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xACC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v21,
          v45);
      if ( (unsigned int)dword_180146228 > 4 )
      {
        v50[0] = 0;
        LODWORD(v51) = v49;
        v48[1] = v62;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180146228,
          (unsigned int)byte_1801263B5,
          v22,
          v23,
          (__int64)&v48[1],
          (__int64)&v51,
          (__int64)v50);
      }
    }
    else
    {
      v24 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v24 > 4u )
      {
        v48[1] = 0;
        LODWORD(v51) = v49;
        v50[0] = v62;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (unsigned int)byte_18012636B,
          v25,
          v26,
          (__int64)v50,
          (__int64)&v51,
          (__int64)&v48[1]);
      }
      v27 = Windows::System::Internal::Implementation::SignInTracker::WaitForSignInToComplete(
              (Windows::System::Internal::Implementation::SignInTracker *)(this + 32),
              v62,
              v25);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAE6,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v27,
          v44);
      v52 = 0;
      v28 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
      v52 = 0;
      v29 = ((__int64 (__fastcall *)(struct Windows::System::Internal::ISignInContext *, struct Windows::System::Internal::ISignInResult **))v28[14])(
              a3,
              &v52);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAE8,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v29,
          v44);
      if ( v52 )
      {
        v48[1] = 0;
        v34 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v54 + 48LL))(v54, &v48[1]);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAF9,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v34,
            v44);
        v58 = 0;
        v56 = v52;
        *(_QWORD *)v50 = 0;
        v35 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::ValidateCredentialsAsyncOperation,Windows::System::Internal::ValidateCredentialsAsyncOperation,Windows::System::Internal::ICredentialSerialization * &,Windows::System::IUser * &>(
                v50,
                &v56,
                &v58);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAFB,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v35,
            v44);
        v51 = 0;
        v36 = *(_QWORD *)v50;
        v37 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::ValidateCredentialsResult *>>(*(_QWORD *)v50);
        if ( v37 >= 0 )
          v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 64LL))(v36, &v51);
        if ( v37 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAFD,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v37,
            v44);
        v48[0] = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v51 + 56LL))(v51, v48);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAFF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v38,
            v44);
        if ( v48[0] < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0xB00,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)v48[0],
            v44);
        wil::com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>(&v51);
        wil::com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>(v50);
      }
      else
      {
        *(_QWORD *)&v48[1] = 0;
        v47[0] = 0;
        v30 = this[67];
        v31 = *v30;
        *(_QWORD *)&v48[1] = 0;
        v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _DWORD *))(v31 + 96))(v30, v62, &v48[1]);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAEE,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v32,
            v44);
        v33 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)&v48[1] + 80LL))(*(_QWORD *)&v48[1], v47);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAEF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v33,
            v44);
        if ( !v47[0] )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAF0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)0x80A20303LL,
            v44);
        wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v48[1]);
      }
      SignInResult = Windows::System::Internal::Implementation::SignInTracker::GetSignInResult(
                       (Windows::System::Internal::Implementation::SignInTracker *)(this + 32),
                       v62,
                       a5);
      if ( SignInResult < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB02,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)SignInResult,
          v44);
    }
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v52);
    v60 = 0;
    lambda_39ee232c9deb1a999e5ca3015c65ab41_::operator()(v59);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    result = 0;
  }
  catch ( ... )
  {
    v48[0] = 0;
    v41 = v63;
    if ( v63 )
      (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, _DWORD *))(*(_QWORD *)v63 + 64LL))(
        v63,
        v48);
    if ( (unsigned int)dword_180146228 > 4 )
    {
      LODWORD(v63) = wil::ResultFromCaughtException(v41);
      v48[1] = v48[0];
      LODWORD(v51) = v62;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180146228,
        (unsigned int)&byte_180126317,
        v42,
        v43,
        (__int64)&v51,
        (__int64)&v48[1],
        (__int64)&v63);
    }
    LODWORD(v63) = wil::ResultFromCaughtException(v41);
    return (unsigned int)v63;
  }
  return result;
}

```

## disassembly

```asm
0x18009a4ec  mov     rax, rsp
0x18009a4ef  mov     [rax+8], rbx
0x18009a4f3  mov     [rax+18h], r8
0x18009a4f7  mov     [rax+10h], edx
0x18009a4fa  push    rsi
0x18009a4fb  push    rdi
0x18009a4fc  push    r12
0x18009a4fe  push    r14
0x18009a500  push    r15
0x18009a502  sub     rsp, 0D0h
0x18009a509  mov     r15, r9
0x18009a50c  mov     rbx, r8
0x18009a50f  mov     rdi, rcx
0x18009a512  mov     [rax-78h], rbx
0x18009a516  lea     rcx, [rax-78h]
0x18009a51a  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009a51f  nop
0x18009a520  xor     r12d, r12d
0x18009a523  mov     [rsp+0F8h+var_80], r12
0x18009a528  lea     rdx, [rsp+0F8h+var_80]
0x18009a52d  lea     rcx, [rsp+0F8h+var_78]
0x18009a535  call    ??$As@UISignInContextPrivate@Implementation@Internal@System@Windows@@@?$ComPtr@UISignInContext@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInContextPrivate@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::Implementation::ISignInContextPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::ISignInContextPrivate>>)
0x18009a53a  mov     rcx, [rsp+0F8h]; this
0x18009a542  test    eax, eax
0x18009a544  js      loc_18009AAF4
0x18009a54a  mov     [rsp+0F8h+var_88], r12
0x18009a54f  mov     [rsp+0F8h+var_A8], r12d
0x18009a554  mov     rax, [rbx]
0x18009a557  lea     rdx, [rsp+0F8h+var_A8]
0x18009a55c  mov     rcx, rbx
0x18009a55f  mov     rax, [rax+40h]
0x18009a563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a568  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18009a56d  mov     ecx, [rax]
0x18009a56f  cmp     ecx, 4
0x18009a572  jbe     short loc_18009A5AA
0x18009a574  mov     ecx, [rsp+0F8h+var_A8]
0x18009a578  mov     dword ptr [rsp+0F8h+var_B4], ecx
0x18009a57c  mov     ecx, [rsp+0F8h+arg_8]
0x18009a583  mov     [rsp+0F8h+var_A0], ecx
0x18009a587  lea     rcx, [rsp+0F8h+var_B4]
0x18009a58c  mov     [rsp+0F8h+var_D0], rcx
0x18009a591  lea     rcx, [rsp+0F8h+var_A0]
0x18009a596  mov     [rsp+0F8h+var_D8], rcx; int
0x18009a59b  lea     rdx, word_1801263F6
0x18009a5a2  mov     rcx, rax
0x18009a5a5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009a5aa  mov     rcx, [rsp+0F8h]; this
0x18009a5b2  mov     rax, [rsp+0F8h+arg_20]
0x18009a5ba  test    rax, rax
0x18009a5bd  jz      loc_18009AB09
0x18009a5c3  mov     [rax], r12
0x18009a5c6  mov     [rsp+0F8h+var_B8], r12b
0x18009a5cb  lea     r14, [rdi+100h]
0x18009a5d2  lea     r8, [rsp+0F8h+var_B8]; bool *
0x18009a5d7  mov     edx, [rsp+0F8h+arg_8]; unsigned int
0x18009a5de  mov     rcx, r14; this
0x18009a5e1  call    ?StartTrackingSignIn@SignInTracker@Implementation@Internal@System@Windows@@QEAAJIPEA_N@Z; Windows::System::Internal::Implementation::SignInTracker::StartTrackingSignIn(uint,bool *)
0x18009a5e6  mov     rcx, [rsp+0F8h]; this
0x18009a5ee  test    eax, eax
0x18009a5f0  js      loc_18009AB20
0x18009a5f6  lea     rax, [rsp+0F8h+var_B8]
0x18009a5fb  mov     [rsp+0F8h+var_58], rax
0x18009a603  mov     [rsp+0F8h+var_50], rdi
0x18009a60b  lea     rax, [rsp+0F8h+arg_8]
0x18009a613  mov     [rsp+0F8h+var_48], rax
0x18009a61b  lea     rax, [rsp+0F8h+arg_20]
0x18009a623  mov     [rsp+0F8h+var_40], rax
0x18009a62b  lea     rax, [rsp+0F8h+var_88]
0x18009a630  mov     [rsp+0F8h+var_38], rax
0x18009a638  mov     sil, 1
0x18009a63b  mov     [rsp+0F8h+var_30], sil
0x18009a643  cmp     [rsp+0F8h+var_B8], r12b
0x18009a648  jz      loc_18009A833
0x18009a64e  lea     rcx, [rdi+140h]; this
0x18009a655  mov     edx, [rsp+0F8h+arg_8]; unsigned int
0x18009a65c  call    ?WaitForSignOutToComplete@SignOutTracker@Implementation@Internal@System@Windows@@QEAAJIK@Z; Windows::System::Internal::Implementation::SignOutTracker::WaitForSignOutToComplete(uint,ulong)
0x18009a661  mov     edx, 80000000h
0x18009a666  lea     ecx, [rax+rdx]
0x18009a669  test    edx, ecx
0x18009a66b  jnz     short loc_18009A674
0x18009a66d  cmp     eax, 80A20309h
0x18009a672  jnz     short loc_18009A677
0x18009a674  mov     sil, r12b
0x18009a677  mov     rcx, [rsp+0F8h]; this
0x18009a67f  test    sil, sil
0x18009a682  jnz     loc_18009AB35
0x18009a688  mov     edx, [rsp+0F8h+arg_8]; unsigned int
0x18009a68f  lea     eax, [rdx-1]
0x18009a692  mov     r9, r15; void *
0x18009a695  mov     r8, rbx; struct Windows::System::Internal::ISignInContext *
0x18009a698  cmp     eax, 0Eh
0x18009a69b  mov     rax, [rsp+0F8h+arg_20]
0x18009a6a3  ja      short loc_18009A6C4
0x18009a6a5  mov     [rsp+0F8h+var_D8], rax; int
0x18009a6aa  mov     rcx, rdi; this
0x18009a6ad  call    ?SignInSponsoredUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z; Windows::System::Internal::UserManagerStatics::SignInSponsoredUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)
0x18009a6b2  mov     rcx, [rsp+0F8h]; this
0x18009a6ba  test    eax, eax
0x18009a6bc  js      loc_18009AB49
0x18009a6c2  jmp     short loc_18009A715
0x18009a6c4  mov     ecx, 200000h
0x18009a6c9  cmp     edx, ecx
0x18009a6cb  jnz     short loc_18009A6EE
0x18009a6cd  mov     [rsp+0F8h+var_D8], rax; int
0x18009a6d2  mov     edx, ecx; unsigned int
0x18009a6d4  mov     rcx, rdi; this
0x18009a6d7  call    ?SignInUnknownUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z; Windows::System::Internal::UserManagerStatics::SignInUnknownUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)
0x18009a6dc  mov     rcx, [rsp+0F8h]; this
0x18009a6e4  test    eax, eax
0x18009a6e6  js      loc_18009AB5D
0x18009a6ec  jmp     short loc_18009A715
0x18009a6ee  mov     [rsp+0F8h+var_D0], rax; struct Windows::System::Internal::ISignInResult **
0x18009a6f3  lea     rax, [rsp+0F8h+var_88]
0x18009a6f8  mov     [rsp+0F8h+var_D8], rax; int
0x18009a6fd  mov     rcx, rdi; this
0x18009a700  call    ?SignInLSAUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUIUser@34@PEAPEAUISignInResult@234@@Z; Windows::System::Internal::UserManagerStatics::SignInLSAUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::IUser * *,Windows::System::Internal::ISignInResult * *)
0x18009a705  mov     rcx, [rsp+0F8h]; this
0x18009a70d  test    eax, eax
0x18009a70f  js      loc_18009AB71
0x18009a715  mov     rax, [rsp+0F8h+arg_20]
0x18009a71d  mov     rbx, [rax]
0x18009a720  mov     [rsp+0F8h+var_90], rbx
0x18009a725  test    rbx, rbx
0x18009a728  jz      short loc_18009A73A
0x18009a72a  mov     rax, [rbx]
0x18009a72d  mov     rcx, rbx
0x18009a730  mov     rax, [rax+8]
0x18009a734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a739  nop
0x18009a73a  mov     dword ptr [rsp+0F8h+var_B4], r12d
0x18009a73f  mov     rax, [rbx]
0x18009a742  lea     rdx, [rsp+0F8h+var_B4]
0x18009a747  mov     rcx, rbx
0x18009a74a  mov     rax, [rax+50h]
0x18009a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a753  mov     rcx, [rsp+0F8h]; this
0x18009a75b  test    eax, eax
0x18009a75d  js      loc_18009AB86
0x18009a763  mov     [rsp+0F8h+var_70], rdi
0x18009a76b  mov     eax, dword ptr [rsp+0F8h+var_B4]
0x18009a76f  mov     [rsp+0F8h+var_68], eax
0x18009a776  lea     rdx, [rsp+0F8h+var_70]
0x18009a77e  call    Windows__Internal__ComTaskPool__QueueTask__lambda_02434b6cd590c78b6080bfcdf6187612___
0x18009a783  mov     rcx, [rsp+0F8h]; this
0x18009a78b  test    eax, eax
0x18009a78d  js      loc_18009AB9A
0x18009a793  mov     eax, cs:dword_180146228
0x18009a799  cmp     eax, 4
0x18009a79c  jbe     short loc_18009A7E8
0x18009a79e  mov     [rsp+0F8h+var_A0], r12d
0x18009a7a3  mov     eax, [rsp+0F8h+var_A8]
0x18009a7a7  mov     dword ptr [rsp+0F8h+var_98], eax
0x18009a7ab  mov     eax, [rsp+0F8h+arg_8]
0x18009a7b2  mov     dword ptr [rsp+0F8h+var_B4+4], eax
0x18009a7b6  lea     rax, [rsp+0F8h+var_A0]
0x18009a7bb  mov     [rsp+0F8h+var_C8], rax
0x18009a7c0  lea     rax, [rsp+0F8h+var_98]
0x18009a7c5  mov     [rsp+0F8h+var_D0], rax
0x18009a7ca  lea     rax, [rsp+0F8h+var_B4+4]
0x18009a7cf  mov     [rsp+0F8h+var_D8], rax
0x18009a7d4  lea     rdx, byte_1801263B5
0x18009a7db  lea     rcx, dword_180146228
0x18009a7e2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009a7e7  nop
0x18009a7e8  lea     rcx, [rsp+0F8h+var_90]
0x18009a7ed  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18009a7f2  nop
0x18009a7f3  mov     [rsp+0F8h+var_30], r12b
0x18009a7fb  lea     rcx, [rsp+0F8h+var_58]
0x18009a803  call    _lambda_39ee232c9deb1a999e5ca3015c65ab41___operator__
0x18009a808  nop
0x18009a809  lea     rcx, [rsp+0F8h+var_88]
0x18009a80e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009a813  nop
0x18009a814  lea     rcx, [rsp+0F8h+var_80]
0x18009a819  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a81e  nop
0x18009a81f  lea     rcx, [rsp+0F8h+var_78]
0x18009a827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009a82c  xor     eax, eax
0x18009a82e  jmp     loc_18009AADC
0x18009a833  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18009a838  mov     ecx, [rax]
0x18009a83a  cmp     ecx, 4
0x18009a83d  jbe     short loc_18009A884
0x18009a83f  mov     dword ptr [rsp+0F8h+var_B4+4], r12d
0x18009a844  mov     ecx, [rsp+0F8h+var_A8]
0x18009a848  mov     dword ptr [rsp+0F8h+var_98], ecx
0x18009a84c  mov     ecx, [rsp+0F8h+arg_8]
0x18009a853  mov     [rsp+0F8h+var_A0], ecx
0x18009a857  lea     rcx, [rsp+0F8h+var_B4+4]
0x18009a85c  mov     [rsp+0F8h+var_C8], rcx
0x18009a861  lea     rcx, [rsp+0F8h+var_98]
0x18009a866  mov     [rsp+0F8h+var_D0], rcx
0x18009a86b  lea     rcx, [rsp+0F8h+var_A0]
0x18009a870  mov     [rsp+0F8h+var_D8], rcx; int
0x18009a875  lea     rdx, byte_18012636B
0x18009a87c  mov     rcx, rax
0x18009a87f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009a884  mov     edx, [rsp+0F8h+arg_8]; unsigned int
0x18009a88b  mov     rcx, r14; this
0x18009a88e  call    ?WaitForSignInToComplete@SignInTracker@Implementation@Internal@System@Windows@@QEAAJIK@Z; Windows::System::Internal::Implementation::SignInTracker::WaitForSignInToComplete(uint,ulong)
0x18009a893  mov     rcx, [rsp+0F8h]; this
0x18009a89b  test    eax, eax
0x18009a89d  js      loc_18009ABAF
0x18009a8a3  mov     [rsp+0F8h+var_90], r12
0x18009a8a8  mov     rax, [rbx]
0x18009a8ab  mov     [rsp+0F8h+var_90], r12
0x18009a8b0  lea     rdx, [rsp+0F8h+var_90]
0x18009a8b5  mov     rcx, rbx
0x18009a8b8  mov     rax, [rax+70h]
0x18009a8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8c1  mov     rcx, [rsp+0F8h]; this
0x18009a8c9  test    eax, eax
0x18009a8cb  js      loc_18009ABC4
0x18009a8d1  cmp     [rsp+0F8h+var_90], r12
0x18009a8d6  jnz     loc_18009A967
0x18009a8dc  mov     qword ptr [rsp+0F8h+var_B4+4], r12
0x18009a8e1  mov     [rsp+0F8h+var_B7], r12b
0x18009a8e6  mov     rcx, [rdi+218h]
0x18009a8ed  mov     rax, [rcx]
0x18009a8f0  mov     qword ptr [rsp+0F8h+var_B4+4], r12
0x18009a8f5  lea     r8, [rsp+0F8h+var_B4+4]
0x18009a8fa  mov     edx, [rsp+0F8h+arg_8]
0x18009a901  mov     rax, [rax+60h]
0x18009a905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a90a  mov     rcx, [rsp+0F8h]; this
0x18009a912  test    eax, eax
0x18009a914  js      loc_18009ABD9
0x18009a91a  mov     rcx, qword ptr [rsp+0F8h+var_B4+4]
0x18009a91f  mov     rax, [rcx]
0x18009a922  lea     rdx, [rsp+0F8h+var_B7]
0x18009a927  mov     rax, [rax+50h]
0x18009a92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a930  mov     rcx, [rsp+0F8h]; this
0x18009a938  test    eax, eax
0x18009a93a  js      loc_18009ABED
0x18009a940  cmp     [rsp+0F8h+var_B7], r12b
0x18009a945  setz    al
0x18009a948  mov     rcx, [rsp+0F8h]; this
0x18009a950  test    al, al
0x18009a952  jnz     loc_18009AC01
0x18009a958  lea     rcx, [rsp+0F8h+var_B4+4]
0x18009a95d  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18009a962  jmp     loc_18009AA66
0x18009a967  mov     dword ptr [rsp+0F8h+var_B4+4], r12d
0x18009a96c  mov     rcx, [rsp+0F8h+var_80]
0x18009a971  mov     rax, [rcx]
0x18009a974  lea     rdx, [rsp+0F8h+var_B4+4]
0x18009a979  mov     rax, [rax+30h]
0x18009a97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a982  mov     rcx, [rsp+0F8h]; this
0x18009a98a  test    eax, eax
0x18009a98c  js      loc_18009AC19
0x18009a992  mov     [rsp+0F8h+var_60], r12
0x18009a99a  mov     rax, [rsp+0F8h+var_90]
0x18009a99f  mov     [rsp+0F8h+var_70], rax
0x18009a9a7  mov     qword ptr [rsp+0F8h+var_A0], r12
0x18009a9ac  lea     r8, [rsp+0F8h+var_60]
0x18009a9b4  lea     rdx, [rsp+0F8h+var_70]
0x18009a9bc  lea     rcx, [rsp+0F8h+var_A0]
0x18009a9c1  call    ??$MakeAndInitialize@VValidateCredentialsAsyncOperation@Internal@System@Windows@@V1234@AEAPEAUICredentialSerialization@234@AEAPEAUIUser@34@@Details@WRL@Microsoft@@YAJPEAPEAVValidateCredentialsAsyncOperation@Internal@System@Windows@@AEAPEAUICredentialSerialization@456@AEAPEAUIUser@56@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::ValidateCredentialsAsyncOperation,Windows::System::Internal::ValidateCredentialsAsyncOperation,Windows::System::Internal::ICredentialSerialization * &,Windows::System::IUser * &>(Windows::System::Internal::ValidateCredentialsAsyncOperation * *,Windows::System::Internal::ICredentialSerialization * &,Windows::System::IUser * &)
0x18009a9c6  mov     rcx, [rsp+0F8h]; this
0x18009a9ce  test    eax, eax
0x18009a9d0  js      loc_18009AC2E
0x18009a9d6  mov     [rsp+0F8h+var_98], r12
0x18009a9db  mov     rbx, qword ptr [rsp+0F8h+var_A0]
0x18009a9e0  mov     rcx, rbx
0x18009a9e3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVValidateCredentialsResult@Internal@System@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::ValidateCredentialsResult *>>(Windows::Foundation::IAsyncOperation<Windows::System::Internal::ValidateCredentialsResult *> *,tagCOWAIT_FLAGS,void *)
0x18009a9e8  test    eax, eax
0x18009a9ea  js      short loc_18009AA00
0x18009a9ec  mov     rax, [rbx]
0x18009a9ef  lea     rdx, [rsp+0F8h+var_98]
0x18009a9f4  mov     rcx, rbx
0x18009a9f7  mov     rax, [rax+40h]
0x18009a9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa00  mov     rcx, [rsp+0F8h]; this
0x18009aa08  test    eax, eax
0x18009aa0a  js      loc_18009AC43
0x18009aa10  mov     dword ptr [rsp+0F8h+var_B4], r12d
0x18009aa15  mov     rcx, [rsp+0F8h+var_98]
0x18009aa1a  mov     rax, [rcx]
0x18009aa1d  lea     rdx, [rsp+0F8h+var_B4]
0x18009aa22  mov     rax, [rax+38h]
0x18009aa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa2b  mov     rcx, [rsp+0F8h]; this
0x18009aa33  test    eax, eax
0x18009aa35  js      loc_18009AC57
0x18009aa3b  mov     r9d, dword ptr [rsp+0F8h+var_B4]; char *
0x18009aa40  mov     rcx, [rsp+0F8h]; this
0x18009aa48  test    r9d, r9d
0x18009aa4b  js      loc_18009AC6B
0x18009aa51  lea     rcx, [rsp+0F8h+var_98]
0x18009aa56  call    ??1?$com_ptr_t@UIValidateCredentialsResult@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>(void)
0x18009aa5b  nop
0x18009aa5c  lea     rcx, [rsp+0F8h+var_A0]
0x18009aa61  call    ??1?$com_ptr_t@UIValidateCredentialsResult@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>(void)
0x18009aa66  mov     r8, [rsp+0F8h+arg_20]; struct Windows::System::Internal::ISignInResult **
0x18009aa6e  mov     edx, [rsp+0F8h+arg_8]; unsigned int
  ... truncated ...
```
