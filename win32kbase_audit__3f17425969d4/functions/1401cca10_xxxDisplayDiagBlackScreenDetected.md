# xxxDisplayDiagBlackScreenDetected

- ea: `0x1401cca10`
- end: `0x1401ccfc9`
- name: `xxxDisplayDiagBlackScreenDetected`
- size: `1465`
- prototype: `void __fastcall(unsigned int, char, char, UUID *, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1401141a8`
- `0x140164758`

## callees

- `0x140003f28`
- `0x140029710`
- `0x14004f4c0`
- `0x14004f550`
- `0x14006e970`
- `0x1400701d4`
- `0x14007b930`
- `0x1400962b0`
- `0x1400d7988`
- `0x140114808`
- `0x14014065c`
- `0x140168d30`
- `0x140196d30`
- `0x140197a80`
- `0x1401cbe80`
- `0x1401cca10`
- `0x1401f3708`
- `0x1401f3860`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x1401ccbe3`
- `ntoskrnl!PsGetThreadProcess` at `0x1401ccde8`
- `ntoskrnl!PsGetThreadProcess` at `0x1401ccbe3`
- `ntoskrnl!PsGetThreadProcess` at `0x1401ccde8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401ccab7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401ccab7`
- `ntoskrnl!ExUuidCreate` at `0x1401ccb88`
- `ntoskrnl!ExUuidCreate` at `0x1401ccb88`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401ccbf2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401ccdf7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401ccbf2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401ccdf7`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cca7b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ccb20`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401cca7b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ccb20`
- `WIN32K!W32GetUserSessionState` at `0x1401cca68`
- `WIN32K!W32GetUserSessionState` at `0x1401cca95`
- `WIN32K!W32GetUserSessionState` at `0x1401ccac3`
- `WIN32K!W32GetUserSessionState` at `0x1401ccb40`
- `WIN32K!W32GetUserSessionState` at `0x1401ccbb8`
- `WIN32K!W32GetUserSessionState` at `0x1401ccbcd`
- `WIN32K!W32GetUserSessionState` at `0x1401ccc34`
- `WIN32K!W32GetUserSessionState` at `0x1401cccd6`
- `WIN32K!W32GetUserSessionState` at `0x1401ccdbc`
- `WIN32K!W32GetUserSessionState` at `0x1401ccdd2`
- `WIN32K!W32GetUserSessionState` at `0x1401cce29`
- `WIN32K!W32GetUserSessionState` at `0x1401cca68`
- `WIN32K!W32GetUserSessionState` at `0x1401cca95`
- `WIN32K!W32GetUserSessionState` at `0x1401ccac3`
- `WIN32K!W32GetUserSessionState` at `0x1401ccb40`
- `WIN32K!W32GetUserSessionState` at `0x1401ccbb8`
- `WIN32K!W32GetUserSessionState` at `0x1401ccbcd`
- `WIN32K!W32GetUserSessionState` at `0x1401ccc34`
- `WIN32K!W32GetUserSessionState` at `0x1401cccd6`
- `WIN32K!W32GetUserSessionState` at `0x1401ccdbc`
- `WIN32K!W32GetUserSessionState` at `0x1401ccdd2`
- `WIN32K!W32GetUserSessionState` at `0x1401cce29`

## pseudocode

