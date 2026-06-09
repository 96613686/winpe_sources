# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180029e44`
- end: `0x180029fa3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002adf4`

## callees

- `0x180023dc8`
- `0x180024a50`
- `0x180029c48`
- `0x180029c64`
- `0x180029e44`
- `0x18002b640`
- `0x18002c40c`
- `0x18002c928`
- `0x18002cd20`
- `0x18002d504`
- `0x18002d640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029ec1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180029ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029e7c`

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
0x180029e44  mov     [rsp-8+arg_10], rbx
0x180029e49  mov     [rsp-8+arg_18], rdi
0x180029e4e  push    rbp
0x180029e4f  lea     rbp, [rsp-170h]
0x180029e57  sub     rsp, 270h
0x180029e5e  mov     rax, cs:__security_cookie
0x180029e65  xor     rax, rsp
0x180029e68  mov     [rbp+170h+var_10], rax
0x180029e6f  mov     rdi, rdx
0x180029e72  mov     qword ptr [rdx], 0
0x180029e79  mov     rbx, rcx
0x180029e7c  call    cs:__imp_GetCurrentProcessId
0x180029e82  mov     [rsp+270h+var_248], rbx
0x180029e87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029e8e  mov     r9d, eax
0x180029e91  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180029e99  mov     edx, 104h; unsigned __int64
0x180029e9e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029ea3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029ea8  mov     r9d, 1F0001h; dwDesiredAccess
0x180029eae  mov     [rsp+270h+var_240], 0
0x180029eb7  xor     r8d, r8d; dwFlags
0x180029eba  lea     rdx, [rsp+270h+Name]; lpName
0x180029ebf  xor     ecx, ecx; lpMutexAttributes
0x180029ec1  call    cs:__imp_CreateMutexExW
0x180029ec7  mov     rdx, rax
0x180029eca  lea     rcx, [rsp+270h+var_240]
0x180029ecf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029ed4  cmp     [rsp+270h+var_240], 0
0x180029eda  jnz     short loc_180029EE5
0x180029edc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029ee1  mov     ebx, eax
0x180029ee3  jmp     short loc_180029F51
0x180029ee5  lea     rdx, [rsp+270h+var_238]
0x180029eea  lea     rcx, [rsp+270h+var_240]
0x180029eef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180029ef4  lea     rdx, [rsp+270h+var_230]; void **
0x180029ef9  mov     [rsp+270h+var_230], 0
0x180029f02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029f07  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180029f0c  mov     ebx, eax
0x180029f0e  test    eax, eax
0x180029f10  jns     short loc_180029F32
0x180029f12  mov     edx, 12Eh; void *
0x180029f17  mov     rcx, [rbp+178h]; this
0x180029f1e  mov     r9d, eax; char *
0x180029f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f26  lea     rcx, [rsp+270h+var_238]
0x180029f2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029f30  jmp     short loc_180029F51
0x180029f32  mov     rcx, [rsp+270h+var_230]
0x180029f37  test    rcx, rcx
0x180029f3a  jz      short loc_180029F81
0x180029f3c  mov     [rdi], rcx
0x180029f3f  mov     eax, [rcx]
0x180029f41  inc     eax
0x180029f43  mov     [rcx], eax
0x180029f45  lea     rcx, [rsp+270h+var_238]
0x180029f4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029f4f  xor     ebx, ebx
0x180029f51  lea     rcx, [rsp+270h+var_240]
0x180029f56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029f5b  mov     eax, ebx
0x180029f5d  mov     rcx, [rbp+170h+var_10]
0x180029f64  xor     rcx, rsp; StackCookie
0x180029f67  call    __security_check_cookie
0x180029f6c  lea     r11, [rsp+270h+var_s0]
0x180029f74  mov     rbx, [r11+20h]
0x180029f78  mov     rdi, [r11+28h]
0x180029f7c  mov     rsp, r11
0x180029f7f  pop     rbp
0x180029f80  retn
0x180029f81  mov     r8, rdi
0x180029f84  lea     rdx, [rsp+270h+var_240]
0x180029f89  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180029f8e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180029f93  mov     ebx, eax
0x180029f95  test    eax, eax
0x180029f97  jns     short loc_180029F45
0x180029f99  mov     edx, 137h
0x180029f9e  jmp     loc_180029F17
```
