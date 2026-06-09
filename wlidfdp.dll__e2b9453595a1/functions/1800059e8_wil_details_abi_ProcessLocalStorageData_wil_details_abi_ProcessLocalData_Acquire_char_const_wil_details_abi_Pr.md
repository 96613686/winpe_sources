# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800059e8`
- end: `0x180005b92`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006cb4`

## callees

- `0x1800027f0`
- `0x180005734`
- `0x180005750`
- `0x1800059e8`
- `0x180006af8`
- `0x1800077d0`
- `0x180008614`
- `0x180008d00`
- `0x18000912c`
- `0x1800095f0`
- `0x1800096f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005a65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005a65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a20`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800059e8  mov     [rsp-8+arg_10], rbx
0x1800059ed  mov     [rsp-8+arg_18], rdi
0x1800059f2  push    rbp
0x1800059f3  lea     rbp, [rsp-170h]
0x1800059fb  sub     rsp, 270h
0x180005a02  mov     rax, cs:__security_cookie
0x180005a09  xor     rax, rsp
0x180005a0c  mov     [rbp+170h+var_10], rax
0x180005a13  mov     rdi, rdx
0x180005a16  mov     qword ptr [rdx], 0
0x180005a1d  mov     rbx, rcx
0x180005a20  call    cs:__imp_GetCurrentProcessId
0x180005a26  mov     [rsp+270h+var_248], rbx
0x180005a2b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005a32  mov     r9d, eax
0x180005a35  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005a3d  mov     edx, 104h; unsigned __int64
0x180005a42  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005a47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a4c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005a52  mov     [rsp+270h+var_240], 0
0x180005a5b  xor     r8d, r8d; dwFlags
0x180005a5e  lea     rdx, [rsp+270h+Name]; lpName
0x180005a63  xor     ecx, ecx; lpMutexAttributes
0x180005a65  call    cs:__imp_CreateMutexExW
0x180005a6b  mov     rdx, rax
0x180005a6e  lea     rcx, [rsp+270h+var_240]
0x180005a73  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005a78  cmp     [rsp+270h+var_240], 0
0x180005a7e  jnz     short loc_180005A8C
0x180005a80  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005a85  mov     ebx, eax
0x180005a87  jmp     loc_180005B3D
0x180005a8c  lea     rdx, [rsp+270h+var_238]
0x180005a91  lea     rcx, [rsp+270h+var_240]
0x180005a96  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005a9b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180005aa0  mov     [rsp+270h+var_230], 0
0x180005aa9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005aae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005ab3  mov     ebx, eax
0x180005ab5  test    eax, eax
0x180005ab7  jns     short loc_180005B16
0x180005ab9  mov     rcx, [rbp+178h]; this
0x180005ac0  lea     r8, aWil; "wil"
0x180005ac7  mov     r9d, eax; char *
0x180005aca  mov     edx, 66h ; 'f'; void *
0x180005acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ad4  mov     rcx, [rbp+178h]; this
0x180005adb  lea     r8, aWil; "wil"
0x180005ae2  mov     r9d, ebx; char *
0x180005ae5  mov     edx, 6Fh ; 'o'; void *
0x180005aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005aef  mov     r9d, ebx; char *
0x180005af2  mov     edx, 12Eh; void *
0x180005af7  mov     rcx, [rbp+178h]; this
0x180005afe  lea     r8, aWil; "wil"
0x180005b05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b0a  lea     rcx, [rsp+270h+var_238]
0x180005b0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005b14  jmp     short loc_180005B3D
0x180005b16  mov     rax, [rsp+270h+var_230]
0x180005b1b  lea     rcx, ds:0[rax*4]
0x180005b23  test    rcx, rcx
0x180005b26  jz      short loc_180005B6D
0x180005b28  mov     [rdi], rcx
0x180005b2b  mov     eax, [rcx]
0x180005b2d  inc     eax
0x180005b2f  mov     [rcx], eax
0x180005b31  lea     rcx, [rsp+270h+var_238]
0x180005b36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005b3b  xor     ebx, ebx
0x180005b3d  lea     rcx, [rsp+270h+var_240]
0x180005b42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005b47  mov     eax, ebx
0x180005b49  mov     rcx, [rbp+170h+var_10]
0x180005b50  xor     rcx, rsp; StackCookie
0x180005b53  call    __security_check_cookie
0x180005b58  lea     r11, [rsp+270h+var_s0]
0x180005b60  mov     rbx, [r11+20h]
0x180005b64  mov     rdi, [r11+28h]
0x180005b68  mov     rsp, r11
0x180005b6b  pop     rbp
0x180005b6c  retn
0x180005b6d  mov     r8, rdi
0x180005b70  lea     rdx, [rsp+270h+var_240]
0x180005b75  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005b7a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005b7f  mov     ebx, eax
0x180005b81  test    eax, eax
0x180005b83  jns     short loc_180005B31
0x180005b85  mov     r9d, eax
0x180005b88  mov     edx, 137h
0x180005b8d  jmp     loc_180005AF7
```
