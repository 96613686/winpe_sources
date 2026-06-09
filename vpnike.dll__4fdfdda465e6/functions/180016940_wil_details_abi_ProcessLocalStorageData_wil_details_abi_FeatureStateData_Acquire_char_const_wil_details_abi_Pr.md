# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180016940`
- end: `0x180016a9f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018d3c`

## callees

- `0x180016284`
- `0x1800162a0`
- `0x180016940`
- `0x180018918`
- `0x18001a43c`
- `0x18001e08c`
- `0x18001ee3c`
- `0x180020340`
- `0x18002065c`
- `0x180020bdc`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800169bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800169bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016978`

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
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
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
0x180016940  mov     [rsp-8+arg_10], rbx
0x180016945  mov     [rsp-8+arg_18], rdi
0x18001694a  push    rbp
0x18001694b  lea     rbp, [rsp-170h]
0x180016953  sub     rsp, 270h
0x18001695a  mov     rax, cs:__security_cookie
0x180016961  xor     rax, rsp
0x180016964  mov     [rbp+170h+var_10], rax
0x18001696b  mov     rdi, rdx
0x18001696e  mov     qword ptr [rdx], 0
0x180016975  mov     rbx, rcx
0x180016978  call    cs:__imp_GetCurrentProcessId
0x18001697e  mov     [rsp+270h+var_248], rbx
0x180016983  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001698a  mov     r9d, eax
0x18001698d  mov     [rsp+270h+var_250], 130h; int
0x180016995  mov     edx, 104h; cchDest
0x18001699a  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001699f  call    StringCchPrintfW
0x1800169a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800169aa  mov     [rsp+270h+var_240], 0
0x1800169b3  xor     r8d, r8d; dwFlags
0x1800169b6  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800169bb  xor     ecx, ecx; lpMutexAttributes
0x1800169bd  call    cs:__imp_CreateMutexExW
0x1800169c3  mov     rdx, rax
0x1800169c6  lea     rcx, [rsp+270h+var_240]
0x1800169cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800169d0  cmp     [rsp+270h+var_240], 0
0x1800169d6  jnz     short loc_1800169E1
0x1800169d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800169dd  mov     ebx, eax
0x1800169df  jmp     short loc_180016A4D
0x1800169e1  lea     rdx, [rsp+270h+var_238]
0x1800169e6  lea     rcx, [rsp+270h+var_240]
0x1800169eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800169f0  lea     rdx, [rsp+270h+var_230]; void **
0x1800169f5  mov     [rsp+270h+var_230], 0
0x1800169fe  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016a03  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180016a08  mov     ebx, eax
0x180016a0a  test    eax, eax
0x180016a0c  jns     short loc_180016A2E
0x180016a0e  mov     edx, 12Eh; void *
0x180016a13  mov     rcx, [rbp+178h]; this
0x180016a1a  mov     r9d, eax; char *
0x180016a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a22  lea     rcx, [rsp+270h+var_238]
0x180016a27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016a2c  jmp     short loc_180016A4D
0x180016a2e  mov     rcx, [rsp+270h+var_230]
0x180016a33  test    rcx, rcx
0x180016a36  jz      short loc_180016A7D
0x180016a38  mov     [rdi], rcx
0x180016a3b  mov     eax, [rcx]
0x180016a3d  inc     eax
0x180016a3f  mov     [rcx], eax
0x180016a41  lea     rcx, [rsp+270h+var_238]
0x180016a46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016a4b  xor     ebx, ebx
0x180016a4d  lea     rcx, [rsp+270h+var_240]
0x180016a52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016a57  mov     eax, ebx
0x180016a59  mov     rcx, [rbp+170h+var_10]
0x180016a60  xor     rcx, rsp; StackCookie
0x180016a63  call    __security_check_cookie
0x180016a68  lea     r11, [rsp+270h+var_s0]
0x180016a70  mov     rbx, [r11+20h]
0x180016a74  mov     rdi, [r11+28h]
0x180016a78  mov     rsp, r11
0x180016a7b  pop     rbp
0x180016a7c  retn
0x180016a7d  mov     r8, rdi
0x180016a80  lea     rdx, [rsp+270h+var_240]
0x180016a85  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016a8a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180016a8f  mov     ebx, eax
0x180016a91  test    eax, eax
0x180016a93  jns     short loc_180016A41
0x180016a95  mov     edx, 137h
0x180016a9a  jmp     loc_180016A13
```
