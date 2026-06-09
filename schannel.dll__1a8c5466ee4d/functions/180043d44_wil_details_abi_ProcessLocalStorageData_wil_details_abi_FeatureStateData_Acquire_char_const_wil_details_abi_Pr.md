# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180043d44`
- end: `0x180043e94`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800624ec`

## callees

- `0x180043d44`
- `0x180043e9c`
- `0x18004ea94`
- `0x180055388`
- `0x1800553a4`
- `0x180055440`
- `0x1800597b0`
- `0x180061930`
- `0x180062cc0`
- `0x18006388c`
- `0x180067904`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043d7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043d7c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180043dc1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180043dc1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  int Pointer; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  void *v13; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-C0h] BYREF
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
  if ( !v12 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v12,
    v14);
  v13 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    v10 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v8, (const char *)(unsigned int)Pointer, 304);
    goto LABEL_8;
  }
  v11 = v13;
  if ( v13 )
  {
    *a2 = v13;
    ++*v11;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v9 = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 311;
      goto LABEL_11;
    }
  }
  v9 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return v9;
}

```

## disassembly

```asm
0x180043d44  mov     [rsp-8+arg_10], rbx
0x180043d49  mov     [rsp-8+arg_18], rdi
0x180043d4e  push    rbp
0x180043d4f  lea     rbp, [rsp-170h]
0x180043d57  sub     rsp, 270h
0x180043d5e  mov     rax, cs:__security_cookie
0x180043d65  xor     rax, rsp
0x180043d68  mov     [rbp+170h+var_10], rax
0x180043d6f  mov     rdi, rdx
0x180043d72  mov     qword ptr [rdx], 0
0x180043d79  mov     rbx, rcx
0x180043d7c  call    cs:__imp_GetCurrentProcessId
0x180043d82  mov     [rsp+270h+var_248], rbx
0x180043d87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180043d8e  mov     r9d, eax
0x180043d91  mov     [rsp+270h+var_250], 130h; int
0x180043d99  mov     edx, 104h; unsigned __int64
0x180043d9e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180043da3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043da8  mov     r9d, 1F0001h; dwDesiredAccess
0x180043dae  mov     [rsp+270h+var_240], 0
0x180043db7  xor     r8d, r8d; dwFlags
0x180043dba  lea     rdx, [rsp+270h+Name]; lpName
0x180043dbf  xor     ecx, ecx; lpMutexAttributes
0x180043dc1  call    cs:__imp_CreateMutexExW
0x180043dc7  mov     rdx, rax
0x180043dca  lea     rcx, [rsp+270h+var_240]
0x180043dcf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180043dd4  cmp     [rsp+270h+var_240], 0
0x180043dda  jnz     short loc_180043DE3
0x180043ddc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043de1  jmp     short loc_180043E42
0x180043de3  lea     rdx, [rsp+270h+var_230]
0x180043de8  lea     rcx, [rsp+270h+var_240]
0x180043ded  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180043df2  lea     rdx, [rsp+270h+var_238]; void **
0x180043df7  mov     [rsp+270h+var_238], 0
0x180043e00  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180043e05  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180043e0a  mov     ebx, eax
0x180043e0c  test    eax, eax
0x180043e0e  jns     short loc_180043E17
0x180043e10  mov     edx, 12Eh
0x180043e15  jmp     short loc_180043E83
0x180043e17  mov     rcx, [rsp+270h+var_238]
0x180043e1c  test    rcx, rcx
0x180043e1f  jz      short loc_180043E66
0x180043e21  mov     [rdi], rcx
0x180043e24  mov     eax, [rcx]
0x180043e26  inc     eax
0x180043e28  mov     [rcx], eax
0x180043e2a  xor     ebx, ebx
0x180043e2c  lea     rcx, [rsp+270h+var_230]
0x180043e31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043e36  lea     rcx, [rsp+270h+var_240]
0x180043e3b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043e40  mov     eax, ebx
0x180043e42  mov     rcx, [rbp+170h+var_10]
0x180043e49  xor     rcx, rsp; StackCookie
0x180043e4c  call    __security_check_cookie
0x180043e51  lea     r11, [rsp+270h+var_s0]
0x180043e59  mov     rbx, [r11+20h]
0x180043e5d  mov     rdi, [r11+28h]
0x180043e61  mov     rsp, r11
0x180043e64  pop     rbp
0x180043e65  retn
0x180043e66  mov     r8, rdi
0x180043e69  lea     rdx, [rsp+270h+var_240]
0x180043e6e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180043e73  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180043e78  mov     ebx, eax
0x180043e7a  test    eax, eax
0x180043e7c  jns     short loc_180043E2A
0x180043e7e  mov     edx, 137h; void *
0x180043e83  mov     rcx, [rbp+178h]; this
0x180043e8a  mov     r9d, eax; char *
0x180043e8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043e92  jmp     short loc_180043E2C
```
