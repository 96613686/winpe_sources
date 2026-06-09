# xxxDisplayDiagBlackScreenDetected

- ea: `0x1401cc1f0`
- end: `0x1401cc7a9`
- name: `xxxDisplayDiagBlackScreenDetected`
- size: `1465`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x140111808`
- `0x1401618e8`

## callees

- `0x140003f28`
- `0x140012c80`
- `0x14002a0e4`
- `0x14002aa70`
- `0x14002ce98`
- `0x1400411c0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400bb7b0`
- `0x140111e68`
- `0x14013de9c`
- `0x140165e30`
- `0x1401940e0`
- `0x1401952f0`
- `0x1401cb610`
- `0x1401cc1f0`
- `0x1401f3668`
- `0x1401f37c0`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x1401cc3c3`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cc5c8`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cc3c3`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cc5c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401cc297`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401cc297`
- `ntoskrnl!ExUuidCreate` at `0x1401cc368`
- `ntoskrnl!ExUuidCreate` at `0x1401cc368`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc3d2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc5d7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc3d2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc5d7`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cc25b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cc300`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cc25b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cc300`
- `WIN32K!W32GetUserSessionState` at `0x1401cc248`
- `WIN32K!W32GetUserSessionState` at `0x1401cc275`
- `WIN32K!W32GetUserSessionState` at `0x1401cc2a3`
- `WIN32K!W32GetUserSessionState` at `0x1401cc320`
- `WIN32K!W32GetUserSessionState` at `0x1401cc398`
- `WIN32K!W32GetUserSessionState` at `0x1401cc3ad`
- `WIN32K!W32GetUserSessionState` at `0x1401cc414`
- `WIN32K!W32GetUserSessionState` at `0x1401cc4b6`
- `WIN32K!W32GetUserSessionState` at `0x1401cc59c`
- `WIN32K!W32GetUserSessionState` at `0x1401cc5b2`
- `WIN32K!W32GetUserSessionState` at `0x1401cc609`
- `WIN32K!W32GetUserSessionState` at `0x1401cc248`
- `WIN32K!W32GetUserSessionState` at `0x1401cc275`
- `WIN32K!W32GetUserSessionState` at `0x1401cc2a3`
- `WIN32K!W32GetUserSessionState` at `0x1401cc320`
- `WIN32K!W32GetUserSessionState` at `0x1401cc398`
- `WIN32K!W32GetUserSessionState` at `0x1401cc3ad`
- `WIN32K!W32GetUserSessionState` at `0x1401cc414`
- `WIN32K!W32GetUserSessionState` at `0x1401cc4b6`
- `WIN32K!W32GetUserSessionState` at `0x1401cc59c`
- `WIN32K!W32GetUserSessionState` at `0x1401cc5b2`
- `WIN32K!W32GetUserSessionState` at `0x1401cc609`

## pseudocode

```c
void __fastcall xxxDisplayDiagBlackScreenDetected(unsigned int a1, char a2, char a3, UUID *a4, int *a5)
{
  _OWORD *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 UserSessionState; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 UserGdiSessionState; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // r12d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // ebx
  UUID *p_Uuid; // rax
  UUID v36; // xmm6
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rax
  PEPROCESS ThreadProcess; // rax
  int ProcessImageFileName; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rbx
  __int64 v47; // rax
  int v48; // r15d
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rbx
  __int64 v53; // rax
  int v54; // esi
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  int v58; // ebx
  UUID *v59; // rax
  UUID v60; // xmm6
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rax
  PEPROCESS v65; // rax
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rbx
  __int64 v71; // rax
  PVOID v72; // rbx
  int v73; // r14d
  unsigned int v74; // edi
  __int64 v75; // rax
  int v76; // r9d
  int v77; // [rsp+30h] [rbp-B9h]
  __int16 v78; // [rsp+78h] [rbp-71h] BYREF
  __int16 v79; // [rsp+7Ah] [rbp-6Fh] BYREF
  unsigned int v80; // [rsp+7Ch] [rbp-6Dh] BYREF
  int v81; // [rsp+80h] [rbp-69h] BYREF
  int v82; // [rsp+84h] [rbp-65h] BYREF
  int v83; // [rsp+88h] [rbp-61h] BYREF
  __int64 v84; // [rsp+90h] [rbp-59h] BYREF
  UUID v85; // [rsp+98h] [rbp-51h] BYREF
  __int128 v86; // [rsp+A8h] [rbp-41h] BYREF
  PVOID Buffer[2]; // [rsp+B8h] [rbp-31h]
  char v88[8]; // [rsp+C8h] [rbp-21h] BYREF
  _OWORD *v89; // [rsp+D0h] [rbp-19h]
  UUID Uuid; // [rsp+D8h] [rbp-11h] BYREF

  LOBYTE(v78) = a3;
  v80 = a1;
  v88[0] = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v88, 0, 0xFu, a1);
  v7 = v89;
  UserSessionState = W32GetUserSessionState(v9, v8, v10);
  v84 = UserSessionState;
  UserGdiSessionState = W32GetUserGdiSessionState(v13, v12);
  v18 = 1;
  while ( *(_DWORD *)(UserGdiSessionState + 36) )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    v22 = W32GetUserSessionState(v20, v19, v21);
    KeWaitForSingleObject(*(PVOID *)(v22 + 68384), WrUserRequest, 0, 0, 0);
    v26 = W32GetUserSessionState(v24, v23, v25);
    v27 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v26,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v26 + 16) = v27;
    if ( v27 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v27) )
    {
      DestroySharedUserCritDeferredUnlockList(v26 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v26 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v26 + 19560);
    }
    UserGdiSessionState = W32GetUserGdiSessionState(v29, v28);
  }
  v86 = 0;
  *(_OWORD *)Buffer = 0;
  LOWORD(v86) = *(_WORD *)(W32GetUserSessionState(v16, v15, v17) + 68736);
  if ( !(unsigned int)UserIsWddmConnectedSession() )
    goto LABEL_41;
  if ( a2 )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    Uuid = 0;
    if ( !a4 && ExUuidCreate(&Uuid) < 0 )
      Uuid = 0;
    if ( a5 )
      v34 = *a5;
    else
      v34 = 0;
    p_Uuid = &Uuid;
    if ( a4 )
      p_Uuid = a4;
    v36 = *p_Uuid;
    if ( *(_QWORD *)(W32GetUserSessionState(v32, v31, v33) + 18984) )
    {
      v40 = W32GetUserSessionState(v38, v37, v39);
      ThreadProcess = PsGetThreadProcess(**(PETHREAD **)(v40 + 18984));
      ProcessImageFileName = PsGetProcessImageFileName(ThreadProcess);
    }
    else
    {
      ProcessImageFileName = 0;
    }
    v85 = v36;
    DrvDxgkCheckDisplayState(v80, 1, ProcessImageFileName, (_DWORD)v7, (__int64)&v85, v34);
    *(_OWORD *)(UserSessionState + 56752) = *v7;
    v46 = W32GetUserSessionState(v44, v43, v45);
    v47 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v46,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v46 + 16) = v47;
    if ( v47 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v47) )
    {
      DestroySharedUserCritDeferredUnlockList(v46 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v46 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v46 + 19560);
    }
  }
  if ( !(unsigned int)UserIsConsoleConnection(v30) || !(_BYTE)v78 )
  {
LABEL_41:
    v48 = DWORD2(v86);
    v18 = DWORD1(v86);
LABEL_42:
    v54 = HIDWORD(v86);
    goto LABEL_43;
  }
  DisplayDiagRecordActiveTopology((struct USER_DETECTED_BLACK_SCREEN_REPORT *)&v86);
  UserSessionSwitchLeaveCritWithNonPaged();
  Uuid.Data1 = 0;
  *(_DWORD *)&Uuid.Data2 = 26;
  v48 = DrvDxgkPollDisplayChildren(&Uuid);
  v52 = W32GetUserSessionState(v50, v49, v51);
  v53 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v52,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v52 + 16) = v53;
  if ( v53 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v53) )
  {
    DestroySharedUserCritDeferredUnlockList(v52 + 19520);
    DestroyDeferredUnlockObjectAssignmentList(v52 + 19576);
    DestroyDeferredUnlockObjectAssignmentList(v52 + 19560);
  }
  *v7 = *(_OWORD *)(v84 + 56752);
  if ( v48 < 0 )
    goto LABEL_42;
  LOBYTE(v77) = 0;
  LOBYTE(v79) = 0;
  v54 = xxxUserSetDisplayConfig(0, 0, 391, 128, 0, v77, 0, &v79, 0, v7, 0);
  if ( v54 >= 0 )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    v85 = 0;
    if ( a5 )
      v58 = *a5;
    else
      v58 = 0;
    v59 = &v85;
    if ( a4 )
      v59 = a4;
    v60 = *v59;
    if ( *(_QWORD *)(W32GetUserSessionState(v56, v55, v57) + 18984) )
    {
      v64 = W32GetUserSessionState(v62, v61, v63);
      v65 = PsGetThreadProcess(**(PETHREAD **)(v64 + 18984));
      v66 = PsGetProcessImageFileName(v65);
    }
    else
    {
      v66 = 0;
    }
    v85 = v60;
    DrvDxgkCheckDisplayState(v80, 0, v66, (_DWORD)v7, (__int64)&v85, v58);
    v70 = W32GetUserSessionState(v68, v67, v69);
    v71 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v70,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v70 + 16) = v71;
    if ( v71 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v71) )
    {
      DestroySharedUserCritDeferredUnlockList(v70 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v70 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v70 + 19560);
    }
  }
