# EtwCaptureStateCallback(void)

- ea: `0x1400c3058`
- end: `0x1400c333b`
- name: `?EtwCaptureStateCallback@@YAXXZ`
- size: `739`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140091468`

## callees

- `0x14001bdf0`
- `0x14001c470`
- `0x140031bf4`
- `0x140036118`
- `0x14004fc74`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400c3058`
- `0x1400c3790`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c3085`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c3085`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3076`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3076`
- `ntoskrnl!PsGetThreadId` at `0x1400c31d0`
- `ntoskrnl!PsGetThreadId` at `0x1400c31d0`
- `WIN32K!W32GetUserSessionState` at `0x1400c3067`
- `WIN32K!W32GetUserSessionState` at `0x1400c3119`
- `WIN32K!W32GetUserSessionState` at `0x1400c317b`
- `WIN32K!W32GetUserSessionState` at `0x1400c32b1`
- `WIN32K!W32GetUserSessionState` at `0x1400c32dc`
- `WIN32K!W32GetUserSessionState` at `0x1400c32f5`
- `WIN32K!W32GetUserSessionState` at `0x1400c3307`
- `WIN32K!W32GetUserSessionState` at `0x1400c3067`
- `WIN32K!W32GetUserSessionState` at `0x1400c3119`
- `WIN32K!W32GetUserSessionState` at `0x1400c317b`
- `WIN32K!W32GetUserSessionState` at `0x1400c32b1`
- `WIN32K!W32GetUserSessionState` at `0x1400c32dc`
- `WIN32K!W32GetUserSessionState` at `0x1400c32f5`
- `WIN32K!W32GetUserSessionState` at `0x1400c3307`

## pseudocode

