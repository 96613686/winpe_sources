# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800106d8`
- end: `0x18001083e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010acc`

## callees

- `0x180006b24`
- `0x18000cb08`
- `0x18000cea0`
- `0x18000d9b0`
- `0x180010658`
- `0x180010674`
- `0x1800106d8`
- `0x180010fec`
- `0x180011508`
- `0x180011858`
- `0x180011918`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010710`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010755`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010755`

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
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800106d8  mov     [rsp-8+arg_10], rbx
0x1800106dd  mov     [rsp-8+arg_18], rdi
0x1800106e2  push    rbp
0x1800106e3  lea     rbp, [rsp-170h]
0x1800106eb  sub     rsp, 270h
0x1800106f2  mov     rax, cs:__security_cookie
0x1800106f9  xor     rax, rsp
0x1800106fc  mov     [rbp+170h+var_10], rax
0x180010703  mov     rdi, rdx
0x180010706  mov     qword ptr [rdx], 0
0x18001070d  mov     rbx, rcx
0x180010710  call    cs:__imp_GetCurrentProcessId
0x180010716  mov     [rsp+270h+var_248], rbx
0x18001071b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010722  mov     r9d, eax
0x180010725  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001072d  mov     edx, 104h; unsigned __int64
0x180010732  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010737  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001073c  mov     r9d, 1F0001h; dwDesiredAccess
0x180010742  mov     [rsp+270h+var_240], 0
0x18001074b  xor     r8d, r8d; dwFlags
0x18001074e  lea     rdx, [rsp+270h+Name]; lpName
0x180010753  xor     ecx, ecx; lpMutexAttributes
0x180010755  call    cs:__imp_CreateMutexExW
0x18001075b  mov     rdx, rax
0x18001075e  lea     rcx, [rsp+270h+var_240]
0x180010763  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010768  cmp     [rsp+270h+var_240], 0
0x18001076e  jnz     short loc_180010779
0x180010770  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010775  mov     ebx, eax
0x180010777  jmp     short loc_1800107EC
0x180010779  lea     rdx, [rsp+270h+var_238]
0x18001077e  lea     rcx, [rsp+270h+var_240]
0x180010783  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180010788  lea     rdx, [rsp+270h+var_230]; void **
0x18001078d  mov     [rsp+270h+var_230], 0
0x180010796  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001079b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800107a0  mov     ebx, eax
0x1800107a2  test    eax, eax
0x1800107a4  jns     short loc_1800107CD
0x1800107a6  mov     edx, 12Eh; void *
0x1800107ab  mov     rcx, [rbp+178h]; this
0x1800107b2  lea     r8, aWil; "wil"
0x1800107b9  mov     r9d, eax; char *
0x1800107bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107c1  lea     rcx, [rsp+270h+var_238]
0x1800107c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107cb  jmp     short loc_1800107EC
0x1800107cd  mov     rcx, [rsp+270h+var_230]
0x1800107d2  test    rcx, rcx
0x1800107d5  jz      short loc_18001081C
0x1800107d7  mov     [rdi], rcx
0x1800107da  mov     eax, [rcx]
0x1800107dc  inc     eax
0x1800107de  mov     [rcx], eax
0x1800107e0  lea     rcx, [rsp+270h+var_238]
0x1800107e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107ea  xor     ebx, ebx
0x1800107ec  lea     rcx, [rsp+270h+var_240]
0x1800107f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800107f6  mov     eax, ebx
0x1800107f8  mov     rcx, [rbp+170h+var_10]
0x1800107ff  xor     rcx, rsp; StackCookie
0x180010802  call    __security_check_cookie
0x180010807  lea     r11, [rsp+270h+var_s0]
0x18001080f  mov     rbx, [r11+20h]
0x180010813  mov     rdi, [r11+28h]
0x180010817  mov     rsp, r11
0x18001081a  pop     rbp
0x18001081b  retn
0x18001081c  mov     r8, rdi
0x18001081f  lea     rdx, [rsp+270h+var_240]
0x180010824  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010829  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001082e  mov     ebx, eax
0x180010830  test    eax, eax
0x180010832  jns     short loc_1800107E0
0x180010834  mov     edx, 137h
0x180010839  jmp     loc_1800107AB
```
