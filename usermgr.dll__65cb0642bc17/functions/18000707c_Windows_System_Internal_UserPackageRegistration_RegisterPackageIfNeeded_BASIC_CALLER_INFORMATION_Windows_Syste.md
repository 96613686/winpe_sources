# Windows::System::Internal::UserPackageRegistration::RegisterPackageIfNeeded(_BASIC_CALLER_INFORMATION *,Windows::System::IUser *)

- ea: `0x18000707c`
- end: `0x1800076ea`
- name: `?RegisterPackageIfNeeded@UserPackageRegistration@Internal@System@Windows@@QEAAJPEAU_BASIC_CALLER_INFORMATION@@PEAUIUser@34@@Z`
- size: `1646`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserPackageRegistration *__hidden this, struct _BASIC_CALLER_INFORMATION *, struct Windows::System::IUser *)`
- caller_count: `9`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006ff0`
- `0x180048230`
- `0x180065560`
- `0x180065730`
- `0x180069a44`
- `0x180069d4c`
- `0x1800bb6d0`
- `0x1800bb7c0`
- `0x1800bb9d0`

## callees

- `0x1800062e4`
- `0x18000707c`
- `0x1800076f0`
- `0x180007950`
- `0x1800088e8`
- `0x18000ce48`
- `0x1800154b0`
- `0x1800181f0`
- `0x1800189b0`
- `0x1800356f8`
- `0x18004bfa0`
- `0x18004c378`
- `0x180067140`
- `0x1800d8eb0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007216`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007127`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007206`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800076e3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007206`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800076e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007297`

## string_xrefs

