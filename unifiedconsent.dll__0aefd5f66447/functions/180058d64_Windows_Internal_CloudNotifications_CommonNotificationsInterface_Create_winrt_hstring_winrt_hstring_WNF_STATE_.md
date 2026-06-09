# Windows::Internal::CloudNotifications::CommonNotificationsInterface::Create(winrt::hstring,winrt::hstring,_WNF_STATE_NAME,std::shared_ptr<Windows::Internal::CloudRequestor::ICommonHttpInterface>,std::shared_ptr<Windows::Internal::CloudNotifications::INotificationSubscriptionHandler>,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>,unsigned __int64,std::shared_ptr<Windows::Internal::CloudRequestor::Common::IRegistryUtils>)

- ea: `0x180058d64`
- end: `0x180059469`
- name: `?Create@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@SA?AV?$shared_ptr@VCommonNotificationsInterface@CloudNotifications@Internal@Windows@@@std@@Uhstring@winrt@@0U_WNF_STATE_NAME@@V?$shared_ptr@VICommonHttpInterface@CloudRequestor@Internal@Windows@@@6@V?$shared_ptr@VINotificationSubscriptionHandler@CloudNotifications@Internal@Windows@@@6@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@6@_KV?$shared_ptr@VIRegistryUtils@Common@CloudRequestor@Internal@Windows@@@6@@Z`
- size: `1797`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180059470`

## callees

- `0x180002810`
- `0x180002840`
- `0x1800034f7`
- `0x1800035ab`
- `0x18003fbf8`
- `0x18004fed8`
- `0x18005625c`
- `0x180056ca8`
- `0x180058d64`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059444`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059453`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059462`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059444`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059453`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180059462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059290`

## string_xrefs

- `0x180058e14`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x180058e44`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x180058e74`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall Windows::Internal::CloudNotifications::CommonNotificationsInterface::Create(
        _QWORD *a1,
        volatile signed __int32 **a2,
        volatile signed __int32 **a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int128 *a7,
        int a8,
        _QWORD *a9)
{
  __int64 v10; // rax
  const WCHAR *v11; // r9
  volatile signed __int32 *v12; // r12
  volatile signed __int32 *v13; // rsi
  char v14; // di
  volatile signed __int32 *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  _DWORD *v19; // rax
  char *v20; // r13
  int v21; // edx
  char v22; // di
  _QWORD *v23; // rdx
  volatile signed __int32 *v24; // rax
  __int64 v25; // rcx
  volatile signed __int32 *v26; // rbx
  char *v27; // rax
  volatile signed __int32 *v28; // rdx
  volatile signed __int32 *v29; // rcx
  char v30; // di
  volatile signed __int32 *v31; // rbx
  volatile signed __int32 *v32; // rbx
  int v33; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v35; // rdi
  volatile signed __int32 *v36; // rbx
  int v37; // eax
  HANDLE v38; // rax
  volatile signed __int32 **v39; // rdi
  volatile signed __int32 *v40; // rbx
  int v41; // eax
  HANDLE v42; // rax
  volatile signed __int32 *v43; // rbx
  volatile signed __int32 *v44; // rbx
  volatile signed __int32 *v45; // rbx
  volatile signed __int32 *v46; // rbx
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  const char *v53; // [rsp+30h] [rbp-D0h]
  const char *v54; // [rsp+30h] [rbp-D0h]
  const char *v55; // [rsp+30h] [rbp-D0h]
  const char *v56; // [rsp+30h] [rbp-D0h]
  const char *v57; // [rsp+30h] [rbp-D0h]
  volatile signed __int32 *v58; // [rsp+68h] [rbp-98h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v60; // [rsp+78h] [rbp-88h]
  char *v61; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v62; // [rsp+88h] [rbp-78h]
  char **v63; // [rsp+90h] [rbp-70h]
  volatile signed __int32 **v64; // [rsp+98h] [rbp-68h]
  volatile signed __int32 **v65; // [rsp+A0h] [rbp-60h]
  _QWORD *v66; // [rsp+A8h] [rbp-58h]
  _QWORD *v67; // [rsp+B0h] [rbp-50h]
  _QWORD *v68; // [rsp+B8h] [rbp-48h]
  _QWORD *v69; // [rsp+C0h] [rbp-40h]
  __int128 v70; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+D8h] [rbp-28h] BYREF
  volatile signed __int32 *v72; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-18h]
  volatile signed __int32 **v74; // [rsp+F0h] [rbp-10h]
  volatile signed __int32 **v75; // [rsp+F8h] [rbp-8h]
  _QWORD *v76; // [rsp+100h] [rbp+0h]
  _QWORD *v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+110h] [rbp+10h]
  _QWORD *v79; // [rsp+118h] [rbp+18h]
  char v80[8]; // [rsp+120h] [rbp+20h] BYREF
  volatile signed __int32 *v81; // [rsp+128h] [rbp+28h]
  __int128 v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v65 = a3;
  v64 = a2;
  v68 = a1;
  v74 = a2;
  v75 = a3;
  v83 = a4;
  v66 = a5;
  v76 = a5;
  v67 = a6;
  v77 = a6;
  v73 = (__int64)a7;
  v78 = (__int64)a7;
  v69 = a9;
  v79 = a9;
  LOBYTE(v48) = *a2 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)0x80070057LL,
    v48,
    (bool)"fullPackageName cannot be empty",
    v53);
  LOBYTE(v49) = *a3 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)0x80070057LL,
    v49,
    (bool)"appId cannot be empty",
    v54);
  LOBYTE(v50) = *a5 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)0x80070057LL,
    v50,
    (bool)"httpInterface is required",
    v55);
  LOBYTE(v51) = *a6 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x62,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)0x80070057LL,
    v51,
    (bool)"subscriptionHandler is required",
    v56);
  if ( *a3 )
    v10 = *((unsigned int *)*a3 + 1);
  else
    v10 = 0;
  LOBYTE(v52) = (unsigned __int64)(v10 + 25) > 0x104;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)0x80070057LL,
    v52,
    (bool)"appId length exceeds the allowed maximum for use in m_mutexName",
    v57);
  if ( *a3 )
    v11 = (const WCHAR *)*((_QWORD *)*a3 + 2);
  else
    v11 = &Name;
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
    &lpMem,
    L"%ls%ls",
    L"Local\\crnotif-",
    v11);
  v12 = (volatile signed __int32 *)lpMem;
  v58 = (volatile signed __int32 *)lpMem;
  lpMem = 0;
  v72 = v58;
  if ( *a9 )
  {
    v16 = a9[1];
    if ( v16 )
      _InterlockedAdd((volatile signed __int32 *)(v16 + 8), 1u);
    v61 = (char *)*a9;
    v15 = (volatile signed __int32 *)a9[1];
    v62 = v15;
    v14 = 4;
    v63 = &v61;
    v13 = v15;
  }
  else
  {
    v13 = (volatile signed __int32 *)operator new(0x18u);
    v60 = v13;
    *(_OWORD *)v13 = 0;
    *((_DWORD *)v13 + 2) = 1;
    *((_DWORD *)v13 + 3) = 1;
    *(_QWORD *)v13 = &std::_Ref_count_obj2<Windows::Internal::CloudRequestor::Common::RegistryUtils>::`vftable';
    *((_QWORD *)v13 + 2) = &Windows::Internal::CloudRequestor::Common::RegistryUtils::`vftable';
    v61 = (char *)(v13 + 4);
    v62 = v13;
    v82 = 0;
    v63 = &v61;
    v14 = 19;
    v15 = v13;
  }
  v71 = 604800;
  v70 = 0;
  v17 = *((_QWORD *)a7 + 1);
  if ( v17 )
    _InterlockedAdd((volatile signed __int32 *)(v17 + 8), 1u);
  v70 = *a7;
  v18 = Windows::Internal::CloudRequestor::CreateInternalLogger(v80, &v70);
  v19 = operator new(0x90u);
  v60 = v19;
  *(_OWORD *)v19 = 0;
  v19[2] = 1;
  v19[3] = 1;
  *(_QWORD *)v19 = &std::_Ref_count_obj2<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::`vftable';
  v20 = (char *)(v19 + 4);
  std::_Construct_in_place<Windows::Internal::CloudNotifications::CommonNotificationsInterface,Windows::Internal::CloudNotifications::CommonNotificationsInterface::Private,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,_WNF_STATE_NAME const &,std::shared_ptr<Windows::Internal::CloudRequestor::ICommonHttpInterface> const &,std::shared_ptr<Windows::Internal::CloudNotifications::INotificationSubscriptionHandler> const &,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>,unsigned __int64,std::shared_ptr<Windows::Internal::CloudRequestor::Common::IRegistryUtils> const>(
    (_DWORD)v19 + 16,
    v21,
    (_DWORD)v64,
    (_DWORD)v65,
    (__int64)&v72,
    (__int64)&v83,
    (__int64)v66,
    (__int64)v67,
    v18,
    (__int64)&v71,
    (unsigned int)v63);
  v22 = v14 | 0x20;
  v23 = v68;
  *v68 = v20;
  v24 = v60;
  v23[1] = v60;
  if ( v20 )
  {
    v25 = *((_QWORD *)v20 + 2);
    if ( !v25 || !*(_DWORD *)(v25 + 8) )
    {
      _InterlockedAdd(v24 + 2, 1u);
      v26 = (volatile signed __int32 *)v23[1];
      v27 = 0;
      v28 = 0;
      if ( v26 )
      {
        v27 = v20;
        v28 = v26;
        _InterlockedAdd(v26 + 3, 1u);
      }
      *((_QWORD *)v20 + 1) = v27;
      v29 = (volatile signed __int32 *)*((_QWORD *)v20 + 2);
      *((_QWORD *)v20 + 2) = v28;
      if ( v29 && _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      v12 = v58;
    }
  }
  v30 = v22 | 8;
  v31 = v81;
  if ( v81 )
  {
    if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  if ( (v30 & 4) != 0 )
  {
    v30 &= ~4u;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
  }
  if ( (v30 & 2) != 0 )
  {
    v30 &= ~2u;
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v13)((void *)v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
  }
  if ( (v30 & 1) != 0 )
  {
    v32 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
    if ( *((_QWORD *)&v82 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v82 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
  }
  if ( v12 )
  {
    v33 = _InterlockedDecrement(v12 + 6);
    if ( v33 )
    {
      if ( v33 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
    }
  }
  if ( lpMem )
    WindowsDeleteString((HSTRING)lpMem);
  v35 = v64;
  v36 = *v64;
  if ( *v64 )
  {
    v37 = _InterlockedDecrement(v36 + 6);
    if ( v37 )
    {
      if ( v37 < 0 )
        abort();
    }
    else
    {
      v38 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v38, 0, (LPVOID)v36);
    }
    *v35 = 0;
  }
  v39 = v65;
  v40 = *v65;
  if ( *v65 )
  {
    v41 = _InterlockedDecrement(v40 + 6);
    if ( v41 )
    {
      if ( v41 < 0 )
        abort();
    }
    else
    {
      v42 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v42, 0, (LPVOID)v40);
    }
    *v39 = 0;
  }
  v43 = (volatile signed __int32 *)v66[1];
  if ( v43 )
  {
    if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
      if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
    }
  }
  v44 = (volatile signed __int32 *)v67[1];
  if ( v44 )
  {
    if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
      if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
    }
  }
  v45 = *(volatile signed __int32 **)(v73 + 8);
  if ( v45 )
  {
    if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
      if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
    }
  }
  v46 = (volatile signed __int32 *)v69[1];
  if ( v46 )
  {
    if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  return v68;
}

