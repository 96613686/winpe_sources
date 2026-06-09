# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000d724`
- end: `0x18000d883`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e678`

## callees

- `0x18000a704`
- `0x18000a9b4`
- `0x18000aa00`
- `0x18000b550`
- `0x18000d554`
- `0x18000d570`
- `0x18000d724`
- `0x18000fefc`
- `0x180010190`
- `0x180010934`
- `0x180010b24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d7a1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d7a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d75c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d75c`

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
0x18000d724  mov     [rsp-8+arg_10], rbx
0x18000d729  mov     [rsp-8+arg_18], rdi
0x18000d72e  push    rbp
0x18000d72f  lea     rbp, [rsp-170h]
0x18000d737  sub     rsp, 270h
0x18000d73e  mov     rax, cs:__security_cookie
0x18000d745  xor     rax, rsp
0x18000d748  mov     [rbp+170h+var_10], rax
0x18000d74f  mov     rdi, rdx
0x18000d752  mov     qword ptr [rdx], 0
0x18000d759  mov     rbx, rcx
0x18000d75c  call    cs:__imp_GetCurrentProcessId
0x18000d762  mov     [rsp+270h+var_248], rbx
0x18000d767  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d76e  mov     r9d, eax
0x18000d771  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000d779  mov     edx, 104h; unsigned __int64
0x18000d77e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d783  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d788  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d78e  mov     [rsp+270h+var_240], 0
0x18000d797  xor     r8d, r8d; dwFlags
0x18000d79a  lea     rdx, [rsp+270h+Name]; lpName
0x18000d79f  xor     ecx, ecx; lpMutexAttributes
0x18000d7a1  call    cs:__imp_CreateMutexExW
0x18000d7a7  mov     rdx, rax
0x18000d7aa  lea     rcx, [rsp+270h+var_240]
0x18000d7af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000d7b4  cmp     [rsp+270h+var_240], 0
0x18000d7ba  jnz     short loc_18000D7C5
0x18000d7bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d7c1  mov     ebx, eax
0x18000d7c3  jmp     short loc_18000D831
0x18000d7c5  lea     rdx, [rsp+270h+var_238]
0x18000d7ca  lea     rcx, [rsp+270h+var_240]
0x18000d7cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000d7d4  lea     rdx, [rsp+270h+var_230]; void **
0x18000d7d9  mov     [rsp+270h+var_230], 0
0x18000d7e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d7e7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000d7ec  mov     ebx, eax
0x18000d7ee  test    eax, eax
0x18000d7f0  jns     short loc_18000D812
0x18000d7f2  mov     edx, 12Eh; void *
0x18000d7f7  mov     rcx, [rbp+178h]; this
0x18000d7fe  mov     r9d, eax; char *
0x18000d801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d806  lea     rcx, [rsp+270h+var_238]
0x18000d80b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d810  jmp     short loc_18000D831
0x18000d812  mov     rcx, [rsp+270h+var_230]
0x18000d817  test    rcx, rcx
0x18000d81a  jz      short loc_18000D861
0x18000d81c  mov     [rdi], rcx
0x18000d81f  mov     eax, [rcx]
0x18000d821  inc     eax
0x18000d823  mov     [rcx], eax
0x18000d825  lea     rcx, [rsp+270h+var_238]
0x18000d82a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d82f  xor     ebx, ebx
0x18000d831  lea     rcx, [rsp+270h+var_240]
0x18000d836  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d83b  mov     eax, ebx
0x18000d83d  mov     rcx, [rbp+170h+var_10]
0x18000d844  xor     rcx, rsp; StackCookie
0x18000d847  call    __security_check_cookie
0x18000d84c  lea     r11, [rsp+270h+var_s0]
0x18000d854  mov     rbx, [r11+20h]
0x18000d858  mov     rdi, [r11+28h]
0x18000d85c  mov     rsp, r11
0x18000d85f  pop     rbp
0x18000d860  retn
0x18000d861  mov     r8, rdi
0x18000d864  lea     rdx, [rsp+270h+var_240]
0x18000d869  lea     rcx, [rsp+270h+Name]
0x18000d86e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d873  mov     ebx, eax
0x18000d875  test    eax, eax
0x18000d877  jns     short loc_18000D825
0x18000d879  mov     edx, 137h
0x18000d87e  jmp     loc_18000D7F7
```