- `0x180007330`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x180007377`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x1800073e3`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x18000743d`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x180007484`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x1800074e1`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x18000753e`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x180007585`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::System::Internal::UserPackageRegistration::RegisterPackageIfNeeded(
        Windows::System::Internal::UserPackageRegistration *this,
        struct _BASIC_CALLER_INFORMATION *a2,
        struct Windows::System::IUser *a3)
{
  struct Windows::System::IUser *v3; // r13
  struct _BASIC_CALLER_INFORMATION *v4; // rdi
  Windows::System::Internal::UserPackageRegistration *v5; // r14
  int HasRegisterPackageIfNeededSucceededForUser; // eax
  unsigned int v7; // ebx
  RTL_SRWLOCK *v8; // r15
  __int64 v9; // r8
  const WCHAR *v10; // r12
  int v11; // eax
  __int64 v12; // r8
  const char *v13; // r9
  int v14; // eax
  __int64 *v15; // rdi
  __int64 v16; // r13
  unsigned __int64 v17; // rbx
  unsigned int v19; // eax
  UINT32 v20; // edx
  HRESULT v21; // eax
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r8
  char v32; // al
  unsigned __int16 **v33; // r8
  int AppIdFromProcessId; // eax
  int v35; // eax
  Windows::System::Internal::UserPackageRegistration *v36; // rdi
  __int64 (__fastcall *v37)(Windows::System::Internal::UserPackageRegistration *, PVOID, char *); // rbx
  HSTRING_HEADER *v38; // rax
  int v39; // eax
  int v40; // [rsp+20h] [rbp-F8h]
  int v41; // [rsp+20h] [rbp-F8h]
  int v42; // [rsp+20h] [rbp-F8h]
  int v43; // [rsp+20h] [rbp-F8h]
  int v44; // [rsp+20h] [rbp-F8h]
  int v45; // [rsp+20h] [rbp-F8h]
  int v46; // [rsp+20h] [rbp-F8h]
  int v47; // [rsp+20h] [rbp-F8h]
  int v48; // [rsp+20h] [rbp-F8h]
  bool v49; // [rsp+30h] [rbp-E8h] BYREF
  char v50[3]; // [rsp+31h] [rbp-E7h] BYREF
  unsigned int v51; // [rsp+34h] [rbp-E4h] BYREF
  char v52; // [rsp+38h] [rbp-E0h] BYREF
  char v53; // [rsp+39h] [rbp-DFh]
  unsigned int v54[2]; // [rsp+40h] [rbp-D8h] BYREF
  Windows::System::Internal::UserPackageRegistration *v55; // [rsp+48h] [rbp-D0h] BYREF
  const WCHAR *v56[2]; // [rsp+50h] [rbp-C8h] BYREF
  Windows::System::Internal::UserPackageRegistration *v57; // [rsp+60h] [rbp-B8h]
  const WCHAR *v58; // [rsp+68h] [rbp-B0h] BYREF
  char *v59; // [rsp+70h] [rbp-A8h] BYREF
  struct _BASIC_CALLER_INFORMATION *v60; // [rsp+78h] [rbp-A0h]
  struct Windows::System::IUser *v61; // [rsp+80h] [rbp-98h]
  RTL_SRWLOCK *v62; // [rsp+88h] [rbp-90h]
  bool *v63; // [rsp+90h] [rbp-88h]
  Windows::System::Internal::UserPackageRegistration *v64; // [rsp+98h] [rbp-80h]
  unsigned int *v65; // [rsp+A0h] [rbp-78h]
  char v66; // [rsp+A8h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-68h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v57 = this;
  v55 = this;
  v5 = this;
  v60 = a2;
  v61 = a3;
  v59 = 0;
  v49 = 0;
  v51 = 0;
  v63 = &v49;
  v64 = this;
  v65 = &v51;
  v66 = 1;
  HasRegisterPackageIfNeededSucceededForUser = Windows::System::Internal::UserPackageRegistration::HasRegisterPackageIfNeededSucceededForUser(
                                                 this,
                                                 a3,
                                                 &v49,
                                                 &v51);
  v7 = HasRegisterPackageIfNeededSucceededForUser;
  if ( HasRegisterPackageIfNeededSucceededForUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
      (const char *)(unsigned int)HasRegisterPackageIfNeededSucceededForUser,
      v40);
    if ( !v49 )
    {
      LOBYTE(v41) = byte_1801481E9;
      std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
        (char *)v5 + 24,
        v56,
        v24,
        &v51,
        v41);
    }
    return v7;
  }
  if ( v49 )
    return 0;
  v8 = (RTL_SRWLOCK *)((char *)v5 + 40);
  v62 = (RTL_SRWLOCK *)((char *)v5 + 40);
  AcquireSRWLockExclusive((PSRWLOCK)v5 + 5);
  v59 = (char *)v5 + 40;
  v10 = (const WCHAR *)((char *)v4 + 132);
  v56[0] = (const WCHAR *)((char *)v4 + 132);
  if ( v4 == (struct _BASIC_CALLER_INFORMATION *)-132LL || !*v10 )
  {
    if ( !v49 )
      std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
        (char *)v5 + 24,
        v56,
        v9,
        &v51,
        byte_1801481E9);
  }
  else
  {
    v52 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v5 + 2) + 280LL))(*((_QWORD *)v5 + 2), &v52);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
        (const char *)(unsigned int)v11,
        v40);
      if ( !v49 )
      {
        LOBYTE(v44) = byte_1801481E9;
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
          (char *)v5 + 24,
          v56,
          v27,
          &v51,
          v44);
      }
      goto LABEL_36;
    }
    if ( v52 )
    {
      v50[0] = 1;
      v53 = 0;
      try
      {
        v32 = Windows::System::Internal::WCOS::IsResourceAccount<Windows::System::IUser *>(v3);
        v53 = v32;
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
          v13);
        v32 = v53;
        v57 = v55;
        v5 = v55;
        v4 = v60;
        v3 = v61;
        v8 = v62;
        v10 = v56[0];
      }
      if ( v32 && *((_BYTE *)v4 + 1) )
      {
        v50[0] = 0;
        *(_QWORD *)v54 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          v54,
          0);
        AppIdFromProcessId = CallerIdentity::GetAppIdFromProcessId(*((_DWORD *)v4 + 1), (unsigned int)v54, v33);
        v7 = AppIdFromProcessId;
        if ( AppIdFromProcessId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
            (const char *)(unsigned int)AppIdFromProcessId,
            v40);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v54);
          if ( !v49 )
          {
            LOBYTE(v42) = byte_1801481E9;
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
              (char *)v5 + 24,
              v56,
              v25,
              &v51,
              v42);
          }
          goto LABEL_36;
        }
        v55 = 0;
        string = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Microsoft.ResourceAccountManager.ResourceAccountPolicy",
          0x37u,
          0x36u);
        v35 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Microsoft::ResourceAccountManager::IResourceAccountPolicy>>(
                (__int64)string,
                &v55);
        v7 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
            (const char *)(unsigned int)v35,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v54);
          if ( !v49 )
          {
            LOBYTE(v45) = byte_1801481E9;
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
              (char *)v5 + 24,
              v56,
              v28,
              &v51,
              v45);
          }
          goto LABEL_36;
        }
        v36 = v55;
        v37 = *(__int64 (__fastcall **)(Windows::System::Internal::UserPackageRegistration *, PVOID, char *))(*(_QWORD *)v55 + 48LL);
        v56[0] = *(const WCHAR **)v54;
        v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v56);
        v39 = v37(v36, v38[1].Reserved.Reserved1, v50);
        v7 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
            (const char *)(unsigned int)v39,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v54);
          if ( !v49 )
          {
            LOBYTE(v46) = byte_1801481E9;
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
              (char *)v5 + 24,
              v56,
              v29,
              &v51,
              v46);
          }
LABEL_36:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v59);
          return v7;
        }
        if ( !v50[0] )
        {
          v7 = -2147009290;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
            (const char *)0x80073CF6LL,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v54);
          if ( !v49 )
          {
            LOBYTE(v43) = byte_1801481E9;
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
              (char *)v5 + 24,
              v56,
              v26,
              &v51,
              v43);
          }
          goto LABEL_36;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v54);
      }
      v58 = 0;
      v14 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::System::IUser *, const WCHAR **))(**((_QWORD **)v5 + 1)
                                                                                               + 136LL))(
              *((_QWORD *)v5 + 1),
              v3,
              &v58);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
          (const char *)(unsigned int)v14,
          v40);
        if ( !v49 )
        {
          LOBYTE(v47) = byte_1801481E9;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
            (char *)v5 + 24,
            v56,
            v30,
            &v51,
            v47);
        }
        goto LABEL_36;
      }
      v15 = *(__int64 **)v57;
      v16 = **(_QWORD **)v57;
      string = 0;
      v17 = -1;
      do
        ++v17;
      while ( v10[v17] );
      if ( v17 > 0xFFFFFFFF )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        return 0;
      }
      v56[0] = v58;
      v19 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
      v20 = v19 - 1;
      if ( (unsigned int)v17 >= v19 )
        goto LABEL_22;
      while ( 1 )
      {
        v20 = v17;
LABEL_22:
        v21 = WindowsCreateStringReference(v10, v20, &hstringHeader, &string);
        if ( v21 >= 0 )
          break;
        RaiseException(v21, 1u, 0, 0);
      }
      v22 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, const WCHAR *))(v16 + 408))(v15, string, v56[0]);
      v7 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userpackageregistration.cpp",
          (const char *)(unsigned int)v22,
          v40);
        if ( !v49 )
        {
          LOBYTE(v48) = byte_1801481E9;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
            (char *)v5 + 24,
            v56,
            v31,
            &v51,
            v48);
        }
        goto LABEL_36;
      }
      if ( !v49 )
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
          (char *)v5 + 24,
          v56,
          v23,
          &v51,
          byte_1801481E9);
    }
    else if ( !v49 )
    {
      std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int const &,std::_Nil>(
        (char *)v5 + 24,
        v56,
        v12,
        &v51,
        byte_1801481E9);
    }
  }
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return 0;
}

```

