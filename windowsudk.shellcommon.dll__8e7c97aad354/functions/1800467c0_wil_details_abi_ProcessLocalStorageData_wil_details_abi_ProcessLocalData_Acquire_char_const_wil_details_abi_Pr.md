# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800467c0`
- end: `0x1800469df`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180046678`

## callees

- `0x180044adc`
- `0x180045100`
- `0x180045594`
- `0x180045850`
- `0x18004586c`
- `0x180045cb0`
- `0x1800467c0`
- `0x1800469e8`
- `0x1800e29a8`
- `0x1800e34bc`
- `0x1800e3810`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046837`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046837`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004687f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004687f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800467fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800467fb`

## string_xrefs

- `0x180046975`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      120);
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
0x1800467c0  mov     [rsp-8+arg_10], rbx
0x1800467c5  mov     [rsp-8+arg_18], rsi
0x1800467ca  push    rbp
0x1800467cb  push    rdi
0x1800467cc  push    r14
0x1800467ce  lea     rbp, [rsp-170h]
0x1800467d6  sub     rsp, 270h
0x1800467dd  mov     rax, cs:__security_cookie
0x1800467e4  xor     rax, rsp
0x1800467e7  mov     [rbp+180h+var_20], rax
0x1800467ee  mov     r14, rdx
0x1800467f1  mov     qword ptr [rdx], 0
0x1800467f8  mov     rbx, rcx
0x1800467fb  call    cs:__imp_GetCurrentProcessId
0x180046801  mov     [rsp+280h+var_258], rbx
0x180046806  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004680d  mov     r9d, eax
0x180046810  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180046818  mov     edx, 104h; unsigned __int64
0x18004681d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180046822  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180046827  mov     r9d, 1F0001h; dwDesiredAccess
0x18004682d  lea     rdx, [rsp+280h+Name]; lpName
0x180046832  xor     r8d, r8d; dwFlags
0x180046835  xor     ecx, ecx; lpMutexAttributes
0x180046837  call    cs:__imp_CreateMutexExW
0x18004683d  mov     [rsp+280h+var_250], rax
0x180046842  mov     rbx, rax
0x180046845  test    rax, rax
0x180046848  jnz     short loc_180046876
0x18004684a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004684f  mov     rcx, [rbp+180h+var_20]
0x180046856  xor     rcx, rsp; StackCookie
0x180046859  call    __security_check_cookie
0x18004685e  lea     r11, [rsp+280h+var_10]
0x180046866  mov     rbx, [r11+30h]
0x18004686a  mov     rsi, [r11+38h]
0x18004686e  mov     rsp, r11
0x180046871  pop     r14
0x180046873  pop     rdi
0x180046874  pop     rbp
0x180046875  retn
0x180046876  xor     r8d, r8d; bAlertable
0x180046879  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004687c  mov     rcx, rbx; hHandle
0x18004687f  call    cs:__imp_WaitForSingleObjectEx
0x180046885  cmp     eax, 102h
0x18004688a  jz      short loc_1800468FD
0x18004688c  test    eax, 0FFFFFF7Fh
0x180046891  jnz     loc_18004696E
0x180046897  mov     rdi, rbx
0x18004689a  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18004689f  mov     [rsp+280h+var_240], rdi
0x1800468a4  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800468a9  mov     [rsp+280h+var_248], 0
0x1800468b2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800468b7  mov     esi, eax
0x1800468b9  test    eax, eax
0x1800468bb  js      short loc_180046901
0x1800468bd  mov     rax, [rsp+280h+var_248]
0x1800468c2  lea     rcx, ds:0[rax*4]
0x1800468ca  test    rcx, rcx
0x1800468cd  jz      loc_180046987
0x1800468d3  mov     [r14], rcx
0x1800468d6  mov     eax, [rcx]
0x1800468d8  inc     eax
0x1800468da  mov     [rcx], eax
0x1800468dc  test    rdi, rdi
0x1800468df  jz      short loc_1800468E9
0x1800468e1  mov     rcx, rdi; this
0x1800468e4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800468e9  test    rbx, rbx
0x1800468ec  jz      short loc_1800468F6
0x1800468ee  mov     rcx, rbx; this
0x1800468f1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800468f6  xor     eax, eax
0x1800468f8  jmp     loc_18004684F
0x1800468fd  xor     edi, edi
0x1800468ff  jmp     short loc_18004689A
0x180046901  mov     rcx, [rbp+188h]; this
0x180046908  lea     r8, aWil; "wil"
0x18004690f  mov     r9d, esi; char *
0x180046912  mov     edx, 66h ; 'f'; void *
0x180046917  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004691c  mov     rcx, [rbp+188h]; this
0x180046923  lea     r8, aWil; "wil"
0x18004692a  mov     r9d, esi; char *
0x18004692d  mov     edx, 6Fh ; 'o'; void *
0x180046932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046937  mov     rcx, [rbp+188h]; this
0x18004693e  lea     r8, aWil; "wil"
0x180046945  mov     r9d, esi; char *
0x180046948  mov     edx, 12Eh; void *
0x18004694d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046952  test    rdi, rdi
0x180046955  jz      short loc_18004695F
0x180046957  mov     rcx, rdi; this
0x18004695a  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18004695f  mov     rcx, rbx; this
0x180046962  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180046967  mov     eax, esi
0x180046969  jmp     loc_18004684F
0x18004696e  mov     rcx, [rbp+188h]; this
0x180046975  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004697c  mov     edx, 0E01h; void *
0x180046981  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180046987  mov     r8, r14
0x18004698a  lea     rdx, [rsp+280h+var_250]
0x18004698f  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180046994  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180046999  mov     ebx, eax
0x18004699b  test    eax, eax
0x18004699d  jns     short loc_1800469D5
0x18004699f  mov     rcx, [rbp+188h]; this
0x1800469a6  lea     r8, aWil; "wil"
0x1800469ad  mov     r9d, eax; char *
0x1800469b0  mov     edx, 137h; void *
0x1800469b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800469ba  lea     rcx, [rsp+280h+var_240]
0x1800469bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800469c4  lea     rcx, [rsp+280h+var_250]
0x1800469c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800469ce  mov     eax, ebx
0x1800469d0  jmp     loc_18004684F
0x1800469d5  mov     rbx, [rsp+280h+var_250]
0x1800469da  jmp     loc_1800468DC
```