```c
void __fastcall xxxDisplayDiagBlackScreenDetected(unsigned int a1, char a2, char a3, UUID *a4, int *a5)
{
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 UserSessionState; // r15
  __int64 v11; // rcx
  __int64 UserGdiSessionState; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // r12d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // ebx
  UUID *p_Uuid; // rax
  UUID v32; // xmm6
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  PEPROCESS ThreadProcess; // rax
  int ProcessImageFileName; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  int v44; // r15d
  __int64 v45; // rdx
  __int64 v46; // rcx
  _QWORD *v47; // rbx
  __int64 v48; // rax
  int v49; // esi
  __int64 v50; // rdx
  __int64 v51; // rcx
  int v52; // ebx
  UUID *v53; // rax
  UUID v54; // xmm6
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  PEPROCESS v58; // rax
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  _QWORD *v62; // rbx
  __int64 v63; // rax
  _DWORD *v64; // rbx
  int v65; // r14d
  unsigned int v66; // edi
  __int64 v67; // rdx
  __int64 *v68; // rax
  __int64 v69; // r9
  __int16 v70; // [rsp+78h] [rbp-71h] BYREF
  __int16 v71; // [rsp+7Ah] [rbp-6Fh] BYREF
  unsigned int v72; // [rsp+7Ch] [rbp-6Dh] BYREF
  int v73; // [rsp+80h] [rbp-69h] BYREF
  int v74; // [rsp+84h] [rbp-65h] BYREF
  int v75; // [rsp+88h] [rbp-61h] BYREF
  __int64 v76; // [rsp+90h] [rbp-59h] BYREF
  UUID v77; // [rsp+98h] [rbp-51h] BYREF
  __int128 v78; // [rsp+A8h] [rbp-41h] BYREF
  PVOID Buffer[2]; // [rsp+B8h] [rbp-31h]
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v80[2]; // [rsp+C8h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+D8h] [rbp-11h] BYREF

  LOBYTE(v70) = a3;
  v72 = a1;
  LOBYTE(v80[0]) = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor(v80, 0, 0xFu, a1);
  v7 = v80[1];
  UserSessionState = W32GetUserSessionState(v9, v8);
  v76 = UserSessionState;
  UserGdiSessionState = W32GetUserGdiSessionState(v11);
  v15 = 1;
  while ( *(_DWORD *)(UserGdiSessionState + 36) )
  {
    UserSessionSwitchLeaveCritWithNonPaged(v14, v13);
    v18 = W32GetUserSessionState(v17, v16);
    KeWaitForSingleObject(*(PVOID *)(v18 + 68384), WrUserRequest, 0, 0, 0);
    v21 = (_QWORD *)W32GetUserSessionState(v20, v19);
    v22 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v21,
            1,
            0,
            (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    v21[2] = v22;
    if ( v22 && UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v22) )
    {
      DestroySharedUserCritDeferredUnlockList((__int64)(v21 + 2440), v24);
      DestroyDeferredUnlockObjectAssignmentList(v21 + 2447);
      DestroyDeferredUnlockObjectAssignmentList(v21 + 2445);
    }
    UserGdiSessionState = W32GetUserGdiSessionState(v23);
  }
  v78 = 0;
  *(_OWORD *)Buffer = 0;
  LOWORD(v78) = *(_WORD *)(W32GetUserSessionState(v14, v13) + 68736);
  if ( !(unsigned int)UserIsWddmConnectedSession((unsigned __int16)v78, v25) )
    goto LABEL_41;
  if ( a2 )
  {
    UserSessionSwitchLeaveCritWithNonPaged(v27, v26);
    Uuid = 0;
    if ( !a4 && ExUuidCreate(&Uuid) < 0 )
      Uuid = 0;
    if ( a5 )
      v30 = *a5;
    else
      v30 = 0;
    p_Uuid = &Uuid;
    if ( a4 )
      p_Uuid = a4;
    v32 = *p_Uuid;
    if ( *(_QWORD *)(W32GetUserSessionState(v29, v28) + 18984) )
    {
      v35 = W32GetUserSessionState(v34, v33);
      ThreadProcess = PsGetThreadProcess(**(PETHREAD **)(v35 + 18984));
      ProcessImageFileName = PsGetProcessImageFileName(ThreadProcess);
    }
    else
    {
      ProcessImageFileName = 0;
    }
    v77 = v32;
    DrvDxgkCheckDisplayState(v72, 1, ProcessImageFileName, (_DWORD)v7, (__int64)&v77, v30);
    *(_OWORD *)(UserSessionState + 56752) = *(_OWORD *)v7;
    v40 = (_QWORD *)W32GetUserSessionState(v39, v38);
    v41 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v40,
            1,
            0,
            (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    v40[2] = v41;
    if ( v41 && UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v41) )
    {
      DestroySharedUserCritDeferredUnlockList((__int64)(v40 + 2440), v26);
      DestroyDeferredUnlockObjectAssignmentList(v40 + 2447);
      DestroyDeferredUnlockObjectAssignmentList(v40 + 2445);
    }
  }
  if ( !UserIsConsoleConnection(v27, v26) || !(_BYTE)v70 )
  {
LABEL_41:
    v44 = DWORD2(v78);
    v15 = DWORD1(v78);
LABEL_42:
    v49 = HIDWORD(v78);
    goto LABEL_43;
  }
  DisplayDiagRecordActiveTopology((struct USER_DETECTED_BLACK_SCREEN_REPORT *)&v78);
  UserSessionSwitchLeaveCritWithNonPaged(v43, v42);
  Uuid.Data1 = 0;
  *(_DWORD *)&Uuid.Data2 = 26;
  v44 = DrvDxgkPollDisplayChildren(&Uuid);
  v47 = (_QWORD *)W32GetUserSessionState(v46, v45);
  v48 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          v47,
          1,
          0,
          (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  v47[2] = v48;
  if ( v48 && UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v48) )
  {
    DestroySharedUserCritDeferredUnlockList((__int64)(v47 + 2440), v26);
    DestroyDeferredUnlockObjectAssignmentList(v47 + 2447);
    DestroyDeferredUnlockObjectAssignmentList(v47 + 2445);
  }
  *(_OWORD *)v7 = *(_OWORD *)(v76 + 56752);
  if ( v44 < 0 )
    goto LABEL_42;
  LOBYTE(v71) = 0;
  v49 = xxxUserSetDisplayConfig(0, 0, 0x187u, 0x80u, 0, 0, 0, (bool *)&v71, 0, v7, 0);
  if ( v49 >= 0 )
  {
    UserSessionSwitchLeaveCritWithNonPaged(v27, v26);
    v77 = 0;
    if ( a5 )
      v52 = *a5;
    else
      v52 = 0;
    v53 = &v77;
    if ( a4 )
      v53 = a4;
    v54 = *v53;
    if ( *(_QWORD *)(W32GetUserSessionState(v51, v50) + 18984) )
    {
      v57 = W32GetUserSessionState(v56, v55);
      v58 = PsGetThreadProcess(**(PETHREAD **)(v57 + 18984));
      v59 = PsGetProcessImageFileName(v58);
    }
    else
    {
      v59 = 0;
    }
    v77 = v54;
    DrvDxgkCheckDisplayState(v72, 0, v59, (_DWORD)v7, (__int64)&v77, v52);
    v62 = (_QWORD *)W32GetUserSessionState(v61, v60);
    v63 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v62,
            1,
            0,
            (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    v62[2] = v63;
    if ( v63 && UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v63) )
    {
      DestroySharedUserCritDeferredUnlockList((__int64)(v62 + 2440), v26);
      DestroyDeferredUnlockObjectAssignmentList(v62 + 2447);
      DestroyDeferredUnlockObjectAssignmentList(v62 + 2445);
    }
  }
LABEL_43:
  v64 = Buffer[1];
  v65 = HIDWORD(Buffer[0]);
  if ( Buffer[1] )
    v66 = 216 * HIDWORD(Buffer[0]);
  else
    v66 = 0;
  if ( UserIsConsoleConnection(v27, v26)
    && (_BYTE)v70
    && (unsigned int)dword_140293E08 > 5
    && tlgKeywordOn((__int64)&dword_140293E08, 0x400000000008LL) )
  {
    v68 = (__int64 *)_tlgWrapBinary<void,1>((__int64)&v77, (__int64)v64, v66);
    LODWORD(v76) = Buffer[0];
    v71 = v78;
    v70 = 4;
    v73 = v65;
    v74 = v49;
    v75 = v44;
    Uuid.Data1 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
      (__int64)&v72,
      (__int64)&byte_14026F6C7,
      (__int64)v7,
      v69,
      (__int64)&v70,
      (__int64)&Uuid,
      (__int64)&v71,
      (__int64)&v76,
      (__int64)&v75,
      (__int64)&v74,
      (__int64)&v73,
      v68,
      (__int64)&v72);
  }
  if ( v64 )
    GreDeleteFastMutex(v64, v67);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope(v80);
}

```

