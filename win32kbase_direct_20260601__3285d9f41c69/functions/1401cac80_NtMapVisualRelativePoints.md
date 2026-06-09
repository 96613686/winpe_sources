# NtMapVisualRelativePoints

- ea: `0x1401cac80`
- end: `0x1401caf97`
- name: `NtMapVisualRelativePoints`
- size: `791`
- prototype: `__int64 __fastcall(int, int, int, int, volatile void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033364`
- `0x140074bf0`
- `0x140078090`
- `0x1400b1d40`
- `0x14018a6e0`
- `0x1401a9f9c`
- `0x1401ca324`
- `0x1401cac80`
- `0x1401cafa0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401cae23`
- `ntoskrnl!ProbeForRead` at `0x1401cae23`
- `ntoskrnl!ProbeForWrite` at `0x1401cae55`
- `ntoskrnl!ProbeForWrite` at `0x1401cae55`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cadfa`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cae2f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cadfa`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cae2f`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401caea4`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401caea4`
- `WIN32K!W32GetUserSessionState` at `0x1401caca2`
- `WIN32K!W32GetUserSessionState` at `0x1401cad7c`
- `WIN32K!W32GetUserSessionState` at `0x1401caf34`
- `WIN32K!W32GetUserSessionState` at `0x1401caca2`
- `WIN32K!W32GetUserSessionState` at `0x1401cad7c`
- `WIN32K!W32GetUserSessionState` at `0x1401caf34`

## pseudocode

```c
__int64 __fastcall NtMapVisualRelativePoints(void *a1, void *a2, __int64 a3, char *a4, char *a5)
{
  __int64 UserSessionState; // r14
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // si
  _QWORD *v10; // rbx
  char v11; // bl
  bool v12; // r14
  __int64 v13; // rax
  int v14; // r8d
  int v15; // edx
  __int64 CurrentProcessWow64Process; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  CTouchProcessor *v19; // rcx
  __int64 v20; // r8
  int i; // ebx
  NTSTATUS v22; // eax
  int v23; // r14d
  ULONG v24; // eax
  bool v25; // r12
  char LastError; // bl
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  unsigned int v36; // [rsp+C0h] [rbp+18h]

  v36 = a3;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  v6 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
         UserSessionState,
         0,
         0,
         _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v6;
  v9 = 1;
  if ( v6 )
  {
    while ( 1 )
    {
      v10 = *(_QWORD **)(UserSessionState + 19544);
      if ( !v10 )
        break;
      *(_QWORD *)(UserSessionState + 19544) = v10[2];
      v10[2] = 0;
      if ( !*(_DWORD *)(*v10 + 8LL) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
      HMUnlockObject(*v10);
    }
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v11 = 0;
  }
  v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = W32GetUserSessionState(WPP_GLOBAL_Control, v7, v8);
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v11;
    WPP_RECORDER_AND_TRACE_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v14,
      *(_QWORD *)(v13 + 69136),
      4,
      2,
      10,
      (__int64)WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids,
      (char)a1,
      (char)a2);
  }
  if ( 8 * (unsigned __int64)v36 > 0xFFFFFFFF )
  {
    v23 = 0;
    UserSetLastError(8);
  }
  else
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 8 * v36, CurrentProcessWow64Process != 0 ? 1 : 4);
    v17 = PsGetCurrentProcessWow64Process();
    ProbeForWrite(a5, 8 * v36, v17 != 0 ? 1 : 4);
    for ( i = 0; i != v36; ++i )
    {
      v22 = KernelMapVisualRelativePoint(
              a1,
              a2,
              (const struct VisualPoint *)&a4[8 * i],
              (struct VisualPoint *)&a5[8 * i]);
      if ( v22 < 0 )
      {
        v23 = 0;
        v24 = RtlNtStatusToDosError(v22);
        UserSetLastError(v24);
        goto LABEL_22;
      }
    }
    v23 = 1;
  }
LABEL_22:
  if ( !v23 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      v9 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LastError = UserGetLastError();
      v30 = W32GetUserSessionState(v28, v27, v29);
      LOBYTE(v31) = v25;
      LOBYTE(v32) = v9;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 69136),
        2,
        2,
        11,
        (__int64)WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids,
        LastError);
    }
  }
  UserSessionSwitchLeaveCritWithNonPaged((__int64)v19, v18, v20);
  return v23;
}

