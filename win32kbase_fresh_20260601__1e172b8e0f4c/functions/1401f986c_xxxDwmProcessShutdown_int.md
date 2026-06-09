# xxxDwmProcessShutdown(int)

- ea: `0x1401f986c`
- end: `0x1401f9aad`
- name: `?xxxDwmProcessShutdown@@YAJH@Z`
- size: `577`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002edcc`
- `0x1401de7b0`

## callees

- `0x140012c80`
- `0x140012dc0`
- `0x140028fe0`
- `0x1400290c0`
- `0x14002a0e4`
- `0x140073a50`
- `0x140076ef0`
- `0x140170150`
- `0x140180b08`
- `0x140183ca4`
- `0x1401aa4fc`
- `0x1401b21a0`
- `0x1401f986c`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1401f9942`
- `ntoskrnl!KeBugCheckEx` at `0x1401f9942`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f99b2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f99b2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f9a7e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f9a7e`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9a53`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9a53`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f989b`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f989b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f98f7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f98f7`
- `WIN32K!W32GetUserSessionState` at `0x1401f9887`
- `WIN32K!W32GetUserSessionState` at `0x1401f9959`
- `WIN32K!W32GetUserSessionState` at `0x1401f9887`
- `WIN32K!W32GetUserSessionState` at `0x1401f9959`

## pseudocode

```c
__int64 __fastcall xxxDwmProcessShutdown(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  unsigned int v4; // ebx
  __int64 UserSessionState; // rsi
  unsigned int v6; // r14d
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(_QWORD); // rax
  unsigned int Count; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v21; // rax
  _QWORD *v22; // rbx
  void *v23; // rcx
  HANDLE CurrentProcessId; // rax
  __int64 v26; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v4 = a1;
  v26 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  if ( (int)DxgkGetSessionTokenManager(&v26) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 104LL))(v26);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 168LL))(v26);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  }
  v6 = 0;
  if ( !*(_DWORD *)(UserSessionState + 70552) )
    v6 = v4;
  if ( (int)IsxxxDwmStopRedirectionSupported() >= 0 )
  {
    v8 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v7) + 48) + 3824LL);
    if ( v8 )
      v3 = v8(v4);
    else
      v3 = -1073741637;
  }
  Count = AtomicExecutionCheck::GetCount();
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  UserSessionSwitchLeaveCritWithNonPaged(v11, v10, v12);
  GreSfmCleanupPresentHistory();
  v16 = W32GetUserSessionState(v14, v13, v15);
  v17 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v16,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v16 + 16) = v17;
  v19 = v17;
  if ( v17 )
  {
    v18 = 0;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v17 + 520), 0, 0) & 0x1000000) != 0
      && *(char *)(v17 + 1360) >= 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
        {
          while ( 1 )
          {
            v22 = *(_QWORD **)(v16 + 19544);
            if ( !v22 )
              break;
            *(_QWORD *)(v16 + 19544) = v22[2];
            v21 = *v22;
            v22[2] = 0;
            if ( !*(_DWORD *)(v21 + 8) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            HMUnlockObject(*v22);
          }
          DestroyDeferredUnlockObjectAssignmentList(v16 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v16 + 19560);
        }
      }
    }
  }
  GreLockDwmState(v18, v19);
  SetDwmApiPort(0);
  v23 = *(void **)(UserSessionState + 70544);
  if ( v23 )
  {
    ObfDereferenceObject(v23);
    *(_QWORD *)(UserSessionState + 70544) = 0;
  }
  GreUnlockDwmState();
  *(_DWORD *)(UserSessionState + 70552) = 0;
  if ( v6 )
  {
    CurrentProcessId = PsGetCurrentProcessId();
    xxxDwmControl(1036, CurrentProcessId);
  }
  return v3;
}

