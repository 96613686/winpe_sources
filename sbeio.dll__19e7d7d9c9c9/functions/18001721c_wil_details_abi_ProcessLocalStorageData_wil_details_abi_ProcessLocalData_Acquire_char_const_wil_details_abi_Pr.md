# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001721c`
- end: `0x1800173b1`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001c8c4`

## callees

- `0x1800015f0`
- `0x1800050cc`
- `0x18001583c`
- `0x180015858`
- `0x18001721c`
- `0x18001c660`
- `0x18001d87c`
- `0x18002444c`
- `0x180026b08`
- `0x1800270d4`
- `0x1800272fc`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180017299`
- `KERNEL32!CreateMutexExW` at `0x180017299`
- `KERNEL32!GetCurrentProcessId` at `0x180017254`
- `KERNEL32!GetCurrentProcessId` at `0x180017254`

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
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001721c  mov     [rsp-8+arg_10], rbx
0x180017221  mov     [rsp-8+arg_18], rdi
0x180017226  push    rbp
0x180017227  lea     rbp, [rsp-170h]
0x18001722f  sub     rsp, 270h
0x180017236  mov     rax, cs:__security_cookie
0x18001723d  xor     rax, rsp
0x180017240  mov     [rbp+170h+var_10], rax
0x180017247  mov     rdi, rdx
0x18001724a  mov     qword ptr [rdx], 0
0x180017251  mov     rbx, rcx
0x180017254  call    cs:__imp_GetCurrentProcessId
0x18001725a  mov     [rsp+270h+var_248], rbx
0x18001725f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017266  mov     r9d, eax
0x180017269  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180017271  mov     edx, 104h; unsigned __int64
0x180017276  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001727b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017280  mov     r9d, 1F0001h; dwDesiredAccess
0x180017286  mov     [rsp+270h+var_240], 0
0x18001728f  xor     r8d, r8d; dwFlags
0x180017292  lea     rdx, [rsp+270h+Name]; lpName
0x180017297  xor     ecx, ecx; lpMutexAttributes
0x180017299  call    cs:__imp_CreateMutexExW
0x18001729f  mov     rdx, rax
0x1800172a2  lea     rcx, [rsp+270h+var_240]
0x1800172a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800172ac  cmp     [rsp+270h+var_240], 0
0x1800172b2  jnz     short loc_1800172C0
0x1800172b4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800172b9  mov     ebx, eax
0x1800172bb  jmp     loc_18001735C
0x1800172c0  lea     rdx, [rsp+270h+var_238]
0x1800172c5  lea     rcx, [rsp+270h+var_240]
0x1800172ca  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800172cf  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800172d4  mov     [rsp+270h+var_230], 0
0x1800172dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800172e2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800172e7  mov     ebx, eax
0x1800172e9  test    eax, eax
0x1800172eb  jns     short loc_180017335
0x1800172ed  mov     rcx, [rbp+178h]; this
0x1800172f4  mov     r9d, eax; char *
0x1800172f7  mov     edx, 66h ; 'f'; void *
0x1800172fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017301  mov     rcx, [rbp+178h]; this
0x180017308  mov     r9d, ebx; char *
0x18001730b  mov     edx, 6Fh ; 'o'; void *
0x180017310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017315  mov     r9d, ebx; char *
0x180017318  mov     edx, 12Eh; void *
0x18001731d  mov     rcx, [rbp+178h]; this
0x180017324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017329  lea     rcx, [rsp+270h+var_238]
0x18001732e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017333  jmp     short loc_18001735C
0x180017335  mov     rax, [rsp+270h+var_230]
0x18001733a  lea     rcx, ds:0[rax*4]
0x180017342  test    rcx, rcx
0x180017345  jz      short loc_18001738C
0x180017347  mov     [rdi], rcx
0x18001734a  mov     eax, [rcx]
0x18001734c  inc     eax
0x18001734e  mov     [rcx], eax
0x180017350  lea     rcx, [rsp+270h+var_238]
0x180017355  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001735a  xor     ebx, ebx
0x18001735c  lea     rcx, [rsp+270h+var_240]
0x180017361  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017366  mov     eax, ebx
0x180017368  mov     rcx, [rbp+170h+var_10]
0x18001736f  xor     rcx, rsp; StackCookie
0x180017372  call    __security_check_cookie
0x180017377  lea     r11, [rsp+270h+var_s0]
0x18001737f  mov     rbx, [r11+20h]
0x180017383  mov     rdi, [r11+28h]
0x180017387  mov     rsp, r11
0x18001738a  pop     rbp
0x18001738b  retn
0x18001738c  mov     r8, rdi
0x18001738f  lea     rdx, [rsp+270h+var_240]
0x180017394  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017399  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001739e  mov     ebx, eax
0x1800173a0  test    eax, eax
0x1800173a2  jns     short loc_180017350
0x1800173a4  mov     r9d, eax
0x1800173a7  mov     edx, 137h
0x1800173ac  jmp     loc_18001731D
```
