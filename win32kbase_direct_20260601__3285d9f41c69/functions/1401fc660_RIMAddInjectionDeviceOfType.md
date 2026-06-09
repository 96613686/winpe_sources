# RIMAddInjectionDeviceOfType

- ea: `0x1401fc660`
- end: `0x1401fcfcc`
- name: `RIMAddInjectionDeviceOfType`
- size: `2412`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14020445c`
- `0x140204810`

## callees

- `0x14001bdf0`
- `0x140033364`
- `0x14004a0d0`
- `0x14004d770`
- `0x140065730`
- `0x1400729c8`
- `0x140072a90`
- `0x140074bf0`
- `0x140078090`
- `0x1400951c0`
- `0x1400e0370`
- `0x1400f9f50`
- `0x140135db0`
- `0x140184c20`
- `0x1401a9f9c`
- `0x1401fc660`
- `0x140238160`
- `0x1402382c0`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fc98f`
- `ntoskrnl!ProbeForRead` at `0x1401fc98f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fca4a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fca4a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fcddd`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fcddd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc9ec`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fc9ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fcd84`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fcd84`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fcb97`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fcb97`
- `WIN32K!W32GetUserSessionState` at `0x1401fc72a`
- `WIN32K!W32GetUserSessionState` at `0x1401fc7ae`
- `WIN32K!W32GetUserSessionState` at `0x1401fcbe9`
- `WIN32K!W32GetUserSessionState` at `0x1401fcc8a`
- `WIN32K!W32GetUserSessionState` at `0x1401fcd14`
- `WIN32K!W32GetUserSessionState` at `0x1401fcd90`
- `WIN32K!W32GetUserSessionState` at `0x1401fcef0`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf5c`
- `WIN32K!W32GetUserSessionState` at `0x1401fc72a`
- `WIN32K!W32GetUserSessionState` at `0x1401fc7ae`
- `WIN32K!W32GetUserSessionState` at `0x1401fcbe9`
- `WIN32K!W32GetUserSessionState` at `0x1401fcc8a`
- `WIN32K!W32GetUserSessionState` at `0x1401fcd14`
- `WIN32K!W32GetUserSessionState` at `0x1401fcd90`
- `WIN32K!W32GetUserSessionState` at `0x1401fcef0`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf5c`

## pseudocode

```c
__int64 __fastcall RIMAddInjectionDeviceOfType(char *a1, __int64 a2, unsigned int a3, __int64 a4, int a5, _QWORD *a6)
{
  __int64 v7; // r8
  char v8; // bl
  bool v9; // r14
  __int64 UserSessionState; // rax
  int v11; // r8d
  int v12; // edx
  char v13; // bl
  bool v14; // r14
  __int64 v15; // rax
  int v16; // r8d
  int v17; // edx
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r14d
  PVOID *v23; // r15
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int ULongFromUser; // ebx
  struct RIMDEV *v29; // rax
  __int64 v30; // rcx
  char v31; // bl
  bool v32; // r12
  int v33; // edx
  int v34; // r8d
  __int64 v35; // r9
  char v36; // bl
  bool v37; // r14
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  char v41; // bl
  bool v42; // r14
  __int64 v43; // rax
  int v44; // r8d
  int v45; // edx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r14
  __int64 v50; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v52; // rax
  char v53; // al
  _QWORD *i; // rbx
  char v55; // bl
  bool v56; // r15
  __int64 v57; // rax
  int v58; // r8d
  int v59; // edx
  __int16 v60; // [rsp+30h] [rbp-188h]
  struct RIMDEV *v61; // [rsp+58h] [rbp-160h] BYREF
  unsigned int v62; // [rsp+60h] [rbp-158h]
  char *v63; // [rsp+68h] [rbp-150h]
  PVOID Object; // [rsp+70h] [rbp-148h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-140h] BYREF
  int v66; // [rsp+88h] [rbp-130h]
  __int64 v67; // [rsp+90h] [rbp-128h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-120h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+A8h] [rbp-110h]
  _QWORD *v70; // [rsp+B0h] [rbp-108h]
  __int64 v71; // [rsp+B8h] [rbp-100h]
  __int64 v72; // [rsp+C0h] [rbp-F8h]
  __int128 v73; // [rsp+C8h] [rbp-F0h]
  __int64 v74[18]; // [rsp+E0h] [rbp-D8h] BYREF

  v62 = a3;
  v67 = a2;
  v63 = a1;
  v70 = a6;
  LODWORD(v61) = a3;
  v71 = a4;
  v72 = (__int64)a6;
  Object = 0;
  memset(v74, 0, 0x88u);
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v8 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v8 = 0;
  }
  v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, v7);
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v8;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v12,
      v11,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      35,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v13 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
    {
      v13 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, v7);
      LOBYTE(v16) = v14;
      LOBYTE(v17) = v13;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v17,
        v16,
        *(_QWORD *)(v15 + 19408),
        3,
        1,
        36,
        (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    }
    return 3221225485LL;
  }
  v19 = a5;
  if ( a5 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1129);
  v22 = RawInputManagerObjectResolveHandle(v63, 3, 0, &Object);
  if ( v22 >= 0 )
  {
    v23 = (PVOID *)Object;
    v63 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v23 + 73) )
    {
      if ( !*((_BYTE *)v23 + 74) )
      {
        v22 = -1073741637;
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
          || (v31 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v31 = 0;
        }
        v32 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v31 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_49;
        v35 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v24, v25) + 19408);
        v60 = 40;
