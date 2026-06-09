# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800309f4`
- end: `0x180030b53`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003174c`

## callees

- `0x180027e20`
- `0x1800305ec`
- `0x180030608`
- `0x1800309f4`
- `0x180031518`
- `0x1800322a0`
- `0x180033244`
- `0x18003399c`
- `0x180034074`
- `0x1800341bc`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180030a71`
- `KERNEL32!CreateMutexExW` at `0x180030a71`
- `KERNEL32!GetCurrentProcessId` at `0x180030a2c`
- `KERNEL32!GetCurrentProcessId` at `0x180030a2c`

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
0x1800309f4  mov     [rsp-8+arg_10], rbx
0x1800309f9  mov     [rsp-8+arg_18], rdi
0x1800309fe  push    rbp
0x1800309ff  lea     rbp, [rsp-170h]
0x180030a07  sub     rsp, 270h
0x180030a0e  mov     rax, cs:__security_cookie
0x180030a15  xor     rax, rsp
0x180030a18  mov     [rbp+170h+var_10], rax
0x180030a1f  mov     rdi, rdx
0x180030a22  mov     qword ptr [rdx], 0
0x180030a29  mov     rbx, rcx
0x180030a2c  call    cs:__imp_GetCurrentProcessId
0x180030a32  mov     [rsp+270h+var_248], rbx
0x180030a37  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180030a3e  mov     r9d, eax
0x180030a41  mov     [rsp+270h+var_250], 130h; int
0x180030a49  mov     edx, 104h; unsigned __int64
0x180030a4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030a53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030a58  mov     r9d, 1F0001h; dwDesiredAccess
0x180030a5e  mov     [rsp+270h+var_240], 0
0x180030a67  xor     r8d, r8d; dwFlags
0x180030a6a  lea     rdx, [rsp+270h+Name]; lpName
0x180030a6f  xor     ecx, ecx; lpMutexAttributes
0x180030a71  call    cs:__imp_CreateMutexExW
0x180030a77  mov     rdx, rax
0x180030a7a  lea     rcx, [rsp+270h+var_240]
0x180030a7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180030a84  cmp     [rsp+270h+var_240], 0
0x180030a8a  jnz     short loc_180030A95
0x180030a8c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030a91  mov     ebx, eax
0x180030a93  jmp     short loc_180030B01
0x180030a95  lea     rdx, [rsp+270h+var_238]
0x180030a9a  lea     rcx, [rsp+270h+var_240]
0x180030a9f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180030aa4  lea     rdx, [rsp+270h+var_230]; void **
0x180030aa9  mov     [rsp+270h+var_230], 0
0x180030ab2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030ab7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180030abc  mov     ebx, eax
0x180030abe  test    eax, eax
0x180030ac0  jns     short loc_180030AE2
0x180030ac2  mov     edx, 12Eh; void *
0x180030ac7  mov     rcx, [rbp+178h]; this
0x180030ace  mov     r9d, eax; char *
0x180030ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030ad6  lea     rcx, [rsp+270h+var_238]
0x180030adb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030ae0  jmp     short loc_180030B01
0x180030ae2  mov     rcx, [rsp+270h+var_230]
0x180030ae7  test    rcx, rcx
0x180030aea  jz      short loc_180030B31
0x180030aec  mov     [rdi], rcx
0x180030aef  mov     eax, [rcx]
0x180030af1  inc     eax
0x180030af3  mov     [rcx], eax
0x180030af5  lea     rcx, [rsp+270h+var_238]
0x180030afa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030aff  xor     ebx, ebx
0x180030b01  lea     rcx, [rsp+270h+var_240]
0x180030b06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030b0b  mov     eax, ebx
0x180030b0d  mov     rcx, [rbp+170h+var_10]
0x180030b14  xor     rcx, rsp; StackCookie
0x180030b17  call    __security_check_cookie
0x180030b1c  lea     r11, [rsp+270h+var_s0]
0x180030b24  mov     rbx, [r11+20h]
0x180030b28  mov     rdi, [r11+28h]
0x180030b2c  mov     rsp, r11
0x180030b2f  pop     rbp
0x180030b30  retn
0x180030b31  mov     r8, rdi
0x180030b34  lea     rdx, [rsp+270h+var_240]
0x180030b39  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180030b3e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180030b43  mov     ebx, eax
0x180030b45  test    eax, eax
0x180030b47  jns     short loc_180030AF5
0x180030b49  mov     edx, 137h
0x180030b4e  jmp     loc_180030AC7
```
