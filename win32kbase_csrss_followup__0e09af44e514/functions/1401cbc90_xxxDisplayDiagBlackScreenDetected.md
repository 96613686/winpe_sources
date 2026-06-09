# xxxDisplayDiagBlackScreenDetected

- ea: `0x1401cbc90`
- end: `0x1401cc249`
- name: `xxxDisplayDiagBlackScreenDetected`
- size: `1465`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x140111338`
- `0x140162188`

## callees

- `0x140003f28`
- `0x14001bdf0`
- `0x140033364`
- `0x140033cf0`
- `0x140036118`
- `0x14004a0d0`
- `0x140078090`
- `0x140078120`
- `0x1400ae870`
- `0x140111998`
- `0x14013e47c`
- `0x1401666d0`
- `0x140194210`
- `0x140195420`
- `0x1401cb0b0`
- `0x1401cbc90`
- `0x1401f2ea8`
- `0x1401f3000`
- `0x140238160`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x1401cbe63`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cc068`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cbe63`
- `ntoskrnl!PsGetThreadProcess` at `0x1401cc068`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401cbd37`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401cbd37`
- `ntoskrnl!ExUuidCreate` at `0x1401cbe08`
- `ntoskrnl!ExUuidCreate` at `0x1401cbe08`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cbe72`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc077`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cbe72`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401cc077`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cbcfb`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cbda0`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cbcfb`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cbda0`
- `WIN32K!W32GetUserSessionState` at `0x1401cbce8`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd15`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd43`
- `WIN32K!W32GetUserSessionState` at `0x1401cbdc0`
- `WIN32K!W32GetUserSessionState` at `0x1401cbe38`
- `WIN32K!W32GetUserSessionState` at `0x1401cbe4d`
- `WIN32K!W32GetUserSessionState` at `0x1401cbeb4`
- `WIN32K!W32GetUserSessionState` at `0x1401cbf56`
- `WIN32K!W32GetUserSessionState` at `0x1401cc03c`
- `WIN32K!W32GetUserSessionState` at `0x1401cc052`
- `WIN32K!W32GetUserSessionState` at `0x1401cc0a9`
- `WIN32K!W32GetUserSessionState` at `0x1401cbce8`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd15`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd43`
- `WIN32K!W32GetUserSessionState` at `0x1401cbdc0`
- `WIN32K!W32GetUserSessionState` at `0x1401cbe38`
- `WIN32K!W32GetUserSessionState` at `0x1401cbe4d`
- `WIN32K!W32GetUserSessionState` at `0x1401cbeb4`
- `WIN32K!W32GetUserSessionState` at `0x1401cbf56`
- `WIN32K!W32GetUserSessionState` at `0x1401cc03c`
- `WIN32K!W32GetUserSessionState` at `0x1401cc052`
- `WIN32K!W32GetUserSessionState` at `0x1401cc0a9`

## pseudocode

