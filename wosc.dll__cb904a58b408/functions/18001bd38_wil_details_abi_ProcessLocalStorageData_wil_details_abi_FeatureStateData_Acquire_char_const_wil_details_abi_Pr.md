# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001bd38`
- end: `0x18001be9e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001c67c`

## callees

- `0x180003110`
- `0x18000e5ac`
- `0x18001b6cc`
- `0x18001b6e8`
- `0x18001bd38`
- `0x18001c464`
- `0x18001ce2c`
- `0x18001e7e4`
- `0x18001eb3c`
- `0x18001f744`
- `0x18001f88c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bdb5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bdb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bd70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bd70`

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
0x18001bd38  mov     [rsp-8+arg_10], rbx
0x18001bd3d  mov     [rsp-8+arg_18], rdi
0x18001bd42  push    rbp
0x18001bd43  lea     rbp, [rsp-170h]
0x18001bd4b  sub     rsp, 270h
0x18001bd52  mov     rax, cs:__security_cookie
0x18001bd59  xor     rax, rsp
0x18001bd5c  mov     [rbp+170h+var_10], rax
0x18001bd63  mov     rdi, rdx
0x18001bd66  mov     qword ptr [rdx], 0
0x18001bd6d  mov     rbx, rcx
0x18001bd70  call    cs:__imp_GetCurrentProcessId
0x18001bd76  mov     [rsp+270h+var_248], rbx
0x18001bd7b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001bd82  mov     r9d, eax
0x18001bd85  mov     [rsp+270h+var_250], 130h; int
0x18001bd8d  mov     edx, 104h; unsigned __int64
0x18001bd92  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bd97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bd9c  mov     r9d, 1F0001h; dwDesiredAccess
0x18001bda2  mov     [rsp+270h+var_240], 0
0x18001bdab  xor     r8d, r8d; dwFlags
0x18001bdae  lea     rdx, [rsp+270h+Name]; lpName
0x18001bdb3  xor     ecx, ecx; lpMutexAttributes
0x18001bdb5  call    cs:__imp_CreateMutexExW
0x18001bdbb  mov     rdx, rax
0x18001bdbe  lea     rcx, [rsp+270h+var_240]
0x18001bdc3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001bdc8  cmp     [rsp+270h+var_240], 0
0x18001bdce  jnz     short loc_18001BDD9
0x18001bdd0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001bdd5  mov     ebx, eax
0x18001bdd7  jmp     short loc_18001BE4C
0x18001bdd9  lea     rdx, [rsp+270h+var_238]
0x18001bdde  lea     rcx, [rsp+270h+var_240]
0x18001bde3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001bde8  lea     rdx, [rsp+270h+var_230]; void **
0x18001bded  mov     [rsp+270h+var_230], 0
0x18001bdf6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001bdfb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001be00  mov     ebx, eax
0x18001be02  test    eax, eax
0x18001be04  jns     short loc_18001BE2D
0x18001be06  mov     edx, 12Eh; void *
0x18001be0b  mov     rcx, [rbp+178h]; this
0x18001be12  lea     r8, aWil; "wil"
0x18001be19  mov     r9d, eax; char *
0x18001be1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be21  lea     rcx, [rsp+270h+var_238]
0x18001be26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001be2b  jmp     short loc_18001BE4C
0x18001be2d  mov     rcx, [rsp+270h+var_230]
0x18001be32  test    rcx, rcx
0x18001be35  jz      short loc_18001BE7C
0x18001be37  mov     [rdi], rcx
0x18001be3a  mov     eax, [rcx]
0x18001be3c  inc     eax
0x18001be3e  mov     [rcx], eax
0x18001be40  lea     rcx, [rsp+270h+var_238]
0x18001be45  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001be4a  xor     ebx, ebx
0x18001be4c  lea     rcx, [rsp+270h+var_240]
0x18001be51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001be56  mov     eax, ebx
0x18001be58  mov     rcx, [rbp+170h+var_10]
0x18001be5f  xor     rcx, rsp; StackCookie
0x18001be62  call    __security_check_cookie
0x18001be67  lea     r11, [rsp+270h+var_s0]
0x18001be6f  mov     rbx, [r11+20h]
0x18001be73  mov     rdi, [r11+28h]
0x18001be77  mov     rsp, r11
0x18001be7a  pop     rbp
0x18001be7b  retn
0x18001be7c  mov     r8, rdi
0x18001be7f  lea     rdx, [rsp+270h+var_240]
0x18001be84  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001be89  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001be8e  mov     ebx, eax
0x18001be90  test    eax, eax
0x18001be92  jns     short loc_18001BE40
0x18001be94  mov     edx, 137h
0x18001be99  jmp     loc_18001BE0B
```
