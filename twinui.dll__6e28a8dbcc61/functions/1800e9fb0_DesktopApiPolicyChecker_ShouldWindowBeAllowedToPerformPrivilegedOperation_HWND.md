# DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND__ *)

- ea: `0x1800e9fb0`
- end: `0x1800ea22f`
- name: `?ShouldWindowBeAllowedToPerformPrivilegedOperation@DesktopApiPolicyChecker@@YAJPEAUHWND__@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(HWND hWnd, HWND)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802106b0`
- `0x180210db0`

## callees

- `0x18003c5e4`
- `0x1800456b0`
- `0x1800542a8`
- `0x18009f240`
- `0x1800a7788`
- `0x1800ac904`
- `0x1800e9fb0`
- `0x1800ead54`
- `0x180109a7c`
- `0x18020ad0c`
- `0x18036eb14`
- `0x18036ec84`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ea14b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ea14b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ea166`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ea166`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800ea17c`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800ea17c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea0dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea1e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea0dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea1e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea209`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800e9fd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800ea1a8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800e9fd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800ea1a8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1800ea13e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1800ea13e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800ea12d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800ea12d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1800ea1d7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1800ea1d7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800ea016`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800ea016`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DesktopApiPolicyChecker::ShouldWindowBeAllowedToPerformPrivilegedOperation(HWND hWnd, HWND a2)
{
  const char *v3; // r9
  int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int Policy; // eax
  struct IUnknown *v10; // rbx
  unsigned __int16 **v11; // r8
  int AppIdFromProcessId; // eax
  int *v13; // r8
  int LastError; // edi
  int *v15; // r8
  __int64 v16; // rdx
  const unsigned __int16 *v17; // rdx
  HWND ForegroundWindow; // rsi
  HWND Ancestor; // r14
  DWORD v20; // r15d
  HANDLE v21; // rax
  const char *v22; // r9
  __int64 v23; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-28h] BYREF
  HANDLE v25; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  char v28; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF
  WINBOOL pbDebuggerPresent; // [rsp+90h] [rbp+40h] BYREF
  DWORD v32; // [rsp+98h] [rbp+48h] BYREF

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13,
             (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
             v3);
  v23 = 0;
  v26 = &v23;
  v27 = 0;
  v28 = 1;
  v5 = UMgrOpenProcessTokenForQuery(dwProcessId, &v27);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v26);
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 24;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
      (const char *)v7,
      v23);
LABEL_34:
    Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v23);
    return (unsigned int)v5;
  }
  pbDebuggerPresent = 0;
  Policy = AppModelPolicy_GetPolicy(v23, v6, &pbDebuggerPresent);
  v5 = Policy;
  if ( Policy < 0 )
  {
    v7 = (unsigned int)Policy;
    v8 = 27;
    goto LABEL_7;
  }
  v10 = 0;
  pv = 0;
  if ( pbDebuggerPresent == 196608
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0),
        AppIdFromProcessId = UserAwareCallerIdentity::GetAppIdFromProcessId(dwProcessId, (unsigned int)&pv, v11),
        v10 = (struct IUnknown *)pv,
        AppIdFromProcessId < 0) )
  {
    ForegroundWindow = GetForegroundWindow();
    Ancestor = GetAncestor(hWnd, 2u);
    v20 = dwProcessId;
    pbDebuggerPresent = IsDebuggerPresent();
    if ( pbDebuggerPresent )
      goto LABEL_35;
    v21 = OpenProcess(0x1000u, 0, v20);
    v25 = v21;
    if ( v21 && !CheckRemoteDebuggerPresent(v21, &pbDebuggerPresent) )
      pbDebuggerPresent = 0;
    CAutoHandle<void *>::~CAutoHandle<void *>(&v25);
    if ( pbDebuggerPresent || Ancestor == ForegroundWindow )
      goto LABEL_35;
    v32 = pbDebuggerPresent;
    if ( !GetWindowThreadProcessId(ForegroundWindow, &v32) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x43,
                    (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
                    v22);
      goto LABEL_13;
    }
    if ( dwProcessId == v32 && IsWindowVisible(hWnd) )
      goto LABEL_35;
    goto LABEL_31;
  }
  pbDebuggerPresent = 0;
  LastError = CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(
                (CallerIdentity::ApiPolicyChecker *)pv,
                (const unsigned __int16 *)&pbDebuggerPresent,
                v13);
  if ( LastError < 0 )
  {
    v16 = 33;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"Internal\\Shell\\Inc\\DesktopApiPolicyChecker.h",
      (const char *)(unsigned int)LastError,
      v23);
