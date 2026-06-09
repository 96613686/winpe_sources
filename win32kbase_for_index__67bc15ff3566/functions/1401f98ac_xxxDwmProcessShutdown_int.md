# xxxDwmProcessShutdown(int)

- ea: `0x1401f98ac`
- end: `0x1401f9aed`
- name: `?xxxDwmProcessShutdown@@YAJH@Z`
- size: `577`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d98bc`
- `0x1401ded90`

## callees

- `0x140029710`
- `0x140029850`
- `0x14004c020`
- `0x14004f4c0`
- `0x14006f060`
- `0x14006f140`
- `0x1400701d4`
- `0x140172700`
- `0x140182fc8`
- `0x140186bfc`
- `0x1401aab9c`
- `0x1401b2e50`
- `0x1401f98ac`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1401f9982`
- `ntoskrnl!KeBugCheckEx` at `0x1401f9982`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f99f2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f99f2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f9abe`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f9abe`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9a93`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9a93`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f98db`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f98db`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f9937`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f9937`
- `WIN32K!W32GetUserSessionState` at `0x1401f98c7`
- `WIN32K!W32GetUserSessionState` at `0x1401f9999`
- `WIN32K!W32GetUserSessionState` at `0x1401f98c7`
- `WIN32K!W32GetUserSessionState` at `0x1401f9999`

## pseudocode

