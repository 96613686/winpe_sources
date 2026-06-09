# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800114e8`
- end: `0x18001165b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001198c`

## callees

- `0x180007008`
- `0x18000d848`
- `0x18000db08`
- `0x18000e640`
- `0x18001145c`
- `0x18001147c`
- `0x1800114e8`
- `0x180011efc`
- `0x180012448`
- `0x1800127ac`
- `0x180012880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011520`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001156b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001156b`

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
0x1800114e8  mov     [rsp-8+arg_10], rbx
0x1800114ed  mov     [rsp-8+arg_18], rdi
0x1800114f2  push    rbp
0x1800114f3  lea     rbp, [rsp-170h]
0x1800114fb  sub     rsp, 270h
0x180011502  mov     rax, cs:__security_cookie
0x180011509  xor     rax, rsp
0x18001150c  mov     [rbp+170h+var_10], rax
0x180011513  mov     rdi, rdx
0x180011516  mov     qword ptr [rdx], 0
0x18001151d  mov     rbx, rcx
0x180011520  call    cs:__imp_GetCurrentProcessId
0x180011527  nop     dword ptr [rax+rax+00h]
0x18001152c  mov     [rsp+270h+var_248], rbx
0x180011531  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011538  mov     r9d, eax
0x18001153b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180011543  mov     edx, 104h; unsigned __int64
0x180011548  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001154d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011552  mov     r9d, 1F0001h; dwDesiredAccess
0x180011558  mov     [rsp+270h+var_240], 0
0x180011561  xor     r8d, r8d; dwFlags
0x180011564  lea     rdx, [rsp+270h+Name]; lpName
0x180011569  xor     ecx, ecx; lpMutexAttributes
0x18001156b  call    cs:__imp_CreateMutexExW
0x180011572  nop     dword ptr [rax+rax+00h]
0x180011577  mov     rdx, rax
0x18001157a  lea     rcx, [rsp+270h+var_240]
0x18001157f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011584  cmp     [rsp+270h+var_240], 0
0x18001158a  jnz     short loc_180011595
0x18001158c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011591  mov     ebx, eax
0x180011593  jmp     short loc_180011608
0x180011595  lea     rdx, [rsp+270h+var_238]
0x18001159a  lea     rcx, [rsp+270h+var_240]
0x18001159f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800115a4  lea     rdx, [rsp+270h+var_230]; void **
0x1800115a9  mov     [rsp+270h+var_230], 0
0x1800115b2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800115b7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800115bc  mov     ebx, eax
0x1800115be  test    eax, eax
0x1800115c0  jns     short loc_1800115E9
0x1800115c2  mov     edx, 12Eh; void *
0x1800115c7  mov     rcx, [rbp+178h]; this
0x1800115ce  lea     r8, aWil; "wil"
0x1800115d5  mov     r9d, eax; char *
0x1800115d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115dd  lea     rcx, [rsp+270h+var_238]
0x1800115e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800115e7  jmp     short loc_180011608
0x1800115e9  mov     rcx, [rsp+270h+var_230]
0x1800115ee  test    rcx, rcx
0x1800115f1  jz      short loc_180011639
0x1800115f3  mov     [rdi], rcx
0x1800115f6  mov     eax, [rcx]
0x1800115f8  inc     eax
0x1800115fa  mov     [rcx], eax
0x1800115fc  lea     rcx, [rsp+270h+var_238]
0x180011601  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011606  xor     ebx, ebx
0x180011608  lea     rcx, [rsp+270h+var_240]
0x18001160d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011612  mov     eax, ebx
0x180011614  mov     rcx, [rbp+170h+var_10]
0x18001161b  xor     rcx, rsp; StackCookie
0x18001161e  call    __security_check_cookie
0x180011623  lea     r11, [rsp+270h+var_s0]
0x18001162b  mov     rbx, [r11+20h]
0x18001162f  mov     rdi, [r11+28h]
0x180011633  mov     rsp, r11
0x180011636  pop     rbp
0x180011637  retn
0x180011639  mov     r8, rdi
0x18001163c  lea     rdx, [rsp+270h+var_240]
0x180011641  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011646  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001164b  mov     ebx, eax
0x18001164d  test    eax, eax
0x18001164f  jns     short loc_1800115FC
0x180011651  mov     edx, 137h
0x180011656  jmp     loc_1800115C7
```
