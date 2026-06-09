# Windows::System::UserStatics::FindUserInMaps(std::function<long (std::pair<uint,ulong>,Windows::System::IUser *,uchar *)>,Windows::System::IUser * *)

- ea: `0x180042b80`
- end: `0x18004302e`
- name: `?FindUserInMaps@UserStatics@System@Windows@@EEAAJV?$function@$$A6AJU?$pair@IK@std@@PEAUIUser@System@Windows@@PEAE@Z@std@@PEAPEAUIUser@23@@Z`
- size: `1198`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008630`
- `0x180009af0`
- `0x18000acdc`
- `0x180012890`
- `0x180015250`
- `0x180015800`
- `0x180017970`
- `0x1800179c0`
- `0x180019600`
- `0x180024828`
- `0x180037e98`
- `0x18003b578`
- `0x180042b80`
- `0x18004a338`
- `0x180076818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042be5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042be5`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180042c51`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180042c51`

## string_xrefs

- `0x180042f79`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042f8e`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042fa2`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042fb7`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042fcb`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042fdf`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180042ff3`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180043007`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18004301b`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::System::UserStatics::FindUserInMaps(
        __int64 a1,
        __int64 a2,
        struct Windows::System::IUser **a3)
{
  const struct _tlgProvider_t *v6; // rax
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rbx
  char v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  char v14; // r8
  __int64 v15; // rbx
  struct Windows::System::IUser **v16; // rdi
  int v17; // eax
  struct Windows::System::IUser **v18; // rdi
  int v19; // eax
  int v20; // eax
  __int64 j; // rax
  struct Windows::System::IUser **v22; // rdi
  int v23; // eax
  int valid; // eax
  __int64 i; // rax
  int v26; // eax
  __int64 v27; // rcx
  __int64 k; // rax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  int v33; // [rsp+20h] [rbp-48h]
  __int64 v34; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v35[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v37; // [rsp+80h] [rbp+18h] BYREF
  struct Windows::System::IUser *v38; // [rsp+88h] [rbp+20h] BYREF

  v6 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v6 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v6,
      byte_1801234E9,
      0);
  LOBYTE(v37) = 0;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
      (const char *)0x80004003LL,
      v33);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  v35[0] = a1 + 128;
  v8 = **(_QWORD **)(a1 + 168);
  v9 = v37;
  while ( v8 != *(_QWORD *)(a1 + 168) )
  {
    if ( v9 )
      goto LABEL_15;
    v22 = (struct Windows::System::IUser **)(v8 + 40);
    v23 = std::_Func_class<long,std::pair<unsigned int,unsigned long>,Windows::System::IUser *,unsigned char *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
            a2,
            *(_QWORD *)(v8 + 32),
            *(_QWORD *)(v8 + 40),
            &v37);
    v7 = retaddr;
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3AA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v23,
        v33);
    v9 = v37;
    if ( (_BYTE)v37 )
    {
      valid = IsValidCallerForUser(*v22, 0);
      if ( valid < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)valid,
          v33);
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v8 + 40);
      *a3 = *v22;
      v9 = v37;
    }
    if ( !*(_BYTE *)(v8 + 25) )
    {
      v7 = *(wil::details::in1diag3 **)(v8 + 16);
      if ( *((_BYTE *)v7 + 25) )
      {
        for ( i = *(_QWORD *)(v8 + 8); !*(_BYTE *)(i + 25) && v8 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v8 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v7);
      }
      v8 = i;
    }
  }
  if ( !v9 )
  {
    v10 = **(_QWORD **)(a1 + 184);
    while ( v10 != *(_QWORD *)(a1 + 184) )
    {
      if ( v9 )
        goto LABEL_15;
      v18 = (struct Windows::System::IUser **)(v10 + 40);
      v19 = std::_Func_class<long,std::pair<unsigned int,unsigned long>,Windows::System::IUser *,unsigned char *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
              a2,
              *(_QWORD *)(v10 + 32),
              *(_QWORD *)(v10 + 40),
              &v37);
      v7 = retaddr;
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B7,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v19,
          v33);
      v9 = v37;
      if ( (_BYTE)v37 )
      {
        v20 = IsValidCallerForUser(*v18, 0);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3BA,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v20,
            v33);
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v10 + 40);
        *a3 = *v18;
        v9 = v37;
      }
      if ( !*(_BYTE *)(v10 + 25) )
      {
        v7 = *(wil::details::in1diag3 **)(v10 + 16);
        if ( *((_BYTE *)v7 + 25) )
        {
          for ( j = *(_QWORD *)(v10 + 8); !*(_BYTE *)(j + 25) && v10 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v10 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v7);
        }
        v10 = j;
      }
    }
    if ( !v9 )
    {
      v38 = 0;
      if ( (int)UserManagerTokenAndShellHandler::TryGetDefaultAccountUser(v7, &v38) >= 0 )
      {
        LODWORD(v34) = 0x100000;
        HIDWORD(v34) = RtlGetCurrentServiceSessionId(v11);
        v12 = std::_Func_class<long,std::pair<unsigned int,unsigned long>,Windows::System::IUser *,unsigned char *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
                a2,
                v34,
                v38,
                &v37);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3C8,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v12,
            v33);
        if ( (_BYTE)v37 )
        {
          v13 = wil::com_ptr_t<Windows::System::IUser,wil::err_returncode_policy>::copy_to<Windows::System::IUser>(
                  (__int64 *)&v38,
                  a3);
          if ( v13 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3CB,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
              (const char *)(unsigned int)v13,
              v33);
        }
      }
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v38);
    }
  }
LABEL_15:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    v14 = v37;
    if ( !(_BYTE)v37 )
    {
      v15 = **(_QWORD **)(a1 + 464);
      while ( v15 != *(_QWORD *)(a1 + 464) && !v14 )
      {
        v16 = (struct Windows::System::IUser **)(v15 + 40);
        v17 = std::_Func_class<long,std::pair<unsigned int,unsigned long>,Windows::System::IUser *,unsigned char *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
                a2,
                *(_QWORD *)(v15 + 32),
                *(_QWORD *)(v15 + 40),
                &v37);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3D6,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
            (const char *)(unsigned int)v17,
            v33);
        v14 = v37;
        if ( (_BYTE)v37 )
        {
          v26 = IsValidCallerForUser(*v16, 0);
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3D9,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
              (const char *)(unsigned int)v26,
              v33);
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v15 + 40);
          *a3 = *v16;
          v14 = v37;
        }
        if ( !*(_BYTE *)(v15 + 25) )
        {
          v27 = *(_QWORD *)(v15 + 16);
          if ( *(_BYTE *)(v27 + 25) )
          {
            for ( k = *(_QWORD *)(v15 + 8); !*(_BYTE *)(k + 25) && v15 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
              v15 = k;
          }
          else
          {
            k = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v27);
          }
          v15 = k;
        }
      }
    }
  }
  v29 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v29 > 5u )
  {
    LODWORD(v34) = 0;
    LOBYTE(v38) = v37;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      (_DWORD)v29,
      (unsigned int)&word_1801234AE,
      v30,
      v31,
      (__int64)&v38,
      (__int64)&v34);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v35);
  std::function<bool (unsigned short const *,IInspectable *)>::~function<bool (unsigned short const *,IInspectable *)>(a2);
  return 0;
}

```

