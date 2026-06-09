# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180045fb0`
- end: `0x1800461cf`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800457dc`

## callees

- `0x180045100`
- `0x180045594`
- `0x180045850`
- `0x18004586c`
- `0x180045cb0`
- `0x180045fb0`
- `0x1800469e8`
- `0x1800e29a8`
- `0x1800e34bc`
- `0x1800e3810`
- `0x18015cb00`
- `0x1802798c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046027`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046027`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004606f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004606f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180045feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180045feb`

## string_xrefs

- `0x180046165`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  void *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  v23 = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v16);
    wil::details::CloseHandle(v6, v16);
    return v14;
  }
  else
  {
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v17,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        return v18;
      }
      v6 = v21;
    }
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180045fb0  mov     [rsp-8+arg_10], rbx
0x180045fb5  mov     [rsp-8+arg_18], rsi
0x180045fba  push    rbp
0x180045fbb  push    rdi
0x180045fbc  push    r14
0x180045fbe  lea     rbp, [rsp-170h]
0x180045fc6  sub     rsp, 270h
0x180045fcd  mov     rax, cs:__security_cookie
0x180045fd4  xor     rax, rsp
0x180045fd7  mov     [rbp+180h+var_20], rax
0x180045fde  mov     r14, rdx
0x180045fe1  mov     qword ptr [rdx], 0
0x180045fe8  mov     rbx, rcx
0x180045feb  call    cs:__imp_GetCurrentProcessId
0x180045ff1  mov     [rsp+280h+var_258], rbx
0x180045ff6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180045ffd  mov     r9d, eax
0x180046000  mov     [rsp+280h+var_260], 130h; int
0x180046008  mov     edx, 104h; unsigned __int64
0x18004600d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180046012  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180046017  mov     r9d, 1F0001h; dwDesiredAccess
0x18004601d  lea     rdx, [rsp+280h+Name]; lpName
0x180046022  xor     r8d, r8d; dwFlags
0x180046025  xor     ecx, ecx; lpMutexAttributes
0x180046027  call    cs:__imp_CreateMutexExW
0x18004602d  mov     [rsp+280h+var_250], rax
0x180046032  mov     rbx, rax
0x180046035  test    rax, rax
0x180046038  jnz     short loc_180046066
0x18004603a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004603f  mov     rcx, [rbp+180h+var_20]
0x180046046  xor     rcx, rsp; StackCookie
0x180046049  call    __security_check_cookie
0x18004604e  lea     r11, [rsp+280h+var_10]
0x180046056  mov     rbx, [r11+30h]
0x18004605a  mov     rsi, [r11+38h]
0x18004605e  mov     rsp, r11
0x180046061  pop     r14
0x180046063  pop     rdi
0x180046064  pop     rbp
0x180046065  retn
0x180046066  xor     r8d, r8d; bAlertable
0x180046069  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004606c  mov     rcx, rbx; hHandle
0x18004606f  call    cs:__imp_WaitForSingleObjectEx
0x180046075  cmp     eax, 102h
0x18004607a  jz      short loc_1800460ED
0x18004607c  test    eax, 0FFFFFF7Fh
0x180046081  jnz     loc_18004615E
0x180046087  mov     rdi, rbx
0x18004608a  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004608f  mov     [rsp+280h+var_240], rdi
0x180046094  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180046099  mov     [rsp+280h+var_248], 0
0x1800460a2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800460a7  mov     esi, eax
0x1800460a9  test    eax, eax
0x1800460ab  js      short loc_1800460F1
0x1800460ad  mov     rax, [rsp+280h+var_248]
0x1800460b2  lea     rcx, ds:0[rax*4]
0x1800460ba  test    rcx, rcx
0x1800460bd  jz      loc_180046177
0x1800460c3  mov     [r14], rcx
0x1800460c6  mov     eax, [rcx]
0x1800460c8  inc     eax
0x1800460ca  mov     [rcx], eax
0x1800460cc  test    rdi, rdi
0x1800460cf  jz      short loc_1800460D9
0x1800460d1  mov     rcx, rdi; this
0x1800460d4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800460d9  test    rbx, rbx
0x1800460dc  jz      short loc_1800460E6
0x1800460de  mov     rcx, rbx; this
0x1800460e1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800460e6  xor     eax, eax
0x1800460e8  jmp     loc_18004603F
0x1800460ed  xor     edi, edi
0x1800460ef  jmp     short loc_18004608A
0x1800460f1  mov     rcx, [rbp+188h]; this
0x1800460f8  lea     r8, aWil; "wil"
0x1800460ff  mov     r9d, esi; char *
0x180046102  mov     edx, 66h ; 'f'; void *
0x180046107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004610c  mov     rcx, [rbp+188h]; this
0x180046113  lea     r8, aWil; "wil"
0x18004611a  mov     r9d, esi; char *
0x18004611d  mov     edx, 6Fh ; 'o'; void *
0x180046122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046127  mov     rcx, [rbp+188h]; this
0x18004612e  lea     r8, aWil; "wil"
0x180046135  mov     r9d, esi; char *
0x180046138  mov     edx, 12Eh; void *
0x18004613d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046142  test    rdi, rdi
0x180046145  jz      short loc_18004614F
0x180046147  mov     rcx, rdi; this
0x18004614a  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18004614f  mov     rcx, rbx; this
0x180046152  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180046157  mov     eax, esi
0x180046159  jmp     loc_18004603F
0x18004615e  mov     rcx, [rbp+188h]; this
0x180046165  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004616c  mov     edx, 0E01h; void *
0x180046171  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180046177  mov     r8, r14
0x18004617a  lea     rdx, [rsp+280h+var_250]
0x18004617f  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180046184  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180046189  mov     ebx, eax
0x18004618b  test    eax, eax
0x18004618d  jns     short loc_1800461C5
0x18004618f  mov     rcx, [rbp+188h]; this
0x180046196  lea     r8, aWil; "wil"
0x18004619d  mov     r9d, eax; char *
0x1800461a0  mov     edx, 137h; void *
0x1800461a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800461aa  lea     rcx, [rsp+280h+var_240]
0x1800461af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800461b4  lea     rcx, [rsp+280h+var_250]
0x1800461b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800461be  mov     eax, ebx
0x1800461c0  jmp     loc_18004603F
0x1800461c5  mov     rbx, [rsp+280h+var_250]
0x1800461ca  jmp     loc_1800460CC
```