```

## disassembly

```asm
0x180058d64  push    rbp
0x180058d66  push    rbx
0x180058d67  push    rsi
0x180058d68  push    rdi
0x180058d69  push    r12
0x180058d6b  push    r13
0x180058d6d  push    r14
0x180058d6f  push    r15
0x180058d71  lea     rbp, [rsp-58h]
0x180058d76  sub     rsp, 158h
0x180058d7d  mov     rax, cs:__security_cookie
0x180058d84  xor     rax, rsp
0x180058d87  mov     [rbp+90h+var_48], rax
0x180058d8b  mov     rdi, r8
0x180058d8e  mov     [rbp+90h+var_F0], r8
0x180058d92  mov     [rbp+90h+var_F8], rdx
0x180058d96  mov     [rbp+90h+var_D8], rcx
0x180058d9a  mov     [rbp+90h+var_D0], rcx
0x180058d9e  mov     [rbp+90h+var_A0], rdx
0x180058da2  mov     [rbp+90h+var_98], r8
0x180058da6  mov     [rbp+90h+var_50], r9
0x180058daa  mov     rsi, [rbp+90h+arg_20]
0x180058db1  mov     [rbp+90h+var_E8], rsi
0x180058db5  mov     [rbp+90h+var_90], rsi
0x180058db9  mov     r14, [rbp+90h+arg_28]
0x180058dc0  mov     [rbp+90h+var_E0], r14
0x180058dc4  mov     [rbp+90h+var_88], r14
0x180058dc8  mov     r13, [rbp+90h+arg_30]
0x180058dcf  mov     [rbp+90h+var_A8], r13
0x180058dd3  mov     [rbp+90h+var_80], r13
0x180058dd7  mov     rbx, [rbp+90h+arg_40]
0x180058dde  mov     [rbp+90h+var_D0], rbx
0x180058de2  mov     [rbp+90h+var_78], rbx
0x180058de6  xor     r15d, r15d
0x180058de9  mov     [rsp+190h+var_130], r15d
0x180058dee  cmp     [rdx], r15
0x180058df1  setz    al
0x180058df4  mov     rcx, [rbp+98h]; this
0x180058dfb  lea     rdx, aFullpackagenam_0; "fullPackageName cannot be empty"
0x180058e02  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x180058e07  mov     byte ptr [rsp+190h+var_170], al; int
0x180058e0b  mov     r12d, 80070057h
0x180058e11  mov     r9d, r12d; char *
0x180058e14  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x180058e1b  lea     edx, [r15+53h]; void *
0x180058e1f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180058e24  cmp     [rdi], r15
0x180058e27  setz    al
0x180058e2a  mov     rcx, [rbp+98h]; this
0x180058e31  lea     rdx, aAppidCannotBeE; "appId cannot be empty"
0x180058e38  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x180058e3d  mov     byte ptr [rsp+190h+var_170], al; int
0x180058e41  mov     r9d, r12d; char *
0x180058e44  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x180058e4b  lea     edx, [r15+58h]; void *
0x180058e4f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180058e54  cmp     [rsi], r15
0x180058e57  setz    al
0x180058e5a  mov     rcx, [rbp+98h]; this
0x180058e61  lea     rdx, aHttpinterfaceI; "httpInterface is required"
0x180058e68  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x180058e6d  mov     byte ptr [rsp+190h+var_170], al; int
0x180058e71  mov     r9d, r12d; char *
0x180058e74  lea     rsi, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x180058e7b  mov     r8, rsi; unsigned int
0x180058e7e  lea     edx, [r15+5Dh]; void *
0x180058e82  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180058e87  cmp     [r14], r15
0x180058e8a  setz    al
0x180058e8d  mov     rcx, [rbp+98h]; this
0x180058e94  lea     rdx, aSubscriptionha; "subscriptionHandler is required"
0x180058e9b  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x180058ea0  mov     byte ptr [rsp+190h+var_170], al; int
0x180058ea4  mov     r9d, r12d; char *
0x180058ea7  mov     r8, rsi; unsigned int
0x180058eaa  lea     edx, [r15+62h]; void *
0x180058eae  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180058eb3  mov     rax, [rdi]
0x180058eb6  test    rax, rax
0x180058eb9  jz      short loc_180058EC0
0x180058ebb  mov     eax, [rax+4]
0x180058ebe  jmp     short loc_180058EC3
0x180058ec0  mov     eax, r15d
0x180058ec3  add     rax, 19h
0x180058ec7  cmp     rax, 104h
0x180058ecd  setnbe  al
0x180058ed0  mov     rcx, [rbp+98h]; this
0x180058ed7  lea     rdx, aAppidLengthExc; "appId length exceeds the allowed maximu"...
0x180058ede  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x180058ee3  mov     byte ptr [rsp+190h+var_170], al; int
0x180058ee7  mov     r9d, r12d; char *
0x180058eea  mov     r8, rsi; unsigned int
0x180058eed  mov     edx, 69h ; 'i'; void *
0x180058ef2  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180058ef7  mov     r9, [rdi]
0x180058efa  test    r9, r9
0x180058efd  jz      short loc_180058F05
0x180058eff  mov     r9, [r9+10h]
0x180058f03  jmp     short loc_180058F0C
0x180058f05  lea     r9, Name
0x180058f0c  lea     r8, ?c_mutexNamePrefix@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@0QBGB; "Local\\crnotif-"
0x180058f13  lea     rdx, aLsLs; "%ls%ls"
0x180058f1a  lea     rcx, [rsp+190h+lpMem]
0x180058f1f  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,...)
0x180058f24  nop
0x180058f25  mov     r12, [rsp+190h+lpMem]
0x180058f2a  mov     [rsp+190h+var_128], r12
0x180058f2f  mov     [rsp+190h+lpMem], r15
0x180058f34  mov     [rbp+90h+var_B0], r12
0x180058f38  cmp     [rbx], r15
0x180058f3b  jnz     short loc_180058F9A
0x180058f3d  mov     ecx, 18h; Size
0x180058f42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058f47  mov     rsi, rax
0x180058f4a  mov     [rsp+190h+var_118], rax
0x180058f4f  xorps   xmm0, xmm0
0x180058f52  movups  xmmword ptr [rax], xmm0
0x180058f55  mov     r15d, 1
0x180058f5b  mov     [rax+8], r15d
0x180058f5f  mov     [rax+0Ch], r15d
0x180058f63  lea     rax, ??_7?$_Ref_count_obj2@VRegistryUtils@Common@CloudRequestor@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::CloudRequestor::Common::RegistryUtils>::`vftable'
0x180058f6a  mov     [rsi], rax
0x180058f6d  lea     rax, [rsi+10h]
0x180058f71  lea     rcx, ??_7RegistryUtils@Common@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::Common::RegistryUtils::`vftable'
0x180058f78  mov     [rax], rcx
0x180058f7b  mov     [rbp+90h+var_110], rax
0x180058f7f  mov     [rbp+90h+var_108], rsi
0x180058f83  movdqu  [rbp+90h+var_60], xmm0
0x180058f88  lea     rcx, [rbp+90h+var_110]
0x180058f8c  mov     [rbp+90h+var_100], rcx
0x180058f90  lea     edi, [r15+12h]
0x180058f94  mov     r14, [rbp+90h+var_108]
0x180058f98  jmp     short loc_180058FCE
0x180058f9a  mov     rax, [rbx+8]
0x180058f9e  mov     r15d, 1
0x180058fa4  test    rax, rax
0x180058fa7  jz      short loc_180058FAE
0x180058fa9  lock add [rax+8], r15d
0x180058fae  mov     rax, [rbx]
0x180058fb1  mov     [rbp+90h+var_110], rax
0x180058fb5  mov     r14, [rbx+8]
0x180058fb9  mov     [rbp+90h+var_108], r14
0x180058fbd  mov     edi, 4
0x180058fc2  lea     rax, [rbp+90h+var_110]
0x180058fc6  mov     [rbp+90h+var_100], rax
0x180058fca  mov     rsi, [rbp+90h+var_108]
0x180058fce  mov     [rsp+190h+var_130], edi
0x180058fd2  mov     [rbp+90h+var_B8], 93A80h
0x180058fda  xorps   xmm0, xmm0
0x180058fdd  movdqu  [rbp+90h+var_C8], xmm0
0x180058fe2  mov     rax, [r13+8]
0x180058fe6  test    rax, rax
0x180058fe9  jz      short loc_180058FF0
0x180058feb  lock add [rax+8], r15d
0x180058ff0  mov     rax, [r13+0]
0x180058ff4  mov     qword ptr [rbp+90h+var_C8], rax
0x180058ff8  mov     rax, [r13+8]
0x180058ffc  mov     qword ptr [rbp+90h+var_C8+8], rax
0x180059000  lea     rdx, [rbp+90h+var_C8]
0x180059004  lea     rcx, [rbp+90h+var_70]
0x180059008  call    ?CreateInternalLogger@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@std@@V45@@Z; Windows::Internal::CloudRequestor::CreateInternalLogger(std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>)
0x18005900d  mov     rbx, rax
0x180059010  mov     ecx, 90h; Size
0x180059015  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005901a  mov     [rsp+190h+var_118], rax
0x18005901f  xorps   xmm0, xmm0
0x180059022  movups  xmmword ptr [rax], xmm0
0x180059025  mov     [rax+8], r15d
0x180059029  mov     [rax+0Ch], r15d
0x18005902d  lea     rcx, ??_7?$_Ref_count_obj2@VCommonNotificationsInterface@CloudNotifications@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::`vftable'
0x180059034  mov     [rax], rcx
0x180059037  lea     r13, [rax+10h]
0x18005903b  mov     rax, [rbp+90h+var_100]
0x18005903f  mov     [rsp+190h+var_140], rax
0x180059044  lea     rax, [rbp+90h+var_B8]
0x180059048  mov     [rsp+190h+var_148], rax
0x18005904d  mov     [rsp+190h+var_150], rbx
0x180059052  mov     rax, [rbp+90h+var_E0]
0x180059056  mov     [rsp+190h+var_158], rax
0x18005905b  mov     rax, [rbp+90h+var_E8]
0x18005905f  mov     [rsp+190h+var_160], rax
0x180059064  lea     rax, [rbp+90h+var_50]
0x180059068  mov     qword ptr [rsp+190h+var_168], rax
0x18005906d  lea     rax, [rbp+90h+var_B0]
0x180059071  mov     qword ptr [rsp+190h+var_170], rax
0x180059076  mov     r9, [rbp+90h+var_F0]
0x18005907a  mov     r8, [rbp+90h+var_F8]
0x18005907e  mov     rcx, r13
0x180059081  call    ??$_Construct_in_place@VCommonNotificationsInterface@CloudNotifications@Internal@Windows@@UPrivate@1234@AEBUhstring@winrt@@AEBU67@AEBU67@AEBU_WNF_STATE_NAME@@AEBV?$shared_ptr@VICommonHttpInterface@CloudRequestor@Internal@Windows@@@std@@AEBV?$shared_ptr@VINotificationSubscriptionHandler@CloudNotifications@Internal@Windows@@@std@@V?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@std@@_K$$CBV?$shared_ptr@VIRegistryUtils@Common@CloudRequestor@Internal@Windows@@@std@@@std@@YAXAEAVCommonNotificationsInterface@CloudNotifications@Internal@Windows@@$$QEAUPrivate@1234@AEBUhstring@winrt@@22AEBU_WNF_STATE_NAME@@AEBV?$shared_ptr@VICommonHttpInterface@CloudRequestor@Internal@Windows@@@0@AEBV?$shared_ptr@VINotificationSubscriptionHandler@CloudNotifications@Internal@Windows@@@0@$$QEAV?$shared_ptr@VILogger@CloudRequestor@Internal@Windows@@@0@$$QEA_K$$QEBV?$shared_ptr@VIRegistryUtils@Common@CloudRequestor@Internal@Windows@@@0@@Z; std::_Construct_in_place<Windows::Internal::CloudNotifications::CommonNotificationsInterface,Windows::Internal::CloudNotifications::CommonNotificationsInterface::Private,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,_WNF_STATE_NAME const &,std::shared_ptr<Windows::Internal::CloudRequestor::ICommonHttpInterface> const &,std::shared_ptr<Windows::Internal::CloudNotifications::INotificationSubscriptionHandler> const &,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger>,unsigned __int64,std::shared_ptr<Windows::Internal::CloudRequestor::Common::IRegistryUtils> const>(Windows::Internal::CloudNotifications::CommonNotificationsInterface &,Windows::Internal::CloudNotifications::CommonNotificationsInterface::Private &&,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,_WNF_STATE_NAME const &,std::shared_ptr<Windows::Internal::CloudRequestor::ICommonHttpInterface> const &,std::shared_ptr<Windows::Internal::CloudNotifications::INotificationSubscriptionHandler> const &,std::shared_ptr<Windows::Internal::CloudRequestor::ILogger> &&,unsigned __int64 &&,std::shared_ptr<Windows::Internal::CloudRequestor::Common::IRegistryUtils> const &&)
0x180059086  nop
0x180059087  or      edi, 20h
0x18005908a  mov     rdx, [rbp+90h+var_D8]
0x18005908e  mov     [rdx], r13
0x180059091  mov     rax, [rsp+190h+var_118]
0x180059096  mov     [rdx+8], rax
0x18005909a  test    r13, r13
0x18005909d  jz      loc_18005913E
0x1800590a3  mov     rcx, [r13+10h]
0x1800590a7  test    rcx, rcx
0x1800590aa  jz      short loc_1800590B6
0x1800590ac  cmp     dword ptr [rcx+8], 0
0x1800590b0  jnz     loc_18005913E
0x1800590b6  lock add [rax+8], r15d
0x1800590bb  mov     rbx, [rdx+8]
0x1800590bf  xor     eax, eax
0x1800590c1  xor     edx, edx
0x1800590c3  test    rbx, rbx
0x1800590c6  jz      short loc_1800590D3
0x1800590c8  mov     rax, r13
0x1800590cb  mov     rdx, rbx
0x1800590ce  lock add [rbx+0Ch], r15d
0x1800590d3  mov     [r13+8], rax
0x1800590d7  mov     rcx, [r13+10h]
0x1800590db  mov     [r13+10h], rdx
0x1800590df  test    rcx, rcx
0x1800590e2  jz      short loc_1800590FD
0x1800590e4  or      eax, 0FFFFFFFFh
0x1800590e7  lock xadd [rcx+0Ch], eax
0x1800590ec  cmp     eax, 1
0x1800590ef  jnz     short loc_1800590FD
0x1800590f1  mov     rax, [rcx]
0x1800590f4  mov     rax, [rax+8]
0x1800590f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800590fd  test    rbx, rbx
0x180059100  jz      short loc_180059139
0x180059102  or      eax, 0FFFFFFFFh
0x180059105  lock xadd [rbx+8], eax
0x18005910a  cmp     eax, 1
0x18005910d  jnz     short loc_180059139
0x18005910f  mov     rax, [rbx]
0x180059112  mov     rcx, rbx
0x180059115  mov     rax, [rax]
0x180059118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005911d  or      eax, 0FFFFFFFFh
0x180059120  lock xadd [rbx+0Ch], eax
0x180059125  cmp     eax, 1
0x180059128  jnz     short loc_180059139
0x18005912a  mov     rax, [rbx]
0x18005912d  mov     rcx, rbx
0x180059130  mov     rax, [rax+8]
0x180059134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059139  mov     r12, [rsp+190h+var_128]
0x18005913e  or      edi, 8
0x180059141  mov     rbx, [rbp+90h+var_68]
0x180059145  or      r13d, 0FFFFFFFFh
0x180059149  test    rbx, rbx
0x18005914c  jz      short loc_180059186
0x18005914e  mov     eax, r13d
0x180059151  lock xadd [rbx+8], eax
0x180059156  add     eax, r13d
0x180059159  jnz     short loc_180059186
0x18005915b  mov     rax, [rbx]
0x18005915e  mov     rcx, rbx
0x180059161  mov     rax, [rax]
0x180059164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059169  mov     eax, r13d
0x18005916c  lock xadd [rbx+0Ch], eax
0x180059171  add     eax, r13d
0x180059174  jnz     short loc_180059186
0x180059176  mov     rax, [rbx]
0x180059179  mov     rcx, rbx
0x18005917c  mov     rax, [rax+8]
0x180059180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059185  nop
0x180059186  test    dil, 4
0x18005918a  jz      short loc_1800591CE
0x18005918c  and     edi, 0FFFFFFFBh
0x18005918f  test    r14, r14
0x180059192  jz      short loc_1800591CE
0x180059194  mov     eax, r13d
0x180059197  lock xadd [r14+8], eax
0x18005919d  add     eax, r13d
0x1800591a0  jnz     short loc_1800591CE
0x1800591a2  mov     rax, [r14]
0x1800591a5  mov     rcx, r14
0x1800591a8  mov     rax, [rax]
0x1800591ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591b0  mov     eax, r13d
0x1800591b3  lock xadd [r14+0Ch], eax
0x1800591b9  add     eax, r13d
0x1800591bc  jnz     short loc_1800591CE
0x1800591be  mov     rax, [r14]
0x1800591c1  mov     rcx, r14
0x1800591c4  mov     rax, [rax+8]
0x1800591c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591cd  nop
0x1800591ce  test    dil, 2
0x1800591d2  jz      short loc_180059214
0x1800591d4  and     edi, 0FFFFFFFDh
0x1800591d7  test    rsi, rsi
0x1800591da  jz      short loc_180059214
0x1800591dc  mov     eax, r13d
0x1800591df  lock xadd [rsi+8], eax
0x1800591e4  add     eax, r13d
0x1800591e7  jnz     short loc_180059214
0x1800591e9  mov     rax, [rsi]
0x1800591ec  mov     rcx, rsi
0x1800591ef  mov     rax, [rax]
0x1800591f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591f7  mov     eax, r13d
  ... truncated ...
```
