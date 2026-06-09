# Windows::Internal::CloudNotifications::CommonNotificationsInterface::UpdateCachedChannelData(winrt::hstring,winrt::hstring,winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse)

- ea: `0x18005e32c`
- end: `0x18005e6c9`
- name: `?UpdateCachedChannelData@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@AEAAXUhstring@winrt@@U56@UNotificationSubscriptionResponse@2346@@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x18000ed24`
- `0x180016e40`
- `0x18005e2dc`
- `0x18005e32c`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18005e5ae`
- `msvcp_win!_Xtime_get_ticks` at `0x18005e5ae`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e455`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e54a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e555`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e6b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e6c2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e455`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e54a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e555`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e6b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005e6c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e63c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e63c`

## string_xrefs

- `0x18005e577`: `WnsChannelUri`
- `0x18005e5f7`: `LastUpdated`
- `0x18005e3c3`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005e4bf`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005e59d`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005e61e`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005e3b4`: `Failed to create reigstry key for notification channel data`
- `0x18005e60f`: `Failed to save last updated time to the registry`
- `0x18005e58e`: `Failed to save WNS channel URI to the registry`
- `0x18005e4b0`: `Failed to save ETag to the registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LSTATUS Windows::Internal::CloudNotifications::CommonNotificationsInterface::UpdateCachedChannelData(_QWORD *a1, ...)
{
  _QWORD *v1; // rdi
  volatile signed __int32 **v2; // r14
  volatile signed __int32 **v3; // r15
  __int64 v4; // rcx
  const WCHAR *v5; // r12
  const WCHAR *v6; // r8
  unsigned int v7; // eax
  __int64 v8; // r13
  void *v9; // rsi
  int v10; // eax
  HANDLE ProcessHeap; // rax
  bool v12; // zf
  _QWORD **v13; // r13
  __int64 v14; // rax
  int v15; // esi
  __int64 v16; // rax
  const WCHAR *v17; // rax
  unsigned int v18; // eax
  void *v19; // rsi
  int v20; // eax
  HANDLE v21; // rax
  void *v22; // rsi
  int v23; // eax
  HANDLE v24; // rax
  volatile signed __int32 *v25; // rax
  int v26; // r8d
  unsigned int v27; // eax
  unsigned int v28; // eax
  LSTATUS result; // eax
  volatile signed __int32 *v30; // rsi
  HANDLE v31; // rax
  volatile signed __int32 *v32; // rsi
  int v33; // ebx
  HANDLE v34; // rax
  char *v35; // [rsp+28h] [rbp-50h]
  char *v36; // [rsp+28h] [rbp-50h]
  char *v37; // [rsp+28h] [rbp-50h]
  char *v38; // [rsp+28h] [rbp-50h]
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-30h] BYREF
  __int64 (__fastcall *v41)(LPVOID, HKEY, const wchar_t *, __int64, const WCHAR *, int); // [rsp+50h] [rbp-28h]
  LPVOID v42; // [rsp+58h] [rbp-20h] BYREF
  __int64 v43[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  LPVOID v45; // [rsp+C0h] [rbp+48h] BYREF
  volatile signed __int32 **v46; // [rsp+C8h] [rbp+50h]
  volatile signed __int32 **v47; // [rsp+D0h] [rbp+58h]
  _QWORD *v48; // [rsp+D8h] [rbp+60h]
  va_list va; // [rsp+E0h] [rbp+68h] BYREF

  va_start(va, a1);
  v46 = va_arg(va, volatile signed __int32 **);
  v47 = va_arg(va, volatile signed __int32 **);
  v48 = va_arg(va, _QWORD *);
  v45 = a1;
  v1 = v48;
  v2 = v47;
  v3 = v46;
  hKey = 0;
  v4 = a1[13];
  v5 = &Name;
  if ( *v46 )
    v6 = (const WCHAR *)*((_QWORD *)*v46 + 2);
  else
    v6 = &Name;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, const WCHAR *, _QWORD, int, HKEY *, _QWORD))(*(_QWORD *)v4 + 16LL))(
         v4,
         -2147483647,
         v6,
         0,
         131078,
         &hKey,
         0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x315,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)v7,
    (int)"Failed to create reigstry key for notification channel data",
    v35);
  v8 = *(_QWORD *)winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(
                    v1,
                    &lpMem);
  if ( v8 )
    LODWORD(v8) = *(_DWORD *)(v8 + 4);
  v9 = lpMem;
  if ( lpMem )
  {
    v10 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v10 )
    {
      if ( v10 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v9);
    }
  }
  v12 = (_DWORD)v8 == 0;
  v13 = (_QWORD **)v45;
  if ( !v12 )
  {
    lpMem = (LPVOID)*((_QWORD *)v45 + 13);
    v41 = *(__int64 (__fastcall **)(LPVOID, HKEY, const wchar_t *, __int64, const WCHAR *, int))(*(_QWORD *)lpMem + 24LL);
    v14 = winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(
            v1,
            &v42);
    if ( *(_QWORD *)v14 )
      v15 = *(_DWORD *)(*(_QWORD *)v14 + 4LL);
    else
      v15 = 0;
    v16 = winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(
            v1,
            &v45);
    if ( *(_QWORD *)v16 )
      v17 = *(const WCHAR **)(*(_QWORD *)v16 + 16LL);
    else
      v17 = &Name;
    v18 = v41(lpMem, hKey, L"SubscriptionEtag", 1, v17, 2 * v15 + 2);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
      (const char *)v18,
      (int)"Failed to save ETag to the registry",
      v36);
    v19 = v45;
    if ( v45 )
    {
      v20 = _InterlockedDecrement((volatile signed __int32 *)v45 + 6);
      if ( v20 )
      {
        if ( v20 < 0 )
          abort();
      }
      else
      {
        v21 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v21, 0, v19);
      }
      v45 = 0;
    }
    v22 = v42;
    if ( v42 )
    {
      v23 = _InterlockedDecrement((volatile signed __int32 *)v42 + 6);
      if ( v23 )
      {
        if ( v23 < 0 )
          abort();
      }
      else
      {
        v24 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v24, 0, v22);
      }
    }
  }
  v25 = *v2;
  if ( *v2 )
  {
    v5 = (const WCHAR *)*((_QWORD *)v25 + 2);
    v26 = *((_DWORD *)v25 + 1);
  }
  else
  {
    v26 = 0;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, HKEY, const wchar_t *, __int64, const WCHAR *, int))(*v13[13] + 24LL))(
          v13[13],
          hKey,
          L"WnsChannelUri",
          1,
          v5,
          2 * v26 + 2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x32C,
    (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
    (const char *)v27,
    (int)"Failed to save WNS channel URI to the registry",
    v37);
  v43[0] = _Xtime_get_ticks() / 10000000;
  v28 = (*(__int64 (__fastcall **)(_QWORD *, HKEY, const wchar_t *, __int64, __int64 *, int))(*v13[13] + 24LL))(
          v13[13],
          hKey,
          L"LastUpdated",
          11,
          v43,
          8);
  result = wil::details::in1diag3::Throw_IfFailedMsg(
             retaddr,
             (void *)0x33B,
             (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
             (const char *)v28,
             (int)"Failed to save last updated time to the registry",
             v38);
  if ( hKey )
    result = RegCloseKey(hKey);
  v30 = *v3;
  if ( *v3 )
  {
    result = _InterlockedDecrement(v30 + 6);
    if ( result )
    {
      if ( result < 0 )
        abort();
    }
    else
    {
      v31 = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(v31, 0, (LPVOID)v30);
    }
    *v3 = 0;
  }
  v32 = *v2;
  if ( *v2 )
  {
    v33 = _InterlockedDecrement(v32 + 6);
    if ( v33 )
    {
      if ( v33 < 0 )
        abort();
    }
    else
    {
      v34 = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(v34, 0, (LPVOID)v32);
    }
    *v2 = 0;
  }
  if ( *v1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1);
  return result;
}

```

