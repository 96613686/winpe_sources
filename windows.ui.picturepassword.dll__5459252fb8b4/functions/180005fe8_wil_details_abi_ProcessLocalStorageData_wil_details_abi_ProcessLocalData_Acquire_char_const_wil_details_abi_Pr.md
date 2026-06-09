# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005fe8`
- end: `0x18000614e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800079bc`

## callees

- `0x180002610`
- `0x180005cd8`
- `0x180005cf4`
- `0x180005fe8`
- `0x180007528`
- `0x1800083f8`
- `0x18000934c`
- `0x18000a254`
- `0x18000a418`
- `0x18000b654`
- `0x18000b82c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006065`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006020`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180005fe8  mov     [rsp-8+arg_10], rbx
0x180005fed  mov     [rsp-8+arg_18], rdi
0x180005ff2  push    rbp
0x180005ff3  lea     rbp, [rsp-170h]
0x180005ffb  sub     rsp, 270h
0x180006002  mov     rax, cs:__security_cookie
0x180006009  xor     rax, rsp
0x18000600c  mov     [rbp+170h+var_10], rax
0x180006013  mov     rdi, rdx
0x180006016  mov     qword ptr [rdx], 0
0x18000601d  mov     rbx, rcx
0x180006020  call    cs:__imp_GetCurrentProcessId
0x180006026  mov     [rsp+270h+var_248], rbx
0x18000602b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006032  mov     r9d, eax
0x180006035  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000603d  mov     edx, 104h; unsigned __int64
0x180006042  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006047  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000604c  mov     r9d, 1F0001h; dwDesiredAccess
0x180006052  mov     [rsp+270h+var_240], 0
0x18000605b  xor     r8d, r8d; dwFlags
0x18000605e  lea     rdx, [rsp+270h+Name]; lpName
0x180006063  xor     ecx, ecx; lpMutexAttributes
0x180006065  call    cs:__imp_CreateMutexExW
0x18000606b  mov     rdx, rax
0x18000606e  lea     rcx, [rsp+270h+var_240]
0x180006073  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006078  cmp     [rsp+270h+var_240], 0
0x18000607e  jnz     short loc_180006089
0x180006080  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006085  mov     ebx, eax
0x180006087  jmp     short loc_1800060FC
0x180006089  lea     rdx, [rsp+270h+var_238]
0x18000608e  lea     rcx, [rsp+270h+var_240]
0x180006093  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006098  lea     rdx, [rsp+270h+var_230]; void **
0x18000609d  mov     [rsp+270h+var_230], 0
0x1800060a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800060ab  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800060b0  mov     ebx, eax
0x1800060b2  test    eax, eax
0x1800060b4  jns     short loc_1800060DD
0x1800060b6  mov     edx, 12Eh; void *
0x1800060bb  mov     rcx, [rbp+178h]; this
0x1800060c2  lea     r8, aWil; "wil"
0x1800060c9  mov     r9d, eax; char *
0x1800060cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060d1  lea     rcx, [rsp+270h+var_238]
0x1800060d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800060db  jmp     short loc_1800060FC
0x1800060dd  mov     rcx, [rsp+270h+var_230]
0x1800060e2  test    rcx, rcx
0x1800060e5  jz      short loc_18000612C
0x1800060e7  mov     [rdi], rcx
0x1800060ea  mov     eax, [rcx]
0x1800060ec  inc     eax
0x1800060ee  mov     [rcx], eax
0x1800060f0  lea     rcx, [rsp+270h+var_238]
0x1800060f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800060fa  xor     ebx, ebx
0x1800060fc  lea     rcx, [rsp+270h+var_240]
0x180006101  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006106  mov     eax, ebx
0x180006108  mov     rcx, [rbp+170h+var_10]
0x18000610f  xor     rcx, rsp; StackCookie
0x180006112  call    __security_check_cookie
0x180006117  lea     r11, [rsp+270h+var_s0]
0x18000611f  mov     rbx, [r11+20h]
0x180006123  mov     rdi, [r11+28h]
0x180006127  mov     rsp, r11
0x18000612a  pop     rbp
0x18000612b  retn
0x18000612c  mov     r8, rdi
0x18000612f  lea     rdx, [rsp+270h+var_240]
0x180006134  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006139  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000613e  mov     ebx, eax
0x180006140  test    eax, eax
0x180006142  jns     short loc_1800060F0
0x180006144  mov     edx, 137h
0x180006149  jmp     loc_1800060BB
```
