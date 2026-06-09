# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007568`
- end: `0x1800076c7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008b38`

## callees

- `0x180003ea4`
- `0x180004410`
- `0x180004b7c`
- `0x180005320`
- `0x180007310`
- `0x18000732c`
- `0x180007568`
- `0x18000ae48`
- `0x18000b21c`
- `0x18000bb80`
- `0x18000bdb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800075e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800075e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800075a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800075a0`

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
0x180007568  mov     [rsp-8+arg_10], rbx
0x18000756d  mov     [rsp-8+arg_18], rdi
0x180007572  push    rbp
0x180007573  lea     rbp, [rsp-170h]
0x18000757b  sub     rsp, 270h
0x180007582  mov     rax, cs:__security_cookie
0x180007589  xor     rax, rsp
0x18000758c  mov     [rbp+170h+var_10], rax
0x180007593  mov     rdi, rdx
0x180007596  mov     qword ptr [rdx], 0
0x18000759d  mov     rbx, rcx
0x1800075a0  call    cs:__imp_GetCurrentProcessId
0x1800075a6  mov     [rsp+270h+var_248], rbx
0x1800075ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800075b2  mov     r9d, eax
0x1800075b5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800075bd  mov     edx, 104h; unsigned __int64
0x1800075c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800075c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800075cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800075d2  mov     [rsp+270h+var_240], 0
0x1800075db  xor     r8d, r8d; dwFlags
0x1800075de  lea     rdx, [rsp+270h+Name]; lpName
0x1800075e3  xor     ecx, ecx; lpMutexAttributes
0x1800075e5  call    cs:__imp_CreateMutexExW
0x1800075eb  mov     rdx, rax
0x1800075ee  lea     rcx, [rsp+270h+var_240]
0x1800075f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800075f8  cmp     [rsp+270h+var_240], 0
0x1800075fe  jnz     short loc_180007609
0x180007600  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007605  mov     ebx, eax
0x180007607  jmp     short loc_180007675
0x180007609  lea     rdx, [rsp+270h+var_238]
0x18000760e  lea     rcx, [rsp+270h+var_240]
0x180007613  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007618  lea     rdx, [rsp+270h+var_230]; void **
0x18000761d  mov     [rsp+270h+var_230], 0
0x180007626  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000762b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007630  mov     ebx, eax
0x180007632  test    eax, eax
0x180007634  jns     short loc_180007656
0x180007636  mov     edx, 12Eh; void *
0x18000763b  mov     rcx, [rbp+178h]; this
0x180007642  mov     r9d, eax; char *
0x180007645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000764a  lea     rcx, [rsp+270h+var_238]
0x18000764f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007654  jmp     short loc_180007675
0x180007656  mov     rcx, [rsp+270h+var_230]
0x18000765b  test    rcx, rcx
0x18000765e  jz      short loc_1800076A5
0x180007660  mov     [rdi], rcx
0x180007663  mov     eax, [rcx]
0x180007665  inc     eax
0x180007667  mov     [rcx], eax
0x180007669  lea     rcx, [rsp+270h+var_238]
0x18000766e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007673  xor     ebx, ebx
0x180007675  lea     rcx, [rsp+270h+var_240]
0x18000767a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000767f  mov     eax, ebx
0x180007681  mov     rcx, [rbp+170h+var_10]
0x180007688  xor     rcx, rsp; StackCookie
0x18000768b  call    __security_check_cookie
0x180007690  lea     r11, [rsp+270h+var_s0]
0x180007698  mov     rbx, [r11+20h]
0x18000769c  mov     rdi, [r11+28h]
0x1800076a0  mov     rsp, r11
0x1800076a3  pop     rbp
0x1800076a4  retn
0x1800076a5  mov     r8, rdi
0x1800076a8  lea     rdx, [rsp+270h+var_240]
0x1800076ad  lea     rcx, [rsp+270h+Name]
0x1800076b2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800076b7  mov     ebx, eax
0x1800076b9  test    eax, eax
0x1800076bb  jns     short loc_180007669
0x1800076bd  mov     edx, 137h
0x1800076c2  jmp     loc_18000763B
```
