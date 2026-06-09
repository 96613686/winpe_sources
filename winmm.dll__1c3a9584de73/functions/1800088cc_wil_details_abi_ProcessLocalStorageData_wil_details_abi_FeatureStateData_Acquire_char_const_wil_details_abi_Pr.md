# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800088cc`
- end: `0x180008a95`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008874`

## callees

- `0x1800088cc`
- `0x180008a9c`
- `0x180008af0`
- `0x18000a3b0`
- `0x18000a9a8`
- `0x18000a9c4`
- `0x18000a9f8`
- `0x18000b1cc`
- `0x18000b5d0`
- `0x18000c990`
- `0x1800183b4`
- `0x180018908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000893e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000893e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008901`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008901`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  wil::details *Mutex; // rbx
  bool v6; // dl
  bool *v7; // r9
  int ValueInternal; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  unsigned int v11; // edi
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  void *v14; // rdx
  unsigned int LastErrorFailHr; // ebx
  _DWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // r8d
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
    goto LABEL_7;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v22,
    &v23);
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v6, &v24, v7);
  v11 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v12, (const char *)v11, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v13, (const char *)v11, v21);
    if ( v23 )
      wil::details::ReleaseMutex(v23, v14);
    wil::details::CloseHandle(Mutex, v14);
    return v11;
  }
  v17 = (_DWORD *)(4 * v24);
  if ( !(4 * v24) )
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v18;
    if ( v18 >= 0 )
    {
      Mutex = v22;
      goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v19, (const char *)(unsigned int)v18, 304);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
LABEL_7:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return LastErrorFailHr;
  }
  *a2 = v17;
  ++*v17;
LABEL_10:
  if ( v23 )
    wil::details::ReleaseMutex(v23, v9);
  if ( Mutex )
    wil::details::CloseHandle(Mutex, v9);
  return 0;
}

```

## disassembly

```asm
0x1800088cc  mov     [rsp-8+arg_10], rbx
0x1800088d1  push    rbp
0x1800088d2  push    rsi
0x1800088d3  push    rdi
0x1800088d4  lea     rbp, [rsp-170h]
0x1800088dc  sub     rsp, 270h
0x1800088e3  mov     rax, cs:__security_cookie
0x1800088ea  xor     rax, rsp
0x1800088ed  mov     [rbp+180h+var_20], rax
0x1800088f4  mov     rsi, rdx
0x1800088f7  mov     rbx, rcx
0x1800088fa  mov     qword ptr [rdx], 0
0x180008901  call    cs:__imp_GetCurrentProcessId
0x180008907  mov     r9d, eax
0x18000890a  mov     [rsp+280h+var_258], rbx
0x18000890f  mov     [rsp+280h+var_260], 130h; int
0x180008917  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000891e  mov     edx, 104h; unsigned __int64
0x180008923  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008928  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000892d  nop
0x18000892e  mov     r9d, 1F0001h; dwDesiredAccess
0x180008934  xor     r8d, r8d; dwFlags
0x180008937  lea     rdx, [rsp+280h+Name]; lpName
0x18000893c  xor     ecx, ecx; lpMutexAttributes
0x18000893e  call    cs:__imp_CreateMutexExW
0x180008944  mov     rbx, rax
0x180008947  mov     [rsp+280h+var_250], rax
0x18000894c  test    rax, rax
0x18000894f  jz      loc_1800089D6
0x180008955  lea     rdx, [rsp+280h+var_248]
0x18000895a  lea     rcx, [rsp+280h+var_250]
0x18000895f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008964  nop
0x180008965  mov     [rsp+280h+var_240], 0
0x18000896e  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x180008973  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008978  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000897d  mov     edi, eax
0x18000897f  test    eax, eax
0x180008981  jns     short loc_1800089EB
0x180008983  mov     rcx, [rbp+188h]; this
0x18000898a  mov     r9d, eax; char *
0x18000898d  mov     edx, 66h ; 'f'; void *
0x180008992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008997  mov     rcx, [rbp+188h]; this
0x18000899e  mov     r9d, edi; char *
0x1800089a1  mov     edx, 6Fh ; 'o'; void *
0x1800089a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089ab  mov     rcx, [rbp+188h]; this
0x1800089b2  mov     r9d, edi; char *
0x1800089b5  mov     edx, 12Eh; void *
0x1800089ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089bf  nop
0x1800089c0  mov     rcx, [rsp+280h+var_248]; this
0x1800089c5  test    rcx, rcx
0x1800089c8  jnz     short loc_180008A39
0x1800089ca  mov     rcx, rbx; this
0x1800089cd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800089d2  mov     eax, edi
0x1800089d4  jmp     short loc_180008A17
0x1800089d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800089db  mov     ebx, eax
0x1800089dd  lea     rcx, [rsp+280h+var_250]
0x1800089e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800089e7  mov     eax, ebx
0x1800089e9  jmp     short loc_180008A17
0x1800089eb  mov     rax, [rsp+280h+var_240]
0x1800089f0  lea     rcx, ds:0[rax*4]
0x1800089f8  test    rcx, rcx
0x1800089fb  jz      short loc_180008A41
0x1800089fd  mov     [rsi], rcx
0x180008a00  mov     eax, [rcx]
0x180008a02  inc     eax
0x180008a04  mov     [rcx], eax
0x180008a06  mov     rcx, [rsp+280h+var_248]; this
0x180008a0b  test    rcx, rcx
0x180008a0e  jnz     short loc_180008A84
0x180008a10  test    rbx, rbx
0x180008a13  jnz     short loc_180008A8B
0x180008a15  xor     eax, eax
0x180008a17  mov     rcx, [rbp+180h+var_20]
0x180008a1e  xor     rcx, rsp; StackCookie
0x180008a21  call    __security_check_cookie
0x180008a26  mov     rbx, [rsp+280h+arg_10]
0x180008a2e  add     rsp, 270h
0x180008a35  pop     rdi
0x180008a36  pop     rsi
0x180008a37  pop     rbp
0x180008a38  retn
0x180008a39  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180008a3e  nop
0x180008a3f  jmp     short loc_1800089CA
0x180008a41  mov     r8, rsi
0x180008a44  lea     rdx, [rsp+280h+var_250]
0x180008a49  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008a4e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008a53  mov     ebx, eax
0x180008a55  test    eax, eax
0x180008a57  jns     short loc_180008A7D
0x180008a59  mov     rcx, [rbp+188h]; this
0x180008a60  mov     r9d, eax; char *
0x180008a63  mov     edx, 137h; void *
0x180008a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a6d  nop
0x180008a6e  lea     rcx, [rsp+280h+var_248]
0x180008a73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008a78  jmp     loc_1800089DD
0x180008a7d  mov     rbx, [rsp+280h+var_250]
0x180008a82  jmp     short loc_180008A06
0x180008a84  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180008a89  jmp     short loc_180008A10
0x180008a8b  mov     rcx, rbx; this
0x180008a8e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008a93  jmp     short loc_180008A15
```