```c
void __fastcall xxxDisplayDiagBlackScreenDetected(unsigned int a1, char a2, char a3, UUID *a4, int *a5)
{
  _OWORD *v7; // r13
  __int64 v8; // rcx
  __int64 UserSessionState; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 UserGdiSessionState; // rax
  __int64 v13; // rcx
  unsigned int v14; // r12d
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // ebx
  UUID *p_Uuid; // rax
  UUID v26; // xmm6
  __int64 v27; // rcx
  __int64 v28; // rax
  PEPROCESS ThreadProcess; // rax
  int ProcessImageFileName; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  int v34; // r15d
  __int64 v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // esi
  __int64 v39; // rcx
  int v40; // ebx
  UUID *v41; // rax
  UUID v42; // xmm6
  __int64 v43; // rcx
  __int64 v44; // rax
  PEPROCESS v45; // rax
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rax
  PVOID v50; // rbx
  int v51; // r14d
  unsigned int v52; // edi
  __int64 v53; // rax
  int v54; // r9d
  int v55; // [rsp+30h] [rbp-B9h]
  __int16 v56; // [rsp+78h] [rbp-71h] BYREF
  __int16 v57; // [rsp+7Ah] [rbp-6Fh] BYREF
  unsigned int v58; // [rsp+7Ch] [rbp-6Dh] BYREF
  int v59; // [rsp+80h] [rbp-69h] BYREF
  int v60; // [rsp+84h] [rbp-65h] BYREF
  int v61; // [rsp+88h] [rbp-61h] BYREF
  __int64 v62; // [rsp+90h] [rbp-59h] BYREF
  UUID v63; // [rsp+98h] [rbp-51h] BYREF
  __int128 v64; // [rsp+A8h] [rbp-41h] BYREF
  PVOID Buffer[2]; // [rsp+B8h] [rbp-31h]
  char v66[8]; // [rsp+C8h] [rbp-21h] BYREF
  _OWORD *v67; // [rsp+D0h] [rbp-19h]
  UUID Uuid; // [rsp+D8h] [rbp-11h] BYREF

  LOBYTE(v56) = a3;
  v58 = a1;
  v66[0] = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v66, 0, 0xFu, a1);
  v7 = v67;
  UserSessionState = W32GetUserSessionState(v8);
  v62 = UserSessionState;
  UserGdiSessionState = W32GetUserGdiSessionState(v11, v10);
  v14 = 1;
  while ( *(_DWORD *)(UserGdiSessionState + 36) )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    v16 = W32GetUserSessionState(v15);
    KeWaitForSingleObject(*(PVOID *)(v16 + 68384), WrUserRequest, 0, 0, 0);
    v18 = W32GetUserSessionState(v17);
    v19 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v18,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v18 + 16) = v19;
    if ( v19 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v19) )
    {
      DestroySharedUserCritDeferredUnlockList(v18 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v18 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v18 + 19560);
    }
    UserGdiSessionState = W32GetUserGdiSessionState(v21, v20);
  }
  v64 = 0;
  *(_OWORD *)Buffer = 0;
  LOWORD(v64) = *(_WORD *)(W32GetUserSessionState(v13) + 68736);
  if ( !(unsigned int)UserIsWddmConnectedSession() )
    goto LABEL_41;
  if ( a2 )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    Uuid = 0;
    if ( !a4 && ExUuidCreate(&Uuid) < 0 )
      Uuid = 0;
    if ( a5 )
      v24 = *a5;
    else
      v24 = 0;
    p_Uuid = &Uuid;
    if ( a4 )
      p_Uuid = a4;
    v26 = *p_Uuid;
    if ( *(_QWORD *)(W32GetUserSessionState(v23) + 18984) )
    {
      v28 = W32GetUserSessionState(v27);
      ThreadProcess = PsGetThreadProcess(**(PETHREAD **)(v28 + 18984));
      ProcessImageFileName = PsGetProcessImageFileName(ThreadProcess);
    }
    else
    {
      ProcessImageFileName = 0;
    }
    v63 = v26;
    DrvDxgkCheckDisplayState(v58, 1, ProcessImageFileName, (_DWORD)v7, (__int64)&v63, v24);
    *(_OWORD *)(UserSessionState + 56752) = *v7;
    v32 = W32GetUserSessionState(v31);
    v33 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v32,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v32 + 16) = v33;
    if ( v33 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v33) )
    {
      DestroySharedUserCritDeferredUnlockList(v32 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v32 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v32 + 19560);
    }
  }
  if ( !(unsigned int)UserIsConsoleConnection(v22) || !(_BYTE)v56 )
  {
LABEL_41:
    v34 = DWORD2(v64);
    v14 = DWORD1(v64);
LABEL_42:
    v38 = HIDWORD(v64);
    goto LABEL_43;
  }
  DisplayDiagRecordActiveTopology((struct USER_DETECTED_BLACK_SCREEN_REPORT *)&v64);
  UserSessionSwitchLeaveCritWithNonPaged();
  Uuid.Data1 = 0;
  *(_DWORD *)&Uuid.Data2 = 26;
  v34 = DrvDxgkPollDisplayChildren(&Uuid);
  v36 = W32GetUserSessionState(v35);
  v37 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v36,
          1,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(v36 + 16) = v37;
  if ( v37 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v37) )
  {
    DestroySharedUserCritDeferredUnlockList(v36 + 19520);
    DestroyDeferredUnlockObjectAssignmentList(v36 + 19576);
    DestroyDeferredUnlockObjectAssignmentList(v36 + 19560);
  }
  *v7 = *(_OWORD *)(v62 + 56752);
  if ( v34 < 0 )
    goto LABEL_42;
  LOBYTE(v55) = 0;
  LOBYTE(v57) = 0;
  v38 = xxxUserSetDisplayConfig(0, 0, 391, 128, 0, v55, 0, &v57, 0, v7, 0);
  if ( v38 >= 0 )
  {
    UserSessionSwitchLeaveCritWithNonPaged();
    v63 = 0;
    if ( a5 )
      v40 = *a5;
    else
      v40 = 0;
    v41 = &v63;
    if ( a4 )
      v41 = a4;
    v42 = *v41;
    if ( *(_QWORD *)(W32GetUserSessionState(v39) + 18984) )
    {
      v44 = W32GetUserSessionState(v43);
      v45 = PsGetThreadProcess(**(PETHREAD **)(v44 + 18984));
      v46 = PsGetProcessImageFileName(v45);
    }
    else
    {
      v46 = 0;
    }
    v63 = v42;
    DrvDxgkCheckDisplayState(v58, 0, v46, (_DWORD)v7, (__int64)&v63, v40);
    v48 = W32GetUserSessionState(v47);
    v49 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v48,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v48 + 16) = v49;
    if ( v49 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v49) )
    {
      DestroySharedUserCritDeferredUnlockList(v48 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v48 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v48 + 19560);
    }
  }
LABEL_43:
  v50 = Buffer[1];
  v51 = HIDWORD(Buffer[0]);
  if ( Buffer[1] )
    v52 = 216 * HIDWORD(Buffer[0]);
  else
    v52 = 0;
  if ( (unsigned int)UserIsConsoleConnection(v22)
    && (_BYTE)v56
    && (unsigned int)dword_140292E08 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_140292E08, 0x400000000008LL) )
  {
    v53 = _tlgWrapBinary<void,1>(&v63, v50, v52);
    LODWORD(v62) = Buffer[0];
    v57 = v64;
    v56 = 4;
    v59 = v51;
    v60 = v38;
    v61 = v34;
    Uuid.Data1 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
      (unsigned int)&v58,
      (unsigned int)&byte_14026E7C7,
      (_DWORD)v7,
      v54,
      (__int64)&v56,
      (__int64)&Uuid,
      (__int64)&v57,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v60,
      (__int64)&v59,
      v53,
      (__int64)&v58);
  }
  if ( v50 )
    GreDeleteFastMutex(v50);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v66);
}

```

