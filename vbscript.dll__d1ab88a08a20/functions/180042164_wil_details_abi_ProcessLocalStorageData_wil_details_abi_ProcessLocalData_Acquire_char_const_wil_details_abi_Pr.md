# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180042164`
- end: `0x1800422d0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180048cb8`

## callees

- `0x1800323e8`
- `0x180034c34`
- `0x180034f88`
- `0x180035484`
- `0x180040d58`
- `0x180042164`
- `0x1800422d8`
- `0x180043820`
- `0x180043c48`
- `0x1800490ec`
- `0x180079490`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18004219c`
- `KERNEL32!GetCurrentProcessId` at `0x18004219c`
- `KERNEL32!CreateMutexExW` at `0x1800421e7`
- `KERNEL32!CreateMutexExW` at `0x1800421e7`

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
0x180042164  mov     [rsp-8+arg_10], rbx
0x180042169  mov     [rsp-8+arg_18], rdi
0x18004216e  push    rbp
0x18004216f  lea     rbp, [rsp-170h]
0x180042177  sub     rsp, 270h
0x18004217e  mov     rax, cs:__security_cookie
0x180042185  xor     rax, rsp
0x180042188  mov     [rbp+170h+var_10], rax
0x18004218f  mov     rdi, rdx
0x180042192  mov     qword ptr [rdx], 0
0x180042199  mov     rbx, rcx
0x18004219c  call    cs:__imp_GetCurrentProcessId
0x1800421a3  nop     dword ptr [rax+rax+00h]
0x1800421a8  mov     [rsp+270h+var_248], rbx
0x1800421ad  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800421b4  mov     r9d, eax
0x1800421b7  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800421bf  mov     edx, 104h; unsigned __int64
0x1800421c4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800421c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800421ce  mov     r9d, 1F0001h; dwDesiredAccess
0x1800421d4  mov     [rsp+270h+var_240], 0
0x1800421dd  xor     r8d, r8d; dwFlags
0x1800421e0  lea     rdx, [rsp+270h+Name]; lpName
0x1800421e5  xor     ecx, ecx; lpMutexAttributes
0x1800421e7  call    cs:__imp_CreateMutexExW
0x1800421ee  nop     dword ptr [rax+rax+00h]
0x1800421f3  mov     rdx, rax
0x1800421f6  lea     rcx, [rsp+270h+var_240]
0x1800421fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180042200  cmp     [rsp+270h+var_240], 0
0x180042206  jnz     short loc_180042211
0x180042208  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004220d  mov     ebx, eax
0x18004220f  jmp     short loc_18004227D
0x180042211  lea     rdx, [rsp+270h+var_238]
0x180042216  lea     rcx, [rsp+270h+var_240]
0x18004221b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180042220  lea     rdx, [rsp+270h+var_230]; void **
0x180042225  mov     [rsp+270h+var_230], 0
0x18004222e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180042233  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180042238  mov     ebx, eax
0x18004223a  test    eax, eax
0x18004223c  jns     short loc_18004225E
0x18004223e  mov     edx, 12Eh; void *
0x180042243  mov     rcx, [rbp+178h]; this
0x18004224a  mov     r9d, eax; char *
0x18004224d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042252  lea     rcx, [rsp+270h+var_238]
0x180042257  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004225c  jmp     short loc_18004227D
0x18004225e  mov     rcx, [rsp+270h+var_230]
0x180042263  test    rcx, rcx
0x180042266  jz      short loc_1800422AE
0x180042268  mov     [rdi], rcx
0x18004226b  mov     eax, [rcx]
0x18004226d  inc     eax
0x18004226f  mov     [rcx], eax
0x180042271  lea     rcx, [rsp+270h+var_238]
0x180042276  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004227b  xor     ebx, ebx
0x18004227d  lea     rcx, [rsp+270h+var_240]
0x180042282  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180042287  mov     eax, ebx
0x180042289  mov     rcx, [rbp+170h+var_10]
0x180042290  xor     rcx, rsp; StackCookie
0x180042293  call    __security_check_cookie
0x180042298  lea     r11, [rsp+270h+var_s0]
0x1800422a0  mov     rbx, [r11+20h]
0x1800422a4  mov     rdi, [r11+28h]
0x1800422a8  mov     rsp, r11
0x1800422ab  pop     rbp
0x1800422ac  retn
0x1800422ae  mov     r8, rdi
0x1800422b1  lea     rdx, [rsp+270h+var_240]
0x1800422b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800422bb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800422c0  mov     ebx, eax
0x1800422c2  test    eax, eax
0x1800422c4  jns     short loc_180042271
0x1800422c6  mov     edx, 137h
0x1800422cb  jmp     loc_180042243
```
