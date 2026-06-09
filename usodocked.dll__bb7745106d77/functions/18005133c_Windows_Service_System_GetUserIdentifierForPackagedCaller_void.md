# Windows::Service::System::GetUserIdentifierForPackagedCaller(void)

- ea: `0x18005133c`
- end: `0x180051670`
- name: `?GetUserIdentifierForPackagedCaller@System@Service@Windows@@UEAA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800460a0`

## callees

- `0x180007660`
- `0x18000856c`
- `0x18001ee04`
- `0x1800209fc`
- `0x180020ac0`
- `0x180023a18`
- `0x18005133c`
- `0x180051808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800513e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800513e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005146e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005146e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005140e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005140e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800513f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800513f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005157a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005157a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800515d7`
- `ntdll!RtlQueryPackageIdentity` at `0x1800514e0`
- `ntdll!RtlQueryPackageIdentity` at `0x1800514e0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051435`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051435`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005139d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005139d`
- `RPCRT4!RpcRevertToSelf` at `0x180051423`
- `RPCRT4!RpcRevertToSelf` at `0x180051423`
- `RPCRT4!RpcImpersonateClient` at `0x18005137c`
- `RPCRT4!RpcImpersonateClient` at `0x18005137c`

## string_xrefs

- `0x1800515fe`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x180051616`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x180051628`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x18005163a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x18005164c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x18005165e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Service::System::GetUserIdentifierForPackagedCaller(__int64 a1, __int64 a2)
{
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  unsigned __int64 v5; // r9
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  HANDLE v9; // rbx
  const char *v10; // r9
  const char *v11; // r9
  int v12; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int Pid; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[144]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[256]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v18 = a2;
  Pid = 0;
  hObject = 0;
  v3 = RpcImpersonateClient(0);
  if ( v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)(v3 | 1u),
      v14);
  v4 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  else
    v5 = (unsigned int)v4;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)v5,
      v14);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(hObject);
    SetLastError(LastError);
  }
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &hObject) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v8);
  RpcRevertToSelf();
  v9 = OpenProcess(0x400u, 0, Pid);
  v20 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v10);
  TokenHandle = 0;
  if ( !OpenProcessToken(v9, 8u, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v11);
  memset_0(v21, 0, 0x82u);
  memset_0(v22, 0, sizeof(v22));
  v18 = 256;
  *(_QWORD *)v19 = 130;
  v12 = RtlQueryPackageIdentity(TokenHandle, v22, &v18, v21);
  if ( v12 != -1073741275 && v12 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)(unsigned int)v12,
      (int)v19);
  *(_BYTE *)(a2 + 32) = 0;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  CloseHandle(v9);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a2;
}

