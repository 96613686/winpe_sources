# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18008917c`
- end: `0x1800892eb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180089518`

## callees

- `0x180027550`
- `0x18006fb88`
- `0x180071508`
- `0x180080fb0`
- `0x180089038`
- `0x180089054`
- `0x18008917c`
- `0x180089750`
- `0x180089f34`
- `0x18008a190`
- `0x18008a248`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800891b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800891b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800891f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800891f9`

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
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
    v12 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18008917c  mov     [rsp-8+arg_10], rbx
0x180089181  mov     [rsp-8+arg_18], rdi
0x180089186  push    rbp
0x180089187  lea     rbp, [rsp-170h]
0x18008918f  sub     rsp, 270h
0x180089196  mov     rax, cs:__security_cookie
0x18008919d  xor     rax, rsp
0x1800891a0  mov     [rbp+170h+var_10], rax
0x1800891a7  mov     rdi, rdx
0x1800891aa  mov     qword ptr [rdx], 0
0x1800891b1  mov     rbx, rcx
0x1800891b4  call    cs:__imp_GetCurrentProcessId
0x1800891ba  mov     [rsp+270h+var_248], rbx
0x1800891bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800891c6  mov     r9d, eax
0x1800891c9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800891d1  mov     edx, 104h; unsigned __int64
0x1800891d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800891db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800891e0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800891e6  mov     [rsp+270h+var_240], 0
0x1800891ef  xor     r8d, r8d; dwFlags
0x1800891f2  lea     rdx, [rsp+270h+Name]; lpName
0x1800891f7  xor     ecx, ecx; lpMutexAttributes
0x1800891f9  call    cs:__imp_CreateMutexExW
0x1800891ff  mov     rdx, rax
0x180089202  lea     rcx, [rsp+270h+var_240]
0x180089207  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18008920c  cmp     [rsp+270h+var_240], 0
0x180089212  jnz     short loc_18008921D
0x180089214  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180089219  mov     ebx, eax
0x18008921b  jmp     short loc_180089299
0x18008921d  lea     rdx, [rsp+270h+var_238]
0x180089222  mov     [rsp+270h+var_238], 0
0x18008922b  lea     rcx, [rsp+270h+var_240]
0x180089230  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180089235  lea     rdx, [rsp+270h+var_230]; void **
0x18008923a  mov     [rsp+270h+var_230], 0
0x180089243  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180089248  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18008924d  mov     ebx, eax
0x18008924f  test    eax, eax
0x180089251  jns     short loc_18008927A
0x180089253  mov     edx, 12Eh; void *
0x180089258  mov     rcx, [rbp+178h]; this
0x18008925f  lea     r8, aWil; "wil"
0x180089266  mov     r9d, eax; char *
0x180089269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008926e  lea     rcx, [rsp+270h+var_238]
0x180089273  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180089278  jmp     short loc_180089299
0x18008927a  mov     rcx, [rsp+270h+var_230]
0x18008927f  test    rcx, rcx
0x180089282  jz      short loc_1800892C9
0x180089284  mov     [rdi], rcx
0x180089287  mov     eax, [rcx]
0x180089289  inc     eax
0x18008928b  mov     [rcx], eax
0x18008928d  lea     rcx, [rsp+270h+var_238]
0x180089292  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180089297  xor     ebx, ebx
0x180089299  lea     rcx, [rsp+270h+var_240]
0x18008929e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800892a3  mov     eax, ebx
0x1800892a5  mov     rcx, [rbp+170h+var_10]
0x1800892ac  xor     rcx, rsp; StackCookie
0x1800892af  call    __security_check_cookie
0x1800892b4  lea     r11, [rsp+270h+var_s0]
0x1800892bc  mov     rbx, [r11+20h]
0x1800892c0  mov     rdi, [r11+28h]
0x1800892c4  mov     rsp, r11
0x1800892c7  pop     rbp
0x1800892c8  retn
0x1800892c9  mov     r8, rdi
0x1800892cc  lea     rdx, [rsp+270h+var_240]
0x1800892d1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800892d6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800892db  mov     ebx, eax
0x1800892dd  test    eax, eax
0x1800892df  jns     short loc_18008928D
0x1800892e1  mov     edx, 137h
0x1800892e6  jmp     loc_180089258
```
