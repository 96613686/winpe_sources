# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003343c`
- end: `0x1800335a2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003c798`

## callees

- `0x180022ee8`
- `0x180030e6c`
- `0x180031e94`
- `0x18003343c`
- `0x1800338d8`
- `0x1800338f4`
- `0x180033928`
- `0x180036f50`
- `0x1800399fc`
- `0x18003a89c`
- `0x18003aa9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800334b9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800334b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033474`

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
0x18003343c  mov     [rsp-8+arg_10], rbx
0x180033441  mov     [rsp-8+arg_18], rdi
0x180033446  push    rbp
0x180033447  lea     rbp, [rsp-170h]
0x18003344f  sub     rsp, 270h
0x180033456  mov     rax, cs:__security_cookie
0x18003345d  xor     rax, rsp
0x180033460  mov     [rbp+170h+var_10], rax
0x180033467  mov     rdi, rdx
0x18003346a  mov     qword ptr [rdx], 0
0x180033471  mov     rbx, rcx
0x180033474  call    cs:__imp_GetCurrentProcessId
0x18003347a  mov     [rsp+270h+var_248], rbx
0x18003347f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180033486  mov     r9d, eax
0x180033489  mov     [rsp+270h+var_250], 130h; int
0x180033491  mov     edx, 104h; unsigned __int64
0x180033496  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003349b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800334a0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800334a6  mov     [rsp+270h+var_240], 0
0x1800334af  xor     r8d, r8d; dwFlags
0x1800334b2  lea     rdx, [rsp+270h+Name]; lpName
0x1800334b7  xor     ecx, ecx; lpMutexAttributes
0x1800334b9  call    cs:__imp_CreateMutexExW
0x1800334bf  mov     rdx, rax
0x1800334c2  lea     rcx, [rsp+270h+var_240]
0x1800334c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800334cc  cmp     [rsp+270h+var_240], 0
0x1800334d2  jnz     short loc_1800334DD
0x1800334d4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800334d9  mov     ebx, eax
0x1800334db  jmp     short loc_180033550
0x1800334dd  lea     rdx, [rsp+270h+var_238]
0x1800334e2  lea     rcx, [rsp+270h+var_240]
0x1800334e7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800334ec  lea     rdx, [rsp+270h+var_230]; void **
0x1800334f1  mov     [rsp+270h+var_230], 0
0x1800334fa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800334ff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180033504  mov     ebx, eax
0x180033506  test    eax, eax
0x180033508  jns     short loc_180033531
0x18003350a  mov     edx, 12Eh; void *
0x18003350f  mov     rcx, [rbp+178h]; this
0x180033516  lea     r8, aWil; "wil"
0x18003351d  mov     r9d, eax; char *
0x180033520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033525  lea     rcx, [rsp+270h+var_238]
0x18003352a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003352f  jmp     short loc_180033550
0x180033531  mov     rcx, [rsp+270h+var_230]
0x180033536  test    rcx, rcx
0x180033539  jz      short loc_180033580
0x18003353b  mov     [rdi], rcx
0x18003353e  mov     eax, [rcx]
0x180033540  inc     eax
0x180033542  mov     [rcx], eax
0x180033544  lea     rcx, [rsp+270h+var_238]
0x180033549  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003354e  xor     ebx, ebx
0x180033550  lea     rcx, [rsp+270h+var_240]
0x180033555  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003355a  mov     eax, ebx
0x18003355c  mov     rcx, [rbp+170h+var_10]
0x180033563  xor     rcx, rsp; StackCookie
0x180033566  call    __security_check_cookie
0x18003356b  lea     r11, [rsp+270h+var_s0]
0x180033573  mov     rbx, [r11+20h]
0x180033577  mov     rdi, [r11+28h]
0x18003357b  mov     rsp, r11
0x18003357e  pop     rbp
0x18003357f  retn
0x180033580  mov     r8, rdi
0x180033583  lea     rdx, [rsp+270h+var_240]
0x180033588  lea     rcx, [rsp+270h+Name]
0x18003358d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180033592  mov     ebx, eax
0x180033594  test    eax, eax
0x180033596  jns     short loc_180033544
0x180033598  mov     edx, 137h
0x18003359d  jmp     loc_18003350F
```
