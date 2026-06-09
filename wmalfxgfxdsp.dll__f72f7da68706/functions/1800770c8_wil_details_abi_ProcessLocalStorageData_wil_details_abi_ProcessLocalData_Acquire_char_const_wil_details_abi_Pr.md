# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800770c8`
- end: `0x180077272`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180078064`

## callees

- `0x180014d58`
- `0x180015190`
- `0x180076a7c`
- `0x180076a98`
- `0x1800770c8`
- `0x180077dc4`
- `0x180078694`
- `0x1800793c0`
- `0x1800794d0`
- `0x180079958`
- `0x180079b10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180077100`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180077100`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180077145`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180077145`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800770c8  mov     [rsp-8+arg_10], rbx
0x1800770cd  mov     [rsp-8+arg_18], rdi
0x1800770d2  push    rbp
0x1800770d3  lea     rbp, [rsp-170h]
0x1800770db  sub     rsp, 270h
0x1800770e2  mov     rax, cs:__security_cookie
0x1800770e9  xor     rax, rsp
0x1800770ec  mov     [rbp+170h+var_10], rax
0x1800770f3  mov     rdi, rdx
0x1800770f6  mov     qword ptr [rdx], 0
0x1800770fd  mov     rbx, rcx
0x180077100  call    cs:__imp_GetCurrentProcessId
0x180077106  mov     [rsp+270h+var_248], rbx
0x18007710b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180077112  mov     r9d, eax
0x180077115  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18007711d  mov     edx, 104h; unsigned __int64
0x180077122  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180077127  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007712c  mov     r9d, 1F0001h; dwDesiredAccess
0x180077132  mov     [rsp+270h+var_240], 0
0x18007713b  xor     r8d, r8d; dwFlags
0x18007713e  lea     rdx, [rsp+270h+Name]; lpName
0x180077143  xor     ecx, ecx; lpMutexAttributes
0x180077145  call    cs:__imp_CreateMutexExW
0x18007714b  mov     rdx, rax
0x18007714e  lea     rcx, [rsp+270h+var_240]
0x180077153  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180077158  cmp     [rsp+270h+var_240], 0
0x18007715e  jnz     short loc_18007716C
0x180077160  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180077165  mov     ebx, eax
0x180077167  jmp     loc_18007721D
0x18007716c  lea     rdx, [rsp+270h+var_238]
0x180077171  lea     rcx, [rsp+270h+var_240]
0x180077176  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007717b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180077180  mov     [rsp+270h+var_230], 0
0x180077189  lea     rcx, [rsp+270h+Name]; pszSrc
0x18007718e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180077193  mov     ebx, eax
0x180077195  test    eax, eax
0x180077197  jns     short loc_1800771F6
0x180077199  mov     rcx, [rbp+178h]; this
0x1800771a0  lea     r8, aWil; "wil"
0x1800771a7  mov     r9d, eax; char *
0x1800771aa  mov     edx, 66h ; 'f'; void *
0x1800771af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771b4  mov     rcx, [rbp+178h]; this
0x1800771bb  lea     r8, aWil; "wil"
0x1800771c2  mov     r9d, ebx; char *
0x1800771c5  mov     edx, 6Fh ; 'o'; void *
0x1800771ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771cf  mov     r9d, ebx; char *
0x1800771d2  mov     edx, 12Eh; void *
0x1800771d7  mov     rcx, [rbp+178h]; this
0x1800771de  lea     r8, aWil; "wil"
0x1800771e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771ea  lea     rcx, [rsp+270h+var_238]
0x1800771ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800771f4  jmp     short loc_18007721D
0x1800771f6  mov     rax, [rsp+270h+var_230]
0x1800771fb  lea     rcx, ds:0[rax*4]
0x180077203  test    rcx, rcx
0x180077206  jz      short loc_18007724D
0x180077208  mov     [rdi], rcx
0x18007720b  mov     eax, [rcx]
0x18007720d  inc     eax
0x18007720f  mov     [rcx], eax
0x180077211  lea     rcx, [rsp+270h+var_238]
0x180077216  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007721b  xor     ebx, ebx
0x18007721d  lea     rcx, [rsp+270h+var_240]
0x180077222  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180077227  mov     eax, ebx
0x180077229  mov     rcx, [rbp+170h+var_10]
0x180077230  xor     rcx, rsp; StackCookie
0x180077233  call    __security_check_cookie
0x180077238  lea     r11, [rsp+270h+var_s0]
0x180077240  mov     rbx, [r11+20h]
0x180077244  mov     rdi, [r11+28h]
0x180077248  mov     rsp, r11
0x18007724b  pop     rbp
0x18007724c  retn
0x18007724d  mov     r8, rdi
0x180077250  lea     rdx, [rsp+270h+var_240]
0x180077255  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007725a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007725f  mov     ebx, eax
0x180077261  test    eax, eax
0x180077263  jns     short loc_180077211
0x180077265  mov     r9d, eax
0x180077268  mov     edx, 137h
0x18007726d  jmp     loc_1800771D7
```
