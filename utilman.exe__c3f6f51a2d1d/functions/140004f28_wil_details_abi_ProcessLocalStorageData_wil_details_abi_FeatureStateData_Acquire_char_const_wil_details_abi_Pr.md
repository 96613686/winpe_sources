# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004f28`
- end: `0x14000509b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005eb8`

## callees

- `0x140002480`
- `0x1400048c4`
- `0x1400048e4`
- `0x140004f28`
- `0x140005ca0`
- `0x140006bf8`
- `0x14000815c`
- `0x1400088cc`
- `0x140008d7c`
- `0x140009714`
- `0x140009cdc`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140004fab`
- `KERNEL32!CreateMutexExW` at `0x140004fab`
- `KERNEL32!GetCurrentProcessId` at `0x140004f60`
- `KERNEL32!GetCurrentProcessId` at `0x140004f60`

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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x140004f28  mov     [rsp-8+arg_10], rbx
0x140004f2d  mov     [rsp-8+arg_18], rdi
0x140004f32  push    rbp
0x140004f33  lea     rbp, [rsp-170h]
0x140004f3b  sub     rsp, 270h
0x140004f42  mov     rax, cs:__security_cookie
0x140004f49  xor     rax, rsp
0x140004f4c  mov     [rbp+170h+var_10], rax
0x140004f53  mov     rdi, rdx
0x140004f56  mov     qword ptr [rdx], 0
0x140004f5d  mov     rbx, rcx
0x140004f60  call    cs:__imp_GetCurrentProcessId
0x140004f67  nop     dword ptr [rax+rax+00h]
0x140004f6c  mov     [rsp+270h+var_248], rbx
0x140004f71  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004f78  mov     r9d, eax
0x140004f7b  mov     [rsp+270h+var_250], 130h; int
0x140004f83  mov     edx, 104h; unsigned __int64
0x140004f88  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004f8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004f92  mov     r9d, 1F0001h; dwDesiredAccess
0x140004f98  mov     [rsp+270h+var_240], 0
0x140004fa1  xor     r8d, r8d; dwFlags
0x140004fa4  lea     rdx, [rsp+270h+Name]; lpName
0x140004fa9  xor     ecx, ecx; lpMutexAttributes
0x140004fab  call    cs:__imp_CreateMutexExW
0x140004fb2  nop     dword ptr [rax+rax+00h]
0x140004fb7  mov     rdx, rax
0x140004fba  lea     rcx, [rsp+270h+var_240]
0x140004fbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004fc4  cmp     [rsp+270h+var_240], 0
0x140004fca  jnz     short loc_140004FD5
0x140004fcc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004fd1  mov     ebx, eax
0x140004fd3  jmp     short loc_140005048
0x140004fd5  lea     rdx, [rsp+270h+var_238]
0x140004fda  lea     rcx, [rsp+270h+var_240]
0x140004fdf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004fe4  lea     rdx, [rsp+270h+var_230]; void **
0x140004fe9  mov     [rsp+270h+var_230], 0
0x140004ff2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004ff7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004ffc  mov     ebx, eax
0x140004ffe  test    eax, eax
0x140005000  jns     short loc_140005029
0x140005002  mov     edx, 12Eh; void *
0x140005007  mov     rcx, [rbp+178h]; this
0x14000500e  lea     r8, aWil; "wil"
0x140005015  mov     r9d, eax; char *
0x140005018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000501d  lea     rcx, [rsp+270h+var_238]
0x140005022  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005027  jmp     short loc_140005048
0x140005029  mov     rcx, [rsp+270h+var_230]
0x14000502e  test    rcx, rcx
0x140005031  jz      short loc_140005079
0x140005033  mov     [rdi], rcx
0x140005036  mov     eax, [rcx]
0x140005038  inc     eax
0x14000503a  mov     [rcx], eax
0x14000503c  lea     rcx, [rsp+270h+var_238]
0x140005041  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005046  xor     ebx, ebx
0x140005048  lea     rcx, [rsp+270h+var_240]
0x14000504d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005052  mov     eax, ebx
0x140005054  mov     rcx, [rbp+170h+var_10]
0x14000505b  xor     rcx, rsp; StackCookie
0x14000505e  call    __security_check_cookie
0x140005063  lea     r11, [rsp+270h+var_s0]
0x14000506b  mov     rbx, [r11+20h]
0x14000506f  mov     rdi, [r11+28h]
0x140005073  mov     rsp, r11
0x140005076  pop     rbp
0x140005077  retn
0x140005079  mov     r8, rdi
0x14000507c  lea     rdx, [rsp+270h+var_240]
0x140005081  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140005086  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000508b  mov     ebx, eax
0x14000508d  test    eax, eax
0x14000508f  jns     short loc_14000503C
0x140005091  mov     edx, 137h
0x140005096  jmp     loc_140005007
```
