# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180040ac0`
- end: `0x180040c1f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800477dc`

## callees

- `0x18002ff44`
- `0x180030230`
- `0x1800306e8`
- `0x18003b804`
- `0x18003f678`
- `0x180040ac0`
- `0x180040c28`
- `0x18004221c`
- `0x1800425bc`
- `0x180047bf0`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180040af8`
- `KERNEL32!GetCurrentProcessId` at `0x180040af8`
- `KERNEL32!CreateMutexExW` at `0x180040b3d`
- `KERNEL32!CreateMutexExW` at `0x180040b3d`

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
0x180040ac0  mov     [rsp-8+arg_10], rbx
0x180040ac5  mov     [rsp-8+arg_18], rdi
0x180040aca  push    rbp
0x180040acb  lea     rbp, [rsp-170h]
0x180040ad3  sub     rsp, 270h
0x180040ada  mov     rax, cs:__security_cookie
0x180040ae1  xor     rax, rsp
0x180040ae4  mov     [rbp+170h+var_10], rax
0x180040aeb  mov     rdi, rdx
0x180040aee  mov     qword ptr [rdx], 0
0x180040af5  mov     rbx, rcx
0x180040af8  call    cs:__imp_GetCurrentProcessId
0x180040afe  mov     [rsp+270h+var_248], rbx
0x180040b03  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180040b0a  mov     r9d, eax
0x180040b0d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180040b15  mov     edx, 104h; unsigned __int64
0x180040b1a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040b1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040b24  mov     r9d, 1F0001h; dwDesiredAccess
0x180040b2a  mov     [rsp+270h+var_240], 0
0x180040b33  xor     r8d, r8d; dwFlags
0x180040b36  lea     rdx, [rsp+270h+Name]; lpName
0x180040b3b  xor     ecx, ecx; lpMutexAttributes
0x180040b3d  call    cs:__imp_CreateMutexExW
0x180040b43  mov     rdx, rax
0x180040b46  lea     rcx, [rsp+270h+var_240]
0x180040b4b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180040b50  cmp     [rsp+270h+var_240], 0
0x180040b56  jnz     short loc_180040B61
0x180040b58  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180040b5d  mov     ebx, eax
0x180040b5f  jmp     short loc_180040BCD
0x180040b61  lea     rdx, [rsp+270h+var_238]
0x180040b66  lea     rcx, [rsp+270h+var_240]
0x180040b6b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180040b70  lea     rdx, [rsp+270h+var_230]; void **
0x180040b75  mov     [rsp+270h+var_230], 0
0x180040b7e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040b83  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180040b88  mov     ebx, eax
0x180040b8a  test    eax, eax
0x180040b8c  jns     short loc_180040BAE
0x180040b8e  mov     edx, 12Eh; void *
0x180040b93  mov     rcx, [rbp+178h]; this
0x180040b9a  mov     r9d, eax; char *
0x180040b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ba2  lea     rcx, [rsp+270h+var_238]
0x180040ba7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040bac  jmp     short loc_180040BCD
0x180040bae  mov     rcx, [rsp+270h+var_230]
0x180040bb3  test    rcx, rcx
0x180040bb6  jz      short loc_180040BFD
0x180040bb8  mov     [rdi], rcx
0x180040bbb  mov     eax, [rcx]
0x180040bbd  inc     eax
0x180040bbf  mov     [rcx], eax
0x180040bc1  lea     rcx, [rsp+270h+var_238]
0x180040bc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040bcb  xor     ebx, ebx
0x180040bcd  lea     rcx, [rsp+270h+var_240]
0x180040bd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040bd7  mov     eax, ebx
0x180040bd9  mov     rcx, [rbp+170h+var_10]
0x180040be0  xor     rcx, rsp; StackCookie
0x180040be3  call    __security_check_cookie
0x180040be8  lea     r11, [rsp+270h+var_s0]
0x180040bf0  mov     rbx, [r11+20h]
0x180040bf4  mov     rdi, [r11+28h]
0x180040bf8  mov     rsp, r11
0x180040bfb  pop     rbp
0x180040bfc  retn
0x180040bfd  mov     r8, rdi
0x180040c00  lea     rdx, [rsp+270h+var_240]
0x180040c05  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040c0a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180040c0f  mov     ebx, eax
0x180040c11  test    eax, eax
0x180040c13  jns     short loc_180040BC1
0x180040c15  mov     edx, 137h
0x180040c1a  jmp     loc_180040B93
```