LABEL_57:
        LOBYTE(v34) = v32;
        LOBYTE(v33) = v31;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v33,
          v34,
          v35,
          3,
          1,
          v60,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_49:
        RIMUnlockExclusive(v63);
        ObfDereferenceObject(v23);
        goto LABEL_98;
      }
    }
    else if ( !*((_BYTE *)v23 + 74) )
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(v62) & *((_DWORD *)v23 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v73 = 0;
          ULongFromUser = RtlReadULongFromUser(v67);
          LODWORD(v73) = ULongFromUser;
          *((_QWORD *)&v73 + 1) = RtlReadULong64FromUser(v67 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v73);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v73 + 1);
          ProbeForRead(*((volatile void **)&v73 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1165);
            ExRaiseAccessViolation();
          }
          DestinationString.MaximumLength = SourceString.Length;
          DestinationString.Length = SourceString.Length;
          DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
          if ( DestinationString.Buffer )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            p_DestinationString = &DestinationString;
          }
          else
          {
            v22 = -1073741801;
            v66 = -1073741801;
          }
          v19 = a5;
        }
        else
        {
          *(_OWORD *)v74 = *(_OWORD *)a4;
          *(_OWORD *)&v74[2] = *(_OWORD *)(a4 + 16);
          *(_OWORD *)&v74[4] = *(_OWORD *)(a4 + 32);
          *(_OWORD *)&v74[6] = *(_OWORD *)(a4 + 48);
          *(_OWORD *)&v74[8] = *(_OWORD *)(a4 + 64);
          *(_OWORD *)&v74[10] = *(_OWORD *)(a4 + 80);
          *(_OWORD *)&v74[12] = *(_OWORD *)(a4 + 96);
          *(_OWORD *)&v74[14] = *(_OWORD *)(a4 + 112);
          v74[16] = *(_QWORD *)(a4 + 128);
        }
        if ( v22 >= 0 )
        {
          v61 = 0;
          v22 = RIMCreateDev((struct RawInputManagerObject *)v23, 1, (__int64)v74, (__int64)&v61);
          if ( !v19 )
            *(_DWORD *)(a4 + 128) = v74[16];
          if ( v22 >= 0 )
          {
            if ( v19 )
            {
              RtlWriteULong64ToUser(v72, *((_QWORD *)v61 + 2));
              v29 = v61;
            }
            else
            {
              v29 = v61;
              v30 = (v74[2] & 1) != 0 ? *((_QWORD *)v61 + 3) : *((_QWORD *)v61 + 2);
              *v70 = v30;
            }
            if ( v23[103] || *((_DWORD *)v23 + 262) )
              *((_DWORD *)v29 + 42) |= 0x40000u;
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_49;
      }
      v22 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v31 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v31 = 0;
      }
      v32 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v31 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_49;
      v35 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v26, v27) + 19408);
      v60 = 37;
      goto LABEL_57;
    }
    if ( KeGetCurrentThread() == v23[5] )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v36 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v36 = 0;
      }
      v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v38 = W32GetUserSessionState(WPP_GLOBAL_Control, v24, v25);
        LOBYTE(v39) = v37;
        LOBYTE(v40) = v36;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v40,
          v39,
          *(_QWORD *)(v38 + 19408),
          3,
          1,
          38,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
      }
      v22 = -1073741637;
      goto LABEL_49;
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v41 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
    {
      v41 = 0;
    }
    v42 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v41 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v43 = W32GetUserSessionState(WPP_GLOBAL_Control, v24, v25);
      LOBYTE(v44) = v42;
      LOBYTE(v45) = v41;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v45,
        v44,
        *(_QWORD *)(v43 + 19408),
        3,
        1,
        39,
        (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    }
    ++*((_DWORD *)v23 + 274);
    RIMUnlockExclusive(v63);
    UserSessionSwitchLeaveCritWithNonPaged();
    KeWaitForSingleObject(v23[136], UserRequest, 0, 0, 0);
    v49 = W32GetUserSessionState(v47, v46, v48);
    v50 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v49,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v49 + 16) = v50;
    if ( v50 )
    {
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v50 + 520), 0, 0) & 0x1000000) == 0
        || *(char *)(v50 + 1360) < 0 )
      {
        v53 = 0;
LABEL_83:
        if ( v53 )
        {
          for ( i = *(_QWORD **)(v49 + 19544); i; i = *(_QWORD **)(v49 + 19544) )
          {
            *(_QWORD *)(v49 + 19544) = i[2];
            i[2] = 0;
            if ( !*(_DWORD *)(*i + 8LL) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            HMUnlockObject(*i);
          }
          DestroyDeferredUnlockObjectAssignmentList(v49 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v49 + 19560);
        }
        goto LABEL_89;
      }
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        v52 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
        if ( v52 )
        {
          if ( *(_BYTE *)(v52 + 1200) == 1 )
          {
            v53 = 1;
            goto LABEL_83;
          }
        }
      }
    }
