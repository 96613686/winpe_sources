# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180041c90`
- end: `0x180041e26`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `406`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180043164`

## callees

- `0x180003ac0`
- `0x18003c39c`
- `0x18003d270`
- `0x180041818`
- `0x180041838`
- `0x180041c90`
- `0x18004423c`
- `0x180045abc`
- `0x180048070`
- `0x180048974`
- `0x180048cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180041d13`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180041d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180041cc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180041cc8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v9; // rcx
  int v11; // eax
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( Pointer >= 0 )
    {
      v9 = v14;
      if ( v14 )
      {
        *a2 = v14;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v11,
            120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180041c90  mov     [rsp-8+arg_10], rbx
0x180041c95  mov     [rsp-8+arg_18], rdi
0x180041c9a  push    rbp
0x180041c9b  lea     rbp, [rsp-170h]
0x180041ca3  sub     rsp, 270h
0x180041caa  mov     rax, cs:__security_cookie
0x180041cb1  xor     rax, rsp
0x180041cb4  mov     [rbp+170h+var_10], rax
0x180041cbb  mov     rdi, rdx
0x180041cbe  mov     rbx, rcx
0x180041cc1  mov     qword ptr [rdx], 0
0x180041cc8  call    cs:__imp_GetCurrentProcessId
0x180041ccf  nop     dword ptr [rax+rax+00h]
0x180041cd4  mov     r9d, eax
0x180041cd7  mov     [rsp+270h+var_248], rbx
0x180041cdc  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180041ce4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180041ceb  mov     edx, 104h; unsigned __int64
0x180041cf0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041cf5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041cfa  mov     [rsp+270h+var_240], 0
0x180041d03  mov     r9d, 1F0001h; dwDesiredAccess
0x180041d09  xor     r8d, r8d; dwFlags
0x180041d0c  lea     rdx, [rsp+270h+Name]; lpName
0x180041d11  xor     ecx, ecx; lpMutexAttributes
0x180041d13  call    cs:__imp_CreateMutexExW
0x180041d1a  nop     dword ptr [rax+rax+00h]
0x180041d1f  mov     rdx, rax
0x180041d22  lea     rcx, [rsp+270h+var_240]
0x180041d27  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180041d2c  cmp     [rsp+270h+var_240], 0
0x180041d32  jnz     short loc_180041D3D
0x180041d34  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180041d39  mov     ebx, eax
0x180041d3b  jmp     short loc_180041DB4
0x180041d3d  lea     rdx, [rsp+270h+var_238]
0x180041d42  lea     rcx, [rsp+270h+var_240]
0x180041d47  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180041d4c  nop
0x180041d4d  mov     [rsp+270h+var_230], 0
0x180041d56  lea     rdx, [rsp+270h+var_230]; void **
0x180041d5b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041d60  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180041d65  mov     ebx, eax
0x180041d67  test    eax, eax
0x180041d69  jns     short loc_180041D94
0x180041d6b  mov     rcx, [rbp+178h]; this
0x180041d72  mov     r9d, eax; char *
0x180041d75  lea     r8, aWil; "wil"
0x180041d7c  mov     edx, 12Eh; void *
0x180041d81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041d86  nop
0x180041d87  lea     rcx, [rsp+270h+var_238]
0x180041d8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041d91  nop
0x180041d92  jmp     short loc_180041DB4
0x180041d94  mov     rcx, [rsp+270h+var_230]
0x180041d99  test    rcx, rcx
0x180041d9c  jz      short loc_180041DE5
0x180041d9e  mov     [rdi], rcx
0x180041da1  mov     eax, [rcx]
0x180041da3  inc     eax
0x180041da5  mov     [rcx], eax
0x180041da7  lea     rcx, [rsp+270h+var_238]
0x180041dac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041db1  nop
0x180041db2  xor     ebx, ebx
0x180041db4  lea     rcx, [rsp+270h+var_240]
0x180041db9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041dbe  mov     eax, ebx
0x180041dc0  mov     rcx, [rbp+170h+var_10]
0x180041dc7  xor     rcx, rsp; StackCookie
0x180041dca  call    __security_check_cookie
0x180041dcf  lea     r11, [rsp+270h+var_s0]
0x180041dd7  mov     rbx, [r11+20h]
0x180041ddb  mov     rdi, [r11+28h]
0x180041ddf  mov     rsp, r11
0x180041de2  pop     rbp
0x180041de3  retn
0x180041de5  mov     r8, rdi
0x180041de8  lea     rdx, [rsp+270h+var_240]
0x180041ded  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180041df2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180041df7  mov     ebx, eax
0x180041df9  test    eax, eax
0x180041dfb  jns     short loc_180041DA7
0x180041dfd  mov     rcx, [rbp+178h]; this
0x180041e04  mov     r9d, eax; char *
0x180041e07  lea     r8, aWil; "wil"
0x180041e0e  mov     edx, 137h; void *
0x180041e13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041e18  nop
0x180041e19  lea     rcx, [rsp+270h+var_238]
0x180041e1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180041e23  nop
0x180041e24  jmp     short loc_180041DB4
```
