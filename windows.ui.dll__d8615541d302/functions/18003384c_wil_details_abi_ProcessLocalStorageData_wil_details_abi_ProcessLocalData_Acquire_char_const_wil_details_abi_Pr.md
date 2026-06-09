# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003384c`
- end: `0x180033a4a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180049a50`

## callees

- `0x180014754`
- `0x18003384c`
- `0x180033a50`
- `0x180033f08`
- `0x180033f6c`
- `0x1800343d8`
- `0x180049048`
- `0x180053d6c`
- `0x1800585f4`
- `0x180066d14`
- `0x180069978`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800338c3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800338c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800338eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800338eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033887`

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
  unsigned int LastErrorFailHr; // ebx
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
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return LastErrorFailHr;
  }
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
  v23[0] = v12;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
    LastErrorFailHr = v15;
    goto LABEL_14;
  }
  v16 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v16;
    ++*v16;
  }
  else
  {
    v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v17,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v12 )
    wil::details::ReleaseMutex(v12, v14);
  if ( v6 )
    wil::details::CloseHandle(v6, v14);
  return 0;
}

```

## disassembly

```asm
0x18003384c  mov     [rsp-8+arg_10], rbx
0x180033851  mov     [rsp-8+arg_18], rsi
0x180033856  push    rbp
0x180033857  push    rdi
0x180033858  push    r14
0x18003385a  lea     rbp, [rsp-170h]
0x180033862  sub     rsp, 270h
0x180033869  mov     rax, cs:__security_cookie
0x180033870  xor     rax, rsp
0x180033873  mov     [rbp+180h+var_20], rax
0x18003387a  mov     r14, rdx
0x18003387d  mov     qword ptr [rdx], 0
0x180033884  mov     rbx, rcx
0x180033887  call    cs:__imp_GetCurrentProcessId
0x18003388d  mov     [rsp+280h+var_258], rbx
0x180033892  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180033899  mov     r9d, eax
0x18003389c  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1800338a4  mov     edx, 104h; unsigned __int64
0x1800338a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800338ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800338b3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800338b9  lea     rdx, [rsp+280h+Name]; lpName
0x1800338be  xor     r8d, r8d; dwFlags
0x1800338c1  xor     ecx, ecx; lpMutexAttributes
0x1800338c3  call    cs:__imp_CreateMutexExW
0x1800338c9  mov     [rsp+280h+var_250], rax
0x1800338ce  mov     rbx, rax
0x1800338d1  test    rax, rax
0x1800338d4  jnz     short loc_1800338E2
0x1800338d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800338db  mov     ebx, eax
0x1800338dd  jmp     loc_1800339F4
0x1800338e2  xor     r8d, r8d; bAlertable
0x1800338e5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800338e8  mov     rcx, rbx; hHandle
0x1800338eb  call    cs:__imp_WaitForSingleObjectEx
0x1800338f1  cmp     eax, 102h
0x1800338f6  jz      short loc_180033916
0x1800338f8  test    eax, 0FFFFFF7Fh
0x1800338fd  jz      short loc_180033911
0x1800338ff  mov     rcx, [rbp+188h]; this
0x180033906  mov     edx, 0E01h; void *
0x18003390b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180033911  mov     rdi, rbx
0x180033914  jmp     short loc_180033918
0x180033916  xor     edi, edi
0x180033918  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18003391d  mov     [rsp+280h+var_240], rdi
0x180033922  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180033927  mov     [rsp+280h+var_248], 0
0x180033930  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180033935  mov     esi, eax
0x180033937  test    eax, eax
0x180033939  jns     short loc_18003399A
0x18003393b  mov     rcx, [rbp+188h]; this
0x180033942  lea     r8, aWil; "wil"
0x180033949  mov     r9d, eax; char *
0x18003394c  mov     edx, 66h ; 'f'; void *
0x180033951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033956  mov     rcx, [rbp+188h]; this
0x18003395d  lea     r8, aWil; "wil"
0x180033964  mov     r9d, esi; char *
0x180033967  mov     edx, 6Fh ; 'o'; void *
0x18003396c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033971  mov     rcx, [rbp+188h]; this
0x180033978  lea     r8, aWil; "wil"
0x18003397f  mov     r9d, esi; char *
0x180033982  mov     edx, 12Eh; void *
0x180033987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003398c  lea     rcx, [rsp+280h+var_240]
0x180033991  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033996  mov     ebx, esi
0x180033998  jmp     short loc_1800339F4
0x18003399a  mov     rax, [rsp+280h+var_248]
0x18003399f  lea     rcx, ds:0[rax*4]
0x1800339a7  test    rcx, rcx
0x1800339aa  jz      short loc_1800339B7
0x1800339ac  mov     [r14], rcx
0x1800339af  mov     eax, [rcx]
0x1800339b1  inc     eax
0x1800339b3  mov     [rcx], eax
0x1800339b5  jmp     short loc_180033A07
0x1800339b7  mov     r8, r14
0x1800339ba  lea     rdx, [rsp+280h+var_250]
0x1800339bf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800339c4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800339c9  mov     ebx, eax
0x1800339cb  test    eax, eax
0x1800339cd  jns     short loc_180033A02
0x1800339cf  mov     rcx, [rbp+188h]; this
0x1800339d6  lea     r8, aWil; "wil"
0x1800339dd  mov     r9d, eax; char *
0x1800339e0  mov     edx, 137h; void *
0x1800339e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339ea  lea     rcx, [rsp+280h+var_240]
0x1800339ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800339f4  lea     rcx, [rsp+280h+var_250]
0x1800339f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800339fe  mov     eax, ebx
0x180033a00  jmp     short loc_180033A23
0x180033a02  mov     rbx, [rsp+280h+var_250]
0x180033a07  test    rdi, rdi
0x180033a0a  jz      short loc_180033A14
0x180033a0c  mov     rcx, rdi; this
0x180033a0f  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180033a14  test    rbx, rbx
0x180033a17  jz      short loc_180033A21
0x180033a19  mov     rcx, rbx; this
0x180033a1c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180033a21  xor     eax, eax
0x180033a23  mov     rcx, [rbp+180h+var_20]
0x180033a2a  xor     rcx, rsp; StackCookie
0x180033a2d  call    __security_check_cookie
0x180033a32  lea     r11, [rsp+280h+var_10]
0x180033a3a  mov     rbx, [r11+30h]
0x180033a3e  mov     rsi, [r11+38h]
0x180033a42  mov     rsp, r11
0x180033a45  pop     r14
0x180033a47  pop     rdi
0x180033a48  pop     rbp
0x180033a49  retn
```
