# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002099c`
- end: `0x180020b87`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800208dc`

## callees

- `0x18002099c`
- `0x180020b90`
- `0x18002e2b0`
- `0x18002e8c4`
- `0x18003f738`
- `0x18003fb94`
- `0x180040bfc`
- `0x180040cdc`
- `0x180040cfc`
- `0x18004c680`
- `0x18004d708`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800209d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800209d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020a45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020a45`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020a19`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020a19`

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
0x18002099c  mov     [rsp-8+arg_10], rbx
0x1800209a1  mov     [rsp-8+arg_18], rsi
0x1800209a6  push    rbp
0x1800209a7  push    rdi
0x1800209a8  push    r14
0x1800209aa  lea     rbp, [rsp-170h]
0x1800209b2  sub     rsp, 270h
0x1800209b9  mov     rax, cs:__security_cookie
0x1800209c0  xor     rax, rsp
0x1800209c3  mov     [rbp+180h+var_20], rax
0x1800209ca  mov     r14, rdx
0x1800209cd  mov     qword ptr [rdx], 0
0x1800209d4  mov     rbx, rcx
0x1800209d7  call    cs:__imp_GetCurrentProcessId
0x1800209de  nop     dword ptr [rax+rax+00h]
0x1800209e3  mov     [rsp+280h+var_258], rbx
0x1800209e8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800209ef  mov     r9d, eax
0x1800209f2  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x1800209fa  mov     edx, 104h; unsigned __int64
0x1800209ff  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180020a04  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180020a09  mov     r9d, 1F0001h; dwDesiredAccess
0x180020a0f  lea     rdx, [rsp+280h+Name]; lpName
0x180020a14  xor     r8d, r8d; dwFlags
0x180020a17  xor     ecx, ecx; lpMutexAttributes
0x180020a19  call    cs:__imp_CreateMutexExW
0x180020a20  nop     dword ptr [rax+rax+00h]
0x180020a25  mov     [rsp+280h+var_250], rax
0x180020a2a  mov     rbx, rax
0x180020a2d  test    rax, rax
0x180020a30  jnz     short loc_180020A3C
0x180020a32  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020a37  jmp     loc_180020B5F
0x180020a3c  xor     r8d, r8d; bAlertable
0x180020a3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020a42  mov     rcx, rbx; hHandle
0x180020a45  call    cs:__imp_WaitForSingleObjectEx
0x180020a4c  nop     dword ptr [rax+rax+00h]
0x180020a51  cmp     eax, 102h
0x180020a56  jz      short loc_180020A71
0x180020a58  test    eax, 0FFFFFF7Fh
0x180020a5d  jz      short loc_180020A6C
0x180020a5f  mov     rcx, [rbp+188h]; this
0x180020a66  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180020a6c  mov     rsi, rbx
0x180020a6f  jmp     short loc_180020A73
0x180020a71  xor     esi, esi
0x180020a73  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180020a78  mov     [rsp+280h+var_240], rsi
0x180020a7d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180020a82  mov     [rsp+280h+var_248], 0
0x180020a8b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180020a90  mov     edi, eax
0x180020a92  test    eax, eax
0x180020a94  jns     short loc_180020AD6
0x180020a96  mov     rcx, [rbp+188h]; this
0x180020a9d  lea     r8, aWil; "wil"
0x180020aa4  mov     r9d, eax; char *
0x180020aa7  mov     edx, 66h ; 'f'; void *
0x180020aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ab1  mov     rcx, [rbp+188h]; this
0x180020ab8  lea     r8, aWil; "wil"
0x180020abf  mov     r9d, edi; char *
0x180020ac2  mov     edx, 6Fh ; 'o'; void *
0x180020ac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020acc  mov     r9d, edi
0x180020acf  mov     edx, 12Eh
0x180020ad4  jmp     short loc_180020B13
0x180020ad6  mov     rax, [rsp+280h+var_248]
0x180020adb  lea     rcx, ds:0[rax*4]
0x180020ae3  test    rcx, rcx
0x180020ae6  jz      short loc_180020AF3
0x180020ae8  mov     [r14], rcx
0x180020aeb  mov     eax, [rcx]
0x180020aed  inc     eax
0x180020aef  mov     [rcx], eax
0x180020af1  jmp     short loc_180020B43
0x180020af3  mov     r8, r14
0x180020af6  lea     rdx, [rsp+280h+var_250]
0x180020afb  lea     rcx, [rsp+280h+Name]
0x180020b00  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180020b05  mov     edi, eax
0x180020b07  test    eax, eax
0x180020b09  jns     short loc_180020B3E
0x180020b0b  mov     r9d, eax; char *
0x180020b0e  mov     edx, 137h; void *
0x180020b13  mov     rcx, [rbp+188h]; this
0x180020b1a  lea     r8, aWil; "wil"
0x180020b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b26  lea     rcx, [rsp+280h+var_240]
0x180020b2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020b30  lea     rcx, [rsp+280h+var_250]
0x180020b35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020b3a  mov     eax, edi
0x180020b3c  jmp     short loc_180020B5F
0x180020b3e  mov     rbx, [rsp+280h+var_250]
0x180020b43  test    rsi, rsi
0x180020b46  jz      short loc_180020B50
0x180020b48  mov     rcx, rsi; this
0x180020b4b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180020b50  test    rbx, rbx
0x180020b53  jz      short loc_180020B5D
0x180020b55  mov     rcx, rbx; this
0x180020b58  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180020b5d  xor     eax, eax
0x180020b5f  mov     rcx, [rbp+180h+var_20]
0x180020b66  xor     rcx, rsp; StackCookie
0x180020b69  call    __security_check_cookie
0x180020b6e  lea     r11, [rsp+280h+var_10]
0x180020b76  mov     rbx, [r11+30h]
0x180020b7a  mov     rsi, [r11+38h]
0x180020b7e  mov     rsp, r11
0x180020b81  pop     r14
0x180020b83  pop     rdi
0x180020b84  pop     rbp
0x180020b85  retn
```