```

## disassembly

```asm
0x1401cac80  mov     rax, rsp
0x1401cac83  mov     [rax+20h], r9
0x1401cac87  mov     [rax+18h], r8d
0x1401cac8b  mov     [rax+10h], rdx
0x1401cac8f  mov     [rax+8], rcx
0x1401cac93  push    rbx
0x1401cac94  push    rsi
0x1401cac95  push    rdi
0x1401cac96  push    r12
0x1401cac98  push    r13
0x1401cac9a  push    r14
0x1401cac9c  push    r15
0x1401cac9e  sub     rsp, 70h
0x1401caca2  call    cs:__imp_W32GetUserSessionState
0x1401caca9  nop     dword ptr [rax+rax+00h]
0x1401cacae  mov     r14, rax
0x1401cacb1  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cacb8  xor     r8d, r8d
0x1401cacbb  xor     edx, edx
0x1401cacbd  mov     rcx, rax
0x1401cacc0  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cacc5  mov     [r14+10h], rax
0x1401cacc9  xor     edi, edi
0x1401caccb  lea     esi, [rdi+1]
0x1401cacce  lea     r15d, [rdi+2]
0x1401cacd2  test    rax, rax
0x1401cacd5  jz      short loc_1401CAD3A
0x1401cacd7  mov     rbx, [r14+4C58h]
0x1401cacde  test    rbx, rbx
0x1401cace1  jz      short loc_1401CAD22
0x1401cace3  mov     rax, [rbx+10h]
0x1401cace7  mov     [r14+4C58h], rax
0x1401cacee  mov     [rbx+10h], rdi
0x1401cacf2  mov     rax, [rbx]
0x1401cacf5  cmp     [rax+8], esi
0x1401cacf8  jnb     short loc_1401CAD18
0x1401cacfa  mov     [rsp+0A8h+var_58], 20000h
0x1401cad02  mov     r8d, 1236h
0x1401cad08  mov     edx, [rsp+0A8h+var_58]
0x1401cad0c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401cad13  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401cad18  mov     rcx, [rbx]
0x1401cad1b  call    HMUnlockObject
0x1401cad20  jmp     short loc_1401CACD7
0x1401cad22  lea     rcx, [r14+4C78h]
0x1401cad29  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cad2e  lea     rcx, [r14+4C68h]
0x1401cad35  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cad3a  lea     r12, WPP_GLOBAL_Control
0x1401cad41  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cad48  cmp     rcx, r12
0x1401cad4b  jz      short loc_1401CAD5E
0x1401cad4d  mov     eax, [rcx+2Ch]
0x1401cad50  test    r15b, al
0x1401cad53  jz      short loc_1401CAD5E
0x1401cad55  cmp     byte ptr [rcx+29h], 4
0x1401cad59  mov     bl, sil
0x1401cad5c  jnb     short loc_1401CAD61
0x1401cad5e  mov     bl, dil
0x1401cad61  lea     r13, WPP_RECORDER_INITIALIZED
0x1401cad68  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401cad6f  setnz   r14b
0x1401cad73  test    bl, bl
0x1401cad75  jnz     short loc_1401CAD7C
0x1401cad77  test    r14b, r14b
0x1401cad7a  jz      short loc_1401CADDB
0x1401cad7c  call    cs:__imp_W32GetUserSessionState
0x1401cad83  nop     dword ptr [rax+rax+00h]
0x1401cad88  mov     r9, [rax+10E10h]
0x1401cad8f  mov     rax, [rsp+0A8h+arg_8]
0x1401cad97  mov     [rsp+0A8h+var_60], rax
0x1401cad9c  mov     rax, [rsp+0A8h+arg_0]
0x1401cada4  mov     [rsp+0A8h+var_68], rax
0x1401cada9  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401cadb0  mov     [rsp+0A8h+var_70], rax
0x1401cadb5  mov     [rsp+0A8h+var_78], 0Ah
0x1401cadbc  mov     [rsp+0A8h+var_80], r15d
0x1401cadc1  mov     [rsp+0A8h+var_88], 4
0x1401cadc6  mov     r8b, r14b
0x1401cadc9  mov     dl, bl
0x1401cadcb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cadd2  mov     rcx, [rcx+18h]
0x1401cadd6  call    WPP_RECORDER_AND_TRACE_SF_ii
0x1401caddb  mov     eax, [rsp+0A8h+arg_10]
0x1401cade2  shl     rax, 3
0x1401cade6  mov     ecx, 0FFFFFFFFh
0x1401cadeb  cmp     rax, rcx
0x1401cadee  ja      loc_1401CAEE5
0x1401cadf4  mov     [rsp+0A8h+var_58], edi
0x1401cadf8  mov     ebx, eax
0x1401cadfa  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cae01  nop     dword ptr [rax+rax+00h]
0x1401cae06  neg     rax
0x1401cae09  sbb     r8d, r8d
0x1401cae0c  mov     r14d, 0FFFFFFFDh
0x1401cae12  and     r8d, r14d
0x1401cae15  add     r8d, 4; Alignment
0x1401cae19  mov     edx, ebx; Length
0x1401cae1b  mov     rcx, [rsp+0A8h+Address]; Address
0x1401cae23  call    cs:__imp_ProbeForRead
0x1401cae2a  nop     dword ptr [rax+rax+00h]
0x1401cae2f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cae36  nop     dword ptr [rax+rax+00h]
0x1401cae3b  neg     rax
0x1401cae3e  sbb     r8d, r8d
0x1401cae41  and     r8d, r14d
0x1401cae44  add     r8d, 4; Alignment
0x1401cae48  mov     edx, ebx; Length
0x1401cae4a  mov     r14, [rsp+0A8h+arg_20]
0x1401cae52  mov     rcx, r14; Address
0x1401cae55  call    cs:__imp_ProbeForWrite
0x1401cae5c  nop     dword ptr [rax+rax+00h]
0x1401cae61  mov     ebx, edi
0x1401cae63  mov     [rsp+0A8h+var_54], ebx
0x1401cae67  cmp     ebx, [rsp+0A8h+arg_10]
0x1401cae6e  jz      short loc_1401CAEBD
0x1401cae70  mov     eax, ebx
0x1401cae72  lea     r9, [r14+rax*8]; struct VisualPoint *
0x1401cae76  mov     rcx, [rsp+0A8h+Address]
0x1401cae7e  lea     r8, [rcx+rax*8]; struct VisualPoint *
0x1401cae82  mov     rdx, [rsp+0A8h+arg_8]; void *
0x1401cae8a  mov     rcx, [rsp+0A8h+arg_0]; void *
0x1401cae92  call    ?KernelMapVisualRelativePoint@@YAJ_J0PEBUVisualPoint@@PEAU1@@Z; KernelMapVisualRelativePoint(__int64,__int64,VisualPoint const *,VisualPoint *)
0x1401cae97  test    eax, eax
0x1401cae99  jns     short loc_1401CAEB9
0x1401cae9b  mov     r14d, edi
0x1401cae9e  mov     [rsp+0A8h+var_44], edi
0x1401caea2  mov     ecx, eax; Status
0x1401caea4  call    cs:__imp_RtlNtStatusToDosError
0x1401caeab  nop     dword ptr [rax+rax+00h]
0x1401caeb0  mov     ecx, eax
0x1401caeb2  call    UserSetLastError
0x1401caeb7  jmp     short loc_1401CAEF2
0x1401caeb9  add     ebx, esi
0x1401caebb  jmp     short loc_1401CAE63
0x1401caebd  mov     r14d, esi
0x1401caec0  jmp     short loc_1401CAEF2
0x1401caec2  mov     r14d, [rsp+0A8h+var_58]
0x1401caec7  mov     [rsp+0A8h+var_44], r14d
0x1401caecc  xor     edi, edi
0x1401caece  lea     esi, [rdi+1]
0x1401caed1  lea     r15d, [rdi+2]
0x1401caed5  lea     r12, WPP_GLOBAL_Control
0x1401caedc  lea     r13, WPP_RECORDER_INITIALIZED
0x1401caee3  jmp     short loc_1401CAEF2
0x1401caee5  mov     r14d, edi
0x1401caee8  mov     ecx, 8
0x1401caeed  call    UserSetLastError
0x1401caef2  test    r14d, r14d
0x1401caef5  jnz     loc_1401CAF7E
0x1401caefb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401caf02  cmp     rcx, r12
0x1401caf05  jz      short loc_1401CAF15
0x1401caf07  mov     eax, [rcx+2Ch]
0x1401caf0a  test    r15b, al
0x1401caf0d  jz      short loc_1401CAF15
0x1401caf0f  cmp     [rcx+29h], r15b
0x1401caf13  jnb     short loc_1401CAF18
0x1401caf15  mov     sil, dil
0x1401caf18  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401caf1f  setnz   r12b
0x1401caf23  test    sil, sil
0x1401caf26  jnz     short loc_1401CAF2D
0x1401caf28  test    r12b, r12b
0x1401caf2b  jz      short loc_1401CAF7E
0x1401caf2d  call    UserGetLastError
0x1401caf32  mov     ebx, eax
0x1401caf34  call    cs:__imp_W32GetUserSessionState
0x1401caf3b  nop     dword ptr [rax+rax+00h]
0x1401caf40  mov     r9, [rax+10E10h]
0x1401caf47  mov     dword ptr [rsp+0A8h+var_68], ebx
0x1401caf4b  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401caf52  mov     [rsp+0A8h+var_70], rax
0x1401caf57  mov     [rsp+0A8h+var_78], 0Bh
0x1401caf5e  mov     [rsp+0A8h+var_80], r15d
0x1401caf63  mov     [rsp+0A8h+var_88], r15b
0x1401caf68  mov     r8b, r12b
0x1401caf6b  mov     dl, sil
0x1401caf6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401caf75  mov     rcx, [rcx+18h]
0x1401caf79  call    WPP_RECORDER_AND_TRACE_SF_D
0x1401caf7e  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401caf83  movsxd  rax, r14d
0x1401caf86  add     rsp, 70h
0x1401caf8a  pop     r15
0x1401caf8c  pop     r14
0x1401caf8e  pop     r13
0x1401caf90  pop     r12
0x1401caf92  pop     rdi
0x1401caf93  pop     rsi
0x1401caf94  pop     rbx
0x1401caf95  retn
0x140239927  push    rbp
0x140239929  sub     rsp, 50h
0x14023992d  mov     rbp, rdx
0x140239930  mov     rax, [rcx]
0x140239933  mov     ecx, [rax]
0x140239935  mov     [rbp+58h], ecx
0x140239938  mov     ecx, [rbp+58h]
0x14023993b  call    SetLastNtError
0x140239940  mov     dword ptr [rbp+60h], 1
0x140239947  mov     eax, [rbp+60h]
0x14023994a  add     rsp, 50h
0x14023994e  pop     rbp
0x14023994f  retn
```
