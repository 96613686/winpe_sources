# RIMAddInjectionDeviceOfType

- ea: `0x1401fcec0`
- end: `0x1401fd82c`
- name: `RIMAddInjectionDeviceOfType`
- size: `2412`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140204cbc`
- `0x140205070`

## callees

- `0x140029710`
- `0x140049df8`
- `0x140049ec0`
- `0x14004c020`
- `0x14004f4c0`
- `0x140062ff0`
- `0x1400682c0`
- `0x1400701d4`
- `0x14007b930`
- `0x14007efd0`
- `0x140092750`
- `0x1400dd4cc`
- `0x1400ff080`
- `0x140137f60`
- `0x1401aab9c`
- `0x1401fcec0`
- `0x1402388e0`
- `0x140238a40`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fd1ef`
- `ntoskrnl!ProbeForRead` at `0x1401fd1ef`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd2aa`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd2aa`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fd63d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401fd63d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd24c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd24c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fd5e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401fd5e4`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd3f7`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd3f7`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf8a`
- `WIN32K!W32GetUserSessionState` at `0x1401fd00e`
- `WIN32K!W32GetUserSessionState` at `0x1401fd449`
- `WIN32K!W32GetUserSessionState` at `0x1401fd4ea`
- `WIN32K!W32GetUserSessionState` at `0x1401fd574`
- `WIN32K!W32GetUserSessionState` at `0x1401fd5f0`
- `WIN32K!W32GetUserSessionState` at `0x1401fd750`
- `WIN32K!W32GetUserSessionState` at `0x1401fd7bc`
- `WIN32K!W32GetUserSessionState` at `0x1401fcf8a`
- `WIN32K!W32GetUserSessionState` at `0x1401fd00e`
- `WIN32K!W32GetUserSessionState` at `0x1401fd449`
- `WIN32K!W32GetUserSessionState` at `0x1401fd4ea`
- `WIN32K!W32GetUserSessionState` at `0x1401fd574`
- `WIN32K!W32GetUserSessionState` at `0x1401fd5f0`
- `WIN32K!W32GetUserSessionState` at `0x1401fd750`
- `WIN32K!W32GetUserSessionState` at `0x1401fd7bc`

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
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r14
  __int64 v51; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v53; // rax
  char v54; // al
  _QWORD *i; // rbx
  char v56; // bl
  bool v57; // r15
  __int64 v58; // rax
  int v59; // r8d
  int v60; // edx
  __int16 v61; // [rsp+30h] [rbp-188h]
  struct RIMDEV *v62; // [rsp+58h] [rbp-160h] BYREF
  unsigned int v63; // [rsp+60h] [rbp-158h]
  char *v64; // [rsp+68h] [rbp-150h]
  PVOID Object; // [rsp+70h] [rbp-148h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-140h] BYREF
  int v67; // [rsp+88h] [rbp-130h]
  __int64 v68; // [rsp+90h] [rbp-128h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-120h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+A8h] [rbp-110h]
  _QWORD *v71; // [rsp+B0h] [rbp-108h]
  __int64 v72; // [rsp+B8h] [rbp-100h]
  __int64 v73; // [rsp+C0h] [rbp-F8h]
  __int128 v74; // [rsp+C8h] [rbp-F0h]
  __int64 v75[18]; // [rsp+E0h] [rbp-D8h] BYREF

  v63 = a3;
  v68 = a2;
  v64 = a1;
  v71 = a6;
  LODWORD(v62) = a3;
  v72 = a4;
  v73 = (__int64)a6;
  Object = 0;
  memset(v75, 0, 0x88u);
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
  v22 = RawInputManagerObjectResolveHandle(v64, 3u, 0, &Object);
  if ( v22 >= 0 )
  {
    v23 = (PVOID *)Object;
    v64 = (char *)Object + 96;
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
        v61 = 40;
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
          v61,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_49:
        RIMUnlockExclusive(v64);
        ObfDereferenceObject(v23);
        goto LABEL_98;
      }
    }
    else if ( !*((_BYTE *)v23 + 74) )
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(v63) & *((_DWORD *)v23 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v74 = 0;
          ULongFromUser = RtlReadULongFromUser(v68);
          LODWORD(v74) = ULongFromUser;
          *((_QWORD *)&v74 + 1) = RtlReadULong64FromUser(v68 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v74);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v74 + 1);
          ProbeForRead(*((volatile void **)&v74 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
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
            v67 = -1073741801;
          }
          v19 = a5;
        }
        else
        {
          *(_OWORD *)v75 = *(_OWORD *)a4;
          *(_OWORD *)&v75[2] = *(_OWORD *)(a4 + 16);
          *(_OWORD *)&v75[4] = *(_OWORD *)(a4 + 32);
          *(_OWORD *)&v75[6] = *(_OWORD *)(a4 + 48);
          *(_OWORD *)&v75[8] = *(_OWORD *)(a4 + 64);
          *(_OWORD *)&v75[10] = *(_OWORD *)(a4 + 80);
          *(_OWORD *)&v75[12] = *(_OWORD *)(a4 + 96);
          *(_OWORD *)&v75[14] = *(_OWORD *)(a4 + 112);
          v75[16] = *(_QWORD *)(a4 + 128);
        }
        if ( v22 >= 0 )
        {
          v62 = 0;
          v22 = RIMCreateDev((struct RawInputManagerObject *)v23, 1, (__int64)v75, (__int64)&v62);
          if ( !v19 )
            *(_DWORD *)(a4 + 128) = v75[16];
          if ( v22 >= 0 )
          {
            if ( v19 )
            {
              RtlWriteULong64ToUser(v73, *((_QWORD *)v62 + 2));
              v29 = v62;
            }
            else
            {
              v29 = v62;
              v30 = (v75[2] & 1) != 0 ? *((_QWORD *)v62 + 3) : *((_QWORD *)v62 + 2);
              *v71 = v30;
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
      v61 = 37;
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
    RIMUnlockExclusive(v64);
    UserSessionSwitchLeaveCritWithNonPaged(v46);
    KeWaitForSingleObject(v23[136], UserRequest, 0, 0, 0);
    v50 = W32GetUserSessionState(v48, v47, v49);
    v51 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
            v50,
            1,
            0,
            _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(v50 + 16) = v51;
    if ( v51 )
    {
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v51 + 520), 0, 0) & 0x1000000) == 0
        || *(char *)(v51 + 1360) < 0 )
      {
        v54 = 0;
LABEL_83:
        if ( v54 )
        {
          for ( i = *(_QWORD **)(v50 + 19544); i; i = *(_QWORD **)(v50 + 19544) )
          {
            *(_QWORD *)(v50 + 19544) = i[2];
            i[2] = 0;
            if ( !*(_DWORD *)(*i + 8LL) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
            HMUnlockObject(*i);
          }
          DestroyDeferredUnlockObjectAssignmentList(v50 + 19576);
          DestroyDeferredUnlockObjectAssignmentList(v50 + 19560);
        }
        goto LABEL_89;
      }
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        v53 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
        if ( v53 )
        {
          if ( *(_BYTE *)(v53 + 1200) == 1 )
          {
            v54 = 1;
            goto LABEL_83;
          }
        }
      }
    }