## disassembly

```asm
0x18000707c  mov     r11, rsp
0x18000707f  push    rbx
0x180007080  push    rsi
0x180007081  push    rdi
0x180007082  push    r12
0x180007084  push    r13
0x180007086  push    r14
0x180007088  push    r15
0x18000708a  sub     rsp, 0E0h
0x180007091  mov     rax, cs:__security_cookie
0x180007098  xor     rax, rsp
0x18000709b  mov     [rsp+118h+var_48], rax
0x1800070a3  mov     r13, r8
0x1800070a6  mov     rdi, rdx
0x1800070a9  mov     [rsp+118h+var_B8], rcx
0x1800070ae  mov     [rsp+118h+var_D0], rcx
0x1800070b3  mov     r14, rcx
0x1800070b6  mov     [rsp+118h+var_A0], rdx
0x1800070bb  mov     [rsp+118h+var_98], r8
0x1800070c3  xor     esi, esi
0x1800070c5  mov     [rsp+118h+var_A8], rsi
0x1800070ca  mov     [rsp+118h+var_E8], sil
0x1800070cf  mov     [rsp+118h+var_E4], esi
0x1800070d3  lea     rax, [rsp+118h+var_E8]
0x1800070d8  mov     [r11-88h], rax
0x1800070df  mov     [r11-80h], rcx
0x1800070e3  lea     rax, [rsp+118h+var_E4]
0x1800070e8  mov     [r11-78h], rax
0x1800070ec  mov     byte ptr [r11-70h], 1
0x1800070f1  lea     r9, [rsp+118h+var_E4]; unsigned int *
0x1800070f6  lea     r8, [rsp+118h+var_E8]; bool *
0x1800070fb  mov     rdx, r13; struct Windows::System::IUser *
0x1800070fe  call    ?HasRegisterPackageIfNeededSucceededForUser@UserPackageRegistration@Internal@System@Windows@@QEAAJPEAUIUser@34@PEA_NPEAI@Z; Windows::System::Internal::UserPackageRegistration::HasRegisterPackageIfNeededSucceededForUser(Windows::System::IUser *,bool *,uint *)
0x180007103  mov     ebx, eax
0x180007105  test    eax, eax
0x180007107  js      loc_180007325
0x18000710d  cmp     [rsp+118h+var_E8], sil
0x180007112  jnz     loc_18000720D
0x180007118  lea     r15, [r14+28h]
0x18000711c  mov     [rsp+118h+var_90], r15
0x180007124  mov     rcx, r15; SRWLock
0x180007127  call    cs:__imp_AcquireSRWLockExclusive
0x18000712d  mov     [rsp+118h+var_A8], r15
0x180007132  lea     r12, [rdi+84h]
0x180007139  mov     [rsp+118h+var_C8], r12
0x18000713e  test    r12, r12
0x180007141  jz      loc_180007241
0x180007147  cmp     [r12], si
0x18000714c  jz      loc_180007241
0x180007152  mov     [rsp+118h+var_E0], sil
0x180007157  mov     rcx, [r14+10h]
0x18000715b  mov     rax, [rcx]
0x18000715e  lea     rdx, [rsp+118h+var_E0]
0x180007163  mov     rax, [rax+118h]
0x18000716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000716f  mov     ebx, eax
0x180007171  test    eax, eax
0x180007173  js      loc_180007432
0x180007179  cmp     [rsp+118h+var_E0], sil
0x18000717e  jz      loc_1800072FE
0x180007184  mov     [rsp+118h+var_E7], 1
0x180007189  mov     [rsp+118h+var_DF], sil
0x18000718e  mov     rcx, r13
0x180007191  call    ??$IsResourceAccount@PEAUIUser@System@Windows@@@WCOS@Internal@System@Windows@@YA_NPEAUIUser@23@@Z; Windows::System::Internal::WCOS::IsResourceAccount<Windows::System::IUser *>(Windows::System::IUser *)
0x180007196  mov     [rsp+118h+var_DF], al
0x18000719a  test    al, al
0x18000719c  jnz     loc_1800075F3
0x1800071a2  mov     [rsp+118h+var_B0], rsi
0x1800071a7  mov     rcx, [r14+8]
0x1800071ab  mov     rax, [rcx]
0x1800071ae  lea     r8, [rsp+118h+var_B0]
0x1800071b3  mov     rdx, r13
0x1800071b6  mov     rax, [rax+88h]
0x1800071bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c2  mov     ebx, eax
0x1800071c4  test    eax, eax
0x1800071c6  js      loc_180007533
0x1800071cc  mov     rdi, [rsp+118h+var_B8]
0x1800071d1  mov     rdi, [rdi]
0x1800071d4  mov     r13, [rdi]
0x1800071d7  mov     [rsp+118h+string], rsi
0x1800071df  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800071e3  inc     rbx
0x1800071e6  cmp     [r12+rbx*2], si
0x1800071eb  jnz     short loc_1800071E3
0x1800071ed  mov     eax, 0FFFFFFFFh
0x1800071f2  cmp     rbx, rax
0x1800071f5  jbe     short loc_18000726B
0x1800071f7  xor     r9d, r9d; lpArguments
0x1800071fa  xor     r8d, r8d; nNumberOfArguments
0x1800071fd  lea     edx, [r9+1]; dwExceptionFlags
0x180007201  mov     ecx, 80070216h; dwExceptionCode
0x180007206  call    cs:__imp_RaiseException
0x18000720c  nop
0x18000720d  mov     ebx, esi
0x18000720f  mov     eax, ebx
0x180007211  jmp     short loc_18000721E
0x180007213  mov     rcx, r15; SRWLock
0x180007216  call    cs:__imp_ReleaseSRWLockExclusive
0x18000721c  xor     eax, eax
0x18000721e  mov     rcx, [rsp+118h+var_48]
0x180007226  xor     rcx, rsp; StackCookie
0x180007229  call    __security_check_cookie
0x18000722e  add     rsp, 0E0h
0x180007235  pop     r15
0x180007237  pop     r14
0x180007239  pop     r13
0x18000723b  pop     r12
0x18000723d  pop     rdi
0x18000723e  pop     rsi
0x18000723f  pop     rbx
0x180007240  retn
0x180007241  cmp     [rsp+118h+var_E8], sil
0x180007246  jnz     short loc_180007266
0x180007248  lea     rcx, [r14+18h]
0x18000724c  mov     al, cs:byte_1801481E9
0x180007252  mov     byte ptr [rsp+118h+var_F8], al
0x180007256  lea     r9, [rsp+118h+var_E4]
0x18000725b  lea     rdx, [rsp+118h+var_C8]
0x180007260  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x180007265  nop
0x180007266  jmp     loc_1800072F0
0x18000726b  mov     rax, [rsp+118h+var_B0]
0x180007270  mov     [rsp+118h+var_C8], rax
0x180007275  mov     ecx, ebx; unsigned int
0x180007277  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000727c  lea     edx, [rax-1]
0x18000727f  cmp     ebx, eax
0x180007281  cmovb   edx, ebx; length
0x180007284  lea     r9, [rsp+118h+string]; string
0x18000728c  lea     r8, [rsp+118h+hstringHeader]; hstringHeader
0x180007294  mov     rcx, r12; sourceString
0x180007297  call    cs:__imp_WindowsCreateStringReference
0x18000729d  test    eax, eax
0x18000729f  js      loc_1800076D7
0x1800072a5  mov     r8, [rsp+118h+var_C8]
0x1800072aa  mov     rdx, [rsp+118h+string]
0x1800072b2  mov     rcx, rdi
0x1800072b5  mov     rax, [r13+198h]
0x1800072bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c1  mov     ebx, eax
0x1800072c3  test    eax, eax
0x1800072c5  js      loc_18000757A
0x1800072cb  cmp     [rsp+118h+var_E8], sil
0x1800072d0  jnz     short loc_1800072F0
0x1800072d2  lea     rcx, [r14+18h]
0x1800072d6  mov     al, cs:byte_1801481E9
0x1800072dc  mov     byte ptr [rsp+118h+var_F8], al
0x1800072e0  lea     r9, [rsp+118h+var_E4]
0x1800072e5  lea     rdx, [rsp+118h+var_C8]
0x1800072ea  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x1800072ef  nop
0x1800072f0  test    r15, r15
0x1800072f3  jz      loc_18000721C
0x1800072f9  jmp     loc_180007213
0x1800072fe  cmp     [rsp+118h+var_E8], sil
0x180007303  jnz     short loc_180007323
0x180007305  lea     rcx, [r14+18h]
0x180007309  mov     al, cs:byte_1801481E9
0x18000730f  mov     byte ptr [rsp+118h+var_F8], al
0x180007313  lea     r9, [rsp+118h+var_E4]
0x180007318  lea     rdx, [rsp+118h+var_C8]
0x18000731d  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x180007322  nop
0x180007323  jmp     short loc_1800072F0
0x180007325  mov     rcx, [rsp+118h]; this
0x18000732d  mov     r9d, eax; char *
0x180007330  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x180007337  mov     edx, 3Eh ; '>'; void *
0x18000733c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007341  nop
0x180007342  cmp     [rsp+118h+var_E8], sil
0x180007347  jnz     short loc_180007367
0x180007349  lea     rcx, [r14+18h]
0x18000734d  mov     al, cs:byte_1801481E9
0x180007353  mov     byte ptr [rsp+118h+var_F8], al
0x180007357  lea     r9, [rsp+118h+var_E4]
0x18000735c  lea     rdx, [rsp+118h+var_C8]
0x180007361  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x180007366  nop
0x180007367  jmp     loc_18000720F
0x18000736c  mov     rcx, [rsp+118h]; this
0x180007374  mov     r9d, eax; char *
0x180007377  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x18000737e  mov     edx, 5Eh ; '^'; void *
0x180007383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007388  nop
0x180007389  lea     rcx, [rsp+118h+var_D8]
0x18000738e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007393  nop
0x180007394  cmp     [rsp+118h+var_E8], sil
0x180007399  jnz     short loc_1800073B9
0x18000739b  lea     rcx, [r14+18h]
0x18000739f  mov     al, cs:byte_1801481E9
0x1800073a5  mov     byte ptr [rsp+118h+var_F8], al
0x1800073a9  lea     r9, [rsp+118h+var_E4]
0x1800073ae  lea     rdx, [rsp+118h+var_C8]
0x1800073b3  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x1800073b8  nop
0x1800073b9  lea     rcx, [rsp+118h+var_A8]
0x1800073be  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800073c3  jmp     loc_18000720F
0x1800073c8  cmp     [rsp+118h+var_E7], sil
0x1800073cd  jnz     loc_1800076BD
0x1800073d3  mov     rcx, [rsp+118h]; this
0x1800073db  mov     ebx, 80073CF6h
0x1800073e0  mov     r9d, ebx; char *
0x1800073e3  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x1800073ea  mov     edx, 62h ; 'b'; void *
0x1800073ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073f4  nop
0x1800073f5  lea     rcx, [rsp+118h+var_D0]
0x1800073fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800073ff  nop
0x180007400  lea     rcx, [rsp+118h+var_D8]
0x180007405  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000740a  nop
0x18000740b  cmp     [rsp+118h+var_E8], sil
0x180007410  jnz     short loc_180007430
0x180007412  lea     rcx, [r14+18h]
0x180007416  mov     al, cs:byte_1801481E9
0x18000741c  mov     byte ptr [rsp+118h+var_F8], al
0x180007420  lea     r9, [rsp+118h+var_E4]
0x180007425  lea     rdx, [rsp+118h+var_C8]
0x18000742a  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x18000742f  nop
0x180007430  jmp     short loc_1800073B9
0x180007432  mov     rcx, [rsp+118h]; this
0x18000743a  mov     r9d, eax; char *
0x18000743d  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x180007444  mov     edx, 4Ch ; 'L'; void *
0x180007449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000744e  nop
0x18000744f  cmp     [rsp+118h+var_E8], sil
0x180007454  jnz     short loc_180007474
0x180007456  lea     rcx, [r14+18h]
0x18000745a  mov     al, cs:byte_1801481E9
0x180007460  mov     byte ptr [rsp+118h+var_F8], al
0x180007464  lea     r9, [rsp+118h+var_E4]
0x180007469  lea     rdx, [rsp+118h+var_C8]
0x18000746e  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x180007473  nop
0x180007474  jmp     loc_1800073B9
0x180007479  mov     rcx, [rsp+118h]; this
0x180007481  mov     r9d, eax; char *
0x180007484  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x18000748b  mov     edx, 60h ; '`'; void *
0x180007490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007495  nop
0x180007496  lea     rcx, [rsp+118h+var_D0]
0x18000749b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074a0  nop
0x1800074a1  lea     rcx, [rsp+118h+var_D8]
0x1800074a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800074ab  nop
0x1800074ac  cmp     [rsp+118h+var_E8], sil
0x1800074b1  jnz     short loc_1800074D1
0x1800074b3  lea     rcx, [r14+18h]
0x1800074b7  mov     al, cs:byte_1801481E9
0x1800074bd  mov     byte ptr [rsp+118h+var_F8], al
0x1800074c1  lea     r9, [rsp+118h+var_E4]
0x1800074c6  lea     rdx, [rsp+118h+var_C8]
0x1800074cb  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x1800074d0  nop
0x1800074d1  jmp     loc_1800073B9
0x1800074d6  mov     rcx, [rsp+118h]; this
0x1800074de  mov     r9d, eax; char *
0x1800074e1  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x1800074e8  mov     edx, 61h ; 'a'; void *
0x1800074ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074f2  nop
0x1800074f3  lea     rcx, [rsp+118h+var_D0]
0x1800074f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074fd  nop
0x1800074fe  lea     rcx, [rsp+118h+var_D8]
0x180007503  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007508  nop
0x180007509  cmp     [rsp+118h+var_E8], sil
0x18000750e  jnz     short loc_18000752E
0x180007510  lea     rcx, [r14+18h]
0x180007514  mov     al, cs:byte_1801481E9
0x18000751a  mov     byte ptr [rsp+118h+var_F8], al
0x18000751e  lea     r9, [rsp+118h+var_E4]
0x180007523  lea     rdx, [rsp+118h+var_C8]
0x180007528  call    ??$_Insert_nohint@AEBIU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_NAEBIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint const &,std::_Nil>(bool,uint const &,std::_Nil)
0x18000752d  nop
0x18000752e  jmp     loc_1800073B9
0x180007533  mov     rcx, [rsp+118h]; this
0x18000753b  mov     r9d, eax; char *
0x18000753e  lea     r8, aOnecoreDsSecur_56; "onecore\\ds\\security\\umstartup\\userm"...
0x180007545  mov     edx, 66h ; 'f'; void *
0x18000754a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000754f  nop
0x180007550  cmp     [rsp+118h+var_E8], sil
0x180007555  jnz     short loc_180007575
0x180007557  lea     rcx, [r14+18h]
0x18000755b  mov     al, cs:byte_1801481E9
0x180007561  mov     byte ptr [rsp+118h+var_F8], al
0x180007565  lea     r9, [rsp+118h+var_E4]
0x18000756a  lea     rdx, [rsp+118h+var_C8]
  ... truncated ...
```
