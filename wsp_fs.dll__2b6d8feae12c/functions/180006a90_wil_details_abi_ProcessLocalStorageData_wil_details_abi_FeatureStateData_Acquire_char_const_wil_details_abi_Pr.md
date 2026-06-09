# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006a90`
- end: `0x180006bef`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800078b0`

## callees

- `0x180002a70`
- `0x18000650c`
- `0x180006528`
- `0x180006a90`
- `0x180007668`
- `0x180008424`
- `0x18000950c`
- `0x180009c70`
- `0x180009f6c`
- `0x18000a764`
- `0x18000aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006b0d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ac8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ac8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006a90  mov     [rsp-8+arg_10], rbx
0x180006a95  mov     [rsp-8+arg_18], rdi
0x180006a9a  push    rbp
0x180006a9b  lea     rbp, [rsp-170h]
0x180006aa3  sub     rsp, 270h
0x180006aaa  mov     rax, cs:__security_cookie
0x180006ab1  xor     rax, rsp
0x180006ab4  mov     [rbp+170h+var_10], rax
0x180006abb  mov     rdi, rdx
0x180006abe  mov     qword ptr [rdx], 0
0x180006ac5  mov     rbx, rcx
0x180006ac8  call    cs:__imp_GetCurrentProcessId
0x180006ace  mov     [rsp+270h+var_248], rbx
0x180006ad3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006ada  mov     r9d, eax
0x180006add  mov     [rsp+270h+var_250], 130h; int
0x180006ae5  mov     edx, 104h; unsigned __int64
0x180006aea  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006aef  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006af4  mov     r9d, 1F0001h; dwDesiredAccess
0x180006afa  mov     [rsp+270h+var_240], 0
0x180006b03  xor     r8d, r8d; dwFlags
0x180006b06  lea     rdx, [rsp+270h+Name]; lpName
0x180006b0b  xor     ecx, ecx; lpMutexAttributes
0x180006b0d  call    cs:__imp_CreateMutexExW
0x180006b13  mov     rdx, rax
0x180006b16  lea     rcx, [rsp+270h+var_240]
0x180006b1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006b20  cmp     [rsp+270h+var_240], 0
0x180006b26  jnz     short loc_180006B31
0x180006b28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006b2d  mov     ebx, eax
0x180006b2f  jmp     short loc_180006B9D
0x180006b31  lea     rdx, [rsp+270h+var_238]
0x180006b36  lea     rcx, [rsp+270h+var_240]
0x180006b3b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006b40  lea     rdx, [rsp+270h+var_230]; void **
0x180006b45  mov     [rsp+270h+var_230], 0
0x180006b4e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006b53  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006b58  mov     ebx, eax
0x180006b5a  test    eax, eax
0x180006b5c  jns     short loc_180006B7E
0x180006b5e  mov     edx, 12Eh; void *
0x180006b63  mov     rcx, [rbp+178h]; this
0x180006b6a  mov     r9d, eax; char *
0x180006b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b72  lea     rcx, [rsp+270h+var_238]
0x180006b77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006b7c  jmp     short loc_180006B9D
0x180006b7e  mov     rcx, [rsp+270h+var_230]
0x180006b83  test    rcx, rcx
0x180006b86  jz      short loc_180006BCD
0x180006b88  mov     [rdi], rcx
0x180006b8b  mov     eax, [rcx]
0x180006b8d  inc     eax
0x180006b8f  mov     [rcx], eax
0x180006b91  lea     rcx, [rsp+270h+var_238]
0x180006b96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006b9b  xor     ebx, ebx
0x180006b9d  lea     rcx, [rsp+270h+var_240]
0x180006ba2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006ba7  mov     eax, ebx
0x180006ba9  mov     rcx, [rbp+170h+var_10]
0x180006bb0  xor     rcx, rsp; StackCookie
0x180006bb3  call    __security_check_cookie
0x180006bb8  lea     r11, [rsp+270h+var_s0]
0x180006bc0  mov     rbx, [r11+20h]
0x180006bc4  mov     rdi, [r11+28h]
0x180006bc8  mov     rsp, r11
0x180006bcb  pop     rbp
0x180006bcc  retn
0x180006bcd  mov     r8, rdi
0x180006bd0  lea     rdx, [rsp+270h+var_240]
0x180006bd5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006bda  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006bdf  mov     ebx, eax
0x180006be1  test    eax, eax
0x180006be3  jns     short loc_180006B91
0x180006be5  mov     edx, 137h
0x180006bea  jmp     loc_180006B63
```
