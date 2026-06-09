# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800170b4`
- end: `0x1800172a2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001705c`

## callees

- `0x1800089c0`
- `0x1800170b4`
- `0x1800172a8`
- `0x1800172c4`
- `0x1800175ac`
- `0x18002021c`
- `0x18002f824`
- `0x18002f8c0`
- `0x180033ad0`
- `0x1800358c0`
- `0x180037f34`
- `0x1800388f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180017173`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180017173`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001712b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001712b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800170ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800170ef`

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
  bool v9; // dl
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
  v20 = 304;
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v21);
    v16 = v15;
    v17 = 302;
LABEL_7:
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
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v15 = v19;
    if ( v19 < 0 )
    {
      v16 = (unsigned int)v19;
      v17 = 311;
      goto LABEL_7;
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
0x1800170b4  mov     [rsp-8+arg_10], rbx
0x1800170b9  mov     [rsp-8+arg_18], rsi
0x1800170be  push    rbp
0x1800170bf  push    rdi
0x1800170c0  push    r14
0x1800170c2  lea     rbp, [rsp-170h]
0x1800170ca  sub     rsp, 270h
0x1800170d1  mov     rax, cs:__security_cookie
0x1800170d8  xor     rax, rsp
0x1800170db  mov     [rbp+180h+var_20], rax
0x1800170e2  mov     r14, rdx
0x1800170e5  mov     qword ptr [rdx], 0
0x1800170ec  mov     rbx, rcx
0x1800170ef  call    cs:__imp_GetCurrentProcessId
0x1800170f5  mov     [rsp+280h+var_258], rbx
0x1800170fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017101  mov     r9d, eax
0x180017104  mov     [rsp+280h+var_260], 130h; int
0x18001710c  mov     edx, 104h; unsigned __int64
0x180017111  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017116  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001711b  mov     r9d, 1F0001h; dwDesiredAccess
0x180017121  lea     rdx, [rsp+280h+Name]; lpName
0x180017126  xor     r8d, r8d; dwFlags
0x180017129  xor     ecx, ecx; lpMutexAttributes
0x18001712b  call    cs:__imp_CreateMutexExW
0x180017131  mov     [rsp+280h+var_250], rax
0x180017136  mov     rbx, rax
0x180017139  test    rax, rax
0x18001713c  jnz     short loc_18001716A
0x18001713e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017143  mov     rcx, [rbp+180h+var_20]
0x18001714a  xor     rcx, rsp; StackCookie
0x18001714d  call    __security_check_cookie
0x180017152  lea     r11, [rsp+280h+var_10]
0x18001715a  mov     rbx, [r11+30h]
0x18001715e  mov     rsi, [r11+38h]
0x180017162  mov     rsp, r11
0x180017165  pop     r14
0x180017167  pop     rdi
0x180017168  pop     rbp
0x180017169  retn
0x18001716a  xor     r8d, r8d; bAlertable
0x18001716d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017170  mov     rcx, rbx; hHandle
0x180017173  call    cs:__imp_WaitForSingleObjectEx
0x180017179  cmp     eax, 102h
0x18001717e  jnz     loc_18001724B
0x180017184  xor     esi, esi
0x180017186  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001718b  mov     [rsp+280h+var_240], rsi
0x180017190  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017195  mov     [rsp+280h+var_248], 0
0x18001719e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800171a3  mov     edi, eax
0x1800171a5  test    eax, eax
0x1800171a7  jns     short loc_180017215
0x1800171a9  mov     rcx, [rbp+188h]; this
0x1800171b0  lea     r8, aWil; "wil"
0x1800171b7  mov     r9d, eax; char *
0x1800171ba  mov     edx, 66h ; 'f'; void *
0x1800171bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171c4  mov     rcx, [rbp+188h]; this
0x1800171cb  lea     r8, aWil; "wil"
0x1800171d2  mov     r9d, edi; char *
0x1800171d5  mov     edx, 6Fh ; 'o'; void *
0x1800171da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171df  mov     r9d, edi; char *
0x1800171e2  mov     edx, 12Eh; void *
0x1800171e7  mov     rcx, [rbp+188h]; this
0x1800171ee  lea     r8, aWil; "wil"
0x1800171f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171fa  lea     rcx, [rsp+280h+var_240]
0x1800171ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017204  lea     rcx, [rsp+280h+var_250]
0x180017209  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001720e  mov     eax, edi
0x180017210  jmp     loc_180017143
0x180017215  mov     rax, [rsp+280h+var_248]
0x18001721a  lea     rcx, ds:0[rax*4]
0x180017222  test    rcx, rcx
0x180017225  jz      short loc_18001726C
0x180017227  mov     [r14], rcx
0x18001722a  mov     eax, [rcx]
0x18001722c  inc     eax
0x18001722e  mov     [rcx], eax
0x180017230  test    rsi, rsi
0x180017233  jnz     short loc_180017298
0x180017235  test    rbx, rbx
0x180017238  jnz     short loc_180017241
0x18001723a  xor     eax, eax
0x18001723c  jmp     loc_180017143
0x180017241  mov     rcx, rbx; this
0x180017244  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180017249  jmp     short loc_18001723A
0x18001724b  test    eax, 0FFFFFF7Fh
0x180017250  jz      short loc_180017264
0x180017252  mov     rcx, [rbp+188h]; this
0x180017259  mov     edx, 0E01h; void *
0x18001725e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180017264  mov     rsi, rbx
0x180017267  jmp     loc_180017186
0x18001726c  mov     r8, r14
0x18001726f  lea     rdx, [rsp+280h+var_250]
0x180017274  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017279  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001727e  mov     edi, eax
0x180017280  test    eax, eax
0x180017282  jns     short loc_180017291
0x180017284  mov     r9d, eax
0x180017287  mov     edx, 137h
0x18001728c  jmp     loc_1800171E7
0x180017291  mov     rbx, [rsp+280h+var_250]
0x180017296  jmp     short loc_180017230
0x180017298  mov     rcx, rsi; this
0x18001729b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800172a0  jmp     short loc_180017235
```
