# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000781c`
- end: `0x1800079d3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800083f4`

## callees

- `0x180001590`
- `0x1800076c4`
- `0x1800076e4`
- `0x18000781c`
- `0x180008140`
- `0x180008bf0`
- `0x180009204`
- `0x180009780`
- `0x180009958`
- `0x180009c88`
- `0x180009d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000789f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000789f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007854`

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
0x18000781c  mov     [rsp-8+arg_10], rbx
0x180007821  mov     [rsp-8+arg_18], rdi
0x180007826  push    rbp
0x180007827  lea     rbp, [rsp-170h]
0x18000782f  sub     rsp, 270h
0x180007836  mov     rax, cs:__security_cookie
0x18000783d  xor     rax, rsp
0x180007840  mov     [rbp+170h+var_10], rax
0x180007847  mov     rdi, rdx
0x18000784a  mov     qword ptr [rdx], 0
0x180007851  mov     rbx, rcx
0x180007854  call    cs:__imp_GetCurrentProcessId
0x18000785b  nop     dword ptr [rax+rax+00h]
0x180007860  mov     [rsp+270h+var_248], rbx
0x180007865  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000786c  mov     r9d, eax
0x18000786f  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180007877  mov     edx, 104h; unsigned __int64
0x18000787c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007881  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007886  mov     r9d, 1F0001h; dwDesiredAccess
0x18000788c  mov     [rsp+270h+var_240], 0
0x180007895  xor     r8d, r8d; dwFlags
0x180007898  lea     rdx, [rsp+270h+Name]; lpName
0x18000789d  xor     ecx, ecx; lpMutexAttributes
0x18000789f  call    cs:__imp_CreateMutexExW
0x1800078a6  nop     dword ptr [rax+rax+00h]
0x1800078ab  mov     rdx, rax
0x1800078ae  lea     rcx, [rsp+270h+var_240]
0x1800078b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800078b8  cmp     [rsp+270h+var_240], 0
0x1800078be  jnz     short loc_1800078CC
0x1800078c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800078c5  mov     ebx, eax
0x1800078c7  jmp     loc_18000797D
0x1800078cc  lea     rdx, [rsp+270h+var_238]
0x1800078d1  lea     rcx, [rsp+270h+var_240]
0x1800078d6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800078db  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800078e0  mov     [rsp+270h+var_230], 0
0x1800078e9  lea     rcx, [rsp+270h+Name]; pszSrc
0x1800078ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800078f3  mov     ebx, eax
0x1800078f5  test    eax, eax
0x1800078f7  jns     short loc_180007956
0x1800078f9  mov     rcx, [rbp+178h]; this
0x180007900  lea     r8, aWil; "wil"
0x180007907  mov     r9d, eax; char *
0x18000790a  mov     edx, 66h ; 'f'; void *
0x18000790f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007914  mov     rcx, [rbp+178h]; this
0x18000791b  lea     r8, aWil; "wil"
0x180007922  mov     r9d, ebx; char *
0x180007925  mov     edx, 6Fh ; 'o'; void *
0x18000792a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000792f  mov     r9d, ebx; char *
0x180007932  mov     edx, 12Eh; void *
0x180007937  mov     rcx, [rbp+178h]; this
0x18000793e  lea     r8, aWil; "wil"
0x180007945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000794a  lea     rcx, [rsp+270h+var_238]
0x18000794f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007954  jmp     short loc_18000797D
0x180007956  mov     rax, [rsp+270h+var_230]
0x18000795b  lea     rcx, ds:0[rax*4]
0x180007963  test    rcx, rcx
0x180007966  jz      short loc_1800079AE
0x180007968  mov     [rdi], rcx
0x18000796b  mov     eax, [rcx]
0x18000796d  inc     eax
0x18000796f  mov     [rcx], eax
0x180007971  lea     rcx, [rsp+270h+var_238]
0x180007976  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000797b  xor     ebx, ebx
0x18000797d  lea     rcx, [rsp+270h+var_240]
0x180007982  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007987  mov     eax, ebx
0x180007989  mov     rcx, [rbp+170h+var_10]
0x180007990  xor     rcx, rsp; StackCookie
0x180007993  call    __security_check_cookie
0x180007998  lea     r11, [rsp+270h+var_s0]
0x1800079a0  mov     rbx, [r11+20h]
0x1800079a4  mov     rdi, [r11+28h]
0x1800079a8  mov     rsp, r11
0x1800079ab  pop     rbp
0x1800079ac  retn
0x1800079ae  mov     r8, rdi
0x1800079b1  lea     rdx, [rsp+270h+var_240]
0x1800079b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800079bb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800079c0  mov     ebx, eax
0x1800079c2  test    eax, eax
0x1800079c4  jns     short loc_180007971
0x1800079c6  mov     r9d, eax
0x1800079c9  mov     edx, 137h
0x1800079ce  jmp     loc_180007937
```
