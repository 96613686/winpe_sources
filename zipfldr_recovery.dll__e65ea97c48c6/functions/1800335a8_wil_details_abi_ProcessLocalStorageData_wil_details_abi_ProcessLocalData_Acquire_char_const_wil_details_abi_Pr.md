# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800335a8`
- end: `0x18003370e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180039ee0`

## callees

- `0x180022ee8`
- `0x180030cc0`
- `0x180031e94`
- `0x1800335a8`
- `0x1800338d8`
- `0x1800338f4`
- `0x180033928`
- `0x180036f50`
- `0x1800399fc`
- `0x18003a89c`
- `0x18003aa9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033625`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800335e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800335e0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, (unsigned int)"wil", (const char *)(unsigned int)Pointer);
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
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800335a8  mov     [rsp-8+arg_10], rbx
0x1800335ad  mov     [rsp-8+arg_18], rdi
0x1800335b2  push    rbp
0x1800335b3  lea     rbp, [rsp-170h]
0x1800335bb  sub     rsp, 270h
0x1800335c2  mov     rax, cs:__security_cookie
0x1800335c9  xor     rax, rsp
0x1800335cc  mov     [rbp+170h+var_10], rax
0x1800335d3  mov     rdi, rdx
0x1800335d6  mov     qword ptr [rdx], 0
0x1800335dd  mov     rbx, rcx
0x1800335e0  call    cs:__imp_GetCurrentProcessId
0x1800335e6  mov     [rsp+270h+var_248], rbx
0x1800335eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800335f2  mov     r9d, eax
0x1800335f5  mov     [rsp+270h+var_250], 78h ; 'x'
0x1800335fd  mov     edx, 104h; unsigned __int64
0x180033602  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033607  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003360c  mov     r9d, 1F0001h; dwDesiredAccess
0x180033612  mov     [rsp+270h+var_240], 0
0x18003361b  xor     r8d, r8d; dwFlags
0x18003361e  lea     rdx, [rsp+270h+Name]; lpName
0x180033623  xor     ecx, ecx; lpMutexAttributes
0x180033625  call    cs:__imp_CreateMutexExW
0x18003362b  mov     rdx, rax
0x18003362e  lea     rcx, [rsp+270h+var_240]
0x180033633  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180033638  cmp     [rsp+270h+var_240], 0
0x18003363e  jnz     short loc_180033649
0x180033640  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180033645  mov     ebx, eax
0x180033647  jmp     short loc_1800336BC
0x180033649  lea     rdx, [rsp+270h+var_238]
0x18003364e  lea     rcx, [rsp+270h+var_240]
0x180033653  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180033658  lea     rdx, [rsp+270h+var_230]; void **
0x18003365d  mov     [rsp+270h+var_230], 0
0x180033666  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003366b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180033670  mov     ebx, eax
0x180033672  test    eax, eax
0x180033674  jns     short loc_18003369D
0x180033676  mov     edx, 12Eh
0x18003367b  mov     rcx, [rbp+178h]
0x180033682  lea     r8, aWil; "wil"
0x180033689  mov     r9d, eax
0x18003368c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033691  lea     rcx, [rsp+270h+var_238]
0x180033696  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003369b  jmp     short loc_1800336BC
0x18003369d  mov     rcx, [rsp+270h+var_230]
0x1800336a2  test    rcx, rcx
0x1800336a5  jz      short loc_1800336EC
0x1800336a7  mov     [rdi], rcx
0x1800336aa  mov     eax, [rcx]
0x1800336ac  inc     eax
0x1800336ae  mov     [rcx], eax
0x1800336b0  lea     rcx, [rsp+270h+var_238]
0x1800336b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800336ba  xor     ebx, ebx
0x1800336bc  lea     rcx, [rsp+270h+var_240]
0x1800336c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800336c6  mov     eax, ebx
0x1800336c8  mov     rcx, [rbp+170h+var_10]
0x1800336cf  xor     rcx, rsp; StackCookie
0x1800336d2  call    __security_check_cookie
0x1800336d7  lea     r11, [rsp+270h+var_s0]
0x1800336df  mov     rbx, [r11+20h]
0x1800336e3  mov     rdi, [r11+28h]
0x1800336e7  mov     rsp, r11
0x1800336ea  pop     rbp
0x1800336eb  retn
0x1800336ec  mov     r8, rdi
0x1800336ef  lea     rdx, [rsp+270h+var_240]
0x1800336f4  lea     rcx, [rsp+270h+Name]
0x1800336f9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800336fe  mov     ebx, eax
0x180033700  test    eax, eax
0x180033702  jns     short loc_1800336B0
0x180033704  mov     edx, 137h
0x180033709  jmp     loc_18003367B
```
