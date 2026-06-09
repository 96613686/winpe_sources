# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006a7c`
- end: `0x180006be8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007ae4`

## callees

- `0x180002ad0`
- `0x180006644`
- `0x180006664`
- `0x180006a7c`
- `0x1800078e0`
- `0x1800085dc`
- `0x18000983c`
- `0x180009fd0`
- `0x18000a26c`
- `0x18000aaa4`
- `0x18000ad54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006aff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab4`

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
0x180006a7c  mov     [rsp-8+arg_10], rbx
0x180006a81  mov     [rsp-8+arg_18], rdi
0x180006a86  push    rbp
0x180006a87  lea     rbp, [rsp-170h]
0x180006a8f  sub     rsp, 270h
0x180006a96  mov     rax, cs:__security_cookie
0x180006a9d  xor     rax, rsp
0x180006aa0  mov     [rbp+170h+var_10], rax
0x180006aa7  mov     rdi, rdx
0x180006aaa  mov     qword ptr [rdx], 0
0x180006ab1  mov     rbx, rcx
0x180006ab4  call    cs:__imp_GetCurrentProcessId
0x180006abb  nop     dword ptr [rax+rax+00h]
0x180006ac0  mov     [rsp+270h+var_248], rbx
0x180006ac5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006acc  mov     r9d, eax
0x180006acf  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006ad7  mov     edx, 104h; unsigned __int64
0x180006adc  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006ae1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006ae6  mov     r9d, 1F0001h; dwDesiredAccess
0x180006aec  mov     [rsp+270h+var_240], 0
0x180006af5  xor     r8d, r8d; dwFlags
0x180006af8  lea     rdx, [rsp+270h+Name]; lpName
0x180006afd  xor     ecx, ecx; lpMutexAttributes
0x180006aff  call    cs:__imp_CreateMutexExW
0x180006b06  nop     dword ptr [rax+rax+00h]
0x180006b0b  mov     rdx, rax
0x180006b0e  lea     rcx, [rsp+270h+var_240]
0x180006b13  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006b18  cmp     [rsp+270h+var_240], 0
0x180006b1e  jnz     short loc_180006B29
0x180006b20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006b25  mov     ebx, eax
0x180006b27  jmp     short loc_180006B95
0x180006b29  lea     rdx, [rsp+270h+var_238]
0x180006b2e  lea     rcx, [rsp+270h+var_240]
0x180006b33  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006b38  lea     rdx, [rsp+270h+var_230]; void **
0x180006b3d  mov     [rsp+270h+var_230], 0
0x180006b46  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006b4b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006b50  mov     ebx, eax
0x180006b52  test    eax, eax
0x180006b54  jns     short loc_180006B76
0x180006b56  mov     edx, 12Eh; void *
0x180006b5b  mov     rcx, [rbp+178h]; this
0x180006b62  mov     r9d, eax; char *
0x180006b65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b6a  lea     rcx, [rsp+270h+var_238]
0x180006b6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006b74  jmp     short loc_180006B95
0x180006b76  mov     rcx, [rsp+270h+var_230]
0x180006b7b  test    rcx, rcx
0x180006b7e  jz      short loc_180006BC6
0x180006b80  mov     [rdi], rcx
0x180006b83  mov     eax, [rcx]
0x180006b85  inc     eax
0x180006b87  mov     [rcx], eax
0x180006b89  lea     rcx, [rsp+270h+var_238]
0x180006b8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006b93  xor     ebx, ebx
0x180006b95  lea     rcx, [rsp+270h+var_240]
0x180006b9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006b9f  mov     eax, ebx
0x180006ba1  mov     rcx, [rbp+170h+var_10]
0x180006ba8  xor     rcx, rsp; StackCookie
0x180006bab  call    __security_check_cookie
0x180006bb0  lea     r11, [rsp+270h+var_s0]
0x180006bb8  mov     rbx, [r11+20h]
0x180006bbc  mov     rdi, [r11+28h]
0x180006bc0  mov     rsp, r11
0x180006bc3  pop     rbp
0x180006bc4  retn
0x180006bc6  mov     r8, rdi
0x180006bc9  lea     rdx, [rsp+270h+var_240]
0x180006bce  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006bd3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006bd8  mov     ebx, eax
0x180006bda  test    eax, eax
0x180006bdc  jns     short loc_180006B89
0x180006bde  mov     edx, 137h
0x180006be3  jmp     loc_180006B5B
```
