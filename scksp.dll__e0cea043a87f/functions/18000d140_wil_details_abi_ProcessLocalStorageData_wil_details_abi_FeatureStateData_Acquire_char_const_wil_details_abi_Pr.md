# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000d140`
- end: `0x18000d2a2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e610`

## callees

- `0x18000cc00`
- `0x18000cc1c`
- `0x18000d140`
- `0x18000e3c8`
- `0x18000f3fc`
- `0x180010c8c`
- `0x18001147c`
- `0x180011900`
- `0x18001232c`
- `0x18001265c`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d178`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d1bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d1bd`

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
0x18000d140  mov     [rsp-8+arg_10], rbx
0x18000d145  mov     [rsp-8+arg_18], rdi
0x18000d14a  push    rbp
0x18000d14b  lea     rbp, [rsp-170h]
0x18000d153  sub     rsp, 270h
0x18000d15a  mov     rax, cs:__security_cookie
0x18000d161  xor     rax, rsp
0x18000d164  mov     [rbp+170h+var_10], rax
0x18000d16b  mov     rdi, rdx
0x18000d16e  mov     rbx, rcx
0x18000d171  mov     qword ptr [rdx], 0
0x18000d178  call    cs:__imp_GetCurrentProcessId
0x18000d17e  mov     r9d, eax
0x18000d181  mov     [rsp+270h+var_248], rbx
0x18000d186  mov     [rsp+270h+var_250], 130h; int
0x18000d18e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d195  mov     edx, 104h; unsigned __int64
0x18000d19a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d19f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d1a4  mov     [rsp+270h+var_240], 0
0x18000d1ad  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d1b3  xor     r8d, r8d; dwFlags
0x18000d1b6  lea     rdx, [rsp+270h+Name]; lpName
0x18000d1bb  xor     ecx, ecx; lpMutexAttributes
0x18000d1bd  call    cs:__imp_CreateMutexExW
0x18000d1c3  mov     rdx, rax
0x18000d1c6  lea     rcx, [rsp+270h+var_240]
0x18000d1cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000d1d0  cmp     [rsp+270h+var_240], 0
0x18000d1d6  jnz     short loc_18000D1E1
0x18000d1d8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d1dd  mov     ebx, eax
0x18000d1df  jmp     short loc_18000D24F
0x18000d1e1  lea     rdx, [rsp+270h+var_238]
0x18000d1e6  lea     rcx, [rsp+270h+var_240]
0x18000d1eb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000d1f0  nop
0x18000d1f1  mov     [rsp+270h+var_230], 0
0x18000d1fa  lea     rdx, [rsp+270h+var_230]; void **
0x18000d1ff  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d204  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000d209  mov     ebx, eax
0x18000d20b  test    eax, eax
0x18000d20d  jns     short loc_18000D230
0x18000d20f  mov     edx, 12Eh; void *
0x18000d214  mov     r9d, eax; char *
0x18000d217  mov     rcx, [rbp+178h]; this
0x18000d21e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d223  nop
0x18000d224  lea     rcx, [rsp+270h+var_238]
0x18000d229  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d22e  jmp     short loc_18000D24F
0x18000d230  mov     rcx, [rsp+270h+var_230]
0x18000d235  test    rcx, rcx
0x18000d238  jz      short loc_18000D27F
0x18000d23a  mov     [rdi], rcx
0x18000d23d  mov     eax, [rcx]
0x18000d23f  inc     eax
0x18000d241  mov     [rcx], eax
0x18000d243  lea     rcx, [rsp+270h+var_238]
0x18000d248  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d24d  xor     ebx, ebx
0x18000d24f  lea     rcx, [rsp+270h+var_240]
0x18000d254  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d259  mov     eax, ebx
0x18000d25b  mov     rcx, [rbp+170h+var_10]
0x18000d262  xor     rcx, rsp; StackCookie
0x18000d265  call    __security_check_cookie
0x18000d26a  lea     r11, [rsp+270h+var_s0]
0x18000d272  mov     rbx, [r11+20h]
0x18000d276  mov     rdi, [r11+28h]
0x18000d27a  mov     rsp, r11
0x18000d27d  pop     rbp
0x18000d27e  retn
0x18000d27f  mov     r8, rdi
0x18000d282  lea     rdx, [rsp+270h+var_240]
0x18000d287  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d28c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d291  mov     ebx, eax
0x18000d293  test    eax, eax
0x18000d295  jns     short loc_18000D243
0x18000d297  mov     edx, 137h
0x18000d29c  jmp     loc_18000D214
```
