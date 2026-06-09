# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800054a8`
- end: `0x180005607`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006420`

## callees

- `0x1800051f0`
- `0x18000520c`
- `0x1800054a8`
- `0x180006138`
- `0x180006e10`
- `0x180007d24`
- `0x180008a0c`
- `0x180008b64`
- `0x18000950c`
- `0x1800096e0`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005525`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054e0`

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
0x1800054a8  mov     [rsp-8+arg_10], rbx
0x1800054ad  mov     [rsp-8+arg_18], rdi
0x1800054b2  push    rbp
0x1800054b3  lea     rbp, [rsp-170h]
0x1800054bb  sub     rsp, 270h
0x1800054c2  mov     rax, cs:__security_cookie
0x1800054c9  xor     rax, rsp
0x1800054cc  mov     [rbp+170h+var_10], rax
0x1800054d3  mov     rdi, rdx
0x1800054d6  mov     qword ptr [rdx], 0
0x1800054dd  mov     rbx, rcx
0x1800054e0  call    cs:__imp_GetCurrentProcessId
0x1800054e6  mov     [rsp+270h+var_248], rbx
0x1800054eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800054f2  mov     r9d, eax
0x1800054f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800054fd  mov     edx, 104h; unsigned __int64
0x180005502  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005507  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000550c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005512  mov     [rsp+270h+var_240], 0
0x18000551b  xor     r8d, r8d; dwFlags
0x18000551e  lea     rdx, [rsp+270h+Name]; lpName
0x180005523  xor     ecx, ecx; lpMutexAttributes
0x180005525  call    cs:__imp_CreateMutexExW
0x18000552b  mov     rdx, rax
0x18000552e  lea     rcx, [rsp+270h+var_240]
0x180005533  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005538  cmp     [rsp+270h+var_240], 0
0x18000553e  jnz     short loc_180005549
0x180005540  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005545  mov     ebx, eax
0x180005547  jmp     short loc_1800055B5
0x180005549  lea     rdx, [rsp+270h+var_238]
0x18000554e  lea     rcx, [rsp+270h+var_240]
0x180005553  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005558  lea     rdx, [rsp+270h+var_230]; void **
0x18000555d  mov     [rsp+270h+var_230], 0
0x180005566  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000556b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005570  mov     ebx, eax
0x180005572  test    eax, eax
0x180005574  jns     short loc_180005596
0x180005576  mov     edx, 12Eh; void *
0x18000557b  mov     rcx, [rbp+178h]; this
0x180005582  mov     r9d, eax; char *
0x180005585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000558a  lea     rcx, [rsp+270h+var_238]
0x18000558f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005594  jmp     short loc_1800055B5
0x180005596  mov     rcx, [rsp+270h+var_230]
0x18000559b  test    rcx, rcx
0x18000559e  jz      short loc_1800055E5
0x1800055a0  mov     [rdi], rcx
0x1800055a3  mov     eax, [rcx]
0x1800055a5  inc     eax
0x1800055a7  mov     [rcx], eax
0x1800055a9  lea     rcx, [rsp+270h+var_238]
0x1800055ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800055b3  xor     ebx, ebx
0x1800055b5  lea     rcx, [rsp+270h+var_240]
0x1800055ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800055bf  mov     eax, ebx
0x1800055c1  mov     rcx, [rbp+170h+var_10]
0x1800055c8  xor     rcx, rsp; StackCookie
0x1800055cb  call    __security_check_cookie
0x1800055d0  lea     r11, [rsp+270h+var_s0]
0x1800055d8  mov     rbx, [r11+20h]
0x1800055dc  mov     rdi, [r11+28h]
0x1800055e0  mov     rsp, r11
0x1800055e3  pop     rbp
0x1800055e4  retn
0x1800055e5  mov     r8, rdi
0x1800055e8  lea     rdx, [rsp+270h+var_240]
0x1800055ed  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800055f2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800055f7  mov     ebx, eax
0x1800055f9  test    eax, eax
0x1800055fb  jns     short loc_1800055A9
0x1800055fd  mov     edx, 137h
0x180005602  jmp     loc_18000557B
```
