# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180021730`
- end: `0x180021896`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800247e0`

## callees

- `0x180007440`
- `0x18000aa20`
- `0x18000aa3c`
- `0x18000b418`
- `0x18000c3d4`
- `0x18000ca28`
- `0x18000cbd8`
- `0x18000d0ac`
- `0x18000d19c`
- `0x180021730`
- `0x180026e4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800217ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800217ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021768`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180021730  mov     [rsp-8+arg_10], rbx
0x180021735  mov     [rsp-8+arg_18], rdi
0x18002173a  push    rbp
0x18002173b  lea     rbp, [rsp-170h]
0x180021743  sub     rsp, 270h
0x18002174a  mov     rax, cs:__security_cookie
0x180021751  xor     rax, rsp
0x180021754  mov     [rbp+170h+var_10], rax
0x18002175b  mov     rdi, rdx
0x18002175e  mov     qword ptr [rdx], 0
0x180021765  mov     rbx, rcx
0x180021768  call    cs:__imp_GetCurrentProcessId
0x18002176e  mov     [rsp+270h+var_248], rbx
0x180021773  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002177a  mov     r9d, eax
0x18002177d  mov     [rsp+270h+var_250], 130h; int
0x180021785  mov     edx, 104h; unsigned __int64
0x18002178a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002178f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021794  mov     r9d, 1F0001h; dwDesiredAccess
0x18002179a  mov     [rsp+270h+var_240], 0
0x1800217a3  xor     r8d, r8d; dwFlags
0x1800217a6  lea     rdx, [rsp+270h+Name]; lpName
0x1800217ab  xor     ecx, ecx; lpMutexAttributes
0x1800217ad  call    cs:__imp_CreateMutexExW
0x1800217b3  mov     rdx, rax
0x1800217b6  lea     rcx, [rsp+270h+var_240]
0x1800217bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800217c0  cmp     [rsp+270h+var_240], 0
0x1800217c6  jnz     short loc_1800217D1
0x1800217c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800217cd  mov     ebx, eax
0x1800217cf  jmp     short loc_180021844
0x1800217d1  lea     rdx, [rsp+270h+var_238]
0x1800217d6  lea     rcx, [rsp+270h+var_240]
0x1800217db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800217e0  lea     rdx, [rsp+270h+var_230]; void **
0x1800217e5  mov     [rsp+270h+var_230], 0
0x1800217ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800217f3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800217f8  mov     ebx, eax
0x1800217fa  test    eax, eax
0x1800217fc  jns     short loc_180021825
0x1800217fe  mov     edx, 12Eh; void *
0x180021803  mov     rcx, [rbp+178h]; this
0x18002180a  lea     r8, aWil; "wil"
0x180021811  mov     r9d, eax; char *
0x180021814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021819  lea     rcx, [rsp+270h+var_238]
0x18002181e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021823  jmp     short loc_180021844
0x180021825  mov     rcx, [rsp+270h+var_230]
0x18002182a  test    rcx, rcx
0x18002182d  jz      short loc_180021874
0x18002182f  mov     [rdi], rcx
0x180021832  mov     eax, [rcx]
0x180021834  inc     eax
0x180021836  mov     [rcx], eax
0x180021838  lea     rcx, [rsp+270h+var_238]
0x18002183d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021842  xor     ebx, ebx
0x180021844  lea     rcx, [rsp+270h+var_240]
0x180021849  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002184e  mov     eax, ebx
0x180021850  mov     rcx, [rbp+170h+var_10]
0x180021857  xor     rcx, rsp; StackCookie
0x18002185a  call    __security_check_cookie
0x18002185f  lea     r11, [rsp+270h+var_s0]
0x180021867  mov     rbx, [r11+20h]
0x18002186b  mov     rdi, [r11+28h]
0x18002186f  mov     rsp, r11
0x180021872  pop     rbp
0x180021873  retn
0x180021874  mov     r8, rdi
0x180021877  lea     rdx, [rsp+270h+var_240]
0x18002187c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180021881  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180021886  mov     ebx, eax
0x180021888  test    eax, eax
0x18002188a  jns     short loc_180021838
0x18002188c  mov     edx, 137h
0x180021891  jmp     loc_180021803
```