LABEL_89:
    RIMLockExclusive(v63);
    v22 = -2147483631;
    goto LABEL_49;
  }
  v22 = -1073741816;
LABEL_98:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v55 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v55 = 0;
  }
  v56 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v55 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v57 = W32GetUserSessionState(WPP_GLOBAL_Control, v20, v21);
    LOBYTE(v58) = v56;
    LOBYTE(v59) = v55;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v59,
      v58,
      *(_QWORD *)(v57 + 19408),
      4,
      1,
      41,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v22);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1401fc660  push    rbx
0x1401fc662  push    rsi
0x1401fc663  push    rdi
0x1401fc664  push    r12
0x1401fc666  push    r13
0x1401fc668  push    r14
0x1401fc66a  push    r15
0x1401fc66c  sub     rsp, 180h
0x1401fc673  mov     rax, cs:__security_cookie
0x1401fc67a  xor     rax, rsp
0x1401fc67d  mov     [rsp+1B8h+var_48], rax
0x1401fc685  mov     r13, r9
0x1401fc688  mov     eax, r8d
0x1401fc68b  mov     [rsp+1B8h+var_158], eax
0x1401fc68f  mov     [rsp+1B8h+var_128], rdx
0x1401fc697  mov     [rsp+1B8h+var_150], rcx
0x1401fc69c  mov     rcx, [rsp+1B8h+arg_28]
0x1401fc6a4  mov     [rsp+1B8h+var_108], rcx
0x1401fc6ac  mov     dword ptr [rsp+1B8h+var_160], eax
0x1401fc6b0  mov     [rsp+1B8h+var_100], r9
0x1401fc6b8  mov     [rsp+1B8h+var_F8], rcx
0x1401fc6c0  xor     edi, edi
0x1401fc6c2  mov     [rsp+1B8h+Object], rdi
0x1401fc6c7  xor     edx, edx; Val
0x1401fc6c9  mov     r8d, 88h; Size
0x1401fc6cf  lea     rcx, [rsp+1B8h+var_D8]; void *
0x1401fc6d7  call    memset
0x1401fc6dc  lea     rdx, WPP_GLOBAL_Control
0x1401fc6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fc6ea  lea     esi, [rdi+1]
0x1401fc6ed  cmp     rcx, rdx
0x1401fc6f0  jz      short loc_1401FC703
0x1401fc6f2  mov     eax, [rcx+2Ch]
0x1401fc6f5  test    sil, al
0x1401fc6f8  jz      short loc_1401FC703
0x1401fc6fa  cmp     byte ptr [rcx+29h], 4
0x1401fc6fe  mov     bl, sil
0x1401fc701  jnb     short loc_1401FC706
0x1401fc703  mov     bl, dil
0x1401fc706  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fc70d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fc714  setnz   r14b
0x1401fc718  test    bl, bl
0x1401fc71a  jnz     short loc_1401FC72A
0x1401fc71c  test    r14b, r14b
0x1401fc71f  jnz     short loc_1401FC72A
0x1401fc721  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fc728  jmp     short loc_1401FC775
0x1401fc72a  call    cs:__imp_W32GetUserSessionState
0x1401fc731  nop     dword ptr [rax+rax+00h]
0x1401fc736  mov     r9, [rax+4BD0h]
0x1401fc73d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fc744  mov     [rsp+1B8h+var_180], r15
0x1401fc749  mov     word ptr [rsp+1B8h+var_188], 23h ; '#'
0x1401fc750  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fc754  mov     byte ptr [rsp+1B8h+Timeout], 4
0x1401fc759  mov     r8b, r14b
0x1401fc75c  mov     dl, bl
0x1401fc75e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fc765  mov     rcx, [rcx+18h]
0x1401fc769  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fc76e  lea     rdx, WPP_GLOBAL_Control
0x1401fc775  test    r13, r13
0x1401fc778  jnz     short loc_1401FC7F5
0x1401fc77a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fc781  cmp     rcx, rdx
0x1401fc784  jz      short loc_1401FC797
0x1401fc786  mov     eax, [rcx+2Ch]
0x1401fc789  test    sil, al
0x1401fc78c  jz      short loc_1401FC797
0x1401fc78e  cmp     byte ptr [rcx+29h], 3
0x1401fc792  mov     bl, sil
0x1401fc795  jnb     short loc_1401FC79A
0x1401fc797  mov     bl, dil
0x1401fc79a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fc7a1  setnz   r14b
0x1401fc7a5  test    bl, bl
0x1401fc7a7  jnz     short loc_1401FC7AE
0x1401fc7a9  test    r14b, r14b
0x1401fc7ac  jz      short loc_1401FC7EB
0x1401fc7ae  call    cs:__imp_W32GetUserSessionState
0x1401fc7b5  nop     dword ptr [rax+rax+00h]
0x1401fc7ba  mov     r9, [rax+4BD0h]
0x1401fc7c1  mov     [rsp+1B8h+var_180], r15
0x1401fc7c6  mov     word ptr [rsp+1B8h+var_188], 24h ; '$'
0x1401fc7cd  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fc7d1  mov     byte ptr [rsp+1B8h+Timeout], 3
0x1401fc7d6  mov     r8b, r14b
0x1401fc7d9  mov     dl, bl
0x1401fc7db  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fc7e2  mov     rcx, [rcx+18h]
0x1401fc7e6  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fc7eb  mov     eax, 0C000000Dh
0x1401fc7f0  jmp     loc_1401FCFA8
0x1401fc7f5  mov     ebx, [rsp+1B8h+arg_20]
0x1401fc7fc  test    ebx, ebx
0x1401fc7fe  jz      short loc_1401FC81E
0x1401fc800  mov     [rsp+1B8h+var_168], 20000h
0x1401fc808  mov     r8d, 469h
0x1401fc80e  mov     edx, [rsp+1B8h+var_168]
0x1401fc812  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fc819  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fc81e  lea     r9, [rsp+1B8h+Object]
0x1401fc823  xor     r8d, r8d
0x1401fc826  lea     edx, [r8+3]
0x1401fc82a  mov     rcx, [rsp+1B8h+var_150]
0x1401fc82f  call    RawInputManagerObjectResolveHandle
0x1401fc834  mov     r14d, eax
0x1401fc837  test    eax, eax
0x1401fc839  js      loc_1401FCF1B
0x1401fc83f  mov     r15, [rsp+1B8h+Object]
0x1401fc844  lea     rax, [r15+60h]
0x1401fc848  mov     [rsp+1B8h+var_150], rax
0x1401fc84d  mov     rcx, rax
0x1401fc850  call    RIMLockExclusive
0x1401fc855  cmp     [r15+49h], dil
0x1401fc859  jnz     loc_1401FCC32
0x1401fc85f  cmp     [r15+4Ah], dil
0x1401fc863  jnz     loc_1401FCC3C
0x1401fc869  mov     ecx, [rsp+1B8h+var_158]
0x1401fc86d  call    DeviceTypeToRimInputType
0x1401fc872  test    [r15+4Ch], eax
0x1401fc876  jz      loc_1401FCBA8
0x1401fc87c  xorps   xmm0, xmm0
0x1401fc87f  movups  xmmword ptr [rsp+1B8h+SourceString.Length], xmm0
0x1401fc884  mov     r12, rdi
0x1401fc887  mov     [rsp+1B8h+var_110], rdi
0x1401fc88f  movups  xmmword ptr [rsp+1B8h+DestinationString.Length], xmm0
0x1401fc897  test    ebx, ebx
0x1401fc899  jnz     loc_1401FC927
0x1401fc89f  mov     r12, [rsp+1B8h+var_128]
0x1401fc8a7  movups  xmm0, xmmword ptr [r13+0]
0x1401fc8ac  movups  xmmword ptr [rsp+1B8h+var_D8], xmm0
0x1401fc8b4  movups  xmm1, xmmword ptr [r13+10h]
0x1401fc8b9  movups  [rsp+1B8h+var_C8], xmm1
0x1401fc8c1  movups  xmm0, xmmword ptr [r13+20h]
0x1401fc8c6  movups  [rsp+1B8h+var_B8], xmm0
0x1401fc8ce  movups  xmm1, xmmword ptr [r13+30h]
0x1401fc8d3  movups  [rsp+1B8h+var_A8], xmm1
0x1401fc8db  movups  xmm0, xmmword ptr [r13+40h]
0x1401fc8e0  movups  [rsp+1B8h+var_98], xmm0
0x1401fc8e8  movups  xmm1, xmmword ptr [r13+50h]
0x1401fc8ed  movups  [rsp+1B8h+var_88], xmm1
0x1401fc8f5  movups  xmm0, xmmword ptr [r13+60h]
0x1401fc8fa  movups  [rsp+1B8h+var_78], xmm0
0x1401fc902  movups  xmm1, xmmword ptr [r13+70h]
0x1401fc907  movups  [rsp+1B8h+var_68], xmm1
0x1401fc90f  mov     rax, [r13+80h]
0x1401fc916  mov     [rsp+1B8h+var_58], rax
0x1401fc91e  mov     eax, [rsp+1B8h+var_158]
0x1401fc922  jmp     loc_1401FCA8A
0x1401fc927  movups  [rsp+1B8h+var_F0], xmm0
0x1401fc92f  mov     rcx, [rsp+1B8h+var_128]
0x1401fc937  call    RtlReadULongFromUser
0x1401fc93c  mov     ebx, eax
0x1401fc93e  mov     dword ptr [rsp+1B8h+var_F0], ebx
0x1401fc945  mov     rcx, [rsp+1B8h+var_128]
0x1401fc94d  add     rcx, 8
0x1401fc951  call    RtlReadULong64FromUser
0x1401fc956  mov     qword ptr [rsp+1B8h+var_F0+8], rax
0x1401fc95e  movzx   edx, bx
0x1401fc961  mov     [rsp+1B8h+SourceString.Length], dx
0x1401fc966  shr     ebx, 10h
0x1401fc969  mov     [rsp+1B8h+SourceString.MaximumLength], bx
0x1401fc96e  mov     ecx, dword ptr [rsp+1B8h+var_F0+4]
0x1401fc975  mov     dword ptr [rsp+1B8h+SourceString+4], ecx
0x1401fc979  mov     [rsp+1B8h+SourceString.Buffer], rax
0x1401fc981  mov     ebx, 2
0x1401fc986  add     rdx, rbx; Length
0x1401fc989  mov     r8d, ebx; Alignment
0x1401fc98c  mov     rcx, rax; Address
0x1401fc98f  call    cs:__imp_ProbeForRead
0x1401fc996  nop     dword ptr [rax+rax+00h]
0x1401fc99b  movzx   eax, [rsp+1B8h+SourceString.Length]
0x1401fc9a0  cmp     ax, [rsp+1B8h+SourceString.MaximumLength]
0x1401fc9a5  ja      short loc_1401FCA25
0x1401fc9a7  mov     byte ptr [rsp+1B8h+SourceString.Length], al
0x1401fc9ab  test    sil, al
0x1401fc9ae  jnz     short loc_1401FCA25
0x1401fc9b0  mov     [rsp+1B8h+DestinationString.MaximumLength], ax
0x1401fc9b8  mov     [rsp+1B8h+DestinationString.Length], ax
0x1401fc9c0  mov     edx, eax; unsigned __int64
0x1401fc9c2  mov     ecx, 100h; unsigned __int64
0x1401fc9c7  mov     r8d, 706D7452h; unsigned int
0x1401fc9cd  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fc9d2  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x1401fc9da  test    rax, rax
0x1401fc9dd  jz      short loc_1401FCA0A
0x1401fc9df  lea     rdx, [rsp+1B8h+SourceString]; SourceString
0x1401fc9e4  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x1401fc9ec  call    cs:__imp_RtlCopyUnicodeString
0x1401fc9f3  nop     dword ptr [rax+rax+00h]
0x1401fc9f8  lea     r12, [rsp+1B8h+DestinationString]
0x1401fca00  mov     [rsp+1B8h+var_110], r12
0x1401fca08  jmp     short loc_1401FCA18
0x1401fca0a  mov     r14d, 0C0000017h
0x1401fca10  mov     [rsp+1B8h+var_130], r14d
0x1401fca18  mov     ebx, [rsp+1B8h+arg_20]
0x1401fca1f  mov     eax, [rsp+1B8h+var_158]
0x1401fca23  jmp     short loc_1401FCA8A
0x1401fca25  test    byte ptr [rsp+1B8h+SourceString.Length], sil
0x1401fca2a  jz      short loc_1401FCA4A
0x1401fca2c  mov     [rsp+1B8h+var_168], 20000h
0x1401fca34  mov     r8d, 48Dh
0x1401fca3a  mov     edx, [rsp+1B8h+var_168]
0x1401fca3e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fca45  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fca4a  call    cs:__imp_ExRaiseAccessViolation
0x1401fca51  nop     dword ptr [rax+rax+00h]
0x1401fca56  nop
0x1401fca57  mov     r14d, 0C000000Dh
0x1401fca5d  mov     [rsp+1B8h+var_130], r14d
0x1401fca65  xor     edi, edi
0x1401fca67  lea     esi, [rdi+1]
0x1401fca6a  mov     r15, [rsp+1B8h+Object]
0x1401fca6f  mov     r12, [rsp+1B8h+var_110]
0x1401fca77  mov     eax, dword ptr [rsp+1B8h+var_160]
0x1401fca7b  mov     r13, [rsp+1B8h+var_100]
0x1401fca83  mov     ebx, [rsp+1B8h+arg_20]
0x1401fca8a  test    r14d, r14d
0x1401fca8d  js      loc_1401FCB6A
0x1401fca93  mov     [rsp+1B8h+var_160], rdi
0x1401fca98  lea     rcx, [rsp+1B8h+var_160]
0x1401fca9d  mov     [rsp+1B8h+var_188], rcx; __int64
0x1401fcaa2  lea     rcx, [rsp+1B8h+var_D8]
0x1401fcaaa  mov     [rsp+1B8h+var_190], rcx; __int64
0x1401fcaaf  mov     dword ptr [rsp+1B8h+Timeout], esi; int
0x1401fcab3  xor     r9d, r9d
0x1401fcab6  mov     r8, r12
0x1401fcab9  mov     edx, eax
0x1401fcabb  mov     rcx, r15; struct RawInputManagerObject *
0x1401fcabe  call    RIMCreateDev
0x1401fcac3  mov     r14d, eax
0x1401fcac6  test    ebx, ebx
0x1401fcac8  jnz     short loc_1401FCAD9
0x1401fcaca  mov     rax, [rsp+1B8h+var_58]
0x1401fcad2  mov     [r13+80h], eax
0x1401fcad9  test    r14d, r14d
0x1401fcadc  js      loc_1401FCB6A
0x1401fcae2  test    ebx, ebx
0x1401fcae4  jnz     short loc_1401FCB0C
0x1401fcae6  mov     rax, [rsp+1B8h+var_160]
0x1401fcaeb  test    byte ptr [rsp+1B8h+var_C8], sil
0x1401fcaf3  jz      short loc_1401FCAFB
0x1401fcaf5  mov     rcx, [rax+18h]
0x1401fcaf9  jmp     short loc_1401FCAFF
0x1401fcafb  mov     rcx, [rax+10h]
0x1401fcaff  mov     rdx, [rsp+1B8h+var_108]
0x1401fcb07  mov     [rdx], rcx
0x1401fcb0a  jmp     short loc_1401FCB3E
0x1401fcb0c  mov     rdx, [rsp+1B8h+var_160]
0x1401fcb11  mov     rdx, [rdx+10h]
0x1401fcb15  mov     rcx, [rsp+1B8h+var_F8]
0x1401fcb1d  call    RtlWriteULong64ToUser
0x1401fcb22  mov     rax, [rsp+1B8h+var_160]
0x1401fcb27  jmp     short loc_1401FCB3E
0x1401fcb29  xor     edi, edi
0x1401fcb2b  lea     esi, [rdi+1]
0x1401fcb2e  mov     r14d, 0C000000Dh
0x1401fcb34  mov     r15, [rsp+1B8h+Object]
0x1401fcb39  mov     rax, [rsp+1B8h+var_160]
0x1401fcb3e  test    r14d, r14d
0x1401fcb41  jns     short loc_1401FCB50
0x1401fcb43  mov     rdx, rax; struct RIMDEV *
0x1401fcb46  mov     rcx, r15; struct RawInputManagerObject *
0x1401fcb49  call    RIMFreeDev
0x1401fcb4e  jmp     short loc_1401FCB6A
0x1401fcb50  cmp     [r15+338h], rdi
0x1401fcb57  jnz     short loc_1401FCB62
0x1401fcb59  cmp     [r15+418h], edi
0x1401fcb60  jz      short loc_1401FCB6A
0x1401fcb62  bts     dword ptr [rax+0A8h], 12h
0x1401fcb6a  mov     rcx, [rsp+1B8h+DestinationString.Buffer]; Buffer
0x1401fcb72  test    rcx, rcx
0x1401fcb75  jz      short loc_1401FCB7C
0x1401fcb77  call    GreDeleteFastMutex
0x1401fcb7c  lea     r13, WPP_GLOBAL_Control
0x1401fcb83  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fcb8a  mov     rcx, [rsp+1B8h+var_150]
0x1401fcb8f  call    RIMUnlockExclusive
0x1401fcb94  mov     rcx, r15; Object
0x1401fcb97  call    cs:__imp_ObfDereferenceObject
0x1401fcb9e  nop     dword ptr [rax+rax+00h]
0x1401fcba3  jmp     loc_1401FCF28
0x1401fcba8  mov     r14d, 0C00000BBh
0x1401fcbae  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcbb5  lea     r13, WPP_GLOBAL_Control
0x1401fcbbc  cmp     rcx, r13
0x1401fcbbf  jz      short loc_1401FCBD2
0x1401fcbc1  mov     eax, [rcx+2Ch]
0x1401fcbc4  test    sil, al
0x1401fcbc7  jz      short loc_1401FCBD2
0x1401fcbc9  cmp     byte ptr [rcx+29h], 3
0x1401fcbcd  mov     bl, sil
0x1401fcbd0  jnb     short loc_1401FCBD5
0x1401fcbd2  mov     bl, dil
0x1401fcbd5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fcbdc  setnz   r12b
0x1401fcbe0  test    bl, bl
0x1401fcbe2  jnz     short loc_1401FCBE9
  ... truncated ...
```
