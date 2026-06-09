# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b6a8`
- end: `0x18000b8c4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b210`

## callees

- `0x180006ac0`
- `0x18000a80c`
- `0x18000a828`
- `0x18000b6a8`
- `0x18000e580`
- `0x18000f008`
- `0x18000f024`
- `0x18000f784`
- `0x180053bd8`
- `0x18005bb30`
- `0x180066910`
- `0x18006a800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b71f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b71f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b767`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b6e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b6e3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  _DWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v21);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v19);
    wil::details::CloseHandle(v6, v19);
    return v15;
  }
  else
  {
    v16 = (_DWORD *)(4 * v23);
    if ( 4 * v23 )
    {
      *a2 = v16;
      ++*v16;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v17,
          120);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        return v18;
      }
      v6 = v22;
    }
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 )
      wil::details::CloseHandle(v6, v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b6a8  mov     [rsp-8+arg_10], rbx
0x18000b6ad  mov     [rsp-8+arg_18], rsi
0x18000b6b2  push    rbp
0x18000b6b3  push    rdi
0x18000b6b4  push    r14
0x18000b6b6  lea     rbp, [rsp-170h]
0x18000b6be  sub     rsp, 270h
0x18000b6c5  mov     rax, cs:__security_cookie
0x18000b6cc  xor     rax, rsp
0x18000b6cf  mov     [rbp+180h+var_20], rax
0x18000b6d6  mov     r14, rdx
0x18000b6d9  mov     qword ptr [rdx], 0
0x18000b6e0  mov     rbx, rcx
0x18000b6e3  call    cs:__imp_GetCurrentProcessId
0x18000b6e9  mov     [rsp+280h+var_258], rbx
0x18000b6ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b6f5  mov     r9d, eax
0x18000b6f8  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18000b700  mov     edx, 104h; unsigned __int64
0x18000b705  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b70a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b70f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b715  lea     rdx, [rsp+280h+Name]; lpName
0x18000b71a  xor     r8d, r8d; dwFlags
0x18000b71d  xor     ecx, ecx; lpMutexAttributes
0x18000b71f  call    cs:__imp_CreateMutexExW
0x18000b725  mov     [rsp+280h+var_250], rax
0x18000b72a  mov     rbx, rax
0x18000b72d  test    rax, rax
0x18000b730  jnz     short loc_18000B75E
0x18000b732  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b737  mov     rcx, [rbp+180h+var_20]
0x18000b73e  xor     rcx, rsp; StackCookie
0x18000b741  call    __security_check_cookie
0x18000b746  lea     r11, [rsp+280h+var_10]
0x18000b74e  mov     rbx, [r11+30h]
0x18000b752  mov     rsi, [r11+38h]
0x18000b756  mov     rsp, r11
0x18000b759  pop     r14
0x18000b75b  pop     rdi
0x18000b75c  pop     rbp
0x18000b75d  retn
0x18000b75e  xor     r8d, r8d; bAlertable
0x18000b761  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b764  mov     rcx, rbx; hHandle
0x18000b767  call    cs:__imp_WaitForSingleObjectEx
0x18000b76d  cmp     eax, 102h
0x18000b772  jz      loc_18000B875
0x18000b778  test    eax, 0FFFFFF7Fh
0x18000b77d  jnz     loc_18000B87C
0x18000b783  mov     rdi, rbx
0x18000b786  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000b78b  mov     [rsp+280h+var_240], rdi
0x18000b790  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b795  mov     [rsp+280h+var_248], 0
0x18000b79e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b7a3  mov     esi, eax
0x18000b7a5  test    eax, eax
0x18000b7a7  js      short loc_18000B808
0x18000b7a9  mov     rax, [rsp+280h+var_248]
0x18000b7ae  lea     rcx, ds:0[rax*4]
0x18000b7b6  test    rcx, rcx
0x18000b7b9  jnz     short loc_18000B7FD
0x18000b7bb  mov     r8, r14
0x18000b7be  lea     rdx, [rsp+280h+var_250]
0x18000b7c3  lea     rcx, [rsp+280h+Name]
0x18000b7c8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b7cd  mov     ebx, eax
0x18000b7cf  test    eax, eax
0x18000b7d1  js      loc_18000B88E
0x18000b7d7  mov     rbx, [rsp+280h+var_250]
0x18000b7dc  test    rdi, rdi
0x18000b7df  jz      short loc_18000B7E9
0x18000b7e1  mov     rcx, rdi; this
0x18000b7e4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000b7e9  test    rbx, rbx
0x18000b7ec  jz      short loc_18000B7F6
0x18000b7ee  mov     rcx, rbx; this
0x18000b7f1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b7f6  xor     eax, eax
0x18000b7f8  jmp     loc_18000B737
0x18000b7fd  mov     [r14], rcx
0x18000b800  mov     eax, [rcx]
0x18000b802  inc     eax
0x18000b804  mov     [rcx], eax
0x18000b806  jmp     short loc_18000B7DC
0x18000b808  mov     rcx, [rbp+188h]; this
0x18000b80f  lea     r8, aWil; "wil"
0x18000b816  mov     r9d, esi; char *
0x18000b819  mov     edx, 66h ; 'f'; void *
0x18000b81e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b823  mov     rcx, [rbp+188h]; this
0x18000b82a  lea     r8, aWil; "wil"
0x18000b831  mov     r9d, esi; char *
0x18000b834  mov     edx, 6Fh ; 'o'; void *
0x18000b839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b83e  mov     rcx, [rbp+188h]; this
0x18000b845  lea     r8, aWil; "wil"
0x18000b84c  mov     r9d, esi; char *
0x18000b84f  mov     edx, 12Eh; void *
0x18000b854  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b859  test    rdi, rdi
0x18000b85c  jz      short loc_18000B866
0x18000b85e  mov     rcx, rdi; this
0x18000b861  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000b866  mov     rcx, rbx; this
0x18000b869  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b86e  mov     eax, esi
0x18000b870  jmp     loc_18000B737
0x18000b875  xor     edi, edi
0x18000b877  jmp     loc_18000B786
0x18000b87c  mov     rcx, [rbp+188h]; this
0x18000b883  mov     edx, 0E01h; void *
0x18000b888  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000b88e  mov     rcx, [rbp+188h]; this
0x18000b895  lea     r8, aWil; "wil"
0x18000b89c  mov     r9d, ebx; char *
0x18000b89f  mov     edx, 137h; void *
0x18000b8a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8a9  lea     rcx, [rsp+280h+var_240]
0x18000b8ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b8b3  lea     rcx, [rsp+280h+var_250]
0x18000b8b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b8bd  mov     eax, ebx
0x18000b8bf  jmp     loc_18000B737
```
