# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180041e2c`
- end: `0x180041fc2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `406`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180042448`

## callees

- `0x180003ac0`
- `0x18003c39c`
- `0x18003d270`
- `0x180041818`
- `0x180041838`
- `0x180041e2c`
- `0x1800443d8`
- `0x180045abc`
- `0x180048070`
- `0x180048974`
- `0x180048cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180041eaf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180041eaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180041e64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180041e64`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v9; // rcx
  int v11; // eax
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( Pointer >= 0 )
    {
      v9 = v14;
      if ( v14 )
      {
        *a2 = v14;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v11,
            304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180041e2c  mov     [rsp-8+arg_10], rbx
0x180041e31  mov     [rsp-8+arg_18], rdi
0x180041e36  push    rbp
0x180041e37  lea     rbp, [rsp-170h]
0x180041e3f  sub     rsp, 270h
0x180041e46  mov     rax, cs:__security_cookie
0x180041e4d  xor     rax, rsp
0x180041e50  mov     [rbp+170h+var_10], rax
0x180041e57  mov     rdi, rdx
0x180041e5a  mov     rbx, rcx
0x180041e5d  mov     qword ptr [rdx], 0
0x180041e64  call    cs:__imp_GetCurrentProcessId
0x180041e6b  nop     dword ptr [rax+rax+00h]
0x180041e70  mov     r9d, eax
0x180041e73  mov     [rsp+270h+var_248], rbx
0x180041e78  mov     [rsp+270h+var_250], 130h; int
0x180041e80  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180041e87  mov     edx, 104h; unsigned __int64
0x180041e8c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041e91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041e96  mov     [rsp+270h+var_240], 0
0x180041e9f  mov     r9d, 1F0001h; dwDesiredAccess
0x180041ea5  xor     r8d, r8d; dwFlags
0x180041ea8  lea     rdx, [rsp+270h+Name]; lpName
0x180041ead  xor     ecx, ecx; lpMutexAttributes
0x180041eaf  call    cs:__imp_CreateMutexExW
0x180041eb6  nop     dword ptr [rax+rax+00h]
0x180041ebb  mov     rdx, rax
0x180041ebe  lea     rcx, [rsp+270h+var_240]
0x180041ec3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180041ec8  cmp     [rsp+270h+var_240], 0
0x180041ece  jnz     short loc_180041ED9
0x180041ed0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180041ed5  mov     ebx, eax
0x180041ed7  jmp     short loc_180041F50
0x180041ed9  lea     rdx, [rsp+270h+var_238]
0x180041ede  lea     rcx, [rsp+270h+var_240]
0x180041ee3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180041ee8  nop
0x180041ee9  mov     [rsp+270h+var_230], 0
0x180041ef2  lea     rdx, [rsp+270h+var_230]; void **
0x180041ef7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041efc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180041f01  mov     ebx, eax
0x180041f03  test    eax, eax
0x180041f05  jns     short loc_180041F30
0x180041f07  mov     rcx, [rbp+178h]; this
0x180041f0e  mov     r9d, eax; char *
0x180041f11  lea     r8, aWil; "wil"
0x180041f18  mov     edx, 12Eh; void *
0x180041f1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041f22  nop
0x180041f23  lea     rcx, [rsp+270h+var_238]
0x180041f28  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041f2d  nop
0x180041f2e  jmp     short loc_180041F50
0x180041f30  mov     rcx, [rsp+270h+var_230]
0x180041f35  test    rcx, rcx
0x180041f38  jz      short loc_180041F81
0x180041f3a  mov     [rdi], rcx
0x180041f3d  mov     eax, [rcx]
0x180041f3f  inc     eax
0x180041f41  mov     [rcx], eax
0x180041f43  lea     rcx, [rsp+270h+var_238]
0x180041f48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041f4d  nop
0x180041f4e  xor     ebx, ebx
0x180041f50  lea     rcx, [rsp+270h+var_240]
0x180041f55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041f5a  mov     eax, ebx
0x180041f5c  mov     rcx, [rbp+170h+var_10]
0x180041f63  xor     rcx, rsp; StackCookie
0x180041f66  call    __security_check_cookie
0x180041f6b  lea     r11, [rsp+270h+var_s0]
0x180041f73  mov     rbx, [r11+20h]
0x180041f77  mov     rdi, [r11+28h]
0x180041f7b  mov     rsp, r11
0x180041f7e  pop     rbp
0x180041f7f  retn
0x180041f81  mov     r8, rdi
0x180041f84  lea     rdx, [rsp+270h+var_240]
0x180041f89  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041f8e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180041f93  mov     ebx, eax
0x180041f95  test    eax, eax
0x180041f97  jns     short loc_180041F43
0x180041f99  mov     rcx, [rbp+178h]; this
0x180041fa0  mov     r9d, eax; char *
0x180041fa3  lea     r8, aWil; "wil"
0x180041faa  mov     edx, 137h; void *
0x180041faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041fb4  nop
0x180041fb5  lea     rcx, [rsp+270h+var_238]
0x180041fba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041fbf  nop
0x180041fc0  jmp     short loc_180041F50
```