## disassembly

```asm
0x180042b80  mov     [rsp+arg_0], rbx
0x180042b85  mov     [rsp+arg_8], rdx
0x180042b8a  push    rsi
0x180042b8b  push    rdi
0x180042b8c  push    r12
0x180042b8e  push    r14
0x180042b90  push    r15
0x180042b92  sub     rsp, 40h
0x180042b96  mov     r14, r8
0x180042b99  mov     r15, rdx
0x180042b9c  mov     rsi, rcx
0x180042b9f  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180042ba4  mov     r9d, [rax]
0x180042ba7  cmp     r9d, 5
0x180042bab  jbe     short loc_180042BBF
0x180042bad  xor     r8d, r8d
0x180042bb0  lea     rdx, byte_1801234E9
0x180042bb7  mov     rcx, rax
0x180042bba  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180042bbf  xor     r12d, r12d
0x180042bc2  mov     byte ptr [rsp+68h+arg_10], r12b
0x180042bca  mov     rcx, [rsp+68h]; this
0x180042bcf  test    r14, r14
0x180042bd2  jz      loc_180042F73
0x180042bd8  mov     [r14], r12
0x180042bdb  lea     rbx, [rsi+80h]
0x180042be2  mov     rcx, rbx; lpCriticalSection
0x180042be5  call    cs:__imp_EnterCriticalSection
0x180042beb  mov     [rsp+68h+var_30], rbx
0x180042bf0  mov     rbx, [rsi+0A8h]
0x180042bf7  mov     rbx, [rbx]
0x180042bfa  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042c02  cmp     rbx, [rsi+0A8h]
0x180042c09  jnz     loc_180042DD6
0x180042c0f  test    r8b, r8b
0x180042c12  jnz     loc_180042CC1
0x180042c18  mov     rbx, [rsi+0B8h]
0x180042c1f  mov     rbx, [rbx]
0x180042c22  cmp     rbx, [rsi+0B8h]
0x180042c29  jnz     loc_180042D33
0x180042c2f  test    r8b, r8b
0x180042c32  jnz     loc_180042CC1
0x180042c38  mov     [rsp+68h+arg_18], r12
0x180042c40  lea     rdx, [rsp+68h+arg_18]; struct Windows::System::IUser **
0x180042c48  call    ?TryGetDefaultAccountUser@UserManagerTokenAndShellHandler@@QEAAJPEAPEAUIUser@System@Windows@@@Z; UserManagerTokenAndShellHandler::TryGetDefaultAccountUser(Windows::System::IUser * *)
0x180042c4d  test    eax, eax
0x180042c4f  js      short loc_180042CB4
0x180042c51  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180042c57  mov     dword ptr [rsp+68h+var_38], 100000h
0x180042c5f  mov     dword ptr [rsp+68h+var_38+4], eax
0x180042c63  lea     r9, [rsp+68h+arg_10]
0x180042c6b  mov     r8, [rsp+68h+arg_18]
0x180042c73  mov     rdx, [rsp+68h+var_38]
0x180042c78  mov     rcx, r15
0x180042c7b  call    ??R?$_Func_class@JU?$pair@IK@std@@PEAUIUser@System@Windows@@PEAEU_Nil@2@U62@U62@U62@@std@@QEBAJU?$pair@IK@1@PEAUIUser@System@Windows@@PEAE@Z; std::_Func_class<long,std::pair<uint,ulong>,Windows::System::IUser *,uchar *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(std::pair<uint,ulong>,Windows::System::IUser *,uchar *)
0x180042c80  mov     rcx, [rsp+68h]; this
0x180042c85  test    eax, eax
0x180042c87  js      loc_180042F8B
0x180042c8d  cmp     byte ptr [rsp+68h+arg_10], r12b
0x180042c95  jz      short loc_180042CB4
0x180042c97  mov     rdx, r14
0x180042c9a  lea     rcx, [rsp+68h+arg_18]
0x180042ca2  call    ??$copy_to@UIUser@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIUser@System@Windows@@@Z; wil::com_ptr_t<Windows::System::IUser,wil::err_returncode_policy>::copy_to<Windows::System::IUser>(Windows::System::IUser * *)
0x180042ca7  mov     rcx, [rsp+68h]; this
0x180042cac  test    eax, eax
0x180042cae  js      loc_180042F9F
0x180042cb4  lea     rcx, [rsp+68h+arg_18]
0x180042cbc  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180042cc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180042cc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180042ccd  test    al, al
0x180042ccf  jz      loc_180042EF3
0x180042cd5  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042cdd  test    r8b, r8b
0x180042ce0  jnz     loc_180042EF3
0x180042ce6  mov     rbx, [rsi+1D0h]
0x180042ced  mov     rbx, [rbx]
0x180042cf0  cmp     rbx, [rsi+1D0h]
0x180042cf7  jz      loc_180042EF3
0x180042cfd  test    r8b, r8b
0x180042d00  jnz     loc_180042EF3
0x180042d06  lea     rdi, [rbx+28h]
0x180042d0a  lea     r9, [rsp+68h+arg_10]
0x180042d12  mov     r8, [rdi]
0x180042d15  mov     rdx, [rbx+20h]
0x180042d19  mov     rcx, r15
0x180042d1c  call    ??R?$_Func_class@JU?$pair@IK@std@@PEAUIUser@System@Windows@@PEAEU_Nil@2@U62@U62@U62@@std@@QEBAJU?$pair@IK@1@PEAUIUser@System@Windows@@PEAE@Z; std::_Func_class<long,std::pair<uint,ulong>,Windows::System::IUser *,uchar *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(std::pair<uint,ulong>,Windows::System::IUser *,uchar *)
0x180042d21  mov     rcx, [rsp+68h]; this
0x180042d26  test    eax, eax
0x180042d28  js      loc_180042FB4
0x180042d2e  jmp     loc_180042E7D
0x180042d33  test    r8b, r8b
0x180042d36  jnz     short loc_180042CC1
0x180042d38  lea     rdi, [rbx+28h]
0x180042d3c  lea     r9, [rsp+68h+arg_10]
0x180042d44  mov     r8, [rdi]
0x180042d47  mov     rdx, [rbx+20h]
0x180042d4b  mov     rcx, r15
0x180042d4e  call    ??R?$_Func_class@JU?$pair@IK@std@@PEAUIUser@System@Windows@@PEAEU_Nil@2@U62@U62@U62@@std@@QEBAJU?$pair@IK@1@PEAUIUser@System@Windows@@PEAE@Z; std::_Func_class<long,std::pair<uint,ulong>,Windows::System::IUser *,uchar *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(std::pair<uint,ulong>,Windows::System::IUser *,uchar *)
0x180042d53  mov     rcx, [rsp+68h]; this
0x180042d58  test    eax, eax
0x180042d5a  js      loc_180042FC8
0x180042d60  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042d68  test    r8b, r8b
0x180042d6b  jz      short loc_180042D9A
0x180042d6d  xor     edx, edx; struct _BASIC_CALLER_INFORMATION *
0x180042d6f  mov     rcx, [rdi]; struct Windows::System::IUser *
0x180042d72  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180042d77  mov     rcx, [rsp+68h]; this
0x180042d7c  test    eax, eax
0x180042d7e  js      loc_180042FDC
0x180042d84  mov     rcx, rdi
0x180042d87  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042d8c  mov     rax, [rdi]
0x180042d8f  mov     [r14], rax
0x180042d92  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042d9a  cmp     [rbx+19h], r12b
0x180042d9e  jnz     loc_180042C22
0x180042da4  mov     rcx, [rbx+10h]
0x180042da8  cmp     [rcx+19h], r12b
0x180042dac  jnz     short loc_180042DBB
0x180042dae  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180042db3  mov     rbx, rax
0x180042db6  jmp     loc_180042C22
0x180042dbb  mov     rax, [rbx+8]
0x180042dbf  jmp     short loc_180042DCE
0x180042dc1  cmp     rbx, [rax+10h]
0x180042dc5  jnz     short loc_180042DB3
0x180042dc7  mov     rbx, rax
0x180042dca  mov     rax, [rax+8]
0x180042dce  cmp     [rax+19h], r12b
0x180042dd2  jz      short loc_180042DC1
0x180042dd4  jmp     short loc_180042DB3
0x180042dd6  test    r8b, r8b
0x180042dd9  jnz     loc_180042CC1
0x180042ddf  lea     rdi, [rbx+28h]
0x180042de3  lea     r9, [rsp+68h+arg_10]
0x180042deb  mov     r8, [rdi]
0x180042dee  mov     rdx, [rbx+20h]
0x180042df2  mov     rcx, r15
0x180042df5  call    ??R?$_Func_class@JU?$pair@IK@std@@PEAUIUser@System@Windows@@PEAEU_Nil@2@U62@U62@U62@@std@@QEBAJU?$pair@IK@1@PEAUIUser@System@Windows@@PEAE@Z; std::_Func_class<long,std::pair<uint,ulong>,Windows::System::IUser *,uchar *,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(std::pair<uint,ulong>,Windows::System::IUser *,uchar *)
0x180042dfa  mov     rcx, [rsp+68h]; this
0x180042dff  test    eax, eax
0x180042e01  js      loc_180042FF0
0x180042e07  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042e0f  test    r8b, r8b
0x180042e12  jz      short loc_180042E41
0x180042e14  xor     edx, edx; struct _BASIC_CALLER_INFORMATION *
0x180042e16  mov     rcx, [rdi]; struct Windows::System::IUser *
0x180042e19  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180042e1e  mov     rcx, [rsp+68h]; this
0x180042e23  test    eax, eax
0x180042e25  js      loc_180043004
0x180042e2b  mov     rcx, rdi
0x180042e2e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042e33  mov     rax, [rdi]
0x180042e36  mov     [r14], rax
0x180042e39  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042e41  cmp     [rbx+19h], r12b
0x180042e45  jnz     loc_180042C02
0x180042e4b  mov     rcx, [rbx+10h]
0x180042e4f  cmp     [rcx+19h], r12b
0x180042e53  jnz     short loc_180042E62
0x180042e55  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180042e5a  mov     rbx, rax
0x180042e5d  jmp     loc_180042C02
0x180042e62  mov     rax, [rbx+8]
0x180042e66  jmp     short loc_180042E75
0x180042e68  cmp     rbx, [rax+10h]
0x180042e6c  jnz     short loc_180042E5A
0x180042e6e  mov     rbx, rax
0x180042e71  mov     rax, [rax+8]
0x180042e75  cmp     [rax+19h], r12b
0x180042e79  jz      short loc_180042E68
0x180042e7b  jmp     short loc_180042E5A
0x180042e7d  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042e85  test    r8b, r8b
0x180042e88  jz      short loc_180042EB7
0x180042e8a  xor     edx, edx; struct _BASIC_CALLER_INFORMATION *
0x180042e8c  mov     rcx, [rdi]; struct Windows::System::IUser *
0x180042e8f  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180042e94  mov     rcx, [rsp+68h]; this
0x180042e99  test    eax, eax
0x180042e9b  js      loc_180043018
0x180042ea1  mov     rcx, rdi
0x180042ea4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042ea9  mov     rax, [rdi]
0x180042eac  mov     [r14], rax
0x180042eaf  mov     r8b, byte ptr [rsp+68h+arg_10]
0x180042eb7  cmp     [rbx+19h], r12b
0x180042ebb  jnz     loc_180042CF0
0x180042ec1  mov     rcx, [rbx+10h]
0x180042ec5  cmp     [rcx+19h], r12b
0x180042ec9  jnz     short loc_180042ED8
0x180042ecb  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180042ed0  mov     rbx, rax
0x180042ed3  jmp     loc_180042CF0
0x180042ed8  mov     rax, [rbx+8]
0x180042edc  jmp     short loc_180042EEB
0x180042ede  cmp     rbx, [rax+10h]
0x180042ee2  jnz     short loc_180042ED0
0x180042ee4  mov     rbx, rax
0x180042ee7  mov     rax, [rax+8]
0x180042eeb  cmp     [rax+19h], r12b
0x180042eef  jz      short loc_180042EDE
0x180042ef1  jmp     short loc_180042ED0
0x180042ef3  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180042ef8  mov     ecx, [rax]
0x180042efa  cmp     ecx, 5
0x180042efd  jbe     short loc_180042F39
0x180042eff  mov     dword ptr [rsp+68h+var_38], r12d
0x180042f04  mov     cl, byte ptr [rsp+68h+arg_10]
0x180042f0b  mov     byte ptr [rsp+68h+arg_18], cl
0x180042f12  lea     rcx, [rsp+68h+var_38]
0x180042f17  mov     [rsp+68h+var_40], rcx
0x180042f1c  lea     rcx, [rsp+68h+arg_18]
0x180042f24  mov     [rsp+68h+var_48], rcx
0x180042f29  lea     rdx, word_1801234AE
0x180042f30  mov     rcx, rax
0x180042f33  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180042f38  nop
0x180042f39  lea     rcx, [rsp+68h+var_30]; this
0x180042f3e  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180042f43  nop
0x180042f44  mov     rcx, r15
0x180042f47  call    ??1?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@QEAA@XZ; std::function<bool (ushort const *,IInspectable *)>::~function<bool (ushort const *,IInspectable *)>(void)
0x180042f4c  xor     eax, eax
0x180042f4e  jmp     short loc_180042F61
0x180042f50  mov     rcx, [rsp+68h+arg_8]
0x180042f55  call    ??1?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@QEAA@XZ; std::function<bool (ushort const *,IInspectable *)>::~function<bool (ushort const *,IInspectable *)>(void)
0x180042f5a  mov     eax, [rsp+68h+arg_10]
0x180042f61  mov     rbx, [rsp+68h+arg_0]
0x180042f66  add     rsp, 40h
0x180042f6a  pop     r15
0x180042f6c  pop     r14
0x180042f6e  pop     r12
0x180042f70  pop     rdi
0x180042f71  pop     rsi
0x180042f72  retn
0x180042f73  mov     r9d, 80004003h; char *
0x180042f79  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042f80  mov     edx, 3A2h; void *
0x180042f85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042f8b  mov     r9d, eax; char *
0x180042f8e  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042f95  mov     edx, 3C8h; void *
0x180042f9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042f9f  mov     r9d, eax; char *
0x180042fa2  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042fa9  mov     edx, 3CBh; void *
0x180042fae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042fb4  mov     r9d, eax; char *
0x180042fb7  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042fbe  mov     edx, 3D6h; void *
0x180042fc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042fc8  mov     r9d, eax; char *
0x180042fcb  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042fd2  mov     edx, 3B7h; void *
0x180042fd7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042fdc  mov     r9d, eax; char *
0x180042fdf  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042fe6  mov     edx, 3BAh; void *
0x180042feb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ff0  mov     r9d, eax; char *
0x180042ff3  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180042ffa  mov     edx, 3AAh; void *
0x180042fff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043004  mov     r9d, eax; char *
0x180043007  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18004300e  mov     edx, 3ADh; void *
0x180043013  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043018  mov     r9d, eax; char *
0x18004301b  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180043022  mov     edx, 3D9h; void *
0x180043027  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
