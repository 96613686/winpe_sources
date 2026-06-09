# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007614`
- end: `0x180007757`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014c24`

## callees

- `0x1800070e8`
- `0x180007590`
- `0x180007614`
- `0x180008910`
- `0x180017674`
- `0x180017f84`
- `0x180017fa0`
- `0x18001ff00`
- `0x1800218d4`
- `0x180021fa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007688`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000764c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000764c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v4; // rcx
  int Pointer; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  HANDLE Mutex; // [rsp+30h] [rbp-D0h] BYREF
  void *v11; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v4);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Mutex,
    v12);
  v11 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v11);
  v7 = Pointer;
  if ( Pointer < 0 )
  {
    v8 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    goto LABEL_8;
  }
  v9 = v11;
  if ( v11 )
  {
    *a2 = v11;
    ++*v9;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    v7 = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 311;
      goto LABEL_11;
    }
  }
  v7 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Mutex);
  return v7;
}

```

## disassembly

```asm
0x180007614  mov     [rsp-8+arg_10], rbx
0x180007619  mov     [rsp-8+arg_18], rdi
0x18000761e  push    rbp
0x18000761f  lea     rbp, [rsp-170h]
0x180007627  sub     rsp, 270h
0x18000762e  mov     rax, cs:__security_cookie
0x180007635  xor     rax, rsp
0x180007638  mov     [rbp+170h+var_10], rax
0x18000763f  mov     rdi, rdx
0x180007642  mov     qword ptr [rdx], 0
0x180007649  mov     rbx, rcx
0x18000764c  call    cs:__imp_GetCurrentProcessId
0x180007652  mov     [rsp+270h+var_248], rbx
0x180007657  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000765e  mov     r9d, eax
0x180007661  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180007669  mov     edx, 104h; unsigned __int64
0x18000766e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007673  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007678  mov     r9d, 1F0001h; dwDesiredAccess
0x18000767e  lea     rdx, [rsp+270h+Name]; lpName
0x180007683  xor     r8d, r8d; dwFlags
0x180007686  xor     ecx, ecx; lpMutexAttributes
0x180007688  call    cs:__imp_CreateMutexExW
0x18000768e  mov     [rsp+270h+var_240], rax
0x180007693  test    rax, rax
0x180007696  jnz     short loc_18000769F
0x180007698  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000769d  jmp     short loc_1800076FE
0x18000769f  lea     rdx, [rsp+270h+var_230]
0x1800076a4  lea     rcx, [rsp+270h+var_240]
0x1800076a9  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800076ae  lea     rdx, [rsp+270h+var_238]; void **
0x1800076b3  mov     [rsp+270h+var_238], 0
0x1800076bc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800076c1  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800076c6  mov     ebx, eax
0x1800076c8  test    eax, eax
0x1800076ca  jns     short loc_1800076D3
0x1800076cc  mov     edx, 12Eh
0x1800076d1  jmp     short loc_18000773F
0x1800076d3  mov     rcx, [rsp+270h+var_238]
0x1800076d8  test    rcx, rcx
0x1800076db  jz      short loc_180007722
0x1800076dd  mov     [rdi], rcx
0x1800076e0  mov     eax, [rcx]
0x1800076e2  inc     eax
0x1800076e4  mov     [rcx], eax
0x1800076e6  xor     ebx, ebx
0x1800076e8  lea     rcx, [rsp+270h+var_230]
0x1800076ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800076f2  lea     rcx, [rsp+270h+var_240]
0x1800076f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800076fc  mov     eax, ebx
0x1800076fe  mov     rcx, [rbp+170h+var_10]
0x180007705  xor     rcx, rsp; StackCookie
0x180007708  call    __security_check_cookie
0x18000770d  lea     r11, [rsp+270h+var_s0]
0x180007715  mov     rbx, [r11+20h]
0x180007719  mov     rdi, [r11+28h]
0x18000771d  mov     rsp, r11
0x180007720  pop     rbp
0x180007721  retn
0x180007722  mov     r8, rdi
0x180007725  lea     rdx, [rsp+270h+var_240]
0x18000772a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000772f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180007734  mov     ebx, eax
0x180007736  test    eax, eax
0x180007738  jns     short loc_1800076E6
0x18000773a  mov     edx, 137h; void *
0x18000773f  mov     rcx, [rbp+178h]; this
0x180007746  lea     r8, aWil; "wil"
0x18000774d  mov     r9d, eax; char *
0x180007750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007755  jmp     short loc_1800076E8
```