```c
void __fastcall EtwCaptureStateCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 UserSessionState; // rdi
  __int64 v4; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rbp
  __int64 i; // rdi
  __int64 v12; // rbx
  _QWORD *j; // rsi
  unsigned int ThreadId; // r12d
  char ThreadInfoFlags; // al
  int v16; // ecx
  char v17; // r10
  __int64 v18; // rax
  unsigned __int64 v19; // rbp
  __int64 v20; // rdx
  unsigned int v21; // ebp
  int v22; // esi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  char CurrentWin32kSessionId; // di
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  int v35; // ecx
  int v36; // r8d

  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v4);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  if ( !*(_QWORD *)CurrentThreadWin32Thread )
    goto LABEL_37;
  if ( (unsigned int)IsThreadCrossSessionAttached() )
  {
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
LABEL_37:
    v7 = 0;
    goto LABEL_4;
  }
  v7 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  *(_QWORD *)(UserSessionState + 16) = v7;
  if ( v7 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v7) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( (W32kEtwEnabledKeyword & 0x8000000000040000uLL) != 0
    && (unsigned __int8)(byte_140292DD8 - 1) > 2u
    && (qword_140292DC0 & 0x8000000000040000uLL) != 0
    && (qword_140292DC8 & 0x8000000000040000uLL) == qword_140292DC8 )
  {
    if ( *(_DWORD *)(W32GetUserSessionState(v7, 0x8000000000040000uLL, v6) + 36184) )
    {
      v19 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v21 = v19 - *(_DWORD *)(W32GetUserSessionState(v7, v8, v6) + 36188);
      if ( v21 >= 0xC8 && (Microsoft_Windows_Win32kEnableBits & 0x40) != 0 )
      {
        v22 = *(_DWORD *)(W32GetUserSessionState(v7, v20, v6) + 36184);
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v24, v23, v25);
        v30 = *(_DWORD *)(W32GetUserSessionState(v28, v27, v29) + 36196);
        v34 = W32GetUserSessionState(v32, v31, v33);
        McTemplateK0qqqqq_EtwWriteTransfer(
          v35,
          (unsigned int)WaitCursorEvent,
          v36,
          *(_DWORD *)(v34 + 36192),
          v30,
          CurrentWin32kSessionId,
          v22,
          v21);
      }
    }
  }
  v9 = 0x8000000000080000uLL;
  if ( (W32kEtwEnabledKeyword & 0x8000000000080000uLL) != 0
    && (unsigned __int8)(byte_140292DD8 - 1) > 2u
    && (qword_140292DC0 & 0x8000000000080000uLL) != 0
    && (qword_140292DC8 & 0x8000000000080000uLL) == qword_140292DC8 )
  {
    v10 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    for ( i = *(_QWORD *)(W32GetUserSessionState(v7, 0x8000000000080000uLL, v6) + 63288); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
        goto LABEL_19;
      v12 = *(_QWORD *)(i + 16);
LABEL_16:
      if ( v12 )
        break;
    }
    for ( j = *(_QWORD **)(v12 + 176); ; j = (_QWORD *)*j )
    {
      if ( j == (_QWORD *)(v12 + 176) )
      {
        v12 = *(_QWORD *)(v12 + 32);
        goto LABEL_16;
      }
      ThreadId = (unsigned int)PsGetThreadId((PETHREAD)*(j - 96));
      ThreadInfoFlags = EtwpGetThreadInfoFlags((struct tagTHREADINFO *const)(j - 96));
      v16 = *((_DWORD *)j + 134);
      v17 = ThreadInfoFlags;
      v6 = v16 ? (unsigned int)(v10 - v16) : 0LL;
      v18 = *(j - 38);
      if ( !v18 )
        break;
      v9 = (unsigned int)(v10 - *(_DWORD *)(v18 + 528));
      if ( !*(_DWORD *)(v18 + 40) )
        goto LABEL_26;
      v7 = (unsigned int)(v10 - *(_DWORD *)(*(_QWORD *)(v18 + 24) + 48LL));
LABEL_27:
      if ( (Microsoft_Windows_Win32kEnableBits & 0x80u) != 0LL )
        McTemplateK0qqqqq_EtwWriteTransfer(v7, (unsigned int)ThreadInfoRundownEvent, v6, ThreadId, v17, v6, v9, v7);
    }
    v9 = 0;
LABEL_26:
    v7 = 0;
    goto LABEL_27;
  }
LABEL_19:
  UserSessionSwitchLeaveCritWithNonPaged(v7, v9, v6);
}

```

## disassembly

