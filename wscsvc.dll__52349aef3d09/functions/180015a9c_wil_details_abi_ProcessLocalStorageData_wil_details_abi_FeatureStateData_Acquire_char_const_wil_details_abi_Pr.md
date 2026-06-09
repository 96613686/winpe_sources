# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180015a9c`
- end: `0x180015bdf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015a44`

## callees

- `0x180015a9c`
- `0x180016ae8`
- `0x1800205e4`
- `0x1800228ec`
- `0x180026cd0`
- `0x180026cec`
- `0x18002956c`
- `0x1800296d4`
- `0x18002e3b0`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015b10`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015b10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015ad4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015ad4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  int Pointer; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  HANDLE Mutex; // [rsp+30h] [rbp-D0h] BYREF
  void *v11; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    v12);
  v11 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v11);
  v7 = Pointer;
  if ( Pointer < 0 )
  {
    v8 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    goto LABEL_8;
  }
  v9 = v11;
  if ( v11 )
  {
    *a2 = v11;
    ++*v9;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v7 = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 311;
      goto LABEL_11;
    }
  }
  v7 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Mutex);
  return v7;
}

```

## disassembly

```asm
0x180015a9c  mov     [rsp-8+arg_10], rbx
0x180015aa1  mov     [rsp-8+arg_18], rdi
0x180015aa6  push    rbp
0x180015aa7  lea     rbp, [rsp-170h]
0x180015aaf  sub     rsp, 270h
0x180015ab6  mov     rax, cs:__security_cookie
0x180015abd  xor     rax, rsp
0x180015ac0  mov     [rbp+170h+var_10], rax
0x180015ac7  mov     rdi, rdx
0x180015aca  mov     qword ptr [rdx], 0
0x180015ad1  mov     rbx, rcx
0x180015ad4  call    cs:__imp_GetCurrentProcessId
0x180015ada  mov     [rsp+270h+var_248], rbx
0x180015adf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180015ae6  mov     r9d, eax
0x180015ae9  mov     [rsp+270h+var_250], 130h; int
0x180015af1  mov     edx, 104h; unsigned __int64
0x180015af6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180015afb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015b00  mov     r9d, 1F0001h; dwDesiredAccess
0x180015b06  lea     rdx, [rsp+270h+Name]; lpName
0x180015b0b  xor     r8d, r8d; dwFlags
0x180015b0e  xor     ecx, ecx; lpMutexAttributes
0x180015b10  call    cs:__imp_CreateMutexExW
0x180015b16  mov     [rsp+270h+var_240], rax
0x180015b1b  test    rax, rax
0x180015b1e  jnz     short loc_180015B27
0x180015b20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015b25  jmp     short loc_180015B86
0x180015b27  lea     rdx, [rsp+270h+var_230]
0x180015b2c  lea     rcx, [rsp+270h+var_240]
0x180015b31  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180015b36  lea     rdx, [rsp+270h+var_238]; void **
0x180015b3b  mov     [rsp+270h+var_238], 0
0x180015b44  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180015b49  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180015b4e  mov     ebx, eax
0x180015b50  test    eax, eax
0x180015b52  jns     short loc_180015B5B
0x180015b54  mov     edx, 12Eh
0x180015b59  jmp     short loc_180015BC7
0x180015b5b  mov     rcx, [rsp+270h+var_238]
0x180015b60  test    rcx, rcx
0x180015b63  jz      short loc_180015BAA
0x180015b65  mov     [rdi], rcx
0x180015b68  mov     eax, [rcx]
0x180015b6a  inc     eax
0x180015b6c  mov     [rcx], eax
0x180015b6e  xor     ebx, ebx
0x180015b70  lea     rcx, [rsp+270h+var_230]
0x180015b75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015b7a  lea     rcx, [rsp+270h+var_240]
0x180015b7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015b84  mov     eax, ebx
0x180015b86  mov     rcx, [rbp+170h+var_10]
0x180015b8d  xor     rcx, rsp; StackCookie
0x180015b90  call    __security_check_cookie
0x180015b95  lea     r11, [rsp+270h+var_s0]
0x180015b9d  mov     rbx, [r11+20h]
0x180015ba1  mov     rdi, [r11+28h]
0x180015ba5  mov     rsp, r11
0x180015ba8  pop     rbp
0x180015ba9  retn
0x180015baa  mov     r8, rdi
0x180015bad  lea     rdx, [rsp+270h+var_240]
0x180015bb2  lea     rcx, [rsp+270h+Name]
0x180015bb7  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180015bbc  mov     ebx, eax
0x180015bbe  test    eax, eax
0x180015bc0  jns     short loc_180015B6E
0x180015bc2  mov     edx, 137h; void *
0x180015bc7  mov     rcx, [rbp+178h]; this
0x180015bce  lea     r8, aWil; "wil"
0x180015bd5  mov     r9d, eax; char *
0x180015bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bdd  jmp     short loc_180015B70
```
