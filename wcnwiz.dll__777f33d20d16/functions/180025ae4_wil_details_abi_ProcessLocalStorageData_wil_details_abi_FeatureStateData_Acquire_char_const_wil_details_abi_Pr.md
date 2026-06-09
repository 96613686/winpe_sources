# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180025ae4`
- end: `0x180025c43`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800262d4`

## callees

- `0x180001820`
- `0x180015d28`
- `0x1800222f8`
- `0x180022314`
- `0x180022ce8`
- `0x180023ce4`
- `0x180024528`
- `0x180024ac0`
- `0x180024bb0`
- `0x180025ae4`
- `0x1800265c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025b1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025b1c`
- `KERNEL32!CreateMutexExW` at `0x180025b61`
- `KERNEL32!CreateMutexExW` at `0x180025b61`

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
0x180025ae4  mov     [rsp-8+arg_10], rbx
0x180025ae9  mov     [rsp-8+arg_18], rdi
0x180025aee  push    rbp
0x180025aef  lea     rbp, [rsp-170h]
0x180025af7  sub     rsp, 270h
0x180025afe  mov     rax, cs:__security_cookie
0x180025b05  xor     rax, rsp
0x180025b08  mov     [rbp+170h+var_10], rax
0x180025b0f  mov     rdi, rdx
0x180025b12  mov     qword ptr [rdx], 0
0x180025b19  mov     rbx, rcx
0x180025b1c  call    cs:__imp_GetCurrentProcessId
0x180025b22  mov     [rsp+270h+var_248], rbx
0x180025b27  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180025b2e  mov     r9d, eax
0x180025b31  mov     [rsp+270h+var_250], 130h; int
0x180025b39  mov     edx, 104h; unsigned __int64
0x180025b3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025b43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025b48  mov     r9d, 1F0001h; dwDesiredAccess
0x180025b4e  mov     [rsp+270h+var_240], 0
0x180025b57  xor     r8d, r8d; dwFlags
0x180025b5a  lea     rdx, [rsp+270h+Name]; lpName
0x180025b5f  xor     ecx, ecx; lpMutexAttributes
0x180025b61  call    cs:__imp_CreateMutexExW
0x180025b67  mov     rdx, rax
0x180025b6a  lea     rcx, [rsp+270h+var_240]
0x180025b6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180025b74  cmp     [rsp+270h+var_240], 0
0x180025b7a  jnz     short loc_180025B85
0x180025b7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025b81  mov     ebx, eax
0x180025b83  jmp     short loc_180025BF1
0x180025b85  lea     rdx, [rsp+270h+var_238]
0x180025b8a  lea     rcx, [rsp+270h+var_240]
0x180025b8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180025b94  lea     rdx, [rsp+270h+var_230]; void **
0x180025b99  mov     [rsp+270h+var_230], 0
0x180025ba2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025ba7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180025bac  mov     ebx, eax
0x180025bae  test    eax, eax
0x180025bb0  jns     short loc_180025BD2
0x180025bb2  mov     edx, 12Eh; void *
0x180025bb7  mov     rcx, [rbp+178h]; this
0x180025bbe  mov     r9d, eax; char *
0x180025bc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025bc6  lea     rcx, [rsp+270h+var_238]
0x180025bcb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025bd0  jmp     short loc_180025BF1
0x180025bd2  mov     rcx, [rsp+270h+var_230]
0x180025bd7  test    rcx, rcx
0x180025bda  jz      short loc_180025C21
0x180025bdc  mov     [rdi], rcx
0x180025bdf  mov     eax, [rcx]
0x180025be1  inc     eax
0x180025be3  mov     [rcx], eax
0x180025be5  lea     rcx, [rsp+270h+var_238]
0x180025bea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025bef  xor     ebx, ebx
0x180025bf1  lea     rcx, [rsp+270h+var_240]
0x180025bf6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025bfb  mov     eax, ebx
0x180025bfd  mov     rcx, [rbp+170h+var_10]
0x180025c04  xor     rcx, rsp; StackCookie
0x180025c07  call    __security_check_cookie
0x180025c0c  lea     r11, [rsp+270h+var_s0]
0x180025c14  mov     rbx, [r11+20h]
0x180025c18  mov     rdi, [r11+28h]
0x180025c1c  mov     rsp, r11
0x180025c1f  pop     rbp
0x180025c20  retn
0x180025c21  mov     r8, rdi
0x180025c24  lea     rdx, [rsp+270h+var_240]
0x180025c29  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025c2e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180025c33  mov     ebx, eax
0x180025c35  test    eax, eax
0x180025c37  jns     short loc_180025BE5
0x180025c39  mov     edx, 137h
0x180025c3e  jmp     loc_180025BB7
```
