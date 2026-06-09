# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006970`
- end: `0x180006acf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007790`

## callees

- `0x180002ae0`
- `0x1800063ec`
- `0x180006408`
- `0x180006970`
- `0x180007548`
- `0x180008304`
- `0x1800093ec`
- `0x180009b50`
- `0x180009e4c`
- `0x18000a53c`
- `0x18000a854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069ed`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069a8`

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
0x180006970  mov     [rsp-8+arg_10], rbx
0x180006975  mov     [rsp-8+arg_18], rdi
0x18000697a  push    rbp
0x18000697b  lea     rbp, [rsp-170h]
0x180006983  sub     rsp, 270h
0x18000698a  mov     rax, cs:__security_cookie
0x180006991  xor     rax, rsp
0x180006994  mov     [rbp+170h+var_10], rax
0x18000699b  mov     rdi, rdx
0x18000699e  mov     qword ptr [rdx], 0
0x1800069a5  mov     rbx, rcx
0x1800069a8  call    cs:__imp_GetCurrentProcessId
0x1800069ae  mov     [rsp+270h+var_248], rbx
0x1800069b3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800069ba  mov     r9d, eax
0x1800069bd  mov     [rsp+270h+var_250], 130h; int
0x1800069c5  mov     edx, 104h; unsigned __int64
0x1800069ca  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800069cf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800069d4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800069da  mov     [rsp+270h+var_240], 0
0x1800069e3  xor     r8d, r8d; dwFlags
0x1800069e6  lea     rdx, [rsp+270h+Name]; lpName
0x1800069eb  xor     ecx, ecx; lpMutexAttributes
0x1800069ed  call    cs:__imp_CreateMutexExW
0x1800069f3  mov     rdx, rax
0x1800069f6  lea     rcx, [rsp+270h+var_240]
0x1800069fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006a00  cmp     [rsp+270h+var_240], 0
0x180006a06  jnz     short loc_180006A11
0x180006a08  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006a0d  mov     ebx, eax
0x180006a0f  jmp     short loc_180006A7D
0x180006a11  lea     rdx, [rsp+270h+var_238]
0x180006a16  lea     rcx, [rsp+270h+var_240]
0x180006a1b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006a20  lea     rdx, [rsp+270h+var_230]; void **
0x180006a25  mov     [rsp+270h+var_230], 0
0x180006a2e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006a33  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006a38  mov     ebx, eax
0x180006a3a  test    eax, eax
0x180006a3c  jns     short loc_180006A5E
0x180006a3e  mov     edx, 12Eh; void *
0x180006a43  mov     rcx, [rbp+178h]; this
0x180006a4a  mov     r9d, eax; char *
0x180006a4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a52  lea     rcx, [rsp+270h+var_238]
0x180006a57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a5c  jmp     short loc_180006A7D
0x180006a5e  mov     rcx, [rsp+270h+var_230]
0x180006a63  test    rcx, rcx
0x180006a66  jz      short loc_180006AAD
0x180006a68  mov     [rdi], rcx
0x180006a6b  mov     eax, [rcx]
0x180006a6d  inc     eax
0x180006a6f  mov     [rcx], eax
0x180006a71  lea     rcx, [rsp+270h+var_238]
0x180006a76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a7b  xor     ebx, ebx
0x180006a7d  lea     rcx, [rsp+270h+var_240]
0x180006a82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a87  mov     eax, ebx
0x180006a89  mov     rcx, [rbp+170h+var_10]
0x180006a90  xor     rcx, rsp; StackCookie
0x180006a93  call    __security_check_cookie
0x180006a98  lea     r11, [rsp+270h+var_s0]
0x180006aa0  mov     rbx, [r11+20h]
0x180006aa4  mov     rdi, [r11+28h]
0x180006aa8  mov     rsp, r11
0x180006aab  pop     rbp
0x180006aac  retn
0x180006aad  mov     r8, rdi
0x180006ab0  lea     rdx, [rsp+270h+var_240]
0x180006ab5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006aba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006abf  mov     ebx, eax
0x180006ac1  test    eax, eax
0x180006ac3  jns     short loc_180006A71
0x180006ac5  mov     edx, 137h
0x180006aca  jmp     loc_180006A43
```
