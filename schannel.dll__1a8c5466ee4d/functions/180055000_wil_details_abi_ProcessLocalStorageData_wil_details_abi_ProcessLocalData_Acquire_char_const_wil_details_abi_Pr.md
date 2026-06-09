# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180055000`
- end: `0x18005515f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180062628`

## callees

- `0x180043e9c`
- `0x18004ea94`
- `0x180055000`
- `0x180055388`
- `0x1800553a4`
- `0x180055440`
- `0x1800597b0`
- `0x180061930`
- `0x180062b9c`
- `0x18006388c`
- `0x180067904`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180055038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180055038`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005507d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005507d`

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
0x180055000  mov     [rsp-8+arg_10], rbx
0x180055005  mov     [rsp-8+arg_18], rdi
0x18005500a  push    rbp
0x18005500b  lea     rbp, [rsp-170h]
0x180055013  sub     rsp, 270h
0x18005501a  mov     rax, cs:__security_cookie
0x180055021  xor     rax, rsp
0x180055024  mov     [rbp+170h+var_10], rax
0x18005502b  mov     rdi, rdx
0x18005502e  mov     qword ptr [rdx], 0
0x180055035  mov     rbx, rcx
0x180055038  call    cs:__imp_GetCurrentProcessId
0x18005503e  mov     [rsp+270h+var_248], rbx
0x180055043  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18005504a  mov     r9d, eax
0x18005504d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180055055  mov     edx, 104h; unsigned __int64
0x18005505a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005505f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055064  mov     r9d, 1F0001h; dwDesiredAccess
0x18005506a  mov     [rsp+270h+var_240], 0
0x180055073  xor     r8d, r8d; dwFlags
0x180055076  lea     rdx, [rsp+270h+Name]; lpName
0x18005507b  xor     ecx, ecx; lpMutexAttributes
0x18005507d  call    cs:__imp_CreateMutexExW
0x180055083  mov     rdx, rax
0x180055086  lea     rcx, [rsp+270h+var_240]
0x18005508b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180055090  cmp     [rsp+270h+var_240], 0
0x180055096  jnz     short loc_1800550A1
0x180055098  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005509d  mov     ebx, eax
0x18005509f  jmp     short loc_18005510D
0x1800550a1  lea     rdx, [rsp+270h+var_238]
0x1800550a6  lea     rcx, [rsp+270h+var_240]
0x1800550ab  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800550b0  lea     rdx, [rsp+270h+var_230]; void **
0x1800550b5  mov     [rsp+270h+var_230], 0
0x1800550be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800550c3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800550c8  mov     ebx, eax
0x1800550ca  test    eax, eax
0x1800550cc  jns     short loc_1800550EE
0x1800550ce  mov     edx, 12Eh; void *
0x1800550d3  mov     rcx, [rbp+178h]; this
0x1800550da  mov     r9d, eax; char *
0x1800550dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800550e2  lea     rcx, [rsp+270h+var_238]
0x1800550e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800550ec  jmp     short loc_18005510D
0x1800550ee  mov     rcx, [rsp+270h+var_230]
0x1800550f3  test    rcx, rcx
0x1800550f6  jz      short loc_18005513D
0x1800550f8  mov     [rdi], rcx
0x1800550fb  mov     eax, [rcx]
0x1800550fd  inc     eax
0x1800550ff  mov     [rcx], eax
0x180055101  lea     rcx, [rsp+270h+var_238]
0x180055106  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005510b  xor     ebx, ebx
0x18005510d  lea     rcx, [rsp+270h+var_240]
0x180055112  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055117  mov     eax, ebx
0x180055119  mov     rcx, [rbp+170h+var_10]
0x180055120  xor     rcx, rsp; StackCookie
0x180055123  call    __security_check_cookie
0x180055128  lea     r11, [rsp+270h+var_s0]
0x180055130  mov     rbx, [r11+20h]
0x180055134  mov     rdi, [r11+28h]
0x180055138  mov     rsp, r11
0x18005513b  pop     rbp
0x18005513c  retn
0x18005513d  mov     r8, rdi
0x180055140  lea     rdx, [rsp+270h+var_240]
0x180055145  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005514a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005514f  mov     ebx, eax
0x180055151  test    eax, eax
0x180055153  jns     short loc_180055101
0x180055155  mov     edx, 137h
0x18005515a  jmp     loc_1800550D3
```
