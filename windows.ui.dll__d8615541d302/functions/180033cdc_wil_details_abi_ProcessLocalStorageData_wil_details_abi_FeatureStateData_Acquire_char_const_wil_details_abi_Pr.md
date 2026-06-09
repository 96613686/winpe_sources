# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180033cdc`
- end: `0x180033f02`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033c24`

## callees

- `0x180014754`
- `0x180033a50`
- `0x180033cdc`
- `0x180033f08`
- `0x180033f6c`
- `0x1800343d8`
- `0x180049048`
- `0x180053d6c`
- `0x1800585f4`
- `0x180066d14`
- `0x180069aa8`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033d53`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033d53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033d9b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033d17`

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
  void *v16; // rdx
  _DWORD *v17; // rcx
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
  if ( ValueInternal >= 0 )
  {
    v17 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v17;
      ++*v17;
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
  else
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
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v6, v16);
    return v15;
  }
}

```

## disassembly

```asm
0x180033cdc  mov     [rsp-8+arg_10], rbx
0x180033ce1  mov     [rsp-8+arg_18], rsi
0x180033ce6  push    rbp
0x180033ce7  push    rdi
0x180033ce8  push    r14
0x180033cea  lea     rbp, [rsp-170h]
0x180033cf2  sub     rsp, 270h
0x180033cf9  mov     rax, cs:__security_cookie
0x180033d00  xor     rax, rsp
0x180033d03  mov     [rbp+180h+var_20], rax
0x180033d0a  mov     r14, rdx
0x180033d0d  mov     qword ptr [rdx], 0
0x180033d14  mov     rbx, rcx
0x180033d17  call    cs:__imp_GetCurrentProcessId
0x180033d1d  mov     [rsp+280h+var_258], rbx
0x180033d22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180033d29  mov     r9d, eax
0x180033d2c  mov     [rsp+280h+var_260], 130h; int
0x180033d34  mov     edx, 104h; unsigned __int64
0x180033d39  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180033d3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033d43  mov     r9d, 1F0001h; dwDesiredAccess
0x180033d49  lea     rdx, [rsp+280h+Name]; lpName
0x180033d4e  xor     r8d, r8d; dwFlags
0x180033d51  xor     ecx, ecx; lpMutexAttributes
0x180033d53  call    cs:__imp_CreateMutexExW
0x180033d59  mov     [rsp+280h+var_250], rax
0x180033d5e  mov     rbx, rax
0x180033d61  test    rax, rax
0x180033d64  jnz     short loc_180033D92
0x180033d66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180033d6b  mov     rcx, [rbp+180h+var_20]
0x180033d72  xor     rcx, rsp; StackCookie
0x180033d75  call    __security_check_cookie
0x180033d7a  lea     r11, [rsp+280h+var_10]
0x180033d82  mov     rbx, [r11+30h]
0x180033d86  mov     rsi, [r11+38h]
0x180033d8a  mov     rsp, r11
0x180033d8d  pop     r14
0x180033d8f  pop     rdi
0x180033d90  pop     rbp
0x180033d91  retn
0x180033d92  xor     r8d, r8d; bAlertable
0x180033d95  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180033d98  mov     rcx, rbx; hHandle
0x180033d9b  call    cs:__imp_WaitForSingleObjectEx
0x180033da1  cmp     eax, 102h
0x180033da6  jz      loc_180033E42
0x180033dac  test    eax, 0FFFFFF7Fh
0x180033db1  jnz     loc_180033E81
0x180033db7  mov     rdi, rbx
0x180033dba  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180033dbf  mov     [rsp+280h+var_240], rdi
0x180033dc4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180033dc9  mov     [rsp+280h+var_248], 0
0x180033dd2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180033dd7  mov     esi, eax
0x180033dd9  test    eax, eax
0x180033ddb  jns     short loc_180033E49
0x180033ddd  mov     rcx, [rbp+188h]; this
0x180033de4  lea     r8, aWil; "wil"
0x180033deb  mov     r9d, eax; char *
0x180033dee  mov     edx, 66h ; 'f'; void *
0x180033df3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033df8  mov     rcx, [rbp+188h]; this
0x180033dff  lea     r8, aWil; "wil"
0x180033e06  mov     r9d, esi; char *
0x180033e09  mov     edx, 6Fh ; 'o'; void *
0x180033e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033e13  mov     rcx, [rbp+188h]; this
0x180033e1a  lea     r8, aWil; "wil"
0x180033e21  mov     r9d, esi; char *
0x180033e24  mov     edx, 12Eh; void *
0x180033e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033e2e  test    rdi, rdi
0x180033e31  jnz     short loc_180033E93
0x180033e33  mov     rcx, rbx; this
0x180033e36  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180033e3b  mov     eax, esi
0x180033e3d  jmp     loc_180033D6B
0x180033e42  xor     edi, edi
0x180033e44  jmp     loc_180033DBA
0x180033e49  mov     rax, [rsp+280h+var_248]
0x180033e4e  lea     rcx, ds:0[rax*4]
0x180033e56  test    rcx, rcx
0x180033e59  jz      short loc_180033E9D
0x180033e5b  mov     [r14], rcx
0x180033e5e  mov     eax, [rcx]
0x180033e60  inc     eax
0x180033e62  mov     [rcx], eax
0x180033e64  test    rdi, rdi
0x180033e67  jnz     loc_180033EF5
0x180033e6d  test    rbx, rbx
0x180033e70  jz      short loc_180033E7A
0x180033e72  mov     rcx, rbx; this
0x180033e75  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180033e7a  xor     eax, eax
0x180033e7c  jmp     loc_180033D6B
0x180033e81  mov     rcx, [rbp+188h]; this
0x180033e88  mov     edx, 0E01h; void *
0x180033e8d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180033e93  mov     rcx, rdi; this
0x180033e96  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180033e9b  jmp     short loc_180033E33
0x180033e9d  mov     r8, r14
0x180033ea0  lea     rdx, [rsp+280h+var_250]
0x180033ea5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180033eaa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180033eaf  mov     ebx, eax
0x180033eb1  test    eax, eax
0x180033eb3  jns     short loc_180033EEB
0x180033eb5  mov     rcx, [rbp+188h]; this
0x180033ebc  lea     r8, aWil; "wil"
0x180033ec3  mov     r9d, eax; char *
0x180033ec6  mov     edx, 137h; void *
0x180033ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ed0  lea     rcx, [rsp+280h+var_240]
0x180033ed5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033eda  lea     rcx, [rsp+280h+var_250]
0x180033edf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033ee4  mov     eax, ebx
0x180033ee6  jmp     loc_180033D6B
0x180033eeb  mov     rbx, [rsp+280h+var_250]
0x180033ef0  jmp     loc_180033E64
0x180033ef5  mov     rcx, rdi; this
0x180033ef8  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180033efd  jmp     loc_180033E6D
```
