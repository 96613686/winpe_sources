# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006bf0`
- end: `0x180006d5c`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007b44`

## callees

- `0x180002ad0`
- `0x180006644`
- `0x180006664`
- `0x180006bf0`
- `0x1800078e0`
- `0x180008704`
- `0x18000983c`
- `0x180009fd0`
- `0x18000a26c`
- `0x18000aaa4`
- `0x18000ad54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006c73`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c28`

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
0x180006bf0  mov     [rsp-8+arg_10], rbx
0x180006bf5  mov     [rsp-8+arg_18], rdi
0x180006bfa  push    rbp
0x180006bfb  lea     rbp, [rsp-170h]
0x180006c03  sub     rsp, 270h
0x180006c0a  mov     rax, cs:__security_cookie
0x180006c11  xor     rax, rsp
0x180006c14  mov     [rbp+170h+var_10], rax
0x180006c1b  mov     rdi, rdx
0x180006c1e  mov     qword ptr [rdx], 0
0x180006c25  mov     rbx, rcx
0x180006c28  call    cs:__imp_GetCurrentProcessId
0x180006c2f  nop     dword ptr [rax+rax+00h]
0x180006c34  mov     [rsp+270h+var_248], rbx
0x180006c39  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006c40  mov     r9d, eax
0x180006c43  mov     [rsp+270h+var_250], 130h; int
0x180006c4b  mov     edx, 104h; unsigned __int64
0x180006c50  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006c55  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006c5a  mov     r9d, 1F0001h; dwDesiredAccess
0x180006c60  mov     [rsp+270h+var_240], 0
0x180006c69  xor     r8d, r8d; dwFlags
0x180006c6c  lea     rdx, [rsp+270h+Name]; lpName
0x180006c71  xor     ecx, ecx; lpMutexAttributes
0x180006c73  call    cs:__imp_CreateMutexExW
0x180006c7a  nop     dword ptr [rax+rax+00h]
0x180006c7f  mov     rdx, rax
0x180006c82  lea     rcx, [rsp+270h+var_240]
0x180006c87  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006c8c  cmp     [rsp+270h+var_240], 0
0x180006c92  jnz     short loc_180006C9D
0x180006c94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006c99  mov     ebx, eax
0x180006c9b  jmp     short loc_180006D09
0x180006c9d  lea     rdx, [rsp+270h+var_238]
0x180006ca2  lea     rcx, [rsp+270h+var_240]
0x180006ca7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006cac  lea     rdx, [rsp+270h+var_230]; void **
0x180006cb1  mov     [rsp+270h+var_230], 0
0x180006cba  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006cbf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006cc4  mov     ebx, eax
0x180006cc6  test    eax, eax
0x180006cc8  jns     short loc_180006CEA
0x180006cca  mov     edx, 12Eh; void *
0x180006ccf  mov     rcx, [rbp+178h]; this
0x180006cd6  mov     r9d, eax; char *
0x180006cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cde  lea     rcx, [rsp+270h+var_238]
0x180006ce3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006ce8  jmp     short loc_180006D09
0x180006cea  mov     rcx, [rsp+270h+var_230]
0x180006cef  test    rcx, rcx
0x180006cf2  jz      short loc_180006D3A
0x180006cf4  mov     [rdi], rcx
0x180006cf7  mov     eax, [rcx]
0x180006cf9  inc     eax
0x180006cfb  mov     [rcx], eax
0x180006cfd  lea     rcx, [rsp+270h+var_238]
0x180006d02  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006d07  xor     ebx, ebx
0x180006d09  lea     rcx, [rsp+270h+var_240]
0x180006d0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006d13  mov     eax, ebx
0x180006d15  mov     rcx, [rbp+170h+var_10]
0x180006d1c  xor     rcx, rsp; StackCookie
0x180006d1f  call    __security_check_cookie
0x180006d24  lea     r11, [rsp+270h+var_s0]
0x180006d2c  mov     rbx, [r11+20h]
0x180006d30  mov     rdi, [r11+28h]
0x180006d34  mov     rsp, r11
0x180006d37  pop     rbp
0x180006d38  retn
0x180006d3a  mov     r8, rdi
0x180006d3d  lea     rdx, [rsp+270h+var_240]
0x180006d42  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006d47  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006d4c  mov     ebx, eax
0x180006d4e  test    eax, eax
0x180006d50  jns     short loc_180006CFD
0x180006d52  mov     edx, 137h
0x180006d57  jmp     loc_180006CCF
```