## disassembly

```asm
0x18005e32c  mov     rax, rsp
0x18005e32f  mov     [rax+20h], r9
0x18005e333  mov     [rax+18h], r8
0x18005e337  mov     [rax+10h], rdx
0x18005e33b  mov     [rax+8], rcx
0x18005e33f  push    rbp
0x18005e340  push    rbx
0x18005e341  push    rsi
0x18005e342  push    rdi
0x18005e343  push    r12
0x18005e345  push    r13
0x18005e347  push    r14
0x18005e349  push    r15
0x18005e34b  mov     rbp, rsp
0x18005e34e  sub     rsp, 78h
0x18005e352  mov     rdi, r9
0x18005e355  mov     r14, r8
0x18005e358  mov     r15, rdx
0x18005e35b  xor     edx, edx
0x18005e35d  mov     [rbp+hKey], rdx
0x18005e361  mov     rcx, [rcx+68h]
0x18005e365  mov     rax, [rcx]
0x18005e368  mov     r10, [rax+10h]
0x18005e36c  mov     [rbp+hKey], rdx
0x18005e370  mov     rax, [r15]
0x18005e373  lea     r12, Name
0x18005e37a  test    rax, rax
0x18005e37d  jz      short loc_18005E385
0x18005e37f  mov     r8, [rax+10h]
0x18005e383  jmp     short loc_18005E388
0x18005e385  mov     r8, r12
0x18005e388  mov     [rsp+78h+var_48], rdx
0x18005e38d  lea     rax, [rbp+hKey]
0x18005e391  mov     [rsp+78h+var_50], rax; char *
0x18005e396  mov     [rsp+78h+var_58], 20006h
0x18005e39e  xor     r9d, r9d
0x18005e3a1  mov     rdx, 0FFFFFFFF80000001h
0x18005e3a8  mov     rax, r10
0x18005e3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3b0  mov     rcx, [rbp+40h]; this
0x18005e3b4  lea     rdx, aFailedToCreate_4; "Failed to create reigstry key for notif"...
0x18005e3bb  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18005e3c0  mov     r9d, eax; char *
0x18005e3c3  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005e3ca  mov     edx, 315h; void *
0x18005e3cf  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e3d4  lea     rdx, [rbp+lpMem]
0x18005e3d8  mov     rcx, rdi
0x18005e3db  call    ?UpdatedETag@?$consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse@UINotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(void)
0x18005e3e0  mov     r13, [rax]
0x18005e3e3  test    r13, r13
0x18005e3e6  jz      short loc_18005E3EC
0x18005e3e8  mov     r13d, [r13+4]
0x18005e3ec  mov     rsi, [rbp+lpMem]
0x18005e3f0  or      ebx, 0FFFFFFFFh
0x18005e3f3  test    rsi, rsi
0x18005e3f6  jz      short loc_18005E417
0x18005e3f8  mov     eax, ebx
0x18005e3fa  lock xadd [rsi+18h], eax
0x18005e3ff  sub     eax, 1
0x18005e402  jnz     short loc_18005E451
0x18005e404  nop
0x18005e405  call    WINRT_IMPL_GetProcessHeap
0x18005e40a  mov     rcx, rax; hHeap
0x18005e40d  mov     r8, rsi; lpMem
0x18005e410  xor     edx, edx; dwFlags
0x18005e412  call    WINRT_IMPL_HeapFree
0x18005e417  test    r13d, r13d
0x18005e41a  mov     r13, [rbp+arg_0]
0x18005e41e  jz      loc_18005E529
0x18005e424  mov     rax, [r13+68h]
0x18005e428  mov     [rbp+lpMem], rax
0x18005e42c  mov     rax, [rax]
0x18005e42f  mov     rax, [rax+18h]
0x18005e433  mov     [rbp+var_28], rax
0x18005e437  lea     rdx, [rbp+var_20]
0x18005e43b  mov     rcx, rdi
0x18005e43e  call    ?UpdatedETag@?$consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse@UINotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(void)
0x18005e443  nop
0x18005e444  mov     rcx, [rax]
0x18005e447  test    rcx, rcx
0x18005e44a  jz      short loc_18005E45C
0x18005e44c  mov     esi, [rcx+4]
0x18005e44f  jmp     short loc_18005E45E
0x18005e451  test    eax, eax
0x18005e453  jns     short loc_18005E417
0x18005e455  call    cs:__imp_abort
0x18005e45c  xor     esi, esi
0x18005e45e  lea     rdx, [rbp+arg_0]
0x18005e462  mov     rcx, rdi
0x18005e465  call    ?UpdatedETag@?$consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse@UINotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(void)
0x18005e46a  nop
0x18005e46b  mov     rcx, [rax]
0x18005e46e  test    rcx, rcx
0x18005e471  jz      short loc_18005E479
0x18005e473  mov     rax, [rcx+10h]
0x18005e477  jmp     short loc_18005E47C
0x18005e479  mov     rax, r12
0x18005e47c  lea     r8d, ds:2[rsi*2]
0x18005e484  mov     dword ptr [rsp+78h+var_50], r8d; char *
0x18005e489  mov     qword ptr [rsp+78h+var_58], rax
0x18005e48e  mov     r9d, 1
0x18005e494  lea     r8, aSubscriptionet; "SubscriptionEtag"
0x18005e49b  mov     rdx, [rbp+hKey]
0x18005e49f  mov     rcx, [rbp+lpMem]
0x18005e4a3  mov     rax, [rbp+var_28]
0x18005e4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4ac  mov     rcx, [rbp+40h]; this
0x18005e4b0  lea     rdx, aFailedToSaveEt; "Failed to save ETag to the registry"
0x18005e4b7  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18005e4bc  mov     r9d, eax; char *
0x18005e4bf  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005e4c6  mov     edx, 321h; void *
0x18005e4cb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e4d0  nop
0x18005e4d1  mov     rsi, [rbp+arg_0]
0x18005e4d5  test    rsi, rsi
0x18005e4d8  jz      short loc_18005E501
0x18005e4da  mov     eax, ebx
0x18005e4dc  lock xadd [rsi+18h], eax
0x18005e4e1  sub     eax, 1
0x18005e4e4  jnz     short loc_18005E546
0x18005e4e6  nop
0x18005e4e7  call    WINRT_IMPL_GetProcessHeap
0x18005e4ec  mov     rcx, rax; hHeap
0x18005e4ef  mov     r8, rsi; lpMem
0x18005e4f2  xor     edx, edx; dwFlags
0x18005e4f4  call    WINRT_IMPL_HeapFree
0x18005e4f9  mov     [rbp+arg_0], 0
0x18005e501  mov     rsi, [rbp+var_20]
0x18005e505  test    rsi, rsi
0x18005e508  jz      short loc_18005E529
0x18005e50a  mov     eax, ebx
0x18005e50c  lock xadd [rsi+18h], eax
0x18005e511  sub     eax, 1
0x18005e514  jnz     short loc_18005E551
0x18005e516  nop
0x18005e517  call    WINRT_IMPL_GetProcessHeap
0x18005e51c  mov     rcx, rax; hHeap
0x18005e51f  mov     r8, rsi; lpMem
0x18005e522  xor     edx, edx; dwFlags
0x18005e524  call    WINRT_IMPL_HeapFree
0x18005e529  mov     rcx, [r13+68h]
0x18005e52d  mov     rax, [rcx]
0x18005e530  mov     r10, [rax+18h]
0x18005e534  mov     rax, [r14]
0x18005e537  test    rax, rax
0x18005e53a  jz      short loc_18005E55C
0x18005e53c  mov     r12, [rax+10h]
0x18005e540  mov     r8d, [rax+4]
0x18005e544  jmp     short loc_18005E55F
0x18005e546  test    eax, eax
0x18005e548  jns     short loc_18005E4F9
0x18005e54a  call    cs:__imp_abort
0x18005e551  test    eax, eax
0x18005e553  jns     short loc_18005E529
0x18005e555  call    cs:__imp_abort
0x18005e55c  xor     r8d, r8d
0x18005e55f  lea     r8d, ds:2[r8*2]
0x18005e567  mov     dword ptr [rsp+78h+var_50], r8d; char *
0x18005e56c  mov     qword ptr [rsp+78h+var_58], r12
0x18005e571  mov     r9d, 1
0x18005e577  lea     r8, aWnschanneluri; "WnsChannelUri"
0x18005e57e  mov     rdx, [rbp+hKey]
0x18005e582  mov     rax, r10
0x18005e585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e58a  mov     rcx, [rbp+40h]; this
0x18005e58e  lea     rdx, aFailedToSaveWn; "Failed to save WNS channel URI to the r"...
0x18005e595  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18005e59a  mov     r9d, eax; char *
0x18005e59d  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005e5a4  mov     edx, 32Ch; void *
0x18005e5a9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e5ae  call    cs:__imp__Xtime_get_ticks
0x18005e5b4  mov     rcx, rax
0x18005e5b7  mov     rax, 0D6BF94D5E57A42BDh
0x18005e5c1  imul    rcx
0x18005e5c4  add     rdx, rcx
0x18005e5c7  sar     rdx, 17h
0x18005e5cb  mov     rax, rdx
0x18005e5ce  shr     rax, 3Fh
0x18005e5d2  add     rdx, rax
0x18005e5d5  mov     [rbp+var_18], rdx
0x18005e5d9  mov     rcx, [r13+68h]
0x18005e5dd  mov     rax, [rcx]
0x18005e5e0  mov     dword ptr [rsp+78h+var_50], 8; char *
0x18005e5e8  lea     rdx, [rbp+var_18]
0x18005e5ec  mov     qword ptr [rsp+78h+var_58], rdx
0x18005e5f1  mov     r9d, 0Bh
0x18005e5f7  lea     r8, aLastupdated; "LastUpdated"
0x18005e5fe  mov     rdx, [rbp+hKey]
0x18005e602  mov     rax, [rax+18h]
0x18005e606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e60b  mov     rcx, [rbp+40h]; this
0x18005e60f  lea     rdx, aFailedToSaveLa; "Failed to save last updated time to the"...
0x18005e616  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18005e61b  mov     r9d, eax; char *
0x18005e61e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005e625  mov     edx, 33Bh; void *
0x18005e62a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e62f  nop
0x18005e630  mov     rcx, [rbp+hKey]; hKey
0x18005e634  xor     r12d, r12d
0x18005e637  test    rcx, rcx
0x18005e63a  jz      short loc_18005E643
0x18005e63c  call    cs:__imp_RegCloseKey
0x18005e642  nop
0x18005e643  mov     rsi, [r15]
0x18005e646  test    rsi, rsi
0x18005e649  jz      short loc_18005E66D
0x18005e64b  mov     eax, ebx
0x18005e64d  lock xadd [rsi+18h], eax
0x18005e652  sub     eax, 1
0x18005e655  jnz     short loc_18005E6B3
0x18005e657  nop
0x18005e658  call    WINRT_IMPL_GetProcessHeap
0x18005e65d  mov     rcx, rax; hHeap
0x18005e660  mov     r8, rsi; lpMem
0x18005e663  xor     edx, edx; dwFlags
0x18005e665  call    WINRT_IMPL_HeapFree
0x18005e66a  mov     [r15], r12
0x18005e66d  mov     rsi, [r14]
0x18005e670  test    rsi, rsi
0x18005e673  jz      short loc_18005E695
0x18005e675  lock xadd [rsi+18h], ebx
0x18005e67a  sub     ebx, 1
0x18005e67d  jnz     short loc_18005E6BE
0x18005e67f  nop
0x18005e680  call    WINRT_IMPL_GetProcessHeap
0x18005e685  mov     rcx, rax; hHeap
0x18005e688  mov     r8, rsi; lpMem
0x18005e68b  xor     edx, edx; dwFlags
0x18005e68d  call    WINRT_IMPL_HeapFree
0x18005e692  mov     [r14], r12
0x18005e695  cmp     [rdi], r12
0x18005e698  jz      short loc_18005E6A2
0x18005e69a  mov     rcx, rdi
0x18005e69d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18005e6a2  add     rsp, 78h
0x18005e6a6  pop     r15
0x18005e6a8  pop     r14
0x18005e6aa  pop     r13
0x18005e6ac  pop     r12
0x18005e6ae  pop     rdi
0x18005e6af  pop     rsi
0x18005e6b0  pop     rbx
0x18005e6b1  pop     rbp
0x18005e6b2  retn
0x18005e6b3  test    eax, eax
0x18005e6b5  jns     short loc_18005E66A
0x18005e6b7  call    cs:__imp_abort
0x18005e6be  test    ebx, ebx
0x18005e6c0  jns     short loc_18005E692
0x18005e6c2  call    cs:__imp_abort
```
