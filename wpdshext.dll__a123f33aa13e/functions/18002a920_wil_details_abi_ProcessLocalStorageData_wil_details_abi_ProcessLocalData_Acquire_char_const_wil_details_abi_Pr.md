# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002a920`
- end: `0x18002aaca`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800380a0`

## callees

- `0x180028e70`
- `0x18002a920`
- `0x18002aad0`
- `0x18002ab04`
- `0x18002ab58`
- `0x18002ae98`
- `0x18002b7d0`
- `0x18002bee4`
- `0x180035590`
- `0x180037858`
- `0x180038e90`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18002a99d`
- `KERNEL32!CreateMutexExW` at `0x18002a99d`
- `KERNEL32!GetCurrentProcessId` at `0x18002a958`
- `KERNEL32!GetCurrentProcessId` at `0x18002a958`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18002a920  mov     [rsp-8+arg_10], rbx
0x18002a925  mov     [rsp-8+arg_18], rdi
0x18002a92a  push    rbp
0x18002a92b  lea     rbp, [rsp-170h]
0x18002a933  sub     rsp, 270h
0x18002a93a  mov     rax, cs:__security_cookie
0x18002a941  xor     rax, rsp
0x18002a944  mov     [rbp+170h+var_10], rax
0x18002a94b  mov     rdi, rdx
0x18002a94e  mov     qword ptr [rdx], 0
0x18002a955  mov     rbx, rcx
0x18002a958  call    cs:__imp_GetCurrentProcessId
0x18002a95e  mov     [rsp+270h+var_248], rbx
0x18002a963  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002a96a  mov     r9d, eax
0x18002a96d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002a975  mov     edx, 104h; unsigned __int64
0x18002a97a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a97f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a984  mov     r9d, 1F0001h; dwDesiredAccess
0x18002a98a  mov     [rsp+270h+var_240], 0
0x18002a993  xor     r8d, r8d; dwFlags
0x18002a996  lea     rdx, [rsp+270h+Name]; lpName
0x18002a99b  xor     ecx, ecx; lpMutexAttributes
0x18002a99d  call    cs:__imp_CreateMutexExW
0x18002a9a3  mov     rdx, rax
0x18002a9a6  lea     rcx, [rsp+270h+var_240]
0x18002a9ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002a9b0  cmp     [rsp+270h+var_240], 0
0x18002a9b6  jnz     short loc_18002A9C4
0x18002a9b8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a9bd  mov     ebx, eax
0x18002a9bf  jmp     loc_18002AA75
0x18002a9c4  lea     rdx, [rsp+270h+var_238]
0x18002a9c9  lea     rcx, [rsp+270h+var_240]
0x18002a9ce  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002a9d3  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18002a9d8  mov     [rsp+270h+var_230], 0
0x18002a9e1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002a9e6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002a9eb  mov     ebx, eax
0x18002a9ed  test    eax, eax
0x18002a9ef  jns     short loc_18002AA4E
0x18002a9f1  mov     rcx, [rbp+178h]; this
0x18002a9f8  lea     r8, aWil; "wil"
0x18002a9ff  mov     r9d, eax; char *
0x18002aa02  mov     edx, 66h ; 'f'; void *
0x18002aa07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa0c  mov     rcx, [rbp+178h]; this
0x18002aa13  lea     r8, aWil; "wil"
0x18002aa1a  mov     r9d, ebx; char *
0x18002aa1d  mov     edx, 6Fh ; 'o'; void *
0x18002aa22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa27  mov     r9d, ebx; char *
0x18002aa2a  mov     edx, 12Eh; void *
0x18002aa2f  mov     rcx, [rbp+178h]; this
0x18002aa36  lea     r8, aWil; "wil"
0x18002aa3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa42  lea     rcx, [rsp+270h+var_238]
0x18002aa47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002aa4c  jmp     short loc_18002AA75
0x18002aa4e  mov     rax, [rsp+270h+var_230]
0x18002aa53  lea     rcx, ds:0[rax*4]
0x18002aa5b  test    rcx, rcx
0x18002aa5e  jz      short loc_18002AAA5
0x18002aa60  mov     [rdi], rcx
0x18002aa63  mov     eax, [rcx]
0x18002aa65  inc     eax
0x18002aa67  mov     [rcx], eax
0x18002aa69  lea     rcx, [rsp+270h+var_238]
0x18002aa6e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002aa73  xor     ebx, ebx
0x18002aa75  lea     rcx, [rsp+270h+var_240]
0x18002aa7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002aa7f  mov     eax, ebx
0x18002aa81  mov     rcx, [rbp+170h+var_10]
0x18002aa88  xor     rcx, rsp; StackCookie
0x18002aa8b  call    __security_check_cookie
0x18002aa90  lea     r11, [rsp+270h+var_s0]
0x18002aa98  mov     rbx, [r11+20h]
0x18002aa9c  mov     rdi, [r11+28h]
0x18002aaa0  mov     rsp, r11
0x18002aaa3  pop     rbp
0x18002aaa4  retn
0x18002aaa5  mov     r8, rdi
0x18002aaa8  lea     rdx, [rsp+270h+var_240]
0x18002aaad  lea     rcx, [rsp+270h+Name]
0x18002aab2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002aab7  mov     ebx, eax
0x18002aab9  test    eax, eax
0x18002aabb  jns     short loc_18002AA69
0x18002aabd  mov     r9d, eax
0x18002aac0  mov     edx, 137h
0x18002aac5  jmp     loc_18002AA2F
```
