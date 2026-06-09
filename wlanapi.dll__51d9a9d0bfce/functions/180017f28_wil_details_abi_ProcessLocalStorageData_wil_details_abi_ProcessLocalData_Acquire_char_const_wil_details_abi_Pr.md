# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180017f28`
- end: `0x18001808e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180023a18`

## callees

- `0x1800052a0`
- `0x1800147d4`
- `0x180017f28`
- `0x180018094`
- `0x1800180b0`
- `0x180018288`
- `0x18001830c`
- `0x180018e74`
- `0x1800193b0`
- `0x180019a20`
- `0x1800242d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017f60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017f60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017fa5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017fa5`

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
0x180017f28  mov     [rsp-8+arg_10], rbx
0x180017f2d  mov     [rsp-8+arg_18], rdi
0x180017f32  push    rbp
0x180017f33  lea     rbp, [rsp-170h]
0x180017f3b  sub     rsp, 270h
0x180017f42  mov     rax, cs:__security_cookie
0x180017f49  xor     rax, rsp
0x180017f4c  mov     [rbp+170h+var_10], rax
0x180017f53  mov     rdi, rdx
0x180017f56  mov     qword ptr [rdx], 0
0x180017f5d  mov     rbx, rcx
0x180017f60  call    cs:__imp_GetCurrentProcessId
0x180017f66  mov     [rsp+270h+var_248], rbx
0x180017f6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017f72  mov     r9d, eax
0x180017f75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180017f7d  mov     edx, 104h; unsigned __int64
0x180017f82  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017f87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017f8c  mov     r9d, 1F0001h; dwDesiredAccess
0x180017f92  mov     [rsp+270h+var_240], 0
0x180017f9b  xor     r8d, r8d; dwFlags
0x180017f9e  lea     rdx, [rsp+270h+Name]; lpName
0x180017fa3  xor     ecx, ecx; lpMutexAttributes
0x180017fa5  call    cs:__imp_CreateMutexExW
0x180017fab  mov     rdx, rax
0x180017fae  lea     rcx, [rsp+270h+var_240]
0x180017fb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017fb8  cmp     [rsp+270h+var_240], 0
0x180017fbe  jnz     short loc_180017FC9
0x180017fc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017fc5  mov     ebx, eax
0x180017fc7  jmp     short loc_18001803C
0x180017fc9  lea     rdx, [rsp+270h+var_238]
0x180017fce  lea     rcx, [rsp+270h+var_240]
0x180017fd3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180017fd8  lea     rdx, [rsp+270h+var_230]; void **
0x180017fdd  mov     [rsp+270h+var_230], 0
0x180017fe6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017feb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180017ff0  mov     ebx, eax
0x180017ff2  test    eax, eax
0x180017ff4  jns     short loc_18001801D
0x180017ff6  mov     edx, 12Eh; void *
0x180017ffb  mov     rcx, [rbp+178h]; this
0x180018002  lea     r8, aWil; "wil"
0x180018009  mov     r9d, eax; char *
0x18001800c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018011  lea     rcx, [rsp+270h+var_238]
0x180018016  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001801b  jmp     short loc_18001803C
0x18001801d  mov     rcx, [rsp+270h+var_230]
0x180018022  test    rcx, rcx
0x180018025  jz      short loc_18001806C
0x180018027  mov     [rdi], rcx
0x18001802a  mov     eax, [rcx]
0x18001802c  inc     eax
0x18001802e  mov     [rcx], eax
0x180018030  lea     rcx, [rsp+270h+var_238]
0x180018035  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001803a  xor     ebx, ebx
0x18001803c  lea     rcx, [rsp+270h+var_240]
0x180018041  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018046  mov     eax, ebx
0x180018048  mov     rcx, [rbp+170h+var_10]
0x18001804f  xor     rcx, rsp; StackCookie
0x180018052  call    __security_check_cookie
0x180018057  lea     r11, [rsp+270h+var_s0]
0x18001805f  mov     rbx, [r11+20h]
0x180018063  mov     rdi, [r11+28h]
0x180018067  mov     rsp, r11
0x18001806a  pop     rbp
0x18001806b  retn
0x18001806c  mov     r8, rdi
0x18001806f  lea     rdx, [rsp+270h+var_240]
0x180018074  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018079  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001807e  mov     ebx, eax
0x180018080  test    eax, eax
0x180018082  jns     short loc_180018030
0x180018084  mov     edx, 137h
0x180018089  jmp     loc_180017FFB
```