```

## disassembly

```asm
0x1401f986c  mov     [rsp+arg_10], rbx
0x1401f9871  mov     [rsp+arg_18], rbp
0x1401f9876  push    rsi
0x1401f9877  push    rdi
0x1401f9878  push    r14
0x1401f987a  sub     rsp, 30h
0x1401f987e  xor     ebp, ebp
0x1401f9880  mov     ebx, ecx
0x1401f9882  mov     [rsp+48h+arg_8], rbp
0x1401f9887  call    cs:__imp_W32GetUserSessionState
0x1401f988e  nop     dword ptr [rax+rax+00h]
0x1401f9893  lea     rcx, [rsp+48h+arg_8]
0x1401f9898  mov     rsi, rax
0x1401f989b  call    cs:__imp_DxgkGetSessionTokenManager
0x1401f98a2  nop     dword ptr [rax+rax+00h]
0x1401f98a7  test    eax, eax
0x1401f98a9  js      short loc_1401F98E1
0x1401f98ab  mov     rcx, [rsp+48h+arg_8]
0x1401f98b0  mov     rax, [rcx]
0x1401f98b3  mov     rax, [rax+68h]
0x1401f98b7  call    _guard_dispatch_icall
0x1401f98bc  mov     rcx, [rsp+48h+arg_8]
0x1401f98c1  mov     rax, [rcx]
0x1401f98c4  mov     rax, [rax+0A8h]
0x1401f98cb  call    _guard_dispatch_icall
0x1401f98d0  mov     rcx, [rsp+48h+arg_8]
0x1401f98d5  mov     rax, [rcx]
0x1401f98d8  mov     rax, [rax+8]
0x1401f98dc  call    _guard_dispatch_icall
0x1401f98e1  xor     r14d, r14d
0x1401f98e4  cmp     [rsi+11398h], ebp
0x1401f98ea  cmovz   r14d, ebx
0x1401f98ee  call    IsxxxDwmStopRedirectionSupported
0x1401f98f3  test    eax, eax
0x1401f98f5  js      short loc_1401F9923
0x1401f98f7  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401f98fe  nop     dword ptr [rax+rax+00h]
0x1401f9903  mov     rcx, [rax+30h]
0x1401f9907  mov     rax, [rcx+0EF0h]
0x1401f990e  test    rax, rax
0x1401f9911  jz      short loc_1401F991E
0x1401f9913  mov     ecx, ebx
0x1401f9915  call    _guard_dispatch_icall
0x1401f991a  mov     ebp, eax
0x1401f991c  jmp     short loc_1401F9923
0x1401f991e  mov     ebp, 0C00000BBh
0x1401f9923  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1401f9928  test    eax, eax
0x1401f992a  jz      short loc_1401F994F
0x1401f992c  mov     edx, eax; BugCheckParameter1
0x1401f992e  xor     r9d, r9d; BugCheckParameter3
0x1401f9931  xor     r8d, r8d; BugCheckParameter2
0x1401f9934  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x1401f993d  mov     ecx, 160h; BugCheckCode
0x1401f9942  call    cs:__imp_KeBugCheckEx
0x1401f994f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401f9954  call    GreSfmCleanupPresentHistory
0x1401f9959  call    cs:__imp_W32GetUserSessionState
0x1401f9960  nop     dword ptr [rax+rax+00h]
0x1401f9965  xor     r8d, r8d
0x1401f9968  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401f996f  mov     rcx, rax
0x1401f9972  mov     rdi, rax
0x1401f9975  lea     edx, [r8+1]
0x1401f9979  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401f997e  mov     [rdi+10h], rax
0x1401f9982  mov     rdx, rax
0x1401f9985  test    rax, rax
0x1401f9988  jz      loc_1401F9A3B
0x1401f998e  xor     ecx, ecx
0x1401f9990  xor     eax, eax
0x1401f9992  lock cmpxchg [rdx+208h], ecx
0x1401f999a  bt      eax, 18h
0x1401f999e  jnb     loc_1401F9A3B
0x1401f99a4  mov     al, [rdx+550h]
0x1401f99aa  test    al, al
0x1401f99ac  js      loc_1401F9A3B
0x1401f99b2  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401f99b9  nop     dword ptr [rax+rax+00h]
0x1401f99be  test    rax, rax
0x1401f99c1  jz      short loc_1401F9A3B
0x1401f99c3  cmp     qword ptr [rax], 0
0x1401f99c7  jz      short loc_1401F9A3B
0x1401f99c9  mov     al, [rax+4B0h]
0x1401f99cf  cmp     al, 1
0x1401f99d1  jnz     short loc_1401F9A3B
0x1401f99d3  jmp     short loc_1401F9A17
0x1401f99d5  mov     rax, [rbx+10h]
0x1401f99d9  mov     [rdi+4C58h], rax
0x1401f99e0  mov     rax, [rbx]
0x1401f99e3  mov     qword ptr [rbx+10h], 0
0x1401f99eb  cmp     dword ptr [rax+8], 1
0x1401f99ef  jnb     short loc_1401F9A0F
0x1401f99f1  mov     [rsp+48h+arg_0], 20000h
0x1401f99f9  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401f9a00  mov     edx, [rsp+48h+arg_0]
0x1401f9a04  mov     r8d, 1236h
0x1401f9a0a  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401f9a0f  mov     rcx, [rbx]
0x1401f9a12  call    HMUnlockObject
0x1401f9a17  mov     rbx, [rdi+4C58h]
0x1401f9a1e  test    rbx, rbx
0x1401f9a21  jnz     short loc_1401F99D5
0x1401f9a23  lea     rcx, [rdi+4C78h]
0x1401f9a2a  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f9a2f  lea     rcx, [rdi+4C68h]
0x1401f9a36  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f9a3b  call    GreLockDwmState
0x1401f9a40  xor     ecx, ecx; void *
0x1401f9a42  call    ?SetDwmApiPort@@YAXPEAX@Z; SetDwmApiPort(void *)
0x1401f9a47  mov     rcx, [rsi+11390h]; Object
0x1401f9a4e  test    rcx, rcx
0x1401f9a51  jz      short loc_1401F9A6A
0x1401f9a53  call    cs:__imp_ObfDereferenceObject
0x1401f9a5a  nop     dword ptr [rax+rax+00h]
0x1401f9a5f  mov     qword ptr [rsi+11390h], 0
0x1401f9a6a  call    GreUnlockDwmState
0x1401f9a6f  mov     dword ptr [rsi+11398h], 0
0x1401f9a79  test    r14d, r14d
0x1401f9a7c  jz      short loc_1401F9A97
0x1401f9a7e  call    cs:__imp_PsGetCurrentProcessId
0x1401f9a85  nop     dword ptr [rax+rax+00h]
0x1401f9a8a  mov     rdx, rax
0x1401f9a8d  mov     ecx, 40Ch
0x1401f9a92  call    xxxDwmControl
0x1401f9a97  mov     rbx, [rsp+48h+arg_10]
0x1401f9a9c  mov     eax, ebp
0x1401f9a9e  mov     rbp, [rsp+48h+arg_18]
0x1401f9aa3  add     rsp, 30h
0x1401f9aa7  pop     r14
0x1401f9aa9  pop     rdi
0x1401f9aaa  pop     rsi
0x1401f9aab  retn
```
