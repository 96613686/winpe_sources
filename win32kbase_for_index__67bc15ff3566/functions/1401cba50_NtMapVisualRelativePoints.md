# NtMapVisualRelativePoints

- ea: `0x1401cba50`
- end: `0x1401cbd67`
- name: `NtMapVisualRelativePoints`
- size: `791`
- prototype: `__int64 __fastcall(int, int, int, int, volatile void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140029710`
- `0x14004c020`
- `0x14004f4c0`
- `0x14006f3a4`
- `0x1400700d8`
- `0x1400701d4`
- `0x1400a5ba0`
- `0x14018c020`
- `0x1401aab9c`
- `0x1401cb0f4`
- `0x1401cba50`
- `0x1401cbd70`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401cbbf3`
- `ntoskrnl!ProbeForRead` at `0x1401cbbf3`
- `ntoskrnl!ProbeForWrite` at `0x1401cbc25`
- `ntoskrnl!ProbeForWrite` at `0x1401cbc25`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cbbca`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cbbff`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cbbca`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cbbff`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401cbc74`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401cbc74`
- `WIN32K!W32GetUserSessionState` at `0x1401cba72`
- `WIN32K!W32GetUserSessionState` at `0x1401cbb4c`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd04`
- `WIN32K!W32GetUserSessionState` at `0x1401cba72`
- `WIN32K!W32GetUserSessionState` at `0x1401cbb4c`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd04`

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
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  CTouchProcessor *v20; // rcx
  __int64 v21; // r8
  int i; // ebx
  NTSTATUS v23; // eax
  int v24; // r14d
  ULONG v25; // eax
  bool v26; // r12
  char LastError; // bl
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  unsigned int v37; // [rsp+C0h] [rbp+18h]

  v37 = a3;
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
  if ( 8 * (unsigned __int64)v37 > 0xFFFFFFFF )
  {
    v24 = 0;
    UserSetLastError(8);
  }
  else
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process(0xFFFFFFFFLL);
    ProbeForRead(a4, 8 * v37, CurrentProcessWow64Process != 0 ? 1 : 4);
    v18 = PsGetCurrentProcessWow64Process(v17);
    ProbeForWrite(a5, 8 * v37, v18 != 0 ? 1 : 4);
    for ( i = 0; i != v37; ++i )
    {
      v23 = KernelMapVisualRelativePoint(
              a1,
              a2,
              (const struct VisualPoint *)&a4[8 * i],
              (struct VisualPoint *)&a5[8 * i]);
      if ( v23 < 0 )
      {
        v24 = 0;
        v25 = RtlNtStatusToDosError(v23);
        UserSetLastError(v25);
        goto LABEL_22;
      }
    }
    v24 = 1;
  }
LABEL_22:
  if ( !v24 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      v9 = 0;
    }
    v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LastError = UserGetLastError();
      v31 = W32GetUserSessionState(v29, v28, v30);
      LOBYTE(v32) = v26;
      LOBYTE(v33) = v9;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v33,
        v32,
        *(_QWORD *)(v31 + 69136),
        2,
        2,
        11,
        (__int64)WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids,
        LastError);
    }
  }
  UserSessionSwitchLeaveCritWithNonPaged((__int64)v20, v19, v21);
  return v24;
}

```

## disassembly