## disassembly

```asm
0x1401cca10  mov     rax, rsp
0x1401cca13  mov     [rax+10h], rbx
0x1401cca17  push    rbp
0x1401cca18  push    rsi
0x1401cca19  push    rdi
0x1401cca1a  push    r12
0x1401cca1c  push    r13
0x1401cca1e  push    r14
0x1401cca20  push    r15
0x1401cca22  lea     rbp, [rax-57h]
0x1401cca26  sub     rsp, 100h
0x1401cca2d  movaps  xmmword ptr [rax-48h], xmm6
0x1401cca31  mov     rax, cs:__security_cookie
0x1401cca38  xor     rax, rsp
0x1401cca3b  mov     [rbp+4Fh+var_50], rax
0x1401cca3f  xor     edi, edi
0x1401cca41  mov     byte ptr [rbp+4Fh+var_C0], r8b
0x1401cca45  mov     r14, r9
0x1401cca48  mov     [rbp+4Fh+var_BC], ecx
0x1401cca4b  mov     sil, dl
0x1401cca4e  mov     [rbp+4Fh+var_70], dil
0x1401cca52  mov     r9d, ecx; unsigned int
0x1401cca55  xor     edx, edx; struct _GUID *
0x1401cca57  lea     r8d, [rdi+0Fh]; unsigned int
0x1401cca5b  lea     rcx, [rbp+4Fh+var_70]; this
0x1401cca5f  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401cca64  mov     r13, [rbp+4Fh+var_68]
0x1401cca68  call    cs:__imp_W32GetUserSessionState
0x1401cca6f  nop     dword ptr [rax+rax+00h]
0x1401cca74  mov     r15, rax
0x1401cca77  mov     [rbp+4Fh+var_A8], rax
0x1401cca7b  call    cs:__imp_W32GetUserGdiSessionState
0x1401cca82  nop     dword ptr [rax+rax+00h]
0x1401cca87  lea     r12d, [rdi+1]
0x1401cca8b  jmp     loc_1401CCB2C
0x1401cca90  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cca95  call    cs:__imp_W32GetUserSessionState
0x1401cca9c  nop     dword ptr [rax+rax+00h]
0x1401ccaa1  xor     r9d, r9d; Alertable
0x1401ccaa4  mov     [rsp+130h+Timeout], rdi; Timeout
0x1401ccaa9  xor     r8d, r8d; WaitMode
0x1401ccaac  mov     rcx, [rax+10B20h]; Object
0x1401ccab3  lea     edx, [r9+0Dh]; WaitReason
0x1401ccab7  call    cs:__imp_KeWaitForSingleObject
0x1401ccabe  nop     dword ptr [rax+rax+00h]
0x1401ccac3  call    cs:__imp_W32GetUserSessionState
0x1401ccaca  nop     dword ptr [rax+rax+00h]
0x1401ccacf  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ccad6  xor     r8d, r8d
0x1401ccad9  mov     rcx, rax
0x1401ccadc  mov     edx, r12d
0x1401ccadf  mov     rbx, rax
0x1401ccae2  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401ccae7  mov     [rbx+10h], rax
0x1401ccaeb  test    rax, rax
0x1401ccaee  jz      short loc_1401CCB20
0x1401ccaf0  mov     rcx, rax
0x1401ccaf3  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401ccaf8  test    al, al
0x1401ccafa  jz      short loc_1401CCB20
0x1401ccafc  lea     rcx, [rbx+4C40h]
0x1401ccb03  call    DestroySharedUserCritDeferredUnlockList
0x1401ccb08  lea     rcx, [rbx+4C78h]
0x1401ccb0f  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccb14  lea     rcx, [rbx+4C68h]
0x1401ccb1b  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccb20  call    cs:__imp_W32GetUserGdiSessionState
0x1401ccb27  nop     dword ptr [rax+rax+00h]
0x1401ccb2c  cmp     [rax+24h], edi
0x1401ccb2f  jnz     loc_1401CCA90
0x1401ccb35  xorps   xmm0, xmm0
0x1401ccb38  movups  [rbp+4Fh+var_90], xmm0
0x1401ccb3c  movups  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1401ccb40  call    cs:__imp_W32GetUserSessionState
0x1401ccb47  nop     dword ptr [rax+rax+00h]
0x1401ccb4c  movzx   ecx, word ptr [rax+10C80h]
0x1401ccb53  mov     word ptr [rbp+4Fh+var_90], cx
0x1401ccb57  call    UserIsWddmConnectedSession
0x1401ccb5c  test    eax, eax
0x1401ccb5e  jz      loc_1401CCE88
0x1401ccb64  mov     rdi, [rbp+4Fh+arg_20]
0x1401ccb68  test    sil, sil
0x1401ccb6b  jz      loc_1401CCC93
0x1401ccb71  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401ccb76  xor     esi, esi
0x1401ccb78  xorps   xmm0, xmm0
0x1401ccb7b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401ccb7f  test    r14, r14
0x1401ccb82  jnz     short loc_1401CCB9F
0x1401ccb84  lea     rcx, [rbp+4Fh+Uuid]; Uuid
0x1401ccb88  call    cs:__imp_ExUuidCreate
0x1401ccb8f  nop     dword ptr [rax+rax+00h]
0x1401ccb94  test    eax, eax
0x1401ccb96  jns     short loc_1401CCB9F
0x1401ccb98  xorps   xmm0, xmm0
0x1401ccb9b  movups  xmmword ptr [rbp+4Fh+Uuid.Data1], xmm0
0x1401ccb9f  test    rdi, rdi
0x1401ccba2  jz      short loc_1401CCBA8
0x1401ccba4  mov     ebx, [rdi]
0x1401ccba6  jmp     short loc_1401CCBAA
0x1401ccba8  mov     ebx, esi
0x1401ccbaa  test    r14, r14
0x1401ccbad  lea     rax, [rbp+4Fh+Uuid]
0x1401ccbb1  cmovnz  rax, r14
0x1401ccbb5  movups  xmm6, xmmword ptr [rax]
0x1401ccbb8  call    cs:__imp_W32GetUserSessionState
0x1401ccbbf  nop     dword ptr [rax+rax+00h]
0x1401ccbc4  cmp     [rax+4A28h], rsi
0x1401ccbcb  jz      short loc_1401CCC00
0x1401ccbcd  call    cs:__imp_W32GetUserSessionState
0x1401ccbd4  nop     dword ptr [rax+rax+00h]
0x1401ccbd9  mov     rcx, [rax+4A28h]
0x1401ccbe0  mov     rcx, [rcx]; Thread
0x1401ccbe3  call    cs:__imp_PsGetThreadProcess
0x1401ccbea  nop     dword ptr [rax+rax+00h]
0x1401ccbef  mov     rcx, rax
0x1401ccbf2  call    cs:__imp_PsGetProcessImageFileName
0x1401ccbf9  nop     dword ptr [rax+rax+00h]
0x1401ccbfe  jmp     short loc_1401CCC03
0x1401ccc00  mov     rax, rsi
0x1401ccc03  lea     rcx, [rbp+4Fh+var_A0]
0x1401ccc07  mov     dword ptr [rsp+130h+var_108], ebx
0x1401ccc0b  mov     [rsp+130h+Timeout], rcx
0x1401ccc10  mov     r9, r13
0x1401ccc13  mov     ecx, [rbp+4Fh+var_BC]
0x1401ccc16  mov     r8, rax
0x1401ccc19  mov     edx, r12d
0x1401ccc1c  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401ccc21  call    DrvDxgkCheckDisplayState
0x1401ccc26  movups  xmm0, xmmword ptr [r13+0]
0x1401ccc2b  movdqu  xmmword ptr [r15+0DDB0h], xmm0
0x1401ccc34  call    cs:__imp_W32GetUserSessionState
0x1401ccc3b  nop     dword ptr [rax+rax+00h]
0x1401ccc40  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ccc47  xor     r8d, r8d
0x1401ccc4a  mov     rcx, rax
0x1401ccc4d  mov     edx, r12d
0x1401ccc50  mov     rbx, rax
0x1401ccc53  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401ccc58  mov     [rbx+10h], rax
0x1401ccc5c  test    rax, rax
0x1401ccc5f  jz      short loc_1401CCC95
0x1401ccc61  mov     rcx, rax
0x1401ccc64  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401ccc69  test    al, al
0x1401ccc6b  jz      short loc_1401CCC95
0x1401ccc6d  lea     rcx, [rbx+4C40h]
0x1401ccc74  call    DestroySharedUserCritDeferredUnlockList
0x1401ccc79  lea     rcx, [rbx+4C78h]
0x1401ccc80  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccc85  lea     rcx, [rbx+4C68h]
0x1401ccc8c  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccc91  jmp     short loc_1401CCC95
0x1401ccc93  xor     esi, esi
0x1401ccc95  call    UserIsConsoleConnection
0x1401ccc9a  test    eax, eax
0x1401ccc9c  jz      loc_1401CCE88
0x1401ccca2  cmp     byte ptr [rbp+4Fh+var_C0], sil
0x1401ccca6  jz      loc_1401CCE88
0x1401cccac  lea     rcx, [rbp+4Fh+var_90]; struct USER_DETECTED_BLACK_SCREEN_REPORT *
0x1401cccb0  call    ?DisplayDiagRecordActiveTopology@@YAXPEAUUSER_DETECTED_BLACK_SCREEN_REPORT@@@Z; DisplayDiagRecordActiveTopology(USER_DETECTED_BLACK_SCREEN_REPORT *)
0x1401cccb5  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cccba  mov     qword ptr [rbp+4Fh+Uuid.Data1], rsi
0x1401cccbe  lea     rcx, [rbp+4Fh+Uuid]
0x1401cccc2  mov     eax, dword ptr [rbp+4Fh+Uuid.Data2]
0x1401cccc5  and     eax, 0FFFFFFFAh
0x1401cccc8  or      eax, 1Ah
0x1401ccccb  mov     dword ptr [rbp+4Fh+Uuid.Data2], eax
0x1401cccce  call    DrvDxgkPollDisplayChildren
0x1401cccd3  mov     r15d, eax
0x1401cccd6  call    cs:__imp_W32GetUserSessionState
0x1401cccdd  nop     dword ptr [rax+rax+00h]
0x1401ccce2  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ccce9  xor     r8d, r8d
0x1401cccec  mov     rcx, rax
0x1401cccef  mov     edx, r12d
0x1401cccf2  mov     rbx, rax
0x1401cccf5  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cccfa  mov     [rbx+10h], rax
0x1401cccfe  test    rax, rax
0x1401ccd01  jz      short loc_1401CCD33
0x1401ccd03  mov     rcx, rax
0x1401ccd06  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401ccd0b  test    al, al
0x1401ccd0d  jz      short loc_1401CCD33
0x1401ccd0f  lea     rcx, [rbx+4C40h]
0x1401ccd16  call    DestroySharedUserCritDeferredUnlockList
0x1401ccd1b  lea     rcx, [rbx+4C78h]
0x1401ccd22  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccd27  lea     rcx, [rbx+4C68h]
0x1401ccd2e  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ccd33  mov     rax, [rbp+4Fh+var_A8]
0x1401ccd37  movups  xmm0, xmmword ptr [rax+0DDB0h]
0x1401ccd3e  movdqu  xmmword ptr [r13+0], xmm0
0x1401ccd44  test    r15d, r15d
0x1401ccd47  js      loc_1401CCE90
0x1401ccd4d  mov     [rsp+130h+var_E0], rsi
0x1401ccd52  lea     rax, [rbp+4Fh+var_BE]
0x1401ccd56  mov     [rsp+130h+var_E8], r13
0x1401ccd5b  xor     edx, edx
0x1401ccd5d  mov     [rsp+130h+var_F0], rsi
0x1401ccd62  xor     ecx, ecx
0x1401ccd64  mov     [rsp+130h+var_F8], rax
0x1401ccd69  mov     r9d, 80h
0x1401ccd6f  mov     [rsp+130h+var_100], rsi
0x1401ccd74  mov     r8d, 187h
0x1401ccd7a  mov     byte ptr [rsp+130h+var_108], sil
0x1401ccd7f  mov     [rsp+130h+Timeout], rsi
0x1401ccd84  mov     byte ptr [rbp+4Fh+var_BE], sil
0x1401ccd88  call    xxxUserSetDisplayConfig
0x1401ccd8d  mov     esi, eax
0x1401ccd8f  test    eax, eax
0x1401ccd91  js      loc_1401CCE93
0x1401ccd97  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401ccd9c  xorps   xmm0, xmm0
0x1401ccd9f  movups  [rbp+4Fh+var_A0], xmm0
0x1401ccda3  test    rdi, rdi
0x1401ccda6  jz      short loc_1401CCDAC
0x1401ccda8  mov     ebx, [rdi]
0x1401ccdaa  jmp     short loc_1401CCDAE
0x1401ccdac  xor     ebx, ebx
0x1401ccdae  test    r14, r14
0x1401ccdb1  lea     rax, [rbp+4Fh+var_A0]
0x1401ccdb5  cmovnz  rax, r14
0x1401ccdb9  movups  xmm6, xmmword ptr [rax]
0x1401ccdbc  call    cs:__imp_W32GetUserSessionState
0x1401ccdc3  nop     dword ptr [rax+rax+00h]
0x1401ccdc8  cmp     qword ptr [rax+4A28h], 0
0x1401ccdd0  jz      short loc_1401CCE05
0x1401ccdd2  call    cs:__imp_W32GetUserSessionState
0x1401ccdd9  nop     dword ptr [rax+rax+00h]
0x1401ccdde  mov     rcx, [rax+4A28h]
0x1401ccde5  mov     rcx, [rcx]; Thread
0x1401ccde8  call    cs:__imp_PsGetThreadProcess
0x1401ccdef  nop     dword ptr [rax+rax+00h]
0x1401ccdf4  mov     rcx, rax
0x1401ccdf7  call    cs:__imp_PsGetProcessImageFileName
0x1401ccdfe  nop     dword ptr [rax+rax+00h]
0x1401cce03  jmp     short loc_1401CCE07
0x1401cce05  xor     eax, eax
0x1401cce07  lea     rcx, [rbp+4Fh+var_A0]
0x1401cce0b  mov     dword ptr [rsp+130h+var_108], ebx
0x1401cce0f  mov     [rsp+130h+Timeout], rcx
0x1401cce14  mov     r9, r13
0x1401cce17  mov     ecx, [rbp+4Fh+var_BC]
0x1401cce1a  mov     r8, rax
0x1401cce1d  xor     edx, edx
0x1401cce1f  movdqu  [rbp+4Fh+var_A0], xmm6
0x1401cce24  call    DrvDxgkCheckDisplayState
0x1401cce29  call    cs:__imp_W32GetUserSessionState
0x1401cce30  nop     dword ptr [rax+rax+00h]
0x1401cce35  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cce3c  xor     r8d, r8d
0x1401cce3f  mov     rcx, rax
0x1401cce42  mov     edx, r12d
0x1401cce45  mov     rbx, rax
0x1401cce48  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cce4d  mov     [rbx+10h], rax
0x1401cce51  test    rax, rax
0x1401cce54  jz      short loc_1401CCE93
0x1401cce56  mov     rcx, rax
0x1401cce59  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1401cce5e  test    al, al
0x1401cce60  jz      short loc_1401CCE93
0x1401cce62  lea     rcx, [rbx+4C40h]
0x1401cce69  call    DestroySharedUserCritDeferredUnlockList
0x1401cce6e  lea     rcx, [rbx+4C78h]
0x1401cce75  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cce7a  lea     rcx, [rbx+4C68h]
0x1401cce81  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cce86  jmp     short loc_1401CCE93
0x1401cce88  mov     r15d, dword ptr [rbp+4Fh+var_90+8]
0x1401cce8c  mov     r12d, dword ptr [rbp+4Fh+var_90+4]
0x1401cce90  mov     esi, dword ptr [rbp+4Fh+var_90+0Ch]
0x1401cce93  mov     rbx, [rbp+4Fh+Buffer+8]
0x1401cce97  mov     r14d, dword ptr [rbp+4Fh+Buffer+4]
0x1401cce9b  test    rbx, rbx
0x1401cce9e  jnz     short loc_1401CCEA4
0x1401ccea0  xor     edi, edi
0x1401ccea2  jmp     short loc_1401CCEAB
0x1401ccea4  imul    edi, r14d, 0D8h
0x1401cceab  call    UserIsConsoleConnection
0x1401cceb0  test    eax, eax
0x1401cceb2  jz      loc_1401CCF86
0x1401cceb8  cmp     byte ptr [rbp+4Fh+var_C0], 0
0x1401ccebc  jz      loc_1401CCF86
0x1401ccec2  mov     eax, cs:dword_140293E08
0x1401ccec8  cmp     eax, 5
0x1401ccecb  jbe     loc_1401CCF86
0x1401cced1  mov     rdx, 400000000008h
0x1401ccedb  lea     rcx, dword_140293E08
0x1401ccee2  call    _tlgKeywordOn
0x1401ccee7  test    al, al
0x1401ccee9  jz      loc_1401CCF86
0x1401cceef  mov     eax, [rbp+4Fh+var_BC]
0x1401ccef2  lea     rcx, [rbp+4Fh+var_A0]
0x1401ccef6  mov     r8d, edi
0x1401ccef9  mov     rdx, rbx
0x1401ccefc  mov     [rbp+4Fh+var_BC], eax
0x1401cceff  call    ??$_tlgWrapBinary@X$00@@YA?AU?$_tlgWrapperArray@$00@@PEBX_K@Z; _tlgWrapBinary<void,1>(void const *,unsigned __int64)
  ... truncated ...
```