```

## disassembly

```asm
0x18005133c  push    rbp
0x18005133e  push    rbx
0x18005133f  push    rsi
0x180051340  push    rdi
0x180051341  lea     rbp, [rsp-138h]
0x180051349  sub     rsp, 238h
0x180051350  mov     rax, cs:__security_cookie
0x180051357  xor     rax, rsp
0x18005135a  mov     [rbp+150h+var_30], rax
0x180051361  mov     rdi, rdx
0x180051364  mov     [rsp+250h+var_200], rdx
0x180051369  mov     [rsp+250h+Pid], 0
0x180051371  mov     [rsp+250h+hObject], 0
0x18005137a  xor     ecx, ecx; BindingHandle
0x18005137c  call    cs:__imp_RpcImpersonateClient
0x180051382  mov     rcx, [rbp+158h]; this
0x180051389  test    eax, eax
0x18005138b  jnz     loc_180051610
0x180051391  mov     [rsp+250h+var_21F], 1
0x180051396  lea     rdx, [rsp+250h+Pid]; Pid
0x18005139b  xor     ecx, ecx; Binding
0x18005139d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800513a3  test    eax, eax
0x1800513a5  jg      short loc_1800513AC
0x1800513a7  mov     r9d, eax
0x1800513aa  jmp     short loc_1800513B7
0x1800513ac  movzx   r9d, ax
0x1800513b0  or      r9d, 80070000h; char *
0x1800513b7  mov     rcx, [rbp+158h]; this
0x1800513be  test    eax, eax
0x1800513c0  jnz     loc_180051628
0x1800513c6  mov     rsi, [rsp+250h+hObject]
0x1800513cb  lea     rax, [rsi-1]
0x1800513cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800513d3  ja      short loc_1800513EE
0x1800513d5  call    cs:__imp_GetLastError
0x1800513db  mov     ebx, eax
0x1800513dd  mov     rcx, rsi; hObject
0x1800513e0  call    cs:__imp_CloseHandle
0x1800513e6  mov     ecx, ebx; dwErrCode
0x1800513e8  call    cs:__imp_SetLastError
0x1800513ee  mov     [rsp+250h+hObject], 0
0x1800513f7  call    cs:__imp_GetCurrentThread
0x1800513fd  lea     r9, [rsp+250h+hObject]; TokenHandle
0x180051402  mov     edx, 0Ch; DesiredAccess
0x180051407  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18005140b  mov     rcx, rax; ThreadHandle
0x18005140e  call    cs:__imp_OpenThreadToken
0x180051414  mov     rcx, [rbp+158h]; this
0x18005141b  test    eax, eax
0x18005141d  jz      loc_18005163A
0x180051423  call    cs:__imp_RpcRevertToSelf
0x180051429  mov     r8d, [rsp+250h+Pid]; dwProcessId
0x18005142e  xor     edx, edx; bInheritHandle
0x180051430  mov     ecx, 400h; dwDesiredAccess
0x180051435  call    cs:__imp_OpenProcess
0x18005143b  mov     rbx, rax
0x18005143e  mov     [rsp+250h+var_1E8], rax
0x180051443  test    rax, rax
0x180051446  setz    al
0x180051449  mov     rcx, [rbp+158h]; this
0x180051450  test    al, al
0x180051452  jnz     loc_18005164C
0x180051458  mov     [rsp+250h+TokenHandle], 0
0x180051461  lea     r8, [rsp+250h+TokenHandle]; TokenHandle
0x180051466  mov     edx, 8; DesiredAccess
0x18005146b  mov     rcx, rbx; ProcessHandle
0x18005146e  call    cs:__imp_OpenProcessToken
0x180051474  mov     rcx, [rbp+158h]; this
0x18005147b  test    eax, eax
0x18005147d  jz      loc_18005165E
0x180051483  xor     edx, edx; Val
0x180051485  mov     r8d, 82h; Size
0x18005148b  lea     rcx, [rbp+150h+var_1C0]; void *
0x18005148f  call    memset_0
0x180051494  mov     esi, 100h
0x180051499  mov     r8d, esi; Size
0x18005149c  xor     edx, edx; Val
0x18005149e  lea     rcx, [rbp+150h+var_130]; void *
0x1800514a2  call    memset_0
0x1800514a7  mov     [rsp+250h+var_200], rsi
0x1800514ac  mov     qword ptr [rsp+250h+var_1F0], 82h
0x1800514b5  mov     [rsp+250h+var_220], 0
0x1800514ba  lea     rax, [rsp+250h+var_220]
0x1800514bf  mov     [rsp+250h+var_228], rax
0x1800514c4  lea     rax, [rsp+250h+var_1F0]
0x1800514c9  mov     qword ptr [rsp+250h+var_230], rax; int
0x1800514ce  lea     r9, [rbp+150h+var_1C0]
0x1800514d2  lea     r8, [rsp+250h+var_200]
0x1800514d7  lea     rdx, [rbp+150h+var_130]
0x1800514db  mov     rcx, [rsp+250h+TokenHandle]
0x1800514e0  call    cs:__imp_RtlQueryPackageIdentity
0x1800514e6  cmp     eax, 0C0000225h
0x1800514eb  jz      loc_18005159F
0x1800514f1  mov     rcx, [rbp+158h]; this
0x1800514f8  test    eax, eax
0x1800514fa  js      loc_1800515FB
0x180051500  jnz     loc_18005159F
0x180051506  cmp     [rsp+250h+var_220], 0
0x18005150b  jz      loc_18005159F
0x180051511  mov     rdx, [rsp+250h+hObject]
0x180051516  lea     rcx, [rsp+250h+var_1E0]
0x18005151b  call    ?GetUserSidStringFromToken@UserMgrHelpers@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; Windows::UserMgrHelpers::GetUserSidStringFromToken(void *)
0x180051520  mov     rcx, rax
0x180051523  xorps   xmm0, xmm0
0x180051526  movups  xmmword ptr [rdi], xmm0
0x180051529  mov     qword ptr [rdi+10h], 0
0x180051531  mov     qword ptr [rdi+18h], 0
0x180051539  movups  xmm0, xmmword ptr [rax]
0x18005153c  movups  xmmword ptr [rdi], xmm0
0x18005153f  movups  xmm1, xmmword ptr [rax+10h]
0x180051543  movups  xmmword ptr [rdi+10h], xmm1
0x180051547  mov     qword ptr [rax+10h], 0
0x18005154f  mov     qword ptr [rax+18h], 7
0x180051557  xor     eax, eax
0x180051559  mov     [rcx], ax
0x18005155c  mov     byte ptr [rdi+20h], 1
0x180051560  lea     rcx, [rsp+250h+var_1E0]
0x180051565  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005156a  nop
0x18005156b  mov     rcx, [rsp+250h+TokenHandle]; hObject
0x180051570  lea     rax, [rcx-1]
0x180051574  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180051578  ja      short loc_180051581
0x18005157a  call    cs:__imp_CloseHandle
0x180051580  nop
0x180051581  test    rbx, rbx
0x180051584  jz      short loc_180051590
0x180051586  mov     rcx, rbx; hObject
0x180051589  call    cs:__imp_CloseHandle
0x18005158f  nop
0x180051590  mov     rcx, [rsp+250h+hObject]
0x180051595  lea     rax, [rcx-1]
0x180051599  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005159d  jmp     short loc_1800515D5
0x18005159f  mov     byte ptr [rdi+20h], 0
0x1800515a3  mov     rcx, [rsp+250h+TokenHandle]; hObject
0x1800515a8  lea     rax, [rcx-1]
0x1800515ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800515b0  ja      short loc_1800515B9
0x1800515b2  call    cs:__imp_CloseHandle
0x1800515b8  nop
0x1800515b9  test    rbx, rbx
0x1800515bc  jz      short loc_1800515C8
0x1800515be  mov     rcx, rbx; hObject
0x1800515c1  call    cs:__imp_CloseHandle
0x1800515c7  nop
0x1800515c8  mov     rcx, [rsp+250h+hObject]; hObject
0x1800515cd  lea     rdx, [rcx-1]
0x1800515d1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800515d5  ja      short loc_1800515DD
0x1800515d7  call    cs:__imp_CloseHandle
0x1800515dd  mov     rax, rdi
0x1800515e0  mov     rcx, [rbp+150h+var_30]
0x1800515e7  xor     rcx, rsp; StackCookie
0x1800515ea  call    __security_check_cookie
0x1800515ef  add     rsp, 238h
0x1800515f6  pop     rdi
0x1800515f7  pop     rsi
0x1800515f8  pop     rbx
0x1800515f9  pop     rbp
0x1800515fa  retn
0x1800515fb  mov     r9d, eax; char *
0x1800515fe  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180051605  mov     edx, 105h; void *
0x18005160a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180051610  or      eax, 1
0x180051613  mov     r9d, eax; char *
0x180051616  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005161d  mov     edx, 0EAh; void *
0x180051622  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051628  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005162f  mov     edx, 0EEh; void *
0x180051634  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005163a  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180051641  mov     edx, 0F0h; void *
0x180051646  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005164c  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180051653  mov     edx, 0F5h; void *
0x180051658  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005165e  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180051665  mov     edx, 0F9h; void *
0x18005166a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
