# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006928`
- end: `0x180006a87`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007850`

## callees

- `0x180002a70`
- `0x18000650c`
- `0x180006528`
- `0x180006928`
- `0x180007668`
- `0x1800082fc`
- `0x18000950c`
- `0x180009c70`
- `0x180009f6c`
- `0x18000a764`
- `0x18000aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006960`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180006928  mov     [rsp-8+arg_10], rbx
0x18000692d  mov     [rsp-8+arg_18], rdi
0x180006932  push    rbp
0x180006933  lea     rbp, [rsp-170h]
0x18000693b  sub     rsp, 270h
0x180006942  mov     rax, cs:__security_cookie
0x180006949  xor     rax, rsp
0x18000694c  mov     [rbp+170h+var_10], rax
0x180006953  mov     rdi, rdx
0x180006956  mov     qword ptr [rdx], 0
0x18000695d  mov     rbx, rcx
0x180006960  call    cs:__imp_GetCurrentProcessId
0x180006966  mov     [rsp+270h+var_248], rbx
0x18000696b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006972  mov     r9d, eax
0x180006975  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000697d  mov     edx, 104h; unsigned __int64
0x180006982  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006987  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000698c  mov     r9d, 1F0001h; dwDesiredAccess
0x180006992  mov     [rsp+270h+var_240], 0
0x18000699b  xor     r8d, r8d; dwFlags
0x18000699e  lea     rdx, [rsp+270h+Name]; lpName
0x1800069a3  xor     ecx, ecx; lpMutexAttributes
0x1800069a5  call    cs:__imp_CreateMutexExW
0x1800069ab  mov     rdx, rax
0x1800069ae  lea     rcx, [rsp+270h+var_240]
0x1800069b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800069b8  cmp     [rsp+270h+var_240], 0
0x1800069be  jnz     short loc_1800069C9
0x1800069c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800069c5  mov     ebx, eax
0x1800069c7  jmp     short loc_180006A35
0x1800069c9  lea     rdx, [rsp+270h+var_238]
0x1800069ce  lea     rcx, [rsp+270h+var_240]
0x1800069d3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800069d8  lea     rdx, [rsp+270h+var_230]; void **
0x1800069dd  mov     [rsp+270h+var_230], 0
0x1800069e6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800069eb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800069f0  mov     ebx, eax
0x1800069f2  test    eax, eax
0x1800069f4  jns     short loc_180006A16
0x1800069f6  mov     edx, 12Eh; void *
0x1800069fb  mov     rcx, [rbp+178h]; this
0x180006a02  mov     r9d, eax; char *
0x180006a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a0a  lea     rcx, [rsp+270h+var_238]
0x180006a0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a14  jmp     short loc_180006A35
0x180006a16  mov     rcx, [rsp+270h+var_230]
0x180006a1b  test    rcx, rcx
0x180006a1e  jz      short loc_180006A65
0x180006a20  mov     [rdi], rcx
0x180006a23  mov     eax, [rcx]
0x180006a25  inc     eax
0x180006a27  mov     [rcx], eax
0x180006a29  lea     rcx, [rsp+270h+var_238]
0x180006a2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a33  xor     ebx, ebx
0x180006a35  lea     rcx, [rsp+270h+var_240]
0x180006a3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a3f  mov     eax, ebx
0x180006a41  mov     rcx, [rbp+170h+var_10]
0x180006a48  xor     rcx, rsp; StackCookie
0x180006a4b  call    __security_check_cookie
0x180006a50  lea     r11, [rsp+270h+var_s0]
0x180006a58  mov     rbx, [r11+20h]
0x180006a5c  mov     rdi, [r11+28h]
0x180006a60  mov     rsp, r11
0x180006a63  pop     rbp
0x180006a64  retn
0x180006a65  mov     r8, rdi
0x180006a68  lea     rdx, [rsp+270h+var_240]
0x180006a6d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006a72  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006a77  mov     ebx, eax
0x180006a79  test    eax, eax
0x180006a7b  jns     short loc_180006A29
0x180006a7d  mov     edx, 137h
0x180006a82  jmp     loc_1800069FB
```
