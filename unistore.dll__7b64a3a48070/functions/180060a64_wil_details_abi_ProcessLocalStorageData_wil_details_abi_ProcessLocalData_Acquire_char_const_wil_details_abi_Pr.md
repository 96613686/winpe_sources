# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180060a64`
- end: `0x180060c3c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800609d8`

## callees

- `0x180013524`
- `0x180060a64`
- `0x180060c9c`
- `0x180060f80`
- `0x180067128`
- `0x18006b91c`
- `0x180072f2c`
- `0x1800733f0`
- `0x180073fdc`
- `0x180093410`
- `0x1800936a0`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180060adb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180060adb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180060b01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180060b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060a9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060a9f`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rsi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v24 = v12;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)v16, v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
    return v15;
  }
  v18 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_14;
    }
    v6 = v22;
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
0x180060a64  mov     [rsp-8+arg_10], rbx
0x180060a69  mov     [rsp-8+arg_18], rsi
0x180060a6e  push    rbp
0x180060a6f  push    rdi
0x180060a70  push    r14
0x180060a72  lea     rbp, [rsp-170h]
0x180060a7a  sub     rsp, 270h
0x180060a81  mov     rax, cs:__security_cookie
0x180060a88  xor     rax, rsp
0x180060a8b  mov     [rbp+180h+var_20], rax
0x180060a92  mov     r14, rdx
0x180060a95  mov     qword ptr [rdx], 0
0x180060a9c  mov     rbx, rcx
0x180060a9f  call    cs:__imp_GetCurrentProcessId
0x180060aa5  mov     [rsp+280h+var_258], rbx
0x180060aaa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180060ab1  mov     r9d, eax
0x180060ab4  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180060abc  mov     edx, 104h; unsigned __int64
0x180060ac1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180060ac6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060acb  mov     r9d, 1F0001h; dwDesiredAccess
0x180060ad1  lea     rdx, [rsp+280h+Name]; lpName
0x180060ad6  xor     r8d, r8d; dwFlags
0x180060ad9  xor     ecx, ecx; lpMutexAttributes
0x180060adb  call    cs:__imp_CreateMutexExW
0x180060ae1  mov     [rsp+280h+var_250], rax
0x180060ae6  mov     rbx, rax
0x180060ae9  test    rax, rax
0x180060aec  jnz     short loc_180060AF8
0x180060aee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180060af3  jmp     loc_180060C15
0x180060af8  xor     r8d, r8d; bAlertable
0x180060afb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180060afe  mov     rcx, rbx; hHandle
0x180060b01  call    cs:__imp_WaitForSingleObjectEx
0x180060b07  cmp     eax, 102h
0x180060b0c  jz      short loc_180060B27
0x180060b0e  test    eax, 0FFFFFF7Fh
0x180060b13  jz      short loc_180060B22
0x180060b15  mov     rcx, [rbp+188h]; this
0x180060b1c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180060b22  mov     rsi, rbx
0x180060b25  jmp     short loc_180060B29
0x180060b27  xor     esi, esi
0x180060b29  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180060b2e  mov     [rsp+280h+var_240], rsi
0x180060b33  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180060b38  mov     [rsp+280h+var_248], 0
0x180060b41  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180060b46  mov     edi, eax
0x180060b48  test    eax, eax
0x180060b4a  jns     short loc_180060B8C
0x180060b4c  mov     rcx, [rbp+188h]; this
0x180060b53  lea     r8, aWil; "wil"
0x180060b5a  mov     r9d, eax; char *
0x180060b5d  mov     edx, 66h ; 'f'; void *
0x180060b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060b67  mov     rcx, [rbp+188h]; this
0x180060b6e  lea     r8, aWil; "wil"
0x180060b75  mov     r9d, edi; char *
0x180060b78  mov     edx, 6Fh ; 'o'; void *
0x180060b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060b82  mov     r9d, edi
0x180060b85  mov     edx, 12Eh
0x180060b8a  jmp     short loc_180060BC9
0x180060b8c  mov     rax, [rsp+280h+var_248]
0x180060b91  lea     rcx, ds:0[rax*4]
0x180060b99  test    rcx, rcx
0x180060b9c  jz      short loc_180060BA9
0x180060b9e  mov     [r14], rcx
0x180060ba1  mov     eax, [rcx]
0x180060ba3  inc     eax
0x180060ba5  mov     [rcx], eax
0x180060ba7  jmp     short loc_180060BF9
0x180060ba9  mov     r8, r14
0x180060bac  lea     rdx, [rsp+280h+var_250]
0x180060bb1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180060bb6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180060bbb  mov     edi, eax
0x180060bbd  test    eax, eax
0x180060bbf  jns     short loc_180060BF4
0x180060bc1  mov     r9d, eax; char *
0x180060bc4  mov     edx, 137h; void *
0x180060bc9  mov     rcx, [rbp+188h]; this
0x180060bd0  lea     r8, aWil; "wil"
0x180060bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060bdc  lea     rcx, [rsp+280h+var_240]
0x180060be1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060be6  lea     rcx, [rsp+280h+var_250]
0x180060beb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060bf0  mov     eax, edi
0x180060bf2  jmp     short loc_180060C15
0x180060bf4  mov     rbx, [rsp+280h+var_250]
0x180060bf9  test    rsi, rsi
0x180060bfc  jz      short loc_180060C06
0x180060bfe  mov     rcx, rsi; this
0x180060c01  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180060c06  test    rbx, rbx
0x180060c09  jz      short loc_180060C13
0x180060c0b  mov     rcx, rbx; this
0x180060c0e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180060c13  xor     eax, eax
0x180060c15  mov     rcx, [rbp+180h+var_20]
0x180060c1c  xor     rcx, rsp; StackCookie
0x180060c1f  call    __security_check_cookie
0x180060c24  lea     r11, [rsp+280h+var_10]
0x180060c2c  mov     rbx, [r11+30h]
0x180060c30  mov     rsi, [r11+38h]
0x180060c34  mov     rsp, r11
0x180060c37  pop     r14
0x180060c39  pop     rdi
0x180060c3a  pop     rbp
0x180060c3b  retn
```
