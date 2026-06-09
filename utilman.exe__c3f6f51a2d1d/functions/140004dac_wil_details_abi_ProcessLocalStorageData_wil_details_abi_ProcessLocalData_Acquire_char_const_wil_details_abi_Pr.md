# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140004dac`
- end: `0x140004f1f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140006028`

## callees

- `0x140002480`
- `0x1400048c4`
- `0x1400048e4`
- `0x140004dac`
- `0x140005ca0`
- `0x140006a94`
- `0x14000815c`
- `0x1400088cc`
- `0x140008d7c`
- `0x140009714`
- `0x140009cdc`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140004e2f`
- `KERNEL32!CreateMutexExW` at `0x140004e2f`
- `KERNEL32!GetCurrentProcessId` at `0x140004de4`
- `KERNEL32!GetCurrentProcessId` at `0x140004de4`

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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x140004dac  mov     [rsp-8+arg_10], rbx
0x140004db1  mov     [rsp-8+arg_18], rdi
0x140004db6  push    rbp
0x140004db7  lea     rbp, [rsp-170h]
0x140004dbf  sub     rsp, 270h
0x140004dc6  mov     rax, cs:__security_cookie
0x140004dcd  xor     rax, rsp
0x140004dd0  mov     [rbp+170h+var_10], rax
0x140004dd7  mov     rdi, rdx
0x140004dda  mov     qword ptr [rdx], 0
0x140004de1  mov     rbx, rcx
0x140004de4  call    cs:__imp_GetCurrentProcessId
0x140004deb  nop     dword ptr [rax+rax+00h]
0x140004df0  mov     [rsp+270h+var_248], rbx
0x140004df5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004dfc  mov     r9d, eax
0x140004dff  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140004e07  mov     edx, 104h; unsigned __int64
0x140004e0c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004e11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004e16  mov     r9d, 1F0001h; dwDesiredAccess
0x140004e1c  mov     [rsp+270h+var_240], 0
0x140004e25  xor     r8d, r8d; dwFlags
0x140004e28  lea     rdx, [rsp+270h+Name]; lpName
0x140004e2d  xor     ecx, ecx; lpMutexAttributes
0x140004e2f  call    cs:__imp_CreateMutexExW
0x140004e36  nop     dword ptr [rax+rax+00h]
0x140004e3b  mov     rdx, rax
0x140004e3e  lea     rcx, [rsp+270h+var_240]
0x140004e43  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140004e48  cmp     [rsp+270h+var_240], 0
0x140004e4e  jnz     short loc_140004E59
0x140004e50  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004e55  mov     ebx, eax
0x140004e57  jmp     short loc_140004ECC
0x140004e59  lea     rdx, [rsp+270h+var_238]
0x140004e5e  lea     rcx, [rsp+270h+var_240]
0x140004e63  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140004e68  lea     rdx, [rsp+270h+var_230]; void **
0x140004e6d  mov     [rsp+270h+var_230], 0
0x140004e76  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004e7b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140004e80  mov     ebx, eax
0x140004e82  test    eax, eax
0x140004e84  jns     short loc_140004EAD
0x140004e86  mov     edx, 12Eh; void *
0x140004e8b  mov     rcx, [rbp+178h]; this
0x140004e92  lea     r8, aWil; "wil"
0x140004e99  mov     r9d, eax; char *
0x140004e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ea1  lea     rcx, [rsp+270h+var_238]
0x140004ea6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004eab  jmp     short loc_140004ECC
0x140004ead  mov     rcx, [rsp+270h+var_230]
0x140004eb2  test    rcx, rcx
0x140004eb5  jz      short loc_140004EFD
0x140004eb7  mov     [rdi], rcx
0x140004eba  mov     eax, [rcx]
0x140004ebc  inc     eax
0x140004ebe  mov     [rcx], eax
0x140004ec0  lea     rcx, [rsp+270h+var_238]
0x140004ec5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004eca  xor     ebx, ebx
0x140004ecc  lea     rcx, [rsp+270h+var_240]
0x140004ed1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004ed6  mov     eax, ebx
0x140004ed8  mov     rcx, [rbp+170h+var_10]
0x140004edf  xor     rcx, rsp; StackCookie
0x140004ee2  call    __security_check_cookie
0x140004ee7  lea     r11, [rsp+270h+var_s0]
0x140004eef  mov     rbx, [r11+20h]
0x140004ef3  mov     rdi, [r11+28h]
0x140004ef7  mov     rsp, r11
0x140004efa  pop     rbp
0x140004efb  retn
0x140004efd  mov     r8, rdi
0x140004f00  lea     rdx, [rsp+270h+var_240]
0x140004f05  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140004f0a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140004f0f  mov     ebx, eax
0x140004f11  test    eax, eax
0x140004f13  jns     short loc_140004EC0
0x140004f15  mov     edx, 137h
0x140004f1a  jmp     loc_140004E8B
```
