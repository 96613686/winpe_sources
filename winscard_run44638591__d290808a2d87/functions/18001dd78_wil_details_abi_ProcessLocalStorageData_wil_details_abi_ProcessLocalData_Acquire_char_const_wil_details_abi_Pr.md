# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001dd78`
- end: `0x18001def3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ef6c`

## callees

- `0x18001be10`
- `0x18001d848`
- `0x18001d864`
- `0x18001dd78`
- `0x18001ecc8`
- `0x18001fb68`
- `0x18002100c`
- `0x180021ab8`
- `0x180021e4c`
- `0x180022614`
- `0x180022810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001ddf5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001ddf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ddb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ddb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001dd78  mov     [rsp-8+arg_10], rbx
0x18001dd7d  mov     [rsp-8+arg_18], rdi
0x18001dd82  push    rbp
0x18001dd83  lea     rbp, [rsp-170h]
0x18001dd8b  sub     rsp, 270h
0x18001dd92  mov     rax, cs:__security_cookie
0x18001dd99  xor     rax, rsp
0x18001dd9c  mov     [rbp+170h+var_10], rax
0x18001dda3  mov     rdi, rdx
0x18001dda6  mov     rbx, rcx
0x18001dda9  mov     qword ptr [rdx], 0
0x18001ddb0  call    cs:__imp_GetCurrentProcessId
0x18001ddb6  mov     r9d, eax
0x18001ddb9  mov     [rsp+270h+var_248], rbx
0x18001ddbe  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001ddc6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001ddcd  mov     edx, 104h; unsigned __int64
0x18001ddd2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ddd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dddc  mov     [rsp+270h+var_240], 0
0x18001dde5  mov     r9d, 1F0001h; dwDesiredAccess
0x18001ddeb  xor     r8d, r8d; dwFlags
0x18001ddee  lea     rdx, [rsp+270h+Name]; lpName
0x18001ddf3  xor     ecx, ecx; lpMutexAttributes
0x18001ddf5  call    cs:__imp_CreateMutexExW
0x18001ddfb  mov     rdx, rax
0x18001ddfe  lea     rcx, [rsp+270h+var_240]
0x18001de03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001de08  cmp     [rsp+270h+var_240], 0
0x18001de0e  jnz     short loc_18001DE19
0x18001de10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001de15  mov     ebx, eax
0x18001de17  jmp     short loc_18001DE89
0x18001de19  lea     rdx, [rsp+270h+var_238]
0x18001de1e  lea     rcx, [rsp+270h+var_240]
0x18001de23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001de28  nop
0x18001de29  mov     [rsp+270h+var_230], 0
0x18001de32  lea     rdx, [rsp+270h+var_230]; void **
0x18001de37  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001de3c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001de41  mov     ebx, eax
0x18001de43  test    eax, eax
0x18001de45  jns     short loc_18001DE69
0x18001de47  mov     rcx, [rbp+178h]; this
0x18001de4e  mov     r9d, eax; char *
0x18001de51  mov     edx, 12Eh; void *
0x18001de56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de5b  nop
0x18001de5c  lea     rcx, [rsp+270h+var_238]
0x18001de61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de66  nop
0x18001de67  jmp     short loc_18001DE89
0x18001de69  mov     rcx, [rsp+270h+var_230]
0x18001de6e  test    rcx, rcx
0x18001de71  jz      short loc_18001DEB9
0x18001de73  mov     [rdi], rcx
0x18001de76  mov     eax, [rcx]
0x18001de78  inc     eax
0x18001de7a  mov     [rcx], eax
0x18001de7c  lea     rcx, [rsp+270h+var_238]
0x18001de81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de86  nop
0x18001de87  xor     ebx, ebx
0x18001de89  lea     rcx, [rsp+270h+var_240]
0x18001de8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001de93  mov     eax, ebx
0x18001de95  mov     rcx, [rbp+170h+var_10]
0x18001de9c  xor     rcx, rsp; StackCookie
0x18001de9f  call    __security_check_cookie
0x18001dea4  lea     r11, [rsp+270h+var_s0]
0x18001deac  mov     rbx, [r11+20h]
0x18001deb0  mov     rdi, [r11+28h]
0x18001deb4  mov     rsp, r11
0x18001deb7  pop     rbp
0x18001deb8  retn
0x18001deb9  mov     r8, rdi
0x18001debc  lea     rdx, [rsp+270h+var_240]
0x18001dec1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dec6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001decb  mov     ebx, eax
0x18001decd  test    eax, eax
0x18001decf  jns     short loc_18001DE7C
0x18001ded1  mov     rcx, [rbp+178h]; this
0x18001ded8  mov     r9d, eax; char *
0x18001dedb  mov     edx, 137h; void *
0x18001dee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dee5  nop
0x18001dee6  lea     rcx, [rsp+270h+var_238]
0x18001deeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001def0  nop
0x18001def1  jmp     short loc_18001DE89
```
