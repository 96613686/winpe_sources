# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180012094`
- end: `0x180012259`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e938`

## callees

- `0x180012094`
- `0x180012260`
- `0x1800122c4`
- `0x180016174`
- `0x180016cd8`
- `0x180016cf4`
- `0x180017278`
- `0x18001e0bc`
- `0x18001e2b4`
- `0x18001ec5c`
- `0x18001f2f8`
- `0x180022190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001210b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001210b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012133`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012133`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800120cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800120cf`

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
  unsigned int LastErrorFailHr; // esi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  wil::details *v12; // rdi
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  _DWORD *v20; // rcx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v27; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v23 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v25 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_15:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v27 = v12;
  v26 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v26, (bool *)v11);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)LastErrorFailHr, v24);
    v18 = LastErrorFailHr;
    v19 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v17, (const char *)v18, v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    goto LABEL_15;
  }
  v20 = (_DWORD *)(4 * v26);
  if ( 4 * v26 )
  {
    *a2 = v20;
    ++*v20;
  }
  else
  {
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v21;
    if ( v21 < 0 )
    {
      v18 = (unsigned int)v21;
      v19 = 311;
      goto LABEL_14;
    }
    v6 = v25;
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
0x180012094  mov     [rsp-8+arg_10], rbx
0x180012099  mov     [rsp-8+arg_18], rsi
0x18001209e  push    rbp
0x18001209f  push    rdi
0x1800120a0  push    r14
0x1800120a2  lea     rbp, [rsp-170h]
0x1800120aa  sub     rsp, 270h
0x1800120b1  mov     rax, cs:__security_cookie
0x1800120b8  xor     rax, rsp
0x1800120bb  mov     [rbp+180h+var_20], rax
0x1800120c2  mov     r14, rdx
0x1800120c5  mov     qword ptr [rdx], 0
0x1800120cc  mov     rbx, rcx
0x1800120cf  call    cs:__imp_GetCurrentProcessId
0x1800120d5  mov     [rsp+280h+var_258], rbx
0x1800120da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800120e1  mov     r9d, eax
0x1800120e4  mov     [rsp+280h+var_260], 130h; int
0x1800120ec  mov     edx, 104h; unsigned __int64
0x1800120f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800120f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800120fb  mov     r9d, 1F0001h; dwDesiredAccess
0x180012101  lea     rdx, [rsp+280h+Name]; lpName
0x180012106  xor     r8d, r8d; dwFlags
0x180012109  xor     ecx, ecx; lpMutexAttributes
0x18001210b  call    cs:__imp_CreateMutexExW
0x180012111  mov     [rsp+280h+var_250], rax
0x180012116  mov     rbx, rax
0x180012119  test    rax, rax
0x18001211c  jnz     short loc_18001212A
0x18001211e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012123  mov     esi, eax
0x180012125  jmp     loc_180012203
0x18001212a  xor     r8d, r8d; bAlertable
0x18001212d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012130  mov     rcx, rbx; hHandle
0x180012133  call    cs:__imp_WaitForSingleObjectEx
0x180012139  cmp     eax, 102h
0x18001213e  jz      short loc_180012159
0x180012140  test    eax, 0FFFFFF7Fh
0x180012145  jz      short loc_180012154
0x180012147  mov     rcx, [rbp+188h]; this
0x18001214e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012154  mov     rdi, rbx
0x180012157  jmp     short loc_18001215B
0x180012159  xor     edi, edi
0x18001215b  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180012160  mov     [rsp+280h+var_240], rdi
0x180012165  lea     rcx, [rsp+280h+Name]; pszSrc
0x18001216a  mov     [rsp+280h+var_248], 0
0x180012173  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180012178  mov     esi, eax
0x18001217a  test    eax, eax
0x18001217c  jns     short loc_1800121B0
0x18001217e  mov     rcx, [rbp+188h]; this
0x180012185  mov     r9d, eax; char *
0x180012188  mov     edx, 66h ; 'f'; void *
0x18001218d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012192  mov     rcx, [rbp+188h]; this
0x180012199  mov     r9d, esi; char *
0x18001219c  mov     edx, 6Fh ; 'o'; void *
0x1800121a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121a6  mov     r9d, esi
0x1800121a9  mov     edx, 12Eh
0x1800121ae  jmp     short loc_1800121ED
0x1800121b0  mov     rax, [rsp+280h+var_248]
0x1800121b5  lea     rcx, ds:0[rax*4]
0x1800121bd  test    rcx, rcx
0x1800121c0  jz      short loc_1800121CD
0x1800121c2  mov     [r14], rcx
0x1800121c5  mov     eax, [rcx]
0x1800121c7  inc     eax
0x1800121c9  mov     [rcx], eax
0x1800121cb  jmp     short loc_180012216
0x1800121cd  mov     r8, r14
0x1800121d0  lea     rdx, [rsp+280h+var_250]
0x1800121d5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800121da  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800121df  mov     esi, eax
0x1800121e1  test    eax, eax
0x1800121e3  jns     short loc_180012211
0x1800121e5  mov     r9d, eax; char *
0x1800121e8  mov     edx, 137h; void *
0x1800121ed  mov     rcx, [rbp+188h]; this
0x1800121f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121f9  lea     rcx, [rsp+280h+var_240]
0x1800121fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012203  lea     rcx, [rsp+280h+var_250]
0x180012208  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001220d  mov     eax, esi
0x18001220f  jmp     short loc_180012232
0x180012211  mov     rbx, [rsp+280h+var_250]
0x180012216  test    rdi, rdi
0x180012219  jz      short loc_180012223
0x18001221b  mov     rcx, rdi; this
0x18001221e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180012223  test    rbx, rbx
0x180012226  jz      short loc_180012230
0x180012228  mov     rcx, rbx; this
0x18001222b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180012230  xor     eax, eax
0x180012232  mov     rcx, [rbp+180h+var_20]
0x180012239  xor     rcx, rsp; StackCookie
0x18001223c  call    __security_check_cookie
0x180012241  lea     r11, [rsp+280h+var_10]
0x180012249  mov     rbx, [r11+30h]
0x18001224d  mov     rsi, [r11+38h]
0x180012251  mov     rsp, r11
0x180012254  pop     r14
0x180012256  pop     rdi
0x180012257  pop     rbp
0x180012258  retn
```
