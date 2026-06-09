# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800235d0`
- end: `0x18002372f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024b38`

## callees

- `0x18001006c`
- `0x18001208c`
- `0x18001233c`
- `0x180012394`
- `0x180022f4c`
- `0x180022f68`
- `0x1800235d0`
- `0x180026968`
- `0x180028324`
- `0x180029af8`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023608`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023608`
- `KERNEL32!CreateMutexExW` at `0x18002364d`
- `KERNEL32!CreateMutexExW` at `0x18002364d`

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
0x1800235d0  mov     [rsp-8+arg_10], rbx
0x1800235d5  mov     [rsp-8+arg_18], rdi
0x1800235da  push    rbp
0x1800235db  lea     rbp, [rsp-170h]
0x1800235e3  sub     rsp, 270h
0x1800235ea  mov     rax, cs:__security_cookie
0x1800235f1  xor     rax, rsp
0x1800235f4  mov     [rbp+170h+var_10], rax
0x1800235fb  mov     rdi, rdx
0x1800235fe  mov     qword ptr [rdx], 0
0x180023605  mov     rbx, rcx
0x180023608  call    cs:__imp_GetCurrentProcessId
0x18002360e  mov     [rsp+270h+var_248], rbx
0x180023613  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002361a  mov     r9d, eax
0x18002361d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180023625  mov     edx, 104h; unsigned __int64
0x18002362a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002362f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023634  mov     r9d, 1F0001h; dwDesiredAccess
0x18002363a  mov     [rsp+270h+var_240], 0
0x180023643  xor     r8d, r8d; dwFlags
0x180023646  lea     rdx, [rsp+270h+Name]; lpName
0x18002364b  xor     ecx, ecx; lpMutexAttributes
0x18002364d  call    cs:__imp_CreateMutexExW
0x180023653  mov     rdx, rax
0x180023656  lea     rcx, [rsp+270h+var_240]
0x18002365b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023660  cmp     [rsp+270h+var_240], 0
0x180023666  jnz     short loc_180023671
0x180023668  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002366d  mov     ebx, eax
0x18002366f  jmp     short loc_1800236DD
0x180023671  lea     rdx, [rsp+270h+var_238]
0x180023676  lea     rcx, [rsp+270h+var_240]
0x18002367b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023680  lea     rdx, [rsp+270h+var_230]; void **
0x180023685  mov     [rsp+270h+var_230], 0
0x18002368e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023693  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023698  mov     ebx, eax
0x18002369a  test    eax, eax
0x18002369c  jns     short loc_1800236BE
0x18002369e  mov     edx, 12Eh; void *
0x1800236a3  mov     rcx, [rbp+178h]; this
0x1800236aa  mov     r9d, eax; char *
0x1800236ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236b2  lea     rcx, [rsp+270h+var_238]
0x1800236b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800236bc  jmp     short loc_1800236DD
0x1800236be  mov     rcx, [rsp+270h+var_230]
0x1800236c3  test    rcx, rcx
0x1800236c6  jz      short loc_18002370D
0x1800236c8  mov     [rdi], rcx
0x1800236cb  mov     eax, [rcx]
0x1800236cd  inc     eax
0x1800236cf  mov     [rcx], eax
0x1800236d1  lea     rcx, [rsp+270h+var_238]
0x1800236d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800236db  xor     ebx, ebx
0x1800236dd  lea     rcx, [rsp+270h+var_240]
0x1800236e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800236e7  mov     eax, ebx
0x1800236e9  mov     rcx, [rbp+170h+var_10]
0x1800236f0  xor     rcx, rsp; StackCookie
0x1800236f3  call    __security_check_cookie
0x1800236f8  lea     r11, [rsp+270h+var_s0]
0x180023700  mov     rbx, [r11+20h]
0x180023704  mov     rdi, [r11+28h]
0x180023708  mov     rsp, r11
0x18002370b  pop     rbp
0x18002370c  retn
0x18002370d  mov     r8, rdi
0x180023710  lea     rdx, [rsp+270h+var_240]
0x180023715  lea     rcx, [rsp+270h+Name]
0x18002371a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002371f  mov     ebx, eax
0x180023721  test    eax, eax
0x180023723  jns     short loc_1800236D1
0x180023725  mov     edx, 137h
0x18002372a  jmp     loc_1800236A3
```
