# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180018aac`
- end: `0x180018cb3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018a50`

## callees

- `0x180018aac`
- `0x180018cbc`
- `0x180018d74`
- `0x180019008`
- `0x18001d2a0`
- `0x18001db54`
- `0x18001db70`
- `0x18001dc90`
- `0x180021060`
- `0x180022fd4`
- `0x180023c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018b49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018b49`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018b23`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018b23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018ae7`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // esi
  void *v15; // rdx
  _DWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rdx
  void *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v23 = Mutex;
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v25[0] = v12;
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v24, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v21);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v22);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
  v16 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v16;
    ++*v16;
LABEL_19:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    if ( v6 )
      wil::details::CloseHandle(v6, v20);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v6 = v23;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 304);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
  if ( v23 )
    wil::details::CloseHandle(v23, v19);
  return v18;
}

```

## disassembly

```asm
0x180018aac  mov     [rsp-8+arg_10], rbx
0x180018ab1  mov     [rsp-8+arg_18], rsi
0x180018ab6  push    rbp
0x180018ab7  push    rdi
0x180018ab8  push    r14
0x180018aba  lea     rbp, [rsp-170h]
0x180018ac2  sub     rsp, 270h
0x180018ac9  mov     rax, cs:__security_cookie
0x180018ad0  xor     rax, rsp
0x180018ad3  mov     [rbp+180h+var_20], rax
0x180018ada  mov     r14, rdx
0x180018add  mov     qword ptr [rdx], 0
0x180018ae4  mov     rbx, rcx
0x180018ae7  call    cs:__imp_GetCurrentProcessId
0x180018aed  mov     [rsp+280h+var_258], rbx
0x180018af2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018af9  mov     r9d, eax
0x180018afc  mov     [rsp+280h+var_260], 130h; int
0x180018b04  mov     edx, 104h; unsigned __int64
0x180018b09  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018b0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018b13  mov     r9d, 1F0001h; dwDesiredAccess
0x180018b19  lea     rdx, [rsp+280h+Name]; lpName
0x180018b1e  xor     r8d, r8d; dwFlags
0x180018b21  xor     ecx, ecx; lpMutexAttributes
0x180018b23  call    cs:__imp_CreateMutexExW
0x180018b29  mov     [rsp+280h+var_250], rax
0x180018b2e  mov     rbx, rax
0x180018b31  test    rax, rax
0x180018b34  jnz     short loc_180018B40
0x180018b36  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018b3b  jmp     loc_180018C8C
0x180018b40  xor     r8d, r8d; bAlertable
0x180018b43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180018b46  mov     rcx, rbx; hHandle
0x180018b49  call    cs:__imp_WaitForSingleObjectEx
0x180018b4f  cmp     eax, 102h
0x180018b54  jz      short loc_180018B6F
0x180018b56  test    eax, 0FFFFFF7Fh
0x180018b5b  jz      short loc_180018B6A
0x180018b5d  mov     rcx, [rbp+188h]; this
0x180018b64  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180018b6a  mov     rdi, rbx
0x180018b6d  jmp     short loc_180018B71
0x180018b6f  xor     edi, edi
0x180018b71  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180018b76  mov     [rsp+280h+var_240], rdi
0x180018b7b  lea     rcx, [rsp+280h+Name]; pszSrc
0x180018b80  mov     [rsp+280h+var_248], 0
0x180018b89  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180018b8e  mov     esi, eax
0x180018b90  test    eax, eax
0x180018b92  jns     short loc_180018C01
0x180018b94  mov     rcx, [rbp+188h]; this
0x180018b9b  lea     r8, aWil; "wil"
0x180018ba2  mov     r9d, eax; char *
0x180018ba5  mov     edx, 66h ; 'f'; void *
0x180018baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018baf  mov     rcx, [rbp+188h]; this
0x180018bb6  lea     r8, aWil; "wil"
0x180018bbd  mov     r9d, esi; char *
0x180018bc0  mov     edx, 6Fh ; 'o'; void *
0x180018bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018bca  mov     rcx, [rbp+188h]; this
0x180018bd1  lea     r8, aWil; "wil"
0x180018bd8  mov     r9d, esi; char *
0x180018bdb  mov     edx, 12Eh; void *
0x180018be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018be5  test    rdi, rdi
0x180018be8  jz      short loc_180018BF2
0x180018bea  mov     rcx, rdi; this
0x180018bed  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180018bf2  mov     rcx, rbx; this
0x180018bf5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018bfa  mov     eax, esi
0x180018bfc  jmp     loc_180018C8C
0x180018c01  mov     rax, [rsp+280h+var_248]
0x180018c06  lea     rcx, ds:0[rax*4]
0x180018c0e  test    rcx, rcx
0x180018c11  jz      short loc_180018C1E
0x180018c13  mov     [r14], rcx
0x180018c16  mov     eax, [rcx]
0x180018c18  inc     eax
0x180018c1a  mov     [rcx], eax
0x180018c1c  jmp     short loc_180018C73
0x180018c1e  mov     r8, r14
0x180018c21  lea     rdx, [rsp+280h+var_250]
0x180018c26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018c2b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018c30  mov     ebx, eax
0x180018c32  test    eax, eax
0x180018c34  jns     short loc_180018C6E
0x180018c36  mov     rcx, [rbp+188h]; this
0x180018c3d  lea     r8, aWil; "wil"
0x180018c44  mov     r9d, eax; char *
0x180018c47  mov     edx, 137h; void *
0x180018c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018c51  lea     rcx, [rsp+280h+var_240]
0x180018c56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018c5b  mov     rcx, [rsp+280h+var_250]; this
0x180018c60  test    rcx, rcx
0x180018c63  jz      short loc_180018C6A
0x180018c65  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018c6a  mov     eax, ebx
0x180018c6c  jmp     short loc_180018C8C
0x180018c6e  mov     rbx, [rsp+280h+var_250]
0x180018c73  lea     rcx, [rsp+280h+var_240]
0x180018c78  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018c7d  test    rbx, rbx
0x180018c80  jz      short loc_180018C8A
0x180018c82  mov     rcx, rbx; this
0x180018c85  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018c8a  xor     eax, eax
0x180018c8c  mov     rcx, [rbp+180h+var_20]
0x180018c93  xor     rcx, rsp; StackCookie
0x180018c96  call    __security_check_cookie
0x180018c9b  lea     r11, [rsp+280h+var_10]
0x180018ca3  mov     rbx, [r11+30h]
0x180018ca7  mov     rsi, [r11+38h]
0x180018cab  mov     rsp, r11
0x180018cae  pop     r14
0x180018cb0  pop     rdi
0x180018cb1  pop     rbp
0x180018cb2  retn
```