LABEL_89:
    RIMLockExclusive(v64);
    v22 = -2147483631;
    goto LABEL_49;
  }
  v22 = -1073741816;
LABEL_98:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v56 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v56 = 0;
  }
  v57 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v56 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v58 = W32GetUserSessionState(WPP_GLOBAL_Control, v20, v21);
    LOBYTE(v59) = v57;
    LOBYTE(v60) = v56;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v60,
      v59,
      *(_QWORD *)(v58 + 19408),
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
0x1401fcec0  push    rbx
0x1401fcec2  push    rsi
0x1401fcec3  push    rdi
0x1401fcec4  push    r12
0x1401fcec6  push    r13
0x1401fcec8  push    r14
0x1401fceca  push    r15
0x1401fcecc  sub     rsp, 180h
0x1401fced3  mov     rax, cs:__security_cookie
0x1401fceda  xor     rax, rsp
0x1401fcedd  mov     [rsp+1B8h+var_48], rax
0x1401fcee5  mov     r13, r9
0x1401fcee8  mov     eax, r8d
0x1401fceeb  mov     [rsp+1B8h+var_158], eax
0x1401fceef  mov     [rsp+1B8h+var_128], rdx
0x1401fcef7  mov     [rsp+1B8h+var_150], rcx
0x1401fcefc  mov     rcx, [rsp+1B8h+arg_28]
0x1401fcf04  mov     [rsp+1B8h+var_108], rcx
0x1401fcf0c  mov     dword ptr [rsp+1B8h+var_160], eax
0x1401fcf10  mov     [rsp+1B8h+var_100], r9
0x1401fcf18  mov     [rsp+1B8h+var_F8], rcx
0x1401fcf20  xor     edi, edi
0x1401fcf22  mov     [rsp+1B8h+Object], rdi
0x1401fcf27  xor     edx, edx; Val
0x1401fcf29  mov     r8d, 88h; Size
0x1401fcf2f  lea     rcx, [rsp+1B8h+var_D8]; void *
0x1401fcf37  call    memset
0x1401fcf3c  lea     rdx, WPP_GLOBAL_Control
0x1401fcf43  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcf4a  lea     esi, [rdi+1]
0x1401fcf4d  cmp     rcx, rdx
0x1401fcf50  jz      short loc_1401FCF63
0x1401fcf52  mov     eax, [rcx+2Ch]
0x1401fcf55  test    sil, al
0x1401fcf58  jz      short loc_1401FCF63
0x1401fcf5a  cmp     byte ptr [rcx+29h], 4
0x1401fcf5e  mov     bl, sil
0x1401fcf61  jnb     short loc_1401FCF66
0x1401fcf63  mov     bl, dil
0x1401fcf66  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fcf6d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fcf74  setnz   r14b
0x1401fcf78  test    bl, bl
0x1401fcf7a  jnz     short loc_1401FCF8A
0x1401fcf7c  test    r14b, r14b
0x1401fcf7f  jnz     short loc_1401FCF8A
0x1401fcf81  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fcf88  jmp     short loc_1401FCFD5
0x1401fcf8a  call    cs:__imp_W32GetUserSessionState
0x1401fcf91  nop     dword ptr [rax+rax+00h]
0x1401fcf96  mov     r9, [rax+4BD0h]
0x1401fcf9d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fcfa4  mov     [rsp+1B8h+var_180], r15
0x1401fcfa9  mov     word ptr [rsp+1B8h+var_188], 23h ; '#'
0x1401fcfb0  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fcfb4  mov     byte ptr [rsp+1B8h+Timeout], 4
0x1401fcfb9  mov     r8b, r14b
0x1401fcfbc  mov     dl, bl
0x1401fcfbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcfc5  mov     rcx, [rcx+18h]
0x1401fcfc9  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fcfce  lea     rdx, WPP_GLOBAL_Control
0x1401fcfd5  test    r13, r13
0x1401fcfd8  jnz     short loc_1401FD055
0x1401fcfda  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fcfe1  cmp     rcx, rdx
0x1401fcfe4  jz      short loc_1401FCFF7
0x1401fcfe6  mov     eax, [rcx+2Ch]
0x1401fcfe9  test    sil, al
0x1401fcfec  jz      short loc_1401FCFF7
0x1401fcfee  cmp     byte ptr [rcx+29h], 3
0x1401fcff2  mov     bl, sil
0x1401fcff5  jnb     short loc_1401FCFFA
0x1401fcff7  mov     bl, dil
0x1401fcffa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd001  setnz   r14b
0x1401fd005  test    bl, bl
0x1401fd007  jnz     short loc_1401FD00E
0x1401fd009  test    r14b, r14b
0x1401fd00c  jz      short loc_1401FD04B
0x1401fd00e  call    cs:__imp_W32GetUserSessionState
0x1401fd015  nop     dword ptr [rax+rax+00h]
0x1401fd01a  mov     r9, [rax+4BD0h]
0x1401fd021  mov     [rsp+1B8h+var_180], r15
0x1401fd026  mov     word ptr [rsp+1B8h+var_188], 24h ; '$'
0x1401fd02d  mov     dword ptr [rsp+1B8h+var_190], esi
0x1401fd031  mov     byte ptr [rsp+1B8h+Timeout], 3
0x1401fd036  mov     r8b, r14b
0x1401fd039  mov     dl, bl
0x1401fd03b  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd042  mov     rcx, [rcx+18h]
0x1401fd046  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fd04b  mov     eax, 0C000000Dh
0x1401fd050  jmp     loc_1401FD808
0x1401fd055  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd05c  test    ebx, ebx
0x1401fd05e  jz      short loc_1401FD07E
0x1401fd060  mov     [rsp+1B8h+var_168], 20000h
0x1401fd068  mov     r8d, 469h
0x1401fd06e  mov     edx, [rsp+1B8h+var_168]
0x1401fd072  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fd079  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fd07e  lea     r9, [rsp+1B8h+Object]
0x1401fd083  xor     r8d, r8d
0x1401fd086  lea     edx, [r8+3]
0x1401fd08a  mov     rcx, [rsp+1B8h+var_150]
0x1401fd08f  call    RawInputManagerObjectResolveHandle
0x1401fd094  mov     r14d, eax
0x1401fd097  test    eax, eax
0x1401fd099  js      loc_1401FD77B
0x1401fd09f  mov     r15, [rsp+1B8h+Object]
0x1401fd0a4  lea     rax, [r15+60h]
0x1401fd0a8  mov     [rsp+1B8h+var_150], rax
0x1401fd0ad  mov     rcx, rax
0x1401fd0b0  call    RIMLockExclusive
0x1401fd0b5  cmp     [r15+49h], dil
0x1401fd0b9  jnz     loc_1401FD492
0x1401fd0bf  cmp     [r15+4Ah], dil
0x1401fd0c3  jnz     loc_1401FD49C
0x1401fd0c9  mov     ecx, [rsp+1B8h+var_158]
0x1401fd0cd  call    DeviceTypeToRimInputType
0x1401fd0d2  test    [r15+4Ch], eax
0x1401fd0d6  jz      loc_1401FD408
0x1401fd0dc  xorps   xmm0, xmm0
0x1401fd0df  movups  xmmword ptr [rsp+1B8h+SourceString.Length], xmm0
0x1401fd0e4  mov     r12, rdi
0x1401fd0e7  mov     [rsp+1B8h+var_110], rdi
0x1401fd0ef  movups  xmmword ptr [rsp+1B8h+DestinationString.Length], xmm0
0x1401fd0f7  test    ebx, ebx
0x1401fd0f9  jnz     loc_1401FD187
0x1401fd0ff  mov     r12, [rsp+1B8h+var_128]
0x1401fd107  movups  xmm0, xmmword ptr [r13+0]
0x1401fd10c  movups  xmmword ptr [rsp+1B8h+var_D8], xmm0
0x1401fd114  movups  xmm1, xmmword ptr [r13+10h]
0x1401fd119  movups  [rsp+1B8h+var_C8], xmm1
0x1401fd121  movups  xmm0, xmmword ptr [r13+20h]
0x1401fd126  movups  [rsp+1B8h+var_B8], xmm0
0x1401fd12e  movups  xmm1, xmmword ptr [r13+30h]
0x1401fd133  movups  [rsp+1B8h+var_A8], xmm1
0x1401fd13b  movups  xmm0, xmmword ptr [r13+40h]
0x1401fd140  movups  [rsp+1B8h+var_98], xmm0
0x1401fd148  movups  xmm1, xmmword ptr [r13+50h]
0x1401fd14d  movups  [rsp+1B8h+var_88], xmm1
0x1401fd155  movups  xmm0, xmmword ptr [r13+60h]
0x1401fd15a  movups  [rsp+1B8h+var_78], xmm0
0x1401fd162  movups  xmm1, xmmword ptr [r13+70h]
0x1401fd167  movups  [rsp+1B8h+var_68], xmm1
0x1401fd16f  mov     rax, [r13+80h]
0x1401fd176  mov     [rsp+1B8h+var_58], rax
0x1401fd17e  mov     eax, [rsp+1B8h+var_158]
0x1401fd182  jmp     loc_1401FD2EA
0x1401fd187  movups  [rsp+1B8h+var_F0], xmm0
0x1401fd18f  mov     rcx, [rsp+1B8h+var_128]
0x1401fd197  call    RtlReadULongFromUser
0x1401fd19c  mov     ebx, eax
0x1401fd19e  mov     dword ptr [rsp+1B8h+var_F0], ebx
0x1401fd1a5  mov     rcx, [rsp+1B8h+var_128]
0x1401fd1ad  add     rcx, 8
0x1401fd1b1  call    RtlReadULong64FromUser
0x1401fd1b6  mov     qword ptr [rsp+1B8h+var_F0+8], rax
0x1401fd1be  movzx   edx, bx
0x1401fd1c1  mov     [rsp+1B8h+SourceString.Length], dx
0x1401fd1c6  shr     ebx, 10h
0x1401fd1c9  mov     [rsp+1B8h+SourceString.MaximumLength], bx
0x1401fd1ce  mov     ecx, dword ptr [rsp+1B8h+var_F0+4]
0x1401fd1d5  mov     dword ptr [rsp+1B8h+SourceString+4], ecx
0x1401fd1d9  mov     [rsp+1B8h+SourceString.Buffer], rax
0x1401fd1e1  mov     ebx, 2
0x1401fd1e6  add     rdx, rbx; Length
0x1401fd1e9  mov     r8d, ebx; Alignment
0x1401fd1ec  mov     rcx, rax; Address
0x1401fd1ef  call    cs:__imp_ProbeForRead
0x1401fd1f6  nop     dword ptr [rax+rax+00h]
0x1401fd1fb  movzx   eax, [rsp+1B8h+SourceString.Length]
0x1401fd200  cmp     ax, [rsp+1B8h+SourceString.MaximumLength]
0x1401fd205  ja      short loc_1401FD285
0x1401fd207  mov     byte ptr [rsp+1B8h+SourceString.Length], al
0x1401fd20b  test    sil, al
0x1401fd20e  jnz     short loc_1401FD285
0x1401fd210  mov     [rsp+1B8h+DestinationString.MaximumLength], ax
0x1401fd218  mov     [rsp+1B8h+DestinationString.Length], ax
0x1401fd220  mov     edx, eax; unsigned __int64
0x1401fd222  mov     ecx, 100h; unsigned __int64
0x1401fd227  mov     r8d, 706D7452h; unsigned int
0x1401fd22d  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fd232  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x1401fd23a  test    rax, rax
0x1401fd23d  jz      short loc_1401FD26A
0x1401fd23f  lea     rdx, [rsp+1B8h+SourceString]; SourceString
0x1401fd244  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x1401fd24c  call    cs:__imp_RtlCopyUnicodeString
0x1401fd253  nop     dword ptr [rax+rax+00h]
0x1401fd258  lea     r12, [rsp+1B8h+DestinationString]
0x1401fd260  mov     [rsp+1B8h+var_110], r12
0x1401fd268  jmp     short loc_1401FD278
0x1401fd26a  mov     r14d, 0C0000017h
0x1401fd270  mov     [rsp+1B8h+var_130], r14d
0x1401fd278  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd27f  mov     eax, [rsp+1B8h+var_158]
0x1401fd283  jmp     short loc_1401FD2EA
0x1401fd285  test    byte ptr [rsp+1B8h+SourceString.Length], sil
0x1401fd28a  jz      short loc_1401FD2AA
0x1401fd28c  mov     [rsp+1B8h+var_168], 20000h
0x1401fd294  mov     r8d, 48Dh
0x1401fd29a  mov     edx, [rsp+1B8h+var_168]
0x1401fd29e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fd2a5  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fd2aa  call    cs:__imp_ExRaiseAccessViolation
0x1401fd2b1  nop     dword ptr [rax+rax+00h]
0x1401fd2b6  nop
0x1401fd2b7  mov     r14d, 0C000000Dh
0x1401fd2bd  mov     [rsp+1B8h+var_130], r14d
0x1401fd2c5  xor     edi, edi
0x1401fd2c7  lea     esi, [rdi+1]
0x1401fd2ca  mov     r15, [rsp+1B8h+Object]
0x1401fd2cf  mov     r12, [rsp+1B8h+var_110]
0x1401fd2d7  mov     eax, dword ptr [rsp+1B8h+var_160]
0x1401fd2db  mov     r13, [rsp+1B8h+var_100]
0x1401fd2e3  mov     ebx, [rsp+1B8h+arg_20]
0x1401fd2ea  test    r14d, r14d
0x1401fd2ed  js      loc_1401FD3CA
0x1401fd2f3  mov     [rsp+1B8h+var_160], rdi
0x1401fd2f8  lea     rcx, [rsp+1B8h+var_160]
0x1401fd2fd  mov     [rsp+1B8h+var_188], rcx; __int64
0x1401fd302  lea     rcx, [rsp+1B8h+var_D8]
0x1401fd30a  mov     [rsp+1B8h+var_190], rcx; __int64
0x1401fd30f  mov     dword ptr [rsp+1B8h+Timeout], esi; int
0x1401fd313  xor     r9d, r9d
0x1401fd316  mov     r8, r12
0x1401fd319  mov     edx, eax
0x1401fd31b  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd31e  call    RIMCreateDev
0x1401fd323  mov     r14d, eax
0x1401fd326  test    ebx, ebx
0x1401fd328  jnz     short loc_1401FD339
0x1401fd32a  mov     rax, [rsp+1B8h+var_58]
0x1401fd332  mov     [r13+80h], eax
0x1401fd339  test    r14d, r14d
0x1401fd33c  js      loc_1401FD3CA
0x1401fd342  test    ebx, ebx
0x1401fd344  jnz     short loc_1401FD36C
0x1401fd346  mov     rax, [rsp+1B8h+var_160]
0x1401fd34b  test    byte ptr [rsp+1B8h+var_C8], sil
0x1401fd353  jz      short loc_1401FD35B
0x1401fd355  mov     rcx, [rax+18h]
0x1401fd359  jmp     short loc_1401FD35F
0x1401fd35b  mov     rcx, [rax+10h]
0x1401fd35f  mov     rdx, [rsp+1B8h+var_108]
0x1401fd367  mov     [rdx], rcx
0x1401fd36a  jmp     short loc_1401FD39E
0x1401fd36c  mov     rdx, [rsp+1B8h+var_160]
0x1401fd371  mov     rdx, [rdx+10h]
0x1401fd375  mov     rcx, [rsp+1B8h+var_F8]
0x1401fd37d  call    RtlWriteULong64ToUser
0x1401fd382  mov     rax, [rsp+1B8h+var_160]
0x1401fd387  jmp     short loc_1401FD39E
0x1401fd389  xor     edi, edi
0x1401fd38b  lea     esi, [rdi+1]
0x1401fd38e  mov     r14d, 0C000000Dh
0x1401fd394  mov     r15, [rsp+1B8h+Object]
0x1401fd399  mov     rax, [rsp+1B8h+var_160]
0x1401fd39e  test    r14d, r14d
0x1401fd3a1  jns     short loc_1401FD3B0
0x1401fd3a3  mov     rdx, rax; struct RIMDEV *
0x1401fd3a6  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd3a9  call    RIMFreeDev
0x1401fd3ae  jmp     short loc_1401FD3CA
0x1401fd3b0  cmp     [r15+338h], rdi
0x1401fd3b7  jnz     short loc_1401FD3C2
0x1401fd3b9  cmp     [r15+418h], edi
0x1401fd3c0  jz      short loc_1401FD3CA
0x1401fd3c2  bts     dword ptr [rax+0A8h], 12h
0x1401fd3ca  mov     rcx, [rsp+1B8h+DestinationString.Buffer]; Buffer
0x1401fd3d2  test    rcx, rcx
0x1401fd3d5  jz      short loc_1401FD3DC
0x1401fd3d7  call    GreDeleteFastMutex
0x1401fd3dc  lea     r13, WPP_GLOBAL_Control
0x1401fd3e3  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fd3ea  mov     rcx, [rsp+1B8h+var_150]
0x1401fd3ef  call    RIMUnlockExclusive
0x1401fd3f4  mov     rcx, r15; Object
0x1401fd3f7  call    cs:__imp_ObfDereferenceObject
0x1401fd3fe  nop     dword ptr [rax+rax+00h]
0x1401fd403  jmp     loc_1401FD788
0x1401fd408  mov     r14d, 0C00000BBh
0x1401fd40e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd415  lea     r13, WPP_GLOBAL_Control
0x1401fd41c  cmp     rcx, r13
0x1401fd41f  jz      short loc_1401FD432
0x1401fd421  mov     eax, [rcx+2Ch]
0x1401fd424  test    sil, al
0x1401fd427  jz      short loc_1401FD432
0x1401fd429  cmp     byte ptr [rcx+29h], 3
0x1401fd42d  mov     bl, sil
0x1401fd430  jnb     short loc_1401FD435
0x1401fd432  mov     bl, dil
0x1401fd435  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd43c  setnz   r12b
0x1401fd440  test    bl, bl
0x1401fd442  jnz     short loc_1401FD449
  ... truncated ...
```
