# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18004cacc`
- end: `0x18004cc38`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800342d4`

## callees

- `0x180031518`
- `0x180042d88`
- `0x180043a30`
- `0x18004c824`
- `0x18004c844`
- `0x18004cacc`
- `0x18004ded0`
- `0x18004ecbc`
- `0x18004f550`
- `0x18004fd24`
- `0x18004fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004cb4f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004cb4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cb04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cb04`

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
0x18004cacc  mov     [rsp-8+arg_10], rbx
0x18004cad1  mov     [rsp-8+arg_18], rdi
0x18004cad6  push    rbp
0x18004cad7  lea     rbp, [rsp-170h]
0x18004cadf  sub     rsp, 270h
0x18004cae6  mov     rax, cs:__security_cookie
0x18004caed  xor     rax, rsp
0x18004caf0  mov     [rbp+170h+var_10], rax
0x18004caf7  mov     rdi, rdx
0x18004cafa  mov     qword ptr [rdx], 0
0x18004cb01  mov     rbx, rcx
0x18004cb04  call    cs:__imp_GetCurrentProcessId
0x18004cb0b  nop     dword ptr [rax+rax+00h]
0x18004cb10  mov     [rsp+270h+var_248], rbx
0x18004cb15  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004cb1c  mov     r9d, eax
0x18004cb1f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18004cb27  mov     edx, 104h; unsigned __int64
0x18004cb2c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cb31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004cb36  mov     r9d, 1F0001h; dwDesiredAccess
0x18004cb3c  mov     [rsp+270h+var_240], 0
0x18004cb45  xor     r8d, r8d; dwFlags
0x18004cb48  lea     rdx, [rsp+270h+Name]; lpName
0x18004cb4d  xor     ecx, ecx; lpMutexAttributes
0x18004cb4f  call    cs:__imp_CreateMutexExW
0x18004cb56  nop     dword ptr [rax+rax+00h]
0x18004cb5b  mov     rdx, rax
0x18004cb5e  lea     rcx, [rsp+270h+var_240]
0x18004cb63  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004cb68  cmp     [rsp+270h+var_240], 0
0x18004cb6e  jnz     short loc_18004CB79
0x18004cb70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004cb75  mov     ebx, eax
0x18004cb77  jmp     short loc_18004CBE5
0x18004cb79  lea     rdx, [rsp+270h+var_238]
0x18004cb7e  lea     rcx, [rsp+270h+var_240]
0x18004cb83  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004cb88  lea     rdx, [rsp+270h+var_230]; void **
0x18004cb8d  mov     [rsp+270h+var_230], 0
0x18004cb96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cb9b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004cba0  mov     ebx, eax
0x18004cba2  test    eax, eax
0x18004cba4  jns     short loc_18004CBC6
0x18004cba6  mov     edx, 12Eh; void *
0x18004cbab  mov     rcx, [rbp+178h]; this
0x18004cbb2  mov     r9d, eax; char *
0x18004cbb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cbba  lea     rcx, [rsp+270h+var_238]
0x18004cbbf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cbc4  jmp     short loc_18004CBE5
0x18004cbc6  mov     rcx, [rsp+270h+var_230]
0x18004cbcb  test    rcx, rcx
0x18004cbce  jz      short loc_18004CC16
0x18004cbd0  mov     [rdi], rcx
0x18004cbd3  mov     eax, [rcx]
0x18004cbd5  inc     eax
0x18004cbd7  mov     [rcx], eax
0x18004cbd9  lea     rcx, [rsp+270h+var_238]
0x18004cbde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cbe3  xor     ebx, ebx
0x18004cbe5  lea     rcx, [rsp+270h+var_240]
0x18004cbea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cbef  mov     eax, ebx
0x18004cbf1  mov     rcx, [rbp+170h+var_10]
0x18004cbf8  xor     rcx, rsp; StackCookie
0x18004cbfb  call    __security_check_cookie
0x18004cc00  lea     r11, [rsp+270h+var_s0]
0x18004cc08  mov     rbx, [r11+20h]
0x18004cc0c  mov     rdi, [r11+28h]
0x18004cc10  mov     rsp, r11
0x18004cc13  pop     rbp
0x18004cc14  retn
0x18004cc16  mov     r8, rdi
0x18004cc19  lea     rdx, [rsp+270h+var_240]
0x18004cc1e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cc23  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004cc28  mov     ebx, eax
0x18004cc2a  test    eax, eax
0x18004cc2c  jns     short loc_18004CBD9
0x18004cc2e  mov     edx, 137h
0x18004cc33  jmp     loc_18004CBAB
```
