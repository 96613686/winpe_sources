# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009600`
- end: `0x1800098d9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a158`

## callees

- `0x1800066f4`
- `0x180009600`
- `0x1800098f4`
- `0x180009eb8`
- `0x18000a904`
- `0x18000aff4`
- `0x18000c03c`
- `0x18000c478`
- `0x18000c590`
- `0x18000c860`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180009638`
- `KERNEL32!GetCurrentProcessId` at `0x180009638`
- `KERNEL32!CreateMutexExW` at `0x180009680`
- `KERNEL32!CreateMutexExW` at `0x180009680`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800096b7`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800096b7`
- `KERNEL32!ReleaseMutex` at `0x180009745`
- `KERNEL32!ReleaseMutex` at `0x1800097a8`
- `KERNEL32!ReleaseMutex` at `0x18000984b`
- `KERNEL32!ReleaseMutex` at `0x180009745`
- `KERNEL32!ReleaseMutex` at `0x1800097a8`
- `KERNEL32!ReleaseMutex` at `0x18000984b`
- `KERNEL32!CloseHandle` at `0x180009763`
- `KERNEL32!CloseHandle` at `0x1800097cd`
- `KERNEL32!CloseHandle` at `0x18000986c`
- `KERNEL32!CloseHandle` at `0x180009763`
- `KERNEL32!CloseHandle` at `0x1800097cd`
- `KERNEL32!CloseHandle` at `0x18000986c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // ebx
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v37[1] = (unsigned __int64)v12;
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v22;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_14;
  }
  v27 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hHandle,
          a2);
  v29 = v27;
  if ( v27 >= 0 )
  {
LABEL_14:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v23, v24);
    if ( hHandle && !CloseHandle(hHandle) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v25, v26);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)(unsigned int)v27, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v30, v31);
  if ( hHandle && !CloseHandle(hHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v32, v33);
  return v29;
}

