# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180019f68`
- end: `0x18001a0ce`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001a948`

## callees

- `0x180004e64`
- `0x1800108a4`
- `0x180010a18`
- `0x1800110d8`
- `0x180012550`
- `0x180015de8`
- `0x180015e04`
- `0x1800173f4`
- `0x1800177f4`
- `0x1800178a0`
- `0x180019f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019fe5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019fa0`

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
0x180019f68  mov     [rsp-8+arg_10], rbx
0x180019f6d  mov     [rsp-8+arg_18], rdi
0x180019f72  push    rbp
0x180019f73  lea     rbp, [rsp-170h]
0x180019f7b  sub     rsp, 270h
0x180019f82  mov     rax, cs:__security_cookie
0x180019f89  xor     rax, rsp
0x180019f8c  mov     [rbp+170h+var_10], rax
0x180019f93  mov     rdi, rdx
0x180019f96  mov     qword ptr [rdx], 0
0x180019f9d  mov     rbx, rcx
0x180019fa0  call    cs:__imp_GetCurrentProcessId
0x180019fa6  mov     [rsp+270h+var_248], rbx
0x180019fab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180019fb2  mov     r9d, eax
0x180019fb5  mov     [rsp+270h+var_250], 130h; int
0x180019fbd  mov     edx, 104h; unsigned __int64
0x180019fc2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019fc7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019fcc  mov     r9d, 1F0001h; dwDesiredAccess
0x180019fd2  mov     [rsp+270h+var_240], 0
0x180019fdb  xor     r8d, r8d; dwFlags
0x180019fde  lea     rdx, [rsp+270h+Name]; lpName
0x180019fe3  xor     ecx, ecx; lpMutexAttributes
0x180019fe5  call    cs:__imp_CreateMutexExW
0x180019feb  mov     rdx, rax
0x180019fee  lea     rcx, [rsp+270h+var_240]
0x180019ff3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019ff8  cmp     [rsp+270h+var_240], 0
0x180019ffe  jnz     short loc_18001A009
0x18001a000  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a005  mov     ebx, eax
0x18001a007  jmp     short loc_18001A07C
0x18001a009  lea     rdx, [rsp+270h+var_238]
0x18001a00e  lea     rcx, [rsp+270h+var_240]
0x18001a013  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001a018  lea     rdx, [rsp+270h+var_230]; void **
0x18001a01d  mov     [rsp+270h+var_230], 0
0x18001a026  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001a02b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001a030  mov     ebx, eax
0x18001a032  test    eax, eax
0x18001a034  jns     short loc_18001A05D
0x18001a036  mov     edx, 12Eh; void *
0x18001a03b  mov     rcx, [rbp+178h]; this
0x18001a042  lea     r8, aWil; "wil"
0x18001a049  mov     r9d, eax; char *
0x18001a04c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a051  lea     rcx, [rsp+270h+var_238]
0x18001a056  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a05b  jmp     short loc_18001A07C
0x18001a05d  mov     rcx, [rsp+270h+var_230]
0x18001a062  test    rcx, rcx
0x18001a065  jz      short loc_18001A0AC
0x18001a067  mov     [rdi], rcx
0x18001a06a  mov     eax, [rcx]
0x18001a06c  inc     eax
0x18001a06e  mov     [rcx], eax
0x18001a070  lea     rcx, [rsp+270h+var_238]
0x18001a075  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a07a  xor     ebx, ebx
0x18001a07c  lea     rcx, [rsp+270h+var_240]
0x18001a081  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a086  mov     eax, ebx
0x18001a088  mov     rcx, [rbp+170h+var_10]
0x18001a08f  xor     rcx, rsp; StackCookie
0x18001a092  call    __security_check_cookie
0x18001a097  lea     r11, [rsp+270h+var_s0]
0x18001a09f  mov     rbx, [r11+20h]
0x18001a0a3  mov     rdi, [r11+28h]
0x18001a0a7  mov     rsp, r11
0x18001a0aa  pop     rbp
0x18001a0ab  retn
0x18001a0ac  mov     r8, rdi
0x18001a0af  lea     rdx, [rsp+270h+var_240]
0x18001a0b4  lea     rcx, [rsp+270h+Name]
0x18001a0b9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001a0be  mov     ebx, eax
0x18001a0c0  test    eax, eax
0x18001a0c2  jns     short loc_18001A070
0x18001a0c4  mov     edx, 137h
0x18001a0c9  jmp     loc_18001A03B
```
