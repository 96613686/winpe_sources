# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001defc`
- end: `0x18001e077`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e32c`

## callees

- `0x18001be10`
- `0x18001d848`
- `0x18001d864`
- `0x18001defc`
- `0x18001ecc8`
- `0x18001fcfc`
- `0x18002100c`
- `0x180021ab8`
- `0x180021e4c`
- `0x180022614`
- `0x180022810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001df79`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001df79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df34`

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
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001defc  mov     [rsp-8+arg_10], rbx
0x18001df01  mov     [rsp-8+arg_18], rdi
0x18001df06  push    rbp
0x18001df07  lea     rbp, [rsp-170h]
0x18001df0f  sub     rsp, 270h
0x18001df16  mov     rax, cs:__security_cookie
0x18001df1d  xor     rax, rsp
0x18001df20  mov     [rbp+170h+var_10], rax
0x18001df27  mov     rdi, rdx
0x18001df2a  mov     rbx, rcx
0x18001df2d  mov     qword ptr [rdx], 0
0x18001df34  call    cs:__imp_GetCurrentProcessId
0x18001df3a  mov     r9d, eax
0x18001df3d  mov     [rsp+270h+var_248], rbx
0x18001df42  mov     [rsp+270h+var_250], 130h; int
0x18001df4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001df51  mov     edx, 104h; unsigned __int64
0x18001df56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001df5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001df60  mov     [rsp+270h+var_240], 0
0x18001df69  mov     r9d, 1F0001h; dwDesiredAccess
0x18001df6f  xor     r8d, r8d; dwFlags
0x18001df72  lea     rdx, [rsp+270h+Name]; lpName
0x18001df77  xor     ecx, ecx; lpMutexAttributes
0x18001df79  call    cs:__imp_CreateMutexExW
0x18001df7f  mov     rdx, rax
0x18001df82  lea     rcx, [rsp+270h+var_240]
0x18001df87  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001df8c  cmp     [rsp+270h+var_240], 0
0x18001df92  jnz     short loc_18001DF9D
0x18001df94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001df99  mov     ebx, eax
0x18001df9b  jmp     short loc_18001E00D
0x18001df9d  lea     rdx, [rsp+270h+var_238]
0x18001dfa2  lea     rcx, [rsp+270h+var_240]
0x18001dfa7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001dfac  nop
0x18001dfad  mov     [rsp+270h+var_230], 0
0x18001dfb6  lea     rdx, [rsp+270h+var_230]; void **
0x18001dfbb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dfc0  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001dfc5  mov     ebx, eax
0x18001dfc7  test    eax, eax
0x18001dfc9  jns     short loc_18001DFED
0x18001dfcb  mov     rcx, [rbp+178h]; this
0x18001dfd2  mov     r9d, eax; char *
0x18001dfd5  mov     edx, 12Eh; void *
0x18001dfda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfdf  nop
0x18001dfe0  lea     rcx, [rsp+270h+var_238]
0x18001dfe5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dfea  nop
0x18001dfeb  jmp     short loc_18001E00D
0x18001dfed  mov     rcx, [rsp+270h+var_230]
0x18001dff2  test    rcx, rcx
0x18001dff5  jz      short loc_18001E03D
0x18001dff7  mov     [rdi], rcx
0x18001dffa  mov     eax, [rcx]
0x18001dffc  inc     eax
0x18001dffe  mov     [rcx], eax
0x18001e000  lea     rcx, [rsp+270h+var_238]
0x18001e005  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e00a  nop
0x18001e00b  xor     ebx, ebx
0x18001e00d  lea     rcx, [rsp+270h+var_240]
0x18001e012  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e017  mov     eax, ebx
0x18001e019  mov     rcx, [rbp+170h+var_10]
0x18001e020  xor     rcx, rsp; StackCookie
0x18001e023  call    __security_check_cookie
0x18001e028  lea     r11, [rsp+270h+var_s0]
0x18001e030  mov     rbx, [r11+20h]
0x18001e034  mov     rdi, [r11+28h]
0x18001e038  mov     rsp, r11
0x18001e03b  pop     rbp
0x18001e03c  retn
0x18001e03d  mov     r8, rdi
0x18001e040  lea     rdx, [rsp+270h+var_240]
0x18001e045  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e04a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001e04f  mov     ebx, eax
0x18001e051  test    eax, eax
0x18001e053  jns     short loc_18001E000
0x18001e055  mov     rcx, [rbp+178h]; this
0x18001e05c  mov     r9d, eax; char *
0x18001e05f  mov     edx, 137h; void *
0x18001e064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e069  nop
0x18001e06a  lea     rcx, [rsp+270h+var_238]
0x18001e06f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e074  nop
0x18001e075  jmp     short loc_18001E00D
```
