# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800366c4`
- end: `0x180036823`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180038a80`

## callees

- `0x180001600`
- `0x180036338`
- `0x180036354`
- `0x1800366c4`
- `0x180038408`
- `0x1800396e4`
- `0x18003acf8`
- `0x18003b9ac`
- `0x18003c484`
- `0x18003c768`
- `0x18003d3dc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800366fc`
- `KERNEL32!GetCurrentProcessId` at `0x1800366fc`
- `KERNEL32!CreateMutexExW` at `0x180036741`
- `KERNEL32!CreateMutexExW` at `0x180036741`

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
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
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
0x1800366c4  mov     [rsp-8+arg_10], rbx
0x1800366c9  mov     [rsp-8+arg_18], rdi
0x1800366ce  push    rbp
0x1800366cf  lea     rbp, [rsp-170h]
0x1800366d7  sub     rsp, 270h
0x1800366de  mov     rax, cs:__security_cookie
0x1800366e5  xor     rax, rsp
0x1800366e8  mov     [rbp+170h+var_10], rax
0x1800366ef  mov     rdi, rdx
0x1800366f2  mov     qword ptr [rdx], 0
0x1800366f9  mov     rbx, rcx
0x1800366fc  call    cs:__imp_GetCurrentProcessId
0x180036702  mov     [rsp+270h+var_248], rbx
0x180036707  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003670e  mov     r9d, eax
0x180036711  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180036719  mov     edx, 104h; cchDest
0x18003671e  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180036723  call    StringCchPrintfW
0x180036728  mov     r9d, 1F0001h; dwDesiredAccess
0x18003672e  mov     [rsp+270h+var_240], 0
0x180036737  xor     r8d, r8d; dwFlags
0x18003673a  lea     rdx, [rsp+270h+pszDest]; lpName
0x18003673f  xor     ecx, ecx; lpMutexAttributes
0x180036741  call    cs:__imp_CreateMutexExW
0x180036747  mov     rdx, rax
0x18003674a  lea     rcx, [rsp+270h+var_240]
0x18003674f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036754  cmp     [rsp+270h+var_240], 0
0x18003675a  jnz     short loc_180036765
0x18003675c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036761  mov     ebx, eax
0x180036763  jmp     short loc_1800367D1
0x180036765  lea     rdx, [rsp+270h+var_238]
0x18003676a  lea     rcx, [rsp+270h+var_240]
0x18003676f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180036774  lea     rdx, [rsp+270h+var_230]; void **
0x180036779  mov     [rsp+270h+var_230], 0
0x180036782  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180036787  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003678c  mov     ebx, eax
0x18003678e  test    eax, eax
0x180036790  jns     short loc_1800367B2
0x180036792  mov     edx, 12Eh; void *
0x180036797  mov     rcx, [rbp+178h]; this
0x18003679e  mov     r9d, eax; char *
0x1800367a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800367a6  lea     rcx, [rsp+270h+var_238]
0x1800367ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800367b0  jmp     short loc_1800367D1
0x1800367b2  mov     rcx, [rsp+270h+var_230]
0x1800367b7  test    rcx, rcx
0x1800367ba  jz      short loc_180036801
0x1800367bc  mov     [rdi], rcx
0x1800367bf  mov     eax, [rcx]
0x1800367c1  inc     eax
0x1800367c3  mov     [rcx], eax
0x1800367c5  lea     rcx, [rsp+270h+var_238]
0x1800367ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800367cf  xor     ebx, ebx
0x1800367d1  lea     rcx, [rsp+270h+var_240]
0x1800367d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800367db  mov     eax, ebx
0x1800367dd  mov     rcx, [rbp+170h+var_10]
0x1800367e4  xor     rcx, rsp; StackCookie
0x1800367e7  call    __security_check_cookie
0x1800367ec  lea     r11, [rsp+270h+var_s0]
0x1800367f4  mov     rbx, [r11+20h]
0x1800367f8  mov     rdi, [r11+28h]
0x1800367fc  mov     rsp, r11
0x1800367ff  pop     rbp
0x180036800  retn
0x180036801  mov     r8, rdi
0x180036804  lea     rdx, [rsp+270h+var_240]
0x180036809  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18003680e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180036813  mov     ebx, eax
0x180036815  test    eax, eax
0x180036817  jns     short loc_1800367C5
0x180036819  mov     edx, 137h
0x18003681e  jmp     loc_180036797
```
