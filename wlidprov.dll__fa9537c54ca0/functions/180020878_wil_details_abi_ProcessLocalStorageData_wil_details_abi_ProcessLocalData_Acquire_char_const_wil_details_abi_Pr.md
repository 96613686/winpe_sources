# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180020878`
- end: `0x1800209de`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180021450`

## callees

- `0x180011010`
- `0x180015a04`
- `0x18001648c`
- `0x180016758`
- `0x18001a0d0`
- `0x18002070c`
- `0x180020728`
- `0x180020878`
- `0x180022438`
- `0x1800228c0`
- `0x1800229b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800208f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800208f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800208b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800208b0`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180020878  mov     [rsp-8+arg_10], rbx
0x18002087d  mov     [rsp-8+arg_18], rdi
0x180020882  push    rbp
0x180020883  lea     rbp, [rsp-170h]
0x18002088b  sub     rsp, 270h
0x180020892  mov     rax, cs:__security_cookie
0x180020899  xor     rax, rsp
0x18002089c  mov     [rbp+170h+var_10], rax
0x1800208a3  mov     rdi, rdx
0x1800208a6  mov     qword ptr [rdx], 0
0x1800208ad  mov     rbx, rcx
0x1800208b0  call    cs:__imp_GetCurrentProcessId
0x1800208b6  mov     [rsp+270h+var_248], rbx
0x1800208bb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800208c2  mov     r9d, eax
0x1800208c5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800208cd  mov     edx, 104h; unsigned __int64
0x1800208d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800208d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800208dc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800208e2  mov     [rsp+270h+var_240], 0
0x1800208eb  xor     r8d, r8d; dwFlags
0x1800208ee  lea     rdx, [rsp+270h+Name]; lpName
0x1800208f3  xor     ecx, ecx; lpMutexAttributes
0x1800208f5  call    cs:__imp_CreateMutexExW
0x1800208fb  mov     rdx, rax
0x1800208fe  lea     rcx, [rsp+270h+var_240]
0x180020903  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020908  cmp     [rsp+270h+var_240], 0
0x18002090e  jnz     short loc_180020919
0x180020910  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020915  mov     ebx, eax
0x180020917  jmp     short loc_18002098C
0x180020919  lea     rdx, [rsp+270h+var_238]
0x18002091e  lea     rcx, [rsp+270h+var_240]
0x180020923  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180020928  lea     rdx, [rsp+270h+var_230]; void **
0x18002092d  mov     [rsp+270h+var_230], 0
0x180020936  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002093b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180020940  mov     ebx, eax
0x180020942  test    eax, eax
0x180020944  jns     short loc_18002096D
0x180020946  mov     edx, 12Eh; void *
0x18002094b  mov     rcx, [rbp+178h]; this
0x180020952  lea     r8, aWil; "wil"
0x180020959  mov     r9d, eax; char *
0x18002095c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020961  lea     rcx, [rsp+270h+var_238]
0x180020966  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002096b  jmp     short loc_18002098C
0x18002096d  mov     rcx, [rsp+270h+var_230]
0x180020972  test    rcx, rcx
0x180020975  jz      short loc_1800209BC
0x180020977  mov     [rdi], rcx
0x18002097a  mov     eax, [rcx]
0x18002097c  inc     eax
0x18002097e  mov     [rcx], eax
0x180020980  lea     rcx, [rsp+270h+var_238]
0x180020985  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002098a  xor     ebx, ebx
0x18002098c  lea     rcx, [rsp+270h+var_240]
0x180020991  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020996  mov     eax, ebx
0x180020998  mov     rcx, [rbp+170h+var_10]
0x18002099f  xor     rcx, rsp; StackCookie
0x1800209a2  call    __security_check_cookie
0x1800209a7  lea     r11, [rsp+270h+var_s0]
0x1800209af  mov     rbx, [r11+20h]
0x1800209b3  mov     rdi, [r11+28h]
0x1800209b7  mov     rsp, r11
0x1800209ba  pop     rbp
0x1800209bb  retn
0x1800209bc  mov     r8, rdi
0x1800209bf  lea     rdx, [rsp+270h+var_240]
0x1800209c4  lea     rcx, [rsp+270h+Name]
0x1800209c9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800209ce  mov     ebx, eax
0x1800209d0  test    eax, eax
0x1800209d2  jns     short loc_180020980
0x1800209d4  mov     edx, 137h
0x1800209d9  jmp     loc_18002094B
```
