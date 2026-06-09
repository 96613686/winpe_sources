# xxxDwmProcessShutdown(int)

- ea: `0x1401f904c`
- end: `0x1401f928d`
- name: `?xxxDwmProcessShutdown@@YAJH@Z`
- size: `577`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003804c`
- `0x1401de250`

## callees

- `0x14001bdf0`
- `0x14001bf30`
- `0x140032260`
- `0x140032340`
- `0x140033364`
- `0x140074bf0`
- `0x140078090`
- `0x140170e70`
- `0x140181458`
- `0x1401845c4`
- `0x1401a9f9c`
- `0x1401b1c40`
- `0x1401f904c`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1401f9122`
- `ntoskrnl!KeBugCheckEx` at `0x1401f9122`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f9192`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401f9192`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f925e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401f925e`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9233`
- `ntoskrnl!ObfDereferenceObject` at `0x1401f9233`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f907b`
- `dxgkrnl!DxgkGetSessionTokenManager` at `0x1401f907b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f90d7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401f90d7`
- `WIN32K!W32GetUserSessionState` at `0x1401f9067`
- `WIN32K!W32GetUserSessionState` at `0x1401f9139`
- `WIN32K!W32GetUserSessionState` at `0x1401f9067`
- `WIN32K!W32GetUserSessionState` at `0x1401f9139`

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
0x1401f904c  mov     [rsp+arg_10], rbx
0x1401f9051  mov     [rsp+arg_18], rbp
0x1401f9056  push    rsi
0x1401f9057  push    rdi
0x1401f9058  push    r14
0x1401f905a  sub     rsp, 30h
0x1401f905e  xor     ebp, ebp
0x1401f9060  mov     ebx, ecx
0x1401f9062  mov     [rsp+48h+arg_8], rbp
0x1401f9067  call    cs:__imp_W32GetUserSessionState
0x1401f906e  nop     dword ptr [rax+rax+00h]
0x1401f9073  lea     rcx, [rsp+48h+arg_8]
0x1401f9078  mov     rsi, rax
0x1401f907b  call    cs:__imp_DxgkGetSessionTokenManager
0x1401f9082  nop     dword ptr [rax+rax+00h]
0x1401f9087  test    eax, eax
0x1401f9089  js      short loc_1401F90C1
0x1401f908b  mov     rcx, [rsp+48h+arg_8]
0x1401f9090  mov     rax, [rcx]
0x1401f9093  mov     rax, [rax+68h]
0x1401f9097  call    _guard_dispatch_icall
0x1401f909c  mov     rcx, [rsp+48h+arg_8]
0x1401f90a1  mov     rax, [rcx]
0x1401f90a4  mov     rax, [rax+0A8h]
0x1401f90ab  call    _guard_dispatch_icall
0x1401f90b0  mov     rcx, [rsp+48h+arg_8]
0x1401f90b5  mov     rax, [rcx]
0x1401f90b8  mov     rax, [rax+8]
0x1401f90bc  call    _guard_dispatch_icall
0x1401f90c1  xor     r14d, r14d
0x1401f90c4  cmp     [rsi+11398h], ebp
0x1401f90ca  cmovz   r14d, ebx
0x1401f90ce  call    IsxxxDwmStopRedirectionSupported
0x1401f90d3  test    eax, eax
0x1401f90d5  js      short loc_1401F9103
0x1401f90d7  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401f90de  nop     dword ptr [rax+rax+00h]
0x1401f90e3  mov     rcx, [rax+30h]
0x1401f90e7  mov     rax, [rcx+0EF0h]
0x1401f90ee  test    rax, rax
0x1401f90f1  jz      short loc_1401F90FE
0x1401f90f3  mov     ecx, ebx
0x1401f90f5  call    _guard_dispatch_icall
0x1401f90fa  mov     ebp, eax
0x1401f90fc  jmp     short loc_1401F9103
0x1401f90fe  mov     ebp, 0C00000BBh
0x1401f9103  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1401f9108  test    eax, eax
0x1401f910a  jz      short loc_1401F912F
0x1401f910c  mov     edx, eax; BugCheckParameter1
0x1401f910e  xor     r9d, r9d; BugCheckParameter3
0x1401f9111  xor     r8d, r8d; BugCheckParameter2
0x1401f9114  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x1401f911d  mov     ecx, 160h; BugCheckCode
0x1401f9122  call    cs:__imp_KeBugCheckEx
0x1401f912f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401f9134  call    GreSfmCleanupPresentHistory
0x1401f9139  call    cs:__imp_W32GetUserSessionState
0x1401f9140  nop     dword ptr [rax+rax+00h]
0x1401f9145  xor     r8d, r8d
0x1401f9148  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401f914f  mov     rcx, rax
0x1401f9152  mov     rdi, rax
0x1401f9155  lea     edx, [r8+1]
0x1401f9159  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401f915e  mov     [rdi+10h], rax
0x1401f9162  mov     rdx, rax
0x1401f9165  test    rax, rax
0x1401f9168  jz      loc_1401F921B
0x1401f916e  xor     ecx, ecx
0x1401f9170  xor     eax, eax
0x1401f9172  lock cmpxchg [rdx+208h], ecx
0x1401f917a  bt      eax, 18h
0x1401f917e  jnb     loc_1401F921B
0x1401f9184  mov     al, [rdx+550h]
0x1401f918a  test    al, al
0x1401f918c  js      loc_1401F921B
0x1401f9192  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401f9199  nop     dword ptr [rax+rax+00h]
0x1401f919e  test    rax, rax
0x1401f91a1  jz      short loc_1401F921B
0x1401f91a3  cmp     qword ptr [rax], 0
0x1401f91a7  jz      short loc_1401F921B
0x1401f91a9  mov     al, [rax+4B0h]
0x1401f91af  cmp     al, 1
0x1401f91b1  jnz     short loc_1401F921B
0x1401f91b3  jmp     short loc_1401F91F7
0x1401f91b5  mov     rax, [rbx+10h]
0x1401f91b9  mov     [rdi+4C58h], rax
0x1401f91c0  mov     rax, [rbx]
0x1401f91c3  mov     qword ptr [rbx+10h], 0
0x1401f91cb  cmp     dword ptr [rax+8], 1
0x1401f91cf  jnb     short loc_1401F91EF
0x1401f91d1  mov     [rsp+48h+arg_0], 20000h
0x1401f91d9  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401f91e0  mov     edx, [rsp+48h+arg_0]
0x1401f91e4  mov     r8d, 1236h
0x1401f91ea  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401f91ef  mov     rcx, [rbx]
0x1401f91f2  call    HMUnlockObject
0x1401f91f7  mov     rbx, [rdi+4C58h]
0x1401f91fe  test    rbx, rbx
0x1401f9201  jnz     short loc_1401F91B5
0x1401f9203  lea     rcx, [rdi+4C78h]
0x1401f920a  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f920f  lea     rcx, [rdi+4C68h]
0x1401f9216  call    DestroyDeferredUnlockObjectAssignmentList
0x1401f921b  call    GreLockDwmState
0x1401f9220  xor     ecx, ecx; void *
0x1401f9222  call    ?SetDwmApiPort@@YAXPEAX@Z; SetDwmApiPort(void *)
0x1401f9227  mov     rcx, [rsi+11390h]; Object
0x1401f922e  test    rcx, rcx
0x1401f9231  jz      short loc_1401F924A
0x1401f9233  call    cs:__imp_ObfDereferenceObject
0x1401f923a  nop     dword ptr [rax+rax+00h]
0x1401f923f  mov     qword ptr [rsi+11390h], 0
0x1401f924a  call    GreUnlockDwmState
0x1401f924f  mov     dword ptr [rsi+11398h], 0
0x1401f9259  test    r14d, r14d
0x1401f925c  jz      short loc_1401F9277
0x1401f925e  call    cs:__imp_PsGetCurrentProcessId
0x1401f9265  nop     dword ptr [rax+rax+00h]
0x1401f926a  mov     rdx, rax
0x1401f926d  mov     ecx, 40Ch
0x1401f9272  call    xxxDwmControl
0x1401f9277  mov     rbx, [rsp+48h+arg_10]
0x1401f927c  mov     eax, ebp
0x1401f927e  mov     rbp, [rsp+48h+arg_18]
0x1401f9283  add     rsp, 30h
0x1401f9287  pop     r14
0x1401f9289  pop     rdi
0x1401f928a  pop     rsi
0x1401f928b  retn
```
