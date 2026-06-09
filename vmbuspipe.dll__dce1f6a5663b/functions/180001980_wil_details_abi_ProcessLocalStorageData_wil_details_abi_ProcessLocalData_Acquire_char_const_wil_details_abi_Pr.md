# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180001980`
- end: `0x180001b3d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004de4`

## callees

- `0x180001980`
- `0x180001b44`
- `0x180001b68`
- `0x180002064`
- `0x1800024e0`
- `0x180004b44`
- `0x1800056bc`
- `0x180005d0c`
- `0x180006390`
- `0x180006558`
- `0x180006d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800019fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800019fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019b8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  void *v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  void *v13; // rdx
  _DWORD *v14; // rcx
  int v16; // eax
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v17 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v19 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v19,
    Mutex);
  if ( !v19 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_12;
  }
  v20 = 0;
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v19,
    &v20);
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v21, v8);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v18);
    v11 = LastErrorFailHr;
    v12 = 302;
    goto LABEL_5;
  }
  v14 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v14;
    ++*v14;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      v11 = (unsigned int)v16;
      v12 = 311;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v17);
      if ( v20 )
        wil::details::ReleaseMutex(v20, v13);
      goto LABEL_12;
    }
  }
  if ( v20 )
    wil::details::ReleaseMutex(v20, v10);
  LastErrorFailHr = 0;
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180001980  mov     [rsp-8+arg_10], rbx
0x180001985  mov     [rsp-8+arg_18], rdi
0x18000198a  push    rbp
0x18000198b  lea     rbp, [rsp-170h]
0x180001993  sub     rsp, 270h
0x18000199a  mov     rax, cs:__security_cookie
0x1800019a1  xor     rax, rsp
0x1800019a4  mov     [rbp+170h+var_10], rax
0x1800019ab  mov     rdi, rdx
0x1800019ae  mov     qword ptr [rdx], 0
0x1800019b5  mov     rbx, rcx
0x1800019b8  call    cs:__imp_GetCurrentProcessId
0x1800019be  mov     [rsp+270h+var_248], rbx
0x1800019c3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800019ca  mov     r9d, eax
0x1800019cd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800019d5  mov     edx, 104h; unsigned __int64
0x1800019da  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800019df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800019e4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800019ea  mov     [rsp+270h+var_240], 0
0x1800019f3  xor     r8d, r8d; dwFlags
0x1800019f6  lea     rdx, [rsp+270h+Name]; lpName
0x1800019fb  xor     ecx, ecx; lpMutexAttributes
0x1800019fd  call    cs:__imp_CreateMutexExW
0x180001a03  mov     rdx, rax
0x180001a06  lea     rcx, [rsp+270h+var_240]
0x180001a0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180001a10  cmp     [rsp+270h+var_240], 0
0x180001a16  jnz     short loc_180001A24
0x180001a18  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180001a1d  mov     ebx, eax
0x180001a1f  jmp     loc_180001AE8
0x180001a24  lea     rdx, [rsp+270h+var_238]
0x180001a29  mov     [rsp+270h+var_238], 0
0x180001a32  lea     rcx, [rsp+270h+var_240]
0x180001a37  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180001a3c  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180001a41  mov     [rsp+270h+var_230], 0
0x180001a4a  lea     rcx, [rsp+270h+Name]; pszSrc
0x180001a4f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180001a54  mov     ebx, eax
0x180001a56  test    eax, eax
0x180001a58  jns     short loc_180001ABC
0x180001a5a  mov     rcx, [rbp+178h]; this
0x180001a61  lea     r8, aWil; "wil"
0x180001a68  mov     r9d, eax; char *
0x180001a6b  mov     edx, 66h ; 'f'; void *
0x180001a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001a75  mov     rcx, [rbp+178h]; this
0x180001a7c  lea     r8, aWil; "wil"
0x180001a83  mov     r9d, ebx; char *
0x180001a86  mov     edx, 6Fh ; 'o'; void *
0x180001a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001a90  mov     r9d, ebx; char *
0x180001a93  mov     edx, 12Eh; void *
0x180001a98  mov     rcx, [rbp+178h]; this
0x180001a9f  lea     r8, aWil; "wil"
0x180001aa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001aab  mov     rcx, [rsp+270h+var_238]; this
0x180001ab0  test    rcx, rcx
0x180001ab3  jz      short loc_180001AE8
0x180001ab5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180001aba  jmp     short loc_180001AE8
0x180001abc  mov     rax, [rsp+270h+var_230]
0x180001ac1  lea     rcx, ds:0[rax*4]
0x180001ac9  test    rcx, rcx
0x180001acc  jz      short loc_180001B18
0x180001ace  mov     [rdi], rcx
0x180001ad1  mov     eax, [rcx]
0x180001ad3  inc     eax
0x180001ad5  mov     [rcx], eax
0x180001ad7  mov     rcx, [rsp+270h+var_238]; this
0x180001adc  test    rcx, rcx
0x180001adf  jz      short loc_180001AE6
0x180001ae1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180001ae6  xor     ebx, ebx
0x180001ae8  lea     rcx, [rsp+270h+var_240]
0x180001aed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180001af2  mov     eax, ebx
0x180001af4  mov     rcx, [rbp+170h+var_10]
0x180001afb  xor     rcx, rsp; StackCookie
0x180001afe  call    __security_check_cookie
0x180001b03  lea     r11, [rsp+270h+var_s0]
0x180001b0b  mov     rbx, [r11+20h]
0x180001b0f  mov     rdi, [r11+28h]
0x180001b13  mov     rsp, r11
0x180001b16  pop     rbp
0x180001b17  retn
0x180001b18  mov     r8, rdi
0x180001b1b  lea     rdx, [rsp+270h+var_240]
0x180001b20  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180001b25  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180001b2a  mov     ebx, eax
0x180001b2c  test    eax, eax
0x180001b2e  jns     short loc_180001AD7
0x180001b30  mov     r9d, eax
0x180001b33  mov     edx, 137h
0x180001b38  jmp     loc_180001A98
```
