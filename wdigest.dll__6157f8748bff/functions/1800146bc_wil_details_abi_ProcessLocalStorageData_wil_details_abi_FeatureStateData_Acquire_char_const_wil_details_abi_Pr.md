# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800146bc`
- end: `0x18001481b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015118`

## callees

- `0x1800120a4`
- `0x180012880`
- `0x1800143d8`
- `0x1800143f4`
- `0x1800146bc`
- `0x180015a1c`
- `0x1800160c0`
- `0x180016428`
- `0x1800166e0`
- `0x180016e94`
- `0x180016f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014739`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014739`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800146f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800146f4`

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
0x1800146bc  mov     [rsp-8+arg_10], rbx
0x1800146c1  mov     [rsp-8+arg_18], rdi
0x1800146c6  push    rbp
0x1800146c7  lea     rbp, [rsp-170h]
0x1800146cf  sub     rsp, 270h
0x1800146d6  mov     rax, cs:__security_cookie
0x1800146dd  xor     rax, rsp
0x1800146e0  mov     [rbp+170h+var_10], rax
0x1800146e7  mov     rdi, rdx
0x1800146ea  mov     qword ptr [rdx], 0
0x1800146f1  mov     rbx, rcx
0x1800146f4  call    cs:__imp_GetCurrentProcessId
0x1800146fa  mov     [rsp+270h+var_248], rbx
0x1800146ff  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014706  mov     r9d, eax
0x180014709  mov     [rsp+270h+var_250], 130h; int
0x180014711  mov     edx, 104h; unsigned __int64
0x180014716  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001471b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014720  mov     r9d, 1F0001h; dwDesiredAccess
0x180014726  mov     [rsp+270h+var_240], 0
0x18001472f  xor     r8d, r8d; dwFlags
0x180014732  lea     rdx, [rsp+270h+Name]; lpName
0x180014737  xor     ecx, ecx; lpMutexAttributes
0x180014739  call    cs:__imp_CreateMutexExW
0x18001473f  mov     rdx, rax
0x180014742  lea     rcx, [rsp+270h+var_240]
0x180014747  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001474c  cmp     [rsp+270h+var_240], 0
0x180014752  jnz     short loc_18001475D
0x180014754  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014759  mov     ebx, eax
0x18001475b  jmp     short loc_1800147C9
0x18001475d  lea     rdx, [rsp+270h+var_238]
0x180014762  lea     rcx, [rsp+270h+var_240]
0x180014767  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001476c  lea     rdx, [rsp+270h+var_230]; void **
0x180014771  mov     [rsp+270h+var_230], 0
0x18001477a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001477f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180014784  mov     ebx, eax
0x180014786  test    eax, eax
0x180014788  jns     short loc_1800147AA
0x18001478a  mov     edx, 12Eh; void *
0x18001478f  mov     rcx, [rbp+178h]; this
0x180014796  mov     r9d, eax; char *
0x180014799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001479e  lea     rcx, [rsp+270h+var_238]
0x1800147a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800147a8  jmp     short loc_1800147C9
0x1800147aa  mov     rcx, [rsp+270h+var_230]
0x1800147af  test    rcx, rcx
0x1800147b2  jz      short loc_1800147F9
0x1800147b4  mov     [rdi], rcx
0x1800147b7  mov     eax, [rcx]
0x1800147b9  inc     eax
0x1800147bb  mov     [rcx], eax
0x1800147bd  lea     rcx, [rsp+270h+var_238]
0x1800147c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800147c7  xor     ebx, ebx
0x1800147c9  lea     rcx, [rsp+270h+var_240]
0x1800147ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800147d3  mov     eax, ebx
0x1800147d5  mov     rcx, [rbp+170h+var_10]
0x1800147dc  xor     rcx, rsp; StackCookie
0x1800147df  call    __security_check_cookie
0x1800147e4  lea     r11, [rsp+270h+var_s0]
0x1800147ec  mov     rbx, [r11+20h]
0x1800147f0  mov     rdi, [r11+28h]
0x1800147f4  mov     rsp, r11
0x1800147f7  pop     rbp
0x1800147f8  retn
0x1800147f9  mov     r8, rdi
0x1800147fc  lea     rdx, [rsp+270h+var_240]
0x180014801  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014806  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001480b  mov     ebx, eax
0x18001480d  test    eax, eax
0x18001480f  jns     short loc_1800147BD
0x180014811  mov     edx, 137h
0x180014816  jmp     loc_18001478F
```
