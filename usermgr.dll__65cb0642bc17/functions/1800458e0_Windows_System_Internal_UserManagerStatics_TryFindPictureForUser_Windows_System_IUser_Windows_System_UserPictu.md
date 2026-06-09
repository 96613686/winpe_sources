# Windows::System::Internal::UserManagerStatics::TryFindPictureForUser(Windows::System::IUser *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x1800458e0`
- end: `0x180045d81`
- name: `?TryFindPictureForUser@UserManagerStatics@Internal@System@Windows@@UEAAJPEAUIUser@34@W4UserPictureSize@34@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `1185`
- prototype: `int __high(struct Windows::System::IUser *, enum Windows::System::UserPictureSize, struct Windows::Storage::Streams::IRandomAccessStreamReference **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008b10`
- `0x180009af0`
- `0x18000a4a0`
- `0x18000acdc`
- `0x18000ca64`
- `0x180011490`
- `0x180012a1c`
- `0x180013278`
- `0x1800132d0`
- `0x180015960`
- `0x180024f5c`
- `0x18002514c`
- `0x1800353d8`
- `0x18003b578`
- `0x18004254c`
- `0x1800458e0`
- `0x18004e58c`
- `0x18006f1c9`
- `0x18006f1e1`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180045b48`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180045b48`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045b99`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045cb3`

## string_xrefs

- `0x180045cf6`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d0b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d1f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d33`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d44`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d59`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180045d6e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::UserManagerStatics::TryFindPictureForUser(
        __int64 a1,
        struct Windows::System::IUser *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int64 v4; // rbp
  unsigned int v6; // r14d
  __int64 result; // rax
  int valid; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int64); // rbx
  int v12; // eax
  __int64 v13; // rcx
  int DefaultLocalAccountPicture; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  const char *v18; // r9
  __int64 v19; // rcx
  int DefaultSignedInAccountPicture; // eax
  __int64 v21; // rcx
  int v22; // eax
  wil *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // [rsp+20h] [rbp-40h]
  _BYTE v30[4]; // [rsp+60h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+288h]

  v4 = (unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL;
  v6 = a3;
  if ( !a4 )
    return 2147942487LL;
  if ( (unsigned int)dword_180146228 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, a3, a4) )
  {
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0x1000000;
    *(_BYTE *)v4 = 1;
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x230) = ((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 24;
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x238) = 8;
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x220) = (unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL;
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x228) = 1;
    v29 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180146228, word_1801248A2, 0, 0);
  }
  *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  memset_0((void *)(v4 + 96), 0, 0x1A0u);
  *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(
    v4 + 24,
    a2);
  try
  {
    wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(
      v4 + 24,
      v4 + 32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v4 + 40,
      0);
    GetCallerTokenFromComCall((PHANDLE)(v4 + 40));
    GetCallerInformationFromToken(
      *(HANDLE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
      (struct _BASIC_CALLER_INFORMATION *)(v4 + 96),
      0);
    if ( !*(_BYTE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) )
    {
      valid = IsValidCallerForUser(a2, (struct _BASIC_CALLER_INFORMATION *)(v4 + 96));
      if ( valid < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D2A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)valid,
          v29);
    }
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                   + 0x20)
                                                     + 88LL))(
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
      v4 + 64);
    Windows::System::Internal::GetDefaultSignedInAccount(
      v4 + 72,
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40));
    *(_OWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    if ( !memcmp_0((const void *)(v4 + 80), (const void *)(v4 + 48), 0x10u) )
    {
      v10 = *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
      v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v10 + 72LL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v12 = v11(v10, v4 + 16);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D35,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v12,
          v29);
      v13 = *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      DefaultLocalAccountPicture = Windows::System::Internal::GetDefaultLocalAccountPicture(
                                     v13,
                                     *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
                                     v4 + 8);
      if ( DefaultLocalAccountPicture < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D36,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)DefaultLocalAccountPicture,
          v29);
    }
    else if ( !memcmp_0((const void *)(v4 + 80), qword_180111500, 0x10u)
           || !memcmp_0((const void *)(v4 + 80), qword_1801114F0, 0x10u) )
    {
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v30
                                                                               & 0xFFFFFFFFFFFFFFE0uLL)
                                                                              + 0x20)
                                                                + 80LL))(
              *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
              v4 + 48);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D3B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v17,
          v29);
      if ( !ImpersonateLoggedOnUser(*(HANDLE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1D3C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          v18);
      *(_BYTE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 5) = 1;
      v19 = *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      DefaultSignedInAccountPicture = Windows::System::Internal::GetDefaultSignedInAccountPicture(
                                        v19,
                                        *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
                                        v4 + 8);
      if ( DefaultSignedInAccountPicture < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D3F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)DefaultSignedInAccountPicture,
          v29);
      RevertToSelf();
    }
    if ( (unsigned int)dword_180146228 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v15, v16) )
    {
      *(_BYTE *)v4 = 1;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0x1000000;
      *(_BYTE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 1;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x240) = (unsigned __int64)v30
                                                                           & 0xFFFFFFFFFFFFFFE0uLL;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x248) = 1;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x230) = ((unsigned __int64)v30
                                                                            & 0xFFFFFFFFFFFFFFE0uLL)
                                                                           + 48;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x238) = 8;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x220) = ((unsigned __int64)v30
                                                                            & 0xFFFFFFFFFFFFFFE0uLL)
                                                                           + 4;
      *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x228) = 1;
      v29 = 5;
      tlgWriteTransfer_EventWriteTransfer(&dword_180146228, &word_180124846, 0, 0);
    }
    v21 = *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    if ( v6 == 3 )
    {
      if ( v21 )
      {
        *a4 = v21;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      }
      else
      {
        *a4 = 0;
      }
    }
    else
    {
      v22 = Windows::System::Internal::ResizePicture(v21, v6, a4);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D4D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v22,
          v29);
    }
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v4 + 72);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v4 + 8);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v4 + 32);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v4 + 24);
    WindowsDeleteString(*(HSTRING *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
    *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v4 + 40);
    result = 0;
  }
  catch ( ... )
  {
    if ( (unsigned int)dword_180146228 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v24, v25) )
      {
        *(_DWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v23);
        *(_QWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0x1000000;
        *(_BYTE *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v26,
          (unsigned int)&unk_1801247F0,
          v27,
          v28,
          ((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 4,
          ((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 24,
          ((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      }
    }
    *(_DWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v23);
    return *(unsigned int *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
  }
  return result;
}

```

## disassembly

```asm
0x1800458e0  mov     [rsp-8+arg_0], rbx
0x1800458e5  push    rbp
0x1800458e6  push    rsi
0x1800458e7  push    rdi
0x1800458e8  push    r14
0x1800458ea  push    r15
0x1800458ec  sub     rsp, 2C0h
0x1800458f3  lea     rbp, [rsp+60h]
0x1800458f8  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800458fc  mov     rax, cs:__security_cookie
0x180045903  xor     rax, rsp
0x180045906  mov     [rbp+280h+var_30], rax
0x18004590d  mov     rsi, r9
0x180045910  mov     r14d, r8d
0x180045913  mov     rbx, rdx
0x180045916  xor     r15d, r15d
0x180045919  test    r9, r9
0x18004591c  jnz     short loc_180045928
0x18004591e  mov     eax, 80070057h
0x180045923  jmp     loc_180045CCD
0x180045928  mov     eax, cs:dword_180146228
0x18004592e  cmp     eax, 5
0x180045931  jbe     short loc_1800459B2
0x180045933  mov     rdx, 400000000000h
0x18004593d  lea     rcx, dword_180146228
0x180045944  call    _tlgKeywordOn
0x180045949  test    al, al
0x18004594b  jz      short loc_1800459B2
0x18004594d  mov     [rbp+280h+var_268], 1000000h
0x180045955  mov     [rbp+280h+var_280], 1
0x180045959  lea     rax, [rbp+280h+var_268]
0x18004595d  mov     [rbp+280h+var_50], rax
0x180045964  mov     [rbp+280h+var_48], 8
0x18004596f  lea     rax, [rbp+280h+var_280]
0x180045973  mov     [rbp+280h+var_60], rax
0x18004597a  mov     [rbp+280h+var_58], 1
0x180045985  lea     rax, [rbp+280h+var_80]
0x18004598c  mov     [rsp+2E0h+var_2B8], rax
0x180045991  mov     [rsp+2E0h+var_2C0], 4; int
0x180045999  xor     r9d, r9d
0x18004599c  xor     r8d, r8d
0x18004599f  lea     rdx, word_1801248A2
0x1800459a6  lea     rcx, dword_180146228
0x1800459ad  call    _tlgWriteTransfer_EventWriteTransfer
0x1800459b2  mov     [rbp+280h+ClientToken], r15
0x1800459b6  xor     edx, edx; Val
0x1800459b8  mov     r8d, 1A0h; Size
0x1800459be  lea     rcx, [rbp+280h+var_220]; void *
0x1800459c2  call    memset_0
0x1800459c7  mov     [rbp+280h+string], r15
0x1800459cb  mov     rdx, rbx
0x1800459ce  lea     rcx, [rbp+280h+var_268]
0x1800459d2  call    ??0?$com_ptr_t@UISignInContext@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUISignInContext@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(Windows::System::Internal::ISignInContext *)
0x1800459d7  nop
0x1800459d8  lea     rdx, [rbp+280h+var_260]
0x1800459dc  lea     rcx, [rbp+280h+var_268]
0x1800459e0  call    ??$query@UIUserInternal@Implementation@Internal@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserInternal@Implementation@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(void)
0x1800459e5  nop
0x1800459e6  xor     edx, edx
0x1800459e8  lea     rcx, [rbp+280h+ClientToken]
0x1800459ec  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800459f1  lea     rcx, [rbp+280h+ClientToken]; phNewToken
0x1800459f5  call    ?GetCallerTokenFromComCall@@YAJPEAPEAX@Z; GetCallerTokenFromComCall(void * *)
0x1800459fa  xor     r8d, r8d; struct _EXTENDED_CALLER_INFORMATION *
0x1800459fd  lea     rdx, [rbp+280h+var_220]; struct _BASIC_CALLER_INFORMATION *
0x180045a01  mov     rcx, [rbp+280h+ClientToken]; ClientToken
0x180045a05  call    ?GetCallerInformationFromToken@@YAJPEAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z; GetCallerInformationFromToken(void *,_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)
0x180045a0a  cmp     [rbp+280h+var_220], r15b
0x180045a0e  jnz     short loc_180045A2C
0x180045a10  lea     rdx, [rbp+280h+var_220]; struct _BASIC_CALLER_INFORMATION *
0x180045a14  mov     rcx, rbx; struct Windows::System::IUser *
0x180045a17  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180045a1c  mov     rcx, [rsp+2E8h]; this
0x180045a24  test    eax, eax
0x180045a26  js      loc_180045CF3
0x180045a2c  mov     [rbp+280h+var_278], r15
0x180045a30  mov     [rbp+280h+var_240], r15
0x180045a34  mov     rcx, [rbp+280h+var_260]
0x180045a38  mov     rax, [rcx]
0x180045a3b  lea     rdx, [rbp+280h+var_240]
0x180045a3f  mov     rax, [rax+58h]
0x180045a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a48  mov     rdx, [rbp+280h+var_240]
0x180045a4c  lea     rcx, [rbp+280h+var_238]
0x180045a50  call    ?GetDefaultSignedInAccount@Internal@System@Windows@@YA?AU?$pair@V?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@U_GUID@@@std@@_K@Z; Windows::System::Internal::GetDefaultSignedInAccount(unsigned __int64)
0x180045a55  nop
0x180045a56  xorps   xmm0, xmm0
0x180045a59  movups  [rbp+280h+Buf2], xmm0
0x180045a5d  mov     ebx, 10h
0x180045a62  mov     r8d, ebx; Size
0x180045a65  lea     rdx, [rbp+280h+Buf2]; Buf2
0x180045a69  lea     rcx, [rbp+280h+Buf1]; Buf1
0x180045a6d  call    memcmp_0
0x180045a72  test    eax, eax
0x180045a74  jnz     short loc_180045AEA
0x180045a76  mov     rdi, [rbp+280h+var_260]
0x180045a7a  mov     rax, [rdi]
0x180045a7d  mov     rbx, [rax+48h]
0x180045a81  mov     rcx, [rbp+280h+string]; string
0x180045a85  call    cs:__imp_WindowsDeleteString
0x180045a8b  mov     [rbp+280h+string], r15
0x180045a8f  lea     rdx, [rbp+280h+string]
0x180045a93  mov     rcx, rdi
0x180045a96  mov     rax, rbx
0x180045a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a9e  mov     rcx, [rsp+2E8h]; this
0x180045aa6  test    eax, eax
0x180045aa8  js      loc_180045D08
0x180045aae  mov     rcx, [rbp+280h+var_278]
0x180045ab2  mov     [rbp+280h+var_278], r15
0x180045ab6  test    rcx, rcx
0x180045ab9  jz      short loc_180045AC8
0x180045abb  mov     rax, [rcx]
0x180045abe  mov     rax, [rax+10h]
0x180045ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ac7  nop
0x180045ac8  lea     r8, [rbp+280h+var_278]
0x180045acc  mov     rdx, [rbp+280h+string]
0x180045ad0  call    ?GetDefaultLocalAccountPicture@Internal@System@Windows@@YAJW4UserPictureSize@23@PEAUHSTRING__@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::System::Internal::GetDefaultLocalAccountPicture(Windows::System::UserPictureSize,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180045ad5  mov     rcx, [rsp+2E8h]; this
0x180045add  test    eax, eax
0x180045adf  js      loc_180045D1C
0x180045ae5  jmp     loc_180045B9F
0x180045aea  mov     r8, rbx; Size
0x180045aed  lea     rdx, qword_180111500; Buf2
0x180045af4  lea     rcx, [rbp+280h+Buf1]; Buf1
0x180045af8  call    memcmp_0
0x180045afd  test    eax, eax
0x180045aff  jz      short loc_180045B1C
0x180045b01  mov     r8, rbx; Size
0x180045b04  lea     rdx, qword_1801114F0; Buf2
0x180045b0b  lea     rcx, [rbp+280h+Buf1]; Buf1
0x180045b0f  call    memcmp_0
0x180045b14  test    eax, eax
0x180045b16  jnz     loc_180045B9F
0x180045b1c  mov     qword ptr [rbp+280h+Buf2], r15
0x180045b20  mov     rcx, [rbp+280h+var_260]
0x180045b24  mov     rax, [rcx]
0x180045b27  lea     rdx, [rbp+280h+Buf2]
0x180045b2b  mov     rax, [rax+50h]
0x180045b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b34  mov     rcx, [rsp+2E8h]; this
0x180045b3c  test    eax, eax
0x180045b3e  js      loc_180045D30
0x180045b44  mov     rcx, qword ptr [rbp+280h+Buf2]; hToken
0x180045b48  call    cs:__imp_ImpersonateLoggedOnUser
0x180045b4e  mov     rcx, [rsp+2E8h]; this
0x180045b56  test    eax, eax
0x180045b58  jz      loc_180045D44
0x180045b5e  mov     [rbp+280h+var_27B], 1
0x180045b62  mov     rcx, [rbp+280h+var_278]
0x180045b66  mov     [rbp+280h+var_278], r15
0x180045b6a  test    rcx, rcx
0x180045b6d  jz      short loc_180045B7C
0x180045b6f  mov     rax, [rcx]
0x180045b72  mov     rax, [rax+10h]
0x180045b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b7b  nop
0x180045b7c  lea     r8, [rbp+280h+var_278]
0x180045b80  mov     rdx, [rbp+280h+var_238]
0x180045b84  call    ?GetDefaultSignedInAccountPicture@Internal@System@Windows@@YAJW4UserPictureSize@23@PEAUIWebAccount@Credentials@Security@3@PEAPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::System::Internal::GetDefaultSignedInAccountPicture(Windows::System::UserPictureSize,Windows::Security::Credentials::IWebAccount *,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180045b89  mov     rcx, [rsp+2E8h]; this
0x180045b91  test    eax, eax
0x180045b93  js      loc_180045D56
0x180045b99  call    cs:__imp_RevertToSelf
0x180045b9f  mov     eax, cs:dword_180146228
0x180045ba5  cmp     eax, 5
0x180045ba8  jbe     loc_180045C47
0x180045bae  mov     rdx, 400000000000h
0x180045bb8  lea     rcx, dword_180146228
0x180045bbf  call    _tlgKeywordOn
0x180045bc4  test    al, al
0x180045bc6  jz      short loc_180045C47
0x180045bc8  mov     [rbp+280h+var_280], 1
0x180045bcc  mov     qword ptr [rbp+280h+Buf2], 1000000h
0x180045bd4  mov     [rbp+280h+var_27C], 1
0x180045bd8  lea     rax, [rbp+280h+var_280]
0x180045bdc  mov     [rbp+280h+var_40], rax
0x180045be3  mov     [rbp+280h+var_38], 1
0x180045bee  lea     rax, [rbp+280h+Buf2]
0x180045bf2  mov     [rbp+280h+var_50], rax
0x180045bf9  mov     [rbp+280h+var_48], 8
0x180045c04  lea     rax, [rbp+280h+var_27C]
0x180045c08  mov     [rbp+280h+var_60], rax
0x180045c0f  mov     [rbp+280h+var_58], 1
0x180045c1a  lea     rax, [rbp+280h+var_80]
0x180045c21  mov     [rsp+2E0h+var_2B8], rax
0x180045c26  mov     [rsp+2E0h+var_2C0], 5; int
0x180045c2e  xor     r9d, r9d
0x180045c31  xor     r8d, r8d
0x180045c34  lea     rdx, word_180124846
0x180045c3b  lea     rcx, dword_180146228
0x180045c42  call    _tlgWriteTransfer_EventWriteTransfer
0x180045c47  mov     rcx, [rbp+280h+var_278]
0x180045c4b  cmp     r14d, 3
0x180045c4f  jz      short loc_180045C6E
0x180045c51  mov     r8, rsi
0x180045c54  mov     edx, r14d
0x180045c57  call    ?ResizePicture@Internal@System@Windows@@YAJPEAUIRandomAccessStreamReference@Streams@Storage@3@W4UserPictureSize@23@PEAPEAU4563@@Z; Windows::System::Internal::ResizePicture(Windows::Storage::Streams::IRandomAccessStreamReference *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180045c5c  mov     rcx, [rsp+2E8h]; this
0x180045c64  test    eax, eax
0x180045c66  js      loc_180045D6B
0x180045c6c  jmp     short loc_180045C87
0x180045c6e  test    rcx, rcx
0x180045c71  jz      short loc_180045C84
0x180045c73  mov     [rsi], rcx
0x180045c76  mov     rax, [rcx]
0x180045c79  mov     rax, [rax+8]
0x180045c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c82  jmp     short loc_180045C87
0x180045c84  mov     [rsi], r15
0x180045c87  lea     rcx, [rbp+280h+var_238]
0x180045c8b  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180045c90  nop
0x180045c91  lea     rcx, [rbp+280h+var_278]
0x180045c95  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180045c9a  nop
0x180045c9b  lea     rcx, [rbp+280h+var_260]
0x180045c9f  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180045ca4  nop
0x180045ca5  lea     rcx, [rbp+280h+var_268]
0x180045ca9  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180045cae  nop
0x180045caf  mov     rcx, [rbp+280h+string]; string
0x180045cb3  call    cs:__imp_WindowsDeleteString
0x180045cb9  mov     [rbp+280h+string], r15
0x180045cbd  lea     rcx, [rbp+280h+ClientToken]
0x180045cc1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180045cc6  xor     eax, eax
0x180045cc8  jmp     short loc_180045CCD
0x180045cca  mov     eax, dword ptr [rbp+280h+var_278]
0x180045ccd  mov     rcx, [rbp+280h+var_30]
0x180045cd4  xor     rcx, rsp; StackCookie
0x180045cd7  call    __security_check_cookie
0x180045cdc  mov     rbx, [rsp+2E0h+arg_0]
0x180045ce4  add     rsp, 2C0h
0x180045ceb  pop     r15
0x180045ced  pop     r14
0x180045cef  pop     rdi
0x180045cf0  pop     rsi
0x180045cf1  pop     rbp
0x180045cf2  retn
0x180045cf3  mov     r9d, eax; char *
0x180045cf6  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045cfd  mov     edx, 1D2Ah; void *
0x180045d02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d08  mov     r9d, eax; char *
0x180045d0b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d12  mov     edx, 1D35h; void *
0x180045d17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d1c  mov     r9d, eax; char *
0x180045d1f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d26  mov     edx, 1D36h; void *
0x180045d2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d30  mov     r9d, eax; char *
0x180045d33  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d3a  mov     edx, 1D3Bh; void *
0x180045d3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d44  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d4b  mov     edx, 1D3Ch; void *
0x180045d50  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180045d56  mov     r9d, eax; char *
0x180045d59  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d60  mov     edx, 1D3Fh; void *
0x180045d65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045d6b  mov     r9d, eax; char *
0x180045d6e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180045d75  mov     edx, 1D4Dh; void *
0x180045d7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
