# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000d360`
- end: `0x18000d585`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d308`

## callees

- `0x180006ac0`
- `0x18000a80c`
- `0x18000a828`
- `0x18000d360`
- `0x18000f008`
- `0x18000f024`
- `0x18000f784`
- `0x180052f48`
- `0x180053bd8`
- `0x18005bb30`
- `0x180066910`
- `0x18006a800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d3d7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d3d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d42b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d42b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d39b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d39b`

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
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  void *v17; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v21);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v17);
    wil::details::CloseHandle(v6, v17);
    return v15;
  }
  else
  {
    v16 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v16;
      ++*v16;
    }
    else
    {
      v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        return v19;
      }
      v6 = v22;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18000d360  mov     [rsp-8+arg_10], rbx
0x18000d365  mov     [rsp-8+arg_18], rsi
0x18000d36a  push    rbp
0x18000d36b  push    rdi
0x18000d36c  push    r14
0x18000d36e  lea     rbp, [rsp-170h]
0x18000d376  sub     rsp, 270h
0x18000d37d  mov     rax, cs:__security_cookie
0x18000d384  xor     rax, rsp
0x18000d387  mov     [rbp+180h+var_20], rax
0x18000d38e  mov     r14, rdx
0x18000d391  mov     qword ptr [rdx], 0
0x18000d398  mov     rbx, rcx
0x18000d39b  call    cs:__imp_GetCurrentProcessId
0x18000d3a1  mov     [rsp+280h+var_258], rbx
0x18000d3a6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d3ad  mov     r9d, eax
0x18000d3b0  mov     [rsp+280h+var_260], 130h; int
0x18000d3b8  mov     edx, 104h; unsigned __int64
0x18000d3bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d3c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d3c7  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d3cd  lea     rdx, [rsp+280h+Name]; lpName
0x18000d3d2  xor     r8d, r8d; dwFlags
0x18000d3d5  xor     ecx, ecx; lpMutexAttributes
0x18000d3d7  call    cs:__imp_CreateMutexExW
0x18000d3dd  mov     [rsp+280h+var_250], rax
0x18000d3e2  mov     rbx, rax
0x18000d3e5  test    rax, rax
0x18000d3e8  jnz     short loc_18000D422
0x18000d3ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d3ef  jmp     short loc_18000D3FB
0x18000d3f1  mov     rcx, rbx; this
0x18000d3f4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d3f9  xor     eax, eax
0x18000d3fb  mov     rcx, [rbp+180h+var_20]
0x18000d402  xor     rcx, rsp; StackCookie
0x18000d405  call    __security_check_cookie
0x18000d40a  lea     r11, [rsp+280h+var_10]
0x18000d412  mov     rbx, [r11+30h]
0x18000d416  mov     rsi, [r11+38h]
0x18000d41a  mov     rsp, r11
0x18000d41d  pop     r14
0x18000d41f  pop     rdi
0x18000d420  pop     rbp
0x18000d421  retn
0x18000d422  xor     r8d, r8d; bAlertable
0x18000d425  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d428  mov     rcx, rbx; hHandle
0x18000d42b  call    cs:__imp_WaitForSingleObjectEx
0x18000d431  cmp     eax, 102h
0x18000d436  jz      loc_18000D514
0x18000d43c  test    eax, 0FFFFFF7Fh
0x18000d441  jnz     loc_18000D51B
0x18000d447  mov     rdi, rbx
0x18000d44a  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000d44f  mov     [rsp+280h+var_240], rdi
0x18000d454  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d459  mov     [rsp+280h+var_248], 0
0x18000d462  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000d467  mov     esi, eax
0x18000d469  test    eax, eax
0x18000d46b  js      short loc_18000D4A7
0x18000d46d  mov     rax, [rsp+280h+var_248]
0x18000d472  lea     rcx, ds:0[rax*4]
0x18000d47a  test    rcx, rcx
0x18000d47d  jz      loc_18000D52D
0x18000d483  mov     [r14], rcx
0x18000d486  mov     eax, [rcx]
0x18000d488  inc     eax
0x18000d48a  mov     [rcx], eax
0x18000d48c  test    rdi, rdi
0x18000d48f  jz      short loc_18000D499
0x18000d491  mov     rcx, rdi; this
0x18000d494  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000d499  test    rbx, rbx
0x18000d49c  jz      loc_18000D3F9
0x18000d4a2  jmp     loc_18000D3F1
0x18000d4a7  mov     rcx, [rbp+188h]; this
0x18000d4ae  lea     r8, aWil; "wil"
0x18000d4b5  mov     r9d, esi; char *
0x18000d4b8  mov     edx, 66h ; 'f'; void *
0x18000d4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4c2  mov     rcx, [rbp+188h]; this
0x18000d4c9  lea     r8, aWil; "wil"
0x18000d4d0  mov     r9d, esi; char *
0x18000d4d3  mov     edx, 6Fh ; 'o'; void *
0x18000d4d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4dd  mov     rcx, [rbp+188h]; this
0x18000d4e4  lea     r8, aWil; "wil"
0x18000d4eb  mov     r9d, esi; char *
0x18000d4ee  mov     edx, 12Eh; void *
0x18000d4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4f8  test    rdi, rdi
0x18000d4fb  jz      short loc_18000D505
0x18000d4fd  mov     rcx, rdi; this
0x18000d500  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000d505  mov     rcx, rbx; this
0x18000d508  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d50d  mov     eax, esi
0x18000d50f  jmp     loc_18000D3FB
0x18000d514  xor     edi, edi
0x18000d516  jmp     loc_18000D44A
0x18000d51b  mov     rcx, [rbp+188h]; this
0x18000d522  mov     edx, 0E01h; void *
0x18000d527  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000d52d  mov     r8, r14
0x18000d530  lea     rdx, [rsp+280h+var_250]
0x18000d535  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d53a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d53f  mov     ebx, eax
0x18000d541  test    eax, eax
0x18000d543  jns     short loc_18000D57B
0x18000d545  mov     rcx, [rbp+188h]; this
0x18000d54c  lea     r8, aWil; "wil"
0x18000d553  mov     r9d, eax; char *
0x18000d556  mov     edx, 137h; void *
0x18000d55b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d560  lea     rcx, [rsp+280h+var_240]
0x18000d565  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d56a  lea     rcx, [rsp+280h+var_250]
0x18000d56f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d574  mov     eax, ebx
0x18000d576  jmp     loc_18000D3FB
0x18000d57b  mov     rbx, [rsp+280h+var_250]
0x18000d580  jmp     loc_18000D48C
```
