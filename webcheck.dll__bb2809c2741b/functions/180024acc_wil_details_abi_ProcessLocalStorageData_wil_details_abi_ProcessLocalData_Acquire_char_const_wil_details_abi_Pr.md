# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180024acc`
- end: `0x180024c61`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002555c`

## callees

- `0x180004adc`
- `0x180024a4c`
- `0x180024a68`
- `0x180024acc`
- `0x1800253e8`
- `0x180025dc0`
- `0x1800269d4`
- `0x180026e5c`
- `0x180027170`
- `0x18002721c`
- `0x180029280`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180024b49`
- `KERNEL32!CreateMutexExW` at `0x180024b49`
- `KERNEL32!GetCurrentProcessId` at `0x180024b04`
- `KERNEL32!GetCurrentProcessId` at `0x180024b04`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180024acc  mov     [rsp-8+arg_10], rbx
0x180024ad1  mov     [rsp-8+arg_18], rdi
0x180024ad6  push    rbp
0x180024ad7  lea     rbp, [rsp-170h]
0x180024adf  sub     rsp, 270h
0x180024ae6  mov     rax, cs:__security_cookie
0x180024aed  xor     rax, rsp
0x180024af0  mov     [rbp+170h+var_10], rax
0x180024af7  mov     rdi, rdx
0x180024afa  mov     qword ptr [rdx], 0
0x180024b01  mov     rbx, rcx
0x180024b04  call    cs:__imp_GetCurrentProcessId
0x180024b0a  mov     [rsp+270h+var_248], rbx
0x180024b0f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180024b16  mov     r9d, eax
0x180024b19  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180024b21  mov     edx, 104h; unsigned __int64
0x180024b26  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024b2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024b30  mov     r9d, 1F0001h; dwDesiredAccess
0x180024b36  mov     [rsp+270h+var_240], 0
0x180024b3f  xor     r8d, r8d; dwFlags
0x180024b42  lea     rdx, [rsp+270h+Name]; lpName
0x180024b47  xor     ecx, ecx; lpMutexAttributes
0x180024b49  call    cs:__imp_CreateMutexExW
0x180024b4f  mov     rdx, rax
0x180024b52  lea     rcx, [rsp+270h+var_240]
0x180024b57  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180024b5c  cmp     [rsp+270h+var_240], 0
0x180024b62  jnz     short loc_180024B70
0x180024b64  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024b69  mov     ebx, eax
0x180024b6b  jmp     loc_180024C0C
0x180024b70  lea     rdx, [rsp+270h+var_238]
0x180024b75  lea     rcx, [rsp+270h+var_240]
0x180024b7a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180024b7f  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180024b84  mov     [rsp+270h+var_230], 0
0x180024b8d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024b92  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180024b97  mov     ebx, eax
0x180024b99  test    eax, eax
0x180024b9b  jns     short loc_180024BE5
0x180024b9d  mov     rcx, [rbp+178h]; this
0x180024ba4  mov     r9d, eax; char *
0x180024ba7  mov     edx, 66h ; 'f'; void *
0x180024bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bb1  mov     rcx, [rbp+178h]; this
0x180024bb8  mov     r9d, ebx; char *
0x180024bbb  mov     edx, 6Fh ; 'o'; void *
0x180024bc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bc5  mov     r9d, ebx; char *
0x180024bc8  mov     edx, 12Eh; void *
0x180024bcd  mov     rcx, [rbp+178h]; this
0x180024bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bd9  lea     rcx, [rsp+270h+var_238]
0x180024bde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024be3  jmp     short loc_180024C0C
0x180024be5  mov     rax, [rsp+270h+var_230]
0x180024bea  lea     rcx, ds:0[rax*4]
0x180024bf2  test    rcx, rcx
0x180024bf5  jz      short loc_180024C3C
0x180024bf7  mov     [rdi], rcx
0x180024bfa  mov     eax, [rcx]
0x180024bfc  inc     eax
0x180024bfe  mov     [rcx], eax
0x180024c00  lea     rcx, [rsp+270h+var_238]
0x180024c05  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024c0a  xor     ebx, ebx
0x180024c0c  lea     rcx, [rsp+270h+var_240]
0x180024c11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024c16  mov     eax, ebx
0x180024c18  mov     rcx, [rbp+170h+var_10]
0x180024c1f  xor     rcx, rsp; StackCookie
0x180024c22  call    __security_check_cookie
0x180024c27  lea     r11, [rsp+270h+var_s0]
0x180024c2f  mov     rbx, [r11+20h]
0x180024c33  mov     rdi, [r11+28h]
0x180024c37  mov     rsp, r11
0x180024c3a  pop     rbp
0x180024c3b  retn
0x180024c3c  mov     r8, rdi
0x180024c3f  lea     rdx, [rsp+270h+var_240]
0x180024c44  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024c49  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180024c4e  mov     ebx, eax
0x180024c50  test    eax, eax
0x180024c52  jns     short loc_180024C00
0x180024c54  mov     r9d, eax
0x180024c57  mov     edx, 137h
0x180024c5c  jmp     loc_180024BCD
```
