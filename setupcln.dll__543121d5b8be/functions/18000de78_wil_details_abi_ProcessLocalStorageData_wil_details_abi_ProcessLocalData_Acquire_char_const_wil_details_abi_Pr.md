# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000de78`
- end: `0x18000dfda`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000efdc`

## callees

- `0x180007f88`
- `0x18000d998`
- `0x18000d9b4`
- `0x18000de78`
- `0x18000ebb8`
- `0x18000fa94`
- `0x180010cdc`
- `0x18001176c`
- `0x180011e44`
- `0x180012718`
- `0x1800131e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000def5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000def5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000deb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000deb0`

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
0x18000de78  mov     [rsp-8+arg_10], rbx
0x18000de7d  mov     [rsp-8+arg_18], rdi
0x18000de82  push    rbp
0x18000de83  lea     rbp, [rsp-170h]
0x18000de8b  sub     rsp, 270h
0x18000de92  mov     rax, cs:__security_cookie
0x18000de99  xor     rax, rsp
0x18000de9c  mov     [rbp+170h+var_10], rax
0x18000dea3  mov     rdi, rdx
0x18000dea6  mov     rbx, rcx
0x18000dea9  mov     qword ptr [rdx], 0
0x18000deb0  call    cs:__imp_GetCurrentProcessId
0x18000deb6  mov     r9d, eax
0x18000deb9  mov     [rsp+270h+var_248], rbx
0x18000debe  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000dec6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000decd  mov     edx, 104h; unsigned __int64
0x18000ded2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ded7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dedc  mov     [rsp+270h+var_240], 0
0x18000dee5  mov     r9d, 1F0001h; dwDesiredAccess
0x18000deeb  xor     r8d, r8d; dwFlags
0x18000deee  lea     rdx, [rsp+270h+Name]; lpName
0x18000def3  xor     ecx, ecx; lpMutexAttributes
0x18000def5  call    cs:__imp_CreateMutexExW
0x18000defb  mov     rdx, rax
0x18000defe  lea     rcx, [rsp+270h+var_240]
0x18000df03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000df08  cmp     [rsp+270h+var_240], 0
0x18000df0e  jnz     short loc_18000DF19
0x18000df10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000df15  mov     ebx, eax
0x18000df17  jmp     short loc_18000DF87
0x18000df19  lea     rdx, [rsp+270h+var_238]
0x18000df1e  lea     rcx, [rsp+270h+var_240]
0x18000df23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000df28  nop
0x18000df29  mov     [rsp+270h+var_230], 0
0x18000df32  lea     rdx, [rsp+270h+var_230]; void **
0x18000df37  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000df3c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000df41  mov     ebx, eax
0x18000df43  test    eax, eax
0x18000df45  jns     short loc_18000DF68
0x18000df47  mov     edx, 12Eh; void *
0x18000df4c  mov     r9d, eax; char *
0x18000df4f  mov     rcx, [rbp+178h]; this
0x18000df56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df5b  nop
0x18000df5c  lea     rcx, [rsp+270h+var_238]
0x18000df61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000df66  jmp     short loc_18000DF87
0x18000df68  mov     rcx, [rsp+270h+var_230]
0x18000df6d  test    rcx, rcx
0x18000df70  jz      short loc_18000DFB7
0x18000df72  mov     [rdi], rcx
0x18000df75  mov     eax, [rcx]
0x18000df77  inc     eax
0x18000df79  mov     [rcx], eax
0x18000df7b  lea     rcx, [rsp+270h+var_238]
0x18000df80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000df85  xor     ebx, ebx
0x18000df87  lea     rcx, [rsp+270h+var_240]
0x18000df8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000df91  mov     eax, ebx
0x18000df93  mov     rcx, [rbp+170h+var_10]
0x18000df9a  xor     rcx, rsp; StackCookie
0x18000df9d  call    __security_check_cookie
0x18000dfa2  lea     r11, [rsp+270h+var_s0]
0x18000dfaa  mov     rbx, [r11+20h]
0x18000dfae  mov     rdi, [r11+28h]
0x18000dfb2  mov     rsp, r11
0x18000dfb5  pop     rbp
0x18000dfb6  retn
0x18000dfb7  mov     r8, rdi
0x18000dfba  lea     rdx, [rsp+270h+var_240]
0x18000dfbf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000dfc4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000dfc9  mov     ebx, eax
0x18000dfcb  test    eax, eax
0x18000dfcd  jns     short loc_18000DF7B
0x18000dfcf  mov     edx, 137h
0x18000dfd4  jmp     loc_18000DF4C
```
