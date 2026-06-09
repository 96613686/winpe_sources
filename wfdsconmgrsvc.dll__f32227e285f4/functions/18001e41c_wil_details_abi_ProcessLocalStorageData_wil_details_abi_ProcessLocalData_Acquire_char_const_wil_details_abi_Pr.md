# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001e41c`
- end: `0x18001e57b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001f464`

## callees

- `0x180002600`
- `0x18001e080`
- `0x18001e09c`
- `0x18001e41c`
- `0x18001f138`
- `0x18001fe88`
- `0x18002102c`
- `0x18002179c`
- `0x180021b78`
- `0x180022394`
- `0x180022658`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e454`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e499`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e499`

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
0x18001e41c  mov     [rsp-8+arg_10], rbx
0x18001e421  mov     [rsp-8+arg_18], rdi
0x18001e426  push    rbp
0x18001e427  lea     rbp, [rsp-170h]
0x18001e42f  sub     rsp, 270h
0x18001e436  mov     rax, cs:__security_cookie
0x18001e43d  xor     rax, rsp
0x18001e440  mov     [rbp+170h+var_10], rax
0x18001e447  mov     rdi, rdx
0x18001e44a  mov     qword ptr [rdx], 0
0x18001e451  mov     rbx, rcx
0x18001e454  call    cs:__imp_GetCurrentProcessId
0x18001e45a  mov     [rsp+270h+var_248], rbx
0x18001e45f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001e466  mov     r9d, eax
0x18001e469  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001e471  mov     edx, 104h; unsigned __int64
0x18001e476  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e47b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e480  mov     r9d, 1F0001h; dwDesiredAccess
0x18001e486  mov     [rsp+270h+var_240], 0
0x18001e48f  xor     r8d, r8d; dwFlags
0x18001e492  lea     rdx, [rsp+270h+Name]; lpName
0x18001e497  xor     ecx, ecx; lpMutexAttributes
0x18001e499  call    cs:__imp_CreateMutexExW
0x18001e49f  mov     rdx, rax
0x18001e4a2  lea     rcx, [rsp+270h+var_240]
0x18001e4a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001e4ac  cmp     [rsp+270h+var_240], 0
0x18001e4b2  jnz     short loc_18001E4BD
0x18001e4b4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e4b9  mov     ebx, eax
0x18001e4bb  jmp     short loc_18001E529
0x18001e4bd  lea     rdx, [rsp+270h+var_238]
0x18001e4c2  lea     rcx, [rsp+270h+var_240]
0x18001e4c7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001e4cc  lea     rdx, [rsp+270h+var_230]; void **
0x18001e4d1  mov     [rsp+270h+var_230], 0
0x18001e4da  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e4df  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001e4e4  mov     ebx, eax
0x18001e4e6  test    eax, eax
0x18001e4e8  jns     short loc_18001E50A
0x18001e4ea  mov     edx, 12Eh; void *
0x18001e4ef  mov     rcx, [rbp+178h]; this
0x18001e4f6  mov     r9d, eax; char *
0x18001e4f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4fe  lea     rcx, [rsp+270h+var_238]
0x18001e503  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e508  jmp     short loc_18001E529
0x18001e50a  mov     rcx, [rsp+270h+var_230]
0x18001e50f  test    rcx, rcx
0x18001e512  jz      short loc_18001E559
0x18001e514  mov     [rdi], rcx
0x18001e517  mov     eax, [rcx]
0x18001e519  inc     eax
0x18001e51b  mov     [rcx], eax
0x18001e51d  lea     rcx, [rsp+270h+var_238]
0x18001e522  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e527  xor     ebx, ebx
0x18001e529  lea     rcx, [rsp+270h+var_240]
0x18001e52e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e533  mov     eax, ebx
0x18001e535  mov     rcx, [rbp+170h+var_10]
0x18001e53c  xor     rcx, rsp; StackCookie
0x18001e53f  call    __security_check_cookie
0x18001e544  lea     r11, [rsp+270h+var_s0]
0x18001e54c  mov     rbx, [r11+20h]
0x18001e550  mov     rdi, [r11+28h]
0x18001e554  mov     rsp, r11
0x18001e557  pop     rbp
0x18001e558  retn
0x18001e559  mov     r8, rdi
0x18001e55c  lea     rdx, [rsp+270h+var_240]
0x18001e561  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e566  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001e56b  mov     ebx, eax
0x18001e56d  test    eax, eax
0x18001e56f  jns     short loc_18001E51D
0x18001e571  mov     edx, 137h
0x18001e576  jmp     loc_18001E4EF
```
