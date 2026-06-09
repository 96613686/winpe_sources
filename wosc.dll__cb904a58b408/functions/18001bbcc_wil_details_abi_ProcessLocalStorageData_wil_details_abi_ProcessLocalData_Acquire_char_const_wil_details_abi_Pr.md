# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001bbcc`
- end: `0x18001bd32`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001c7ec`

## callees

- `0x180003110`
- `0x18000e5ac`
- `0x18001b6cc`
- `0x18001b6e8`
- `0x18001bbcc`
- `0x18001c464`
- `0x18001ccc8`
- `0x18001e7e4`
- `0x18001eb3c`
- `0x18001f744`
- `0x18001f88c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bc49`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bc49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bc04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bc04`

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
0x18001bbcc  mov     [rsp-8+arg_10], rbx
0x18001bbd1  mov     [rsp-8+arg_18], rdi
0x18001bbd6  push    rbp
0x18001bbd7  lea     rbp, [rsp-170h]
0x18001bbdf  sub     rsp, 270h
0x18001bbe6  mov     rax, cs:__security_cookie
0x18001bbed  xor     rax, rsp
0x18001bbf0  mov     [rbp+170h+var_10], rax
0x18001bbf7  mov     rdi, rdx
0x18001bbfa  mov     qword ptr [rdx], 0
0x18001bc01  mov     rbx, rcx
0x18001bc04  call    cs:__imp_GetCurrentProcessId
0x18001bc0a  mov     [rsp+270h+var_248], rbx
0x18001bc0f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001bc16  mov     r9d, eax
0x18001bc19  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001bc21  mov     edx, 104h; unsigned __int64
0x18001bc26  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bc2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bc30  mov     r9d, 1F0001h; dwDesiredAccess
0x18001bc36  mov     [rsp+270h+var_240], 0
0x18001bc3f  xor     r8d, r8d; dwFlags
0x18001bc42  lea     rdx, [rsp+270h+Name]; lpName
0x18001bc47  xor     ecx, ecx; lpMutexAttributes
0x18001bc49  call    cs:__imp_CreateMutexExW
0x18001bc4f  mov     rdx, rax
0x18001bc52  lea     rcx, [rsp+270h+var_240]
0x18001bc57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001bc5c  cmp     [rsp+270h+var_240], 0
0x18001bc62  jnz     short loc_18001BC6D
0x18001bc64  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001bc69  mov     ebx, eax
0x18001bc6b  jmp     short loc_18001BCE0
0x18001bc6d  lea     rdx, [rsp+270h+var_238]
0x18001bc72  lea     rcx, [rsp+270h+var_240]
0x18001bc77  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001bc7c  lea     rdx, [rsp+270h+var_230]; void **
0x18001bc81  mov     [rsp+270h+var_230], 0
0x18001bc8a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bc8f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001bc94  mov     ebx, eax
0x18001bc96  test    eax, eax
0x18001bc98  jns     short loc_18001BCC1
0x18001bc9a  mov     edx, 12Eh; void *
0x18001bc9f  mov     rcx, [rbp+178h]; this
0x18001bca6  lea     r8, aWil; "wil"
0x18001bcad  mov     r9d, eax; char *
0x18001bcb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcb5  lea     rcx, [rsp+270h+var_238]
0x18001bcba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bcbf  jmp     short loc_18001BCE0
0x18001bcc1  mov     rcx, [rsp+270h+var_230]
0x18001bcc6  test    rcx, rcx
0x18001bcc9  jz      short loc_18001BD10
0x18001bccb  mov     [rdi], rcx
0x18001bcce  mov     eax, [rcx]
0x18001bcd0  inc     eax
0x18001bcd2  mov     [rcx], eax
0x18001bcd4  lea     rcx, [rsp+270h+var_238]
0x18001bcd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bcde  xor     ebx, ebx
0x18001bce0  lea     rcx, [rsp+270h+var_240]
0x18001bce5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001bcea  mov     eax, ebx
0x18001bcec  mov     rcx, [rbp+170h+var_10]
0x18001bcf3  xor     rcx, rsp; StackCookie
0x18001bcf6  call    __security_check_cookie
0x18001bcfb  lea     r11, [rsp+270h+var_s0]
0x18001bd03  mov     rbx, [r11+20h]
0x18001bd07  mov     rdi, [r11+28h]
0x18001bd0b  mov     rsp, r11
0x18001bd0e  pop     rbp
0x18001bd0f  retn
0x18001bd10  mov     r8, rdi
0x18001bd13  lea     rdx, [rsp+270h+var_240]
0x18001bd18  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bd1d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001bd22  mov     ebx, eax
0x18001bd24  test    eax, eax
0x18001bd26  jns     short loc_18001BCD4
0x18001bd28  mov     edx, 137h
0x18001bd2d  jmp     loc_18001BC9F
```