LABEL_13:
    if ( v10 )
      CoTaskMemFree(v10);
    v5 = LastError;
    goto LABEL_34;
  }
  if ( !pbDebuggerPresent )
  {
    pbDebuggerPresent = 0;
    if ( (int)CallerIdentity::ApiPolicyChecker::IsApplicationForeground(
                (CallerIdentity::ApiPolicyChecker *)v10,
                (const unsigned __int16 *)&pbDebuggerPresent,
                v15) < 0
      || pbDebuggerPresent )
    {
      LastError = CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(
                    v10,
                    v17);
      if ( LastError < 0 )
      {
        v16 = 43;
        goto LABEL_12;
      }
      goto LABEL_35;
    }
LABEL_31:
    if ( v10 )
      CoTaskMemFree(v10);
    v5 = -2147019873;
    goto LABEL_34;
  }
LABEL_35:
  if ( v10 )
    CoTaskMemFree(v10);
  Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x1800e9fb0  mov     [rsp-28h+arg_0], rbx
0x1800e9fb5  push    rbp
0x1800e9fb6  push    rsi
0x1800e9fb7  push    rdi
0x1800e9fb8  push    r14
0x1800e9fba  push    r15
0x1800e9fbc  mov     rbp, rsp
0x1800e9fbf  sub     rsp, 50h
0x1800e9fc3  mov     rdi, rcx
0x1800e9fc6  mov     [rbp+dwProcessId], 0
0x1800e9fcd  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800e9fd1  call    cs:__imp_GetWindowThreadProcessId
0x1800e9fd7  test    eax, eax
0x1800e9fd9  jnz     short loc_1800E9FF3
0x1800e9fdb  mov     rcx, [rbp+28h]; this
0x1800e9fdf  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x1800e9fe6  lea     edx, [rax+13h]; void *
0x1800e9fe9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e9fee  jmp     loc_1800EA21B
0x1800e9ff3  mov     [rbp+var_30], 0
0x1800e9ffb  lea     rax, [rbp+var_30]
0x1800e9fff  mov     [rbp+var_18], rax
0x1800ea003  mov     [rbp+var_10], 0
0x1800ea00b  mov     [rbp+var_8], 1
0x1800ea00f  lea     rdx, [rbp+var_10]
0x1800ea013  mov     ecx, [rbp+dwProcessId]
0x1800ea016  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x1800ea01c  mov     ebx, eax
0x1800ea01e  lea     rcx, [rbp+var_18]
0x1800ea022  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ea027  test    ebx, ebx
0x1800ea029  jns     short loc_1800EA035
0x1800ea02b  mov     r9d, ebx
0x1800ea02e  mov     edx, 18h
0x1800ea033  jmp     short loc_1800EA057
0x1800ea035  mov     [rbp+pbDebuggerPresent], 0
0x1800ea03c  lea     r8, [rbp+pbDebuggerPresent]
0x1800ea040  mov     rcx, [rbp+var_30]
0x1800ea044  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x1800ea049  mov     ebx, eax
0x1800ea04b  test    eax, eax
0x1800ea04d  jns     short loc_1800EA06C
0x1800ea04f  mov     r9d, eax; char *
0x1800ea052  mov     edx, 1Bh; void *
0x1800ea057  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x1800ea05e  mov     rcx, [rbp+28h]; this
0x1800ea062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea067  jmp     loc_1800EA1F4
0x1800ea06c  xor     ebx, ebx
0x1800ea06e  mov     [rbp+pv], rbx
0x1800ea072  cmp     [rbp+pbDebuggerPresent], 30000h
0x1800ea079  jz      loc_1800EA12D
0x1800ea07f  xor     edx, edx
0x1800ea081  lea     rcx, [rbp+pv]
0x1800ea085  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ea08a  lea     rdx, [rbp+pv]; unsigned int
0x1800ea08e  mov     ecx, [rbp+dwProcessId]; dwProcessId
0x1800ea091  call    ?GetAppIdFromProcessId@UserAwareCallerIdentity@@YAJKPEAPEAG@Z; UserAwareCallerIdentity::GetAppIdFromProcessId(ulong,ushort * *)
0x1800ea096  mov     rbx, [rbp+pv]
0x1800ea09a  test    eax, eax
0x1800ea09c  js      loc_1800EA12D
0x1800ea0a2  mov     [rbp+pbDebuggerPresent], 0
0x1800ea0a9  lea     rdx, [rbp+pbDebuggerPresent]; unsigned __int16 *
0x1800ea0ad  mov     rcx, rbx; this
0x1800ea0b0  call    ?IsAppBeingDebugged@ApiPolicyChecker@CallerIdentity@@YAJPEBGPEAH@Z; CallerIdentity::ApiPolicyChecker::IsAppBeingDebugged(ushort const *,int *)
0x1800ea0b5  mov     edi, eax
0x1800ea0b7  test    eax, eax
0x1800ea0b9  jns     short loc_1800EA0E9
0x1800ea0bb  mov     edx, 21h ; '!'; void *
0x1800ea0c0  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x1800ea0c7  mov     r9d, edi; char *
0x1800ea0ca  mov     rcx, [rbp+28h]; this
0x1800ea0ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea0d3  nop
0x1800ea0d4  test    rbx, rbx
0x1800ea0d7  jz      short loc_1800EA0E2
0x1800ea0d9  mov     rcx, rbx; pv
0x1800ea0dc  call    cs:__imp_CoTaskMemFree
0x1800ea0e2  mov     ebx, edi
0x1800ea0e4  jmp     loc_1800EA1F4
0x1800ea0e9  cmp     [rbp+pbDebuggerPresent], 0
0x1800ea0ed  jnz     loc_1800EA201
0x1800ea0f3  mov     [rbp+pbDebuggerPresent], 0
0x1800ea0fa  lea     rdx, [rbp+pbDebuggerPresent]; unsigned __int16 *
0x1800ea0fe  mov     rcx, rbx; this
0x1800ea101  call    ?IsApplicationForeground@ApiPolicyChecker@CallerIdentity@@YAJPEBGPEAH@Z; CallerIdentity::ApiPolicyChecker::IsApplicationForeground(ushort const *,int *)
0x1800ea106  test    eax, eax
0x1800ea108  js      short loc_1800EA114
0x1800ea10a  cmp     [rbp+pbDebuggerPresent], 0
0x1800ea10e  jz      loc_1800EA1E1
0x1800ea114  mov     rcx, rbx; this
0x1800ea117  call    ?ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground@ApiPolicyChecker@CallerIdentity@@YAJPEBG@Z; CallerIdentity::ApiPolicyChecker::ShouldAppBeAllowedToPerformPrivilegedOperationBasedOnForeground(ushort const *)
0x1800ea11c  mov     edi, eax
0x1800ea11e  test    eax, eax
0x1800ea120  jns     loc_1800EA201
0x1800ea126  mov     edx, 2Bh ; '+'
0x1800ea12b  jmp     short loc_1800EA0C0
0x1800ea12d  call    cs:__imp_GetForegroundWindow
0x1800ea133  mov     rsi, rax
0x1800ea136  mov     edx, 2; gaFlags
0x1800ea13b  mov     rcx, rdi; hwnd
0x1800ea13e  call    cs:__imp_GetAncestor
0x1800ea144  mov     r14, rax
0x1800ea147  mov     r15d, [rbp+dwProcessId]
0x1800ea14b  call    cs:__imp_IsDebuggerPresent
0x1800ea151  mov     [rbp+pbDebuggerPresent], eax
0x1800ea154  test    eax, eax
0x1800ea156  jnz     loc_1800EA201
0x1800ea15c  mov     r8d, r15d; dwProcessId
0x1800ea15f  xor     edx, edx; bInheritHandle
0x1800ea161  mov     ecx, 1000h; dwDesiredAccess
0x1800ea166  call    cs:__imp_OpenProcess
0x1800ea16c  mov     [rbp+var_20], rax
0x1800ea170  test    rax, rax
0x1800ea173  jz      short loc_1800EA189
0x1800ea175  lea     rdx, [rbp+pbDebuggerPresent]; pbDebuggerPresent
0x1800ea179  mov     rcx, rax; hProcess
0x1800ea17c  call    cs:__imp_CheckRemoteDebuggerPresent
0x1800ea182  test    eax, eax
0x1800ea184  jnz     short loc_1800EA189
0x1800ea186  mov     [rbp+pbDebuggerPresent], eax
0x1800ea189  lea     rcx, [rbp+var_20]
0x1800ea18d  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800ea192  mov     eax, [rbp+pbDebuggerPresent]
0x1800ea195  test    eax, eax
0x1800ea197  jnz     short loc_1800EA201
0x1800ea199  cmp     r14, rsi
0x1800ea19c  jz      short loc_1800EA201
0x1800ea19e  mov     [rbp+arg_18], eax
0x1800ea1a1  lea     rdx, [rbp+arg_18]; lpdwProcessId
0x1800ea1a5  mov     rcx, rsi; hWnd
0x1800ea1a8  call    cs:__imp_GetWindowThreadProcessId
0x1800ea1ae  test    eax, eax
0x1800ea1b0  jnz     short loc_1800EA1CC
0x1800ea1b2  mov     rcx, [rbp+28h]; this
0x1800ea1b6  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\DesktopApiPolicyC"...
0x1800ea1bd  lea     edx, [rax+43h]; void *
0x1800ea1c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ea1c5  mov     edi, eax
0x1800ea1c7  jmp     loc_1800EA0D4
0x1800ea1cc  mov     eax, [rbp+arg_18]
0x1800ea1cf  cmp     [rbp+dwProcessId], eax
0x1800ea1d2  jnz     short loc_1800EA1E1
0x1800ea1d4  mov     rcx, rdi; hWnd
0x1800ea1d7  call    cs:__imp_IsWindowVisible
0x1800ea1dd  test    eax, eax
0x1800ea1df  jnz     short loc_1800EA201
0x1800ea1e1  test    rbx, rbx
0x1800ea1e4  jz      short loc_1800EA1EF
0x1800ea1e6  mov     rcx, rbx; pv
0x1800ea1e9  call    cs:__imp_CoTaskMemFree
0x1800ea1ef  mov     ebx, 8007139Fh
0x1800ea1f4  lea     rcx, [rbp+var_30]
0x1800ea1f8  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ea1fd  mov     eax, ebx
0x1800ea1ff  jmp     short loc_1800EA21B
0x1800ea201  test    rbx, rbx
0x1800ea204  jz      short loc_1800EA210
0x1800ea206  mov     rcx, rbx; pv
0x1800ea209  call    cs:__imp_CoTaskMemFree
0x1800ea20f  nop
0x1800ea210  lea     rcx, [rbp+var_30]
0x1800ea214  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ea219  xor     eax, eax
0x1800ea21b  mov     rbx, [rsp+50h+arg_0]
0x1800ea223  add     rsp, 50h
0x1800ea227  pop     r15
0x1800ea229  pop     r14
0x1800ea22b  pop     rdi
0x1800ea22c  pop     rsi
0x1800ea22d  pop     rbp
0x1800ea22e  retn
```
