# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180056b28`
- end: `0x180056c7f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003d604`

## callees

- `0x180004a6c`
- `0x18000592c`
- `0x180005a68`
- `0x180005c34`
- `0x18004329c`
- `0x1800436d8`
- `0x18005388c`
- `0x180056b28`
- `0x180056ce0`
- `0x1800602b4`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180056ba5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180056ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056b60`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  int Pointer; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  void *v12; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-C0h] BYREF
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
  if ( !v11 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v11,
    v13);
  v12 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v12);
  v8 = Pointer;
  if ( Pointer < 0 )
  {
    v9 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    goto LABEL_8;
  }
  v10 = v12;
  if ( v12 )
  {
    *a2 = v12;
    ++*v10;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v8 = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 311;
      goto LABEL_11;
    }
  }
  v8 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return v8;
}

```

## disassembly

```asm
0x180056b28  mov     [rsp-8+arg_10], rbx
0x180056b2d  mov     [rsp-8+arg_18], rdi
0x180056b32  push    rbp
0x180056b33  lea     rbp, [rsp-170h]
0x180056b3b  sub     rsp, 270h
0x180056b42  mov     rax, cs:__security_cookie
0x180056b49  xor     rax, rsp
0x180056b4c  mov     [rbp+170h+var_10], rax
0x180056b53  mov     rdi, rdx
0x180056b56  mov     qword ptr [rdx], 0
0x180056b5d  mov     rbx, rcx
0x180056b60  call    cs:__imp_GetCurrentProcessId
0x180056b66  mov     [rsp+270h+var_248], rbx
0x180056b6b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180056b72  mov     r9d, eax
0x180056b75  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180056b7d  mov     edx, 104h; unsigned __int64
0x180056b82  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180056b87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056b8c  mov     r9d, 1F0001h; dwDesiredAccess
0x180056b92  mov     [rsp+270h+var_240], 0
0x180056b9b  xor     r8d, r8d; dwFlags
0x180056b9e  lea     rdx, [rsp+270h+Name]; lpName
0x180056ba3  xor     ecx, ecx; lpMutexAttributes
0x180056ba5  call    cs:__imp_CreateMutexExW
0x180056bab  mov     rdx, rax
0x180056bae  lea     rcx, [rsp+270h+var_240]
0x180056bb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180056bb8  cmp     [rsp+270h+var_240], 0
0x180056bbe  jnz     short loc_180056BC7
0x180056bc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180056bc5  jmp     short loc_180056C26
0x180056bc7  lea     rdx, [rsp+270h+var_230]
0x180056bcc  lea     rcx, [rsp+270h+var_240]
0x180056bd1  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180056bd6  lea     rdx, [rsp+270h+var_238]; void **
0x180056bdb  mov     [rsp+270h+var_238], 0
0x180056be4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180056be9  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180056bee  mov     ebx, eax
0x180056bf0  test    eax, eax
0x180056bf2  jns     short loc_180056BFB
0x180056bf4  mov     edx, 12Eh
0x180056bf9  jmp     short loc_180056C67
0x180056bfb  mov     rcx, [rsp+270h+var_238]
0x180056c00  test    rcx, rcx
0x180056c03  jz      short loc_180056C4A
0x180056c05  mov     [rdi], rcx
0x180056c08  mov     eax, [rcx]
0x180056c0a  inc     eax
0x180056c0c  mov     [rcx], eax
0x180056c0e  xor     ebx, ebx
0x180056c10  lea     rcx, [rsp+270h+var_230]
0x180056c15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180056c1a  lea     rcx, [rsp+270h+var_240]
0x180056c1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180056c24  mov     eax, ebx
0x180056c26  mov     rcx, [rbp+170h+var_10]
0x180056c2d  xor     rcx, rsp; StackCookie
0x180056c30  call    __security_check_cookie
0x180056c35  lea     r11, [rsp+270h+var_s0]
0x180056c3d  mov     rbx, [r11+20h]
0x180056c41  mov     rdi, [r11+28h]
0x180056c45  mov     rsp, r11
0x180056c48  pop     rbp
0x180056c49  retn
0x180056c4a  mov     r8, rdi
0x180056c4d  lea     rdx, [rsp+270h+var_240]
0x180056c52  lea     rcx, [rsp+270h+Name]
0x180056c57  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180056c5c  mov     ebx, eax
0x180056c5e  test    eax, eax
0x180056c60  jns     short loc_180056C0E
0x180056c62  mov     edx, 137h; void *
0x180056c67  mov     rcx, [rbp+178h]; this
0x180056c6e  lea     r8, aWil; "wil"
0x180056c75  mov     r9d, eax; char *
0x180056c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056c7d  jmp     short loc_180056C10
```
