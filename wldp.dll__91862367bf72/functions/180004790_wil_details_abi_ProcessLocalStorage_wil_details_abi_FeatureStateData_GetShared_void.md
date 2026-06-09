# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)

- ea: `0x180004790`
- end: `0x1800049ca`
- name: `?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ`
- size: `570`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001c330`
- `0x1800207b4`

## callees

- `0x180003514`
- `0x180003664`
- `0x180003690`
- `0x180004790`
- `0x1800049d0`
- `0x180004a60`
- `0x180004ad0`
- `0x180004df4`
- `0x180006d00`
- `0x18001f038`
- `0x18001faa0`
- `0x180021ec0`
- `0x180025af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004815`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000498f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000498f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(__int64 a1)
{
  _DWORD *v2; // rsi
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  __int64 v5; // rdx
  __int64 result; // rax
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  void *v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  wil::details *Mutex; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwErrCode[2]; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v19; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v20; // [rsp+48h] [rbp-B8h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( *(_QWORD *)(a1 + 8) )
    goto LABEL_4;
  v2 = 0;
  v20 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v4) < 0 )
      goto LABEL_4;
    goto LABEL_16;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    &v19);
  *(_QWORD *)dwErrCode = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, (unsigned __int64 *)dwErrCode, v8);
  v11 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v11, v16);
    v12 = v11;
    v13 = 302;
LABEL_9:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v13, (unsigned int)"wil", (const char *)v12, v15);
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v19);
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&Mutex);
    goto LABEL_4;
  }
  v2 = (_DWORD *)(4LL * *(_QWORD *)dwErrCode);
  if ( 4LL * *(_QWORD *)dwErrCode )
  {
    ++*v2;
  }
  else
  {
    v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    if ( v14 < 0 )
    {
      v12 = (unsigned int)v14;
      v13 = 311;
      goto LABEL_9;
    }
    v2 = v20;
  }
  if ( v19 )
    wil::details::ReleaseMutex(v19, v10);
  if ( Mutex )
    wil::details::CloseHandle(Mutex, v10);
LABEL_16:
  if ( !*(_QWORD *)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = v2;
LABEL_4:
  v5 = *(_QWORD *)(a1 + 8);
  result = v5 + 32;
  if ( !v5 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180004790  push    rbp
0x180004792  push    rbx
0x180004793  push    rsi
0x180004794  push    rdi
0x180004795  push    r14
0x180004797  push    r15
0x180004799  lea     rbp, [rsp-188h]
0x1800047a1  sub     rsp, 288h
0x1800047a8  mov     rax, cs:__security_cookie
0x1800047af  xor     rax, rsp
0x1800047b2  mov     [rbp+1B0h+var_40], rax
0x1800047b9  mov     rbx, rcx
0x1800047bc  xor     r15d, r15d
0x1800047bf  cmp     [rcx+8], r15
0x1800047c3  jnz     loc_180004853
0x1800047c9  mov     rdi, [rcx]
0x1800047cc  mov     esi, r15d
0x1800047cf  mov     [rsp+2B0h+var_268], r15
0x1800047d4  call    cs:__imp_GetCurrentProcessId
0x1800047da  mov     r9d, eax
0x1800047dd  mov     [rsp+2B0h+var_288], rdi
0x1800047e2  mov     [rsp+2B0h+var_290], 130h; int
0x1800047ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800047f1  mov     edx, 104h; unsigned __int64
0x1800047f6  lea     rcx, [rsp+2B0h+Name]; unsigned __int16 *
0x1800047fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004800  mov     [rsp+2B0h+var_280], r15
0x180004805  mov     r9d, 1F0001h; dwDesiredAccess
0x18000480b  xor     r8d, r8d; dwFlags
0x18000480e  lea     rdx, [rsp+2B0h+Name]; lpName
0x180004813  xor     ecx, ecx; lpMutexAttributes
0x180004815  call    cs:__imp_CreateMutexExW
0x18000481b  mov     rdi, rax
0x18000481e  mov     r14, [rsp+2B0h+var_280]
0x180004823  test    r14, r14
0x180004826  jnz     loc_18000496C
0x18000482c  mov     [rsp+2B0h+var_280], rdi
0x180004831  test    rdi, rdi
0x180004834  jnz     short loc_180004881
0x180004836  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000483b  mov     edi, eax
0x18000483d  mov     rcx, [rsp+2B0h+var_280]; this
0x180004842  test    rcx, rcx
0x180004845  jnz     loc_180004962
0x18000484b  test    edi, edi
0x18000484d  jns     loc_18000494E
0x180004853  mov     rdx, [rbx+8]
0x180004857  lea     rax, [rdx+20h]
0x18000485b  test    rdx, rdx
0x18000485e  cmovz   rax, r15
0x180004862  mov     rcx, [rbp+1B0h+var_40]
0x180004869  xor     rcx, rsp; StackCookie
0x18000486c  call    __security_check_cookie
0x180004871  add     rsp, 288h
0x180004878  pop     r15
0x18000487a  pop     r14
0x18000487c  pop     rdi
0x18000487d  pop     rsi
0x18000487e  pop     rbx
0x18000487f  pop     rbp
0x180004880  retn
0x180004881  lea     rdx, [rsp+2B0h+var_270]
0x180004886  lea     rcx, [rsp+2B0h+var_280]
0x18000488b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004890  nop
0x180004891  mov     qword ptr [rsp+2B0h+dwErrCode], r15
0x180004896  lea     r8, [rsp+2B0h+dwErrCode]; unsigned __int64 *
0x18000489b  lea     rcx, [rsp+2B0h+Name]; unsigned __int16 *
0x1800048a0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800048a5  mov     edi, eax
0x1800048a7  test    eax, eax
0x1800048a9  jns     short loc_180004917
0x1800048ab  mov     rcx, [rbp+1B8h]; this
0x1800048b2  mov     r9d, eax; char *
0x1800048b5  lea     r8, aWil; "wil"
0x1800048bc  mov     edx, 66h ; 'f'; void *
0x1800048c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048c6  mov     rcx, [rbp+1B8h]; this
0x1800048cd  mov     r9d, edi; char *
0x1800048d0  lea     r8, aWil; "wil"
0x1800048d7  mov     edx, 6Fh ; 'o'; void *
0x1800048dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048e1  mov     r9d, edi; char *
0x1800048e4  mov     edx, 12Eh; void *
0x1800048e9  lea     r8, aWil; "wil"
0x1800048f0  mov     rcx, [rbp+1B8h]; this
0x1800048f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048fc  nop
0x1800048fd  lea     rcx, [rsp+2B0h+var_270]
0x180004902  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180004907  nop
0x180004908  lea     rcx, [rsp+2B0h+var_280]
0x18000490d  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180004912  jmp     loc_180004853
0x180004917  mov     rax, qword ptr [rsp+2B0h+dwErrCode]
0x18000491c  lea     rsi, ds:0[rax*4]
0x180004924  test    rsi, rsi
0x180004927  jz      short loc_18000499A
0x180004929  mov     eax, [rsi]
0x18000492b  inc     eax
0x18000492d  mov     [rsi], eax
0x18000492f  mov     rcx, [rsp+2B0h+var_270]; this
0x180004934  test    rcx, rcx
0x180004937  jz      short loc_18000493F
0x180004939  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000493e  nop
0x18000493f  mov     rcx, [rsp+2B0h+var_280]; this
0x180004944  test    rcx, rcx
0x180004947  jz      short loc_18000494E
0x180004949  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000494e  cmp     qword ptr [rbx+8], 0
0x180004953  jnz     loc_180004853
0x180004959  mov     [rbx+8], rsi
0x18000495d  jmp     loc_180004853
0x180004962  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004967  jmp     loc_18000484B
0x18000496c  lea     rcx, [rsp+2B0h+dwErrCode]; this
0x180004971  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004976  nop
0x180004977  mov     rcx, r14; this
0x18000497a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000497f  nop
0x180004980  cmp     byte ptr [rsp+2B0h+dwErrCode], 0
0x180004985  jnz     loc_18000482C
0x18000498b  mov     ecx, [rsp+2B0h+dwErrCode+4]; dwErrCode
0x18000498f  call    cs:__imp_SetLastError
0x180004995  jmp     loc_18000482C
0x18000499a  lea     r8, [rsp+2B0h+var_268]
0x18000499f  lea     rdx, [rsp+2B0h+var_280]
0x1800049a4  lea     rcx, [rsp+2B0h+Name]; unsigned __int16 *
0x1800049a9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800049ae  test    eax, eax
0x1800049b0  jns     short loc_1800049BF
0x1800049b2  mov     r9d, eax
0x1800049b5  mov     edx, 137h
0x1800049ba  jmp     loc_1800048E9
0x1800049bf  mov     rsi, [rsp+2B0h+var_268]
0x1800049c4  jmp     loc_18000492F
```