```c
__int64 __fastcall xxxDwmProcessShutdown(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  unsigned int v4; // ebx
  __int64 UserSessionState; // rsi
  unsigned int v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(_QWORD); // rax
  unsigned int Count; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v22; // rax
  _QWORD *v23; // rbx
  void *v24; // rcx
  HANDLE CurrentProcessId; // rax
  __int64 v27; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v4 = a1;
  v27 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  if ( (int)DxgkGetSessionTokenManager(&v27) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 104LL))(v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 168LL))(v27);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
  }
  v6 = 0;
  if ( !*(_DWORD *)(UserSessionState + 70552) )
    v6 = v4;
  if ( (int)IsxxxDwmStopRedirectionSupported() >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v8, v7) + 48) + 3824LL);
    if ( v9 )
      v3 = v9(v4);
    else
      v3 = -1073741637;
  }
  Count = AtomicExecutionCheck::GetCount();
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  UserSessionSwitchLeaveCritWithNonPaged(v12, v11, v13);
  GreSfmCleanupPresentHistory();
  v17 = W32GetUserSessionState(v15, v14, v16);
  v18 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v17,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v17 + 16) = v18;
  v20 = v18;
  if ( v18 )
  {
    v19 = 0;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v18 + 520), 0, 0) & 0x1000000) != 0
      && *(char *)(v18 + 1360) >= 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
        {
          while ( 1 )
          {
            v23 = *(_QWORD **)(v17 + 19544);
            if ( !v23 )
              break;
            *(_QWORD *)(v17 + 19544) = v23[2];
            v22 = *v23;
            v23[2] = 0;
            if ( !*(_DWORD *)(v22 + 8) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            HMUnlockObject(*v23);
          }
          DestroyDeferredUnlockObjectAssignmentList(v17 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v17 + 19560);
        }
      }
    }
  }
  GreLockDwmState(v19, v20);
  SetDwmApiPort(0);
  v24 = *(void **)(UserSessionState + 70544);
  if ( v24 )
  {
    ObfDereferenceObject(v24);
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
0x1401f98ac  mov     [rsp+arg_10], rbx
0x1401f98b1  mov     [rsp+arg_18], rbp
0x1401f98b6  push    rsi
0x1401f98b7  push    rdi
0x1401f98b8  push    r14
0x1401f98ba  sub     rsp, 30h
0x1401f98be  xor     ebp, ebp
0x1401f98c0  mov     ebx, ecx
0x1401f98c2  mov     [rsp+48h+arg_8], rbp
0x1401f98c7  call    cs:__imp_W32GetUserSessionState
0x1401f98ce  nop     dword ptr [rax+rax+00h]
0x1401f98d3  lea     rcx, [rsp+48h+arg_8]
0x1401f98d8  mov     rsi, rax
0x1401f98db  call    cs:__imp_DxgkGetSessionTokenManager
0x1401f98e2  nop     dword ptr [rax+rax+00h]
0x1401f98e7  test    eax, eax
0x1401f98e9  js      short loc_1401F9921
0x1401f98eb  mov     rcx, [rsp+48h+arg_8]
0x1401f98f0  mov     rax, [rcx]
0x1401f98f3  mov     rax, [rax+68h]
0x1401f98f7  call    _guard_dispatch_icall
0x1401f98fc  mov     rcx, [rsp+48h+arg_8]
0x1401f9901  mov     rax, [rcx]
0x1401f9904  mov     rax, [rax+0A8h]
0x1401f990b  call    _guard_dispatch_icall
0x1401f9910  mov     rcx, [rsp+48h+arg_8]
0x1401f9915  mov     rax, [rcx]
0x1401f9918  mov     rax, [rax+8]
0x1401f991c  call    _guard_dispatch_icall
0x1401f9921  xor     r14d, r14d
0x1401f9924  cmp     [rsi+11398h], ebp
0x1401f992a  cmovz   r14d, ebx
0x1401f992e  call    IsxxxDwmStopRedirectionSupported
0x1401f9933  test    eax, eax
0x1401f9935  js      short loc_1401F9963
0x1401f9937  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401f993e  nop     dword ptr [rax+rax+00h]
0x1401f9943  mov     rcx, [rax+30h]
0x1401f9947  mov     rax, [rcx+0EF0h]
0x1401f994e  test    rax, rax
0x1401f9951  jz      short loc_1401F995E
0x1401f9953  mov     ecx, ebx
0x1401f9955  call    _guard_dispatch_icall
0x1401f995a  mov     ebp, eax
0x1401f995c  jmp     short loc_1401F9963
0x1401f995e  mov     ebp, 0C00000BBh
0x1401f9963  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1401f9968  test    eax, eax
0x1401f996a  jz      short loc_1401F998F
0x1401f996c  mov     edx, eax; BugCheckParameter1
0x1401f996e  xor     r9d, r9d; BugCheckParameter3
0x1401f9971  xor     r8d, r8d; BugCheckParameter2
0x1401f9974  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x1401f997d  mov     ecx, 160h; BugCheckCode
0x1401f9982  call    cs:__imp_KeBugCheckEx
0x1401f998f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401f9994  call    GreSfmCleanupPresentHistory
0x1401f9999  call    cs:__imp_W32GetUserSessionState
0x1401f99a0  nop     dword ptr [rax+rax+00h]
0x1401f99a5  xor     r8d, r8d
0x1401f99a8  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401f99af  mov     rcx, rax
0x1401f99b2  mov     rdi, rax
0x1401f99b5  lea     edx, [r8+1]
0x1401f99b9  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401f99be  mov     [rdi+10h], rax
0x1401f99c2  mov     rdx, rax
0x1401f99c5  test    rax, rax
0x1401f99c8  jz      loc_1401F9A7B
0x1401f99ce  xor     ecx, ecx
0x1401f99d0  xor     eax, eax
0x1401f99d2  lock cmpxchg [rdx+208h], ecx
0x1401f99da  bt      eax, 18h
0x1401f99de  jnb     loc_1401F9A7B
0x1401f99e4  mov     al, [rdx+550h]
0x1401f99ea  test    al, al
0x1401f99ec  js      loc_1401F9A7B
0x1401f99f2  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401f99f9  nop     dword ptr [rax+rax+00h]
0x1401f99fe  test    rax, rax
0x1401f9a01  jz      short loc_1401F9A7B
0x1401f9a03  cmp     qword ptr [rax], 0
0x1401f9a07  jz      short loc_1401F9A7B
0x1401f9a09  mov     al, [rax+4B0h]
0x1401f9a0f  cmp     al, 1
0x1401f9a11  jnz     short loc_1401F9A7B
0x1401f9a13  jmp     short loc_1401F9A57
0x1401f9a15  mov     rax, [rbx+10h]
0x1401f9a19  mov     [rdi+4C58h], rax
0x1401f9a20  mov     rax, [rbx]
0x1401f9a23  mov     qword ptr [rbx+10h], 0
0x1401f9a2b  cmp     dword ptr [rax+8], 1
0x1401f9a2f  jnb     short loc_1401F9A4F
0x1401f9a31  mov     [rsp+48h+arg_0], 20000h
0x1401f9a39  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401f9a40  mov     edx, [rsp+48h+arg_0]
0x1401f9a44  mov     r8d, 1236h
0x1401f9a4a  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401f9a4f  mov     rcx, [rbx]
0x1401f9a52  call    HMUnlockObject
0x1401f9a57  mov     rbx, [rdi+4C58h]
0x1401f9a5e  test    rbx, rbx
0x1401f9a61  jnz     short loc_1401F9A15
0x1401f9a63  lea     rcx, [rdi+4C78h]
0x1401f9a6a  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f9a6f  lea     rcx, [rdi+4C68h]
0x1401f9a76  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f9a7b  call    GreLockDwmState
0x1401f9a80  xor     ecx, ecx; void *
0x1401f9a82  call    ?SetDwmApiPort@@YAXPEAX@Z; SetDwmApiPort(void *)
0x1401f9a87  mov     rcx, [rsi+11390h]; Object
0x1401f9a8e  test    rcx, rcx
0x1401f9a91  jz      short loc_1401F9AAA
0x1401f9a93  call    cs:__imp_ObfDereferenceObject
0x1401f9a9a  nop     dword ptr [rax+rax+00h]
0x1401f9a9f  mov     qword ptr [rsi+11390h], 0
0x1401f9aaa  call    GreUnlockDwmState
0x1401f9aaf  mov     dword ptr [rsi+11398h], 0
0x1401f9ab9  test    r14d, r14d
0x1401f9abc  jz      short loc_1401F9AD7
0x1401f9abe  call    cs:__imp_PsGetCurrentProcessId
0x1401f9ac5  nop     dword ptr [rax+rax+00h]
0x1401f9aca  mov     rdx, rax
0x1401f9acd  mov     ecx, 40Ch
0x1401f9ad2  call    xxxDwmControl
0x1401f9ad7  mov     rbx, [rsp+48h+arg_10]
0x1401f9adc  mov     eax, ebp
0x1401f9ade  mov     rbp, [rsp+48h+arg_18]
0x1401f9ae3  add     rsp, 30h
0x1401f9ae7  pop     r14
0x1401f9ae9  pop     rdi
0x1401f9aea  pop     rsi
0x1401f9aeb  retn
```
