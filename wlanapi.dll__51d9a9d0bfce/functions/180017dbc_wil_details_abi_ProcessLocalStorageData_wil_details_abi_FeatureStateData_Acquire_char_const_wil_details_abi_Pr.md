# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180017dbc`
- end: `0x180017f22`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800226d0`

## callees

- `0x1800052a0`
- `0x1800147d4`
- `0x180017dbc`
- `0x180018094`
- `0x1800180b0`
- `0x180018288`
- `0x18001830c`
- `0x180018e74`
- `0x1800193b0`
- `0x180019a20`
- `0x180024408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017df4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017e39`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017e39`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180017dbc  mov     [rsp-8+arg_10], rbx
0x180017dc1  mov     [rsp-8+arg_18], rdi
0x180017dc6  push    rbp
0x180017dc7  lea     rbp, [rsp-170h]
0x180017dcf  sub     rsp, 270h
0x180017dd6  mov     rax, cs:__security_cookie
0x180017ddd  xor     rax, rsp
0x180017de0  mov     [rbp+170h+var_10], rax
0x180017de7  mov     rdi, rdx
0x180017dea  mov     qword ptr [rdx], 0
0x180017df1  mov     rbx, rcx
0x180017df4  call    cs:__imp_GetCurrentProcessId
0x180017dfa  mov     [rsp+270h+var_248], rbx
0x180017dff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017e06  mov     r9d, eax
0x180017e09  mov     [rsp+270h+var_250], 130h; int
0x180017e11  mov     edx, 104h; unsigned __int64
0x180017e16  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017e1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017e20  mov     r9d, 1F0001h; dwDesiredAccess
0x180017e26  mov     [rsp+270h+var_240], 0
0x180017e2f  xor     r8d, r8d; dwFlags
0x180017e32  lea     rdx, [rsp+270h+Name]; lpName
0x180017e37  xor     ecx, ecx; lpMutexAttributes
0x180017e39  call    cs:__imp_CreateMutexExW
0x180017e3f  mov     rdx, rax
0x180017e42  lea     rcx, [rsp+270h+var_240]
0x180017e47  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017e4c  cmp     [rsp+270h+var_240], 0
0x180017e52  jnz     short loc_180017E5D
0x180017e54  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017e59  mov     ebx, eax
0x180017e5b  jmp     short loc_180017ED0
0x180017e5d  lea     rdx, [rsp+270h+var_238]
0x180017e62  lea     rcx, [rsp+270h+var_240]
0x180017e67  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180017e6c  lea     rdx, [rsp+270h+var_230]; void **
0x180017e71  mov     [rsp+270h+var_230], 0
0x180017e7a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017e7f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180017e84  mov     ebx, eax
0x180017e86  test    eax, eax
0x180017e88  jns     short loc_180017EB1
0x180017e8a  mov     edx, 12Eh; void *
0x180017e8f  mov     rcx, [rbp+178h]; this
0x180017e96  lea     r8, aWil; "wil"
0x180017e9d  mov     r9d, eax; char *
0x180017ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ea5  lea     rcx, [rsp+270h+var_238]
0x180017eaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017eaf  jmp     short loc_180017ED0
0x180017eb1  mov     rcx, [rsp+270h+var_230]
0x180017eb6  test    rcx, rcx
0x180017eb9  jz      short loc_180017F00
0x180017ebb  mov     [rdi], rcx
0x180017ebe  mov     eax, [rcx]
0x180017ec0  inc     eax
0x180017ec2  mov     [rcx], eax
0x180017ec4  lea     rcx, [rsp+270h+var_238]
0x180017ec9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017ece  xor     ebx, ebx
0x180017ed0  lea     rcx, [rsp+270h+var_240]
0x180017ed5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017eda  mov     eax, ebx
0x180017edc  mov     rcx, [rbp+170h+var_10]
0x180017ee3  xor     rcx, rsp; StackCookie
0x180017ee6  call    __security_check_cookie
0x180017eeb  lea     r11, [rsp+270h+var_s0]
0x180017ef3  mov     rbx, [r11+20h]
0x180017ef7  mov     rdi, [r11+28h]
0x180017efb  mov     rsp, r11
0x180017efe  pop     rbp
0x180017eff  retn
0x180017f00  mov     r8, rdi
0x180017f03  lea     rdx, [rsp+270h+var_240]
0x180017f08  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017f0d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180017f12  mov     ebx, eax
0x180017f14  test    eax, eax
0x180017f16  jns     short loc_180017EC4
0x180017f18  mov     edx, 137h
0x180017f1d  jmp     loc_180017E8F
```
