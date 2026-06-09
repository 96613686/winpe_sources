# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000696c`
- end: `0x180006ad8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800079d4`

## callees

- `0x180002b50`
- `0x180006530`
- `0x180006550`
- `0x18000696c`
- `0x1800077d0`
- `0x1800084cc`
- `0x18000972c`
- `0x180009ec0`
- `0x18000a15c`
- `0x18000a87c`
- `0x18000ab14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800069ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069a4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000696c  mov     [rsp-8+arg_10], rbx
0x180006971  mov     [rsp-8+arg_18], rdi
0x180006976  push    rbp
0x180006977  lea     rbp, [rsp-170h]
0x18000697f  sub     rsp, 270h
0x180006986  mov     rax, cs:__security_cookie
0x18000698d  xor     rax, rsp
0x180006990  mov     [rbp+170h+var_10], rax
0x180006997  mov     rdi, rdx
0x18000699a  mov     qword ptr [rdx], 0
0x1800069a1  mov     rbx, rcx
0x1800069a4  call    cs:__imp_GetCurrentProcessId
0x1800069ab  nop     dword ptr [rax+rax+00h]
0x1800069b0  mov     [rsp+270h+var_248], rbx
0x1800069b5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800069bc  mov     r9d, eax
0x1800069bf  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800069c7  mov     edx, 104h; unsigned __int64
0x1800069cc  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800069d1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800069d6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800069dc  mov     [rsp+270h+var_240], 0
0x1800069e5  xor     r8d, r8d; dwFlags
0x1800069e8  lea     rdx, [rsp+270h+Name]; lpName
0x1800069ed  xor     ecx, ecx; lpMutexAttributes
0x1800069ef  call    cs:__imp_CreateMutexExW
0x1800069f6  nop     dword ptr [rax+rax+00h]
0x1800069fb  mov     rdx, rax
0x1800069fe  lea     rcx, [rsp+270h+var_240]
0x180006a03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006a08  cmp     [rsp+270h+var_240], 0
0x180006a0e  jnz     short loc_180006A19
0x180006a10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006a15  mov     ebx, eax
0x180006a17  jmp     short loc_180006A85
0x180006a19  lea     rdx, [rsp+270h+var_238]
0x180006a1e  lea     rcx, [rsp+270h+var_240]
0x180006a23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180006a28  lea     rdx, [rsp+270h+var_230]; void **
0x180006a2d  mov     [rsp+270h+var_230], 0
0x180006a36  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006a3b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180006a40  mov     ebx, eax
0x180006a42  test    eax, eax
0x180006a44  jns     short loc_180006A66
0x180006a46  mov     edx, 12Eh; void *
0x180006a4b  mov     rcx, [rbp+178h]; this
0x180006a52  mov     r9d, eax; char *
0x180006a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a5a  lea     rcx, [rsp+270h+var_238]
0x180006a5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a64  jmp     short loc_180006A85
0x180006a66  mov     rcx, [rsp+270h+var_230]
0x180006a6b  test    rcx, rcx
0x180006a6e  jz      short loc_180006AB6
0x180006a70  mov     [rdi], rcx
0x180006a73  mov     eax, [rcx]
0x180006a75  inc     eax
0x180006a77  mov     [rcx], eax
0x180006a79  lea     rcx, [rsp+270h+var_238]
0x180006a7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a83  xor     ebx, ebx
0x180006a85  lea     rcx, [rsp+270h+var_240]
0x180006a8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006a8f  mov     eax, ebx
0x180006a91  mov     rcx, [rbp+170h+var_10]
0x180006a98  xor     rcx, rsp; StackCookie
0x180006a9b  call    __security_check_cookie
0x180006aa0  lea     r11, [rsp+270h+var_s0]
0x180006aa8  mov     rbx, [r11+20h]
0x180006aac  mov     rdi, [r11+28h]
0x180006ab0  mov     rsp, r11
0x180006ab3  pop     rbp
0x180006ab4  retn
0x180006ab6  mov     r8, rdi
0x180006ab9  lea     rdx, [rsp+270h+var_240]
0x180006abe  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006ac3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006ac8  mov     ebx, eax
0x180006aca  test    eax, eax
0x180006acc  jns     short loc_180006A79
0x180006ace  mov     edx, 137h
0x180006ad3  jmp     loc_180006A4B
```