```asm
0x1400c3058  push    rbx
0x1400c305a  push    rbp
0x1400c305b  push    rsi
0x1400c305c  push    rdi
0x1400c305d  push    r12
0x1400c305f  push    r14
0x1400c3061  push    r15
0x1400c3063  sub     rsp, 40h
0x1400c3067  call    cs:__imp_W32GetUserSessionState
0x1400c306e  nop     dword ptr [rax+rax+00h]
0x1400c3073  mov     rdi, rax
0x1400c3076  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c307d  nop     dword ptr [rax+rax+00h]
0x1400c3082  mov     rbx, rax
0x1400c3085  call    cs:__imp_KeEnterCriticalRegion
0x1400c308c  nop     dword ptr [rax+rax+00h]
0x1400c3091  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400c3094  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400c3097  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400c309c  cmp     qword ptr [rbx], 0
0x1400c30a0  jz      loc_1400C329C
0x1400c30a6  call    IsThreadCrossSessionAttached
0x1400c30ab  test    eax, eax
0x1400c30ad  jnz     loc_1400C3298
0x1400c30b3  mov     rcx, [rbx]
0x1400c30b6  mov     byte ptr [rcx+6ACh], 1
0x1400c30bd  mov     [rdi+10h], rcx
0x1400c30c1  test    rcx, rcx
0x1400c30c4  jnz     loc_1400C3265
0x1400c30ca  mov     rdx, 8000000000040000h
0x1400c30d4  mov     r14, 0FFFFF78000000320h
0x1400c30de  test    cs:W32kEtwEnabledKeyword, rdx
0x1400c30e5  mov     r15, 0FFFFF78000000004h
0x1400c30ef  jz      short loc_1400C3132
0x1400c30f1  mov     al, cs:byte_140292DD8
0x1400c30f7  dec     al
0x1400c30f9  cmp     al, 2
0x1400c30fb  jbe     short loc_1400C3132
0x1400c30fd  test    cs:qword_140292DC0, rdx
0x1400c3104  jz      short loc_1400C3132
0x1400c3106  mov     rax, cs:qword_140292DC8
0x1400c310d  and     rax, rdx
0x1400c3110  cmp     rax, cs:qword_140292DC8
0x1400c3117  jnz     short loc_1400C3132
0x1400c3119  call    cs:__imp_W32GetUserSessionState
0x1400c3120  nop     dword ptr [rax+rax+00h]
0x1400c3125  cmp     dword ptr [rax+8D58h], 0
0x1400c312c  jnz     loc_1400C32A3
0x1400c3132  mov     rdx, 8000000000080000h
0x1400c313c  test    cs:W32kEtwEnabledKeyword, rdx
0x1400c3143  jz      short loc_1400C31A2
0x1400c3145  mov     al, cs:byte_140292DD8
0x1400c314b  dec     al
0x1400c314d  cmp     al, 2
0x1400c314f  jbe     short loc_1400C31A2
0x1400c3151  test    cs:qword_140292DC0, rdx
0x1400c3158  jz      short loc_1400C31A2
0x1400c315a  mov     rax, cs:qword_140292DC8
0x1400c3161  and     rax, rdx
0x1400c3164  cmp     rax, cs:qword_140292DC8
0x1400c316b  jnz     short loc_1400C31A2
0x1400c316d  mov     rax, [r14]
0x1400c3170  mov     ebp, [r15]
0x1400c3173  imul    rbp, rax
0x1400c3177  shr     rbp, 18h
0x1400c317b  call    cs:__imp_W32GetUserSessionState
0x1400c3182  nop     dword ptr [rax+rax+00h]
0x1400c3187  mov     rdi, [rax+0F738h]
0x1400c318e  jmp     short loc_1400C319D
0x1400c3190  mov     rbx, [rdi+10h]
0x1400c3194  test    rbx, rbx
0x1400c3197  jnz     short loc_1400C31B7
0x1400c3199  mov     rdi, [rdi+8]
0x1400c319d  test    rdi, rdi
0x1400c31a0  jnz     short loc_1400C3190
0x1400c31a2  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400c31a7  add     rsp, 40h
0x1400c31ab  pop     r15
0x1400c31ad  pop     r14
0x1400c31af  pop     r12
0x1400c31b1  pop     rdi
0x1400c31b2  pop     rsi
0x1400c31b3  pop     rbp
0x1400c31b4  pop     rbx
0x1400c31b5  retn
0x1400c31b7  lea     r14, [rbx+0B0h]
0x1400c31be  mov     rsi, [r14]
0x1400c31c1  cmp     rsi, r14
0x1400c31c4  jz      short loc_1400C3235
0x1400c31c6  lea     r15, [rsi-300h]
0x1400c31cd  mov     rcx, [r15]; Thread
0x1400c31d0  call    cs:__imp_PsGetThreadId
0x1400c31d7  nop     dword ptr [rax+rax+00h]
0x1400c31dc  mov     rcx, r15; struct tagTHREADINFO *
0x1400c31df  mov     r12, rax
0x1400c31e2  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x1400c31e7  mov     ecx, [r15+518h]
0x1400c31ee  mov     r10d, eax
0x1400c31f1  test    ecx, ecx
0x1400c31f3  jz      short loc_1400C3225
0x1400c31f5  mov     r8d, ebp
0x1400c31f8  sub     r8d, ecx
0x1400c31fb  mov     rax, [r15+1D0h]
0x1400c3202  test    rax, rax
0x1400c3205  jz      short loc_1400C3261
0x1400c3207  mov     edx, ebp
0x1400c3209  sub     edx, [rax+210h]
0x1400c320f  cmp     dword ptr [rax+28h], 0
0x1400c3213  jnz     short loc_1400C322A
0x1400c3215  xor     ecx, ecx
0x1400c3217  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits, 0
0x1400c321e  jl      short loc_1400C323E
0x1400c3220  mov     rsi, [rsi]
0x1400c3223  jmp     short loc_1400C31C1
0x1400c3225  xor     r8d, r8d
0x1400c3228  jmp     short loc_1400C31FB
0x1400c322a  mov     rax, [rax+18h]
0x1400c322e  mov     ecx, ebp
0x1400c3230  sub     ecx, [rax+30h]
0x1400c3233  jmp     short loc_1400C3217
0x1400c3235  mov     rbx, [rbx+20h]
0x1400c3239  jmp     loc_1400C3194
0x1400c323e  mov     [rsp+78h+var_40], ecx
0x1400c3242  mov     r9d, r12d
0x1400c3245  mov     [rsp+78h+var_48], edx
0x1400c3249  lea     rdx, ThreadInfoRundownEvent
0x1400c3250  mov     [rsp+78h+var_50], r8d
0x1400c3255  mov     [rsp+78h+var_58], r10d
0x1400c325a  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400c325f  jmp     short loc_1400C3220
0x1400c3261  xor     edx, edx
0x1400c3263  jmp     short loc_1400C3215
0x1400c3265  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400c326a  test    al, al
0x1400c326c  jz      loc_1400C30CA
0x1400c3272  lea     rbx, [rdi+4C40h]
0x1400c3279  mov     rcx, rbx
0x1400c327c  call    DestroySharedUserCritDeferredUnlockList
0x1400c3281  lea     rcx, [rbx+38h]
0x1400c3285  call    DestroyDeferredUnlockObjectAssignmentList
0x1400c328a  lea     rcx, [rbx+28h]
0x1400c328e  call    DestroyDeferredUnlockObjectAssignmentList
0x1400c3293  jmp     loc_1400C30CA
0x1400c3298  or      dword ptr [rbx+18h], 2
0x1400c329c  xor     ecx, ecx
0x1400c329e  jmp     loc_1400C30BD
0x1400c32a3  mov     rax, [r14]
0x1400c32a6  mov     ebp, [r15]
0x1400c32a9  imul    rbp, rax
0x1400c32ad  shr     rbp, 18h
0x1400c32b1  call    cs:__imp_W32GetUserSessionState
0x1400c32b8  nop     dword ptr [rax+rax+00h]
0x1400c32bd  sub     ebp, [rax+8D5Ch]
0x1400c32c3  cmp     ebp, 0C8h
0x1400c32c9  jb      loc_1400C3132
0x1400c32cf  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 40h
0x1400c32d6  jz      loc_1400C3132
0x1400c32dc  call    cs:__imp_W32GetUserSessionState
0x1400c32e3  nop     dword ptr [rax+rax+00h]
0x1400c32e8  mov     esi, [rax+8D58h]
0x1400c32ee  call    W32GetCurrentWin32kSessionId
0x1400c32f3  mov     edi, eax
0x1400c32f5  call    cs:__imp_W32GetUserSessionState
0x1400c32fc  nop     dword ptr [rax+rax+00h]
0x1400c3301  mov     ebx, [rax+8D64h]
0x1400c3307  call    cs:__imp_W32GetUserSessionState
0x1400c330e  nop     dword ptr [rax+rax+00h]
0x1400c3313  mov     [rsp+78h+var_40], ebp
0x1400c3317  lea     rdx, WaitCursorEvent
0x1400c331e  mov     [rsp+78h+var_48], esi
0x1400c3322  mov     [rsp+78h+var_50], edi
0x1400c3326  mov     r9d, [rax+8D60h]
0x1400c332d  mov     [rsp+78h+var_58], ebx
0x1400c3331  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400c3336  jmp     loc_1400C3132
```
