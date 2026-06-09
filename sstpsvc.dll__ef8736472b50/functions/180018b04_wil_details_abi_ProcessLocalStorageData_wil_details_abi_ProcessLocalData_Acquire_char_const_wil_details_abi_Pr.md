# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180018b04`
- end: `0x180018c70`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019b40`

## callees

- `0x1800177cc`
- `0x180018828`
- `0x180018848`
- `0x180018b04`
- `0x180019950`
- `0x18001a624`
- `0x18001b87c`
- `0x18001c070`
- `0x18001c794`
- `0x18001ca0c`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018b87`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b3c`

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
0x180018b04  mov     [rsp-8+arg_10], rbx
0x180018b09  mov     [rsp-8+arg_18], rdi
0x180018b0e  push    rbp
0x180018b0f  lea     rbp, [rsp-170h]
0x180018b17  sub     rsp, 270h
0x180018b1e  mov     rax, cs:__security_cookie
0x180018b25  xor     rax, rsp
0x180018b28  mov     [rbp+170h+var_10], rax
0x180018b2f  mov     rdi, rdx
0x180018b32  mov     qword ptr [rdx], 0
0x180018b39  mov     rbx, rcx
0x180018b3c  call    cs:__imp_GetCurrentProcessId
0x180018b43  nop     dword ptr [rax+rax+00h]
0x180018b48  mov     [rsp+270h+var_248], rbx
0x180018b4d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018b54  mov     r9d, eax
0x180018b57  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180018b5f  mov     edx, 104h; unsigned __int64
0x180018b64  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018b69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018b6e  mov     r9d, 1F0001h; dwDesiredAccess
0x180018b74  mov     [rsp+270h+var_240], 0
0x180018b7d  xor     r8d, r8d; dwFlags
0x180018b80  lea     rdx, [rsp+270h+Name]; lpName
0x180018b85  xor     ecx, ecx; lpMutexAttributes
0x180018b87  call    cs:__imp_CreateMutexExW
0x180018b8e  nop     dword ptr [rax+rax+00h]
0x180018b93  mov     rdx, rax
0x180018b96  lea     rcx, [rsp+270h+var_240]
0x180018b9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018ba0  cmp     [rsp+270h+var_240], 0
0x180018ba6  jnz     short loc_180018BB1
0x180018ba8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018bad  mov     ebx, eax
0x180018baf  jmp     short loc_180018C1D
0x180018bb1  lea     rdx, [rsp+270h+var_238]
0x180018bb6  lea     rcx, [rsp+270h+var_240]
0x180018bbb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180018bc0  lea     rdx, [rsp+270h+var_230]; void **
0x180018bc5  mov     [rsp+270h+var_230], 0
0x180018bce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018bd3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180018bd8  mov     ebx, eax
0x180018bda  test    eax, eax
0x180018bdc  jns     short loc_180018BFE
0x180018bde  mov     edx, 12Eh; void *
0x180018be3  mov     rcx, [rbp+178h]; this
0x180018bea  mov     r9d, eax; char *
0x180018bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018bf2  lea     rcx, [rsp+270h+var_238]
0x180018bf7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018bfc  jmp     short loc_180018C1D
0x180018bfe  mov     rcx, [rsp+270h+var_230]
0x180018c03  test    rcx, rcx
0x180018c06  jz      short loc_180018C4E
0x180018c08  mov     [rdi], rcx
0x180018c0b  mov     eax, [rcx]
0x180018c0d  inc     eax
0x180018c0f  mov     [rcx], eax
0x180018c11  lea     rcx, [rsp+270h+var_238]
0x180018c16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018c1b  xor     ebx, ebx
0x180018c1d  lea     rcx, [rsp+270h+var_240]
0x180018c22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018c27  mov     eax, ebx
0x180018c29  mov     rcx, [rbp+170h+var_10]
0x180018c30  xor     rcx, rsp; StackCookie
0x180018c33  call    __security_check_cookie
0x180018c38  lea     r11, [rsp+270h+var_s0]
0x180018c40  mov     rbx, [r11+20h]
0x180018c44  mov     rdi, [r11+28h]
0x180018c48  mov     rsp, r11
0x180018c4b  pop     rbp
0x180018c4c  retn
0x180018c4e  mov     r8, rdi
0x180018c51  lea     rdx, [rsp+270h+var_240]
0x180018c56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018c5b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018c60  mov     ebx, eax
0x180018c62  test    eax, eax
0x180018c64  jns     short loc_180018C11
0x180018c66  mov     edx, 137h
0x180018c6b  jmp     loc_180018BE3
```