## disassembly

```asm
0x1401cbc90  mov     rax, rsp
0x1401cbc93  mov     [rax+10h], rbx
0x1401cbc97  push    rbp
0x1401cbc98  push    rsi
0x1401cbc99  push    rdi
0x1401cbc9a  push    r12
0x1401cbc9c  push    r13
0x1401cbc9e  push    r14
0x1401cbca0  push    r15
0x1401cbca2  lea     rbp, [rax-57h]
0x1401cbca6  sub     rsp, 100h
0x1401cbcad  movaps  xmmword ptr [rax-48h], xmm6
0x1401cbcb1  mov     rax, cs:__security_cookie
0x1401cbcb8  xor     rax, rsp
0x1401cbcbb  mov     [rbp+4Fh+var_50], rax
0x1401cbcbf  xor     edi, edi
0x1401cbcc1  mov     byte ptr [rbp+4Fh+var_C0], r8b
0x1401cbcc5  mov     r14, r9
0x1401cbcc8  mov     [rbp+4Fh+var_BC], ecx
0x1401cbccb  mov     sil, dl
0x1401cbcce  mov     [rbp+4Fh+var_70], dil
0x1401cbcd2  mov     r9d, ecx; unsigned int
0x1401cbcd5  xor     edx, edx; struct _GUID *
0x1401cbcd7  lea     r8d, [rdi+0Fh]; unsigned int
0x1401cbcdb  lea     rcx, [rbp+4Fh+var_70]; this
0x1401cbcdf  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401cbce4  mov     r13, [rbp+4Fh+var_68]
0x1401cbce8  call    cs:__imp_W32GetUserSessionState
0x1401cbcef  nop     dword ptr [rax+rax+00h]
0x1401cbcf4  mov     r15, rax
0x1401cbcf7  mov     [rbp+4Fh+var_A8], rax
0x1401cbcfb  call    cs:__imp_W32GetUserGdiSessionState
0x1401cbd02  nop     dword ptr [rax+rax+00h]
0x1401cbd07  lea     r12d, [rdi+1]
0x1401cbd0b  jmp     loc_1401CBDAC
0x1401cbd10  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cbd15  call    cs:__imp_W32GetUserSessionState
0x1401cbd1c  nop     dword ptr [rax+rax+00h]
0x1401cbd21  xor     r9d, r9d; Alertable
0x1401cbd24  mov     [rsp+130h+Timeout], rdi; Timeout
0x1401cbd29  xor     r8d, r8d; WaitMode
0x1401cbd2c  mov     rcx, [rax+10B20h]; Object
0x1401cbd33  lea     edx, [r9+0Dh]; WaitReason
0x1401cbd37  call    cs:__imp_KeWaitForSingleObject
0x1401cbd3e  nop     dword ptr [rax+rax+00h]
0x1401cbd43  call    cs:__imp_W32GetUserSessionState
0x1401cbd4a  nop     dword ptr [rax+rax+00h]
0x1401cbd4f  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cbd56  xor     r8d, r8d
0x1401cbd59  mov     rcx, rax
0x1401cbd5c  mov     edx, r12d
0x1401cbd5f  mov     rbx, rax
0x1401cbd62  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cbd67  mov     [rbx+10h], rax
0x1401cbd6b  test    rax, rax
0x1401cbd6e  jz      short loc_1401CBDA0
0x1401cbd70  mov     rcx, rax
0x1401cbd73  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cbd78  test    al, al
0x1401cbd7a  jz      short loc_1401CBDA0
0x1401cbd7c  lea     rcx, [rbx+4C40h]
0x1401cbd83  call    DestroySharedUserCritDeferredUnlockList
0x1401cbd88  lea     rcx, [rbx+4C78h]
0x1401cbd8f  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbd94  lea     rcx, [rbx+4C68h]
0x1401cbd9b  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbda0  call    cs:__imp_W32GetUserGdiSessionState
0x1401cbda7  nop     dword ptr [rax+rax+00h]
0x1401cbdac  cmp     [rax+24h], edi
0x1401cbdaf  jnz     loc_1401CBD10
0x1401cbdb5  xorps   xmm0, xmm0
0x1401cbdb8  movups  [rbp+4Fh+var_90], xmm0
0x1401cbdbc  movups  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1401cbdc0  call    cs:__imp_W32GetUserSessionState
0x1401cbdc7  nop     dword ptr [rax+rax+00h]
0x1401cbdcc  movzx   ecx, word ptr [rax+10C80h]
0x1401cbdd3  mov     word ptr [rbp+4Fh+var_90], cx
0x1401cbdd7  call    UserIsWddmConnectedSession
0x1401cbddc  test    eax, eax
0x1401cbdde  jz      loc_1401CC108
0x1401cbde4  mov     rdi, [rbp+4Fh+arg_20]
0x1401cbde8  test    sil, sil
0x1401cbdeb  jz      loc_1401CBF13
0x1401cbdf1  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cbdf6  xor     esi, esi
0x1401cbdf8  xorps   xmm0, xmm0
0x1401cbdfb  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401cbdff  test    r14, r14
0x1401cbe02  jnz     short loc_1401CBE1F
0x1401cbe04  lea     rcx, [rbp+4Fh+Uuid]; Uuid
0x1401cbe08  call    cs:__imp_ExUuidCreate
0x1401cbe0f  nop     dword ptr [rax+rax+00h]
0x1401cbe14  test    eax, eax
0x1401cbe16  jns     short loc_1401CBE1F
0x1401cbe18  xorps   xmm0, xmm0
0x1401cbe1b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401cbe1f  test    rdi, rdi
0x1401cbe22  jz      short loc_1401CBE28
0x1401cbe24  mov     ebx, [rdi]
0x1401cbe26  jmp     short loc_1401CBE2A
0x1401cbe28  mov     ebx, esi
0x1401cbe2a  test    r14, r14
0x1401cbe2d  lea     rax, [rbp+4Fh+Uuid]
0x1401cbe31  cmovnz  rax, r14
0x1401cbe35  movups  xmm6, xmmword ptr [rax]
0x1401cbe38  call    cs:__imp_W32GetUserSessionState
0x1401cbe3f  nop     dword ptr [rax+rax+00h]
0x1401cbe44  cmp     [rax+4A28h], rsi
0x1401cbe4b  jz      short loc_1401CBE80
0x1401cbe4d  call    cs:__imp_W32GetUserSessionState
0x1401cbe54  nop     dword ptr [rax+rax+00h]
0x1401cbe59  mov     rcx, [rax+4A28h]
0x1401cbe60  mov     rcx, [rcx]; Thread
0x1401cbe63  call    cs:__imp_PsGetThreadProcess
0x1401cbe6a  nop     dword ptr [rax+rax+00h]
0x1401cbe6f  mov     rcx, rax
0x1401cbe72  call    cs:__imp_PsGetProcessImageFileName
0x1401cbe79  nop     dword ptr [rax+rax+00h]
0x1401cbe7e  jmp     short loc_1401CBE83
0x1401cbe80  mov     rax, rsi
0x1401cbe83  lea     rcx, [rbp+4Fh+var_A0]
0x1401cbe87  mov     dword ptr [rsp+130h+var_108], ebx
0x1401cbe8b  mov     [rsp+130h+Timeout], rcx
0x1401cbe90  mov     r9, r13
0x1401cbe93  mov     ecx, [rbp+4Fh+var_BC]
0x1401cbe96  mov     r8, rax
0x1401cbe99  mov     edx, r12d
0x1401cbe9c  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401cbea1  call    DrvDxgkCheckDisplayState
0x1401cbea6  movups  xmm0, xmmword ptr [r13+0]
0x1401cbeab  movdqu  xmmword ptr [r15+0DDB0h], xmm0
0x1401cbeb4  call    cs:__imp_W32GetUserSessionState
0x1401cbebb  nop     dword ptr [rax+rax+00h]
0x1401cbec0  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cbec7  xor     r8d, r8d
0x1401cbeca  mov     rcx, rax
0x1401cbecd  mov     edx, r12d
0x1401cbed0  mov     rbx, rax
0x1401cbed3  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cbed8  mov     [rbx+10h], rax
0x1401cbedc  test    rax, rax
0x1401cbedf  jz      short loc_1401CBF15
0x1401cbee1  mov     rcx, rax
0x1401cbee4  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cbee9  test    al, al
0x1401cbeeb  jz      short loc_1401CBF15
0x1401cbeed  lea     rcx, [rbx+4C40h]
0x1401cbef4  call    DestroySharedUserCritDeferredUnlockList
0x1401cbef9  lea     rcx, [rbx+4C78h]
0x1401cbf00  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbf05  lea     rcx, [rbx+4C68h]
0x1401cbf0c  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbf11  jmp     short loc_1401CBF15
0x1401cbf13  xor     esi, esi
0x1401cbf15  call    UserIsConsoleConnection
0x1401cbf1a  test    eax, eax
0x1401cbf1c  jz      loc_1401CC108
0x1401cbf22  cmp     byte ptr [rbp+4Fh+var_C0], sil
0x1401cbf26  jz      loc_1401CC108
0x1401cbf2c  lea     rcx, [rbp+4Fh+var_90]; struct USER_DETECTED_BLACK_SCREEN_REPORT *
0x1401cbf30  call    ?DisplayDiagRecordActiveTopology@@YAXPEAUUSER_DETECTED_BLACK_SCREEN_REPORT@@@Z; DisplayDiagRecordActiveTopology(USER_DETECTED_BLACK_SCREEN_REPORT *)
0x1401cbf35  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cbf3a  mov     qword ptr [rbp+4Fh+Uuid.Data1], rsi
0x1401cbf3e  lea     rcx, [rbp+4Fh+Uuid]
0x1401cbf42  mov     eax, dword ptr [rbp+4Fh+Uuid.Data2]
0x1401cbf45  and     eax, 0FFFFFFFAh
0x1401cbf48  or      eax, 1Ah
0x1401cbf4b  mov     dword ptr [rbp+4Fh+Uuid.Data2], eax
0x1401cbf4e  call    DrvDxgkPollDisplayChildren
0x1401cbf53  mov     r15d, eax
0x1401cbf56  call    cs:__imp_W32GetUserSessionState
0x1401cbf5d  nop     dword ptr [rax+rax+00h]
0x1401cbf62  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cbf69  xor     r8d, r8d
0x1401cbf6c  mov     rcx, rax
0x1401cbf6f  mov     edx, r12d
0x1401cbf72  mov     rbx, rax
0x1401cbf75  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cbf7a  mov     [rbx+10h], rax
0x1401cbf7e  test    rax, rax
0x1401cbf81  jz      short loc_1401CBFB3
0x1401cbf83  mov     rcx, rax
0x1401cbf86  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cbf8b  test    al, al
0x1401cbf8d  jz      short loc_1401CBFB3
0x1401cbf8f  lea     rcx, [rbx+4C40h]
0x1401cbf96  call    DestroySharedUserCritDeferredUnlockList
0x1401cbf9b  lea     rcx, [rbx+4C78h]
0x1401cbfa2  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbfa7  lea     rcx, [rbx+4C68h]
0x1401cbfae  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbfb3  mov     rax, [rbp+4Fh+var_A8]
0x1401cbfb7  movups  xmm0, xmmword ptr [rax+0DDB0h]
0x1401cbfbe  movdqu  xmmword ptr [r13+0], xmm0
0x1401cbfc4  test    r15d, r15d
0x1401cbfc7  js      loc_1401CC110
0x1401cbfcd  mov     [rsp+130h+var_E0], rsi
0x1401cbfd2  lea     rax, [rbp+4Fh+var_BE]
0x1401cbfd6  mov     [rsp+130h+var_E8], r13
0x1401cbfdb  xor     edx, edx
0x1401cbfdd  mov     [rsp+130h+var_F0], rsi
0x1401cbfe2  xor     ecx, ecx
0x1401cbfe4  mov     [rsp+130h+var_F8], rax
0x1401cbfe9  mov     r9d, 80h
0x1401cbfef  mov     [rsp+130h+var_100], rsi
0x1401cbff4  mov     r8d, 187h
0x1401cbffa  mov     byte ptr [rsp+130h+var_108], sil
0x1401cbfff  mov     [rsp+130h+Timeout], rsi
0x1401cc004  mov     byte ptr [rbp+4Fh+var_BE], sil
0x1401cc008  call    xxxUserSetDisplayConfig
0x1401cc00d  mov     esi, eax
0x1401cc00f  test    eax, eax
0x1401cc011  js      loc_1401CC113
0x1401cc017  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cc01c  xorps   xmm0, xmm0
0x1401cc01f  movups  [rbp+4Fh+var_A0], xmm0
0x1401cc023  test    rdi, rdi
0x1401cc026  jz      short loc_1401CC02C
0x1401cc028  mov     ebx, [rdi]
0x1401cc02a  jmp     short loc_1401CC02E
0x1401cc02c  xor     ebx, ebx
0x1401cc02e  test    r14, r14
0x1401cc031  lea     rax, [rbp+4Fh+var_A0]
0x1401cc035  cmovnz  rax, r14
0x1401cc039  movups  xmm6, xmmword ptr [rax]
0x1401cc03c  call    cs:__imp_W32GetUserSessionState
0x1401cc043  nop     dword ptr [rax+rax+00h]
0x1401cc048  cmp     qword ptr [rax+4A28h], 0
0x1401cc050  jz      short loc_1401CC085
0x1401cc052  call    cs:__imp_W32GetUserSessionState
0x1401cc059  nop     dword ptr [rax+rax+00h]
0x1401cc05e  mov     rcx, [rax+4A28h]
0x1401cc065  mov     rcx, [rcx]; Thread
0x1401cc068  call    cs:__imp_PsGetThreadProcess
0x1401cc06f  nop     dword ptr [rax+rax+00h]
0x1401cc074  mov     rcx, rax
0x1401cc077  call    cs:__imp_PsGetProcessImageFileName
0x1401cc07e  nop     dword ptr [rax+rax+00h]
0x1401cc083  jmp     short loc_1401CC087
0x1401cc085  xor     eax, eax
0x1401cc087  lea     rcx, [rbp+4Fh+var_A0]
0x1401cc08b  mov     dword ptr [rsp+130h+var_108], ebx
0x1401cc08f  mov     [rsp+130h+Timeout], rcx
0x1401cc094  mov     r9, r13
0x1401cc097  mov     ecx, [rbp+4Fh+var_BC]
0x1401cc09a  mov     r8, rax
0x1401cc09d  xor     edx, edx
0x1401cc09f  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401cc0a4  call    DrvDxgkCheckDisplayState
0x1401cc0a9  call    cs:__imp_W32GetUserSessionState
0x1401cc0b0  nop     dword ptr [rax+rax+00h]
0x1401cc0b5  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cc0bc  xor     r8d, r8d
0x1401cc0bf  mov     rcx, rax
0x1401cc0c2  mov     edx, r12d
0x1401cc0c5  mov     rbx, rax
0x1401cc0c8  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cc0cd  mov     [rbx+10h], rax
0x1401cc0d1  test    rax, rax
0x1401cc0d4  jz      short loc_1401CC113
0x1401cc0d6  mov     rcx, rax
0x1401cc0d9  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cc0de  test    al, al
0x1401cc0e0  jz      short loc_1401CC113
0x1401cc0e2  lea     rcx, [rbx+4C40h]
0x1401cc0e9  call    DestroySharedUserCritDeferredUnlockList
0x1401cc0ee  lea     rcx, [rbx+4C78h]
0x1401cc0f5  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc0fa  lea     rcx, [rbx+4C68h]
0x1401cc101  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cc106  jmp     short loc_1401CC113
0x1401cc108  mov     r15d, dword ptr [rbp+4Fh+var_90+8]
0x1401cc10c  mov     r12d, dword ptr [rbp+4Fh+var_90+4]
0x1401cc110  mov     esi, dword ptr [rbp+4Fh+var_90+0Ch]
0x1401cc113  mov     rbx, [rbp+4Fh+Buffer+8]
0x1401cc117  mov     r14d, dword ptr [rbp+4Fh+Buffer+4]
0x1401cc11b  test    rbx, rbx
0x1401cc11e  jnz     short loc_1401CC124
0x1401cc120  xor     edi, edi
0x1401cc122  jmp     short loc_1401CC12B
0x1401cc124  imul    edi, r14d, 0D8h
0x1401cc12b  call    UserIsConsoleConnection
0x1401cc130  test    eax, eax
0x1401cc132  jz      loc_1401CC206
0x1401cc138  cmp     byte ptr [rbp+4Fh+var_C0], 0
0x1401cc13c  jz      loc_1401CC206
0x1401cc142  mov     eax, cs:dword_140292E08
0x1401cc148  cmp     eax, 5
0x1401cc14b  jbe     loc_1401CC206
0x1401cc151  mov     rdx, 400000000008h
0x1401cc15b  lea     rcx, dword_140292E08
0x1401cc162  call    _tlgKeywordOn
0x1401cc167  test    al, al
0x1401cc169  jz      loc_1401CC206
0x1401cc16f  mov     eax, [rbp+4Fh+var_BC]
0x1401cc172  lea     rcx, [rbp+4Fh+var_A0]
0x1401cc176  mov     r8d, edi
0x1401cc179  mov     rdx, rbx
0x1401cc17c  mov     [rbp+4Fh+var_BC], eax
0x1401cc17f  call    ??$_tlgWrapBinary@X$00@@YA?AU?$_tlgWrapperArray@$00@@PEBX_K@Z; _tlgWrapBinary<void,1>(void const *,unsigned __int64)
  ... truncated ...
```
