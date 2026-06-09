# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a37c`
- end: `0x18000a4db`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000acdc`

## callees

- `0x1800051f0`
- `0x18000520c`
- `0x180006138`
- `0x180007d24`
- `0x180008a0c`
- `0x180008b64`
- `0x18000950c`
- `0x1800096e0`
- `0x18000a37c`
- `0x18000b054`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a3f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a3f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3b4`

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
0x18000a37c  mov     [rsp-8+arg_10], rbx
0x18000a381  mov     [rsp-8+arg_18], rdi
0x18000a386  push    rbp
0x18000a387  lea     rbp, [rsp-170h]
0x18000a38f  sub     rsp, 270h
0x18000a396  mov     rax, cs:__security_cookie
0x18000a39d  xor     rax, rsp
0x18000a3a0  mov     [rbp+170h+var_10], rax
0x18000a3a7  mov     rdi, rdx
0x18000a3aa  mov     qword ptr [rdx], 0
0x18000a3b1  mov     rbx, rcx
0x18000a3b4  call    cs:__imp_GetCurrentProcessId
0x18000a3ba  mov     [rsp+270h+var_248], rbx
0x18000a3bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a3c6  mov     r9d, eax
0x18000a3c9  mov     [rsp+270h+var_250], 130h; int
0x18000a3d1  mov     edx, 104h; unsigned __int64
0x18000a3d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a3db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a3e0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a3e6  mov     [rsp+270h+var_240], 0
0x18000a3ef  xor     r8d, r8d; dwFlags
0x18000a3f2  lea     rdx, [rsp+270h+Name]; lpName
0x18000a3f7  xor     ecx, ecx; lpMutexAttributes
0x18000a3f9  call    cs:__imp_CreateMutexExW
0x18000a3ff  mov     rdx, rax
0x18000a402  lea     rcx, [rsp+270h+var_240]
0x18000a407  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a40c  cmp     [rsp+270h+var_240], 0
0x18000a412  jnz     short loc_18000A41D
0x18000a414  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a419  mov     ebx, eax
0x18000a41b  jmp     short loc_18000A489
0x18000a41d  lea     rdx, [rsp+270h+var_238]
0x18000a422  lea     rcx, [rsp+270h+var_240]
0x18000a427  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a42c  lea     rdx, [rsp+270h+var_230]; void **
0x18000a431  mov     [rsp+270h+var_230], 0
0x18000a43a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a43f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a444  mov     ebx, eax
0x18000a446  test    eax, eax
0x18000a448  jns     short loc_18000A46A
0x18000a44a  mov     edx, 12Eh; void *
0x18000a44f  mov     rcx, [rbp+178h]; this
0x18000a456  mov     r9d, eax; char *
0x18000a459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a45e  lea     rcx, [rsp+270h+var_238]
0x18000a463  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a468  jmp     short loc_18000A489
0x18000a46a  mov     rcx, [rsp+270h+var_230]
0x18000a46f  test    rcx, rcx
0x18000a472  jz      short loc_18000A4B9
0x18000a474  mov     [rdi], rcx
0x18000a477  mov     eax, [rcx]
0x18000a479  inc     eax
0x18000a47b  mov     [rcx], eax
0x18000a47d  lea     rcx, [rsp+270h+var_238]
0x18000a482  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a487  xor     ebx, ebx
0x18000a489  lea     rcx, [rsp+270h+var_240]
0x18000a48e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a493  mov     eax, ebx
0x18000a495  mov     rcx, [rbp+170h+var_10]
0x18000a49c  xor     rcx, rsp; StackCookie
0x18000a49f  call    __security_check_cookie
0x18000a4a4  lea     r11, [rsp+270h+var_s0]
0x18000a4ac  mov     rbx, [r11+20h]
0x18000a4b0  mov     rdi, [r11+28h]
0x18000a4b4  mov     rsp, r11
0x18000a4b7  pop     rbp
0x18000a4b8  retn
0x18000a4b9  mov     r8, rdi
0x18000a4bc  lea     rdx, [rsp+270h+var_240]
0x18000a4c1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a4c6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a4cb  mov     ebx, eax
0x18000a4cd  test    eax, eax
0x18000a4cf  jns     short loc_18000A47D
0x18000a4d1  mov     edx, 137h
0x18000a4d6  jmp     loc_18000A44F
```