LABEL_43:
  v72 = Buffer[1];
  v73 = HIDWORD(Buffer[0]);
  if ( Buffer[1] )
    v74 = 216 * HIDWORD(Buffer[0]);
  else
    v74 = 0;
  if ( (unsigned int)UserIsConsoleConnection(v30)
    && (_BYTE)v78
    && (unsigned int)dword_140294E08 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_140294E08, 0x400000000008LL) )
  {
    v75 = _tlgWrapBinary<void,1>(&v85, v72, v74);
    LODWORD(v84) = Buffer[0];
    v79 = v86;
    v78 = 4;
    v81 = v73;
    v82 = v54;
    v83 = v48;
    Uuid.Data1 = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
      (unsigned int)&v80,
      (unsigned int)&byte_14026F947,
      (_DWORD)v7,
      v76,
      (__int64)&v78,
      (__int64)&Uuid,
      (__int64)&v79,
      (__int64)&v84,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v81,
      v75,
      (__int64)&v80);
  }
  if ( v72 )
    GreDeleteFastMutex(v72);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v88);
}

```

## disassembly

```asm
0x1401cc1f0  mov     rax, rsp
0x1401cc1f3  mov     [rax+10h], rbx
0x1401cc1f7  push    rbp
0x1401cc1f8  push    rsi
0x1401cc1f9  push    rdi
0x1401cc1fa  push    r12
0x1401cc1fc  push    r13
0x1401cc1fe  push    r14
0x1401cc200  push    r15
0x1401cc202  lea     rbp, [rax-57h]
0x1401cc206  sub     rsp, 100h
0x1401cc20d  movaps  xmmword ptr [rax-48h], xmm6
0x1401cc211  mov     rax, cs:__security_cookie
0x1401cc218  xor     rax, rsp
0x1401cc21b  mov     [rbp+4Fh+var_50], rax
0x1401cc21f  xor     edi, edi
0x1401cc221  mov     byte ptr [rbp+4Fh+var_C0], r8b
0x1401cc225  mov     r14, r9
0x1401cc228  mov     [rbp+4Fh+var_BC], ecx
0x1401cc22b  mov     sil, dl
0x1401cc22e  mov     [rbp+4Fh+var_70], dil
0x1401cc232  mov     r9d, ecx; unsigned int
0x1401cc235  xor     edx, edx; struct _GUID *
0x1401cc237  lea     r8d, [rdi+0Fh]; unsigned int
0x1401cc23b  lea     rcx, [rbp+4Fh+var_70]; this
0x1401cc23f  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401cc244  mov     r13, [rbp+4Fh+var_68]
0x1401cc248  call    cs:__imp_W32GetUserSessionState
0x1401cc24f  nop     dword ptr [rax+rax+00h]
0x1401cc254  mov     r15, rax
0x1401cc257  mov     [rbp+4Fh+var_A8], rax
0x1401cc25b  call    cs:__imp_W32GetUserGdiSessionState
0x1401cc262  nop     dword ptr [rax+rax+00h]
0x1401cc267  lea     r12d, [rdi+1]
0x1401cc26b  jmp     loc_1401CC30C
0x1401cc270  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cc275  call    cs:__imp_W32GetUserSessionState
0x1401cc27c  nop     dword ptr [rax+rax+00h]
0x1401cc281  xor     r9d, r9d; Alertable
0x1401cc284  mov     [rsp+130h+Timeout], rdi; Timeout
0x1401cc289  xor     r8d, r8d; WaitMode
0x1401cc28c  mov     rcx, [rax+10B20h]; Object
0x1401cc293  lea     edx, [r9+0Dh]; WaitReason
0x1401cc297  call    cs:__imp_KeWaitForSingleObject
0x1401cc29e  nop     dword ptr [rax+rax+00h]
0x1401cc2a3  call    cs:__imp_W32GetUserSessionState
0x1401cc2aa  nop     dword ptr [rax+rax+00h]
0x1401cc2af  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cc2b6  xor     r8d, r8d
0x1401cc2b9  mov     rcx, rax
0x1401cc2bc  mov     edx, r12d
0x1401cc2bf  mov     rbx, rax
0x1401cc2c2  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cc2c7  mov     [rbx+10h], rax
0x1401cc2cb  test    rax, rax
0x1401cc2ce  jz      short loc_1401CC300
0x1401cc2d0  mov     rcx, rax
0x1401cc2d3  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cc2d8  test    al, al
0x1401cc2da  jz      short loc_1401CC300
0x1401cc2dc  lea     rcx, [rbx+4C40h]
0x1401cc2e3  call    DestroySharedUserCritDeferredUnlockList
0x1401cc2e8  lea     rcx, [rbx+4C78h]
0x1401cc2ef  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc2f4  lea     rcx, [rbx+4C68h]
0x1401cc2fb  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc300  call    cs:__imp_W32GetUserGdiSessionState
0x1401cc307  nop     dword ptr [rax+rax+00h]
0x1401cc30c  cmp     [rax+24h], edi
0x1401cc30f  jnz     loc_1401CC270
0x1401cc315  xorps   xmm0, xmm0
0x1401cc318  movups  [rbp+4Fh+var_90], xmm0
0x1401cc31c  movups  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1401cc320  call    cs:__imp_W32GetUserSessionState
0x1401cc327  nop     dword ptr [rax+rax+00h]
0x1401cc32c  movzx   ecx, word ptr [rax+10C80h]
0x1401cc333  mov     word ptr [rbp+4Fh+var_90], cx
0x1401cc337  call    UserIsWddmConnectedSession
0x1401cc33c  test    eax, eax
0x1401cc33e  jz      loc_1401CC668
0x1401cc344  mov     rdi, [rbp+4Fh+arg_20]
0x1401cc348  test    sil, sil
0x1401cc34b  jz      loc_1401CC473
0x1401cc351  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cc356  xor     esi, esi
0x1401cc358  xorps   xmm0, xmm0
0x1401cc35b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401cc35f  test    r14, r14
0x1401cc362  jnz     short loc_1401CC37F
0x1401cc364  lea     rcx, [rbp+4Fh+Uuid]; Uuid
0x1401cc368  call    cs:__imp_ExUuidCreate
0x1401cc36f  nop     dword ptr [rax+rax+00h]
0x1401cc374  test    eax, eax
0x1401cc376  jns     short loc_1401CC37F
0x1401cc378  xorps   xmm0, xmm0
0x1401cc37b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401cc37f  test    rdi, rdi
0x1401cc382  jz      short loc_1401CC388
0x1401cc384  mov     ebx, [rdi]
0x1401cc386  jmp     short loc_1401CC38A
0x1401cc388  mov     ebx, esi
0x1401cc38a  test    r14, r14
0x1401cc38d  lea     rax, [rbp+4Fh+Uuid]
0x1401cc391  cmovnz  rax, r14
0x1401cc395  movups  xmm6, xmmword ptr [rax]
0x1401cc398  call    cs:__imp_W32GetUserSessionState
0x1401cc39f  nop     dword ptr [rax+rax+00h]
0x1401cc3a4  cmp     [rax+4A28h], rsi
0x1401cc3ab  jz      short loc_1401CC3E0
0x1401cc3ad  call    cs:__imp_W32GetUserSessionState
0x1401cc3b4  nop     dword ptr [rax+rax+00h]
0x1401cc3b9  mov     rcx, [rax+4A28h]
0x1401cc3c0  mov     rcx, [rcx]; Thread
0x1401cc3c3  call    cs:__imp_PsGetThreadProcess
0x1401cc3ca  nop     dword ptr [rax+rax+00h]
0x1401cc3cf  mov     rcx, rax
0x1401cc3d2  call    cs:__imp_PsGetProcessImageFileName
0x1401cc3d9  nop     dword ptr [rax+rax+00h]
0x1401cc3de  jmp     short loc_1401CC3E3
0x1401cc3e0  mov     rax, rsi
0x1401cc3e3  lea     rcx, [rbp+4Fh+var_A0]
0x1401cc3e7  mov     dword ptr [rsp+130h+var_108], ebx
0x1401cc3eb  mov     [rsp+130h+Timeout], rcx
0x1401cc3f0  mov     r9, r13
0x1401cc3f3  mov     ecx, [rbp+4Fh+var_BC]
0x1401cc3f6  mov     r8, rax
0x1401cc3f9  mov     edx, r12d
0x1401cc3fc  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401cc401  call    DrvDxgkCheckDisplayState
0x1401cc406  movups  xmm0, xmmword ptr [r13+0]
0x1401cc40b  movdqu  xmmword ptr [r15+0DDB0h], xmm0
0x1401cc414  call    cs:__imp_W32GetUserSessionState
0x1401cc41b  nop     dword ptr [rax+rax+00h]
0x1401cc420  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cc427  xor     r8d, r8d
0x1401cc42a  mov     rcx, rax
0x1401cc42d  mov     edx, r12d
0x1401cc430  mov     rbx, rax
0x1401cc433  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cc438  mov     [rbx+10h], rax
0x1401cc43c  test    rax, rax
0x1401cc43f  jz      short loc_1401CC475
0x1401cc441  mov     rcx, rax
0x1401cc444  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cc449  test    al, al
0x1401cc44b  jz      short loc_1401CC475
0x1401cc44d  lea     rcx, [rbx+4C40h]
0x1401cc454  call    DestroySharedUserCritDeferredUnlockList
0x1401cc459  lea     rcx, [rbx+4C78h]
0x1401cc460  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc465  lea     rcx, [rbx+4C68h]
0x1401cc46c  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc471  jmp     short loc_1401CC475
0x1401cc473  xor     esi, esi
0x1401cc475  call    UserIsConsoleConnection
0x1401cc47a  test    eax, eax
0x1401cc47c  jz      loc_1401CC668
0x1401cc482  cmp     byte ptr [rbp+4Fh+var_C0], sil
0x1401cc486  jz      loc_1401CC668
0x1401cc48c  lea     rcx, [rbp+4Fh+var_90]; struct USER_DETECTED_BLACK_SCREEN_REPORT *
0x1401cc490  call    ?DisplayDiagRecordActiveTopology@@YAXPEAUUSER_DETECTED_BLACK_SCREEN_REPORT@@@Z; DisplayDiagRecordActiveTopology(USER_DETECTED_BLACK_SCREEN_REPORT *)
0x1401cc495  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cc49a  mov     qword ptr [rbp+4Fh+Uuid.Data1], rsi
0x1401cc49e  lea     rcx, [rbp+4Fh+Uuid]
0x1401cc4a2  mov     eax, dword ptr [rbp+4Fh+Uuid.Data2]
0x1401cc4a5  and     eax, 0FFFFFFFAh
0x1401cc4a8  or      eax, 1Ah
0x1401cc4ab  mov     dword ptr [rbp+4Fh+Uuid.Data2], eax
0x1401cc4ae  call    DrvDxgkPollDisplayChildren
0x1401cc4b3  mov     r15d, eax
0x1401cc4b6  call    cs:__imp_W32GetUserSessionState
0x1401cc4bd  nop     dword ptr [rax+rax+00h]
0x1401cc4c2  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cc4c9  xor     r8d, r8d
0x1401cc4cc  mov     rcx, rax
0x1401cc4cf  mov     edx, r12d
0x1401cc4d2  mov     rbx, rax
0x1401cc4d5  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cc4da  mov     [rbx+10h], rax
0x1401cc4de  test    rax, rax
0x1401cc4e1  jz      short loc_1401CC513
0x1401cc4e3  mov     rcx, rax
0x1401cc4e6  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cc4eb  test    al, al
0x1401cc4ed  jz      short loc_1401CC513
0x1401cc4ef  lea     rcx, [rbx+4C40h]
0x1401cc4f6  call    DestroySharedUserCritDeferredUnlockList
0x1401cc4fb  lea     rcx, [rbx+4C78h]
0x1401cc502  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc507  lea     rcx, [rbx+4C68h]
0x1401cc50e  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc513  mov     rax, [rbp+4Fh+var_A8]
0x1401cc517  movups  xmm0, xmmword ptr [rax+0DDB0h]
0x1401cc51e  movdqu  xmmword ptr [r13+0], xmm0
0x1401cc524  test    r15d, r15d
0x1401cc527  js      loc_1401CC670
0x1401cc52d  mov     [rsp+130h+var_E0], rsi
0x1401cc532  lea     rax, [rbp+4Fh+var_BE]
0x1401cc536  mov     [rsp+130h+var_E8], r13
0x1401cc53b  xor     edx, edx
0x1401cc53d  mov     [rsp+130h+var_F0], rsi
0x1401cc542  xor     ecx, ecx
0x1401cc544  mov     [rsp+130h+var_F8], rax
0x1401cc549  mov     r9d, 80h
0x1401cc54f  mov     [rsp+130h+var_100], rsi
0x1401cc554  mov     r8d, 187h
0x1401cc55a  mov     byte ptr [rsp+130h+var_108], sil
0x1401cc55f  mov     [rsp+130h+Timeout], rsi
0x1401cc564  mov     byte ptr [rbp+4Fh+var_BE], sil
0x1401cc568  call    xxxUserSetDisplayConfig
0x1401cc56d  mov     esi, eax
0x1401cc56f  test    eax, eax
0x1401cc571  js      loc_1401CC673
0x1401cc577  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cc57c  xorps   xmm0, xmm0
0x1401cc57f  movups  [rbp+4Fh+var_A0], xmm0
0x1401cc583  test    rdi, rdi
0x1401cc586  jz      short loc_1401CC58C
0x1401cc588  mov     ebx, [rdi]
0x1401cc58a  jmp     short loc_1401CC58E
0x1401cc58c  xor     ebx, ebx
0x1401cc58e  test    r14, r14
0x1401cc591  lea     rax, [rbp+4Fh+var_A0]
0x1401cc595  cmovnz  rax, r14
0x1401cc599  movups  xmm6, xmmword ptr [rax]
0x1401cc59c  call    cs:__imp_W32GetUserSessionState
0x1401cc5a3  nop     dword ptr [rax+rax+00h]
0x1401cc5a8  cmp     qword ptr [rax+4A28h], 0
0x1401cc5b0  jz      short loc_1401CC5E5
0x1401cc5b2  call    cs:__imp_W32GetUserSessionState
0x1401cc5b9  nop     dword ptr [rax+rax+00h]
0x1401cc5be  mov     rcx, [rax+4A28h]
0x1401cc5c5  mov     rcx, [rcx]; Thread
0x1401cc5c8  call    cs:__imp_PsGetThreadProcess
0x1401cc5cf  nop     dword ptr [rax+rax+00h]
0x1401cc5d4  mov     rcx, rax
0x1401cc5d7  call    cs:__imp_PsGetProcessImageFileName
0x1401cc5de  nop     dword ptr [rax+rax+00h]
0x1401cc5e3  jmp     short loc_1401CC5E7
0x1401cc5e5  xor     eax, eax
0x1401cc5e7  lea     rcx, [rbp+4Fh+var_A0]
0x1401cc5eb  mov     dword ptr [rsp+130h+var_108], ebx
0x1401cc5ef  mov     [rsp+130h+Timeout], rcx
0x1401cc5f4  mov     r9, r13
0x1401cc5f7  mov     ecx, [rbp+4Fh+var_BC]
0x1401cc5fa  mov     r8, rax
0x1401cc5fd  xor     edx, edx
0x1401cc5ff  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401cc604  call    DrvDxgkCheckDisplayState
0x1401cc609  call    cs:__imp_W32GetUserSessionState
0x1401cc610  nop     dword ptr [rax+rax+00h]
0x1401cc615  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cc61c  xor     r8d, r8d
0x1401cc61f  mov     rcx, rax
0x1401cc622  mov     edx, r12d
0x1401cc625  mov     rbx, rax
0x1401cc628  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cc62d  mov     [rbx+10h], rax
0x1401cc631  test    rax, rax
0x1401cc634  jz      short loc_1401CC673
0x1401cc636  mov     rcx, rax
0x1401cc639  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cc63e  test    al, al
0x1401cc640  jz      short loc_1401CC673
0x1401cc642  lea     rcx, [rbx+4C40h]
0x1401cc649  call    DestroySharedUserCritDeferredUnlockList
0x1401cc64e  lea     rcx, [rbx+4C78h]
0x1401cc655  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc65a  lea     rcx, [rbx+4C68h]
0x1401cc661  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc666  jmp     short loc_1401CC673
0x1401cc668  mov     r15d, dword ptr [rbp+4Fh+var_90+8]
0x1401cc66c  mov     r12d, dword ptr [rbp+4Fh+var_90+4]
0x1401cc670  mov     esi, dword ptr [rbp+4Fh+var_90+0Ch]
0x1401cc673  mov     rbx, [rbp+4Fh+Buffer+8]
0x1401cc677  mov     r14d, dword ptr [rbp+4Fh+Buffer+4]
0x1401cc67b  test    rbx, rbx
0x1401cc67e  jnz     short loc_1401CC684
0x1401cc680  xor     edi, edi
0x1401cc682  jmp     short loc_1401CC68B
0x1401cc684  imul    edi, r14d, 0D8h
0x1401cc68b  call    UserIsConsoleConnection
0x1401cc690  test    eax, eax
0x1401cc692  jz      loc_1401CC766
0x1401cc698  cmp     byte ptr [rbp+4Fh+var_C0], 0
0x1401cc69c  jz      loc_1401CC766
0x1401cc6a2  mov     eax, cs:dword_140294E08
0x1401cc6a8  cmp     eax, 5
0x1401cc6ab  jbe     loc_1401CC766
0x1401cc6b1  mov     rdx, 400000000008h
0x1401cc6bb  lea     rcx, dword_140294E08
0x1401cc6c2  call    _tlgKeywordOn
0x1401cc6c7  test    al, al
0x1401cc6c9  jz      loc_1401CC766
0x1401cc6cf  mov     eax, [rbp+4Fh+var_BC]
0x1401cc6d2  lea     rcx, [rbp+4Fh+var_A0]
0x1401cc6d6  mov     r8d, edi
0x1401cc6d9  mov     rdx, rbx
0x1401cc6dc  mov     [rbp+4Fh+var_BC], eax
0x1401cc6df  call    ??$_tlgWrapBinary@X$00@@YA?AU?$_tlgWrapperArray@$00@@PEBX_K@Z; _tlgWrapBinary<void,1>(void const *,unsigned __int64)
  ... truncated ...
```
