# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18004cc40`
- end: `0x18004cdac`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004d058`

## callees

- `0x180031518`
- `0x180042d88`
- `0x180043a30`
- `0x18004c824`
- `0x18004c844`
- `0x18004cc40`
- `0x18004dff4`
- `0x18004ecbc`
- `0x18004f550`
- `0x18004fd24`
- `0x18004fe90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004ccc3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004ccc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cc78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cc78`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18004cc40  mov     [rsp-8+arg_10], rbx
0x18004cc45  mov     [rsp-8+arg_18], rdi
0x18004cc4a  push    rbp
0x18004cc4b  lea     rbp, [rsp-170h]
0x18004cc53  sub     rsp, 270h
0x18004cc5a  mov     rax, cs:__security_cookie
0x18004cc61  xor     rax, rsp
0x18004cc64  mov     [rbp+170h+var_10], rax
0x18004cc6b  mov     rdi, rdx
0x18004cc6e  mov     qword ptr [rdx], 0
0x18004cc75  mov     rbx, rcx
0x18004cc78  call    cs:__imp_GetCurrentProcessId
0x18004cc7f  nop     dword ptr [rax+rax+00h]
0x18004cc84  mov     [rsp+270h+var_248], rbx
0x18004cc89  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004cc90  mov     r9d, eax
0x18004cc93  mov     [rsp+270h+var_250], 130h; int
0x18004cc9b  mov     edx, 104h; unsigned __int64
0x18004cca0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cca5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ccaa  mov     r9d, 1F0001h; dwDesiredAccess
0x18004ccb0  mov     [rsp+270h+var_240], 0
0x18004ccb9  xor     r8d, r8d; dwFlags
0x18004ccbc  lea     rdx, [rsp+270h+Name]; lpName
0x18004ccc1  xor     ecx, ecx; lpMutexAttributes
0x18004ccc3  call    cs:__imp_CreateMutexExW
0x18004ccca  nop     dword ptr [rax+rax+00h]
0x18004cccf  mov     rdx, rax
0x18004ccd2  lea     rcx, [rsp+270h+var_240]
0x18004ccd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004ccdc  cmp     [rsp+270h+var_240], 0
0x18004cce2  jnz     short loc_18004CCED
0x18004cce4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004cce9  mov     ebx, eax
0x18004cceb  jmp     short loc_18004CD59
0x18004cced  lea     rdx, [rsp+270h+var_238]
0x18004ccf2  lea     rcx, [rsp+270h+var_240]
0x18004ccf7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18004ccfc  lea     rdx, [rsp+270h+var_230]; void **
0x18004cd01  mov     [rsp+270h+var_230], 0
0x18004cd0a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cd0f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18004cd14  mov     ebx, eax
0x18004cd16  test    eax, eax
0x18004cd18  jns     short loc_18004CD3A
0x18004cd1a  mov     edx, 12Eh; void *
0x18004cd1f  mov     rcx, [rbp+178h]; this
0x18004cd26  mov     r9d, eax; char *
0x18004cd29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cd2e  lea     rcx, [rsp+270h+var_238]
0x18004cd33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cd38  jmp     short loc_18004CD59
0x18004cd3a  mov     rcx, [rsp+270h+var_230]
0x18004cd3f  test    rcx, rcx
0x18004cd42  jz      short loc_18004CD8A
0x18004cd44  mov     [rdi], rcx
0x18004cd47  mov     eax, [rcx]
0x18004cd49  inc     eax
0x18004cd4b  mov     [rcx], eax
0x18004cd4d  lea     rcx, [rsp+270h+var_238]
0x18004cd52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cd57  xor     ebx, ebx
0x18004cd59  lea     rcx, [rsp+270h+var_240]
0x18004cd5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004cd63  mov     eax, ebx
0x18004cd65  mov     rcx, [rbp+170h+var_10]
0x18004cd6c  xor     rcx, rsp; StackCookie
0x18004cd6f  call    __security_check_cookie
0x18004cd74  lea     r11, [rsp+270h+var_s0]
0x18004cd7c  mov     rbx, [r11+20h]
0x18004cd80  mov     rdi, [r11+28h]
0x18004cd84  mov     rsp, r11
0x18004cd87  pop     rbp
0x18004cd88  retn
0x18004cd8a  mov     r8, rdi
0x18004cd8d  lea     rdx, [rsp+270h+var_240]
0x18004cd92  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004cd97  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18004cd9c  mov     ebx, eax
0x18004cd9e  test    eax, eax
0x18004cda0  jns     short loc_18004CD4D
0x18004cda2  mov     edx, 137h
0x18004cda7  jmp     loc_18004CD1F
```
