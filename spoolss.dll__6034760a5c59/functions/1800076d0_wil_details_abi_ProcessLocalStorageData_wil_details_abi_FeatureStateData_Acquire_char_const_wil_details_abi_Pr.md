# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800076d0`
- end: `0x18000782f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800089c8`

## callees

- `0x180003ff8`
- `0x180004410`
- `0x180004b7c`
- `0x180005320`
- `0x180007310`
- `0x18000732c`
- `0x1800076d0`
- `0x18000ae48`
- `0x18000b21c`
- `0x18000bb80`
- `0x18000bdb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000774d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000774d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007708`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800076d0  mov     [rsp-8+arg_10], rbx
0x1800076d5  mov     [rsp-8+arg_18], rdi
0x1800076da  push    rbp
0x1800076db  lea     rbp, [rsp-170h]
0x1800076e3  sub     rsp, 270h
0x1800076ea  mov     rax, cs:__security_cookie
0x1800076f1  xor     rax, rsp
0x1800076f4  mov     [rbp+170h+var_10], rax
0x1800076fb  mov     rdi, rdx
0x1800076fe  mov     qword ptr [rdx], 0
0x180007705  mov     rbx, rcx
0x180007708  call    cs:__imp_GetCurrentProcessId
0x18000770e  mov     [rsp+270h+var_248], rbx
0x180007713  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000771a  mov     r9d, eax
0x18000771d  mov     [rsp+270h+var_250], 130h; int
0x180007725  mov     edx, 104h; unsigned __int64
0x18000772a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000772f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007734  mov     r9d, 1F0001h; dwDesiredAccess
0x18000773a  mov     [rsp+270h+var_240], 0
0x180007743  xor     r8d, r8d; dwFlags
0x180007746  lea     rdx, [rsp+270h+Name]; lpName
0x18000774b  xor     ecx, ecx; lpMutexAttributes
0x18000774d  call    cs:__imp_CreateMutexExW
0x180007753  mov     rdx, rax
0x180007756  lea     rcx, [rsp+270h+var_240]
0x18000775b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007760  cmp     [rsp+270h+var_240], 0
0x180007766  jnz     short loc_180007771
0x180007768  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000776d  mov     ebx, eax
0x18000776f  jmp     short loc_1800077DD
0x180007771  lea     rdx, [rsp+270h+var_238]
0x180007776  lea     rcx, [rsp+270h+var_240]
0x18000777b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180007780  lea     rdx, [rsp+270h+var_230]; void **
0x180007785  mov     [rsp+270h+var_230], 0
0x18000778e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007793  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180007798  mov     ebx, eax
0x18000779a  test    eax, eax
0x18000779c  jns     short loc_1800077BE
0x18000779e  mov     edx, 12Eh; void *
0x1800077a3  mov     rcx, [rbp+178h]; this
0x1800077aa  mov     r9d, eax; char *
0x1800077ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077b2  lea     rcx, [rsp+270h+var_238]
0x1800077b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800077bc  jmp     short loc_1800077DD
0x1800077be  mov     rcx, [rsp+270h+var_230]
0x1800077c3  test    rcx, rcx
0x1800077c6  jz      short loc_18000780D
0x1800077c8  mov     [rdi], rcx
0x1800077cb  mov     eax, [rcx]
0x1800077cd  inc     eax
0x1800077cf  mov     [rcx], eax
0x1800077d1  lea     rcx, [rsp+270h+var_238]
0x1800077d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800077db  xor     ebx, ebx
0x1800077dd  lea     rcx, [rsp+270h+var_240]
0x1800077e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800077e7  mov     eax, ebx
0x1800077e9  mov     rcx, [rbp+170h+var_10]
0x1800077f0  xor     rcx, rsp; StackCookie
0x1800077f3  call    __security_check_cookie
0x1800077f8  lea     r11, [rsp+270h+var_s0]
0x180007800  mov     rbx, [r11+20h]
0x180007804  mov     rdi, [r11+28h]
0x180007808  mov     rsp, r11
0x18000780b  pop     rbp
0x18000780c  retn
0x18000780d  mov     r8, rdi
0x180007810  lea     rdx, [rsp+270h+var_240]
0x180007815  lea     rcx, [rsp+270h+Name]
0x18000781a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000781f  mov     ebx, eax
0x180007821  test    eax, eax
0x180007823  jns     short loc_1800077D1
0x180007825  mov     edx, 137h
0x18000782a  jmp     loc_1800077A3
```
