# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008790`
- end: `0x1800088ef`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009188`

## callees

- `0x180002ae0`
- `0x180006aa4`
- `0x180008730`
- `0x18000874c`
- `0x180008790`
- `0x1800096fc`
- `0x180009b20`
- `0x180009f08`
- `0x18000a288`
- `0x18000a334`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000880d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000880d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800087c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800087c8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180008790  mov     [rsp-8+arg_10], rbx
0x180008795  mov     [rsp-8+arg_18], rdi
0x18000879a  push    rbp
0x18000879b  lea     rbp, [rsp-170h]
0x1800087a3  sub     rsp, 270h
0x1800087aa  mov     rax, cs:__security_cookie
0x1800087b1  xor     rax, rsp
0x1800087b4  mov     [rbp+170h+var_10], rax
0x1800087bb  mov     rdi, rdx
0x1800087be  mov     qword ptr [rdx], 0
0x1800087c5  mov     rbx, rcx
0x1800087c8  call    cs:__imp_GetCurrentProcessId
0x1800087ce  mov     [rsp+270h+var_248], rbx
0x1800087d3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800087da  mov     r9d, eax
0x1800087dd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800087e5  mov     edx, 104h; unsigned __int64
0x1800087ea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800087ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800087f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800087fa  mov     [rsp+270h+var_240], 0
0x180008803  xor     r8d, r8d; dwFlags
0x180008806  lea     rdx, [rsp+270h+Name]; lpName
0x18000880b  xor     ecx, ecx; lpMutexAttributes
0x18000880d  call    cs:__imp_CreateMutexExW
0x180008813  mov     rdx, rax
0x180008816  lea     rcx, [rsp+270h+var_240]
0x18000881b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008820  cmp     [rsp+270h+var_240], 0
0x180008826  jnz     short loc_180008831
0x180008828  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000882d  mov     ebx, eax
0x18000882f  jmp     short loc_18000889D
0x180008831  lea     rdx, [rsp+270h+var_238]
0x180008836  lea     rcx, [rsp+270h+var_240]
0x18000883b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008840  lea     rdx, [rsp+270h+var_230]; void **
0x180008845  mov     [rsp+270h+var_230], 0
0x18000884e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008853  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180008858  mov     ebx, eax
0x18000885a  test    eax, eax
0x18000885c  jns     short loc_18000887E
0x18000885e  mov     edx, 12Eh; void *
0x180008863  mov     rcx, [rbp+178h]; this
0x18000886a  mov     r9d, eax; char *
0x18000886d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008872  lea     rcx, [rsp+270h+var_238]
0x180008877  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000887c  jmp     short loc_18000889D
0x18000887e  mov     rcx, [rsp+270h+var_230]
0x180008883  test    rcx, rcx
0x180008886  jz      short loc_1800088CD
0x180008888  mov     [rdi], rcx
0x18000888b  mov     eax, [rcx]
0x18000888d  inc     eax
0x18000888f  mov     [rcx], eax
0x180008891  lea     rcx, [rsp+270h+var_238]
0x180008896  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000889b  xor     ebx, ebx
0x18000889d  lea     rcx, [rsp+270h+var_240]
0x1800088a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800088a7  mov     eax, ebx
0x1800088a9  mov     rcx, [rbp+170h+var_10]
0x1800088b0  xor     rcx, rsp; StackCookie
0x1800088b3  call    __security_check_cookie
0x1800088b8  lea     r11, [rsp+270h+var_s0]
0x1800088c0  mov     rbx, [r11+20h]
0x1800088c4  mov     rdi, [r11+28h]
0x1800088c8  mov     rsp, r11
0x1800088cb  pop     rbp
0x1800088cc  retn
0x1800088cd  mov     r8, rdi
0x1800088d0  lea     rdx, [rsp+270h+var_240]
0x1800088d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800088da  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800088df  mov     ebx, eax
0x1800088e1  test    eax, eax
0x1800088e3  jns     short loc_180008891
0x1800088e5  mov     edx, 137h
0x1800088ea  jmp     loc_180008863
```
