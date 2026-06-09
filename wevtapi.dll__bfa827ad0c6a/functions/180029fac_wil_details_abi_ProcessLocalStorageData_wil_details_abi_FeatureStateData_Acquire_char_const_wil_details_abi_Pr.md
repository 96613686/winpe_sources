# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180029fac`
- end: `0x18002a10b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002a424`

## callees

- `0x180023dc8`
- `0x180024a50`
- `0x180029c48`
- `0x180029c64`
- `0x180029fac`
- `0x18002b764`
- `0x18002c40c`
- `0x18002c928`
- `0x18002cd20`
- `0x18002d504`
- `0x18002d640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a029`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002a029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029fe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029fe4`

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
0x180029fac  mov     [rsp-8+arg_10], rbx
0x180029fb1  mov     [rsp-8+arg_18], rdi
0x180029fb6  push    rbp
0x180029fb7  lea     rbp, [rsp-170h]
0x180029fbf  sub     rsp, 270h
0x180029fc6  mov     rax, cs:__security_cookie
0x180029fcd  xor     rax, rsp
0x180029fd0  mov     [rbp+170h+var_10], rax
0x180029fd7  mov     rdi, rdx
0x180029fda  mov     qword ptr [rdx], 0
0x180029fe1  mov     rbx, rcx
0x180029fe4  call    cs:__imp_GetCurrentProcessId
0x180029fea  mov     [rsp+270h+var_248], rbx
0x180029fef  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180029ff6  mov     r9d, eax
0x180029ff9  mov     [rsp+270h+var_250], 130h; int
0x18002a001  mov     edx, 104h; unsigned __int64
0x18002a006  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002a00b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002a010  mov     r9d, 1F0001h; dwDesiredAccess
0x18002a016  mov     [rsp+270h+var_240], 0
0x18002a01f  xor     r8d, r8d; dwFlags
0x18002a022  lea     rdx, [rsp+270h+Name]; lpName
0x18002a027  xor     ecx, ecx; lpMutexAttributes
0x18002a029  call    cs:__imp_CreateMutexExW
0x18002a02f  mov     rdx, rax
0x18002a032  lea     rcx, [rsp+270h+var_240]
0x18002a037  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002a03c  cmp     [rsp+270h+var_240], 0
0x18002a042  jnz     short loc_18002A04D
0x18002a044  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a049  mov     ebx, eax
0x18002a04b  jmp     short loc_18002A0B9
0x18002a04d  lea     rdx, [rsp+270h+var_238]
0x18002a052  lea     rcx, [rsp+270h+var_240]
0x18002a057  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002a05c  lea     rdx, [rsp+270h+var_230]; void **
0x18002a061  mov     [rsp+270h+var_230], 0
0x18002a06a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002a06f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18002a074  mov     ebx, eax
0x18002a076  test    eax, eax
0x18002a078  jns     short loc_18002A09A
0x18002a07a  mov     edx, 12Eh; void *
0x18002a07f  mov     rcx, [rbp+178h]; this
0x18002a086  mov     r9d, eax; char *
0x18002a089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a08e  lea     rcx, [rsp+270h+var_238]
0x18002a093  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a098  jmp     short loc_18002A0B9
0x18002a09a  mov     rcx, [rsp+270h+var_230]
0x18002a09f  test    rcx, rcx
0x18002a0a2  jz      short loc_18002A0E9
0x18002a0a4  mov     [rdi], rcx
0x18002a0a7  mov     eax, [rcx]
0x18002a0a9  inc     eax
0x18002a0ab  mov     [rcx], eax
0x18002a0ad  lea     rcx, [rsp+270h+var_238]
0x18002a0b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a0b7  xor     ebx, ebx
0x18002a0b9  lea     rcx, [rsp+270h+var_240]
0x18002a0be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a0c3  mov     eax, ebx
0x18002a0c5  mov     rcx, [rbp+170h+var_10]
0x18002a0cc  xor     rcx, rsp; StackCookie
0x18002a0cf  call    __security_check_cookie
0x18002a0d4  lea     r11, [rsp+270h+var_s0]
0x18002a0dc  mov     rbx, [r11+20h]
0x18002a0e0  mov     rdi, [r11+28h]
0x18002a0e4  mov     rsp, r11
0x18002a0e7  pop     rbp
0x18002a0e8  retn
0x18002a0e9  mov     r8, rdi
0x18002a0ec  lea     rdx, [rsp+270h+var_240]
0x18002a0f1  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002a0f6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002a0fb  mov     ebx, eax
0x18002a0fd  test    eax, eax
0x18002a0ff  jns     short loc_18002A0AD
0x18002a101  mov     edx, 137h
0x18002a106  jmp     loc_18002A07F
```
