# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180026224`
- end: `0x180026447`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180025fe8`

## callees

- `0x180003320`
- `0x18000bfd8`
- `0x180017af0`
- `0x18001f73c`
- `0x180026224`
- `0x180026678`
- `0x180026690`
- `0x18002d4f8`
- `0x18002de8c`
- `0x180033dbc`
- `0x180034494`
- `0x180034f50`
- `0x180035020`
- `0x180035830`
- `0x180038680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026259`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800262cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800262cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002629f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002629f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  wil::details *v7; // rdi
  DWORD v8; // eax
  unsigned int v9; // r8d
  const char *v10; // r9
  bool v11; // dl
  bool *v12; // r9
  int ValueInternal; // eax
  unsigned int LastErrorFailHr; // ebx
  _DWORD *v15; // rcx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  void *v19; // rdx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v24; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v25[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  __0__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v24);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = v24;
  v7 = Mutex;
  if ( v24 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
    wil::details::CloseHandle(v6, v19);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
  }
  v24 = v7;
  if ( v7 )
  {
    v8 = WaitForSingleObjectEx(v7, 0xFFFFFFFF, 0);
    if ( v8 == 258 )
    {
      v7 = 0;
    }
    else if ( (v8 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v9, v10);
    }
    v23 = (unsigned __int64)v7;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
      v25,
      &v23);
    v23 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v11, &v23, v12);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
      v17 = LastErrorFailHr;
      v18 = 302;
    }
    else
    {
      v15 = (_DWORD *)(4 * v23);
      if ( 4 * v23 )
      {
        *a2 = v15;
        ++*v15;
LABEL_9:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
        return 0;
      }
      v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v20;
      if ( v20 >= 0 )
        goto LABEL_9;
      v17 = (unsigned int)v20;
      v18 = 311;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, (unsigned int)"wil", (const char *)v17, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180026224  mov     [rsp-8+arg_10], rbx
0x180026229  push    rbp
0x18002622a  push    rsi
0x18002622b  push    rdi
0x18002622c  lea     rbp, [rsp-170h]
0x180026234  sub     rsp, 270h
0x18002623b  mov     rax, cs:__security_cookie
0x180026242  xor     rax, rsp
0x180026245  mov     [rbp+180h+var_20], rax
0x18002624c  mov     rsi, rdx
0x18002624f  mov     qword ptr [rdx], 0
0x180026256  mov     rbx, rcx
0x180026259  call    cs:__imp_GetCurrentProcessId
0x18002625f  mov     [rsp+280h+var_258], rbx
0x180026264  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002626b  mov     r9d, eax
0x18002626e  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180026276  mov     edx, 104h; unsigned __int64
0x18002627b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180026280  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026285  lea     rcx, [rsp+280h+var_248]
0x18002628a  call    ??0?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18002628f  mov     r9d, 1F0001h; dwDesiredAccess
0x180026295  lea     rdx, [rsp+280h+Name]; lpName
0x18002629a  xor     r8d, r8d; dwFlags
0x18002629d  xor     ecx, ecx; lpMutexAttributes
0x18002629f  call    cs:__imp_CreateMutexExW
0x1800262a5  mov     rbx, [rsp+280h+var_248]
0x1800262aa  mov     rdi, rax
0x1800262ad  test    rbx, rbx
0x1800262b0  jnz     loc_180026400
0x1800262b6  mov     [rsp+280h+var_248], rdi
0x1800262bb  test    rdi, rdi
0x1800262be  jz      loc_180026352
0x1800262c4  xor     r8d, r8d; bAlertable
0x1800262c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800262ca  mov     rcx, rdi; hHandle
0x1800262cd  call    cs:__imp_WaitForSingleObjectEx
0x1800262d3  cmp     eax, 102h
0x1800262d8  jz      loc_180026387
0x1800262de  test    eax, 0FFFFFF7Fh
0x1800262e3  jnz     loc_1800263EE
0x1800262e9  lea     rdx, [rsp+280h+var_250]
0x1800262ee  mov     [rsp+280h+var_250], rdi
0x1800262f3  lea     rcx, [rsp+280h+var_240]
0x1800262f8  call    ??$?0AEAPEAG$$V@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@AEAPEAG@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(ushort * &)
0x1800262fd  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180026302  mov     [rsp+280h+var_250], 0
0x18002630b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180026310  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180026315  mov     ebx, eax
0x180026317  test    eax, eax
0x180026319  js      short loc_18002638E
0x18002631b  mov     rax, [rsp+280h+var_250]
0x180026320  lea     rcx, ds:0[rax*4]
0x180026328  test    rcx, rcx
0x18002632b  jz      loc_180026421
0x180026331  mov     [rsi], rcx
0x180026334  mov     eax, [rcx]
0x180026336  inc     eax
0x180026338  mov     [rcx], eax
0x18002633a  lea     rcx, [rsp+280h+var_240]
0x18002633f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026344  lea     rcx, [rsp+280h+var_248]
0x180026349  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002634e  xor     eax, eax
0x180026350  jmp     short loc_180026365
0x180026352  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180026357  mov     ebx, eax
0x180026359  lea     rcx, [rsp+280h+var_248]
0x18002635e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026363  mov     eax, ebx
0x180026365  mov     rcx, [rbp+180h+var_20]
0x18002636c  xor     rcx, rsp; StackCookie
0x18002636f  call    __security_check_cookie
0x180026374  mov     rbx, [rsp+280h+arg_10]
0x18002637c  add     rsp, 270h
0x180026383  pop     rdi
0x180026384  pop     rsi
0x180026385  pop     rbp
0x180026386  retn
0x180026387  xor     edi, edi
0x180026389  jmp     loc_1800262E9
0x18002638e  mov     rcx, [rbp+188h]; this
0x180026395  lea     r8, aWil; "wil"
0x18002639c  mov     r9d, ebx; char *
0x18002639f  mov     edx, 66h ; 'f'; void *
0x1800263a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263a9  mov     rcx, [rbp+188h]; this
0x1800263b0  lea     r8, aWil; "wil"
0x1800263b7  mov     r9d, ebx; char *
0x1800263ba  mov     edx, 6Fh ; 'o'; void *
0x1800263bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263c4  mov     r9d, ebx; char *
0x1800263c7  mov     edx, 12Eh; void *
0x1800263cc  mov     rcx, [rbp+188h]; this
0x1800263d3  lea     r8, aWil; "wil"
0x1800263da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263df  lea     rcx, [rsp+280h+var_240]
0x1800263e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800263e9  jmp     loc_180026359
0x1800263ee  mov     rcx, [rbp+188h]; this
0x1800263f5  mov     edx, 0E01h; void *
0x1800263fa  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180026400  lea     rcx, [rsp+280h+var_250]; this
0x180026405  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002640a  mov     rcx, rbx; this
0x18002640d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026412  lea     rcx, [rsp+280h+var_250]; this
0x180026417  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002641c  jmp     loc_1800262B6
0x180026421  mov     r8, rsi
0x180026424  lea     rdx, [rsp+280h+var_248]
0x180026429  lea     rcx, [rsp+280h+Name]
0x18002642e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180026433  mov     ebx, eax
0x180026435  test    eax, eax
0x180026437  jns     loc_18002633A
0x18002643d  mov     r9d, eax
0x180026440  mov     edx, 137h
0x180026445  jmp     short loc_1800263CC
```
