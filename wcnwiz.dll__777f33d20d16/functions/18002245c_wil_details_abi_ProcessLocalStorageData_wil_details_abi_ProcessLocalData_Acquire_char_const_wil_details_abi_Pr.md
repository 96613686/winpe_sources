# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002245c`
- end: `0x1800225bb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022f88`

## callees

- `0x180001820`
- `0x180015d28`
- `0x1800222f8`
- `0x180022314`
- `0x18002245c`
- `0x180022ce8`
- `0x1800238ec`
- `0x180023ce4`
- `0x180024528`
- `0x180024ac0`
- `0x180024bb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022494`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022494`
- `KERNEL32!CreateMutexExW` at `0x1800224d9`
- `KERNEL32!CreateMutexExW` at `0x1800224d9`

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
0x18002245c  mov     [rsp-8+arg_10], rbx
0x180022461  mov     [rsp-8+arg_18], rdi
0x180022466  push    rbp
0x180022467  lea     rbp, [rsp-170h]
0x18002246f  sub     rsp, 270h
0x180022476  mov     rax, cs:__security_cookie
0x18002247d  xor     rax, rsp
0x180022480  mov     [rbp+170h+var_10], rax
0x180022487  mov     rdi, rdx
0x18002248a  mov     qword ptr [rdx], 0
0x180022491  mov     rbx, rcx
0x180022494  call    cs:__imp_GetCurrentProcessId
0x18002249a  mov     [rsp+270h+var_248], rbx
0x18002249f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800224a6  mov     r9d, eax
0x1800224a9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800224b1  mov     edx, 104h; unsigned __int64
0x1800224b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800224bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800224c0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800224c6  mov     [rsp+270h+var_240], 0
0x1800224cf  xor     r8d, r8d; dwFlags
0x1800224d2  lea     rdx, [rsp+270h+Name]; lpName
0x1800224d7  xor     ecx, ecx; lpMutexAttributes
0x1800224d9  call    cs:__imp_CreateMutexExW
0x1800224df  mov     rdx, rax
0x1800224e2  lea     rcx, [rsp+270h+var_240]
0x1800224e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800224ec  cmp     [rsp+270h+var_240], 0
0x1800224f2  jnz     short loc_1800224FD
0x1800224f4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800224f9  mov     ebx, eax
0x1800224fb  jmp     short loc_180022569
0x1800224fd  lea     rdx, [rsp+270h+var_238]
0x180022502  lea     rcx, [rsp+270h+var_240]
0x180022507  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002250c  lea     rdx, [rsp+270h+var_230]; void **
0x180022511  mov     [rsp+270h+var_230], 0
0x18002251a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002251f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180022524  mov     ebx, eax
0x180022526  test    eax, eax
0x180022528  jns     short loc_18002254A
0x18002252a  mov     edx, 12Eh; void *
0x18002252f  mov     rcx, [rbp+178h]; this
0x180022536  mov     r9d, eax; char *
0x180022539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002253e  lea     rcx, [rsp+270h+var_238]
0x180022543  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022548  jmp     short loc_180022569
0x18002254a  mov     rcx, [rsp+270h+var_230]
0x18002254f  test    rcx, rcx
0x180022552  jz      short loc_180022599
0x180022554  mov     [rdi], rcx
0x180022557  mov     eax, [rcx]
0x180022559  inc     eax
0x18002255b  mov     [rcx], eax
0x18002255d  lea     rcx, [rsp+270h+var_238]
0x180022562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022567  xor     ebx, ebx
0x180022569  lea     rcx, [rsp+270h+var_240]
0x18002256e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022573  mov     eax, ebx
0x180022575  mov     rcx, [rbp+170h+var_10]
0x18002257c  xor     rcx, rsp; StackCookie
0x18002257f  call    __security_check_cookie
0x180022584  lea     r11, [rsp+270h+var_s0]
0x18002258c  mov     rbx, [r11+20h]
0x180022590  mov     rdi, [r11+28h]
0x180022594  mov     rsp, r11
0x180022597  pop     rbp
0x180022598  retn
0x180022599  mov     r8, rdi
0x18002259c  lea     rdx, [rsp+270h+var_240]
0x1800225a1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800225a6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800225ab  mov     ebx, eax
0x1800225ad  test    eax, eax
0x1800225af  jns     short loc_18002255D
0x1800225b1  mov     edx, 137h
0x1800225b6  jmp     loc_18002252F
```
