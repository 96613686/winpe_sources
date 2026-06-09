# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800143c8`
- end: `0x180014551`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001494c`

## callees

- `0x18000d030`
- `0x180010b08`
- `0x180010b24`
- `0x180011688`
- `0x180012734`
- `0x180012ce0`
- `0x180012eec`
- `0x180013380`
- `0x180013484`
- `0x1800143c8`
- `0x180014d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014445`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014445`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014400`

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
  _DWORD *v8; // rcx
  int v10; // eax
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
    if ( Pointer >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a2 = v13;
        ++*v8;
      }
      else
      {
        v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v10,
            304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800143c8  mov     [rsp-8+arg_10], rbx
0x1800143cd  mov     [rsp-8+arg_18], rdi
0x1800143d2  push    rbp
0x1800143d3  lea     rbp, [rsp-170h]
0x1800143db  sub     rsp, 270h
0x1800143e2  mov     rax, cs:__security_cookie
0x1800143e9  xor     rax, rsp
0x1800143ec  mov     [rbp+170h+var_10], rax
0x1800143f3  mov     rdi, rdx
0x1800143f6  mov     rbx, rcx
0x1800143f9  mov     qword ptr [rdx], 0
0x180014400  call    cs:__imp_GetCurrentProcessId
0x180014406  mov     r9d, eax
0x180014409  mov     [rsp+270h+var_248], rbx
0x18001440e  mov     [rsp+270h+var_250], 130h; int
0x180014416  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001441d  mov     edx, 104h; unsigned __int64
0x180014422  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180014427  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001442c  mov     [rsp+270h+var_240], 0
0x180014435  mov     r9d, 1F0001h; dwDesiredAccess
0x18001443b  xor     r8d, r8d; dwFlags
0x18001443e  lea     rdx, [rsp+270h+Name]; lpName
0x180014443  xor     ecx, ecx; lpMutexAttributes
0x180014445  call    cs:__imp_CreateMutexExW
0x18001444b  mov     rdx, rax
0x18001444e  lea     rcx, [rsp+270h+var_240]
0x180014453  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180014458  cmp     [rsp+270h+var_240], 0
0x18001445e  jnz     short loc_180014469
0x180014460  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014465  mov     ebx, eax
0x180014467  jmp     short loc_1800144E0
0x180014469  lea     rdx, [rsp+270h+var_238]
0x18001446e  lea     rcx, [rsp+270h+var_240]
0x180014473  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180014478  nop
0x180014479  mov     [rsp+270h+var_230], 0
0x180014482  lea     rdx, [rsp+270h+var_230]; void **
0x180014487  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001448c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180014491  mov     ebx, eax
0x180014493  test    eax, eax
0x180014495  jns     short loc_1800144C0
0x180014497  mov     rcx, [rbp+178h]; this
0x18001449e  mov     r9d, eax; char *
0x1800144a1  lea     r8, aWil; "wil"
0x1800144a8  mov     edx, 12Eh; void *
0x1800144ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800144b2  nop
0x1800144b3  lea     rcx, [rsp+270h+var_238]
0x1800144b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800144bd  nop
0x1800144be  jmp     short loc_1800144E0
0x1800144c0  mov     rcx, [rsp+270h+var_230]
0x1800144c5  test    rcx, rcx
0x1800144c8  jz      short loc_180014510
0x1800144ca  mov     [rdi], rcx
0x1800144cd  mov     eax, [rcx]
0x1800144cf  inc     eax
0x1800144d1  mov     [rcx], eax
0x1800144d3  lea     rcx, [rsp+270h+var_238]
0x1800144d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800144dd  nop
0x1800144de  xor     ebx, ebx
0x1800144e0  lea     rcx, [rsp+270h+var_240]
0x1800144e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800144ea  mov     eax, ebx
0x1800144ec  mov     rcx, [rbp+170h+var_10]
0x1800144f3  xor     rcx, rsp; StackCookie
0x1800144f6  call    __security_check_cookie
0x1800144fb  lea     r11, [rsp+270h+var_s0]
0x180014503  mov     rbx, [r11+20h]
0x180014507  mov     rdi, [r11+28h]
0x18001450b  mov     rsp, r11
0x18001450e  pop     rbp
0x18001450f  retn
0x180014510  mov     r8, rdi
0x180014513  lea     rdx, [rsp+270h+var_240]
0x180014518  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001451d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180014522  mov     ebx, eax
0x180014524  test    eax, eax
0x180014526  jns     short loc_1800144D3
0x180014528  mov     rcx, [rbp+178h]; this
0x18001452f  mov     r9d, eax; char *
0x180014532  lea     r8, aWil; "wil"
0x180014539  mov     edx, 137h; void *
0x18001453e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014543  nop
0x180014544  lea     rcx, [rsp+270h+var_238]
0x180014549  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001454e  nop
0x18001454f  jmp     short loc_1800144E0
```
