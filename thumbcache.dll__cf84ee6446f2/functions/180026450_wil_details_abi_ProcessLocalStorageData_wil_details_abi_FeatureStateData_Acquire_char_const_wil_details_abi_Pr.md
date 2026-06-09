# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180026450`
- end: `0x180026672`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180025e00`

## callees

- `0x180003320`
- `0x18000bfd8`
- `0x180017af0`
- `0x18001f73c`
- `0x180026450`
- `0x180026678`
- `0x180026690`
- `0x18002d4f8`
- `0x18002de8c`
- `0x180033dbc`
- `0x180034494`
- `0x180034f50`
- `0x180035164`
- `0x180035830`
- `0x180038680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026485`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002650d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002650d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800264cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800264cb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  wil::details *v7; // rdi
  unsigned int LastErrorFailHr; // ebx
  DWORD v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  bool v13; // dl
  bool *v14; // r9
  int ValueInternal; // eax
  _DWORD *v16; // rcx
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
  v21 = 304;
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
  if ( !v7 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_5:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    return LastErrorFailHr;
  }
  v10 = WaitForSingleObjectEx(v7, 0xFFFFFFFF, 0);
  if ( v10 == 258 )
  {
    v7 = 0;
  }
  else if ( (v10 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v11, v12);
  }
  v23 = (unsigned __int64)v7;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
    v25,
    &v23);
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v13, &v23, v14);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
    v17 = LastErrorFailHr;
    v18 = 302;
    goto LABEL_14;
  }
  v16 = (_DWORD *)(4 * v23);
  if ( !(4 * v23) )
  {
    v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v20;
    if ( v20 >= 0 )
      goto LABEL_11;
    v17 = (unsigned int)v20;
    v18 = 311;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, (unsigned int)"wil", (const char *)v17, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    goto LABEL_5;
  }
  *a2 = v16;
  ++*v16;
LABEL_11:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
  return 0;
}

```

## disassembly

```asm
0x180026450  mov     [rsp-8+arg_10], rbx
0x180026455  push    rbp
0x180026456  push    rsi
0x180026457  push    rdi
0x180026458  lea     rbp, [rsp-170h]
0x180026460  sub     rsp, 270h
0x180026467  mov     rax, cs:__security_cookie
0x18002646e  xor     rax, rsp
0x180026471  mov     [rbp+180h+var_20], rax
0x180026478  mov     rsi, rdx
0x18002647b  mov     qword ptr [rdx], 0
0x180026482  mov     rbx, rcx
0x180026485  call    cs:__imp_GetCurrentProcessId
0x18002648b  mov     [rsp+280h+var_258], rbx
0x180026490  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180026497  mov     r9d, eax
0x18002649a  mov     [rsp+280h+var_260], 130h; int
0x1800264a2  mov     edx, 104h; unsigned __int64
0x1800264a7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800264ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800264b1  lea     rcx, [rsp+280h+var_248]
0x1800264b6  call    ??0?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x1800264bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800264c1  lea     rdx, [rsp+280h+Name]; lpName
0x1800264c6  xor     r8d, r8d; dwFlags
0x1800264c9  xor     ecx, ecx; lpMutexAttributes
0x1800264cb  call    cs:__imp_CreateMutexExW
0x1800264d1  mov     rbx, [rsp+280h+var_248]
0x1800264d6  mov     rdi, rax
0x1800264d9  test    rbx, rbx
0x1800264dc  jnz     loc_18002662B
0x1800264e2  mov     [rsp+280h+var_248], rdi
0x1800264e7  test    rdi, rdi
0x1800264ea  jnz     short loc_180026504
0x1800264ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800264f1  mov     ebx, eax
0x1800264f3  lea     rcx, [rsp+280h+var_248]
0x1800264f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800264fd  mov     eax, ebx
0x1800264ff  jmp     loc_180026590
0x180026504  xor     r8d, r8d; bAlertable
0x180026507  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002650a  mov     rcx, rdi; hHandle
0x18002650d  call    cs:__imp_WaitForSingleObjectEx
0x180026513  cmp     eax, 102h
0x180026518  jz      loc_1800265B2
0x18002651e  test    eax, 0FFFFFF7Fh
0x180026523  jnz     loc_180026619
0x180026529  lea     rdx, [rsp+280h+var_250]
0x18002652e  mov     [rsp+280h+var_250], rdi
0x180026533  lea     rcx, [rsp+280h+var_240]
0x180026538  call    ??$?0AEAPEAG$$V@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@AEAPEAG@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(ushort * &)
0x18002653d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180026542  mov     [rsp+280h+var_250], 0
0x18002654b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180026550  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180026555  mov     ebx, eax
0x180026557  test    eax, eax
0x180026559  js      short loc_1800265B9
0x18002655b  mov     rax, [rsp+280h+var_250]
0x180026560  lea     rcx, ds:0[rax*4]
0x180026568  test    rcx, rcx
0x18002656b  jz      loc_18002664C
0x180026571  mov     [rsi], rcx
0x180026574  mov     eax, [rcx]
0x180026576  inc     eax
0x180026578  mov     [rcx], eax
0x18002657a  lea     rcx, [rsp+280h+var_240]
0x18002657f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026584  lea     rcx, [rsp+280h+var_248]
0x180026589  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002658e  xor     eax, eax
0x180026590  mov     rcx, [rbp+180h+var_20]
0x180026597  xor     rcx, rsp; StackCookie
0x18002659a  call    __security_check_cookie
0x18002659f  mov     rbx, [rsp+280h+arg_10]
0x1800265a7  add     rsp, 270h
0x1800265ae  pop     rdi
0x1800265af  pop     rsi
0x1800265b0  pop     rbp
0x1800265b1  retn
0x1800265b2  xor     edi, edi
0x1800265b4  jmp     loc_180026529
0x1800265b9  mov     rcx, [rbp+188h]; this
0x1800265c0  lea     r8, aWil; "wil"
0x1800265c7  mov     r9d, ebx; char *
0x1800265ca  mov     edx, 66h ; 'f'; void *
0x1800265cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265d4  mov     rcx, [rbp+188h]; this
0x1800265db  lea     r8, aWil; "wil"
0x1800265e2  mov     r9d, ebx; char *
0x1800265e5  mov     edx, 6Fh ; 'o'; void *
0x1800265ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265ef  mov     r9d, ebx; char *
0x1800265f2  mov     edx, 12Eh; void *
0x1800265f7  mov     rcx, [rbp+188h]; this
0x1800265fe  lea     r8, aWil; "wil"
0x180026605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002660a  lea     rcx, [rsp+280h+var_240]
0x18002660f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026614  jmp     loc_1800264F3
0x180026619  mov     rcx, [rbp+188h]; this
0x180026620  mov     edx, 0E01h; void *
0x180026625  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002662b  lea     rcx, [rsp+280h+var_250]; this
0x180026630  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180026635  mov     rcx, rbx; this
0x180026638  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002663d  lea     rcx, [rsp+280h+var_250]; this
0x180026642  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180026647  jmp     loc_1800264E2
0x18002664c  mov     r8, rsi
0x18002664f  lea     rdx, [rsp+280h+var_248]
0x180026654  lea     rcx, [rsp+280h+Name]
0x180026659  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002665e  mov     ebx, eax
0x180026660  test    eax, eax
0x180026662  jns     loc_18002657A
0x180026668  mov     r9d, eax
0x18002666b  mov     edx, 137h
0x180026670  jmp     short loc_1800265F7
```
