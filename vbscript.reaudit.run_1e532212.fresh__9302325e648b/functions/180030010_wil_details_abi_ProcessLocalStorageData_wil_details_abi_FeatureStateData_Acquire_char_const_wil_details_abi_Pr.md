# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180030010`
- end: `0x18003022a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002ffb8`

## callees

- `0x180030010`
- `0x180030230`
- `0x180030294`
- `0x1800306bc`
- `0x1800306e8`
- `0x18003a6d4`
- `0x180040c28`
- `0x18004221c`
- `0x1800425bc`
- `0x1800470c0`
- `0x180047d14`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003004b`
- `KERNEL32!GetCurrentProcessId` at `0x18003004b`
- `KERNEL32!CreateMutexExW` at `0x180030087`
- `KERNEL32!CreateMutexExW` at `0x180030087`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800300a7`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800300a7`

## string_xrefs

- `0x1800301ad`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  DWORD v7; // eax
  bool v8; // dl
  char *v9; // r9
  wil::details *v10; // rdi
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // esi
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  void *v17; // rdx
  _DWORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v27; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v25 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = v6;
  }
  v27 = v10;
  v26 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v26, (bool *)v9);
  v14 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v19 = (_DWORD *)(4 * v26);
    if ( 4 * v26 )
    {
      *a2 = v19;
      ++*v19;
    }
    else
    {
      v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v22 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v21, (const char *)(unsigned int)v20, 304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
        return v22;
      }
      v6 = v25;
    }
    if ( v10 )
      wil::details::ReleaseMutex(v10, v12);
    if ( v6 )
      wil::details::CloseHandle(v6, v12);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v23);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v24);
    if ( v10 )
      wil::details::ReleaseMutex(v10, v17);
    wil::details::CloseHandle(v6, v17);
    return v14;
  }
}

```

## disassembly

```asm
0x180030010  mov     [rsp-8+arg_10], rbx
0x180030015  mov     [rsp-8+arg_18], rsi
0x18003001a  push    rbp
0x18003001b  push    rdi
0x18003001c  push    r14
0x18003001e  lea     rbp, [rsp-170h]
0x180030026  sub     rsp, 270h
0x18003002d  mov     rax, cs:__security_cookie
0x180030034  xor     rax, rsp
0x180030037  mov     [rbp+180h+var_20], rax
0x18003003e  mov     r14, rdx
0x180030041  mov     qword ptr [rdx], 0
0x180030048  mov     rbx, rcx
0x18003004b  call    cs:__imp_GetCurrentProcessId
0x180030051  mov     [rsp+280h+var_258], rbx
0x180030056  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003005d  mov     r9d, eax
0x180030060  mov     [rsp+280h+var_260], 130h; int
0x180030068  mov     edx, 104h; unsigned __int64
0x18003006d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180030072  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030077  mov     r9d, 1F0001h; dwDesiredAccess
0x18003007d  lea     rdx, [rsp+280h+Name]; lpName
0x180030082  xor     r8d, r8d; dwFlags
0x180030085  xor     ecx, ecx; lpMutexAttributes
0x180030087  call    cs:__imp_CreateMutexExW
0x18003008d  mov     [rsp+280h+var_250], rax
0x180030092  mov     rbx, rax
0x180030095  test    rax, rax
0x180030098  jz      loc_18003013E
0x18003009e  xor     r8d, r8d; bAlertable
0x1800300a1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800300a4  mov     rcx, rax; hHandle
0x1800300a7  call    cs:__imp_WaitForSingleObjectEx
0x1800300ad  cmp     eax, 102h
0x1800300b2  jz      loc_18003016A
0x1800300b8  test    eax, 0FFFFFF7Fh
0x1800300bd  jnz     loc_1800301A6
0x1800300c3  mov     rdi, rbx
0x1800300c6  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800300cb  mov     [rsp+280h+var_240], rdi
0x1800300d0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800300d5  mov     [rsp+280h+var_248], 0
0x1800300de  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800300e3  mov     esi, eax
0x1800300e5  test    eax, eax
0x1800300e7  jns     loc_180030171
0x1800300ed  mov     rcx, [rbp+188h]; this
0x1800300f4  mov     r9d, eax; char *
0x1800300f7  mov     edx, 66h ; 'f'; void *
0x1800300fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030101  mov     rcx, [rbp+188h]; this
0x180030108  mov     r9d, esi; char *
0x18003010b  mov     edx, 6Fh ; 'o'; void *
0x180030110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030115  mov     rcx, [rbp+188h]; this
0x18003011c  mov     r9d, esi; char *
0x18003011f  mov     edx, 12Eh; void *
0x180030124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030129  test    rdi, rdi
0x18003012c  jnz     loc_1800301BF
0x180030132  mov     rcx, rbx; this
0x180030135  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003013a  mov     eax, esi
0x18003013c  jmp     short loc_180030143
0x18003013e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030143  mov     rcx, [rbp+180h+var_20]
0x18003014a  xor     rcx, rsp; StackCookie
0x18003014d  call    __security_check_cookie
0x180030152  lea     r11, [rsp+280h+var_10]
0x18003015a  mov     rbx, [r11+30h]
0x18003015e  mov     rsi, [r11+38h]
0x180030162  mov     rsp, r11
0x180030165  pop     r14
0x180030167  pop     rdi
0x180030168  pop     rbp
0x180030169  retn
0x18003016a  xor     edi, edi
0x18003016c  jmp     loc_1800300C6
0x180030171  mov     rax, [rsp+280h+var_248]
0x180030176  lea     rcx, ds:0[rax*4]
0x18003017e  test    rcx, rcx
0x180030181  jz      short loc_1800301CC
0x180030183  mov     [r14], rcx
0x180030186  mov     eax, [rcx]
0x180030188  inc     eax
0x18003018a  mov     [rcx], eax
0x18003018c  test    rdi, rdi
0x18003018f  jnz     loc_18003021D
0x180030195  test    rbx, rbx
0x180030198  jz      short loc_1800301A2
0x18003019a  mov     rcx, rbx; this
0x18003019d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800301a2  xor     eax, eax
0x1800301a4  jmp     short loc_180030143
0x1800301a6  mov     rcx, [rbp+188h]; this
0x1800301ad  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800301b4  mov     edx, 0E01h; void *
0x1800301b9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800301bf  mov     rcx, rdi; this
0x1800301c2  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800301c7  jmp     loc_180030132
0x1800301cc  mov     r8, r14
0x1800301cf  lea     rdx, [rsp+280h+var_250]
0x1800301d4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800301d9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800301de  mov     ebx, eax
0x1800301e0  test    eax, eax
0x1800301e2  jns     short loc_180030213
0x1800301e4  mov     rcx, [rbp+188h]; this
0x1800301eb  mov     r9d, eax; char *
0x1800301ee  mov     edx, 137h; void *
0x1800301f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301f8  lea     rcx, [rsp+280h+var_240]
0x1800301fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030202  lea     rcx, [rsp+280h+var_250]
0x180030207  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003020c  mov     eax, ebx
0x18003020e  jmp     loc_180030143
0x180030213  mov     rbx, [rsp+280h+var_250]
0x180030218  jmp     loc_18003018C
0x18003021d  mov     rcx, rdi; this
0x180030220  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180030225  jmp     loc_180030195
```
