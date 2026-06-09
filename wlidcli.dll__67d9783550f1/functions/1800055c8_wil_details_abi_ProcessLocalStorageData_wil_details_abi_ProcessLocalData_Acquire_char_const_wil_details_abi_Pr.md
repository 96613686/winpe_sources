# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800055c8`
- end: `0x18000572e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800066e8`

## callees

- `0x180002da0`
- `0x180005130`
- `0x18000514c`
- `0x1800055c8`
- `0x1800063b8`
- `0x180007100`
- `0x1800083cc`
- `0x180008bb4`
- `0x180009038`
- `0x1800099a4`
- `0x180009cc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005645`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005645`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005600`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800055c8  mov     [rsp-8+arg_10], rbx
0x1800055cd  mov     [rsp-8+arg_18], rdi
0x1800055d2  push    rbp
0x1800055d3  lea     rbp, [rsp-170h]
0x1800055db  sub     rsp, 270h
0x1800055e2  mov     rax, cs:__security_cookie
0x1800055e9  xor     rax, rsp
0x1800055ec  mov     [rbp+170h+var_10], rax
0x1800055f3  mov     rdi, rdx
0x1800055f6  mov     qword ptr [rdx], 0
0x1800055fd  mov     rbx, rcx
0x180005600  call    cs:__imp_GetCurrentProcessId
0x180005606  mov     [rsp+270h+var_248], rbx
0x18000560b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005612  mov     r9d, eax
0x180005615  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000561d  mov     edx, 104h; unsigned __int64
0x180005622  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005627  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000562c  mov     r9d, 1F0001h; dwDesiredAccess
0x180005632  mov     [rsp+270h+var_240], 0
0x18000563b  xor     r8d, r8d; dwFlags
0x18000563e  lea     rdx, [rsp+270h+Name]; lpName
0x180005643  xor     ecx, ecx; lpMutexAttributes
0x180005645  call    cs:__imp_CreateMutexExW
0x18000564b  mov     rdx, rax
0x18000564e  lea     rcx, [rsp+270h+var_240]
0x180005653  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005658  cmp     [rsp+270h+var_240], 0
0x18000565e  jnz     short loc_180005669
0x180005660  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005665  mov     ebx, eax
0x180005667  jmp     short loc_1800056DC
0x180005669  lea     rdx, [rsp+270h+var_238]
0x18000566e  lea     rcx, [rsp+270h+var_240]
0x180005673  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005678  lea     rdx, [rsp+270h+var_230]; void **
0x18000567d  mov     [rsp+270h+var_230], 0
0x180005686  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000568b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005690  mov     ebx, eax
0x180005692  test    eax, eax
0x180005694  jns     short loc_1800056BD
0x180005696  mov     edx, 12Eh; void *
0x18000569b  mov     rcx, [rbp+178h]; this
0x1800056a2  lea     r8, aWil; "wil"
0x1800056a9  mov     r9d, eax; char *
0x1800056ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b1  lea     rcx, [rsp+270h+var_238]
0x1800056b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056bb  jmp     short loc_1800056DC
0x1800056bd  mov     rcx, [rsp+270h+var_230]
0x1800056c2  test    rcx, rcx
0x1800056c5  jz      short loc_18000570C
0x1800056c7  mov     [rdi], rcx
0x1800056ca  mov     eax, [rcx]
0x1800056cc  inc     eax
0x1800056ce  mov     [rcx], eax
0x1800056d0  lea     rcx, [rsp+270h+var_238]
0x1800056d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056da  xor     ebx, ebx
0x1800056dc  lea     rcx, [rsp+270h+var_240]
0x1800056e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800056e6  mov     eax, ebx
0x1800056e8  mov     rcx, [rbp+170h+var_10]
0x1800056ef  xor     rcx, rsp; StackCookie
0x1800056f2  call    __security_check_cookie
0x1800056f7  lea     r11, [rsp+270h+var_s0]
0x1800056ff  mov     rbx, [r11+20h]
0x180005703  mov     rdi, [r11+28h]
0x180005707  mov     rsp, r11
0x18000570a  pop     rbp
0x18000570b  retn
0x18000570c  mov     r8, rdi
0x18000570f  lea     rdx, [rsp+270h+var_240]
0x180005714  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180005719  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000571e  mov     ebx, eax
0x180005720  test    eax, eax
0x180005722  jns     short loc_1800056D0
0x180005724  mov     edx, 137h
0x180005729  jmp     loc_18000569B
```