```asm
0x1401cba50  mov     rax, rsp
0x1401cba53  mov     [rax+20h], r9
0x1401cba57  mov     [rax+18h], r8d
0x1401cba5b  mov     [rax+10h], rdx
0x1401cba5f  mov     [rax+8], rcx
0x1401cba63  push    rbx
0x1401cba64  push    rsi
0x1401cba65  push    rdi
0x1401cba66  push    r12
0x1401cba68  push    r13
0x1401cba6a  push    r14
0x1401cba6c  push    r15
0x1401cba6e  sub     rsp, 70h
0x1401cba72  call    cs:__imp_W32GetUserSessionState
0x1401cba79  nop     dword ptr [rax+rax+00h]
0x1401cba7e  mov     r14, rax
0x1401cba81  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cba88  xor     r8d, r8d
0x1401cba8b  xor     edx, edx
0x1401cba8d  mov     rcx, rax
0x1401cba90  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cba95  mov     [r14+10h], rax
0x1401cba99  xor     edi, edi
0x1401cba9b  lea     esi, [rdi+1]
0x1401cba9e  lea     r15d, [rdi+2]
0x1401cbaa2  test    rax, rax
0x1401cbaa5  jz      short loc_1401CBB0A
0x1401cbaa7  mov     rbx, [r14+4C58h]
0x1401cbaae  test    rbx, rbx
0x1401cbab1  jz      short loc_1401CBAF2
0x1401cbab3  mov     rax, [rbx+10h]
0x1401cbab7  mov     [r14+4C58h], rax
0x1401cbabe  mov     [rbx+10h], rdi
0x1401cbac2  mov     rax, [rbx]
0x1401cbac5  cmp     [rax+8], esi
0x1401cbac8  jnb     short loc_1401CBAE8
0x1401cbaca  mov     [rsp+0A8h+var_58], 20000h
0x1401cbad2  mov     r8d, 1236h
0x1401cbad8  mov     edx, [rsp+0A8h+var_58]
0x1401cbadc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401cbae3  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401cbae8  mov     rcx, [rbx]
0x1401cbaeb  call    HMUnlockObject
0x1401cbaf0  jmp     short loc_1401CBAA7
0x1401cbaf2  lea     rcx, [r14+4C78h]
0x1401cbaf9  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbafe  lea     rcx, [r14+4C68h]
0x1401cbb05  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cbb0a  lea     r12, WPP_GLOBAL_Control
0x1401cbb11  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cbb18  cmp     rcx, r12
0x1401cbb1b  jz      short loc_1401CBB2E
0x1401cbb1d  mov     eax, [rcx+2Ch]
0x1401cbb20  test    r15b, al
0x1401cbb23  jz      short loc_1401CBB2E
0x1401cbb25  cmp     byte ptr [rcx+29h], 4
0x1401cbb29  mov     bl, sil
0x1401cbb2c  jnb     short loc_1401CBB31
0x1401cbb2e  mov     bl, dil
0x1401cbb31  lea     r13, WPP_RECORDER_INITIALIZED
0x1401cbb38  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401cbb3f  setnz   r14b
0x1401cbb43  test    bl, bl
0x1401cbb45  jnz     short loc_1401CBB4C
0x1401cbb47  test    r14b, r14b
0x1401cbb4a  jz      short loc_1401CBBAB
0x1401cbb4c  call    cs:__imp_W32GetUserSessionState
0x1401cbb53  nop     dword ptr [rax+rax+00h]
0x1401cbb58  mov     r9, [rax+10E10h]
0x1401cbb5f  mov     rax, [rsp+0A8h+arg_8]
0x1401cbb67  mov     [rsp+0A8h+var_60], rax
0x1401cbb6c  mov     rax, [rsp+0A8h+arg_0]
0x1401cbb74  mov     [rsp+0A8h+var_68], rax
0x1401cbb79  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401cbb80  mov     [rsp+0A8h+var_70], rax
0x1401cbb85  mov     [rsp+0A8h+var_78], 0Ah
0x1401cbb8c  mov     [rsp+0A8h+var_80], r15d
0x1401cbb91  mov     [rsp+0A8h+var_88], 4
0x1401cbb96  mov     r8b, r14b
0x1401cbb99  mov     dl, bl
0x1401cbb9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cbba2  mov     rcx, [rcx+18h]
0x1401cbba6  call    WPP_RECORDER_AND_TRACE_SF_ii
0x1401cbbab  mov     eax, [rsp+0A8h+arg_10]
0x1401cbbb2  shl     rax, 3
0x1401cbbb6  mov     ecx, 0FFFFFFFFh
0x1401cbbbb  cmp     rax, rcx
0x1401cbbbe  ja      loc_1401CBCB5
0x1401cbbc4  mov     [rsp+0A8h+var_58], edi
0x1401cbbc8  mov     ebx, eax
0x1401cbbca  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cbbd1  nop     dword ptr [rax+rax+00h]
0x1401cbbd6  neg     rax
0x1401cbbd9  sbb     r8d, r8d
0x1401cbbdc  mov     r14d, 0FFFFFFFDh
0x1401cbbe2  and     r8d, r14d
0x1401cbbe5  add     r8d, 4; Alignment
0x1401cbbe9  mov     edx, ebx; Length
0x1401cbbeb  mov     rcx, [rsp+0A8h+Address]; Address
0x1401cbbf3  call    cs:__imp_ProbeForRead
0x1401cbbfa  nop     dword ptr [rax+rax+00h]
0x1401cbbff  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cbc06  nop     dword ptr [rax+rax+00h]
0x1401cbc0b  neg     rax
0x1401cbc0e  sbb     r8d, r8d
0x1401cbc11  and     r8d, r14d
0x1401cbc14  add     r8d, 4; Alignment
0x1401cbc18  mov     edx, ebx; Length
0x1401cbc1a  mov     r14, [rsp+0A8h+arg_20]
0x1401cbc22  mov     rcx, r14; Address
0x1401cbc25  call    cs:__imp_ProbeForWrite
0x1401cbc2c  nop     dword ptr [rax+rax+00h]
0x1401cbc31  mov     ebx, edi
0x1401cbc33  mov     [rsp+0A8h+var_54], ebx
0x1401cbc37  cmp     ebx, [rsp+0A8h+arg_10]
0x1401cbc3e  jz      short loc_1401CBC8D
0x1401cbc40  mov     eax, ebx
0x1401cbc42  lea     r9, [r14+rax*8]; struct VisualPoint *
0x1401cbc46  mov     rcx, [rsp+0A8h+Address]
0x1401cbc4e  lea     r8, [rcx+rax*8]; struct VisualPoint *
0x1401cbc52  mov     rdx, [rsp+0A8h+arg_8]; void *
0x1401cbc5a  mov     rcx, [rsp+0A8h+arg_0]; void *
0x1401cbc62  call    ?KernelMapVisualRelativePoint@@YAJ_J0PEBUVisualPoint@@PEAU1@@Z; KernelMapVisualRelativePoint(__int64,__int64,VisualPoint const *,VisualPoint *)
0x1401cbc67  test    eax, eax
0x1401cbc69  jns     short loc_1401CBC89
0x1401cbc6b  mov     r14d, edi
0x1401cbc6e  mov     [rsp+0A8h+var_44], edi
0x1401cbc72  mov     ecx, eax; Status
0x1401cbc74  call    cs:__imp_RtlNtStatusToDosError
0x1401cbc7b  nop     dword ptr [rax+rax+00h]
0x1401cbc80  mov     ecx, eax
0x1401cbc82  call    UserSetLastError
0x1401cbc87  jmp     short loc_1401CBCC2
0x1401cbc89  add     ebx, esi
0x1401cbc8b  jmp     short loc_1401CBC33
0x1401cbc8d  mov     r14d, esi
0x1401cbc90  jmp     short loc_1401CBCC2
0x1401cbc92  mov     r14d, [rsp+0A8h+var_58]
0x1401cbc97  mov     [rsp+0A8h+var_44], r14d
0x1401cbc9c  xor     edi, edi
0x1401cbc9e  lea     esi, [rdi+1]
0x1401cbca1  lea     r15d, [rdi+2]
0x1401cbca5  lea     r12, WPP_GLOBAL_Control
0x1401cbcac  lea     r13, WPP_RECORDER_INITIALIZED
0x1401cbcb3  jmp     short loc_1401CBCC2
0x1401cbcb5  mov     r14d, edi
0x1401cbcb8  mov     ecx, 8
0x1401cbcbd  call    UserSetLastError
0x1401cbcc2  test    r14d, r14d
0x1401cbcc5  jnz     loc_1401CBD4E
0x1401cbccb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cbcd2  cmp     rcx, r12
0x1401cbcd5  jz      short loc_1401CBCE5
0x1401cbcd7  mov     eax, [rcx+2Ch]
0x1401cbcda  test    r15b, al
0x1401cbcdd  jz      short loc_1401CBCE5
0x1401cbcdf  cmp     [rcx+29h], r15b
0x1401cbce3  jnb     short loc_1401CBCE8
0x1401cbce5  mov     sil, dil
0x1401cbce8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401cbcef  setnz   r12b
0x1401cbcf3  test    sil, sil
0x1401cbcf6  jnz     short loc_1401CBCFD
0x1401cbcf8  test    r12b, r12b
0x1401cbcfb  jz      short loc_1401CBD4E
0x1401cbcfd  call    UserGetLastError
0x1401cbd02  mov     ebx, eax
0x1401cbd04  call    cs:__imp_W32GetUserSessionState
0x1401cbd0b  nop     dword ptr [rax+rax+00h]
0x1401cbd10  mov     r9, [rax+10E10h]
0x1401cbd17  mov     dword ptr [rsp+0A8h+var_68], ebx
0x1401cbd1b  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401cbd22  mov     [rsp+0A8h+var_70], rax
0x1401cbd27  mov     [rsp+0A8h+var_78], 0Bh
0x1401cbd2e  mov     [rsp+0A8h+var_80], r15d
0x1401cbd33  mov     [rsp+0A8h+var_88], r15b
0x1401cbd38  mov     r8b, r12b
0x1401cbd3b  mov     dl, sil
0x1401cbd3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cbd45  mov     rcx, [rcx+18h]
0x1401cbd49  call    WPP_RECORDER_AND_TRACE_SF_D
0x1401cbd4e  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cbd53  movsxd  rax, r14d
0x1401cbd56  add     rsp, 70h
0x1401cbd5a  pop     r15
0x1401cbd5c  pop     r14
0x1401cbd5e  pop     r13
0x1401cbd60  pop     r12
0x1401cbd62  pop     rdi
0x1401cbd63  pop     rsi
0x1401cbd64  pop     rbx
0x1401cbd65  retn
0x14023a0ca  push    rbp
0x14023a0cc  sub     rsp, 50h
0x14023a0d0  mov     rbp, rdx
0x14023a0d3  mov     rax, [rcx]
0x14023a0d6  mov     ecx, [rax]
0x14023a0d8  mov     [rbp+58h], ecx
0x14023a0db  mov     ecx, [rbp+58h]
0x14023a0de  call    SetLastNtError
0x14023a0e3  mov     dword ptr [rbp+60h], 1
0x14023a0ea  mov     eax, [rbp+60h]
0x14023a0ed  add     rsp, 50h
0x14023a0f1  pop     rbp
0x14023a0f2  retn
```
