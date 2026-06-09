# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800863a0`
- end: `0x180086515`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180087530`

## callees

- `0x180071c14`
- `0x1800722f0`
- `0x1800861fc`
- `0x18008621c`
- `0x1800863a0`
- `0x180087d38`
- `0x180088c40`
- `0x180089208`
- `0x180089994`
- `0x180089a54`
- `0x180089de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800863d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800863d8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180086423`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180086423`

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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x1800863a0  mov     [rsp-8+arg_10], rbx
0x1800863a5  mov     [rsp-8+arg_18], rdi
0x1800863aa  push    rbp
0x1800863ab  lea     rbp, [rsp-170h]
0x1800863b3  sub     rsp, 270h
0x1800863ba  mov     rax, cs:__security_cookie
0x1800863c1  xor     rax, rsp
0x1800863c4  mov     [rbp+170h+var_10], rax
0x1800863cb  mov     rdi, rdx
0x1800863ce  mov     qword ptr [rdx], 0
0x1800863d5  mov     rbx, rcx
0x1800863d8  call    cs:__imp_GetCurrentProcessId
0x1800863df  nop     dword ptr [rax+rax+00h]
0x1800863e4  mov     [rsp+270h+var_248], rbx
0x1800863e9  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800863f0  mov     r9d, eax
0x1800863f3  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800863fb  mov     edx, 104h; cchDest
0x180086400  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180086405  call    StringCchPrintfW
0x18008640a  mov     r9d, 1F0001h; dwDesiredAccess
0x180086410  mov     [rsp+270h+var_240], 0
0x180086419  xor     r8d, r8d; dwFlags
0x18008641c  lea     rdx, [rsp+270h+pszDest]; lpName
0x180086421  xor     ecx, ecx; lpMutexAttributes
0x180086423  call    cs:__imp_CreateMutexExW
0x18008642a  nop     dword ptr [rax+rax+00h]
0x18008642f  mov     rdx, rax
0x180086432  lea     rcx, [rsp+270h+var_240]
0x180086437  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18008643c  cmp     [rsp+270h+var_240], 0
0x180086442  jnz     short loc_18008644D
0x180086444  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180086449  mov     ebx, eax
0x18008644b  jmp     short loc_1800864C2
0x18008644d  lea     rdx, [rsp+270h+var_238]
0x180086452  mov     [rsp+270h+var_238], 0
0x18008645b  lea     rcx, [rsp+270h+var_240]
0x180086460  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180086465  lea     rdx, [rsp+270h+var_230]; void **
0x18008646a  mov     [rsp+270h+var_230], 0
0x180086473  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180086478  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18008647d  mov     ebx, eax
0x18008647f  test    eax, eax
0x180086481  jns     short loc_1800864A3
0x180086483  mov     edx, 12Eh; void *
0x180086488  mov     rcx, [rbp+178h]; this
0x18008648f  mov     r9d, eax; char *
0x180086492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086497  lea     rcx, [rsp+270h+var_238]
0x18008649c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800864a1  jmp     short loc_1800864C2
0x1800864a3  mov     rcx, [rsp+270h+var_230]
0x1800864a8  test    rcx, rcx
0x1800864ab  jz      short loc_1800864F3
0x1800864ad  mov     [rdi], rcx
0x1800864b0  mov     eax, [rcx]
0x1800864b2  inc     eax
0x1800864b4  mov     [rcx], eax
0x1800864b6  lea     rcx, [rsp+270h+var_238]
0x1800864bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800864c0  xor     ebx, ebx
0x1800864c2  lea     rcx, [rsp+270h+var_240]
0x1800864c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800864cc  mov     eax, ebx
0x1800864ce  mov     rcx, [rbp+170h+var_10]
0x1800864d5  xor     rcx, rsp; StackCookie
0x1800864d8  call    __security_check_cookie
0x1800864dd  lea     r11, [rsp+270h+var_s0]
0x1800864e5  mov     rbx, [r11+20h]
0x1800864e9  mov     rdi, [r11+28h]
0x1800864ed  mov     rsp, r11
0x1800864f0  pop     rbp
0x1800864f1  retn
0x1800864f3  mov     r8, rdi
0x1800864f6  lea     rdx, [rsp+270h+var_240]
0x1800864fb  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180086500  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180086505  mov     ebx, eax
0x180086507  test    eax, eax
0x180086509  jns     short loc_1800864B6
0x18008650b  mov     edx, 137h
0x180086510  jmp     loc_180086488
```