```

## disassembly

```asm
0x180009600  mov     [rsp-8+arg_10], rbx
0x180009605  mov     [rsp-8+arg_18], rsi
0x18000960a  push    rbp
0x18000960b  push    rdi
0x18000960c  push    r14
0x18000960e  lea     rbp, [rsp-170h]
0x180009616  sub     rsp, 270h
0x18000961d  mov     rax, cs:__security_cookie
0x180009624  xor     rax, rsp
0x180009627  mov     [rbp+180h+var_20], rax
0x18000962e  mov     r14, rdx
0x180009631  mov     rbx, rcx
0x180009634  and     qword ptr [rdx], 0
0x180009638  call    cs:__imp_GetCurrentProcessId
0x18000963f  nop     dword ptr [rax+rax+00h]
0x180009644  mov     r9d, eax
0x180009647  mov     [rsp+280h+var_258], rbx
0x18000964c  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x180009654  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000965b  mov     edx, 104h; unsigned __int64
0x180009660  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009665  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000966a  and     [rsp+280h+hHandle], 0
0x180009670  mov     r9d, 1F0001h; dwDesiredAccess
0x180009676  xor     r8d, r8d; dwFlags
0x180009679  lea     rdx, [rsp+280h+Name]; lpName
0x18000967e  xor     ecx, ecx; lpMutexAttributes
0x180009680  call    cs:__imp_CreateMutexExW
0x180009687  nop     dword ptr [rax+rax+00h]
0x18000968c  mov     rdx, rax
0x18000968f  lea     rcx, [rsp+280h+hHandle]
0x180009694  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009699  mov     rbx, [rsp+280h+hHandle]
0x18000969e  test    rbx, rbx
0x1800096a1  jnz     short loc_1800096AE
0x1800096a3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800096a8  nop
0x1800096a9  jmp     loc_1800097EA
0x1800096ae  xor     r8d, r8d; bAlertable
0x1800096b1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800096b4  mov     rcx, rbx; hHandle
0x1800096b7  call    cs:__imp_WaitForSingleObjectEx
0x1800096be  nop     dword ptr [rax+rax+00h]
0x1800096c3  cmp     eax, 102h
0x1800096c8  jz      short loc_1800096DA
0x1800096ca  test    eax, 0FFFFFF7Fh
0x1800096cf  jnz     loc_180009895
0x1800096d5  mov     rdi, rbx
0x1800096d8  jmp     short loc_1800096DC
0x1800096da  xor     edi, edi
0x1800096dc  mov     [rsp+280h+var_240], rdi
0x1800096e1  and     [rsp+280h+var_248], 0
0x1800096e7  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800096ec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800096f1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800096f6  mov     esi, eax
0x1800096f8  test    eax, eax
0x1800096fa  jns     loc_180009782
0x180009700  mov     rcx, [rbp+188h]; this
0x180009707  mov     r9d, eax; char *
0x18000970a  mov     edx, 64h ; 'd'; void *
0x18000970f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009714  mov     rcx, [rbp+188h]; this
0x18000971b  mov     r9d, esi; char *
0x18000971e  mov     edx, 6Dh ; 'm'; void *
0x180009723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009728  mov     rcx, [rbp+188h]; this
0x18000972f  mov     r9d, esi; char *
0x180009732  mov     edx, 12Bh; void *
0x180009737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000973c  nop
0x18000973d  test    rdi, rdi
0x180009740  jz      short loc_180009760
0x180009742  mov     rcx, rdi; hMutex
0x180009745  call    cs:__imp_ReleaseMutex
0x18000974c  nop     dword ptr [rax+rax+00h]
0x180009751  mov     rcx, [rbp+188h]; this
0x180009758  test    eax, eax
0x18000975a  jz      loc_1800098A2
0x180009760  mov     rcx, rbx; hObject
0x180009763  call    cs:__imp_CloseHandle
0x18000976a  nop     dword ptr [rax+rax+00h]
0x18000976f  mov     rcx, [rbp+188h]; this
0x180009776  test    eax, eax
0x180009778  jz      loc_1800098AD
0x18000977e  mov     eax, esi
0x180009780  jmp     short loc_1800097EA
0x180009782  mov     rax, [rsp+280h+var_248]
0x180009787  lea     rcx, ds:0[rax*4]
0x18000978f  test    rcx, rcx
0x180009792  jz      short loc_180009812
0x180009794  mov     [r14], rcx
0x180009797  mov     ecx, [rcx]
0x180009799  inc     ecx
0x18000979b  mov     rax, [r14]
0x18000979e  mov     [rax], ecx
0x1800097a0  test    rdi, rdi
0x1800097a3  jz      short loc_1800097C3
0x1800097a5  mov     rcx, rdi; hMutex
0x1800097a8  call    cs:__imp_ReleaseMutex
0x1800097af  nop     dword ptr [rax+rax+00h]
0x1800097b4  mov     rcx, [rbp+188h]; this
0x1800097bb  test    eax, eax
0x1800097bd  jz      loc_1800098B8
0x1800097c3  mov     rcx, [rsp+280h+hHandle]; hObject
0x1800097c8  test    rcx, rcx
0x1800097cb  jz      short loc_1800097E8
0x1800097cd  call    cs:__imp_CloseHandle
0x1800097d4  nop     dword ptr [rax+rax+00h]
0x1800097d9  mov     rcx, [rbp+188h]; this
0x1800097e0  test    eax, eax
0x1800097e2  jz      loc_18000988A
0x1800097e8  xor     eax, eax
0x1800097ea  mov     rcx, [rbp+180h+var_20]
0x1800097f1  xor     rcx, rsp; StackCookie
0x1800097f4  call    __security_check_cookie
0x1800097f9  lea     r11, [rsp+280h+var_10]
0x180009801  mov     rbx, [r11+30h]
0x180009805  mov     rsi, [r11+38h]
0x180009809  mov     rsp, r11
0x18000980c  pop     r14
0x18000980e  pop     rdi
0x18000980f  pop     rbp
0x180009810  retn
0x180009812  mov     r8, r14
0x180009815  lea     rdx, [rsp+280h+hHandle]
0x18000981a  lea     rcx, [rsp+280h+Name]
0x18000981f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009824  mov     ebx, eax
0x180009826  test    eax, eax
0x180009828  jns     loc_1800097A0
0x18000982e  mov     rcx, [rbp+188h]; this
0x180009835  mov     r9d, eax; char *
0x180009838  mov     edx, 134h; void *
0x18000983d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009842  nop
0x180009843  test    rdi, rdi
0x180009846  jz      short loc_180009862
0x180009848  mov     rcx, rdi; hMutex
0x18000984b  call    cs:__imp_ReleaseMutex
0x180009852  nop     dword ptr [rax+rax+00h]
0x180009857  mov     rcx, [rbp+188h]; this
0x18000985e  test    eax, eax
0x180009860  jz      short loc_1800098C3
0x180009862  mov     rcx, [rsp+280h+hHandle]; hObject
0x180009867  test    rcx, rcx
0x18000986a  jz      short loc_180009883
0x18000986c  call    cs:__imp_CloseHandle
0x180009873  nop     dword ptr [rax+rax+00h]
0x180009878  mov     rcx, [rbp+188h]; this
0x18000987f  test    eax, eax
0x180009881  jz      short loc_1800098CE
0x180009883  mov     eax, ebx
0x180009885  jmp     loc_1800097EA
0x18000988a  mov     edx, 9DDh; void *
0x18000988f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009895  mov     rcx, [rbp+188h]; this
0x18000989c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800098a2  mov     edx, 9E7h; void *
0x1800098a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098ad  mov     edx, 9DDh; void *
0x1800098b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098b8  mov     edx, 9E7h; void *
0x1800098bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098c3  mov     edx, 9E7h; void *
0x1800098c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098ce  mov     edx, 9DDh; void *
0x1800098d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
